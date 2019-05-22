---
title: Анализ диапазонов данных с помощью индексов и диапазонов
description: В этом учебнике подробно рассказывается, как анализировать данные с помощью индексов и диапазонов и, таким образом, изучать срезы последовательного набора данных.
ms.date: 04/19/2019
ms.custom: mvc
ms.openlocfilehash: 64fae4581e265d4f70b8356d5c651b4fdaca3fe9
ms.sourcegitcommit: dd3b897feb5c4ac39732bb165848e37a344b0765
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/25/2019
ms.locfileid: "64431491"
---
# <a name="indices-and-ranges"></a><span data-ttu-id="a1dfb-103">Индексы и диапазоны</span><span class="sxs-lookup"><span data-stu-id="a1dfb-103">Indices and ranges</span></span>

<span data-ttu-id="a1dfb-104">Диапазоны и индексы обеспечивают лаконичный синтаксис для доступа к отдельным элементам или диапазонам в <xref:System.Array>, <xref:System.Span%601> или <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-104">Ranges and indices provide a succinct syntax for accessing single elements or ranges in an <xref:System.Array>, <xref:System.Span%601>, or <xref:System.ReadOnlySpan%601>.</span></span> <span data-ttu-id="a1dfb-105">Благодаря этим функциям синтаксис для доступа к отдельным элементам или диапазонам элементов в последовательности становится более четким и понятным.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-105">These features enable more concise, clear syntax to access single elements or ranges of elements in a sequence.</span></span>

<span data-ttu-id="a1dfb-106">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="a1dfb-106">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="a1dfb-107">Использовать этот синтаксис для диапазонов в последовательности.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-107">Use the syntax for ranges in a sequence.</span></span>
> * <span data-ttu-id="a1dfb-108">Проектировать начало и конец каждой последовательности.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-108">Understand the design decisions for the start and end of each sequence.</span></span>
> * <span data-ttu-id="a1dfb-109">Составлять сценарии для типов <xref:System.Index> и <xref:System.Range>.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-109">Learn scenarios for the <xref:System.Index> and <xref:System.Range> types.</span></span>

## <a name="language-support-for-indices-and-ranges"></a><span data-ttu-id="a1dfb-110">Поддержка языков для индексов и диапазонов</span><span class="sxs-lookup"><span data-stu-id="a1dfb-110">Language support for indices and ranges</span></span>

<span data-ttu-id="a1dfb-111">Можно указать индекс **с конца**, вставив перед индексом символ `^`.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-111">You can specify an index **from the end** using the `^` character before the index.</span></span> <span data-ttu-id="a1dfb-112">Индексирование с конца начинается с правила, которое `0..^0` указывает весь диапазон.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-112">Indexing from the end starts from the rule that `0..^0` specifies the entire range.</span></span> <span data-ttu-id="a1dfb-113">Чтобы перечислить полный массив, начните *с первого элемента* и продолжайте, пока не пройдете *последний элемент*.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-113">To enumerate an entire array, you start *at the first element*, and continue until you are *past the last element*.</span></span> <span data-ttu-id="a1dfb-114">Можно рассмотреть поведение метода `MoveNext` перечислителя: он возвращает значение false по прохождении последнего элемента перечисления.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-114">Think of the behavior of the `MoveNext` method on an enumerator: it returns false when the enumeration passes the last element.</span></span> <span data-ttu-id="a1dfb-115">Индекс `^0` означает "конец", `array[array.Length]` или индекс, который следует за последним элементом.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-115">The index `^0` means "the end", `array[array.Length]`, or the index that follows the last element.</span></span> <span data-ttu-id="a1dfb-116">Вы знакомы с выражением `array[2]`, то есть элемент "2 с самого начала".</span><span class="sxs-lookup"><span data-stu-id="a1dfb-116">You are familiar with `array[2]` meaning the element "2 from the start".</span></span> <span data-ttu-id="a1dfb-117">Теперь выражение `array[^2]` означает элемент "2 с конца".</span><span class="sxs-lookup"><span data-stu-id="a1dfb-117">Now, `array[^2]` means the element "2 from the end".</span></span> 

