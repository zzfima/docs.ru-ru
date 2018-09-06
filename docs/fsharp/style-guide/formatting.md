---
title: 'Рекомендациями по форматированию кода F #'
description: 'Дополнительные сведения, касающиеся форматирования кода на F #.'
ms.date: 05/14/2018
ms.openlocfilehash: 0d7d2d1771710db55bf990f3a06079b2aec48fd7
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43858009"
---
# <a name="f-code-formatting-guidelines"></a><span data-ttu-id="c2db9-103">Рекомендациями по форматированию кода F #</span><span class="sxs-lookup"><span data-stu-id="c2db9-103">F# code formatting guidelines</span></span>

<span data-ttu-id="c2db9-104">В данной статье рассматриваются рекомендации по форматированию кода таким образом, код F #:</span><span class="sxs-lookup"><span data-stu-id="c2db9-104">This article offers guidelines for how to format your code so that your F# code is:</span></span>

* <span data-ttu-id="c2db9-105">Обычно рассматривать как более читаемым</span><span class="sxs-lookup"><span data-stu-id="c2db9-105">Generally viewed as more legible</span></span>
* <span data-ttu-id="c2db9-106">— В соответствии с соглашениями об примененное форматирование средства в Visual Studio и другие редакторы</span><span class="sxs-lookup"><span data-stu-id="c2db9-106">Is in accordance with conventions applied by formatting tools in Visual Studio and other editors</span></span>
* <span data-ttu-id="c2db9-107">Аналогично другим кодом по сети</span><span class="sxs-lookup"><span data-stu-id="c2db9-107">Similar to other code online</span></span>

