---
title: Руководство по программированию на C#. Использование оператора foreach с массивами
ms.custom: seodec18
ms.date: 05/23/2018
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: a290cd709dd6491981658f467fa0163011290128
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53238472"
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a><span data-ttu-id="f9128-102">Использование оператора foreach с массивами (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="f9128-102">Using foreach with arrays (C# Programming Guide)</span></span>

<span data-ttu-id="f9128-103">Оператор [foreach](../../language-reference/keywords/foreach-in.md) обеспечивает простой и понятный способ итерации по элементам массива или любой перечислимой коллекции.</span><span class="sxs-lookup"><span data-stu-id="f9128-103">The [foreach](../../language-reference/keywords/foreach-in.md) statement provides a simple, clean way to iterate through the elements of an array.</span></span>

<span data-ttu-id="f9128-104">Для одномерных массивов оператор `foreach` обрабатывает элементы в порядке возрастания индекса, начиная с индекса 0 и заканчивая индексом `Length - 1`:</span><span class="sxs-lookup"><span data-stu-id="f9128-104">For single-dimensional arrays, the `foreach` statement processes elements in increasing index order, starting with index 0 and ending with index `Length - 1`:</span></span>

[!code-csharp[csProgGuideArrays#28](./codesnippet/CSharp/using-foreach-with-arrays_1.cs)]

<span data-ttu-id="f9128-105">Для многомерных массивов элементов обрабатываются так, что сначала увеличиваются индексы крайнего правого измерения, а затем — следующего левого и т. д. влево:</span><span class="sxs-lookup"><span data-stu-id="f9128-105">For multi-dimensional arrays, elements are traversed such that the indices of the rightmost dimension are increased first, then the next left dimension, and so on to the left:</span></span>

[!code-csharp[csProgGuideArrays#29](./codesnippet/CSharp/using-foreach-with-arrays_2.cs)]

<span data-ttu-id="f9128-106">Тем не менее для управления порядком обрабатываемых элементов в многомерных массивах можно использовать вложенный цикл [for](../../language-reference/keywords/for.md).</span><span class="sxs-lookup"><span data-stu-id="f9128-106">However, with multidimensional arrays, using a nested [for](../../language-reference/keywords/for.md) loop gives you more control over the order in which to process the array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9128-107">См. также</span><span class="sxs-lookup"><span data-stu-id="f9128-107">See Also</span></span>

- <xref:System.Array>  
- [<span data-ttu-id="f9128-108">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f9128-108">C# Programming Guide</span></span>](../index.md)  
- [<span data-ttu-id="f9128-109">Массивы</span><span class="sxs-lookup"><span data-stu-id="f9128-109">Arrays</span></span>](index.md)  
- [<span data-ttu-id="f9128-110">Одномерные массивы</span><span class="sxs-lookup"><span data-stu-id="f9128-110">Single-Dimensional Arrays</span></span>](single-dimensional-arrays.md)  
- [<span data-ttu-id="f9128-111">Многомерные массивы</span><span class="sxs-lookup"><span data-stu-id="f9128-111">Multidimensional Arrays</span></span>](multidimensional-arrays.md)  
- [<span data-ttu-id="f9128-112">Массивы массивов</span><span class="sxs-lookup"><span data-stu-id="f9128-112">Jagged Arrays</span></span>](jagged-arrays.md)
