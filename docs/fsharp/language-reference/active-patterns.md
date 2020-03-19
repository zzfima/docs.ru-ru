---
title: Активные шаблоны
description: Узнайте, как использовать активные шаблоны для определения названных разделов, которые делят входные данные на языке программирования F.
ms.date: 05/16/2016
ms.openlocfilehash: 898ef201369683bfd49d53e863e86f919f5837fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187058"
---
# <a name="active-patterns"></a><span data-ttu-id="82535-103">Активные шаблоны</span><span class="sxs-lookup"><span data-stu-id="82535-103">Active Patterns</span></span>

<span data-ttu-id="82535-104">*Активные шаблоны* позволяют определить названные разделы, которые делят входные данные, так что вы можете использовать эти имена в выражении, соответствующем шаблону так же, как для дискриминируемого соединения.</span><span class="sxs-lookup"><span data-stu-id="82535-104">*Active patterns* enable you to define named partitions that subdivide input data, so that you can use these names in a pattern matching expression just as you would for a discriminated union.</span></span> <span data-ttu-id="82535-105">Активные шаблоны можно использовать для разложения данных в настраиваемом порядке для каждого раздела.</span><span class="sxs-lookup"><span data-stu-id="82535-105">You can use active patterns to decompose data in a customized manner for each partition.</span></span>

## <a name="syntax"></a><span data-ttu-id="82535-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82535-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="82535-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="82535-107">Remarks</span></span>

<span data-ttu-id="82535-108">В предыдущем синтаксисе идентификаторы представляют собой имена для разделов входных данных, представленных *аргументами,* или, другими словами, для подмножества всех значений аргументов.</span><span class="sxs-lookup"><span data-stu-id="82535-108">In the previous syntax, the identifiers are names for partitions of the input data that is represented by *arguments*, or, in other words, names for subsets of the set of all values of the arguments.</span></span> <span data-ttu-id="82535-109">В активном определении шаблона может быть до семи разделов.</span><span class="sxs-lookup"><span data-stu-id="82535-109">There can be up to seven partitions in an active pattern definition.</span></span> <span data-ttu-id="82535-110">*Выражение* описывает форму, в которую следует разложить данные.</span><span class="sxs-lookup"><span data-stu-id="82535-110">The *expression* describes the form into which to decompose the data.</span></span> <span data-ttu-id="82535-111">Можно использовать определение активного шаблона для определения правил определения того, к какому из названных разделов принадлежат значения, приведенные в качестве аргументов.</span><span class="sxs-lookup"><span data-stu-id="82535-111">You can use an active pattern definition to define the rules for determining which of the named partitions the values given as arguments belong to.</span></span> <span data-ttu-id="82535-112">Символы (к) и символы называются *банановые клипы* и функция, созданная этим типом пусть связывания называется *активным распознавающим*.</span><span class="sxs-lookup"><span data-stu-id="82535-112">The (| and |) symbols are referred to as *banana clips* and the function created by this type of let binding is called an *active recognizer*.</span></span>

<span data-ttu-id="82535-113">В качестве примера рассмотрим следующий активный шаблон с аргументом.</span><span class="sxs-lookup"><span data-stu-id="82535-113">As an example, consider the following active pattern with an argument.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

<span data-ttu-id="82535-114">Активный шаблон можно использовать в выражении, соответствующем шаблону, как в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="82535-114">You can use the active pattern in a pattern matching expression, as in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

<span data-ttu-id="82535-115">Выход этой программы заключается в следующем:</span><span class="sxs-lookup"><span data-stu-id="82535-115">The output of this program is as follows:</span></span>

```console
7 is odd
11 is odd
32 is even
```

