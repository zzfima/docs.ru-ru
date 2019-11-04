---
title: Активные шаблоны
description: Узнайте, как использовать активные шаблоны для определения именованных секций, разделяющих входные F# данные на языке программирования.
ms.date: 05/16/2016
ms.openlocfilehash: f5ed4a8600cba10d23d01628aba6ca07e543c586
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425095"
---
# <a name="active-patterns"></a><span data-ttu-id="9d84a-103">Активные шаблоны</span><span class="sxs-lookup"><span data-stu-id="9d84a-103">Active Patterns</span></span>

<span data-ttu-id="9d84a-104">*Активные шаблоны* позволяют определить именованные секции, которые подделят входные данные, чтобы эти имена можно было использовать в выражении сопоставления шаблонов точно так же, как для размеченного объединения.</span><span class="sxs-lookup"><span data-stu-id="9d84a-104">*Active patterns* enable you to define named partitions that subdivide input data, so that you can use these names in a pattern matching expression just as you would for a discriminated union.</span></span> <span data-ttu-id="9d84a-105">Активные шаблоны можно использовать для разложения данных в настраиваемом порядке для каждого раздела.</span><span class="sxs-lookup"><span data-stu-id="9d84a-105">You can use active patterns to decompose data in a customized manner for each partition.</span></span>

## <a name="syntax"></a><span data-ttu-id="9d84a-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d84a-106">Syntax</span></span>

```fsharp
// Active pattern of one choice.
let (|identifier|) [arguments] valueToMatch= expression

// Active Pattern with multiple choices.
// Uses a FSharp.Core.Choice<_,...,_> based on the number of case names. In F#, the limitation n <= 7 applies.
let (|identifer1|identifier2|...|) valueToMatch = expression

// Partial active pattern definition.
// Uses a FSharp.Core.option<_> to represent if the type is satisfied at the call site.
let (|identifier|_|) [arguments ] valueToMatch = expression
```

## <a name="remarks"></a><span data-ttu-id="9d84a-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="9d84a-107">Remarks</span></span>

<span data-ttu-id="9d84a-108">В предыдущем синтаксисе идентификаторы представляют собой имена секций входных данных, представленных *аргументами*, или, иными словами, имена подмножеств набора всех значений аргументов.</span><span class="sxs-lookup"><span data-stu-id="9d84a-108">In the previous syntax, the identifiers are names for partitions of the input data that is represented by *arguments*, or, in other words, names for subsets of the set of all values of the arguments.</span></span> <span data-ttu-id="9d84a-109">В определении активного шаблона может быть до семи секций.</span><span class="sxs-lookup"><span data-stu-id="9d84a-109">There can be up to seven partitions in an active pattern definition.</span></span> <span data-ttu-id="9d84a-110">*Выражение* описывает форму, в которую разбиваются данные.</span><span class="sxs-lookup"><span data-stu-id="9d84a-110">The *expression* describes the form into which to decompose the data.</span></span> <span data-ttu-id="9d84a-111">Определение активного шаблона можно использовать для определения правил, определяющих, какие из именованных секций являются значениями, заданными в качестве аргументов.</span><span class="sxs-lookup"><span data-stu-id="9d84a-111">You can use an active pattern definition to define the rules for determining which of the named partitions the values given as arguments belong to.</span></span> <span data-ttu-id="9d84a-112">Символы (| и |) называются *скрепками в виде полукруглого* символа, а функция, созданная с помощью этого типа привязки let, называется *активным распознавателем*.</span><span class="sxs-lookup"><span data-stu-id="9d84a-112">The (| and |) symbols are referred to as *banana clips* and the function created by this type of let binding is called an *active recognizer*.</span></span>

<span data-ttu-id="9d84a-113">В качестве примера рассмотрим следующий активный шаблон с аргументом.</span><span class="sxs-lookup"><span data-stu-id="9d84a-113">As an example, consider the following active pattern with an argument.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

<span data-ttu-id="9d84a-114">Активный шаблон можно использовать в выражении сопоставления шаблонов, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="9d84a-114">You can use the active pattern in a pattern matching expression, as in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

<span data-ttu-id="9d84a-115">Выходные данные этой программы выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9d84a-115">The output of this program is as follows:</span></span>

