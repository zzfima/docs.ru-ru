---
title: Анализ диапазонов данных с помощью индексов и диапазонов
description: В этом учебнике подробно рассказывается, как анализировать данные с помощью индексов и диапазонов и, таким образом, изучать срезы последовательного набора данных.
ms.date: 09/20/2019
ms.technology: csharp-fundamentals
ms.custom: mvc
ms.openlocfilehash: bbf3f257db9079c4f69f25c9ea08e7711b5ea04b
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039675"
---
# <a name="indices-and-ranges"></a><span data-ttu-id="8291b-103">Индексы и диапазоны</span><span class="sxs-lookup"><span data-stu-id="8291b-103">Indices and ranges</span></span>

<span data-ttu-id="8291b-104">Диапазоны и индексы обеспечивают лаконичный синтаксис для доступа к отдельным элементам или диапазонам в последовательности.</span><span class="sxs-lookup"><span data-stu-id="8291b-104">Ranges and indices provide a succinct syntax for accessing single elements or ranges in a sequence.</span></span>

<span data-ttu-id="8291b-105">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="8291b-105">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="8291b-106">Использовать этот синтаксис для диапазонов в последовательности.</span><span class="sxs-lookup"><span data-stu-id="8291b-106">Use the syntax for ranges in a sequence.</span></span>
> - <span data-ttu-id="8291b-107">Проектировать начало и конец каждой последовательности.</span><span class="sxs-lookup"><span data-stu-id="8291b-107">Understand the design decisions for the start and end of each sequence.</span></span>
> - <span data-ttu-id="8291b-108">Составлять сценарии для типов <xref:System.Index> и <xref:System.Range>.</span><span class="sxs-lookup"><span data-stu-id="8291b-108">Learn scenarios for the <xref:System.Index> and <xref:System.Range> types.</span></span>

## <a name="language-support-for-indices-and-ranges"></a><span data-ttu-id="8291b-109">Поддержка языков для индексов и диапазонов</span><span class="sxs-lookup"><span data-stu-id="8291b-109">Language support for indices and ranges</span></span>

<span data-ttu-id="8291b-110">Поддержка языков опирается на два новых типа и два новых оператора:</span><span class="sxs-lookup"><span data-stu-id="8291b-110">This language support relies on two new types and two new operators:</span></span>

- <span data-ttu-id="8291b-111"><xref:System.Index?displayProperty=nameWithType> представляет индекс в последовательности.</span><span class="sxs-lookup"><span data-stu-id="8291b-111"><xref:System.Index?displayProperty=nameWithType> represents an index into a sequence.</span></span>
- <span data-ttu-id="8291b-112">Оператор `^` (индекс с конца), который указывает, что индекс указан относительно конца последовательности.</span><span class="sxs-lookup"><span data-stu-id="8291b-112">The index from end operator `^`, which specifies that an index is relative to the end of a sequence.</span></span>
- <span data-ttu-id="8291b-113"><xref:System.Range?displayProperty=nameWithType> представляет вложенный диапазон последовательности.</span><span class="sxs-lookup"><span data-stu-id="8291b-113"><xref:System.Range?displayProperty=nameWithType> represents a sub range of a sequence.</span></span>
- <span data-ttu-id="8291b-114">Оператор диапазона `..`, который задает начало и конец диапазона в качестве своих операндов.</span><span class="sxs-lookup"><span data-stu-id="8291b-114">The range operator `..`, which specifies the start and end of a range as its operands.</span></span>

<span data-ttu-id="8291b-115">Начнем с правил для использования в индексах.</span><span class="sxs-lookup"><span data-stu-id="8291b-115">Let's start with the rules for indices.</span></span> <span data-ttu-id="8291b-116">Рассмотрим массив `sequence`.</span><span class="sxs-lookup"><span data-stu-id="8291b-116">Consider an array `sequence`.</span></span> <span data-ttu-id="8291b-117">Индекс `0` совпадает с `sequence[0]`.</span><span class="sxs-lookup"><span data-stu-id="8291b-117">The `0` index is the same as `sequence[0]`.</span></span> <span data-ttu-id="8291b-118">Индекс `^0` совпадает с `sequence[sequence.Length]`.</span><span class="sxs-lookup"><span data-stu-id="8291b-118">The `^0` index is the same as `sequence[sequence.Length]`.</span></span> <span data-ttu-id="8291b-119">Обратите внимание, что `sequence[^0]` создает исключение так же, как и `sequence[sequence.Length]`.</span><span class="sxs-lookup"><span data-stu-id="8291b-119">Note that `sequence[^0]` does throw an exception, just as `sequence[sequence.Length]` does.</span></span> <span data-ttu-id="8291b-120">Для любого числа `n` индекс `^n` совпадает с `sequence[sequence.Length - n]`.</span><span class="sxs-lookup"><span data-stu-id="8291b-120">For any number `n`, the index `^n` is the same as `sequence[sequence.Length - n]`.</span></span>

