---
title: Массивы в C#. Краткий обзор языка C#
description: Массивы — это самый простой тип коллекций в языке C#
ms.date: 02/27/2020
ms.assetid: a440704c-9e88-4c75-97dd-bfe30ca0fb97
ms.openlocfilehash: 3e045c0933a21beab6958c7851546ba6e0b55ef9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78159199"
---
# <a name="arrays"></a><span data-ttu-id="a5580-103">Массивы</span><span class="sxs-lookup"><span data-stu-id="a5580-103">Arrays</span></span>

<span data-ttu-id="a5580-104">***Массив*** — это структура данных, содержащая несколько переменных, доступ к которым осуществляется по вычисляемым индексам.</span><span class="sxs-lookup"><span data-stu-id="a5580-104">An ***array*** is a data structure that contains a number of variables that are accessed through computed indices.</span></span> <span data-ttu-id="a5580-105">Содержащиеся в массиве переменные именуются ***элементами*** этого массива. Все они имеют одинаковый тип, который называется ***типом элементов*** массива.</span><span class="sxs-lookup"><span data-stu-id="a5580-105">The variables contained in an array, also called the ***elements*** of the array, are all of the same type, and this type is called the ***element type*** of the array.</span></span>

<span data-ttu-id="a5580-106">Сами массивы имеют ссылочный тип, и объявление переменной массива только выделяет память для ссылки на экземпляр массива.</span><span class="sxs-lookup"><span data-stu-id="a5580-106">Array types are reference types, and the declaration of an array variable simply sets aside space for a reference to an array instance.</span></span> <span data-ttu-id="a5580-107">Фактические экземпляры массива создаются динамически во время выполнения с помощью оператора new.</span><span class="sxs-lookup"><span data-stu-id="a5580-107">Actual array instances are created dynamically at runtime using the new operator.</span></span> <span data-ttu-id="a5580-108">Операция new указывает ***длину*** нового экземпляра массива, которая остается неизменной в течение всего времени существования этого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="a5580-108">The new operation specifies the ***length*** of the new array instance, which is then fixed for the lifetime of the instance.</span></span> <span data-ttu-id="a5580-109">Элементы массива имеют индексы в диапазоне от `0` до `Length - 1`.</span><span class="sxs-lookup"><span data-stu-id="a5580-109">The indices of the elements of an array range from `0` to `Length - 1`.</span></span> <span data-ttu-id="a5580-110">Оператор `new` автоматически инициализирует все элементы массива значением по умолчанию. Например, для всех числовых типов устанавливается нулевое значение, а для всех ссылочных типов — значение `null`.</span><span class="sxs-lookup"><span data-stu-id="a5580-110">The `new` operator automatically initializes the elements of an array to their default value, which, for example, is zero for all numeric types and `null` for all reference types.</span></span>

<span data-ttu-id="a5580-111">Следующий пример кода создает массив из `int` элементов, затем инициализирует этот массив и выводит содержимое массива.</span><span class="sxs-lookup"><span data-stu-id="a5580-111">The following example creates an array of `int` elements, initializes the array, and prints out the contents of the array.</span></span>

