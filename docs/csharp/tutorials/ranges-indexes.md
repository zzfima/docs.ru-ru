---
title: Анализ диапазонов данных с помощью индексов и диапазонов
description: В этом учебнике подробно рассказывается, как анализировать данные с помощью индексов и диапазонов и, таким образом, изучать срезы последовательного набора данных.
ms.date: 04/19/2019
ms.custom: mvc
ms.openlocfilehash: 118d3c9ccad98ec02195c2b5e26a2ca203990adf
ms.sourcegitcommit: 682c64df0322c7bda016f8bfea8954e9b31f1990
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2019
ms.locfileid: "65557190"
---
# <a name="indices-and-ranges"></a>Индексы и диапазоны

Диапазоны и индексы обеспечивают лаконичный синтаксис для доступа к отдельным элементам или диапазонам в <xref:System.Array>, <xref:System.Span%601> или <xref:System.ReadOnlySpan%601>. Благодаря этим функциям синтаксис для доступа к отдельным элементам или диапазонам элементов в последовательности становится более четким и понятным.

В этом руководстве вы узнаете, как:

> [!div class="checklist"]
> * Использовать этот синтаксис для диапазонов в последовательности.
> * Проектировать начало и конец каждой последовательности.
> * Составлять сценарии для типов <xref:System.Index> и <xref:System.Range>.

## <a name="language-support-for-indices-and-ranges"></a>Поддержка языков для индексов и диапазонов

Поддержка языков зависит от двух новых типов и двух новых операторов.
- <xref:System.Index?displayProperty=nameWithType> представляет индекс в последовательности.
- Оператор `^`, который указывает, что индекс указан относительно конца последовательности.
- <xref:System.Range?displayProperty=nameWithType> представляет вложенный диапазон последовательности.
- Оператор диапазона (`..`), который задает начало и конец диапазона в качестве своих операндов.

Начнем с правил для использования в индексах. Рассмотрим массив `sequence`. Индекс `0` совпадает с `sequence[0]`. Индекс `^0` совпадает с `sequence[sequence.Length]`. Обратите внимание, что `sequence[^0]` создает исключение так же, как и `sequence[sequence.Length]`. Для любого числа `n` индекс `^n` совпадает с `sequence[sequence.Length - n]`.

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

Последнее слово можно получить с помощью индекса `^1`. Добавьте следующий код после инициализации:

[!code-csharp[LastIndex](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastIndex)]

Диапазон указывает *начало* и *конец* диапазона. Диапазоны являются открытыми, то есть *конечное значение* не включается в диапазон. Диапазон `[0..^0]` представляет весь диапазон так же, как `[0..sequence.Length]` представляет весь диапазон. 

Следующий код создает поддиапазон со словами "quick", "brown" и "fox". Он включает в себя элементы от `words[1]` до `words[3]`. Элемент `words[4]` в диапазон не входит. Добавьте в тот же метод указанный ниже код. Скопируйте и вставьте этот код в нижней части интерактивного окна.

[!code-csharp[Range](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Range)]

Следующий код создает поддиапазон со словами "lazy" и "dog". Он включает элементы `words[^2]` и `words[^1]`. Конечный индекс `words[^0]` не включен. Добавьте также следующий код:

[!code-csharp[LastRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastRange)]

В следующих примерах создаются диапазоны, которые должны быть открыты для начала, конца или в обоих случаях:

[!code-csharp[PartialRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_PartialRanges)]

Диапазоны или индексы можно также объявлять как переменные. Впоследствии такую переменную можно использовать внутри символов `[` и `]`:

[!code-csharp[IndexRangeTypes](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_RangeIndexTypes)]

Следующий пример демонстрирует многие возможные причины для таких решений. Измените `x`, `y` и `z` и опробуйте различные комбинации. Поэкспериментируйте со значениями, у которых `x` меньше `y`, а `y` меньше, чем `z` для допустимых сочетаний. Добавьте в новый метод приведенный ниже код. Опробуйте различные комбинации:

[!code-csharp[SemanticsExamples](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Semantics)]

## <a name="scenarios-for-indices-and-ranges"></a>Сценарии для индексов и диапазонов

Часто для анализа отдельного поддиапазона последовательности используются диапазоны и индексы. В новом синтаксисе легче понять, о каком поддиапазоне идет речь. Локальная функция `MovingAverage` принимает <xref:System.Range> в качестве аргумента. После этого метод перечисляет только это диапазон и вычисляет минимальное, максимальное и среднее значение. Попробуйте добавить в свой проект следующий код:

[!code-csharp[MovingAverages](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_MovingAverage)]

Готовый код можно загрузить из репозитория [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes).