```console
7 is odd
11 is odd
32 is even
```

<span data-ttu-id="9d84a-116">Другим применением активных шаблонов является разбиение типов данных несколькими способами, например, когда одни и те же базовые данные имеют различные возможные представления.</span><span class="sxs-lookup"><span data-stu-id="9d84a-116">Another use of active patterns is to decompose data types in multiple ways, such as when the same underlying data has various possible representations.</span></span> <span data-ttu-id="9d84a-117">Например, объект `Color` можно разбить на представление RGB или в представление HSB.</span><span class="sxs-lookup"><span data-stu-id="9d84a-117">For example, a `Color` object could be decomposed into an RGB representation or an HSB representation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

<span data-ttu-id="9d84a-118">Выходные данные приведенной выше программы выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9d84a-118">The output of the above program is as follows:</span></span>

```console
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

<span data-ttu-id="9d84a-119">В сочетании эти два способа использования активных шаблонов позволяют секционировать и разбивать данные на соответствующую форму и выполнять соответствующие вычисления с соответствующими данными в форме, наиболее удобной для вычислений.</span><span class="sxs-lookup"><span data-stu-id="9d84a-119">In combination, these two ways of using active patterns enable you to partition and decompose data into just the appropriate form and perform the appropriate computations on the appropriate data in the form most convenient for the computation.</span></span>

<span data-ttu-id="9d84a-120">Результирующие выражения сопоставления шаблонов позволяют написать данные удобным для чтения способом, значительно упрощая потенциально сложную ветвление и код анализа данных.</span><span class="sxs-lookup"><span data-stu-id="9d84a-120">The resulting pattern matching expressions enable data to be written in a convenient way that is very readable, greatly simplifying potentially complex branching and data analysis code.</span></span>

## <a name="partial-active-patterns"></a><span data-ttu-id="9d84a-121">Частичные активные шаблоны</span><span class="sxs-lookup"><span data-stu-id="9d84a-121">Partial Active Patterns</span></span>

<span data-ttu-id="9d84a-122">Иногда необходимо секционировать только часть входного пространства.</span><span class="sxs-lookup"><span data-stu-id="9d84a-122">Sometimes, you need to partition only part of the input space.</span></span> <span data-ttu-id="9d84a-123">В этом случае вы пишете набор частичных шаблонов, каждый из которых соответствует некоторым входным данным, но не соответствует другим входным данным.</span><span class="sxs-lookup"><span data-stu-id="9d84a-123">In that case, you write a set of partial patterns each of which match some inputs but fail to match other inputs.</span></span> <span data-ttu-id="9d84a-124">Активные шаблоны, которые не всегда создают значение, называются *частичными активными шаблонами*; они имеют возвращаемое значение, которое является типом параметра.</span><span class="sxs-lookup"><span data-stu-id="9d84a-124">Active patterns that do not always produce a value are called *partial active patterns*; they have a return value that is an option type.</span></span> <span data-ttu-id="9d84a-125">Чтобы определить частичный активный шаблон, используйте подстановочный знак (\_) в конце списка шаблонов в неменяющих роликах.</span><span class="sxs-lookup"><span data-stu-id="9d84a-125">To define a partial active pattern, you use a wildcard character (\_) at the end of the list of patterns inside the banana clips.</span></span> <span data-ttu-id="9d84a-126">Следующий код иллюстрирует использование частично активного шаблона.</span><span class="sxs-lookup"><span data-stu-id="9d84a-126">The following code illustrates the use of a partial active pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

<span data-ttu-id="9d84a-127">Выходные данные предыдущего примера выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9d84a-127">The output of the previous example is as follows:</span></span>

```console
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