<span data-ttu-id="c2db9-108">Эти рекомендации основаны на [полное руководство по правилам форматирования F #](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) по [Anh-Данг Фан](https://github.com/dungpa).</span><span class="sxs-lookup"><span data-stu-id="c2db9-108">These guidelines are based on [A comprehensive guide to F# Formatting Conventions](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) by [Anh-Dung Phan](https://github.com/dungpa).</span></span>

## <a name="general-rules-for-indentation"></a><span data-ttu-id="c2db9-109">Общие правила для отступа</span><span class="sxs-lookup"><span data-stu-id="c2db9-109">General rules for indentation</span></span>

<span data-ttu-id="c2db9-110">F # по умолчанию используется значащим пробелом.</span><span class="sxs-lookup"><span data-stu-id="c2db9-110">F# uses significant white space by default.</span></span> <span data-ttu-id="c2db9-111">Следующие рекомендации предназначены для предоставления рекомендации о том, как корпоративные некоторые проблемы, это может создать.</span><span class="sxs-lookup"><span data-stu-id="c2db9-111">The following guidelines are intended to provide guidance as to how to juggle some challenges this can impose.</span></span>

### <a name="using-spaces"></a><span data-ttu-id="c2db9-112">С помощью пробелов</span><span class="sxs-lookup"><span data-stu-id="c2db9-112">Using spaces</span></span>

<span data-ttu-id="c2db9-113">Если требуется отступ, необходимо использовать не знаки табуляции.</span><span class="sxs-lookup"><span data-stu-id="c2db9-113">When indentation is required, you must use spaces, not tabs.</span></span> <span data-ttu-id="c2db9-114">Необходим по крайней мере один пробел.</span><span class="sxs-lookup"><span data-stu-id="c2db9-114">At least one space is required.</span></span> <span data-ttu-id="c2db9-115">Организации могут создавать стандарты кодирования, чтобы указать число пробелов, используемых для отступов; двух, трех или четырех пробелов отступа на каждом уровне, где происходит отступа является типичным.</span><span class="sxs-lookup"><span data-stu-id="c2db9-115">Your organization can create coding standards to specify the number of spaces to use for indentation; two, three or four spaces of indentation at each level where indentation occurs is typical.</span></span>

<span data-ttu-id="c2db9-116">**Мы рекомендуем 4 пробелов для отступа.**</span><span class="sxs-lookup"><span data-stu-id="c2db9-116">**We recommend 4 spaces per indentation.**</span></span>

<span data-ttu-id="c2db9-117">С другой стороны, отступы программ сводится к субъективным.</span><span class="sxs-lookup"><span data-stu-id="c2db9-117">That said, indentation of programs is a subjective matter.</span></span> <span data-ttu-id="c2db9-118">Варианты ОК, но первое правило, необходимо следовать *согласованности отступа*.</span><span class="sxs-lookup"><span data-stu-id="c2db9-118">Variations are OK, but the first rule you should follow is *consistency of indentation*.</span></span> <span data-ttu-id="c2db9-119">Выберите широко распространенный стиль отступов и используйте его систематически во всей базе кода.</span><span class="sxs-lookup"><span data-stu-id="c2db9-119">Choose a generally accepted style of indentation and use it systematically throughout your codebase.</span></span>

## <a name="formatting-blank-lines"></a><span data-ttu-id="c2db9-120">Форматирование пустых строк</span><span class="sxs-lookup"><span data-stu-id="c2db9-120">Formatting blank lines</span></span>

* <span data-ttu-id="c2db9-121">Отдельные верхнего уровня функций и классов определения двух пустыми строками.</span><span class="sxs-lookup"><span data-stu-id="c2db9-121">Separate top-level function and class definitions with two blank lines.</span></span>
* <span data-ttu-id="c2db9-122">Определения методов внутри класса разделяются одна пустая строка.</span><span class="sxs-lookup"><span data-stu-id="c2db9-122">Method definitions inside a class are separated by a single blank line.</span></span>
* <span data-ttu-id="c2db9-123">Лишних пустых строк может использоваться для разделения групп связанных функций (только в случае необходимости).</span><span class="sxs-lookup"><span data-stu-id="c2db9-123">Extra blank lines may be used (sparingly) to separate groups of related functions.</span></span> <span data-ttu-id="c2db9-124">Можно опустить пустые строки между ряд связанных командных строк (например, набор заглушки).</span><span class="sxs-lookup"><span data-stu-id="c2db9-124">Blank lines may be omitted between a bunch of related one-liners (for example, a set of dummy implementations).</span></span>
* <span data-ttu-id="c2db9-125">Используйте пустые строки в функции, только в случае необходимости, чтобы указать логические разделы.</span><span class="sxs-lookup"><span data-stu-id="c2db9-125">Use blank lines in functions, sparingly, to indicate logical sections.</span></span>

## <a name="formatting-comments"></a><span data-ttu-id="c2db9-126">Форматирование комментарии</span><span class="sxs-lookup"><span data-stu-id="c2db9-126">Formatting comments</span></span>

<span data-ttu-id="c2db9-127">Обычно предпочтение комментарии блок в стиле ML несколько комментариев двойной косой чертой.</span><span class="sxs-lookup"><span data-stu-id="c2db9-127">Generally prefer multiple double-slash comments over ML-style block comments.</span></span>

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

<span data-ttu-id="c2db9-128">Встроенные комментарии должны преобразование первой буквы.</span><span class="sxs-lookup"><span data-stu-id="c2db9-128">Inline comments should capitalize the first letter.</span></span>

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a><span data-ttu-id="c2db9-129">Соглашения об именах</span><span class="sxs-lookup"><span data-stu-id="c2db9-129">Naming conventions</span></span>

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a><span data-ttu-id="c2db9-130">Использующие camelCase для класса, привязанного к выражению с связыванием и шаблон значения и функции</span><span class="sxs-lookup"><span data-stu-id="c2db9-130">Use camelCase for class-bound, expression-bound and pattern-bound values and functions</span></span>

<span data-ttu-id="c2db9-131">Довольно часто и стиль принятые F # для использования camelCase все имена привязку как локальные переменные или соответствия шаблону и определения функций.</span><span class="sxs-lookup"><span data-stu-id="c2db9-131">It is common and accepted F# style to use camelCase for all names bound as local variables or in pattern matches and function definitions.</span></span>

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

<span data-ttu-id="c2db9-132">Локально функций в классах, также следует использовать camelCase.</span><span class="sxs-lookup"><span data-stu-id="c2db9-132">Locally-bound functions in classes should also use camelCase.</span></span>

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a><span data-ttu-id="c2db9-133">Использующие camelCase для связанного с модулем открытых функций</span><span class="sxs-lookup"><span data-stu-id="c2db9-133">Use camelCase for module-bound public functions</span></span>

<span data-ttu-id="c2db9-134">Когда связанного с модулем функции является частью открытого API, его следует использовать camelCase.</span><span class="sxs-lookup"><span data-stu-id="c2db9-134">When a module-bound function is part of a public API, it should use camelCase:</span></span>

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a><span data-ttu-id="c2db9-135">Использующие camelCase для внутреннего использования и частных значения связанного с модулем и функции</span><span class="sxs-lookup"><span data-stu-id="c2db9-135">Use camelCase for internal and private module-bound values and functions</span></span>

<span data-ttu-id="c2db9-136">Использования camelCase закрытый значений связанного с модулем, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="c2db9-136">Use camelCase for private module-bound values, including the following:</span></span>

* <span data-ttu-id="c2db9-137">Нерегламентированные функции в скриптах</span><span class="sxs-lookup"><span data-stu-id="c2db9-137">Ad hoc functions in scripts</span></span>

* <span data-ttu-id="c2db9-138">Значения, входящим в состав внутренняя реализация модуля или тип</span><span class="sxs-lookup"><span data-stu-id="c2db9-138">Values making up the internal implementation of a module or type</span></span>

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a><span data-ttu-id="c2db9-139">Использующие camelCase для параметров</span><span class="sxs-lookup"><span data-stu-id="c2db9-139">Use camelCase for parameters</span></span>

<span data-ttu-id="c2db9-140">Все параметры следует использовать camelCase в соответствии с соглашениями об именовании .NET.</span><span class="sxs-lookup"><span data-stu-id="c2db9-140">All parameters should use camelCase in accordance with .NET naming conventions.</span></span>

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a><span data-ttu-id="c2db9-141">Используйте PascalCase для модулей</span><span class="sxs-lookup"><span data-stu-id="c2db9-141">Use PascalCase for modules</span></span>

<span data-ttu-id="c2db9-142">Все модули (верхнего уровня, внутренний, закрытый, вложенные) следует использовать PascalCase.</span><span class="sxs-lookup"><span data-stu-id="c2db9-142">All modules (top-level, internal, private, nested) should use PascalCase.</span></span>

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a><span data-ttu-id="c2db9-143">Использующие PascalCase для объявления типов, членов и меток</span><span class="sxs-lookup"><span data-stu-id="c2db9-143">Use PascalCase for type declarations, members, and labels</span></span>

<span data-ttu-id="c2db9-144">Классы, интерфейсы, структуры, перечисления, делегаты, записи и размеченные объединения должны иметь имя с PascalCase.</span><span class="sxs-lookup"><span data-stu-id="c2db9-144">Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase.</span></span> <span data-ttu-id="c2db9-145">Элементы типов и метки для записи и размеченные объединения также следует использовать PascalCase.</span><span class="sxs-lookup"><span data-stu-id="c2db9-145">Members within types and labels for records and discriminated unions should also use PascalCase.</span></span>

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

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a><span data-ttu-id="c2db9-146">Использующие PascalCase для конструкций, встроенными в .NET</span><span class="sxs-lookup"><span data-stu-id="c2db9-146">Use PascalCase for constructs intrinsic to .NET</span></span>

<span data-ttu-id="c2db9-147">Пространства имен, исключения, события и проект /`.dll` имена также следует использовать PascalCase.</span><span class="sxs-lookup"><span data-stu-id="c2db9-147">Namespaces, exceptions, events, and project/`.dll` names should also use PascalCase.</span></span> <span data-ttu-id="c2db9-148">Не только делает ли это потребление из других языков .NET, в целом более привычны для потребителей, он также был совместим с .NET соглашения об именовании, которые могут возникнуть.</span><span class="sxs-lookup"><span data-stu-id="c2db9-148">Not only does this make consumption from other .NET languages feel more natural to consumers, it's also consistent with .NET naming conventions that you are likely to encounter.</span></span>

### <a name="avoid-underscores-in-names"></a><span data-ttu-id="c2db9-149">Избежать символов подчеркивания в именах</span><span class="sxs-lookup"><span data-stu-id="c2db9-149">Avoid underscores in names</span></span>

<span data-ttu-id="c2db9-150">Исторически сложилось так, что некоторые библиотеки F # использовали символы подчеркивания в именах.</span><span class="sxs-lookup"><span data-stu-id="c2db9-150">Historically, some F# libraries have used underscores in names.</span></span> <span data-ttu-id="c2db9-151">Тем не менее принимается больше не широко, отчасти потому, что он противоречит соглашения об именовании .NET.</span><span class="sxs-lookup"><span data-stu-id="c2db9-151">However, this is no longer widely accepted, partly because it clashes with .NET naming conventions.</span></span> <span data-ttu-id="c2db9-152">С другой стороны, некоторые программисты на F # используйте символы подчеркивания во многом, отчасти по историческим причинам и важно допуска и уважение.</span><span class="sxs-lookup"><span data-stu-id="c2db9-152">That said, some F# programmers use underscores heavily, partly for historical reasons, and tolerance and respect is important.</span></span> <span data-ttu-id="c2db9-153">Однако имейте в виду, что стиль часто нравилось с другими пользователями, существует выбор, следует ли использовать его.</span><span class="sxs-lookup"><span data-stu-id="c2db9-153">However, be aware that the style is often disliked by others who have a choice about whether to use it.</span></span>

<span data-ttu-id="c2db9-154">Некоторые исключения включает в себя взаимодействие с компонентами в машинном коде, где очень распространены символы подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="c2db9-154">Some exceptions includes interoperating with native components, where underscores are very common.</span></span>

### <a name="use-standard-f-operators"></a><span data-ttu-id="c2db9-155">Использовать стандартные операторы F #</span><span class="sxs-lookup"><span data-stu-id="c2db9-155">Use standard F# operators</span></span>

<span data-ttu-id="c2db9-156">Следующие операторы определены в стандартной библиотеке F # и должен использоваться вместо определения эквиваленты.</span><span class="sxs-lookup"><span data-stu-id="c2db9-156">The following operators are defined in the F# standard library and should be used instead of defining equivalents.</span></span> <span data-ttu-id="c2db9-157">Использование этих операторов рекомендуется, так как он, как правило, чтобы сделать код более читаемым и устойчивым.</span><span class="sxs-lookup"><span data-stu-id="c2db9-157">Using these operators is recommended as it tends to make code more readable and idiomatic.</span></span> <span data-ttu-id="c2db9-158">Разработчиков, имеющих опыт в OCaml или других функциональный язык программирования, могли привыкнуть к различных выражений.</span><span class="sxs-lookup"><span data-stu-id="c2db9-158">Developers with a background in OCaml or other functional programming language may be accustomed to different idioms.</span></span> <span data-ttu-id="c2db9-159">В следующем списке перечислены рекомендуемые операторов F #.</span><span class="sxs-lookup"><span data-stu-id="c2db9-159">The following list summarizes the recommended F# operators.</span></span>

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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a><span data-ttu-id="c2db9-160">Используйте синтаксис префикс для универсальных типов (`Foo<T>`) предпочтение постфиксный синтаксис (`T Foo`)</span><span class="sxs-lookup"><span data-stu-id="c2db9-160">Use prefix syntax for generics (`Foo<T>`) in preference to postfix syntax (`T Foo`)</span></span>

<span data-ttu-id="c2db9-161">F # наследует стиль постфиксного ML именования универсальных типов (например, `int list`) а также префикс стиля .NET (например, `list<int>`).</span><span class="sxs-lookup"><span data-stu-id="c2db9-161">F# inherits both the postfix ML style of naming generic types (for example, `int list`) as well as the prefix .NET style (for example, `list<int>`).</span></span> <span data-ttu-id="c2db9-162">Предпочитаете в стиле .NET, за исключением четырех определенных типов:</span><span class="sxs-lookup"><span data-stu-id="c2db9-162">Prefer the .NET style, except for four specific types:</span></span>

1. <span data-ttu-id="c2db9-163">Для списки F #, используйте в постфиксной форме: `int list` вместо `list<int>`.</span><span class="sxs-lookup"><span data-stu-id="c2db9-163">For F# Lists, use the postfix form: `int list` rather than `list<int>`.</span></span>
2. <span data-ttu-id="c2db9-164">Для параметры F #, используйте в постфиксной форме: `int option` вместо `option<int>`.</span><span class="sxs-lookup"><span data-stu-id="c2db9-164">For F# Options, use the postfix form: `int option` rather than `option<int>`.</span></span>
3. <span data-ttu-id="c2db9-165">Для F # массивы, используйте имя синтаксические `int[]` вместо `int array` или `array<int>`.</span><span class="sxs-lookup"><span data-stu-id="c2db9-165">For F# arrays, use the syntactic name `int[]` rather than `int array` or `array<int>`.</span></span>
4. <span data-ttu-id="c2db9-166">Ссылочные ячейки, используйте `int ref` вместо `ref<int>` или `Ref<int>`.</span><span class="sxs-lookup"><span data-stu-id="c2db9-166">For Reference Cells, use `int ref` rather than `ref<int>` or `Ref<int>`.</span></span>

<span data-ttu-id="c2db9-167">Для всех других типов используйте форму префикс.</span><span class="sxs-lookup"><span data-stu-id="c2db9-167">For all other types, use the prefix form.</span></span>

## <a name="formatting-tuples"></a><span data-ttu-id="c2db9-168">Форматирование кортежей</span><span class="sxs-lookup"><span data-stu-id="c2db9-168">Formatting tuples</span></span>

<span data-ttu-id="c2db9-169">Создание экземпляра кортежа должно быть заключено в скобки и разделителей запятые внутри должен следовать один пробел, например: `(1, 2)`, `(x, y, z)`.</span><span class="sxs-lookup"><span data-stu-id="c2db9-169">A tuple instantiation should be parenthesized, and the delimiting commas within should be followed by a single space, for example: `(1, 2)`, `(x, y, z)`.</span></span>

<span data-ttu-id="c2db9-170">Обычно принимается опустить скобки при сопоставлении шаблонов кортежей:</span><span class="sxs-lookup"><span data-stu-id="c2db9-170">It is commonly accepted to omit parentheses in pattern matching of tuples:</span></span>

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

## <a name="formatting-discriminated-union-declarations"></a><span data-ttu-id="c2db9-171">Форматирование размеченные объявления объединений</span><span class="sxs-lookup"><span data-stu-id="c2db9-171">Formatting discriminated union declarations</span></span>

<span data-ttu-id="c2db9-172">Отступ `|` в определении типа по 4 пробела:</span><span class="sxs-lookup"><span data-stu-id="c2db9-172">Indent `|` in type definition by 4 spaces:</span></span>

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

## <a name="formatting-discriminated-unions"></a><span data-ttu-id="c2db9-173">Форматирование размеченные объединения</span><span class="sxs-lookup"><span data-stu-id="c2db9-173">Formatting discriminated unions</span></span>

<span data-ttu-id="c2db9-174">Созданный экземпляр размеченные объединения, которые разбиваются на несколько строк следует предоставить новую область с отступами содержащиеся данные:</span><span class="sxs-lookup"><span data-stu-id="c2db9-174">Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:</span></span>

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

<span data-ttu-id="c2db9-175">Также может быть закрывающую скобку на новой строке:</span><span class="sxs-lookup"><span data-stu-id="c2db9-175">The closing parenthesis can also be on a new line:</span></span>

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a><span data-ttu-id="c2db9-176">Форматирование запись объявления</span><span class="sxs-lookup"><span data-stu-id="c2db9-176">Formatting record declarations</span></span>

<span data-ttu-id="c2db9-177">Отступ `{` в типе определения по 4, пробелы и начать полей списка полей в той же строке:</span><span class="sxs-lookup"><span data-stu-id="c2db9-177">Indent `{` in type definition by 4 spaces and start the field list on the same line:</span></span>

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

<span data-ttu-id="c2db9-178">Поместив токен открывающий в той же строке, а также маркер закрытия в новой строке также допустимо, но имейте в виду, что вам нужно использовать [подробный синтаксис](../language-reference/verbose-syntax.md) для определения элементов ( `with` ключевое слово):</span><span class="sxs-lookup"><span data-stu-id="c2db9-178">Placing the opening token on the same line and the closing token on a new line is also fine, but be aware that you need to use the [verbose syntax](../language-reference/verbose-syntax.md) to define members (the `with` keyword):</span></span>

```fsharp
//  OK, but verbose syntax required
type PostalAddress = { 
    Address: string
    City: string
    Zip: string
} with
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City
```

## <a name="formatting-records"></a><span data-ttu-id="c2db9-179">Форматирование записей</span><span class="sxs-lookup"><span data-stu-id="c2db9-179">Formatting records</span></span>

<span data-ttu-id="c2db9-180">Короткие записи могут быть написаны на одной строке:</span><span class="sxs-lookup"><span data-stu-id="c2db9-180">Short records can be written in one line:</span></span>

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

<span data-ttu-id="c2db9-181">Длинные записи следует использовать новые строки для меток:</span><span class="sxs-lookup"><span data-stu-id="c2db9-181">Records that are longer should use new lines for labels:</span></span>

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="c2db9-182">Поместив токен открывающий в той же строке, а также маркер закрытия в новой строке также очень мило:</span><span class="sxs-lookup"><span data-stu-id="c2db9-182">Placing the opening token on the same line and the closing token on a new line is also fine:</span></span>

```fsharp
let rainbow = {
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
```

<span data-ttu-id="c2db9-183">Те же правила применяются для элементов списка и массива.</span><span class="sxs-lookup"><span data-stu-id="c2db9-183">The same rules apply for list and array elements.</span></span>

## <a name="formatting-lists-and-arrays"></a><span data-ttu-id="c2db9-184">Форматирование, списки и массивы</span><span class="sxs-lookup"><span data-stu-id="c2db9-184">Formatting lists and arrays</span></span>

<span data-ttu-id="c2db9-185">Запись `x :: l` с пробелы вокруг `::` оператор (`::` инфиксные оператор, поэтому окружен пробелами) и `[1; 2; 3]` (`;` — разделитель, следовательно, разделенных пробелами).</span><span class="sxs-lookup"><span data-stu-id="c2db9-185">Write `x :: l` with spaces around the `::` operator (`::` is an infix operator, hence surrounded by spaces) and `[1; 2; 3]` (`;` is a delimiter, hence followed by a space).</span></span>

<span data-ttu-id="c2db9-186">Всегда используйте по крайней мере один пробел между двумя операторами distinct стиле фигурную скобку.</span><span class="sxs-lookup"><span data-stu-id="c2db9-186">Always use at least one space between two distinct brace-like operators.</span></span> <span data-ttu-id="c2db9-187">Например, оставьте пробел между `[` и `{`.</span><span class="sxs-lookup"><span data-stu-id="c2db9-187">For example, leave a space between a `[` and a `{`.</span></span>

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

<span data-ttu-id="c2db9-188">Списки и массивы, которые разбиты на несколько строк выполните аналогичные правила, как записи.</span><span class="sxs-lookup"><span data-stu-id="c2db9-188">Lists and arrays that split across multiple lines follow a similar rule as records do:</span></span>

```fsharp
let pascalsTriangle = [|
    [|1|]
    [|1; 1|]
    [|1; 2; 1|]
    [|1; 3; 3; 1|]
    [|1; 4; 6; 4; 1|]
    [|1; 5; 10; 10; 5; 1|]
    [|1; 6; 15; 20; 15; 6; 1|]
    [|1; 7; 21; 35; 35; 21; 7; 1|]
    [|1; 8; 28; 56; 70; 56; 28; 8; 1|]
|]
```

## <a name="formatting-if-expressions"></a><span data-ttu-id="c2db9-189">Если форматирования выражения</span><span class="sxs-lookup"><span data-stu-id="c2db9-189">Formatting if expressions</span></span>

<span data-ttu-id="c2db9-190">Отступ элемента условные выражения зависит от размеров выражений, составляющих их.</span><span class="sxs-lookup"><span data-stu-id="c2db9-190">Indentation of conditionals depends on the sizes of the expressions that make them up.</span></span> <span data-ttu-id="c2db9-191">Если `cond`, `e1` и `e2` короткие, просто записывать их в одной строке:</span><span class="sxs-lookup"><span data-stu-id="c2db9-191">If `cond`, `e1` and `e2` are short, simply write them on one line:</span></span>

```fsharp
if cond then e1 else e2
```

<span data-ttu-id="c2db9-192">Если параметр `cond`, `e1` или `e2` больше времени, но не несколько строк:</span><span class="sxs-lookup"><span data-stu-id="c2db9-192">If either `cond`, `e1` or `e2` are longer, but not multi-line:</span></span>

```fsharp
if cond
then e1
else e2
```

<span data-ttu-id="c2db9-193">Если любое из выражений несколько строк:</span><span class="sxs-lookup"><span data-stu-id="c2db9-193">If any of the expressions are multi-line:</span></span>

```fsharp
if cond then
    e1
else
    e2
```

<span data-ttu-id="c2db9-194">Несколько условий с `elif` и `else` отображаются с отступом в той же области, что `if`:</span><span class="sxs-lookup"><span data-stu-id="c2db9-194">Multiple conditionals with `elif` and `else` are indented at the same scope as the `if`:</span></span>

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a><span data-ttu-id="c2db9-195">Шаблон сопоставления конструкции</span><span class="sxs-lookup"><span data-stu-id="c2db9-195">Pattern matching constructs</span></span>

<span data-ttu-id="c2db9-196">Используйте `|` для каждого предложения совпадения с без отступов.</span><span class="sxs-lookup"><span data-stu-id="c2db9-196">Use a `|` for each clause of a match with no indentation.</span></span> <span data-ttu-id="c2db9-197">Если выражение является коротким, можно с помощью одной строки, если каждой части выражения стоит также выполняется очень просто.</span><span class="sxs-lookup"><span data-stu-id="c2db9-197">If the expression is short, you can consider using a single line if each subexpression is also simple.</span></span>

```fsharp
// OK
match l with
| { him = x; her = "Posh" } :: tail -> _
| _ :: tail -> findDavid tail
| [] -> failwith "Couldn't find David"

// Not OK
match l with
    | { him = x; her = "Posh" } :: tail -> _
    | _ :: tail -> findDavid tail
    | [] -> failwith "Couldn't find David"
```

<span data-ttu-id="c2db9-198">Если выражение справа сопоставления стрелку шаблона слишком велико, перемещается в следующую строку, с отступом один шаг из `match` / `|`.</span><span class="sxs-lookup"><span data-stu-id="c2db9-198">If the expression on the right of the pattern matching arrow is too large, move it to the following line, indented one step from the `match`/`|`.</span></span>

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

<span data-ttu-id="c2db9-199">Сопоставления анонимных функций, начиная с шаблонов `function`, обычно не создать отступы слишком далеко.</span><span class="sxs-lookup"><span data-stu-id="c2db9-199">Pattern matching of anonymous functions, starting by `function`, should generally not indent too far.</span></span> <span data-ttu-id="c2db9-200">Например следующим образом отступов одну область очень мило:</span><span class="sxs-lookup"><span data-stu-id="c2db9-200">For example, indenting one scope as follows is fine:</span></span>

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

<span data-ttu-id="c2db9-201">Шаблоны в функциях, определяемых `let` или `let rec` должно быть с отступом 4 пробелов после начала `let`, даже если `function` используется ключевое слово:</span><span class="sxs-lookup"><span data-stu-id="c2db9-201">Pattern matching in functions defined by `let` or `let rec` should be indented 4 spaces after starting of `let`, even if `function` keyword is used:</span></span>

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

<span data-ttu-id="c2db9-202">Мы не рекомендуем выравнивание кнопки со стрелками.</span><span class="sxs-lookup"><span data-stu-id="c2db9-202">We do not recommend aligning arrows.</span></span>

## <a name="formatting-trywith-expressions"></a><span data-ttu-id="c2db9-203">Форматирования try / with выражения</span><span class="sxs-lookup"><span data-stu-id="c2db9-203">Formatting try/with expressions</span></span>

<span data-ttu-id="c2db9-204">Сопоставление шаблонов в тип исключения должен иметь отступ на том же уровне, что `with`.</span><span class="sxs-lookup"><span data-stu-id="c2db9-204">Pattern matching on the exception type should be indented at the same level as `with`.</span></span>

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

## <a name="formatting-function-parameter-application"></a><span data-ttu-id="c2db9-205">Форматирование функции параметр приложения</span><span class="sxs-lookup"><span data-stu-id="c2db9-205">Formatting function parameter application</span></span>

<span data-ttu-id="c2db9-206">Как правило большинство функции параметр приложения выполняется в той же строке.</span><span class="sxs-lookup"><span data-stu-id="c2db9-206">In general, most function parameter application is done on the same line.</span></span>

<span data-ttu-id="c2db9-207">Если вы хотите применить параметры функции с новой строки, отступ их на одну область.</span><span class="sxs-lookup"><span data-stu-id="c2db9-207">If you wish to apply parameters to a function on a new line, indent them by one scope.</span></span>

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

<span data-ttu-id="c2db9-208">Те же правила применяются для лямбда-выражения как аргументы функции.</span><span class="sxs-lookup"><span data-stu-id="c2db9-208">The same guidelines apply for lambda expressions as function arguments.</span></span> <span data-ttu-id="c2db9-209">Если тело лямбда-выражения, текст может иметь другую строку, отступом в одну область</span><span class="sxs-lookup"><span data-stu-id="c2db9-209">If the body of a lambda expression, the body can have another line, indented by one scope</span></span>

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

<span data-ttu-id="c2db9-210">Тем не менее если тело лямбда-выражения является более одной строки, рассмотрите возможность факторинг его в отдельную функцию вместо конструкцию многострочного применяется как один аргумент функции.</span><span class="sxs-lookup"><span data-stu-id="c2db9-210">However, if the body of a lambda expression is more than one line, consider factoring it out into a separate function rather than have a multi-line construct applied as a single argument to a function.</span></span>

### <a name="formatting-infix-operators"></a><span data-ttu-id="c2db9-211">Форматирование инфиксные операторы</span><span class="sxs-lookup"><span data-stu-id="c2db9-211">Formatting infix operators</span></span>

<span data-ttu-id="c2db9-212">Отдельные операторы пробелами.</span><span class="sxs-lookup"><span data-stu-id="c2db9-212">Separate operators by spaces.</span></span> <span data-ttu-id="c2db9-213">Очевидным исключения этого правила являются `!` и `.` операторы.</span><span class="sxs-lookup"><span data-stu-id="c2db9-213">Obvious exceptions to this rule are the `!` and `.` operators.</span></span>

<span data-ttu-id="c2db9-214">Инфиксные выражения — ОК в линейку и того же столбца:</span><span class="sxs-lookup"><span data-stu-id="c2db9-214">Infix expressions are OK to lineup on same column:</span></span>

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a><span data-ttu-id="c2db9-215">Форматирование конвейерных операторов</span><span class="sxs-lookup"><span data-stu-id="c2db9-215">Formatting pipeline operators</span></span>

<span data-ttu-id="c2db9-216">Конвейер `|>` операторы должны начать выполняться под выражения, они работают.</span><span class="sxs-lookup"><span data-stu-id="c2db9-216">Pipeline `|>` operators should go underneath the expressions they operate on.</span></span>

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

### <a name="formatting-modules"></a><span data-ttu-id="c2db9-217">Модули форматирования</span><span class="sxs-lookup"><span data-stu-id="c2db9-217">Formatting modules</span></span>

<span data-ttu-id="c2db9-218">Код в локальном модуле должен иметь отступ относительно модуля, но код в модуль верхнего уровня не должен иметь отступ.</span><span class="sxs-lookup"><span data-stu-id="c2db9-218">Code in a local module must be indented relative to the module, but code in a top-level module should not be indented.</span></span> <span data-ttu-id="c2db9-219">Элементы пространства имен нет необходимости иметь отступ.</span><span class="sxs-lookup"><span data-stu-id="c2db9-219">Namespace elements do not have to be indented.</span></span>

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

### <a name="formatting-object-expressions-and-interfaces"></a><span data-ttu-id="c2db9-220">Форматирование выражения объекта и интерфейсов</span><span class="sxs-lookup"><span data-stu-id="c2db9-220">Formatting object expressions and interfaces</span></span>

<span data-ttu-id="c2db9-221">Выражения объекта и интерфейсы должны быть выровнены с таким же образом `member` с отступом после 4 пробела.</span><span class="sxs-lookup"><span data-stu-id="c2db9-221">Object expressions and interfaces should be aligned in the same way with `member` being indented after 4 spaces.</span></span>

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s : String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a><span data-ttu-id="c2db9-222">Форматирование пустое пространство в выражениях</span><span class="sxs-lookup"><span data-stu-id="c2db9-222">Formatting white space in expressions</span></span>

<span data-ttu-id="c2db9-223">Избегайте лишние пробелы в выражения F #.</span><span class="sxs-lookup"><span data-stu-id="c2db9-223">Avoid extraneous white space in F# expressions.</span></span>

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

<span data-ttu-id="c2db9-224">Именованные аргументы также не должны иметь пространство вокруг `=`:</span><span class="sxs-lookup"><span data-stu-id="c2db9-224">Named arguments should also not have space surrounding the `=`:</span></span>

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```
