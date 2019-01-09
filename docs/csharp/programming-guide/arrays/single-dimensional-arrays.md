---
title: Руководство по программированию на C#. Одномерные массивы
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: 316f8f59b86294b1f344b31f7355017ebd992362
ms.sourcegitcommit: 8598d446303b545eed2d520a6ccd061c1a7d00cb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/13/2018
ms.locfileid: "53334760"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a><span data-ttu-id="1aca4-102">Одномерные массивы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="1aca4-102">Single-Dimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="1aca4-103">Вы можете объявить одномерный массив, содержащий пять целых чисел, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="1aca4-103">You can declare a single-dimensional array of five integers as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#4](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_1.cs)]  
  
 <span data-ttu-id="1aca4-104">Этот массив содержит элементы с `array[0]` по `array[4]`.</span><span class="sxs-lookup"><span data-stu-id="1aca4-104">This array contains the elements from `array[0]` to `array[4]`.</span></span> <span data-ttu-id="1aca4-105">С помощью оператора [new](../../../csharp/language-reference/keywords/new.md) можно создать массив и инициализировать его элементы, используя значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1aca4-105">The [new](../../../csharp/language-reference/keywords/new.md) operator is used to create the array and initialize the array elements to their default values.</span></span> <span data-ttu-id="1aca4-106">В этом примере при инициализации всем элементам массива присваиваются нулевые значения.</span><span class="sxs-lookup"><span data-stu-id="1aca4-106">In this example, all the array elements are initialized to zero.</span></span>  
  
 <span data-ttu-id="1aca4-107">Таким же образом можно объявить массив, в котором хранятся строковые элементы.</span><span class="sxs-lookup"><span data-stu-id="1aca4-107">An array that stores string elements can be declared in the same way.</span></span> <span data-ttu-id="1aca4-108">Например:</span><span class="sxs-lookup"><span data-stu-id="1aca4-108">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#5](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_2.cs)]  
  
## <a name="array-initialization"></a><span data-ttu-id="1aca4-109">Инициализация массива</span><span class="sxs-lookup"><span data-stu-id="1aca4-109">Array Initialization</span></span>

 <span data-ttu-id="1aca4-110">Массив можно инициализировать при объявлении. В этом случае не требуется спецификатор длины, поскольку он уже задан по числу элементов в списке инициализации.</span><span class="sxs-lookup"><span data-stu-id="1aca4-110">It is possible to initialize an array upon declaration, in which case, the length specifier is not needed because it is already supplied by the number of elements in the initialization list.</span></span> <span data-ttu-id="1aca4-111">Например:</span><span class="sxs-lookup"><span data-stu-id="1aca4-111">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#6](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_3.cs)]  
  
 <span data-ttu-id="1aca4-112">Массив строк можно инициализировать таким же образом.</span><span class="sxs-lookup"><span data-stu-id="1aca4-112">A string array can be initialized in the same way.</span></span> <span data-ttu-id="1aca4-113">Ниже приведено объявление массива строк, где каждый элемент массива инициализируется с использованием названия дня:</span><span class="sxs-lookup"><span data-stu-id="1aca4-113">The following is a declaration of a string array where each array element is initialized by a name of a day:</span></span>  
  
 [!code-csharp[csProgGuideArrays#7](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_4.cs)]  
  
 <span data-ttu-id="1aca4-114">Если массив инициализируется при объявлении, вы можете использовать следующие сочетания клавиш:</span><span class="sxs-lookup"><span data-stu-id="1aca4-114">When you initialize an array upon declaration, you can use the following shortcuts:</span></span>  
  
 [!code-csharp[csProgGuideArrays#8](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_5.cs)]  
  
 <span data-ttu-id="1aca4-115">Переменную массива можно объявить без инициализации, однако при присвоении массива этой переменной необходимо использовать оператор `new`.</span><span class="sxs-lookup"><span data-stu-id="1aca4-115">It is possible to declare an array variable without initialization, but you must use the `new` operator when you assign an array to this variable.</span></span> <span data-ttu-id="1aca4-116">Например:</span><span class="sxs-lookup"><span data-stu-id="1aca4-116">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#9](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_6.cs)]  
  
 <span data-ttu-id="1aca4-117">В C# 3.0 представлены неявно типизированные массивы.</span><span class="sxs-lookup"><span data-stu-id="1aca4-117">C# 3.0 introduces implicitly typed arrays.</span></span> <span data-ttu-id="1aca4-118">Дополнительные сведения см. в разделе [Неявно типизированные массивы](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="1aca4-118">For more information, see [Implicitly Typed Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span></span>  
  
## <a name="value-type-and-reference-type-arrays"></a><span data-ttu-id="1aca4-119">Массивы типов значений и ссылочных типов</span><span class="sxs-lookup"><span data-stu-id="1aca4-119">Value Type and Reference Type Arrays</span></span>

 <span data-ttu-id="1aca4-120">Рассмотрим следующее объявление массива:</span><span class="sxs-lookup"><span data-stu-id="1aca4-120">Consider the following array declaration:</span></span>  
  
 [!code-csharp[csProgGuideArrays#10](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_7.cs)]  
  
 <span data-ttu-id="1aca4-121">Результат этого оператора зависит от того, является ли `SomeType` типом значения или ссылочным типом.</span><span class="sxs-lookup"><span data-stu-id="1aca4-121">The result of this statement depends on whether `SomeType` is a value type or a reference type.</span></span> <span data-ttu-id="1aca4-122">Если это тип значения, оператор создает массив из 10 элементов, каждый из которых имеет тип `SomeType`.</span><span class="sxs-lookup"><span data-stu-id="1aca4-122">If it is a value type, the statement creates an array of 10 elements, each of which has the type `SomeType`.</span></span> <span data-ttu-id="1aca4-123">Если `SomeType` является ссылочным типом, этот оператор создает массив из 10 элементов, каждый из которых инициализируется с использованием ссылки NULL.</span><span class="sxs-lookup"><span data-stu-id="1aca4-123">If `SomeType` is a reference type, the statement creates an array of 10 elements, each of which is initialized to a null reference.</span></span>  
  
 <span data-ttu-id="1aca4-124">Дополнительные сведения о типах значений и ссылочных типах см. в разделе [Типы](../../../csharp/language-reference/keywords/types.md).</span><span class="sxs-lookup"><span data-stu-id="1aca4-124">For more information about value types and reference types, see [Types](../../../csharp/language-reference/keywords/types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aca4-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1aca4-125">See Also</span></span>

- <xref:System.Array>  
- [<span data-ttu-id="1aca4-126">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="1aca4-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="1aca4-127">Массивы</span><span class="sxs-lookup"><span data-stu-id="1aca4-127">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
- [<span data-ttu-id="1aca4-128">Многомерные массивы</span><span class="sxs-lookup"><span data-stu-id="1aca4-128">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
- [<span data-ttu-id="1aca4-129">Массивы массивов</span><span class="sxs-lookup"><span data-stu-id="1aca4-129">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
