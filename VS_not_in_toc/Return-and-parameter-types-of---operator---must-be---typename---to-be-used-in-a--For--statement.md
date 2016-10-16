---
title: "Return and parameter types of &#39;&lt;operator&gt;&#39; must be &#39;&lt;typename&gt;&#39; to be used in a &#39;For&#39; statement"
ms.custom: na
ms.date: 10/01/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-csharp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 30e8cfa8-c086-474c-a4f0-ad01d01096e2
caps.latest.revision: 9
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
# Return and parameter types of &#39;&lt;operator&gt;&#39; must be &#39;&lt;typename&gt;&#39; to be used in a &#39;For&#39; statement
A `For` loop specifies a counter variable of a type that does not define the `+` or `-` operator with parameters and return value of its own type.  
  
 The counter variable must be of a type that supports addition (`+`) and subtraction (`-`) operators that operate completely on their containing type. This means both of the operands and the return value must be of the type of the counter variable.  
  
 If you use a numeric data type for the counter variable, the `+` and `-` operators are supported on the containing type. If you use a user-defined class or structure, you must define both operators with operands and return value of the type of your class or structure.  
  
 **Error ID:** BC33039  
  
### To correct this error  
  
1.  Make sure the spelling of the counter-variable data type is correct.  
  
2.  If you are using a user-defined class or structure for the counter variable, define `+` and `-` operators that operate completely on that class or structure.  
  
## See Also  
 [For...Next Statement](../Topic/For...Next%20Statement%20\(Visual%20Basic\).md)   
 [Operator Procedures](../Topic/Operator%20Procedures%20\(Visual%20Basic\).md)   
 [Operator Statement](../Topic/Operator%20Statement.md)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)