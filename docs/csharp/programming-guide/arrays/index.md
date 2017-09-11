---
title: "Массивы (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
caps.latest.revision: 33
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
ms.openlocfilehash: 1035caae15b64d1311305cfe4c1f1a74c80ed19a
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="arrays-c-programming-guide"></a><span data-ttu-id="b4029-102">Массивы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="b4029-102">Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="b4029-103">В структуре данных массива можно хранить несколько переменных одного типа.</span><span class="sxs-lookup"><span data-stu-id="b4029-103">You can store multiple variables of the same type in an array data structure.</span></span> <span data-ttu-id="b4029-104">Чтобы объявить массив, следует указать тип его элементов.</span><span class="sxs-lookup"><span data-stu-id="b4029-104">You declare an array by specifying the type of its elements.</span></span>  
  
 `type[] arrayName;`  
  
 <span data-ttu-id="b4029-105">В следующих примерах создаются одномерные массивы, многомерные массивы и массивы массивов:</span><span class="sxs-lookup"><span data-stu-id="b4029-105">The following examples create single-dimensional, multidimensional, and jagged arrays:</span></span>  
  
 <span data-ttu-id="b4029-106">[!code-cs[csProgGuideArrays#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/index_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b4029-106">[!code-cs[csProgGuideArrays#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/index_1.cs)]</span></span>  
  
## <a name="array-overview"></a><span data-ttu-id="b4029-107">Общие сведения о массивах</span><span class="sxs-lookup"><span data-stu-id="b4029-107">Array Overview</span></span>  
 <span data-ttu-id="b4029-108">Массив имеет следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="b4029-108">An array has the following properties:</span></span>  
  
-   <span data-ttu-id="b4029-109">Массив может быть [одномерным](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md), [многомерным](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) или [массивом массивов](../../../csharp/programming-guide/arrays/jagged-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="b4029-109">An array can be [Single-Dimensional](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md), [Multidimensional](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) or [Jagged](../../../csharp/programming-guide/arrays/jagged-arrays.md).</span></span>  
  
-   <span data-ttu-id="b4029-110">Количество измерений и длина каждого из измерений задаются, когда создается экземпляр массива.</span><span class="sxs-lookup"><span data-stu-id="b4029-110">The number of dimensions and the length of each dimension are established when the array instance is created.</span></span> <span data-ttu-id="b4029-111">Эти значения нельзя изменить во время существования экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b4029-111">These values can't be changed during the lifetime of the instance.</span></span>  
  
-   <span data-ttu-id="b4029-112">Используемые по умолчанию значения числовых элементов массива равны нулю, и элементам ссылки присвоено значение NULL.</span><span class="sxs-lookup"><span data-stu-id="b4029-112">The default values of numeric array elements are set to zero, and reference elements are set to null.</span></span>  
  
-   <span data-ttu-id="b4029-113">В массиве массивов элементы являются ссылочными типами и инициализируются значением `null`.</span><span class="sxs-lookup"><span data-stu-id="b4029-113">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>  
  
-   <span data-ttu-id="b4029-114">Массивы индексируются от нуля: массив с `n` элементами индексируется от `0` до `n-1`.</span><span class="sxs-lookup"><span data-stu-id="b4029-114">Arrays are zero indexed: an array with `n` elements is indexed from `0` to `n-1`.</span></span>  
  
-   <span data-ttu-id="b4029-115">Элементы массива могут иметь любой тип, в том числе тип массива.</span><span class="sxs-lookup"><span data-stu-id="b4029-115">Array elements can be of any type, including an array type.</span></span>  
  
-   <span data-ttu-id="b4029-116">Типы массивов — это [ссылочные типы](../../../csharp/language-reference/keywords/reference-types.md), производные от абстрактного базового типа <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="b4029-116">Array types are [reference types](../../../csharp/language-reference/keywords/reference-types.md) derived from the abstract base type <xref:System.Array>.</span></span> <span data-ttu-id="b4029-117">Поскольку этот тип реализует <xref:System.Collections.IEnumerable> и <xref:System.Collections.Generic.IEnumerable%601>, вы можете просматривать в цикле [foreach](../../../csharp/language-reference/keywords/foreach-in.md) любые массивы C#.</span><span class="sxs-lookup"><span data-stu-id="b4029-117">Since this type implements <xref:System.Collections.IEnumerable> and <xref:System.Collections.Generic.IEnumerable%601>, you can use [foreach](../../../csharp/language-reference/keywords/foreach-in.md) iteration on all arrays in C#.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b4029-118">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="b4029-118">Related Sections</span></span>  
  
-   [<span data-ttu-id="b4029-119">Массивы как объекты</span><span class="sxs-lookup"><span data-stu-id="b4029-119">Arrays as Objects</span></span>](../../../csharp/programming-guide/arrays/arrays-as-objects.md)  
  
-   [<span data-ttu-id="b4029-120">Использование оператора foreach с массивами</span><span class="sxs-lookup"><span data-stu-id="b4029-120">Using foreach with Arrays</span></span>](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
-   [<span data-ttu-id="b4029-121">Передача массивов в качестве аргументов</span><span class="sxs-lookup"><span data-stu-id="b4029-121">Passing Arrays as Arguments</span></span>](../../../csharp/programming-guide/arrays/passing-arrays-as-arguments.md)  
  
-   [<span data-ttu-id="b4029-122">Передача массивов при помощи параметров ref и out</span><span class="sxs-lookup"><span data-stu-id="b4029-122">Passing Arrays Using ref and out</span></span>](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)   
  
## <a name="c-language-specification"></a><span data-ttu-id="b4029-123">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="b4029-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b4029-124">См. также</span><span class="sxs-lookup"><span data-stu-id="b4029-124">See Also</span></span>  
 <span data-ttu-id="b4029-125">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b4029-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="b4029-126">[Коллекции](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b) </span><span class="sxs-lookup"><span data-stu-id="b4029-126">[Collections](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b) </span></span>  
 <span data-ttu-id="b4029-127">[Array Collection Type](http://msdn.microsoft.com/en-us/8a9964de-8941-47b1-a3cf-a01bc88db9e8) (Тип коллекции Array)</span><span class="sxs-lookup"><span data-stu-id="b4029-127">[Array Collection Type](http://msdn.microsoft.com/en-us/8a9964de-8941-47b1-a3cf-a01bc88db9e8)</span></span>

