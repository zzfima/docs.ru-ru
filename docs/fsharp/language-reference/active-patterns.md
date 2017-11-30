---
title: "Активные шаблоны (F#)"
description: "Узнайте, как определять именованные разделы, на которые подразделяются входные данные в языке F # в активные шаблоны."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 11a724ff-f9ff-4056-b5e0-87e9ed986f4a
ms.openlocfilehash: 845184e6150cf0b93393038ca3d39f0e6d898a2e
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="active-patterns"></a><span data-ttu-id="8d675-104">Активные шаблоны</span><span class="sxs-lookup"><span data-stu-id="8d675-104">Active Patterns</span></span>

<span data-ttu-id="8d675-105">*Активные шаблоны* позволяют определять именованные разделы, на которые подразделяются входные данные, чтобы эти имена можно использовать в выражении шаблона так же, как и для размеченного объединения.</span><span class="sxs-lookup"><span data-stu-id="8d675-105">*Active patterns* enable you to define named partitions that subdivide input data, so that you can use these names in a pattern matching expression just as you would for a discriminated union.</span></span> <span data-ttu-id="8d675-106">Активные шаблоны можно использовать для разложения данных в настраиваемом порядке для каждого раздела.</span><span class="sxs-lookup"><span data-stu-id="8d675-106">You can use active patterns to decompose data in a customized manner for each partition.</span></span>


## <a name="syntax"></a><span data-ttu-id="8d675-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d675-107">Syntax</span></span>

```fsharp
// Complete active pattern definition.
let (|identifer1|identifier2|...|) [ arguments ] = expression
// Partial active pattern definition.
let (|identifier|_|) [ arguments ] = expression
```

## <a name="remarks"></a><span data-ttu-id="8d675-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="8d675-108">Remarks</span></span>
<span data-ttu-id="8d675-109">В предыдущем синтаксисе идентификаторы — это имена разделов входных данных, представленного *аргументы*, или, иными словами, имена подмножеств набора всех значений аргументов.</span><span class="sxs-lookup"><span data-stu-id="8d675-109">In the previous syntax, the identifiers are names for partitions of the input data that is represented by *arguments*, or, in other words, names for subsets of the set of all values of the arguments.</span></span> <span data-ttu-id="8d675-110">Активное определение шаблона может быть до семи секций.</span><span class="sxs-lookup"><span data-stu-id="8d675-110">There can be up to seven partitions in an active pattern definition.</span></span> <span data-ttu-id="8d675-111">*Выражение* описание формы, которые разбиваются данные.</span><span class="sxs-lookup"><span data-stu-id="8d675-111">The *expression* describes the form into which to decompose the data.</span></span> <span data-ttu-id="8d675-112">Активное определение шаблона можно использовать для определения правил по выбору именованные разделы значения, заданные в виде аргументы принадлежат.</span><span class="sxs-lookup"><span data-stu-id="8d675-112">You can use an active pattern definition to define the rules for determining which of the named partitions the values given as arguments belong to.</span></span> <span data-ttu-id="8d675-113">(| И |) символы называются *клипы банана* и вызывается функция, созданная этим типом привязки let *активный распознаватель*.</span><span class="sxs-lookup"><span data-stu-id="8d675-113">The (| and |) symbols are referred to as *banana clips* and the function created by this type of let binding is called an *active recognizer*.</span></span>

<span data-ttu-id="8d675-114">Например рассмотрим следующий активный шаблон с аргументом.</span><span class="sxs-lookup"><span data-stu-id="8d675-114">As an example, consider the following active pattern with an argument.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

<span data-ttu-id="8d675-115">Активный шаблон можно использовать в выражении шаблона, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8d675-115">You can use the active pattern in a pattern matching expression, as in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

<span data-ttu-id="8d675-116">Выходные данные этой программы выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8d675-116">The output of this program is as follows:</span></span>

```
7 is odd
11 is odd
32 is even
```

