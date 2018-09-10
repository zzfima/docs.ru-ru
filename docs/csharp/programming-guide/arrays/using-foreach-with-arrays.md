---
title: Использование оператора foreach с массивами (Руководство по программированию на C#)
ms.date: 05/23/2018
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: 298ee915bbe11313f3b33ea7dae9353ef956a231
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43509539"
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a>Использование оператора foreach с массивами (Руководство по программированию на C#)

Оператор [foreach](../../language-reference/keywords/foreach-in.md) обеспечивает простой и понятный способ итерации по элементам массива или любой перечислимой коллекции.

Для одномерных массивов оператор `foreach` обрабатывает элементы в порядке возрастания индекса, начиная с индекса 0 и заканчивая индексом `Length - 1`:

[!code-csharp[csProgGuideArrays#28](./codesnippet/CSharp/using-foreach-with-arrays_1.cs)]

Для многомерных массивов элементов обрабатываются так, что сначала увеличиваются индексы крайнего правого измерения, а затем — следующего левого и т. д. влево:

[!code-csharp[csProgGuideArrays#29](./codesnippet/CSharp/using-foreach-with-arrays_2.cs)]

Тем не менее для управления порядком обрабатываемых элементов в многомерных массивах можно использовать вложенный цикл [for](../../language-reference/keywords/for.md).

## <a name="see-also"></a>См. также

- <xref:System.Array>  
- [Руководство по программированию на C#](../index.md)  
- [Массивы](index.md)  
- [Одномерные массивы](single-dimensional-arrays.md)  
- [Многомерные массивы](multidimensional-arrays.md)  
- [Массивы массивов](jagged-arrays.md)