<span data-ttu-id="82535-116">Другим использованием активных шаблонов является разложение типов данных несколькими способами, например, когда одни и те же базовые данные имеют различные возможные представления.</span><span class="sxs-lookup"><span data-stu-id="82535-116">Another use of active patterns is to decompose data types in multiple ways, such as when the same underlying data has various possible representations.</span></span> <span data-ttu-id="82535-117">Например, `Color` объект может быть разложен на rGB-представление или представление HSB.</span><span class="sxs-lookup"><span data-stu-id="82535-117">For example, a `Color` object could be decomposed into an RGB representation or an HSB representation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

<span data-ttu-id="82535-118">Выход вышеупомянутой программы заключается в следующем:</span><span class="sxs-lookup"><span data-stu-id="82535-118">The output of the above program is as follows:</span></span>

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

<span data-ttu-id="82535-119">В сочетании эти два способа использования активных шаблонов позволяют разделить и разложить данные в соответствующую форму и выполнить соответствующие вычисления на соответствующие данные в форме, наиболее удобной для вычислений.</span><span class="sxs-lookup"><span data-stu-id="82535-119">In combination, these two ways of using active patterns enable you to partition and decompose data into just the appropriate form and perform the appropriate computations on the appropriate data in the form most convenient for the computation.</span></span>

<span data-ttu-id="82535-120">Полученные выражения сопоставления шаблонов позволяют писать данные очень читаемым способом, значительно упрощая потенциально сложное ветвление и код анализа данных.</span><span class="sxs-lookup"><span data-stu-id="82535-120">The resulting pattern matching expressions enable data to be written in a convenient way that is very readable, greatly simplifying potentially complex branching and data analysis code.</span></span>

## <a name="partial-active-patterns"></a><span data-ttu-id="82535-121">Частичные активные шаблоны</span><span class="sxs-lookup"><span data-stu-id="82535-121">Partial Active Patterns</span></span>

<span data-ttu-id="82535-122">Иногда необходимо перегородка только части входной площади.</span><span class="sxs-lookup"><span data-stu-id="82535-122">Sometimes, you need to partition only part of the input space.</span></span> <span data-ttu-id="82535-123">В этом случае вы пишете набор частичных шаблонов, каждый из которых соответствует некоторым входным данным, но не соответствует другим входным данным.</span><span class="sxs-lookup"><span data-stu-id="82535-123">In that case, you write a set of partial patterns each of which match some inputs but fail to match other inputs.</span></span> <span data-ttu-id="82535-124">Активные шаблоны, которые не всегда производят значение, называются *частичными активными шаблонами;* они имеют значение возврата, которое является типом опциона.</span><span class="sxs-lookup"><span data-stu-id="82535-124">Active patterns that do not always produce a value are called *partial active patterns*; they have a return value that is an option type.</span></span> <span data-ttu-id="82535-125">Чтобы определить частичный активный шаблон, вы\_используете символ подстановочного знака () в конце списка шаблонов внутри банановых клипов.</span><span class="sxs-lookup"><span data-stu-id="82535-125">To define a partial active pattern, you use a wildcard character (\_) at the end of the list of patterns inside the banana clips.</span></span> <span data-ttu-id="82535-126">Следующий код иллюстрирует использование частичного активного шаблона.</span><span class="sxs-lookup"><span data-stu-id="82535-126">The following code illustrates the use of a partial active pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

<span data-ttu-id="82535-127">Выход предыдущего примера заключается в следующем:</span><span class="sxs-lookup"><span data-stu-id="82535-127">The output of the previous example is as follows:</span></span>