```csharp
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

<span data-ttu-id="8291b-121">Последнее слово можно получить с помощью индекса `^1`.</span><span class="sxs-lookup"><span data-stu-id="8291b-121">You can retrieve the last word with the `^1` index.</span></span> <span data-ttu-id="8291b-122">Добавьте следующий код после инициализации:</span><span class="sxs-lookup"><span data-stu-id="8291b-122">Add the following code below the initialization:</span></span>

[!code-csharp[LastIndex](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastIndex)]

<span data-ttu-id="8291b-123">Диапазон указывает *начало* и *конец* диапазона.</span><span class="sxs-lookup"><span data-stu-id="8291b-123">A range specifies the *start* and *end* of a range.</span></span> <span data-ttu-id="8291b-124">Диапазоны являются открытыми, то есть *конечное значение* не включается в диапазон.</span><span class="sxs-lookup"><span data-stu-id="8291b-124">Ranges are exclusive, meaning the *end* is not included in the range.</span></span> <span data-ttu-id="8291b-125">Диапазон `[0..^0]` представляет весь диапазон так же, как `[0..sequence.Length]` представляет весь диапазон.</span><span class="sxs-lookup"><span data-stu-id="8291b-125">The range `[0..^0]` represents the entire range, just as `[0..sequence.Length]` represents the entire range.</span></span> 

<span data-ttu-id="8291b-126">Следующий код создает поддиапазон со словами "quick", "brown" и "fox".</span><span class="sxs-lookup"><span data-stu-id="8291b-126">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="8291b-127">Он включает в себя элементы от `words[1]` до `words[3]`.</span><span class="sxs-lookup"><span data-stu-id="8291b-127">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="8291b-128">Элемент `words[4]` в диапазон не входит.</span><span class="sxs-lookup"><span data-stu-id="8291b-128">The element `words[4]` isn't in the range.</span></span> <span data-ttu-id="8291b-129">Добавьте в тот же метод указанный ниже код.</span><span class="sxs-lookup"><span data-stu-id="8291b-129">Add the following code to the same method.</span></span> <span data-ttu-id="8291b-130">Скопируйте и вставьте этот код в нижней части интерактивного окна.</span><span class="sxs-lookup"><span data-stu-id="8291b-130">Copy and paste it at the bottom of the interactive window.</span></span>

[!code-csharp[Range](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Range)]

<span data-ttu-id="8291b-131">Следующий код создает поддиапазон со словами "lazy" и "dog".</span><span class="sxs-lookup"><span data-stu-id="8291b-131">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="8291b-132">Он включает элементы `words[^2]` и `words[^1]`.</span><span class="sxs-lookup"><span data-stu-id="8291b-132">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="8291b-133">Конечный индекс `words[^0]` не включен.</span><span class="sxs-lookup"><span data-stu-id="8291b-133">The end index `words[^0]` isn't included.</span></span> <span data-ttu-id="8291b-134">Добавьте также следующий код:</span><span class="sxs-lookup"><span data-stu-id="8291b-134">Add the following code as well:</span></span>

[!code-csharp[LastRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastRange)]

<span data-ttu-id="8291b-135">В следующих примерах создаются диапазоны, которые должны быть открыты для начала, конца или в обоих случаях:</span><span class="sxs-lookup"><span data-stu-id="8291b-135">The following examples create ranges that are open ended for the start, end, or both:</span></span>

[!code-csharp[PartialRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_PartialRanges)]

<span data-ttu-id="8291b-136">Диапазоны или индексы можно также объявлять как переменные.</span><span class="sxs-lookup"><span data-stu-id="8291b-136">You can also declare ranges or indices as variables.</span></span> <span data-ttu-id="8291b-137">Впоследствии такую переменную можно использовать внутри символов `[` и `]`:</span><span class="sxs-lookup"><span data-stu-id="8291b-137">The variable can then be used inside the `[` and `]` characters:</span></span>

[!code-csharp[IndexRangeTypes](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_RangeIndexTypes)]

<span data-ttu-id="8291b-138">Следующий пример демонстрирует многие возможные причины для таких решений.</span><span class="sxs-lookup"><span data-stu-id="8291b-138">The following sample shows many of the reasons for those choices.</span></span> <span data-ttu-id="8291b-139">Измените `x`, `y` и `z` и опробуйте различные комбинации.</span><span class="sxs-lookup"><span data-stu-id="8291b-139">Modify `x`, `y`, and `z` to try different combinations.</span></span> <span data-ttu-id="8291b-140">Поэкспериментируйте со значениями, у которых `x` меньше `y`, а `y` меньше, чем `z` для допустимых сочетаний.</span><span class="sxs-lookup"><span data-stu-id="8291b-140">When you experiment, use values where `x` is less than `y`, and `y` is less than `z` for valid combinations.</span></span> <span data-ttu-id="8291b-141">Добавьте в новый метод приведенный ниже код.</span><span class="sxs-lookup"><span data-stu-id="8291b-141">Add the following code in a new method.</span></span> <span data-ttu-id="8291b-142">Опробуйте различные комбинации:</span><span class="sxs-lookup"><span data-stu-id="8291b-142">Try different combinations:</span></span>

[!code-csharp[SemanticsExamples](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Semantics)]

## <a name="type-support-for-indices-and-ranges"></a><span data-ttu-id="8291b-143">Поддержка типов для индексов и диапазонов</span><span class="sxs-lookup"><span data-stu-id="8291b-143">Type support for indices and ranges</span></span>

<span data-ttu-id="8291b-144">Если тип предоставляет [индексатор](../programming-guide/indexers/index.md) с параметром <xref:System.Index> или <xref:System.Range>, он явно поддерживает индексы или диапазоны соответственно.</span><span class="sxs-lookup"><span data-stu-id="8291b-144">If a type provides an [indexer](../programming-guide/indexers/index.md) with an <xref:System.Index> or <xref:System.Range> parameter, it explicitly supports indices or ranges respectively.</span></span>

<span data-ttu-id="8291b-145">Тип является **счетным**, если у него есть свойство с именем `Length` или `Count` с доступным методом получения и типом возвращаемого значения `int`.</span><span class="sxs-lookup"><span data-stu-id="8291b-145">A type is **countable** if it has a property named `Length` or `Count` with an accessible getter and a return type of `int`.</span></span> <span data-ttu-id="8291b-146">Счетный тип, который не поддерживает индексы или диапазоны явным образом, может предоставить неявную поддержку для них.</span><span class="sxs-lookup"><span data-stu-id="8291b-146">A countable type that doesn't explicitly support indices or ranges may provide an implicit support for them.</span></span> <span data-ttu-id="8291b-147">Дополнительные сведения см. в разделах о [поддержке неявного индекса](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-index-support) и [неявного диапазона](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-range-support) в [примечании к предлагаемой функции](~/_csharplang/proposals/csharp-8.0/ranges.md).</span><span class="sxs-lookup"><span data-stu-id="8291b-147">For more information, see the [Implicit Index support](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-index-support) and [Implicit Range support](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-range-support) sections of the [feature proposal note](~/_csharplang/proposals/csharp-8.0/ranges.md).</span></span>

<span data-ttu-id="8291b-148">Например, следующие типы .NET поддерживают как индексы, так и диапазоны: <xref:System.Array>, <xref:System.String>, <xref:System.Span%601> и <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="8291b-148">For example, the following .NET types support both indices and ranges: <xref:System.Array>, <xref:System.String>, <xref:System.Span%601>, and <xref:System.ReadOnlySpan%601>.</span></span> <span data-ttu-id="8291b-149"><xref:System.Collections.Generic.List%601> поддерживает индексы, но не поддерживает диапазоны.</span><span class="sxs-lookup"><span data-stu-id="8291b-149">The <xref:System.Collections.Generic.List%601> supports indices but doesn't support ranges.</span></span>

## <a name="scenarios-for-indices-and-ranges"></a><span data-ttu-id="8291b-150">Сценарии для индексов и диапазонов</span><span class="sxs-lookup"><span data-stu-id="8291b-150">Scenarios for indices and ranges</span></span>

<span data-ttu-id="8291b-151">Часто для анализа отдельного поддиапазона последовательности используются диапазоны и индексы.</span><span class="sxs-lookup"><span data-stu-id="8291b-151">You'll often use ranges and indices when you want to perform some analysis on subrange of an entire sequence.</span></span> <span data-ttu-id="8291b-152">В новом синтаксисе легче понять, о каком поддиапазоне идет речь.</span><span class="sxs-lookup"><span data-stu-id="8291b-152">The new syntax is clearer in reading exactly what subrange is involved.</span></span> <span data-ttu-id="8291b-153">Локальная функция `MovingAverage` принимает <xref:System.Range> в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="8291b-153">The local function `MovingAverage` takes a <xref:System.Range> as its argument.</span></span> <span data-ttu-id="8291b-154">После этого метод перечисляет только это диапазон и вычисляет минимальное, максимальное и среднее значение.</span><span class="sxs-lookup"><span data-stu-id="8291b-154">The method then enumerates just that range when calculating the min, max, and average.</span></span> <span data-ttu-id="8291b-155">Попробуйте добавить в свой проект следующий код:</span><span class="sxs-lookup"><span data-stu-id="8291b-155">Try the following code in your project:</span></span>

[!code-csharp[MovingAverages](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_MovingAverage)]

<span data-ttu-id="8291b-156">Готовый код можно загрузить из репозитория [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes).</span><span class="sxs-lookup"><span data-stu-id="8291b-156">You can download the completed code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) repository.</span></span>
