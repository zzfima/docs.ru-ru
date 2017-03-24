---
title: "Передача параметров (Руководство по программированию в C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "аргументы [C#]"
  - "C# - язык, параметры методов"
  - "методы [C#], передача параметров"
  - "параметры [C#], передача"
  - "передача параметров [C#]"
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# Передача параметров (Руководство по программированию в C#)
В C\# аргументы могут быть переданы параметрам либо по значению, либо по ссылке.  Передача по ссылке позволяет изменять и сохранять измененные значения параметров членов функций, методов, свойств, индексаторов, операторов и конструкторов в вызывающей среде.  Для передачи параметра по ссылке используйте ключевое слово `ref` или `out`.  Для простоты в этом примере используется только ключевое слово `ref`.  Дополнительные сведения об отличиях ключевых слов `ref` и `out` см. в разделах [ref](../../../csharp/language-reference/keywords/ref.md), [out](../../../csharp/language-reference/keywords/out.md) и [Передача массивов при помощи параметров ref и out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).  
  
 В следующем примере показано различие между значением и ссылочными параметрами.  
  
 [!code-cs[csProgGuideParameters#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-parameters_1.cs)]  
  
 Дополнительные сведения см. в следующих разделах.  
  
-   [Передача параметров типа значения](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md)  
  
-   [Передача параметров ссылочного типа](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Методы](../../../csharp/programming-guide/classes-and-structs/methods.md)