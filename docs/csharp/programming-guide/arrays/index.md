---
title: Руководство по программированию на C#. Массивы
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: e31cff94c51c626c4b8f0e08df270c45a9cc1316
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72772099"
---
# <a name="arrays-c-programming-guide"></a><span data-ttu-id="9ef65-102">Массивы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="9ef65-102">Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="9ef65-103">В структуре данных массива можно хранить несколько переменных одного типа.</span><span class="sxs-lookup"><span data-stu-id="9ef65-103">You can store multiple variables of the same type in an array data structure.</span></span> <span data-ttu-id="9ef65-104">Чтобы объявить массив, следует указать тип его элементов.</span><span class="sxs-lookup"><span data-stu-id="9ef65-104">You declare an array by specifying the type of its elements.</span></span> <span data-ttu-id="9ef65-105">Если требуется, чтобы массив мог хранить элементы любого типа, можно указать `object` в качестве его типа.</span><span class="sxs-lookup"><span data-stu-id="9ef65-105">If you want the array to store elements of any type, you can specify `object` as its type.</span></span> <span data-ttu-id="9ef65-106">В унифицированной системе типов C# все типы, стандартные и определяемые пользователем, ссылочные типы и типы значений напрямую или косвенно наследуются из <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="9ef65-106">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span>

```csharp
type[] arrayName;
```

## <a name="example"></a><span data-ttu-id="9ef65-107">Пример</span><span class="sxs-lookup"><span data-stu-id="9ef65-107">Example</span></span>

<span data-ttu-id="9ef65-108">В следующих примерах создаются одномерные массивы, многомерные массивы и массивы массивов:</span><span class="sxs-lookup"><span data-stu-id="9ef65-108">The following example creates single-dimensional, multidimensional, and jagged arrays:</span></span>

[!code-csharp[csProgGuideArrays#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#1)]

## <a name="array-overview"></a><span data-ttu-id="9ef65-109">Общие сведения о массивах</span><span class="sxs-lookup"><span data-stu-id="9ef65-109">Array overview</span></span>

<span data-ttu-id="9ef65-110">Массив имеет следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="9ef65-110">An array has the following properties:</span></span>

- <span data-ttu-id="9ef65-111">Массив может быть [одномерным](single-dimensional-arrays.md), [многомерным](multidimensional-arrays.md) или [массивом массивов](jagged-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="9ef65-111">An array can be [Single-Dimensional](single-dimensional-arrays.md), [Multidimensional](multidimensional-arrays.md) or [Jagged](jagged-arrays.md).</span></span>
- <span data-ttu-id="9ef65-112">Количество измерений и длина каждого из измерений задаются, когда создается экземпляр массива.</span><span class="sxs-lookup"><span data-stu-id="9ef65-112">The number of dimensions and the length of each dimension are established when the array instance is created.</span></span> <span data-ttu-id="9ef65-113">Эти значения нельзя изменить во время существования экземпляра.</span><span class="sxs-lookup"><span data-stu-id="9ef65-113">These values can't be changed during the lifetime of the instance.</span></span>
- <span data-ttu-id="9ef65-114">Используемые по умолчанию значения числовых элементов массива равны нулю, и элементам ссылки присвоено значение NULL.</span><span class="sxs-lookup"><span data-stu-id="9ef65-114">The default values of numeric array elements are set to zero, and reference elements are set to null.</span></span>
- <span data-ttu-id="9ef65-115">В массиве массивов элементы являются ссылочными типами и инициализируются значением `null`.</span><span class="sxs-lookup"><span data-stu-id="9ef65-115">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>
- <span data-ttu-id="9ef65-116">Массивы индексируются от нуля: массив с `n` элементами индексируется от `0` до `n-1`.</span><span class="sxs-lookup"><span data-stu-id="9ef65-116">Arrays are zero indexed: an array with `n` elements is indexed from `0` to `n-1`.</span></span>
- <span data-ttu-id="9ef65-117">Элементы массива могут иметь любой тип, в том числе тип массива.</span><span class="sxs-lookup"><span data-stu-id="9ef65-117">Array elements can be of any type, including an array type.</span></span>
- <span data-ttu-id="9ef65-118">Типы массивов — это [ссылочные типы](../../language-reference/keywords/reference-types.md), производные от абстрактного базового типа <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="9ef65-118">Array types are [reference types](../../language-reference/keywords/reference-types.md) derived from the abstract base type <xref:System.Array>.</span></span> <span data-ttu-id="9ef65-119">Поскольку этот тип реализует <xref:System.Collections.IEnumerable> и <xref:System.Collections.Generic.IEnumerable%601>, вы можете просматривать в цикле [foreach](../../language-reference/keywords/foreach-in.md) любые массивы C#.</span><span class="sxs-lookup"><span data-stu-id="9ef65-119">Since this type implements <xref:System.Collections.IEnumerable> and <xref:System.Collections.Generic.IEnumerable%601>, you can use [foreach](../../language-reference/keywords/foreach-in.md) iteration on all arrays in C#.</span></span>

## <a name="related-sections"></a><span data-ttu-id="9ef65-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="9ef65-120">Related sections</span></span>

- [<span data-ttu-id="9ef65-121">Массивы как объекты</span><span class="sxs-lookup"><span data-stu-id="9ef65-121">Arrays as Objects</span></span>](arrays-as-objects.md)
- [<span data-ttu-id="9ef65-122">Использование оператора foreach с массивами</span><span class="sxs-lookup"><span data-stu-id="9ef65-122">Using foreach with Arrays</span></span>](using-foreach-with-arrays.md)
- [<span data-ttu-id="9ef65-123">Передача массивов в качестве аргументов</span><span class="sxs-lookup"><span data-stu-id="9ef65-123">Passing Arrays as Arguments</span></span>](passing-arrays-as-arguments.md)

## <a name="c-language-specification"></a><span data-ttu-id="9ef65-124">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="9ef65-124">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="9ef65-125">См. также</span><span class="sxs-lookup"><span data-stu-id="9ef65-125">See also</span></span>

- [<span data-ttu-id="9ef65-126">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="9ef65-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="9ef65-127">Коллекции</span><span class="sxs-lookup"><span data-stu-id="9ef65-127">Collections</span></span>](../concepts/collections.md)