<span data-ttu-id="8d675-117">Другой активных шаблонов используется для разложения типов данных различными способами, например, если существует несколько возможных представлений в те же базовые данные.</span><span class="sxs-lookup"><span data-stu-id="8d675-117">Another use of active patterns is to decompose data types in multiple ways, such as when the same underlying data has various possible representations.</span></span> <span data-ttu-id="8d675-118">Например `Color` объекта можно разложить на представления RGB или HSB.</span><span class="sxs-lookup"><span data-stu-id="8d675-118">For example, a `Color` object could be decomposed into an RGB representation or an HSB representation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

<span data-ttu-id="8d675-119">Выходные данные программы выше выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8d675-119">The output of the above program is as follows:</span></span>

```
Red
 Red: 255 Green: 0 Blue: 0
 Hue: 360.000000 Saturation: 1.000000 Brightness: 0.500000
Black
 Red: 0 Green: 0 Blue: 0
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.000000
White
 Red: 255 Green: 255 Blue: 255
 Hue: 0.000000 Saturation: 0.000000 Brightness: 1.000000
Gray
 Red: 128 Green: 128 Blue: 128
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.501961
BlanchedAlmond
 Red: 255 Green: 235 Blue: 205
 Hue: 36.000000 Saturation: 1.000000 Brightness: 0.901961
```

<span data-ttu-id="8d675-120">В сочетании эти два способа использования активные шаблоны позволяют объединить в секцию и разбить данные на нужной форме и совершать соответствующие вычисления с нужными данными в форме, наиболее подходящие для вычисления.</span><span class="sxs-lookup"><span data-stu-id="8d675-120">In combination, these two ways of using active patterns enable you to partition and decompose data into just the appropriate form and perform the appropriate computations on the appropriate data in the form most convenient for the computation.</span></span>

<span data-ttu-id="8d675-121">Получающиеся выражения шаблона включить данные будут записываться в удобным способом, который очень прочтение, упрощая потенциально сложное ветвление и код анализа данных.</span><span class="sxs-lookup"><span data-stu-id="8d675-121">The resulting pattern matching expressions enable data to be written in a convenient way that is very readable, greatly simplifying potentially complex branching and data analysis code.</span></span>


## <a name="partial-active-patterns"></a><span data-ttu-id="8d675-122">Частично активные шаблоны</span><span class="sxs-lookup"><span data-stu-id="8d675-122">Partial Active Patterns</span></span>
<span data-ttu-id="8d675-123">В некоторых случаях необходимо разделы только часть пространства входных данных.</span><span class="sxs-lookup"><span data-stu-id="8d675-123">Sometimes, you need to partition only part of the input space.</span></span> <span data-ttu-id="8d675-124">В этом случае набор частичных шаблонов записи из которых соответствует некоторых входных данных, но не соответствует другие входные данные.</span><span class="sxs-lookup"><span data-stu-id="8d675-124">In that case, you write a set of partial patterns each of which match some inputs but fail to match other inputs.</span></span> <span data-ttu-id="8d675-125">Активные шаблоны, которые не всегда производят значение, называются *частично активные шаблоны*; они имеют возвращает значение, которое имеет тип параметра.</span><span class="sxs-lookup"><span data-stu-id="8d675-125">Active patterns that do not always produce a value are called *partial active patterns*; they have a return value that is an option type.</span></span> <span data-ttu-id="8d675-126">Чтобы определить частичный активный шаблон, используйте подстановочный знак (_) в конце списка шаблонов банана клипы.</span><span class="sxs-lookup"><span data-stu-id="8d675-126">To define a partial active pattern, you use a wildcard character (_) at the end of the list of patterns inside the banana clips.</span></span> <span data-ttu-id="8d675-127">Следующий код иллюстрирует использование частичного активного шаблона.</span><span class="sxs-lookup"><span data-stu-id="8d675-127">The following code illustrates the use of a partial active pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

<span data-ttu-id="8d675-128">Выходные данные предыдущего примера выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8d675-128">The output of the previous example is as follows:</span></span>