```console
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

<span data-ttu-id="82535-128">При использовании частичных активных шаблонов, иногда индивидуальный выбор может быть разрозненным или взаимоисключающим, но они не должны быть.</span><span class="sxs-lookup"><span data-stu-id="82535-128">When using partial active patterns, sometimes the individual choices can be disjoint or mutually exclusive, but they need not be.</span></span> <span data-ttu-id="82535-129">В следующем примере квадрат шаблона и куб шаблон не разрознены, поскольку некоторые числа являются как квадратами, так и кубиками, например 64.</span><span class="sxs-lookup"><span data-stu-id="82535-129">In the following example, the pattern Square and the pattern Cube are not disjoint, because some numbers are both squares and cubes, such as 64.</span></span> <span data-ttu-id="82535-130">Следующая программа использует шаблон AND для объединения шаблонов Square и Cube.</span><span class="sxs-lookup"><span data-stu-id="82535-130">The following program uses the AND pattern to combine the Square and Cube patterns.</span></span> <span data-ttu-id="82535-131">Он печатает все целые столбы до 1000, которые являются как квадраты и кубики, а также те, которые являются только кубиками.</span><span class="sxs-lookup"><span data-stu-id="82535-131">It prints out all integers up to 1000 that are both squares and cubes, as well as those which are only cubes.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

<span data-ttu-id="82535-132">Вывод выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="82535-132">The output is as follows:</span></span>

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

## <a name="parameterized-active-patterns"></a><span data-ttu-id="82535-133">Параметризированные активные шаблоны</span><span class="sxs-lookup"><span data-stu-id="82535-133">Parameterized Active Patterns</span></span>

<span data-ttu-id="82535-134">Активные шаблоны всегда принимают по крайней мере один аргумент для соответствия элемента, но они могут принимать дополнительные аргументы, и в этом случае имя *параметризированный активный шаблон* применяется.</span><span class="sxs-lookup"><span data-stu-id="82535-134">Active patterns always take at least one argument for the item being matched, but they may take additional arguments as well, in which case the name *parameterized active pattern* applies.</span></span> <span data-ttu-id="82535-135">Дополнительные аргументы позволяют специализироваться на общей схеме.</span><span class="sxs-lookup"><span data-stu-id="82535-135">Additional arguments allow a general pattern to be specialized.</span></span> <span data-ttu-id="82535-136">Например, активные шаблоны, которые используют регулярные выражения для разбора строк, часто включают регулярное выражение в качестве `Integer` дополнительного параметра, как в следующем коде, который также использует частичный активный шаблон, определенный в предыдущем примере кода.</span><span class="sxs-lookup"><span data-stu-id="82535-136">For example, active patterns that use regular expressions to parse strings often include the regular expression as an extra parameter, as in the following code, which also uses the partial active pattern `Integer` defined in the previous code example.</span></span> <span data-ttu-id="82535-137">В этом примере для настройки общего активного шаблона ParseRegex приводятся строки, в которых используются регулярные выражения для различных форматов дат.</span><span class="sxs-lookup"><span data-stu-id="82535-137">In this example, strings that use regular expressions for various date formats are given to customize the general ParseRegex active pattern.</span></span> <span data-ttu-id="82535-138">Активный шаблон Integer используется для преобразования сытых строк в ряды, которые могут быть переданы конструктору DateTime.</span><span class="sxs-lookup"><span data-stu-id="82535-138">The Integer active pattern is used to convert the matched strings into integers that can be passed to the DateTime constructor.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

<span data-ttu-id="82535-139">Выход предыдущего кода:</span><span class="sxs-lookup"><span data-stu-id="82535-139">The output of the previous code is as follows:</span></span>

```console
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

<span data-ttu-id="82535-140">Активные шаблоны не ограничиваются только шаблоном, сопрягающими выражения, их можно использовать и в привязки.</span><span class="sxs-lookup"><span data-stu-id="82535-140">Active patterns are not restricted only to pattern matching expressions, you can also use them on let-bindings.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

<span data-ttu-id="82535-141">Выход предыдущего кода:</span><span class="sxs-lookup"><span data-stu-id="82535-141">The output of the previous code is as follows:</span></span>

```console
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a><span data-ttu-id="82535-142">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="82535-142">See also</span></span>

- [<span data-ttu-id="82535-143">Ссылка на язык F</span><span class="sxs-lookup"><span data-stu-id="82535-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="82535-144">Выражения match</span><span class="sxs-lookup"><span data-stu-id="82535-144">Match Expressions</span></span>](match-expressions.md)
