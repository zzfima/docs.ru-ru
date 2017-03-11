---
title: "#undef (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "#undef"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#undef - директива [C#]"
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# #undef (Справочник по C#)
Директива `#undef` позволяет отменить определение символа, который, при его использовании в качестве выражения, переданного директиве [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md), приведет к получению значения `false`.  
  
 Символ можно определить с помощью директивы [\#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) или параметра компилятора [\/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md).  Директива `#undef` должна находиться в файле перед использованием любых операторов, не являющихся директивами.  
  
## Пример  
  
```  
// preprocessor_undef.cs  
// compile with: /d:DEBUG  
#undef DEBUG  
using System;  
class MyClass   
{  
    static void Main()   
    {  
#if DEBUG  
        Console.WriteLine("DEBUG is defined");  
#else  
        Console.WriteLine("DEBUG is not defined");  
#endif  
    }  
}  
```  
  
  **DEBUG is not defined**   
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Директивы препроцессора C\#](../../../csharp/language-reference/preprocessor-directives/index.md)