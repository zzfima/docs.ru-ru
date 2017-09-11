---
title: "Массивы массивов (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- jagged arrays [C#]
- arrays [C#], jagged
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: cb6c0823af37924235dba7daa20e607cb8402a79
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="jagged-arrays-c-programming-guide"></a><span data-ttu-id="1a978-102">Массивы массивов (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="1a978-102">Jagged Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="1a978-103">Массив массивов — это массив, элементы которого сами являются массивами.</span><span class="sxs-lookup"><span data-stu-id="1a978-103">A jagged array is an array whose elements are arrays.</span></span> <span data-ttu-id="1a978-104">Элементы массива массивов могут иметь различные измерения и размеры.</span><span class="sxs-lookup"><span data-stu-id="1a978-104">The elements of a jagged array can be of different dimensions and sizes.</span></span> <span data-ttu-id="1a978-105">Массив массивов иногда называется нерегулярным массивом.</span><span class="sxs-lookup"><span data-stu-id="1a978-105">A jagged array is sometimes called an "array of arrays."</span></span> <span data-ttu-id="1a978-106">В следующих примерах показано, как объявлять и инициализировать массивы массивов, а также получать доступ к ним.</span><span class="sxs-lookup"><span data-stu-id="1a978-106">The following examples show how to declare, initialize, and access jagged arrays.</span></span>  
  
 <span data-ttu-id="1a978-107">Ниже объявляется одномерный массив из трех элементов, каждый из которых является одномерным массивом целых чисел:</span><span class="sxs-lookup"><span data-stu-id="1a978-107">The following is a declaration of a single-dimensional array that has three elements, each of which is a single-dimensional array of integers:</span></span>  
  
 <span data-ttu-id="1a978-108">[!code-cs[csProgGuideArrays#19](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="1a978-108">[!code-cs[csProgGuideArrays#19](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_1.cs)]</span></span>  
  
 <span data-ttu-id="1a978-109">Прежде чем использовать `jaggedArray`, его элементы необходимо инициализировать.</span><span class="sxs-lookup"><span data-stu-id="1a978-109">Before you can use `jaggedArray`, its elements must be initialized.</span></span> <span data-ttu-id="1a978-110">Это можно сделать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1a978-110">You can initialize the elements like this:</span></span>  
  
 <span data-ttu-id="1a978-111">[!code-cs[csProgGuideArrays#20](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="1a978-111">[!code-cs[csProgGuideArrays#20](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_2.cs)]</span></span>  
  
 <span data-ttu-id="1a978-112">Каждый элемент представляет собой одномерный массив целых чисел.</span><span class="sxs-lookup"><span data-stu-id="1a978-112">Each of the elements is a single-dimensional array of integers.</span></span> <span data-ttu-id="1a978-113">Первый из них содержит 5 целых чисел, второй — 4, а третий — 2.</span><span class="sxs-lookup"><span data-stu-id="1a978-113">The first element is an array of 5 integers, the second is an array of 4 integers, and the third is an array of 2 integers.</span></span>  
  
 <span data-ttu-id="1a978-114">Кроме того, с помощью инициализаторов можно заполнять элементы массива значениями (при этом вам не потребуется знать размер массива).</span><span class="sxs-lookup"><span data-stu-id="1a978-114">It is also possible to use initializers to fill the array elements with values, in which case you do not need the array size.</span></span> <span data-ttu-id="1a978-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="1a978-115">For example:</span></span>  
  
 <span data-ttu-id="1a978-116">[!code-cs[csProgGuideArrays#21](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="1a978-116">[!code-cs[csProgGuideArrays#21](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_3.cs)]</span></span>  
  
 <span data-ttu-id="1a978-117">Также массив можно инициализировать при объявлении, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="1a978-117">You can also initialize the array upon declaration like this:</span></span>  
  
 <span data-ttu-id="1a978-118">[!code-cs[csProgGuideArrays#22](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="1a978-118">[!code-cs[csProgGuideArrays#22](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_4.cs)]</span></span>  
  
 <span data-ttu-id="1a978-119">Можно использовать следующую краткую форму.</span><span class="sxs-lookup"><span data-stu-id="1a978-119">You can use the following shorthand form.</span></span> <span data-ttu-id="1a978-120">Обратите внимание, что при инициализации элементов нельзя опускать оператор `new`, поскольку механизм инициализации по умолчанию для них не предусмотрен:</span><span class="sxs-lookup"><span data-stu-id="1a978-120">Notice that you cannot omit the `new` operator from the elements initialization because there is no default initialization for the elements:</span></span>  
  
 <span data-ttu-id="1a978-121">[!code-cs[csProgGuideArrays#23](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="1a978-121">[!code-cs[csProgGuideArrays#23](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_5.cs)]</span></span>  
  
 <span data-ttu-id="1a978-122">В массиве массивов элементы являются ссылочными типами и инициализируются значением `null`.</span><span class="sxs-lookup"><span data-stu-id="1a978-122">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>  
  
 <span data-ttu-id="1a978-123">Доступ к отдельным элементам массива можно получить способами, показанными в следующих примерах:</span><span class="sxs-lookup"><span data-stu-id="1a978-123">You can access individual array elements like these examples:</span></span>  
  
 <span data-ttu-id="1a978-124">[!code-cs[csProgGuideArrays#24](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="1a978-124">[!code-cs[csProgGuideArrays#24](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_6.cs)]</span></span>  
  
 <span data-ttu-id="1a978-125">Массивы массивов и многомерные массивы можно смешивать.</span><span class="sxs-lookup"><span data-stu-id="1a978-125">It is possible to mix jagged and multidimensional arrays.</span></span> <span data-ttu-id="1a978-126">Ниже показаны объявление и инициализация одномерного массива массивов, элементами которого являются двухмерные массивы разного размера.</span><span class="sxs-lookup"><span data-stu-id="1a978-126">The following is a declaration and initialization of a single-dimensional jagged array that contains three two-dimensional array elements of different sizes.</span></span> <span data-ttu-id="1a978-127">Дополнительные сведения о двумерных массивах см. в разделе [Многомерные массивы](../../../csharp/programming-guide/arrays/multidimensional-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="1a978-127">For more information about two-dimensional arrays, see [Multidimensional Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md).</span></span>  
  
 <span data-ttu-id="1a978-128">[!code-cs[csProgGuideArrays#25](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="1a978-128">[!code-cs[csProgGuideArrays#25](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_7.cs)]</span></span>  
  
 <span data-ttu-id="1a978-129">В этом примере демонстрируется доступ к отдельным элементам, для чего отображается значение элемента `[1,0]` первого массива (`5`):</span><span class="sxs-lookup"><span data-stu-id="1a978-129">You can access individual elements as shown in this example, which displays the value of the element `[1,0]` of the first array (value `5`):</span></span>  
  
 <span data-ttu-id="1a978-130">[!code-cs[csProgGuideArrays#26](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="1a978-130">[!code-cs[csProgGuideArrays#26](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_8.cs)]</span></span>  
  
 <span data-ttu-id="1a978-131">Метод `Length` возвращает число массивов, содержащихся в массиве массивов.</span><span class="sxs-lookup"><span data-stu-id="1a978-131">The method `Length` returns the number of arrays contained in the jagged array.</span></span> <span data-ttu-id="1a978-132">Допустим, предыдущий массив был объявлен с использованием следующей строки:</span><span class="sxs-lookup"><span data-stu-id="1a978-132">For example, assuming you have declared the previous array, this line:</span></span>  
  
 <span data-ttu-id="1a978-133">[!code-cs[csProgGuideArrays#27](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="1a978-133">[!code-cs[csProgGuideArrays#27](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_9.cs)]</span></span>  
  
 <span data-ttu-id="1a978-134">возвращает значение 3.</span><span class="sxs-lookup"><span data-stu-id="1a978-134">returns a value of 3.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a978-135">Пример</span><span class="sxs-lookup"><span data-stu-id="1a978-135">Example</span></span>  
 <span data-ttu-id="1a978-136">В этом примере создается массив, элементы которого являются массивами.</span><span class="sxs-lookup"><span data-stu-id="1a978-136">This example builds an array whose elements are themselves arrays.</span></span> <span data-ttu-id="1a978-137">Все элементы массива имеют разный размер.</span><span class="sxs-lookup"><span data-stu-id="1a978-137">Each one of the array elements has a different size.</span></span>  
  
 <span data-ttu-id="1a978-138">[!code-cs[csProgGuideArrays#18](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_10.cs)]</span><span class="sxs-lookup"><span data-stu-id="1a978-138">[!code-cs[csProgGuideArrays#18](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_10.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a978-139">См. также</span><span class="sxs-lookup"><span data-stu-id="1a978-139">See Also</span></span>  
 <span data-ttu-id="1a978-140"><xref:System.Array></span><span class="sxs-lookup"><span data-stu-id="1a978-140"><xref:System.Array></span></span>   
 <span data-ttu-id="1a978-141">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1a978-141">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="1a978-142">[Массивы](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="1a978-142">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="1a978-143">[Одномерные массивы](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="1a978-143">[Single-Dimensional Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span></span>  
 [<span data-ttu-id="1a978-144">Многомерные массивы</span><span class="sxs-lookup"><span data-stu-id="1a978-144">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)

