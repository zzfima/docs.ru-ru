---
title: "Одномерные массивы (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
caps.latest.revision: 18
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
ms.openlocfilehash: cc42640715274b89c4c4a12ced8c0ae6af603318
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="single-dimensional-arrays-c-programming-guide"></a><span data-ttu-id="8b33b-102">Одномерные массивы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="8b33b-102">Single-Dimensional Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="8b33b-103">Вы можете объявить одномерный массив, содержащий пять целых чисел, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8b33b-103">You can declare a single-dimensional array of five integers as shown in the following example:</span></span>  
  
 <span data-ttu-id="8b33b-104">[!code-cs[csProgGuideArrays#4](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8b33b-104">[!code-cs[csProgGuideArrays#4](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_1.cs)]</span></span>  
  
 <span data-ttu-id="8b33b-105">Этот массив содержит элементы с `array[0]` по `array[4]`.</span><span class="sxs-lookup"><span data-stu-id="8b33b-105">This array contains the elements from `array[0]` to `array[4]`.</span></span> <span data-ttu-id="8b33b-106">С помощью оператора [new](../../../csharp/language-reference/keywords/new.md) можно создать массив и инициализировать его элементы, используя значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8b33b-106">The [new](../../../csharp/language-reference/keywords/new.md) operator is used to create the array and initialize the array elements to their default values.</span></span> <span data-ttu-id="8b33b-107">В этом примере при инициализации всем элементам массива присваиваются нулевые значения.</span><span class="sxs-lookup"><span data-stu-id="8b33b-107">In this example, all the array elements are initialized to zero.</span></span>  
  
 <span data-ttu-id="8b33b-108">Таким же образом можно объявить массив, в котором хранятся строковые элементы.</span><span class="sxs-lookup"><span data-stu-id="8b33b-108">An array that stores string elements can be declared in the same way.</span></span> <span data-ttu-id="8b33b-109">Пример:</span><span class="sxs-lookup"><span data-stu-id="8b33b-109">For example:</span></span>  
  
 <span data-ttu-id="8b33b-110">[!code-cs[csProgGuideArrays#5](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="8b33b-110">[!code-cs[csProgGuideArrays#5](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_2.cs)]</span></span>  
  
## <a name="array-initialization"></a><span data-ttu-id="8b33b-111">Инициализация массива</span><span class="sxs-lookup"><span data-stu-id="8b33b-111">Array Initialization</span></span>  
 <span data-ttu-id="8b33b-112">Массив можно инициализировать при объявлении. В этом случае не требуется спецификатор ранга, поскольку он уже задается по числу элементов в списке инициализации.</span><span class="sxs-lookup"><span data-stu-id="8b33b-112">It is possible to initialize an array upon declaration, in which case, the rank specifier is not needed because it is already supplied by the number of elements in the initialization list.</span></span> <span data-ttu-id="8b33b-113">Пример:</span><span class="sxs-lookup"><span data-stu-id="8b33b-113">For example:</span></span>  
  
 <span data-ttu-id="8b33b-114">[!code-cs[csProgGuideArrays#6](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="8b33b-114">[!code-cs[csProgGuideArrays#6](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_3.cs)]</span></span>  
  
 <span data-ttu-id="8b33b-115">Массив строк можно инициализировать таким же образом.</span><span class="sxs-lookup"><span data-stu-id="8b33b-115">A string array can be initialized in the same way.</span></span> <span data-ttu-id="8b33b-116">Ниже приведено объявление массива строк, где каждый элемент массива инициализируется с использованием названия дня:</span><span class="sxs-lookup"><span data-stu-id="8b33b-116">The following is a declaration of a string array where each array element is initialized by a name of a day:</span></span>  
  
 <span data-ttu-id="8b33b-117">[!code-cs[csProgGuideArrays#7](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="8b33b-117">[!code-cs[csProgGuideArrays#7](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_4.cs)]</span></span>  
  
 <span data-ttu-id="8b33b-118">Если массив инициализируется при объявлении, вы можете использовать следующие сочетания клавиш:</span><span class="sxs-lookup"><span data-stu-id="8b33b-118">When you initialize an array upon declaration, you can use the following shortcuts:</span></span>  
  
 <span data-ttu-id="8b33b-119">[!code-cs[csProgGuideArrays#8](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="8b33b-119">[!code-cs[csProgGuideArrays#8](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_5.cs)]</span></span>  
  
 <span data-ttu-id="8b33b-120">Переменную массива можно объявить без инициализации, однако при присвоении массива этой переменной необходимо использовать оператор `new`.</span><span class="sxs-lookup"><span data-stu-id="8b33b-120">It is possible to declare an array variable without initialization, but you must use the `new` operator when you assign an array to this variable.</span></span> <span data-ttu-id="8b33b-121">Пример:</span><span class="sxs-lookup"><span data-stu-id="8b33b-121">For example:</span></span>  
  
 <span data-ttu-id="8b33b-122">[!code-cs[csProgGuideArrays#9](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="8b33b-122">[!code-cs[csProgGuideArrays#9](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_6.cs)]</span></span>  
  
 <span data-ttu-id="8b33b-123">В C# 3.0 представлены неявно типизированные массивы.</span><span class="sxs-lookup"><span data-stu-id="8b33b-123">C# 3.0 introduces implicitly typed arrays.</span></span> <span data-ttu-id="8b33b-124">Дополнительные сведения см. в разделе [Неявно типизированные массивы](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="8b33b-124">For more information, see [Implicitly Typed Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span></span>  
  
## <a name="value-type-and-reference-type-arrays"></a><span data-ttu-id="8b33b-125">Массивы типов значений и ссылочных типов</span><span class="sxs-lookup"><span data-stu-id="8b33b-125">Value Type and Reference Type Arrays</span></span>  
 <span data-ttu-id="8b33b-126">Рассмотрим следующее объявление массива:</span><span class="sxs-lookup"><span data-stu-id="8b33b-126">Consider the following array declaration:</span></span>  
  
 <span data-ttu-id="8b33b-127">[!code-cs[csProgGuideArrays#10](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="8b33b-127">[!code-cs[csProgGuideArrays#10](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_7.cs)]</span></span>  
  
 <span data-ttu-id="8b33b-128">Результат этого оператора зависит от того, является ли `SomeType` типом значения или ссылочным типом.</span><span class="sxs-lookup"><span data-stu-id="8b33b-128">The result of this statement depends on whether `SomeType` is a value type or a reference type.</span></span> <span data-ttu-id="8b33b-129">Если это тип значения, оператор создает массив из 10 элементов, каждый из которых имеет тип `SomeType`.</span><span class="sxs-lookup"><span data-stu-id="8b33b-129">If it is a value type, the statement creates an array of 10 elements, each of which has the type `SomeType`.</span></span> <span data-ttu-id="8b33b-130">Если `SomeType` является ссылочным типом, этот оператор создает массив из 10 элементов, каждый из которых инициализируется с использованием ссылки NULL.</span><span class="sxs-lookup"><span data-stu-id="8b33b-130">If `SomeType` is a reference type, the statement creates an array of 10 elements, each of which is initialized to a null reference.</span></span>  
  
 <span data-ttu-id="8b33b-131">Дополнительные сведения о типах значений и ссылочных типах см. в разделе [Типы](../../../csharp/language-reference/keywords/types.md).</span><span class="sxs-lookup"><span data-stu-id="8b33b-131">For more information about value types and reference types, see [Types](../../../csharp/language-reference/keywords/types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b33b-132">См. также</span><span class="sxs-lookup"><span data-stu-id="8b33b-132">See Also</span></span>  
 <span data-ttu-id="8b33b-133"><xref:System.Array></span><span class="sxs-lookup"><span data-stu-id="8b33b-133"><xref:System.Array></span></span>   
 <span data-ttu-id="8b33b-134">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8b33b-134">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="8b33b-135">[Массивы](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="8b33b-135">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="8b33b-136">[Многомерные массивы](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="8b33b-136">[Multidimensional Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span></span>  
 [<span data-ttu-id="8b33b-137">Массивы массивов</span><span class="sxs-lookup"><span data-stu-id="8b33b-137">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)

