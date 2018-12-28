---
title: F#рекомендации по форматированию кода
description: Дополнительные сведения, касающиеся форматирования F# кода.
ms.date: 11/26/2018
ms.openlocfilehash: e8e0af2ebffd0e2f3720896bf710961afa11e7bd
ms.sourcegitcommit: 49af435bfdd41faf26d38c20c5b0cc07e87bea60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53396829"
---
# <a name="f-code-formatting-guidelines"></a><span data-ttu-id="c3c10-103">F#рекомендации по форматированию кода</span><span class="sxs-lookup"><span data-stu-id="c3c10-103">F# code formatting guidelines</span></span>

<span data-ttu-id="c3c10-104">В этой статье приведены инструкции по форматированию кода, чтобы ваши F# код:</span><span class="sxs-lookup"><span data-stu-id="c3c10-104">This article offers guidelines for how to format your code so that your F# code is:</span></span>

* <span data-ttu-id="c3c10-105">Обычно рассматривать как более читаемым</span><span class="sxs-lookup"><span data-stu-id="c3c10-105">Generally viewed as more legible</span></span>
* <span data-ttu-id="c3c10-106">— В соответствии с соглашениями об примененное форматирование средства в Visual Studio и другие редакторы</span><span class="sxs-lookup"><span data-stu-id="c3c10-106">Is in accordance with conventions applied by formatting tools in Visual Studio and other editors</span></span>
* <span data-ttu-id="c3c10-107">Аналогично другим кодом по сети</span><span class="sxs-lookup"><span data-stu-id="c3c10-107">Similar to other code online</span></span>

