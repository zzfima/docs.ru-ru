---
title: Анализ диапазонов данных с помощью индексов и диапазонов
description: В этом учебнике подробно рассказывается, как анализировать данные с помощью индексов и диапазонов и, таким образом, изучать срезы последовательного набора данных.
ms.date: 04/19/2019
ms.custom: mvc
ms.openlocfilehash: 27f4b90f130345dd10517a5de78c759066afdf07
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926639"
---
# <a name="indices-and-ranges"></a><span data-ttu-id="9dbfe-103">Индексы и диапазоны</span><span class="sxs-lookup"><span data-stu-id="9dbfe-103">Indices and ranges</span></span>

<span data-ttu-id="9dbfe-104">Диапазоны и индексы обеспечивают лаконичный синтаксис для доступа к отдельным элементам или диапазонам в <xref:System.Array>, <xref:System.Span%601> или <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-104">Ranges and indices provide a succinct syntax for accessing single elements or ranges in an <xref:System.Array>, <xref:System.Span%601>, or <xref:System.ReadOnlySpan%601>.</span></span> <span data-ttu-id="9dbfe-105">Благодаря этим функциям синтаксис для доступа к отдельным элементам или диапазонам элементов в последовательности становится более четким и понятным.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-105">These features enable more concise, clear syntax to access single elements or ranges of elements in a sequence.</span></span>

<span data-ttu-id="9dbfe-106">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="9dbfe-106">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="9dbfe-107">Использовать этот синтаксис для диапазонов в последовательности.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-107">Use the syntax for ranges in a sequence.</span></span>
> - <span data-ttu-id="9dbfe-108">Проектировать начало и конец каждой последовательности.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-108">Understand the design decisions for the start and end of each sequence.</span></span>
> - <span data-ttu-id="9dbfe-109">Составлять сценарии для типов <xref:System.Index> и <xref:System.Range>.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-109">Learn scenarios for the <xref:System.Index> and <xref:System.Range> types.</span></span>

## <a name="language-support-for-indices-and-ranges"></a><span data-ttu-id="9dbfe-110">Поддержка языков для индексов и диапазонов</span><span class="sxs-lookup"><span data-stu-id="9dbfe-110">Language support for indices and ranges</span></span>

<span data-ttu-id="9dbfe-111">Поддержка языков зависит от двух новых типов и двух новых операторов.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-111">This language support relies on two new types and two new operators.</span></span>

- <span data-ttu-id="9dbfe-112"><xref:System.Index?displayProperty=nameWithType> представляет индекс в последовательности.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-112"><xref:System.Index?displayProperty=nameWithType> represents an index into a sequence.</span></span>
- <span data-ttu-id="9dbfe-113">Оператор `^`, который указывает, что индекс указан относительно конца последовательности.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-113">The `^` operator, which specifies that an index is relative to the end of a sequence.</span></span>
- <span data-ttu-id="9dbfe-114"><xref:System.Range?displayProperty=nameWithType> представляет вложенный диапазон последовательности.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-114"><xref:System.Range?displayProperty=nameWithType> represents a sub range of a sequence.</span></span>
- <span data-ttu-id="9dbfe-115">Оператор диапазона (`..`), который задает начало и конец диапазона в качестве своих операндов.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-115">The Range operator (`..`), which specifies the start and end of a range as its operands.</span></span>

<span data-ttu-id="9dbfe-116">Начнем с правил для использования в индексах.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-116">Let's start with the rules for indices.</span></span> <span data-ttu-id="9dbfe-117">Рассмотрим массив `sequence`.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-117">Consider an array `sequence`.</span></span> <span data-ttu-id="9dbfe-118">Индекс `0` совпадает с `sequence[0]`.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-118">The `0` index is the same as `sequence[0]`.</span></span> <span data-ttu-id="9dbfe-119">Индекс `^0` совпадает с `sequence[sequence.Length]`.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-119">The `^0` index is the same as `sequence[sequence.Length]`.</span></span> <span data-ttu-id="9dbfe-120">Обратите внимание, что `sequence[^0]` создает исключение так же, как и `sequence[sequence.Length]`.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-120">Note that `sequence[^0]` does throw an exception, just as `sequence[sequence.Length]` does.</span></span> <span data-ttu-id="9dbfe-121">Для любого числа `n` индекс `^n` совпадает с `sequence[sequence.Length - n]`.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-121">For any number `n`, the index `^n` is the same as `sequence[sequence.Length - n]`.</span></span>

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

<span data-ttu-id="9dbfe-122">Последнее слово можно получить с помощью индекса `^1`.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-122">You can retrieve the last word with the `^1` index.</span></span> <span data-ttu-id="9dbfe-123">Добавьте следующий код после инициализации:</span><span class="sxs-lookup"><span data-stu-id="9dbfe-123">Add the following code below the initialization:</span></span>

[!code-csharp[LastIndex](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastIndex)]

<span data-ttu-id="9dbfe-124">Диапазон указывает *начало* и *конец* диапазона.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-124">A range specifies the *start* and *end* of a range.</span></span> <span data-ttu-id="9dbfe-125">Диапазоны являются открытыми, то есть *конечное значение* не включается в диапазон.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-125">Ranges are exclusive, meaning the *end* is not included in the range.</span></span> <span data-ttu-id="9dbfe-126">Диапазон `[0..^0]` представляет весь диапазон так же, как `[0..sequence.Length]` представляет весь диапазон.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-126">The range `[0..^0]` represents the entire range, just as `[0..sequence.Length]` represents the entire range.</span></span> 