<span data-ttu-id="a1dfb-118">Вы можете указать **диапазон** с помощью **оператора диапазона**: `..`.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-118">You can specify a **range** with the **range operator**: `..`.</span></span> <span data-ttu-id="a1dfb-119">Например, оператор `0..^0` указывает весь диапазон массива: 0 от начала до, но не включая 0 с конца.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-119">For example, `0..^0` specifies the entire range of the array: 0 from the start up to, but not including 0 from the end.</span></span> <span data-ttu-id="a1dfb-120">Любой операнд может использовать элемент "от начала" или "с конца".</span><span class="sxs-lookup"><span data-stu-id="a1dfb-120">Either operand may use "from the start" or "from the end".</span></span> <span data-ttu-id="a1dfb-121">Кроме того, можно опустить один из операндов.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-121">Furthermore, either operand may be omitted.</span></span> <span data-ttu-id="a1dfb-122">По умолчанию оператор `0` используется для начального индекса, а `^0` — для конечного индекса.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-122">The defaults are `0` for the start index, and `^0` for the end index.</span></span>

```csharp-interactive
string[] words = new string[]
{
                // index from start    index from end
    "The",      // 0                   ^9
    "quick",    // 1                   ^8
    "brown",    // 2                   ^7
    "fox",      // 3                   ^6
    "jumped",   // 4                   ^5
    "over",     // 5                   ^4
    "the",      // 6                   ^3
    "lazy",     // 7                   ^2
    "dog"       // 8                   ^1
};              // 9 (or words.Length) ^0
```

<span data-ttu-id="a1dfb-123">Индекс каждого элемента вводит понятие "от начала" и "от конца", и диапазоны указаны без учета конца диапазона.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-123">The index of each element reinforces the concept of "from the start", and "from the end", and that ranges are exclusive of the end of the range.</span></span> <span data-ttu-id="a1dfb-124">"Начало" всего массива является первым элементом.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-124">The "start" of the entire array is the first element.</span></span> <span data-ttu-id="a1dfb-125">"Конец" всего массива следует *после* последнего элемента.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-125">The "end" of the entire array is *past* the last element.</span></span>

<span data-ttu-id="a1dfb-126">Последнее слово можно получить с помощью индекса `^1`.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-126">You can retrieve the last word with the `^1` index.</span></span> <span data-ttu-id="a1dfb-127">Добавьте следующий код после инициализации:</span><span class="sxs-lookup"><span data-stu-id="a1dfb-127">Add the following code below the initialization:</span></span>

[!code-csharp[LastIndex](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastIndex)]

<span data-ttu-id="a1dfb-128">Следующий код создает поддиапазон со словами "quick", "brown" и "fox".</span><span class="sxs-lookup"><span data-stu-id="a1dfb-128">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="a1dfb-129">Он включает в себя элементы от `words[1]` до `words[3]`.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-129">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="a1dfb-130">Элемент `words[4]` в диапазон не входит.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-130">The element `words[4]` isn't in the range.</span></span> <span data-ttu-id="a1dfb-131">Добавьте в тот же метод указанный ниже код.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-131">Add the following code to the same method.</span></span> <span data-ttu-id="a1dfb-132">Скопируйте и вставьте этот код в нижней части интерактивного окна.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-132">Copy and paste it at the bottom of the interactive window.</span></span>

[!code-csharp[Range](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Range)]

<span data-ttu-id="a1dfb-133">Следующий код создает поддиапазон со словами "lazy" и "dog".</span><span class="sxs-lookup"><span data-stu-id="a1dfb-133">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="a1dfb-134">Он включает элементы `words[^2]` и `words[^1]`.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-134">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="a1dfb-135">Конечный индекс `words[^0]` не включен.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-135">The end index `words[^0]` isn't included.</span></span> <span data-ttu-id="a1dfb-136">Добавьте также следующий код:</span><span class="sxs-lookup"><span data-stu-id="a1dfb-136">Add the following code as well:</span></span>

[!code-csharp[LastRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastRange)]

<span data-ttu-id="a1dfb-137">В следующих примерах создаются диапазоны, которые должны быть открыты для начала, конца или в обоих случаях:</span><span class="sxs-lookup"><span data-stu-id="a1dfb-137">The following examples create ranges that are open ended for the start, end, or both:</span></span>