<span data-ttu-id="c3c10-108">Эти рекомендации основаны на [полное руководство по F# соглашения о форматировании](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) по [Anh-Данг Фан](https://github.com/dungpa).</span><span class="sxs-lookup"><span data-stu-id="c3c10-108">These guidelines are based on [A comprehensive guide to F# Formatting Conventions](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) by [Anh-Dung Phan](https://github.com/dungpa).</span></span>

## <a name="general-rules-for-indentation"></a><span data-ttu-id="c3c10-109">Общие правила для отступа</span><span class="sxs-lookup"><span data-stu-id="c3c10-109">General rules for indentation</span></span>

<span data-ttu-id="c3c10-110">F#по умолчанию используется значащим пробелом.</span><span class="sxs-lookup"><span data-stu-id="c3c10-110">F# uses significant white space by default.</span></span> <span data-ttu-id="c3c10-111">Следующие рекомендации предназначены для предоставления рекомендации о том, как корпоративные некоторые проблемы, это может создать.</span><span class="sxs-lookup"><span data-stu-id="c3c10-111">The following guidelines are intended to provide guidance as to how to juggle some challenges this can impose.</span></span>

### <a name="using-spaces"></a><span data-ttu-id="c3c10-112">С помощью пробелов</span><span class="sxs-lookup"><span data-stu-id="c3c10-112">Using spaces</span></span>

<span data-ttu-id="c3c10-113">Если требуется отступ, необходимо использовать не знаки табуляции.</span><span class="sxs-lookup"><span data-stu-id="c3c10-113">When indentation is required, you must use spaces, not tabs.</span></span> <span data-ttu-id="c3c10-114">Необходим по крайней мере один пробел.</span><span class="sxs-lookup"><span data-stu-id="c3c10-114">At least one space is required.</span></span> <span data-ttu-id="c3c10-115">Организации могут создавать стандарты кодирования, чтобы указать число пробелов, используемых для отступов; двух, трех или четырех пробелов отступа на каждом уровне, где происходит отступа является типичным.</span><span class="sxs-lookup"><span data-stu-id="c3c10-115">Your organization can create coding standards to specify the number of spaces to use for indentation; two, three or four spaces of indentation at each level where indentation occurs is typical.</span></span>

<span data-ttu-id="c3c10-116">**Мы рекомендуем 4 пробелов для отступа.**</span><span class="sxs-lookup"><span data-stu-id="c3c10-116">**We recommend 4 spaces per indentation.**</span></span>

<span data-ttu-id="c3c10-117">С другой стороны, отступы программ сводится к субъективным.</span><span class="sxs-lookup"><span data-stu-id="c3c10-117">That said, indentation of programs is a subjective matter.</span></span> <span data-ttu-id="c3c10-118">Варианты ОК, но первое правило, необходимо следовать *согласованности отступа*.</span><span class="sxs-lookup"><span data-stu-id="c3c10-118">Variations are OK, but the first rule you should follow is *consistency of indentation*.</span></span> <span data-ttu-id="c3c10-119">Выберите широко распространенный стиль отступов и используйте его систематически во всей базе кода.</span><span class="sxs-lookup"><span data-stu-id="c3c10-119">Choose a generally accepted style of indentation and use it systematically throughout your codebase.</span></span>

## <a name="formatting-white-space"></a><span data-ttu-id="c3c10-120">Форматирование пустое пространство</span><span class="sxs-lookup"><span data-stu-id="c3c10-120">Formatting white space</span></span>

<span data-ttu-id="c3c10-121">F#чувствителен ли пустое пространство.</span><span class="sxs-lookup"><span data-stu-id="c3c10-121">F# is white space sensitive.</span></span> <span data-ttu-id="c3c10-122">Несмотря на то, что большинство семантику из пробелов, охватываются правильного отступа, существуют некоторые вещи, которые следует учитывать.</span><span class="sxs-lookup"><span data-stu-id="c3c10-122">Although most semantics from white space are covered by proper indentation, there are some other things to consider.</span></span>

### <a name="formatting-operators-in-arithmetic-expressions"></a><span data-ttu-id="c3c10-123">Форматирование операторов в арифметических выражениях</span><span class="sxs-lookup"><span data-stu-id="c3c10-123">Formatting operators in arithmetic expressions</span></span>

<span data-ttu-id="c3c10-124">Всегда используйте пробелы вокруг двоичные арифметические выражения:</span><span class="sxs-lookup"><span data-stu-id="c3c10-124">Always use white space around binary arithmetic expressions:</span></span>

```fsharp
let subtractThenAdd x = x - 1 + 3
```

<span data-ttu-id="c3c10-125">Унарный `-` операторы всегда должны иметь значения, они Инверсия следовать сразу за:</span><span class="sxs-lookup"><span data-stu-id="c3c10-125">Unary `-` operators should always have the value they are negating immediately follow:</span></span>

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

<span data-ttu-id="c3c10-126">Добавление пробела после `-` оператор может привести к путанице для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="c3c10-126">Adding a white-space character after the `-` operator can lead to confusion for others.</span></span>

<span data-ttu-id="c3c10-127">Таким образом важно всегда:</span><span class="sxs-lookup"><span data-stu-id="c3c10-127">In summary, it's important to always:</span></span>

* <span data-ttu-id="c3c10-128">Вокруг бинарных операторов с пробела</span><span class="sxs-lookup"><span data-stu-id="c3c10-128">Surround binary operators with white space</span></span>
* <span data-ttu-id="c3c10-129">Никогда не имеют конечный пробел после унарного оператора</span><span class="sxs-lookup"><span data-stu-id="c3c10-129">Never have trailing white space after a unary operator</span></span>

<span data-ttu-id="c3c10-130">Ориентировочная бинарный оператор арифметического особенно важна.</span><span class="sxs-lookup"><span data-stu-id="c3c10-130">The binary arithmetic operator guideline is especially important.</span></span> <span data-ttu-id="c3c10-131">Сбой вокруг двоичный файл `-` оператора, где сочетаются разные варианты форматирования может привести к его интерпретировать как унарный `-`.</span><span class="sxs-lookup"><span data-stu-id="c3c10-131">Failing to surround a binary `-` operator, when combined with certain formatting choices, could lead to interpreting it as a unary `-`.</span></span>

### <a name="surround-a-custom-operator-definition-with-white-space"></a><span data-ttu-id="c3c10-132">Определение пользовательского оператора с пустого пространства вокруг</span><span class="sxs-lookup"><span data-stu-id="c3c10-132">Surround a custom operator definition with white space</span></span>

<span data-ttu-id="c3c10-133">Всегда используете пробелы вокруг определение оператора:</span><span class="sxs-lookup"><span data-stu-id="c3c10-133">Always use white space to surround an operator definition:</span></span>

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

<span data-ttu-id="c3c10-134">Для любого пользовательского оператора, который начинается с `*`, вам потребуется добавить пробел в начале определения, чтобы избежать неоднозначности компилятора.</span><span class="sxs-lookup"><span data-stu-id="c3c10-134">For any custom operator that starts with `*`, you'll need to add a white space to the beginning of the definition to avoid a compiler ambiguity.</span></span> <span data-ttu-id="c3c10-135">По этой причине рекомендуется просто заключите определения всех операторов в виде одного символа пробела.</span><span class="sxs-lookup"><span data-stu-id="c3c10-135">Because of this, it's recommended that you simply surround the definitions of all operators with a single white-space character.</span></span>

### <a name="surround-function-parameter-arrows-with-white-space"></a><span data-ttu-id="c3c10-136">Заключите стрелки параметра функции с пробела</span><span class="sxs-lookup"><span data-stu-id="c3c10-136">Surround function parameter arrows with white space</span></span>

<span data-ttu-id="c3c10-137">При определении Сигнатура функции, используйте пустое пространство вокруг `->` символа:</span><span class="sxs-lookup"><span data-stu-id="c3c10-137">When defining the signature of a function, use white space around the `->` symbol:</span></span>

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

## <a name="formatting-blank-lines"></a><span data-ttu-id="c3c10-138">Форматирование пустых строк</span><span class="sxs-lookup"><span data-stu-id="c3c10-138">Formatting blank lines</span></span>

* <span data-ttu-id="c3c10-139">Отдельные верхнего уровня функций и классов определения двух пустыми строками.</span><span class="sxs-lookup"><span data-stu-id="c3c10-139">Separate top-level function and class definitions with two blank lines.</span></span>
* <span data-ttu-id="c3c10-140">Определения методов внутри класса разделяются одна пустая строка.</span><span class="sxs-lookup"><span data-stu-id="c3c10-140">Method definitions inside a class are separated by a single blank line.</span></span>
* <span data-ttu-id="c3c10-141">Лишних пустых строк может использоваться для разделения групп связанных функций (только в случае необходимости).</span><span class="sxs-lookup"><span data-stu-id="c3c10-141">Extra blank lines may be used (sparingly) to separate groups of related functions.</span></span> <span data-ttu-id="c3c10-142">Можно опустить пустые строки между ряд связанных командных строк (например, набор заглушки).</span><span class="sxs-lookup"><span data-stu-id="c3c10-142">Blank lines may be omitted between a bunch of related one-liners (for example, a set of dummy implementations).</span></span>
* <span data-ttu-id="c3c10-143">Используйте пустые строки в функции, только в случае необходимости, чтобы указать логические разделы.</span><span class="sxs-lookup"><span data-stu-id="c3c10-143">Use blank lines in functions, sparingly, to indicate logical sections.</span></span>

## <a name="formatting-comments"></a><span data-ttu-id="c3c10-144">Форматирование комментарии</span><span class="sxs-lookup"><span data-stu-id="c3c10-144">Formatting comments</span></span>

<span data-ttu-id="c3c10-145">Обычно предпочтение комментарии блок в стиле ML несколько комментариев двойной косой чертой.</span><span class="sxs-lookup"><span data-stu-id="c3c10-145">Generally prefer multiple double-slash comments over ML-style block comments.</span></span>

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

<span data-ttu-id="c3c10-146">Встроенные комментарии должны преобразование первой буквы.</span><span class="sxs-lookup"><span data-stu-id="c3c10-146">Inline comments should capitalize the first letter.</span></span>

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a><span data-ttu-id="c3c10-147">Соглашения об именах</span><span class="sxs-lookup"><span data-stu-id="c3c10-147">Naming conventions</span></span>

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a><span data-ttu-id="c3c10-148">Использующие camelCase для класса, привязанного к выражению с связыванием и шаблон значения и функции</span><span class="sxs-lookup"><span data-stu-id="c3c10-148">Use camelCase for class-bound, expression-bound and pattern-bound values and functions</span></span>

<span data-ttu-id="c3c10-149">Распространенный и принятых F# стиль, используемый camelCase, для всех имен привязан как локальные переменные или в соответствие шаблону и функцию, определения.</span><span class="sxs-lookup"><span data-stu-id="c3c10-149">It is common and accepted F# style to use camelCase for all names bound as local variables or in pattern matches and function definitions.</span></span>

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

<span data-ttu-id="c3c10-150">Локально функций в классах, также следует использовать camelCase.</span><span class="sxs-lookup"><span data-stu-id="c3c10-150">Locally-bound functions in classes should also use camelCase.</span></span>

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a><span data-ttu-id="c3c10-151">Использующие camelCase для связанного с модулем открытых функций</span><span class="sxs-lookup"><span data-stu-id="c3c10-151">Use camelCase for module-bound public functions</span></span>

<span data-ttu-id="c3c10-152">Когда связанного с модулем функции является частью открытого API, его следует использовать camelCase.</span><span class="sxs-lookup"><span data-stu-id="c3c10-152">When a module-bound function is part of a public API, it should use camelCase:</span></span>

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a><span data-ttu-id="c3c10-153">Использующие camelCase для внутреннего использования и частных значения связанного с модулем и функции</span><span class="sxs-lookup"><span data-stu-id="c3c10-153">Use camelCase for internal and private module-bound values and functions</span></span>

<span data-ttu-id="c3c10-154">Использования camelCase закрытый значений связанного с модулем, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="c3c10-154">Use camelCase for private module-bound values, including the following:</span></span>

* <span data-ttu-id="c3c10-155">Нерегламентированные функции в скриптах</span><span class="sxs-lookup"><span data-stu-id="c3c10-155">Ad hoc functions in scripts</span></span>

* <span data-ttu-id="c3c10-156">Значения, входящим в состав внутренняя реализация модуля или тип</span><span class="sxs-lookup"><span data-stu-id="c3c10-156">Values making up the internal implementation of a module or type</span></span>

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a><span data-ttu-id="c3c10-157">Использующие camelCase для параметров</span><span class="sxs-lookup"><span data-stu-id="c3c10-157">Use camelCase for parameters</span></span>

<span data-ttu-id="c3c10-158">Все параметры следует использовать camelCase в соответствии с соглашениями об именовании .NET.</span><span class="sxs-lookup"><span data-stu-id="c3c10-158">All parameters should use camelCase in accordance with .NET naming conventions.</span></span>

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a><span data-ttu-id="c3c10-159">Используйте PascalCase для модулей</span><span class="sxs-lookup"><span data-stu-id="c3c10-159">Use PascalCase for modules</span></span>

<span data-ttu-id="c3c10-160">Все модули (верхнего уровня, внутренний, закрытый, вложенные) следует использовать PascalCase.</span><span class="sxs-lookup"><span data-stu-id="c3c10-160">All modules (top-level, internal, private, nested) should use PascalCase.</span></span>

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a><span data-ttu-id="c3c10-161">Использующие PascalCase для объявления типов, членов и меток</span><span class="sxs-lookup"><span data-stu-id="c3c10-161">Use PascalCase for type declarations, members, and labels</span></span>

<span data-ttu-id="c3c10-162">Классы, интерфейсы, структуры, перечисления, делегаты, записи и размеченные объединения должны иметь имя с PascalCase.</span><span class="sxs-lookup"><span data-stu-id="c3c10-162">Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase.</span></span> <span data-ttu-id="c3c10-163">Элементы типов и метки для записи и размеченные объединения также следует использовать PascalCase.</span><span class="sxs-lookup"><span data-stu-id="c3c10-163">Members within types and labels for records and discriminated unions should also use PascalCase.</span></span>

```fsharp
type IMyInterface =
    abstract Something: int

type MyClass() =
    member this.MyMethod(x, y) = x + y

type MyRecord = { IntVal: int; StringVal: string }

type SchoolPerson =
    | Professor
    | Student
    | Advisor
    | Administrator
```

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a><span data-ttu-id="c3c10-164">Использующие PascalCase для конструкций, встроенными в .NET</span><span class="sxs-lookup"><span data-stu-id="c3c10-164">Use PascalCase for constructs intrinsic to .NET</span></span>

<span data-ttu-id="c3c10-165">Пространства имен, исключения, события и проект /`.dll` имена также следует использовать PascalCase.</span><span class="sxs-lookup"><span data-stu-id="c3c10-165">Namespaces, exceptions, events, and project/`.dll` names should also use PascalCase.</span></span> <span data-ttu-id="c3c10-166">Не только делает ли это потребление из других языков .NET, в целом более привычны для потребителей, он также был совместим с .NET соглашения об именовании, которые могут возникнуть.</span><span class="sxs-lookup"><span data-stu-id="c3c10-166">Not only does this make consumption from other .NET languages feel more natural to consumers, it's also consistent with .NET naming conventions that you are likely to encounter.</span></span>

### <a name="avoid-underscores-in-names"></a><span data-ttu-id="c3c10-167">Избежать символов подчеркивания в именах</span><span class="sxs-lookup"><span data-stu-id="c3c10-167">Avoid underscores in names</span></span>

<span data-ttu-id="c3c10-168">Исторически сложилось так, что некоторые F# библиотеки использовали символы подчеркивания в именах.</span><span class="sxs-lookup"><span data-stu-id="c3c10-168">Historically, some F# libraries have used underscores in names.</span></span> <span data-ttu-id="c3c10-169">Тем не менее принимается больше не широко, отчасти потому, что он противоречит соглашения об именовании .NET.</span><span class="sxs-lookup"><span data-stu-id="c3c10-169">However, this is no longer widely accepted, partly because it clashes with .NET naming conventions.</span></span> <span data-ttu-id="c3c10-170">С другой стороны, некоторые F# программисты используют символы подчеркивания во многом, отчасти по историческим причинам, и важно допуска и уважение.</span><span class="sxs-lookup"><span data-stu-id="c3c10-170">That said, some F# programmers use underscores heavily, partly for historical reasons, and tolerance and respect is important.</span></span> <span data-ttu-id="c3c10-171">Однако имейте в виду, что стиль часто нравилось с другими пользователями, существует выбор, следует ли использовать его.</span><span class="sxs-lookup"><span data-stu-id="c3c10-171">However, be aware that the style is often disliked by others who have a choice about whether to use it.</span></span>

<span data-ttu-id="c3c10-172">Некоторые исключения включает в себя взаимодействие с компонентами в машинном коде, где очень распространены символы подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="c3c10-172">Some exceptions includes interoperating with native components, where underscores are very common.</span></span>

### <a name="use-standard-f-operators"></a><span data-ttu-id="c3c10-173">Используйте стандартные F# операторы</span><span class="sxs-lookup"><span data-stu-id="c3c10-173">Use standard F# operators</span></span>

<span data-ttu-id="c3c10-174">Следующие операторы определены в F# стандартной библиотеки и должны использоваться вместо определения эквиваленты.</span><span class="sxs-lookup"><span data-stu-id="c3c10-174">The following operators are defined in the F# standard library and should be used instead of defining equivalents.</span></span> <span data-ttu-id="c3c10-175">Использование этих операторов рекомендуется, так как он, как правило, чтобы сделать код более читаемым и устойчивым.</span><span class="sxs-lookup"><span data-stu-id="c3c10-175">Using these operators is recommended as it tends to make code more readable and idiomatic.</span></span> <span data-ttu-id="c3c10-176">Разработчиков, имеющих опыт в OCaml или других функциональный язык программирования, могли привыкнуть к различных выражений.</span><span class="sxs-lookup"><span data-stu-id="c3c10-176">Developers with a background in OCaml or other functional programming language may be accustomed to different idioms.</span></span> <span data-ttu-id="c3c10-177">В следующем списке перечислены рекомендуемые F# операторы.</span><span class="sxs-lookup"><span data-stu-id="c3c10-177">The following list summarizes the recommended F# operators.</span></span>

```fsharp
x |> f // Forward pipeline
f >> g // Forward composition
x |> ignore // Discard away a value
x + y // Overloaded addition (including string concatenation)
x - y // Overloaded subtraction
x * y // Overloaded multiplication
x / y // Overloaded division
x % y // Overloaded modulus
x && y // Lazy/short-cut "and"
x || y // Lazy/short-cut "or"
x <<< y // Bitwise left shift
x >>> y // Bitwise right shift
x ||| y // Bitwise or, also for working with “flags” enumeration
x &&& y // Bitwise and, also for working with “flags” enumeration
x ^^^ y // Bitwise xor, also for working with “flags” enumeration
```

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a><span data-ttu-id="c3c10-178">Используйте синтаксис префикс для универсальных типов (`Foo<T>`) предпочтение постфиксный синтаксис (`T Foo`)</span><span class="sxs-lookup"><span data-stu-id="c3c10-178">Use prefix syntax for generics (`Foo<T>`) in preference to postfix syntax (`T Foo`)</span></span>

<span data-ttu-id="c3c10-179">F#наследует стиль постфиксного ML именования универсальных типов (например, `int list`) а также префикс стиля .NET (например, `list<int>`).</span><span class="sxs-lookup"><span data-stu-id="c3c10-179">F# inherits both the postfix ML style of naming generic types (for example, `int list`) as well as the prefix .NET style (for example, `list<int>`).</span></span> <span data-ttu-id="c3c10-180">Предпочитаете в стиле .NET, за исключением четырех определенных типов:</span><span class="sxs-lookup"><span data-stu-id="c3c10-180">Prefer the .NET style, except for four specific types:</span></span>

1. <span data-ttu-id="c3c10-181">Для F# списки, используйте в постфиксной форме: `int list` вместо `list<int>`.</span><span class="sxs-lookup"><span data-stu-id="c3c10-181">For F# Lists, use the postfix form: `int list` rather than `list<int>`.</span></span>
2. <span data-ttu-id="c3c10-182">Для F# параметрах, используется в постфиксной форме: `int option` вместо `option<int>`.</span><span class="sxs-lookup"><span data-stu-id="c3c10-182">For F# Options, use the postfix form: `int option` rather than `option<int>`.</span></span>
3. <span data-ttu-id="c3c10-183">Для F# массивы, используемое имя синтаксические `int[]` вместо `int array` или `array<int>`.</span><span class="sxs-lookup"><span data-stu-id="c3c10-183">For F# arrays, use the syntactic name `int[]` rather than `int array` or `array<int>`.</span></span>
4. <span data-ttu-id="c3c10-184">Ссылочные ячейки, используйте `int ref` вместо `ref<int>` или `Ref<int>`.</span><span class="sxs-lookup"><span data-stu-id="c3c10-184">For Reference Cells, use `int ref` rather than `ref<int>` or `Ref<int>`.</span></span>

<span data-ttu-id="c3c10-185">Для всех других типов используйте форму префикс.</span><span class="sxs-lookup"><span data-stu-id="c3c10-185">For all other types, use the prefix form.</span></span>

## <a name="formatting-tuples"></a><span data-ttu-id="c3c10-186">Форматирование кортежей</span><span class="sxs-lookup"><span data-stu-id="c3c10-186">Formatting tuples</span></span>

<span data-ttu-id="c3c10-187">Создание экземпляра кортежа должно быть заключено в скобки и разделителей запятые внутри должен следовать один пробел, например: `(1, 2)`, `(x, y, z)`.</span><span class="sxs-lookup"><span data-stu-id="c3c10-187">A tuple instantiation should be parenthesized, and the delimiting commas within should be followed by a single space, for example: `(1, 2)`, `(x, y, z)`.</span></span>

<span data-ttu-id="c3c10-188">Обычно принимается опустить скобки при сопоставлении шаблонов кортежей:</span><span class="sxs-lookup"><span data-stu-id="c3c10-188">It is commonly accepted to omit parentheses in pattern matching of tuples:</span></span>

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

## <a name="formatting-discriminated-union-declarations"></a><span data-ttu-id="c3c10-189">Форматирование размеченные объявления объединений</span><span class="sxs-lookup"><span data-stu-id="c3c10-189">Formatting discriminated union declarations</span></span>

<span data-ttu-id="c3c10-190">Отступ `|` в определении типа по 4 пробела:</span><span class="sxs-lookup"><span data-stu-id="c3c10-190">Indent `|` in type definition by 4 spaces:</span></span>

```fsharp
// OK
type Volume =
    | Liter of float
    | FluidOunce of float
    | ImperialPint of float

// Not OK
type Volume =
| Liter of float
| USPint of float
| ImperialPint of float
```

## <a name="formatting-discriminated-unions"></a><span data-ttu-id="c3c10-191">Форматирование размеченные объединения</span><span class="sxs-lookup"><span data-stu-id="c3c10-191">Formatting discriminated unions</span></span>

<span data-ttu-id="c3c10-192">Созданный экземпляр размеченные объединения, которые разбиваются на несколько строк следует предоставить новую область с отступами содержащиеся данные:</span><span class="sxs-lookup"><span data-stu-id="c3c10-192">Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:</span></span>

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

<span data-ttu-id="c3c10-193">Также может быть закрывающую скобку на новой строке:</span><span class="sxs-lookup"><span data-stu-id="c3c10-193">The closing parenthesis can also be on a new line:</span></span>

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a><span data-ttu-id="c3c10-194">Форматирование запись объявления</span><span class="sxs-lookup"><span data-stu-id="c3c10-194">Formatting record declarations</span></span>

<span data-ttu-id="c3c10-195">Отступ `{` в типе определения по 4, пробелы и начать полей списка полей в той же строке:</span><span class="sxs-lookup"><span data-stu-id="c3c10-195">Indent `{` in type definition by 4 spaces and start the field list on the same line:</span></span>

```fsharp
// OK
type PostalAddress =
    { Address: string
      City: string
      Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Not OK
type PostalAddress =
  { Address: string
    City: string
    Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City
    
// Unusual in F#
type PostalAddress =
    { 
        Address: string
        City: string
        Zip: string
    }
```

<span data-ttu-id="c3c10-196">Помещение открывающей маркер на новую строку и закрытия токен в новой строке является рекомендуемое в том случае, если вы объявляете реализации интерфейса или элементы в записи:</span><span class="sxs-lookup"><span data-stu-id="c3c10-196">Placing the opening token on a new line and the closing token on a new line is preferrable if you are declaring interface implementations or members on the record:</span></span>

```fsharp
// Declaring additional members on PostalAddress
type PostalAddress =
    { 
        Address: string
        City: string
        Zip: string
    } with
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City
    
type MyRecord =
    {
        SomeField : int
    }
    interface IMyInterface
```

## <a name="formatting-records"></a><span data-ttu-id="c3c10-197">Форматирование записей</span><span class="sxs-lookup"><span data-stu-id="c3c10-197">Formatting records</span></span>

<span data-ttu-id="c3c10-198">Короткие записи могут быть написаны на одной строке:</span><span class="sxs-lookup"><span data-stu-id="c3c10-198">Short records can be written in one line:</span></span>

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

<span data-ttu-id="c3c10-199">Длинные записи следует использовать новые строки для меток:</span><span class="sxs-lookup"><span data-stu-id="c3c10-199">Records that are longer should use new lines for labels:</span></span>

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="c3c10-200">Поместив открывающий маркера в новой строке, с вкладками содержимое более чем одну область, и токен закрытия в новой строке рекомендуемое в том случае, если вы являетесь:</span><span class="sxs-lookup"><span data-stu-id="c3c10-200">Placing the opening token on a new line, the contents tabbed over one scope, and the closing token on a new line is preferrable if you are:</span></span>

* <span data-ttu-id="c3c10-201">Перемещение записей в коде с помощью отступов для разных областей</span><span class="sxs-lookup"><span data-stu-id="c3c10-201">Moving records around in code with different indentation scopes</span></span>
* <span data-ttu-id="c3c10-202">Их по конвейеру в функцию</span><span class="sxs-lookup"><span data-stu-id="c3c10-202">Piping them into a function</span></span>

```fsharp
let rainbow =
    {
        Boss1 = "Jeffrey"
        Boss2 = "Jeffrey"
        Boss3 = "Jeffrey"
        Boss4 = "Jeffrey"
        Boss5 = "Jeffrey"
        Boss6 = "Jeffrey"
        Boss7 = "Jeffrey"
        Boss8 = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"]
    }
    
type MyRecord =
    {
        SomeField : int
    }
    interface IMyInterface

let foo a =
    a
    |> Option.map (fun x ->
        {
            MyField = x
        })
```

<span data-ttu-id="c3c10-203">Те же правила применяются для элементов списка и массива.</span><span class="sxs-lookup"><span data-stu-id="c3c10-203">The same rules apply for list and array elements.</span></span>

## <a name="formatting-lists-and-arrays"></a><span data-ttu-id="c3c10-204">Форматирование, списки и массивы</span><span class="sxs-lookup"><span data-stu-id="c3c10-204">Formatting lists and arrays</span></span>

<span data-ttu-id="c3c10-205">Запись `x :: l` с пробелы вокруг `::` оператор (`::` инфиксные оператор, поэтому окружен пробелами).</span><span class="sxs-lookup"><span data-stu-id="c3c10-205">Write `x :: l` with spaces around the `::` operator (`::` is an infix operator, hence surrounded by spaces).</span></span>

<span data-ttu-id="c3c10-206">Список и массивов, объявленных в одной строке должны иметь пробел после открывающей скобки и перед закрывающей скобкой:</span><span class="sxs-lookup"><span data-stu-id="c3c10-206">List and arrays declared on a single line should have a space after the opening bracket and before the closing bracket:</span></span>

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

<span data-ttu-id="c3c10-207">Всегда используйте по крайней мере один пробел между двумя операторами distinct стиле фигурную скобку.</span><span class="sxs-lookup"><span data-stu-id="c3c10-207">Always use at least one space between two distinct brace-like operators.</span></span> <span data-ttu-id="c3c10-208">Например, оставьте пробел между `[` и `{`.</span><span class="sxs-lookup"><span data-stu-id="c3c10-208">For example, leave a space between a `[` and a `{`.</span></span>

```fsharp
// OK
[ { IngredientName = "Green beans"; Quantity = 250 }
  { IngredientName = "Pine nuts"; Quantity = 250 }
  { IngredientName = "Feta cheese"; Quantity = 250 }
  { IngredientName = "Olive oil"; Quantity = 10 }
  { IngredientName = "Lemon"; Quantity = 1 } ]

// Not OK
[{ IngredientName = "Green beans"; Quantity = 250 }
 { IngredientName = "Pine nuts"; Quantity = 250 }
 { IngredientName = "Feta cheese"; Quantity = 250 }
 { IngredientName = "Olive oil"; Quantity = 10 }
 { IngredientName = "Lemon"; Quantity = 1 }]
```

<span data-ttu-id="c3c10-209">Же правило применяется для списков или массивы кортежей.</span><span class="sxs-lookup"><span data-stu-id="c3c10-209">The same guideline applies for lists or arrays of tuples.</span></span>

<span data-ttu-id="c3c10-210">Списки и массивы, которые разбиты на несколько строк выполните аналогичные правила, как записи.</span><span class="sxs-lookup"><span data-stu-id="c3c10-210">Lists and arrays that split across multiple lines follow a similar rule as records do:</span></span>

```fsharp
let pascalsTriangle =
    [|
        [| 1 |]
        [| 1; 1 |]
        [| 1; 2; 1 |]
        [| 1; 3; 3; 1 |]
        [| 1; 4; 6; 4; 1 |]
        [| 1; 5; 10; 10; 5; 1 |]
        [| 1; 6; 15; 20; 15; 6; 1 |]
        [| 1; 7; 21; 35; 35; 21; 7; 1 |]
        [| 1; 8; 28; 56; 70; 56; 28; 8; 1 |]
    |]
```

<span data-ttu-id="c3c10-211">И с помощью записей объявление на строке открывающие и закрывающие скобки будут упрощают перемещение кода вокруг и передачи по конвейеру в функцию.</span><span class="sxs-lookup"><span data-stu-id="c3c10-211">And as with records, declaring the opening and closing brackets on their own line will make moving code around and piping into functions easier.</span></span>

## <a name="formatting-if-expressions"></a><span data-ttu-id="c3c10-212">Если форматирования выражения</span><span class="sxs-lookup"><span data-stu-id="c3c10-212">Formatting if expressions</span></span>

<span data-ttu-id="c3c10-213">Отступ элемента условные выражения зависит от размеров выражений, составляющих их.</span><span class="sxs-lookup"><span data-stu-id="c3c10-213">Indentation of conditionals depends on the sizes of the expressions that make them up.</span></span> <span data-ttu-id="c3c10-214">Если `cond`, `e1` и `e2` короткие, просто записывать их в одной строке:</span><span class="sxs-lookup"><span data-stu-id="c3c10-214">If `cond`, `e1` and `e2` are short, simply write them on one line:</span></span>

```fsharp
if cond then e1 else e2
```

<span data-ttu-id="c3c10-215">Если параметр `cond`, `e1` или `e2` больше времени, но не несколько строк:</span><span class="sxs-lookup"><span data-stu-id="c3c10-215">If either `cond`, `e1` or `e2` are longer, but not multi-line:</span></span>

```fsharp
if cond
then e1
else e2
```

<span data-ttu-id="c3c10-216">Если любое из выражений несколько строк:</span><span class="sxs-lookup"><span data-stu-id="c3c10-216">If any of the expressions are multi-line:</span></span>

```fsharp
if cond then
    e1
else
    e2
```

<span data-ttu-id="c3c10-217">Несколько условий с `elif` и `else` отображаются с отступом в той же области, что `if`:</span><span class="sxs-lookup"><span data-stu-id="c3c10-217">Multiple conditionals with `elif` and `else` are indented at the same scope as the `if`:</span></span>

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a><span data-ttu-id="c3c10-218">Шаблон сопоставления конструкции</span><span class="sxs-lookup"><span data-stu-id="c3c10-218">Pattern matching constructs</span></span>

<span data-ttu-id="c3c10-219">Используйте `|` для каждого предложения совпадения с без отступов.</span><span class="sxs-lookup"><span data-stu-id="c3c10-219">Use a `|` for each clause of a match with no indentation.</span></span> <span data-ttu-id="c3c10-220">Если выражение является коротким, можно с помощью одной строки, если каждой части выражения стоит также выполняется очень просто.</span><span class="sxs-lookup"><span data-stu-id="c3c10-220">If the expression is short, you can consider using a single line if each subexpression is also simple.</span></span>

```fsharp
// OK
match l with
| { him = x; her = "Posh" } :: tail -> x
| _ :: tail -> findDavid tail
| [] -> failwith "Couldn't find David"

// Not OK
match l with
    | { him = x; her = "Posh" } :: tail -> x
    | _ :: tail -> findDavid tail
    | [] -> failwith "Couldn't find David"
```

<span data-ttu-id="c3c10-221">Если выражение справа сопоставления стрелку шаблона слишком велико, перемещается в следующую строку, с отступом один шаг из `match` / `|`.</span><span class="sxs-lookup"><span data-stu-id="c3c10-221">If the expression on the right of the pattern matching arrow is too large, move it to the following line, indented one step from the `match`/`|`.</span></span>

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

<span data-ttu-id="c3c10-222">Сопоставления анонимных функций, начиная с шаблонов `function`, обычно не создать отступы слишком далеко.</span><span class="sxs-lookup"><span data-stu-id="c3c10-222">Pattern matching of anonymous functions, starting by `function`, should generally not indent too far.</span></span> <span data-ttu-id="c3c10-223">Например следующим образом отступов одну область очень мило:</span><span class="sxs-lookup"><span data-stu-id="c3c10-223">For example, indenting one scope as follows is fine:</span></span>

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

<span data-ttu-id="c3c10-224">Шаблоны в функциях, определяемых `let` или `let rec` должно быть с отступом 4 пробелов после начала `let`, даже если `function` используется ключевое слово:</span><span class="sxs-lookup"><span data-stu-id="c3c10-224">Pattern matching in functions defined by `let` or `let rec` should be indented 4 spaces after starting of `let`, even if `function` keyword is used:</span></span>

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

<span data-ttu-id="c3c10-225">Мы не рекомендуем выравнивание кнопки со стрелками.</span><span class="sxs-lookup"><span data-stu-id="c3c10-225">We do not recommend aligning arrows.</span></span>

## <a name="formatting-trywith-expressions"></a><span data-ttu-id="c3c10-226">Форматирования try / with выражения</span><span class="sxs-lookup"><span data-stu-id="c3c10-226">Formatting try/with expressions</span></span>

<span data-ttu-id="c3c10-227">Сопоставление шаблонов в тип исключения должен иметь отступ на том же уровне, что `with`.</span><span class="sxs-lookup"><span data-stu-id="c3c10-227">Pattern matching on the exception type should be indented at the same level as `with`.</span></span>

```fsharp
try
    if System.DateTime.Now.Second % 3 = 0 then
        raise (new System.Exception())
    else
        raise (new System.ApplicationException())
with
| :? System.ApplicationException ->
    printfn "A second that was not a multiple of 3"
| _ ->
    printfn "A second that was a multiple of 3"
```

## <a name="formatting-function-parameter-application"></a><span data-ttu-id="c3c10-228">Форматирование функции параметр приложения</span><span class="sxs-lookup"><span data-stu-id="c3c10-228">Formatting function parameter application</span></span>

<span data-ttu-id="c3c10-229">Как правило большинство функции параметр приложения выполняется в той же строке.</span><span class="sxs-lookup"><span data-stu-id="c3c10-229">In general, most function parameter application is done on the same line.</span></span>

<span data-ttu-id="c3c10-230">Если вы хотите применить параметры функции с новой строки, отступ их на одну область.</span><span class="sxs-lookup"><span data-stu-id="c3c10-230">If you wish to apply parameters to a function on a new line, indent them by one scope.</span></span>

```fsharp
// OK
sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
sprintf
     "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
let printVolumes x =
    printf "Volume in liters = %f, in us pints = %f, in imperial = %f"
        (convertVolumeToLiter x)
        (convertVolumeUSPint x)
        (convertVolumeImperialPint x)
```

<span data-ttu-id="c3c10-231">Те же правила применяются для лямбда-выражения как аргументы функции.</span><span class="sxs-lookup"><span data-stu-id="c3c10-231">The same guidelines apply for lambda expressions as function arguments.</span></span> <span data-ttu-id="c3c10-232">Если тело лямбда-выражения, текст может иметь другую строку, отступом в одну область</span><span class="sxs-lookup"><span data-stu-id="c3c10-232">If the body of a lambda expression, the body can have another line, indented by one scope</span></span>

```fsharp
let printListWithOffset a list1 =
    List.iter
        (fun elem -> printfn "%d" (a + elem))
        list1

// OK if lambda body is long enough
let printListWithOffset a list1 =
    List.iter
        (fun elem ->
            printfn "%d" (a + elem))
        list1
```

<span data-ttu-id="c3c10-233">Тем не менее если тело лямбда-выражения является более одной строки, рассмотрите возможность факторинг его в отдельную функцию вместо конструкцию многострочного применяется как один аргумент функции.</span><span class="sxs-lookup"><span data-stu-id="c3c10-233">However, if the body of a lambda expression is more than one line, consider factoring it out into a separate function rather than have a multi-line construct applied as a single argument to a function.</span></span>

### <a name="formatting-infix-operators"></a><span data-ttu-id="c3c10-234">Форматирование инфиксные операторы</span><span class="sxs-lookup"><span data-stu-id="c3c10-234">Formatting infix operators</span></span>

<span data-ttu-id="c3c10-235">Отдельные операторы пробелами.</span><span class="sxs-lookup"><span data-stu-id="c3c10-235">Separate operators by spaces.</span></span> <span data-ttu-id="c3c10-236">Очевидным исключения этого правила являются `!` и `.` операторы.</span><span class="sxs-lookup"><span data-stu-id="c3c10-236">Obvious exceptions to this rule are the `!` and `.` operators.</span></span>

<span data-ttu-id="c3c10-237">Инфиксные выражения — ОК в линейку и того же столбца:</span><span class="sxs-lookup"><span data-stu-id="c3c10-237">Infix expressions are OK to lineup on same column:</span></span>

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a><span data-ttu-id="c3c10-238">Форматирование конвейерных операторов</span><span class="sxs-lookup"><span data-stu-id="c3c10-238">Formatting pipeline operators</span></span>

<span data-ttu-id="c3c10-239">Конвейер `|>` операторы должны начать выполняться под выражения, они работают.</span><span class="sxs-lookup"><span data-stu-id="c3c10-239">Pipeline `|>` operators should go underneath the expressions they operate on.</span></span>

```fsharp
// Preferred approach
let methods2 =
    System.AppDomain.CurrentDomain.GetAssemblies()
    |> List.ofArray
    |> List.map (fun assm -> assm.GetTypes())
    |> Array.concat
    |> List.ofArray
    |> List.map (fun t -> t.GetMethods())
    |> Array.concat

// Not OK
let methods2 = System.AppDomain.CurrentDomain.GetAssemblies()
            |> List.ofArray
            |> List.map (fun assm -> assm.GetTypes())
            |> Array.concat
            |> List.ofArray
            |> List.map (fun t -> t.GetMethods())
            |> Array.concat
```

### <a name="formatting-modules"></a><span data-ttu-id="c3c10-240">Модули форматирования</span><span class="sxs-lookup"><span data-stu-id="c3c10-240">Formatting modules</span></span>

<span data-ttu-id="c3c10-241">Код в локальном модуле должен иметь отступ относительно модуля, но код в модуль верхнего уровня не должен иметь отступ.</span><span class="sxs-lookup"><span data-stu-id="c3c10-241">Code in a local module must be indented relative to the module, but code in a top-level module should not be indented.</span></span> <span data-ttu-id="c3c10-242">Элементы пространства имен нет необходимости иметь отступ.</span><span class="sxs-lookup"><span data-stu-id="c3c10-242">Namespace elements do not have to be indented.</span></span>

```fsharp
// A is a top-level module.
module A

let function1 a b = a - b * b
```

```fsharp
// A1 and A2 are local modules.
module A1 =
    let function1 a b = a*a + b*b

module A2 =
    let function2 a b = a*a - b*b
```

### <a name="formatting-object-expressions-and-interfaces"></a><span data-ttu-id="c3c10-243">Форматирование выражения объекта и интерфейсов</span><span class="sxs-lookup"><span data-stu-id="c3c10-243">Formatting object expressions and interfaces</span></span>

<span data-ttu-id="c3c10-244">Выражения объекта и интерфейсы должны быть выровнены с таким же образом `member` с отступом после 4 пробела.</span><span class="sxs-lookup"><span data-stu-id="c3c10-244">Object expressions and interfaces should be aligned in the same way with `member` being indented after 4 spaces.</span></span>

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s : String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a><span data-ttu-id="c3c10-245">Форматирование пустое пространство в выражениях</span><span class="sxs-lookup"><span data-stu-id="c3c10-245">Formatting white space in expressions</span></span>

<span data-ttu-id="c3c10-246">Избегайте лишние пробелы в F# выражения.</span><span class="sxs-lookup"><span data-stu-id="c3c10-246">Avoid extraneous white space in F# expressions.</span></span>

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

<span data-ttu-id="c3c10-247">Именованные аргументы также не должны иметь пространство вокруг `=`:</span><span class="sxs-lookup"><span data-stu-id="c3c10-247">Named arguments should also not have space surrounding the `=`:</span></span>

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-attributes"></a><span data-ttu-id="c3c10-248">Атрибуты форматирования</span><span class="sxs-lookup"><span data-stu-id="c3c10-248">Formatting attributes</span></span>

<span data-ttu-id="c3c10-249">[Атрибуты](../language-reference/attributes.md) помещаются выше конструкцию:</span><span class="sxs-lookup"><span data-stu-id="c3c10-249">[Attributes](../language-reference/attributes.md) are placed above a construct:</span></span>

```fsharp
[<SomeAttribute>]
type MyClass() = ...

[<RequireQualifiedAccess>]
module M =
    let f x = x

[<Struct>]
type MyRecord =
    { Label1: int
      Label2: string }
```

### <a name="formatting-attributes-on-parameters"></a><span data-ttu-id="c3c10-250">Атрибуты параметров форматирования</span><span class="sxs-lookup"><span data-stu-id="c3c10-250">Formatting attributes on parameters</span></span>

<span data-ttu-id="c3c10-251">Атрибуты также могут быть окружение на параметры.</span><span class="sxs-lookup"><span data-stu-id="c3c10-251">Attributes can also be places on parameters.</span></span> <span data-ttu-id="c3c10-252">В этом случае затем поместите в той же строке, в качестве параметра и перед именем:</span><span class="sxs-lookup"><span data-stu-id="c3c10-252">In this case, place then on the same line as the parameter and before the name:</span></span>

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member __.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a><span data-ttu-id="c3c10-253">Форматирование нескольких атрибутов</span><span class="sxs-lookup"><span data-stu-id="c3c10-253">Formatting multiple attributes</span></span>

<span data-ttu-id="c3c10-254">Если несколько атрибутов применяются к конструкцию, которая не является параметром, следует ли размещать их таким образом, что имеется один атрибут в строке:</span><span class="sxs-lookup"><span data-stu-id="c3c10-254">When multiple attributes are applied to a construct that is not a parameter, they should be placed such that there is one attribute per line:</span></span>

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

<span data-ttu-id="c3c10-255">При применении к параметру, они должны находиться в той же строке и разделены `;` разделителя.</span><span class="sxs-lookup"><span data-stu-id="c3c10-255">When applied to a parameter, they must be on the same line and separated by a `;` separator.</span></span>

## <a name="formatting-literals"></a><span data-ttu-id="c3c10-256">Форматирование литералы</span><span class="sxs-lookup"><span data-stu-id="c3c10-256">Formatting literals</span></span>

<span data-ttu-id="c3c10-257">[F#литералы](../language-reference/literals.md) с помощью `Literal` атрибут следует поместить атрибут на отдельной строке и использовать именования camelCase:</span><span class="sxs-lookup"><span data-stu-id="c3c10-257">[F# literals](../language-reference/literals.md) using the `Literal` attribute should should place the attribute on its own line and use camelCase naming:</span></span>

```fsharp
[<Literal>]
let path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let myUrl = "www.mywebsitethatiamworkingwith.com"
```

<span data-ttu-id="c3c10-258">Избегайте размещения в той же строке, что значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="c3c10-258">Avoid placing the attribute on the same line as the value.</span></span>
