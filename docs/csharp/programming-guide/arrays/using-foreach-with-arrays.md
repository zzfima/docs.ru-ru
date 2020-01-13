---
title: Руководство по программированию на C#. Использование оператора foreach с массивами
ms.date: 05/23/2018
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: bb121b0f5d990ef6e596b34a45606e2abde6811a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705682"
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a><span data-ttu-id="25ce4-102">Использование оператора foreach с массивами (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="25ce4-102">Using foreach with arrays (C# Programming Guide)</span></span>

<span data-ttu-id="25ce4-103">Оператор [foreach](../../language-reference/keywords/foreach-in.md) обеспечивает простой и понятный способ итерации по элементам массива или любой перечислимой коллекции.</span><span class="sxs-lookup"><span data-stu-id="25ce4-103">The [foreach](../../language-reference/keywords/foreach-in.md) statement provides a simple, clean way to iterate through the elements of an array.</span></span>

<span data-ttu-id="25ce4-104">Для одномерных массивов оператор `foreach` обрабатывает элементы в порядке возрастания индекса, начиная с индекса 0 и заканчивая индексом `Length - 1`:</span><span class="sxs-lookup"><span data-stu-id="25ce4-104">For single-dimensional arrays, the `foreach` statement processes elements in increasing index order, starting with index 0 and ending with index `Length - 1`:</span></span>

 [!code-csharp[csProgGuideArrays#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#28)]

<span data-ttu-id="25ce4-105">Для многомерных массивов элементов обрабатываются так, что сначала увеличиваются индексы крайнего правого измерения, а затем — следующего левого и т. д. влево:</span><span class="sxs-lookup"><span data-stu-id="25ce4-105">For multi-dimensional arrays, elements are traversed such that the indices of the rightmost dimension are increased first, then the next left dimension, and so on to the left:</span></span>

 [!code-csharp[csProgGuideArrays#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#29)]

<span data-ttu-id="25ce4-106">Тем не менее для управления порядком обрабатываемых элементов в многомерных массивах можно использовать вложенный цикл [for](../../language-reference/keywords/for.md).</span><span class="sxs-lookup"><span data-stu-id="25ce4-106">However, with multidimensional arrays, using a nested [for](../../language-reference/keywords/for.md) loop gives you more control over the order in which to process the array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="25ce4-107">См. также</span><span class="sxs-lookup"><span data-stu-id="25ce4-107">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="25ce4-108">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="25ce4-108">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="25ce4-109">Массивы</span><span class="sxs-lookup"><span data-stu-id="25ce4-109">Arrays</span></span>](index.md)
- [<span data-ttu-id="25ce4-110">Одномерные массивы</span><span class="sxs-lookup"><span data-stu-id="25ce4-110">Single-Dimensional Arrays</span></span>](single-dimensional-arrays.md)
- [<span data-ttu-id="25ce4-111">Многомерные массивы</span><span class="sxs-lookup"><span data-stu-id="25ce4-111">Multidimensional Arrays</span></span>](multidimensional-arrays.md)
- [<span data-ttu-id="25ce4-112">Массивы массивов</span><span class="sxs-lookup"><span data-stu-id="25ce4-112">Jagged Arrays</span></span>](jagged-arrays.md)