[!code-csharp[PartialRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_PartialRanges)]

<span data-ttu-id="a1dfb-138">Диапазоны или индексы можно также объявлять как переменные.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-138">You can also declare ranges or indices as variables.</span></span> <span data-ttu-id="a1dfb-139">Впоследствии такую переменную можно использовать внутри символов `[` и `]`:</span><span class="sxs-lookup"><span data-stu-id="a1dfb-139">The variable can then be used inside the `[` and `]` characters:</span></span>

[!code-csharp[IndexRangeTypes](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_RangeIndexTypes)]

<span data-ttu-id="a1dfb-140">В предыдущих примерах представлены два проектных решения, которые требуют более подробного объяснения:</span><span class="sxs-lookup"><span data-stu-id="a1dfb-140">The previous examples show two design decisions that require more explanation:</span></span>

- <span data-ttu-id="a1dfb-141">Диапазоны *исключительны*, т. е. элемент с последним индексом в диапазон не входит.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-141">Ranges are *exclusive*, meaning the element at the last index isn't in the range.</span></span>
- <span data-ttu-id="a1dfb-142">Индекс `^0` — это *конец* коллекции, а не *последний элемент* в коллекции.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-142">The index `^0` is *the end* of the collection, not *the last element* in the collection.</span></span>

<span data-ttu-id="a1dfb-143">Следующий пример демонстрирует многие возможные причины для таких решений.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-143">The following sample shows many of the reasons for those choices.</span></span> <span data-ttu-id="a1dfb-144">Измените `x`, `y` и `z` и опробуйте различные комбинации.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-144">Modify `x`, `y`, and `z` to try different combinations.</span></span> <span data-ttu-id="a1dfb-145">Поэкспериментируйте со значениями, у которых `x` меньше `y`, а `y` меньше, чем `z` для допустимых сочетаний.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-145">When you experiment, use values where `x` is less than `y`, and `y` is less than `z` for valid combinations.</span></span> <span data-ttu-id="a1dfb-146">Добавьте в новый метод приведенный ниже код.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-146">Add the following code in a new method.</span></span> <span data-ttu-id="a1dfb-147">Опробуйте различные комбинации:</span><span class="sxs-lookup"><span data-stu-id="a1dfb-147">Try different combinations:</span></span>

[!code-csharp[SemanticsExamples](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Semantics)]

## <a name="scenarios-for-indices-and-ranges"></a><span data-ttu-id="a1dfb-148">Сценарии для индексов и диапазонов</span><span class="sxs-lookup"><span data-stu-id="a1dfb-148">Scenarios for Indices and Ranges</span></span>

<span data-ttu-id="a1dfb-149">Часто для анализа отдельного поддиапазона последовательности используются диапазоны и индексы.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-149">You'll often use ranges and indices when you want to perform some analysis on subrange of an entire sequence.</span></span> <span data-ttu-id="a1dfb-150">В новом синтаксисе легче понять, о каком поддиапазоне идет речь.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-150">The new syntax is clearer in reading exactly what subrange is involved.</span></span> <span data-ttu-id="a1dfb-151">Локальная функция `MovingAverage` принимает <xref:System.Range> в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-151">The local function `MovingAverage` takes a <xref:System.Range> as its argument.</span></span> <span data-ttu-id="a1dfb-152">После этого метод перечисляет только это диапазон и вычисляет минимальное, максимальное и среднее значение.</span><span class="sxs-lookup"><span data-stu-id="a1dfb-152">The method then enumerates just that range when calculating the min, max, and average.</span></span> <span data-ttu-id="a1dfb-153">Попробуйте добавить в свой проект следующий код:</span><span class="sxs-lookup"><span data-stu-id="a1dfb-153">Try the following code in your project:</span></span>

[!code-csharp[MovingAverages](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_MovingAverage)]

<span data-ttu-id="a1dfb-154">Готовый код можно загрузить из репозитория [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes).</span><span class="sxs-lookup"><span data-stu-id="a1dfb-154">You can download the completed code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) repository.</span></span>
