---
title: Массивы массивов (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- jagged arrays [C#]
- arrays [C#], jagged
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
ms.openlocfilehash: 2e4988439000712f4d1bd9b5abe412e7fd5d43eb
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2018
ms.locfileid: "46525192"
---
# <a name="jagged-arrays-c-programming-guide"></a><span data-ttu-id="d5443-102">Массивы массивов (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="d5443-102">Jagged Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="d5443-103">Массив массивов — это массив, элементы которого сами являются массивами.</span><span class="sxs-lookup"><span data-stu-id="d5443-103">A jagged array is an array whose elements are arrays.</span></span> <span data-ttu-id="d5443-104">Элементы массива массивов могут иметь различные измерения и размеры.</span><span class="sxs-lookup"><span data-stu-id="d5443-104">The elements of a jagged array can be of different dimensions and sizes.</span></span> <span data-ttu-id="d5443-105">Массив массивов иногда называется нерегулярным массивом.</span><span class="sxs-lookup"><span data-stu-id="d5443-105">A jagged array is sometimes called an "array of arrays."</span></span> <span data-ttu-id="d5443-106">В следующих примерах показано, как объявлять и инициализировать массивы массивов, а также получать доступ к ним.</span><span class="sxs-lookup"><span data-stu-id="d5443-106">The following examples show how to declare, initialize, and access jagged arrays.</span></span>  
  
 <span data-ttu-id="d5443-107">Ниже объявляется одномерный массив из трех элементов, каждый из которых является одномерным массивом целых чисел:</span><span class="sxs-lookup"><span data-stu-id="d5443-107">The following is a declaration of a single-dimensional array that has three elements, each of which is a single-dimensional array of integers:</span></span>  
  
 [!code-csharp[csProgGuideArrays#19](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_1.cs)]  
  
 <span data-ttu-id="d5443-108">Прежде чем использовать `jaggedArray`, его элементы необходимо инициализировать.</span><span class="sxs-lookup"><span data-stu-id="d5443-108">Before you can use `jaggedArray`, its elements must be initialized.</span></span> <span data-ttu-id="d5443-109">Это можно сделать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d5443-109">You can initialize the elements like this:</span></span>  
  
 [!code-csharp[csProgGuideArrays#20](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_2.cs)]  
  
 <span data-ttu-id="d5443-110">Каждый элемент представляет собой одномерный массив целых чисел.</span><span class="sxs-lookup"><span data-stu-id="d5443-110">Each of the elements is a single-dimensional array of integers.</span></span> <span data-ttu-id="d5443-111">Первый из них содержит 5 целых чисел, второй — 4, а третий — 2.</span><span class="sxs-lookup"><span data-stu-id="d5443-111">The first element is an array of 5 integers, the second is an array of 4 integers, and the third is an array of 2 integers.</span></span>  
  
 <span data-ttu-id="d5443-112">Кроме того, с помощью инициализаторов можно заполнять элементы массива значениями (при этом вам не потребуется знать размер массива).</span><span class="sxs-lookup"><span data-stu-id="d5443-112">It is also possible to use initializers to fill the array elements with values, in which case you do not need the array size.</span></span> <span data-ttu-id="d5443-113">Пример:</span><span class="sxs-lookup"><span data-stu-id="d5443-113">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#21](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_3.cs)]  
  
 <span data-ttu-id="d5443-114">Также массив можно инициализировать при объявлении, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="d5443-114">You can also initialize the array upon declaration like this:</span></span>  
  
 [!code-csharp[csProgGuideArrays#22](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_4.cs)]  
  
 <span data-ttu-id="d5443-115">Можно использовать следующую краткую форму.</span><span class="sxs-lookup"><span data-stu-id="d5443-115">You can use the following shorthand form.</span></span> <span data-ttu-id="d5443-116">Обратите внимание, что при инициализации элементов нельзя опускать оператор `new`, поскольку механизм инициализации по умолчанию для них не предусмотрен:</span><span class="sxs-lookup"><span data-stu-id="d5443-116">Notice that you cannot omit the `new` operator from the elements initialization because there is no default initialization for the elements:</span></span>  
  
 [!code-csharp[csProgGuideArrays#23](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_5.cs)]  
  
 <span data-ttu-id="d5443-117">В массиве массивов элементы являются ссылочными типами и инициализируются значением `null`.</span><span class="sxs-lookup"><span data-stu-id="d5443-117">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>  
  
 <span data-ttu-id="d5443-118">Доступ к отдельным элементам массива можно получить способами, показанными в следующих примерах:</span><span class="sxs-lookup"><span data-stu-id="d5443-118">You can access individual array elements like these examples:</span></span>  
  
 [!code-csharp[csProgGuideArrays#24](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_6.cs)]  
  
 <span data-ttu-id="d5443-119">Массивы массивов и многомерные массивы можно смешивать.</span><span class="sxs-lookup"><span data-stu-id="d5443-119">It is possible to mix jagged and multidimensional arrays.</span></span> <span data-ttu-id="d5443-120">Ниже показаны объявление и инициализация одномерного массива массивов, элементами которого являются двухмерные массивы разного размера.</span><span class="sxs-lookup"><span data-stu-id="d5443-120">The following is a declaration and initialization of a single-dimensional jagged array that contains three two-dimensional array elements of different sizes.</span></span> <span data-ttu-id="d5443-121">Дополнительные сведения о двумерных массивах см. в разделе [Многомерные массивы](../../../csharp/programming-guide/arrays/multidimensional-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="d5443-121">For more information about two-dimensional arrays, see [Multidimensional Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md).</span></span>  
  
 [!code-csharp[csProgGuideArrays#25](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_7.cs)]  
  
 <span data-ttu-id="d5443-122">В этом примере демонстрируется доступ к отдельным элементам, для чего отображается значение элемента `[1,0]` первого массива (`5`):</span><span class="sxs-lookup"><span data-stu-id="d5443-122">You can access individual elements as shown in this example, which displays the value of the element `[1,0]` of the first array (value `5`):</span></span>  
  
 [!code-csharp[csProgGuideArrays#26](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_8.cs)]  
  
 <span data-ttu-id="d5443-123">Метод `Length` возвращает число массивов, содержащихся в массиве массивов.</span><span class="sxs-lookup"><span data-stu-id="d5443-123">The method `Length` returns the number of arrays contained in the jagged array.</span></span> <span data-ttu-id="d5443-124">Допустим, предыдущий массив был объявлен с использованием следующей строки:</span><span class="sxs-lookup"><span data-stu-id="d5443-124">For example, assuming you have declared the previous array, this line:</span></span>  
  
 [!code-csharp[csProgGuideArrays#27](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_9.cs)]  
  
 <span data-ttu-id="d5443-125">возвращает значение 3.</span><span class="sxs-lookup"><span data-stu-id="d5443-125">returns a value of 3.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5443-126">Пример</span><span class="sxs-lookup"><span data-stu-id="d5443-126">Example</span></span>

 <span data-ttu-id="d5443-127">В этом примере создается массив, элементы которого являются массивами.</span><span class="sxs-lookup"><span data-stu-id="d5443-127">This example builds an array whose elements are themselves arrays.</span></span> <span data-ttu-id="d5443-128">Все элементы массива имеют разный размер.</span><span class="sxs-lookup"><span data-stu-id="d5443-128">Each one of the array elements has a different size.</span></span>  
  
 [!code-csharp[csProgGuideArrays#18](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_10.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="d5443-129">См. также</span><span class="sxs-lookup"><span data-stu-id="d5443-129">See Also</span></span>

- <xref:System.Array>  
- [<span data-ttu-id="d5443-130">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="d5443-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="d5443-131">Массивы</span><span class="sxs-lookup"><span data-stu-id="d5443-131">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
- [<span data-ttu-id="d5443-132">Одномерные массивы</span><span class="sxs-lookup"><span data-stu-id="d5443-132">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
- [<span data-ttu-id="d5443-133">Многомерные массивы</span><span class="sxs-lookup"><span data-stu-id="d5443-133">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)