<span data-ttu-id="9dbfe-127">Следующий код создает поддиапазон со словами "quick", "brown" и "fox".</span><span class="sxs-lookup"><span data-stu-id="9dbfe-127">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="9dbfe-128">Он включает в себя элементы от `words[1]` до `words[3]`.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-128">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="9dbfe-129">Элемент `words[4]` в диапазон не входит.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-129">The element `words[4]` isn't in the range.</span></span> <span data-ttu-id="9dbfe-130">Добавьте в тот же метод указанный ниже код.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-130">Add the following code to the same method.</span></span> <span data-ttu-id="9dbfe-131">Скопируйте и вставьте этот код в нижней части интерактивного окна.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-131">Copy and paste it at the bottom of the interactive window.</span></span>

[!code-csharp[Range](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Range)]

<span data-ttu-id="9dbfe-132">Следующий код создает поддиапазон со словами "lazy" и "dog".</span><span class="sxs-lookup"><span data-stu-id="9dbfe-132">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="9dbfe-133">Он включает элементы `words[^2]` и `words[^1]`.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-133">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="9dbfe-134">Конечный индекс `words[^0]` не включен.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-134">The end index `words[^0]` isn't included.</span></span> <span data-ttu-id="9dbfe-135">Добавьте также следующий код:</span><span class="sxs-lookup"><span data-stu-id="9dbfe-135">Add the following code as well:</span></span>

[!code-csharp[LastRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastRange)]

<span data-ttu-id="9dbfe-136">В следующих примерах создаются диапазоны, которые должны быть открыты для начала, конца или в обоих случаях:</span><span class="sxs-lookup"><span data-stu-id="9dbfe-136">The following examples create ranges that are open ended for the start, end, or both:</span></span>

[!code-csharp[PartialRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_PartialRanges)]

<span data-ttu-id="9dbfe-137">Диапазоны или индексы можно также объявлять как переменные.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-137">You can also declare ranges or indices as variables.</span></span> <span data-ttu-id="9dbfe-138">Впоследствии такую переменную можно использовать внутри символов `[` и `]`:</span><span class="sxs-lookup"><span data-stu-id="9dbfe-138">The variable can then be used inside the `[` and `]` characters:</span></span>

[!code-csharp[IndexRangeTypes](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_RangeIndexTypes)]

<span data-ttu-id="9dbfe-139">Следующий пример демонстрирует многие возможные причины для таких решений.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-139">The following sample shows many of the reasons for those choices.</span></span> <span data-ttu-id="9dbfe-140">Измените `x`, `y` и `z` и опробуйте различные комбинации.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-140">Modify `x`, `y`, and `z` to try different combinations.</span></span> <span data-ttu-id="9dbfe-141">Поэкспериментируйте со значениями, у которых `x` меньше `y`, а `y` меньше, чем `z` для допустимых сочетаний.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-141">When you experiment, use values where `x` is less than `y`, and `y` is less than `z` for valid combinations.</span></span> <span data-ttu-id="9dbfe-142">Добавьте в новый метод приведенный ниже код.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-142">Add the following code in a new method.</span></span> <span data-ttu-id="9dbfe-143">Опробуйте различные комбинации:</span><span class="sxs-lookup"><span data-stu-id="9dbfe-143">Try different combinations:</span></span>

[!code-csharp[SemanticsExamples](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Semantics)]

## <a name="scenarios-for-indices-and-ranges"></a><span data-ttu-id="9dbfe-144">Сценарии для индексов и диапазонов</span><span class="sxs-lookup"><span data-stu-id="9dbfe-144">Scenarios for Indices and Ranges</span></span>

<span data-ttu-id="9dbfe-145">Часто для анализа отдельного поддиапазона последовательности используются диапазоны и индексы.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-145">You'll often use ranges and indices when you want to perform some analysis on subrange of an entire sequence.</span></span> <span data-ttu-id="9dbfe-146">В новом синтаксисе легче понять, о каком поддиапазоне идет речь.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-146">The new syntax is clearer in reading exactly what subrange is involved.</span></span> <span data-ttu-id="9dbfe-147">Локальная функция `MovingAverage` принимает <xref:System.Range> в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-147">The local function `MovingAverage` takes a <xref:System.Range> as its argument.</span></span> <span data-ttu-id="9dbfe-148">После этого метод перечисляет только это диапазон и вычисляет минимальное, максимальное и среднее значение.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-148">The method then enumerates just that range when calculating the min, max, and average.</span></span> <span data-ttu-id="9dbfe-149">Попробуйте добавить в свой проект следующий код:</span><span class="sxs-lookup"><span data-stu-id="9dbfe-149">Try the following code in your project:</span></span>

[!code-csharp[MovingAverages](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_MovingAverage)]

<span data-ttu-id="9dbfe-150">Готовый код можно загрузить из репозитория [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes).</span><span class="sxs-lookup"><span data-stu-id="9dbfe-150">You can download the completed code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) repository.</span></span>