[!code-csharp[ArraySample](../../../samples/snippets/csharp/tour/arrays/Program.cs#L3-L18)]

<span data-ttu-id="a5580-112">Этот пример создает и использует ***одномерный массив***.</span><span class="sxs-lookup"><span data-stu-id="a5580-112">This example creates and operates on a ***single-dimensional array***.</span></span> <span data-ttu-id="a5580-113">Кроме этого, C# поддерживает ***многомерные массивы***.</span><span class="sxs-lookup"><span data-stu-id="a5580-113">C# also supports ***multi-dimensional arrays***.</span></span> <span data-ttu-id="a5580-114">Число измерений массива, которое именуется ***рангом*** для типа массива, всегда на единицу больше числа запятых, включенных в квадратные скобки типа массива.</span><span class="sxs-lookup"><span data-stu-id="a5580-114">The number of dimensions of an array type, also known as the ***rank*** of the array type, is one plus the number of commas written between the square brackets of the array type.</span></span> <span data-ttu-id="a5580-115">Следующий пример кода поочередно создает одномерный, двухмерный и трехмерный массивы.</span><span class="sxs-lookup"><span data-stu-id="a5580-115">The following example allocates a single-dimensional, a two-dimensional, and a three-dimensional array, respectively.</span></span>

[!code-csharp[ArrayRank](../../../samples/snippets/csharp/tour/arrays/Program.cs#L24-L26)]

<span data-ttu-id="a5580-116">Массив `a1` содержит 10 элементов, массив `a2` — 50 элементов (10 × 5), и наконец `a3` содержит 100 элементов (10 × 5 × 2).</span><span class="sxs-lookup"><span data-stu-id="a5580-116">The `a1` array contains 10 elements, the `a2` array contains 50 (10 × 5) elements, and the `a3` array contains 100 (10 × 5 × 2) elements.</span></span>
<span data-ttu-id="a5580-117">Элементы массива могут иметь любой тип, в том числе тип массива.</span><span class="sxs-lookup"><span data-stu-id="a5580-117">The element type of an array can be any type, including an array type.</span></span> <span data-ttu-id="a5580-118">Массив с элементами типа массива иногда называют ***массивом массивов***, так как элементы такого массива не обязаны иметь одинаковую длину.</span><span class="sxs-lookup"><span data-stu-id="a5580-118">An array with elements of an array type is sometimes called a ***jagged array*** because the lengths of the element arrays don't all have to be the same.</span></span> <span data-ttu-id="a5580-119">Следующий пример создает массив массивов `int`.</span><span class="sxs-lookup"><span data-stu-id="a5580-119">The following example allocates an array of arrays of `int`:</span></span>

[!code-csharp[ArrayAllocation](../../../samples/snippets/csharp/tour/arrays/Program.cs#L31-L34)]

<span data-ttu-id="a5580-120">В первой строке создается массив с тремя элементами, каждый из которых имеет тип `int[]` и начальное значение `null`.</span><span class="sxs-lookup"><span data-stu-id="a5580-120">The first line creates an array with three elements, each of type `int[]` and each with an initial value of `null`.</span></span> <span data-ttu-id="a5580-121">В последующих строках эти три элемента инициализируются ссылками на отдельные экземпляры массивов различной длины.</span><span class="sxs-lookup"><span data-stu-id="a5580-121">The subsequent lines then initialize the three elements with references to individual array instances of varying lengths.</span></span>

<span data-ttu-id="a5580-122">Оператор new позволяет задать начальные значения элементов массива, используя ***инициализатор массива***. Так называется список выражений, записанных между разделителями `{` и `}`.</span><span class="sxs-lookup"><span data-stu-id="a5580-122">The new operator permits the initial values of the array elements to be specified using an ***array initializer***, which is a list of expressions written between the delimiters `{` and `}`.</span></span> <span data-ttu-id="a5580-123">Следующий пример создает и инициализирует массив `int[]` с тремя элементами.</span><span class="sxs-lookup"><span data-stu-id="a5580-123">The following example allocates and initializes an `int[]` with three elements.</span></span>

[!code-csharp[ArrayInitialization](../../../samples/snippets/csharp/tour/arrays/Program.cs#L39-L39)]

<span data-ttu-id="a5580-124">Длина массива определяется по числу выражений между скобками { и }.</span><span class="sxs-lookup"><span data-stu-id="a5580-124">The length of the array is inferred from the number of expressions between { and }.</span></span> <span data-ttu-id="a5580-125">Локальные объявления переменных и полей можно сократить, поскольку тип массива не обязательно объявлять повторно.</span><span class="sxs-lookup"><span data-stu-id="a5580-125">Local variable and field declarations can be shortened further such that the array type does not have to be restated.</span></span>

[!code-csharp[ArrayInitialization](../../../samples/snippets/csharp/tour/arrays/Program.cs#L44-L44)]

<span data-ttu-id="a5580-126">Оба приведенных выше примера дают результат, эквивалентный следующему коду:</span><span class="sxs-lookup"><span data-stu-id="a5580-126">Both of the previous examples are equivalent to the following code:</span></span>

[!code-csharp[ArrayAssignment](../../../samples/snippets/csharp/tour/arrays/Program.cs#L49-L53)]

>[!div class="step-by-step"]
><span data-ttu-id="a5580-127">[Назад](classes-and-objects.md)
>[Вперед](interfaces.md)</span><span class="sxs-lookup"><span data-stu-id="a5580-127">[Previous](classes-and-objects.md)
[Next](interfaces.md)</span></span>
