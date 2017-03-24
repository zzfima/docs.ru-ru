---
title: "#region (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "#region"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#region - директива [C#]"
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# #region (Справочник по C#)
Директива `#region` позволяет указать блок кода, который можно разворачивать и сворачивать с помощью функции [структурирования](/visual-studio/ide/outlining) в редакторе кода Visual Studio.  В больших файлах кода очень удобно сворачивать или скрывать одну или несколько областей, чтобы не отвлекать внимание от той части файла, над которой в настоящее время идет работа.  В следующем примере показано, как определить область.  
  
```  
  
      #region MyClass definition  
public class MyClass   
{  
    static void Main()   
    {  
    }  
}  
#endregion  
```  
  
## Заметки  
 В конце блока `#region` должна присутствовать директива [\#endregion](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md).  
  
 Блок `#region` не может накладываться на блок [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md).  Однако блок `#region` можно вложить в блок `#if`, а блок `#if` – в блок `#region`.  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Директивы препроцессора C\#](../../../csharp/language-reference/preprocessor-directives/index.md)