---
title: Руководство по программированию на C#. Массивы
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: 24c6d54c3fe92ada661e732adec582e87ab62417
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69597529"
---
# <a name="arrays-c-programming-guide"></a><span data-ttu-id="e129b-102">Массивы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="e129b-102">Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="e129b-103">В структуре данных массива можно хранить несколько переменных одного типа.</span><span class="sxs-lookup"><span data-stu-id="e129b-103">You can store multiple variables of the same type in an array data structure.</span></span> <span data-ttu-id="e129b-104">Чтобы объявить массив, следует указать тип его элементов.</span><span class="sxs-lookup"><span data-stu-id="e129b-104">You declare an array by specifying the type of its elements.</span></span>  
  
 `type[] arrayName;`  
  
 <span data-ttu-id="e129b-105">В следующих примерах создаются одномерные массивы, многомерные массивы и массивы массивов:</span><span class="sxs-lookup"><span data-stu-id="e129b-105">The following example creates single-dimensional, multidimensional, and jagged arrays:</span></span>  
  
 [!code-csharp[csProgGuideArrays#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#1)]  
  
## <a name="array-overview"></a><span data-ttu-id="e129b-106">Общие сведения о массивах</span><span class="sxs-lookup"><span data-stu-id="e129b-106">Array Overview</span></span>

 <span data-ttu-id="e129b-107">Массив имеет следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="e129b-107">An array has the following properties:</span></span>  
  
- <span data-ttu-id="e129b-108">Массив может быть [одномерным](./single-dimensional-arrays.md), [многомерным](./multidimensional-arrays.md) или [массивом массивов](./jagged-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="e129b-108">An array can be [Single-Dimensional](./single-dimensional-arrays.md), [Multidimensional](./multidimensional-arrays.md) or [Jagged](./jagged-arrays.md).</span></span>  
  
- <span data-ttu-id="e129b-109">Количество измерений и длина каждого из измерений задаются, когда создается экземпляр массива.</span><span class="sxs-lookup"><span data-stu-id="e129b-109">The number of dimensions and the length of each dimension are established when the array instance is created.</span></span> <span data-ttu-id="e129b-110">Эти значения нельзя изменить во время существования экземпляра.</span><span class="sxs-lookup"><span data-stu-id="e129b-110">These values can't be changed during the lifetime of the instance.</span></span>  
  
- <span data-ttu-id="e129b-111">Используемые по умолчанию значения числовых элементов массива равны нулю, и элементам ссылки присвоено значение NULL.</span><span class="sxs-lookup"><span data-stu-id="e129b-111">The default values of numeric array elements are set to zero, and reference elements are set to null.</span></span>  
  
- <span data-ttu-id="e129b-112">В массиве массивов элементы являются ссылочными типами и инициализируются значением `null`.</span><span class="sxs-lookup"><span data-stu-id="e129b-112">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>  
  
- <span data-ttu-id="e129b-113">Массивы индексируются от нуля: массив с `n` элементами индексируется от `0` до `n-1`.</span><span class="sxs-lookup"><span data-stu-id="e129b-113">Arrays are zero indexed: an array with `n` elements is indexed from `0` to `n-1`.</span></span>  
  
- <span data-ttu-id="e129b-114">Элементы массива могут иметь любой тип, в том числе тип массива.</span><span class="sxs-lookup"><span data-stu-id="e129b-114">Array elements can be of any type, including an array type.</span></span>  
  
- <span data-ttu-id="e129b-115">Типы массивов — это [ссылочные типы](../../language-reference/keywords/reference-types.md), производные от абстрактного базового типа <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="e129b-115">Array types are [reference types](../../language-reference/keywords/reference-types.md) derived from the abstract base type <xref:System.Array>.</span></span> <span data-ttu-id="e129b-116">Поскольку этот тип реализует <xref:System.Collections.IEnumerable> и <xref:System.Collections.Generic.IEnumerable%601>, вы можете просматривать в цикле [foreach](../../language-reference/keywords/foreach-in.md) любые массивы C#.</span><span class="sxs-lookup"><span data-stu-id="e129b-116">Since this type implements <xref:System.Collections.IEnumerable> and <xref:System.Collections.Generic.IEnumerable%601>, you can use [foreach](../../language-reference/keywords/foreach-in.md) iteration on all arrays in C#.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e129b-117">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="e129b-117">Related Sections</span></span>  
  
- [<span data-ttu-id="e129b-118">Массивы как объекты</span><span class="sxs-lookup"><span data-stu-id="e129b-118">Arrays as Objects</span></span>](./arrays-as-objects.md)  
  
- [<span data-ttu-id="e129b-119">Использование оператора foreach с массивами</span><span class="sxs-lookup"><span data-stu-id="e129b-119">Using foreach with Arrays</span></span>](./using-foreach-with-arrays.md)  
  
- [<span data-ttu-id="e129b-120">Передача массивов в качестве аргументов</span><span class="sxs-lookup"><span data-stu-id="e129b-120">Passing Arrays as Arguments</span></span>](./passing-arrays-as-arguments.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="e129b-121">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="e129b-121">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e129b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="e129b-122">See also</span></span>

- [<span data-ttu-id="e129b-123">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e129b-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e129b-124">Коллекции</span><span class="sxs-lookup"><span data-stu-id="e129b-124">Collections</span></span>](../concepts/collections.md)
