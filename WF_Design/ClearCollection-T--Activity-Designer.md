---
title: "ClearCollection&lt;T&gt; Activity Designer"
ms.custom: na
ms.date: 10/02/2016
ms.prod: .net-framework-4.6
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: reference
ms.assetid: db0e5da2-7b5a-4f1a-864c-f3aeeeeb51a7
caps.latest.revision: 7
manager: erikre
translation.priority.ht: 
  - cs-cz
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - pl-pl
  - pt-br
  - ru-ru
  - tr-tr
  - zh-cn
  - zh-tw
---
# ClearCollection&lt;T&gt; Activity Designer
The **ClearCollection<T\>** activity designer is used to create and configure a <xref:System.Activities.Statements.ClearCollection`1?qualifyHint=False> activity.  
  
## The ClearCollection<T\> Activity  
 The <xref:System.Activities.Statements.ClearCollection`1?qualifyHint=False> activity clears a specified collection of all items.  
  
### Using the ClearCollection<T\> Activity Designer  
 The **ClearCollection<T\>** activity designer can be found in the **Collection** category of the **Toolbox**, which is accessed by clicking the **Toolbox** tab of the Workflow Designer (Alternatively, select **Toolbar** from the **View** menu or CTRL+ALT+X.)  
  
 The **ClearCollection<T\>** activity designer can be dragged from the **Toolbox** and dropped on to the Workflow Designer surface wherever activities are usually placed, such as inside a <xref:System.Activities.Statements.Sequence?qualifyHint=False>. This creates a <xref:System.Activities.Statements.ClearCollection`1?qualifyHint=False> activity with a default <xref:System.Activities.Activity.DisplayName?qualifyHint=False> of ClearCollection<Int32\>. (By default, the *TypeArgument* is **Int32**. This can be changed in the property grid.) The <xref:System.Activities.Activity.DisplayName?qualifyHint=False> value can be edited in the header of the **ClearCollection<T\>** activity designer or in the **DisplayName** box of the property grid. The other properties must be edited on the property grid.  
  
### The ClearCollection<T\> Properties  
 The following table shows the <xref:System.Activities.Statements.ClearCollection`1?qualifyHint=False> properties and describes how they are used in the designer.  
  
|Property Name|Required|Usage|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName?qualifyHint=False>|False|Specifies the optional friendly name of the <xref:System.Activities.Statements.ClearCollection`1?qualifyHint=False> activity. The default is ClearCollection<Int32\>. Although the <xref:System.Activities.Activity.DisplayName?qualifyHint=False> value is not strictly required, it is a best practice to use one.|  
|<xref:System.Activities.Statements.ClearCollection`1.Collection?qualifyHint=False>|True|Specifies the collection to be cleared of items. This collection is of type **ICollection<TypeArgument\>.** To specify the collection, type a Visual Basic expression in the property grid.|  
|*TypeArgument*|True|Specifies the type T of the items contained in the <xref:System.Collections.Generic.ICollection`1?qualifyHint=False>. By default, this *TypeArgument* type is set to **Int32**. To change the type, change the value of the *TypeArgument* in the combo box in the property grid.|  
  
## See Also  
 [Collection](../WF_Design/Collection-Activity-Designers.md)   
 [AddToCollection<T\>](../WF_Design/AddToCollection-T--Activity-Designer.md)   
 [ExistsInCollection<T\>](../WF_Design/ExistsInCollection-T--Activity-Designer.md)   
 [RemoveFromCollection<T\>](../WF_Design/RemoveFromCollection-T--Activity-Designer.md)