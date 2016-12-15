---
title: "Использование оператора foreach с массивами (Руководство по программированию на C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "массивы [C#], foreach"
  - "foreach - оператор [C#], использование с массивами"
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Использование оператора foreach с массивами (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В C\# также предусмотрен оператор [foreach](../../../csharp/language-reference/keywords/foreach-in.md).  Этот оператор обеспечивает простой и понятный способ итерации по элементам массива или любой перечислимой коллекции.  Оператор `foreach` обрабатывает элементы в порядке, возвращенном массивом или перечислителем типа коллекции, обычно от нулевого до последнего элемента.  Например, следующий код создает массив `numbers` и осуществляет итерацию по нему с помощью оператора `foreach`.  
  
 [!code-cs[csProgGuideArrays#28](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_1.cs)]  
  
 Этот же метод можно использовать для итерации по элементам в многомерных массивах, например:  
  
 [!code-cs[csProgGuideArrays#29](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_2.cs)]  
  
 Однако для лучшего управления элементами в многомерных массивах можно использовать вложенный цикл [for](../../../csharp/language-reference/keywords/for.md).  
  
## См. также  
 <xref:System.Array>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Массивы](../../../csharp/programming-guide/arrays/index.md)   
 [Одномерные массивы](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [Многомерные массивы](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [Массивы массивов](../../../csharp/programming-guide/arrays/jagged-arrays.md)