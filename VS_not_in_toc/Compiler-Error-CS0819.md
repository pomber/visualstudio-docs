---
title: "Compiler Error CS0819"
ms.custom: na
ms.date: 10/01/2016
ms.devlang: 
  - CSharp
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-csharp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: a5369e03-eb7d-4c88-b390-51304bd8d1ae
caps.latest.revision: 7
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
# Compiler Error CS0819
Implicitly typed locals cannot have multiple declarators.  
  
 Multiple declarators are allowed in explicit type declarations, but not with implicitly typed variables.  
  
### To correct this error  
  
1.  Declare and assign a value to each implicitly typed local variable on a separate line.  
  
## Example  
 The following code generates CS0819:  
  
```  
// cs0819.cs  
class A  
{  
    public static int Main()  
    {  
        var a = 3, b = 2; // CS0819  
        return -1;  
    }  
}  
```  
  
## See Also  
 [Implicitly Typed Local Variables](../Topic/Implicitly%20Typed%20Local%20Variables%20\(C%23%20Programming%20Guide\).md)