<span data-ttu-id="9d84a-128">При использовании частичных активных шаблонов иногда отдельные варианты могут быть несоединенными или взаимоисключающими, но они не должны быть.</span><span class="sxs-lookup"><span data-stu-id="9d84a-128">When using partial active patterns, sometimes the individual choices can be disjoint or mutually exclusive, but they need not be.</span></span> <span data-ttu-id="9d84a-129">В следующем примере прямоугольный квадрат и куб шаблона не являются несвязанными, так как некоторые числа представляют собой квадраты и Кубы, например 64.</span><span class="sxs-lookup"><span data-stu-id="9d84a-129">In the following example, the pattern Square and the pattern Cube are not disjoint, because some numbers are both squares and cubes, such as 64.</span></span> <span data-ttu-id="9d84a-130">Следующая программа использует шаблон и для объединения квадратных и шаблонных шаблонов Куба.</span><span class="sxs-lookup"><span data-stu-id="9d84a-130">The following program uses the AND pattern to combine the Square and Cube patterns.</span></span> <span data-ttu-id="9d84a-131">Он выводит все целые числа до 1000, которые являются квадратами и кубами, а также только Кубы.</span><span class="sxs-lookup"><span data-stu-id="9d84a-131">It print out all integers up to 1000 that are both squares and cubes, as well as those which are only cubes.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

<span data-ttu-id="9d84a-132">Выходные данные выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9d84a-132">The output is as follows:</span></span>

```console
1 is a cube and a square
8 is a cube
27 is a cube
64 is a cube and a square
125 is a cube
216 is a cube
343 is a cube
512 is a cube
729 is a cube and a square
1000 is a cube
```

## <a name="parameterized-active-patterns"></a><span data-ttu-id="9d84a-133">Параметризованные активные шаблоны</span><span class="sxs-lookup"><span data-stu-id="9d84a-133">Parameterized Active Patterns</span></span>

<span data-ttu-id="9d84a-134">Активные шаблоны всегда принимают по крайней мере один аргумент для сопоставляемого элемента, но они могут также принимать дополнительные аргументы, в этом случае применяется к *параметризованному активному шаблону* Name.</span><span class="sxs-lookup"><span data-stu-id="9d84a-134">Active patterns always take at least one argument for the item being matched, but they may take additional arguments as well, in which case the name *parameterized active pattern* applies.</span></span> <span data-ttu-id="9d84a-135">Дополнительные аргументы позволяют специализированные шаблоны.</span><span class="sxs-lookup"><span data-stu-id="9d84a-135">Additional arguments allow a general pattern to be specialized.</span></span> <span data-ttu-id="9d84a-136">Например, активные шаблоны, использующие регулярные выражения для анализа строк, часто содержат регулярное выражение в качестве дополнительного параметра, как в следующем коде, который также использует частичный активный шаблон `Integer`, определенный в предыдущем примере кода.</span><span class="sxs-lookup"><span data-stu-id="9d84a-136">For example, active patterns that use regular expressions to parse strings often include the regular expression as an extra parameter, as in the following code, which also uses the partial active pattern `Integer` defined in the previous code example.</span></span> <span data-ttu-id="9d84a-137">В этом примере строки, в которых используются регулярные выражения для различных форматов даты, предоставляются для настройки общего Парсережекс активного шаблона.</span><span class="sxs-lookup"><span data-stu-id="9d84a-137">In this example, strings that use regular expressions for various date formats are given to customize the general ParseRegex active pattern.</span></span> <span data-ttu-id="9d84a-138">Целочисленный активный шаблон используется для преобразования совпадающих строк в целые числа, которые могут быть переданы конструктору DateTime.</span><span class="sxs-lookup"><span data-stu-id="9d84a-138">The Integer active pattern is used to convert the matched strings into integers that can be passed to the DateTime constructor.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

<span data-ttu-id="9d84a-139">Выходные данные предыдущего кода выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9d84a-139">The output of the previous code is as follows:</span></span>

```console
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

<span data-ttu-id="9d84a-140">Активные шаблоны не ограничиваются только выражениями, соответствующими шаблонам, их также можно использовать в привязке let.</span><span class="sxs-lookup"><span data-stu-id="9d84a-140">Active patterns are not restricted only to pattern matching expressions, you can also use them on let-bindings.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

<span data-ttu-id="9d84a-141">Выходные данные предыдущего кода выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9d84a-141">The output of the previous code is as follows:</span></span>

```console
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a><span data-ttu-id="9d84a-142">См. также</span><span class="sxs-lookup"><span data-stu-id="9d84a-142">See also</span></span>

- [<span data-ttu-id="9d84a-143">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="9d84a-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="9d84a-144">Выражения match</span><span class="sxs-lookup"><span data-stu-id="9d84a-144">Match Expressions</span></span>](match-expressions.md)
