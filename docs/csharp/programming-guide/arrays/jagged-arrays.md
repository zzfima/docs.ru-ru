---
title: Руководство по программированию на C#. Массивы массивов
ms.date: 07/20/2015
helpviewer_keywords:
- jagged arrays [C#]
- arrays [C#], jagged
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
ms.openlocfilehash: 56013f0143d5efcb31a476909cb6e92504ff0dbc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705708"
---
# <a name="jagged-arrays-c-programming-guide"></a><span data-ttu-id="fce52-102">Массивы массивов (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="fce52-102">Jagged Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="fce52-103">Массив массивов — это массив, элементы которого сами являются массивами.</span><span class="sxs-lookup"><span data-stu-id="fce52-103">A jagged array is an array whose elements are arrays.</span></span> <span data-ttu-id="fce52-104">Элементы массива массивов могут иметь различные измерения и размеры.</span><span class="sxs-lookup"><span data-stu-id="fce52-104">The elements of a jagged array can be of different dimensions and sizes.</span></span> <span data-ttu-id="fce52-105">Массив массивов иногда называется нерегулярным массивом.</span><span class="sxs-lookup"><span data-stu-id="fce52-105">A jagged array is sometimes called an "array of arrays."</span></span> <span data-ttu-id="fce52-106">В следующих примерах показано, как объявлять и инициализировать массивы массивов, а также получать доступ к ним.</span><span class="sxs-lookup"><span data-stu-id="fce52-106">The following examples show how to declare, initialize, and access jagged arrays.</span></span>  
  
 <span data-ttu-id="fce52-107">Ниже объявляется одномерный массив из трех элементов, каждый из которых является одномерным массивом целых чисел:</span><span class="sxs-lookup"><span data-stu-id="fce52-107">The following is a declaration of a single-dimensional array that has three elements, each of which is a single-dimensional array of integers:</span></span>  
  
 [!code-csharp[csProgGuideArrays#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#19)]  
  
 <span data-ttu-id="fce52-108">Прежде чем использовать `jaggedArray`, его элементы необходимо инициализировать.</span><span class="sxs-lookup"><span data-stu-id="fce52-108">Before you can use `jaggedArray`, its elements must be initialized.</span></span> <span data-ttu-id="fce52-109">Это можно сделать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="fce52-109">You can initialize the elements like this:</span></span>  
  
 [!code-csharp[csProgGuideArrays#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#20)]  
  
 <span data-ttu-id="fce52-110">Каждый элемент представляет собой одномерный массив целых чисел.</span><span class="sxs-lookup"><span data-stu-id="fce52-110">Each of the elements is a single-dimensional array of integers.</span></span> <span data-ttu-id="fce52-111">Первый из них содержит 5 целых чисел, второй — 4, а третий — 2.</span><span class="sxs-lookup"><span data-stu-id="fce52-111">The first element is an array of 5 integers, the second is an array of 4 integers, and the third is an array of 2 integers.</span></span>  
  
 <span data-ttu-id="fce52-112">Кроме того, с помощью инициализаторов можно заполнять элементы массива значениями (при этом вам не потребуется знать размер массива).</span><span class="sxs-lookup"><span data-stu-id="fce52-112">It is also possible to use initializers to fill the array elements with values, in which case you do not need the array size.</span></span> <span data-ttu-id="fce52-113">Пример:</span><span class="sxs-lookup"><span data-stu-id="fce52-113">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#21)]  
  
 <span data-ttu-id="fce52-114">Также массив можно инициализировать при объявлении, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="fce52-114">You can also initialize the array upon declaration like this:</span></span>  
  
 [!code-csharp[csProgGuideArrays#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#22)]  
  
 <span data-ttu-id="fce52-115">Можно использовать следующую краткую форму.</span><span class="sxs-lookup"><span data-stu-id="fce52-115">You can use the following shorthand form.</span></span> <span data-ttu-id="fce52-116">Обратите внимание, что при инициализации элементов нельзя опускать оператор `new`, поскольку механизм инициализации по умолчанию для них не предусмотрен:</span><span class="sxs-lookup"><span data-stu-id="fce52-116">Notice that you cannot omit the `new` operator from the elements initialization because there is no default initialization for the elements:</span></span>  
  
 [!code-csharp[csProgGuideArrays#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#23)]  
  
 <span data-ttu-id="fce52-117">В массиве массивов элементы являются ссылочными типами и инициализируются значением `null`.</span><span class="sxs-lookup"><span data-stu-id="fce52-117">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>  
  
 <span data-ttu-id="fce52-118">Доступ к отдельным элементам массива можно получить способами, показанными в следующих примерах:</span><span class="sxs-lookup"><span data-stu-id="fce52-118">You can access individual array elements like these examples:</span></span>  
  
 [!code-csharp[csProgGuideArrays#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#24)]  
  
 <span data-ttu-id="fce52-119">Массивы массивов и многомерные массивы можно смешивать.</span><span class="sxs-lookup"><span data-stu-id="fce52-119">It is possible to mix jagged and multidimensional arrays.</span></span> <span data-ttu-id="fce52-120">Ниже показаны объявление и инициализация одномерного массива массивов, элементами которого являются двухмерные массивы разного размера.</span><span class="sxs-lookup"><span data-stu-id="fce52-120">The following is a declaration and initialization of a single-dimensional jagged array that contains three two-dimensional array elements of different sizes.</span></span> <span data-ttu-id="fce52-121">Дополнительные сведения о двумерных массивах см. в разделе [Многомерные массивы](./multidimensional-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="fce52-121">For more information about two-dimensional arrays, see [Multidimensional Arrays](./multidimensional-arrays.md).</span></span>  
  
 [!code-csharp[csProgGuideArrays#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#25)]  
  
 <span data-ttu-id="fce52-122">В этом примере демонстрируется доступ к отдельным элементам, для чего отображается значение элемента `[1,0]` первого массива (`5`):</span><span class="sxs-lookup"><span data-stu-id="fce52-122">You can access individual elements as shown in this example, which displays the value of the element `[1,0]` of the first array (value `5`):</span></span>  
  
 [!code-csharp[csProgGuideArrays#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#26)]  
  
 <span data-ttu-id="fce52-123">Метод `Length` возвращает число массивов, содержащихся в массиве массивов.</span><span class="sxs-lookup"><span data-stu-id="fce52-123">The method `Length` returns the number of arrays contained in the jagged array.</span></span> <span data-ttu-id="fce52-124">Допустим, предыдущий массив был объявлен с использованием следующей строки:</span><span class="sxs-lookup"><span data-stu-id="fce52-124">For example, assuming you have declared the previous array, this line:</span></span>  
  
 [!code-csharp[csProgGuideArrays#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#27)]  
  
 <span data-ttu-id="fce52-125">возвращает значение 3.</span><span class="sxs-lookup"><span data-stu-id="fce52-125">returns a value of 3.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fce52-126">Пример</span><span class="sxs-lookup"><span data-stu-id="fce52-126">Example</span></span>

 <span data-ttu-id="fce52-127">В этом примере создается массив, элементы которого являются массивами.</span><span class="sxs-lookup"><span data-stu-id="fce52-127">This example builds an array whose elements are themselves arrays.</span></span> <span data-ttu-id="fce52-128">Все элементы массива имеют разный размер.</span><span class="sxs-lookup"><span data-stu-id="fce52-128">Each one of the array elements has a different size.</span></span>  
  
 [!code-csharp[csProgGuideArrays#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#18)]  
  
## <a name="see-also"></a><span data-ttu-id="fce52-129">См. также</span><span class="sxs-lookup"><span data-stu-id="fce52-129">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="fce52-130">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="fce52-130">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="fce52-131">Массивы</span><span class="sxs-lookup"><span data-stu-id="fce52-131">Arrays</span></span>](./index.md)
- [<span data-ttu-id="fce52-132">Одномерные массивы</span><span class="sxs-lookup"><span data-stu-id="fce52-132">Single-Dimensional Arrays</span></span>](./single-dimensional-arrays.md)
- [<span data-ttu-id="fce52-133">Многомерные массивы</span><span class="sxs-lookup"><span data-stu-id="fce52-133">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
