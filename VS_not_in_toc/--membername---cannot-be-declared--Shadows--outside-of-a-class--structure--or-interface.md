---
title: "&#39;&lt;membername&gt;&#39; cannot be declared &#39;Shadows&#39; outside of a class, structure, or interface"
ms.custom: na
ms.date: 10/01/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-csharp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 23e28894-5854-46ef-924d-f1cb6e81bcb1
caps.latest.revision: 8
manager: douge
translation.priority.ht: 
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - ru-ru
  - zh-cn
  - zh-tw
translation.priority.mt: 
  - cs-cz
  - pl-pl
  - pt-br
  - tr-tr
---
# &#39;&lt;membername&gt;&#39; cannot be declared &#39;Shadows&#39; outside of a class, structure, or interface
The `Shadows` keyword appears in a declaration at namespace, module, or file level. Shadowing is meaningful only within a programming element that can inherit from a base element.  
  
 **Error ID:** BC32200  
  
### To correct this error  
  
-   Remove the `Shadows` keyword, or move the declaration inside a class, structure, or interface.  
  
## See Also  
 [Shadows](../Topic/Shadows%20\(Visual%20Basic\).md)   
 [Shadowing in Visual Basic](../Topic/Shadowing%20in%20Visual%20Basic.md)