```
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

<span data-ttu-id="8d675-129">При использовании частично активные шаблоны, иногда отдельные параметры могут быть несвязанными или взаимоисключающими, но не обязательно.</span><span class="sxs-lookup"><span data-stu-id="8d675-129">When using partial active patterns, sometimes the individual choices can be disjoint or mutually exclusive, but they need not be.</span></span> <span data-ttu-id="8d675-130">В следующем примере квадрат шаблон и шаблон куба не являются несвязанными, так как некоторые числа квадраты и кубов, например 64.</span><span class="sxs-lookup"><span data-stu-id="8d675-130">In the following example, the pattern Square and the pattern Cube are not disjoint, because some numbers are both squares and cubes, such as 64.</span></span> <span data-ttu-id="8d675-131">Следующая программа выводит все целые числа до 1000000, которые квадратов и кубов.</span><span class="sxs-lookup"><span data-stu-id="8d675-131">The following program prints out all integers up to 1000000 that are both squares and cubes.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

<span data-ttu-id="8d675-132">Выходные данные выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8d675-132">The output is as follows:</span></span>

```
1
64
729
4096
15625
46656
117649
262144
531441
1000000
```

## <a name="parameterized-active-patterns"></a><span data-ttu-id="8d675-133">Параметризованные активные шаблоны</span><span class="sxs-lookup"><span data-stu-id="8d675-133">Parameterized Active Patterns</span></span>
<span data-ttu-id="8d675-134">Активные шаблоны всегда принимают хотя бы один аргумент для сопоставляемого элемента, но могут стать дополнительные аргументы, в этом случае имя *параметризованный активный шаблон* применяется.</span><span class="sxs-lookup"><span data-stu-id="8d675-134">Active patterns always take at least one argument for the item being matched, but they may take additional arguments as well, in which case the name *parameterized active pattern* applies.</span></span> <span data-ttu-id="8d675-135">Дополнительные аргументы позволяют общий шаблон для специализации.</span><span class="sxs-lookup"><span data-stu-id="8d675-135">Additional arguments allow a general pattern to be specialized.</span></span> <span data-ttu-id="8d675-136">Например, активные шаблоны, которые используют регулярные выражения для анализа строк, часто включают регулярное выражение в качестве дополнительного параметра, как в следующем коде, которая также использует частичный активный шаблон `Integer` определенный в предыдущем примере кода.</span><span class="sxs-lookup"><span data-stu-id="8d675-136">For example, active patterns that use regular expressions to parse strings often include the regular expression as an extra parameter, as in the following code, which also uses the partial active pattern `Integer` defined in the previous code example.</span></span> <span data-ttu-id="8d675-137">В этом примере строки, которые используют регулярные выражения для различных форматов дат, предоставленные настроить общий активный шаблон ParseRegex.</span><span class="sxs-lookup"><span data-stu-id="8d675-137">In this example, strings that use regular expressions for various date formats are given to customize the general ParseRegex active pattern.</span></span> <span data-ttu-id="8d675-138">Активный шаблон Integer используется для преобразования соответствующие строки в целые числа, которые можно передать конструктору DateTime.</span><span class="sxs-lookup"><span data-stu-id="8d675-138">The Integer active pattern is used to convert the matched strings into integers that can be passed to the DateTime constructor.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

<span data-ttu-id="8d675-139">Результат выполнения предыдущего кода выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8d675-139">The output of the previous code is as follows:</span></span>

```
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

<span data-ttu-id="8d675-140">Активные шаблоны не ограничиваются только шаблон выражения, их также можно использовать в привязках let.</span><span class="sxs-lookup"><span data-stu-id="8d675-140">Active patterns are not restricted only to pattern matching expressions, you can also use them on let-bindings.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

<span data-ttu-id="8d675-141">Результат выполнения предыдущего кода выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8d675-141">The output of the previous code is as follows:</span></span>

```
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a><span data-ttu-id="8d675-142">См. также</span><span class="sxs-lookup"><span data-stu-id="8d675-142">See Also</span></span>
[<span data-ttu-id="8d675-143">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="8d675-143">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="8d675-144">Выражения match</span><span class="sxs-lookup"><span data-stu-id="8d675-144">Match Expressions</span></span>](match-expressions.md)

