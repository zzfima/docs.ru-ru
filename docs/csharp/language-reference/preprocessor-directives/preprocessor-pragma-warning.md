---
title: "#pragma warning (Справочник по C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "#pragma warning"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#pragma warning [C#]"
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
caps.latest.revision: 17
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# #pragma warning (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`#pragma warning` позволяет включать или отключать определенные предупреждения.  
  
## Синтаксис  
  
```  
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
#### Параметры  
 `warning-list`  
 Список номеров предупреждений с разделителями\-запятыми.  Вводите номер без префикса “CS”.  
  
 Если номера предупреждений не указаны, `disable` отключает все предупреждения, а `restore` включает все предупреждения.  
  
> [!NOTE]
>  Чтобы найти номера предупреждений в Visual Studio, создайте проект и ищите номера предупреждений в окне **Вывод**.  
  
## Пример  
  
```  
// pragma_warning.cs  
using System;  
  
#pragma warning disable 414, 3021  
[CLSCompliant(false)]  
public class C  
{  
    int i = 1;  
    static void Main()  
    {  
    }  
}  
#pragma warning restore 3021  
[CLSCompliant(false)]  // CS3021  
public class D  
{  
    int i = 1;  
    public static void F()  
    {  
    }  
}  
```  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Директивы препроцессора C\#](../../../csharp/language-reference/preprocessor-directives/index.md)   
 [C\# Compiler Errors](../../../csharp/language-reference/compiler-messages/index.md)