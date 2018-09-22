---
title: Массивы (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: e0ed2d678363a29bb870a496846fc6f054769a4b
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2018
ms.locfileid: "46530080"
---
# <a name="arrays-c-programming-guide"></a><span data-ttu-id="71baa-102">Массивы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="71baa-102">Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="71baa-103">В структуре данных массива можно хранить несколько переменных одного типа.</span><span class="sxs-lookup"><span data-stu-id="71baa-103">You can store multiple variables of the same type in an array data structure.</span></span> <span data-ttu-id="71baa-104">Чтобы объявить массив, следует указать тип его элементов.</span><span class="sxs-lookup"><span data-stu-id="71baa-104">You declare an array by specifying the type of its elements.</span></span>  
  
 `type[] arrayName;`  
  
 <span data-ttu-id="71baa-105">В следующих примерах создаются одномерные массивы, многомерные массивы и массивы массивов:</span><span class="sxs-lookup"><span data-stu-id="71baa-105">The following examples create single-dimensional, multidimensional, and jagged arrays:</span></span>  
  
 [!code-csharp[csProgGuideArrays#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/index_1.cs)]  
  
## <a name="array-overview"></a><span data-ttu-id="71baa-106">Общие сведения о массивах</span><span class="sxs-lookup"><span data-stu-id="71baa-106">Array Overview</span></span>

 <span data-ttu-id="71baa-107">Массив имеет следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="71baa-107">An array has the following properties:</span></span>  
  
-   <span data-ttu-id="71baa-108">Массив может быть [одномерным](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md), [многомерным](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) или [массивом массивов](../../../csharp/programming-guide/arrays/jagged-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="71baa-108">An array can be [Single-Dimensional](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md), [Multidimensional](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) or [Jagged](../../../csharp/programming-guide/arrays/jagged-arrays.md).</span></span>  
  
-   <span data-ttu-id="71baa-109">Количество измерений и длина каждого из измерений задаются, когда создается экземпляр массива.</span><span class="sxs-lookup"><span data-stu-id="71baa-109">The number of dimensions and the length of each dimension are established when the array instance is created.</span></span> <span data-ttu-id="71baa-110">Эти значения нельзя изменить во время существования экземпляра.</span><span class="sxs-lookup"><span data-stu-id="71baa-110">These values can't be changed during the lifetime of the instance.</span></span>  
  
-   <span data-ttu-id="71baa-111">Используемые по умолчанию значения числовых элементов массива равны нулю, и элементам ссылки присвоено значение NULL.</span><span class="sxs-lookup"><span data-stu-id="71baa-111">The default values of numeric array elements are set to zero, and reference elements are set to null.</span></span>  
  
-   <span data-ttu-id="71baa-112">В массиве массивов элементы являются ссылочными типами и инициализируются значением `null`.</span><span class="sxs-lookup"><span data-stu-id="71baa-112">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>  
  
-   <span data-ttu-id="71baa-113">Массивы индексируются от нуля: массив с `n` элементами индексируется от `0` до `n-1`.</span><span class="sxs-lookup"><span data-stu-id="71baa-113">Arrays are zero indexed: an array with `n` elements is indexed from `0` to `n-1`.</span></span>  
  
-   <span data-ttu-id="71baa-114">Элементы массива могут иметь любой тип, в том числе тип массива.</span><span class="sxs-lookup"><span data-stu-id="71baa-114">Array elements can be of any type, including an array type.</span></span>  
  
-   <span data-ttu-id="71baa-115">Типы массивов — это [ссылочные типы](../../../csharp/language-reference/keywords/reference-types.md), производные от абстрактного базового типа <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="71baa-115">Array types are [reference types](../../../csharp/language-reference/keywords/reference-types.md) derived from the abstract base type <xref:System.Array>.</span></span> <span data-ttu-id="71baa-116">Поскольку этот тип реализует <xref:System.Collections.IEnumerable> и <xref:System.Collections.Generic.IEnumerable%601>, вы можете просматривать в цикле [foreach](../../../csharp/language-reference/keywords/foreach-in.md) любые массивы C#.</span><span class="sxs-lookup"><span data-stu-id="71baa-116">Since this type implements <xref:System.Collections.IEnumerable> and <xref:System.Collections.Generic.IEnumerable%601>, you can use [foreach](../../../csharp/language-reference/keywords/foreach-in.md) iteration on all arrays in C#.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="71baa-117">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="71baa-117">Related Sections</span></span>  
  
-   [<span data-ttu-id="71baa-118">Массивы как объекты</span><span class="sxs-lookup"><span data-stu-id="71baa-118">Arrays as Objects</span></span>](../../../csharp/programming-guide/arrays/arrays-as-objects.md)  
  
-   [<span data-ttu-id="71baa-119">Использование оператора foreach с массивами</span><span class="sxs-lookup"><span data-stu-id="71baa-119">Using foreach with Arrays</span></span>](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
-   [<span data-ttu-id="71baa-120">Передача массивов в качестве аргументов</span><span class="sxs-lookup"><span data-stu-id="71baa-120">Passing Arrays as Arguments</span></span>](../../../csharp/programming-guide/arrays/passing-arrays-as-arguments.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="71baa-121">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="71baa-121">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="71baa-122">См. также</span><span class="sxs-lookup"><span data-stu-id="71baa-122">See Also</span></span>

- [<span data-ttu-id="71baa-123">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="71baa-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="71baa-124">Коллекции</span><span class="sxs-lookup"><span data-stu-id="71baa-124">Collections</span></span>](../../../csharp/programming-guide/concepts/collections.md)  
- <span data-ttu-id="71baa-125">[Array Collection Type](https://msdn.microsoft.com/library/8a9964de-8941-47b1-a3cf-a01bc88db9e8) (Тип коллекции Array)</span><span class="sxs-lookup"><span data-stu-id="71baa-125">[Array Collection Type](https://msdn.microsoft.com/library/8a9964de-8941-47b1-a3cf-a01bc88db9e8)</span></span>
