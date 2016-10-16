---
title: "How to: Implement Error Markers"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "editors [Visual Studio SDK], legacy - error markers"
ms.assetid: e8e78514-5720-4fc2-aa43-00b6af482e38
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
translation.priority.mt: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# How to: Implement Error Markers
Error markers (or red wavy underlines) are the most difficult of the text editor customizations to implement. However, the benefits they give to users of your VSPackage can far outweigh the cost to provide them. Error markers subtly mark text that your language parser deems incorrect with a squiggly or wavy red line. This indicator helps programmers by visually displaying incorrect code.  
  
 Use text markers to implement the red wavy underlines. As a rule, language services add red wavy underlines to the text buffer as a background pass, either at idle time or in a background thread.  
  
### To implement the red wavy underline feature  
  
1.  Select the text under which you want place the red wavy underline.  
  
2.  Create a marker of the type `MARKER_CODESENSE_ERROR`. For more information, see [How to: Add Standard Text Markers](../extensibility/how-to--add-standard-text-markers.md).  
  
3.  After that, pass in an \<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> interface pointer.  
  
 This process also allows you to create tip text or a special context menu over a given marker. For more information, see [How to: Add Standard Text Markers](../extensibility/how-to--add-standard-text-markers.md).  
  
 The following objects are required before error markers can be displayed.  
  
-   A parser.  
  
-   A task provider (that is, an implementation of \<xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskProvider2>) that maintains a record of changes in line information in order to identify the lines to be re-parsed.  
  
-   A text view filter that captures caret change events from the view using the \<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEvents.OnChangeCaretLine*>) method.  
  
 The parser, task provider, and filter provide the infrastructure necessary to make error markers possible. The following steps provide the process for displaying error markers.  
  
1.  In a view that is being filtered, the filter obtains a pointer to the task provider associated with that view's data.  
  
    > [!NOTE]
    >  You can use the same command filter for method tips, statement completion, error markers, and so on.  
  
2.  When the filter receives an event indicating that you have moved to another line, a task is created to check for errors.  
  
3.  The task handler checks if the line is dirty. If so, it parses the line for errors.  
  
4.  If errors are found, the task provider creates a task item instance. This instance creates the text marker that the environment uses as an error marker in the text view.  
  
## See Also  
 [Using Text Markers with the Legacy API](../extensibility/using-text-markers-with-the-legacy-api.md)   
 [How to: Add Standard Text Markers](../extensibility/how-to--add-standard-text-markers.md)   
 [How to: Create Custom Text Markers](../extensibility/how-to--create-custom-text-markers.md)   
 [How to: Use Text Markers](../extensibility/how-to--use-text-markers.md)