---
title: "Использование оператора foreach с массивами (Руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 797cb9a63a5e1009b170b2afda8634bd21a50035
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a>Использование оператора foreach с массивами (Руководство по программированию на C#)
В C# также предусмотрен оператор [foreach](../../../csharp/language-reference/keywords/foreach-in.md). Этот оператор обеспечивает простой и понятный способ итерации по элементам массива или любой перечислимой коллекции. Оператор `foreach` обрабатывает элементы в порядке, возвращенном массивом или перечислителем типа коллекции, обычно от нулевого до последнего элемента. Например, следующий код создает массив `numbers` и осуществляет итерацию по нему с помощью оператора `foreach`.  
  
 [!code-csharp[csProgGuideArrays#28](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_1.cs)]  
  
 Этот же метод можно использовать для итерации по элементам в многомерных массивах, например:  
  
 [!code-csharp[csProgGuideArrays#29](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_2.cs)]  
  
 Однако для лучшего управления элементами в многомерных массивах можно использовать вложенный цикл [for](../../../csharp/language-reference/keywords/for.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Array>  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Массивы](../../../csharp/programming-guide/arrays/index.md)  
 [Одномерные массивы](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [Многомерные массивы](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [Массивы массивов](../../../csharp/programming-guide/arrays/jagged-arrays.md)
