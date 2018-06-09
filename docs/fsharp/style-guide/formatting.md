---
title: 'Правила форматирования кода F #'
description: 'Дополнительные рекомендации для форматирования кода F #.'
ms.date: 05/14/2018
ms.openlocfilehash: 6c8e4059fd4bf1e7450118a6df02609217c4f4db
ms.sourcegitcommit: 2ad7d06f4f469b5d8a5280ac0e0289a81867fc8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2018
ms.locfileid: "35231515"
---
# <a name="f-code-formatting-guidelines"></a><span data-ttu-id="0b01b-103">Правила форматирования кода F #</span><span class="sxs-lookup"><span data-stu-id="0b01b-103">F# code formatting guidelines</span></span>

<span data-ttu-id="0b01b-104">В этой статье предлагаются рекомендации по форматировать код так, чтобы код F #:</span><span class="sxs-lookup"><span data-stu-id="0b01b-104">This article offers guidelines for how to format your code so that your F# code is:</span></span>

* <span data-ttu-id="0b01b-105">Обычно рассматривать как более читаемым</span><span class="sxs-lookup"><span data-stu-id="0b01b-105">Generally viewed as more legible</span></span>
* <span data-ttu-id="0b01b-106">— В соответствии с соглашениями, применяется форматирование средств в Visual Studio и других редакторах</span><span class="sxs-lookup"><span data-stu-id="0b01b-106">Is in accordance with conventions applied by formatting tools in Visual Studio and other editors</span></span>
* <span data-ttu-id="0b01b-107">Аналогично другим кодом по сети</span><span class="sxs-lookup"><span data-stu-id="0b01b-107">Similar to other code online</span></span>

<span data-ttu-id="0b01b-108">Эти рекомендации основаны на [полное руководство по F # форматирование соглашения о](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) по [Phan Anh Dung](https://github.com/dungpa).</span><span class="sxs-lookup"><span data-stu-id="0b01b-108">These guidelines are based on [A comprehensive guide to F# Formatting Conventions](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) by [Anh-Dung Phan](https://github.com/dungpa).</span></span>

## <a name="general-rules-for-indentation"></a><span data-ttu-id="0b01b-109">Общие правила использования отступов</span><span class="sxs-lookup"><span data-stu-id="0b01b-109">General rules for indentation</span></span>

<span data-ttu-id="0b01b-110">F # по умолчанию используется значимых пробелов.</span><span class="sxs-lookup"><span data-stu-id="0b01b-110">F# uses significant whitespace by default.</span></span> <span data-ttu-id="0b01b-111">Следующие инструкции предназначены для предоставления рекомендации о том, как работать с определенными трудностями, это можно наложить.</span><span class="sxs-lookup"><span data-stu-id="0b01b-111">The following guidelines are intended to provide guidance as to how to juggle some challenges this can impose.</span></span>

### <a name="using-spaces"></a><span data-ttu-id="0b01b-112">С помощью пространств</span><span class="sxs-lookup"><span data-stu-id="0b01b-112">Using spaces</span></span>

<span data-ttu-id="0b01b-113">Если требуется отступ, необходимо использовать пробелы, а не символы табуляции.</span><span class="sxs-lookup"><span data-stu-id="0b01b-113">When indentation is required, you must use spaces, not tabs.</span></span> <span data-ttu-id="0b01b-114">Требуется по крайней мере один пробел.</span><span class="sxs-lookup"><span data-stu-id="0b01b-114">At least one space is required.</span></span> <span data-ttu-id="0b01b-115">Организации могут создавать стандарты кодирования, чтобы указать количество пробелов, используемых для отступов; является типичным для двух, трех или четырех пробелов отступа на каждом уровне, где происходит отступов.</span><span class="sxs-lookup"><span data-stu-id="0b01b-115">Your organization can create coding standards to specify the number of spaces to use for indentation; two, three or four spaces of indentation at each level where indentation occurs is typical.</span></span>

<span data-ttu-id="0b01b-116">**Мы рекомендуем 4 пространств для каждого отступа.**</span><span class="sxs-lookup"><span data-stu-id="0b01b-116">**We recommend 4 spaces per indentation.**</span></span>

<span data-ttu-id="0b01b-117">С другой стороны, отступы программ — это субъективная тема.</span><span class="sxs-lookup"><span data-stu-id="0b01b-117">That said, indentation of programs is a subjective matter.</span></span> <span data-ttu-id="0b01b-118">Варианты ОК, но первое правило, необходимо следовать *согласованности отступа*.</span><span class="sxs-lookup"><span data-stu-id="0b01b-118">Variations are OK, but the first rule you should follow is *consistency of indentation*.</span></span> <span data-ttu-id="0b01b-119">Выбор стиля общепринятые отступов и использовать его систематически во всей базе кода.</span><span class="sxs-lookup"><span data-stu-id="0b01b-119">Choose a generally accepted style of indentation and use it systematically throughout your codebase.</span></span>

## <a name="formatting-blank-lines"></a><span data-ttu-id="0b01b-120">Форматирование пустых строк</span><span class="sxs-lookup"><span data-stu-id="0b01b-120">Formatting blank lines</span></span>

* <span data-ttu-id="0b01b-121">Отдельные верхнего уровня функций и классов определения с две пустые строки.</span><span class="sxs-lookup"><span data-stu-id="0b01b-121">Separate top-level function and class definitions with two blank lines.</span></span>
* <span data-ttu-id="0b01b-122">Метод определения внутри класса разделяются одна пустая строка.</span><span class="sxs-lookup"><span data-stu-id="0b01b-122">Method definitions inside a class are separated by a single blank line.</span></span>
* <span data-ttu-id="0b01b-123">Лишних пустых строк может использоваться для разделения группы связанных функций (ограниченно).</span><span class="sxs-lookup"><span data-stu-id="0b01b-123">Extra blank lines may be used (sparingly) to separate groups of related functions.</span></span> <span data-ttu-id="0b01b-124">Можно опустить пустые строки между множества связанных командных строк (например, набор фиктивный реализации).</span><span class="sxs-lookup"><span data-stu-id="0b01b-124">Blank lines may be omitted between a bunch of related one-liners (for example, a set of dummy implementations).</span></span>
* <span data-ttu-id="0b01b-125">Используйте пустые строки в функции, только в случае необходимости, чтобы указать логические разделы.</span><span class="sxs-lookup"><span data-stu-id="0b01b-125">Use blank lines in functions, sparingly, to indicate logical sections.</span></span>

## <a name="formatting-comments"></a><span data-ttu-id="0b01b-126">Форматирование комментарии</span><span class="sxs-lookup"><span data-stu-id="0b01b-126">Formatting comments</span></span>

<span data-ttu-id="0b01b-127">Обычно предпочтение комментарии блока стиля ML несколько комментариев косая черта double.</span><span class="sxs-lookup"><span data-stu-id="0b01b-127">Generally prefer multiple double-slash comments over ML-style block comments.</span></span>

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

<span data-ttu-id="0b01b-128">Встроенных комментариев следует преобразовать в прописную первую букву.</span><span class="sxs-lookup"><span data-stu-id="0b01b-128">Inline comments should capitalize the first letter.</span></span>

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a><span data-ttu-id="0b01b-129">Соглашения об именах</span><span class="sxs-lookup"><span data-stu-id="0b01b-129">Naming conventions</span></span>

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a><span data-ttu-id="0b01b-130">Используйте camelCase для класса привязанных к ограничениям, выражение привязки и шаблон значения и функции</span><span class="sxs-lookup"><span data-stu-id="0b01b-130">Use camelCase for class-bound, expression-bound and pattern-bound values and functions</span></span>

<span data-ttu-id="0b01b-131">Общие и принимаемые F # стиль camelCase для всех имен связан как локальные переменные или в соответствие шаблону и определения функций.</span><span class="sxs-lookup"><span data-stu-id="0b01b-131">It is common and accepted F# style to use camelCase for all names bound as local variables or in pattern matches and function definitions.</span></span>

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

<span data-ttu-id="0b01b-132">Локально функций в классах, также следует использовать camelCase.</span><span class="sxs-lookup"><span data-stu-id="0b01b-132">Locally-bound functions in classes should also use camelCase.</span></span>

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a><span data-ttu-id="0b01b-133">Используйте camelCase для открытых функций модуля привязки</span><span class="sxs-lookup"><span data-stu-id="0b01b-133">Use camelCase for module-bound public functions</span></span>

<span data-ttu-id="0b01b-134">Если функция привязкой модуль является частью открытого API, следует использовать camelCase:</span><span class="sxs-lookup"><span data-stu-id="0b01b-134">When a module-bound function is part of a public API, it should use camelCase:</span></span>

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a><span data-ttu-id="0b01b-135">Используйте camelCase для внутреннего использования и частных значения, связанные с модулем и функций</span><span class="sxs-lookup"><span data-stu-id="0b01b-135">Use camelCase for internal and private module-bound values and functions</span></span>

<span data-ttu-id="0b01b-136">Используйте camelCase для частного значения, связанные с модуля, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="0b01b-136">Use camelCase for private module-bound values, including the following:</span></span>

* <span data-ttu-id="0b01b-137">Нерегламентированные функции в скриптах</span><span class="sxs-lookup"><span data-stu-id="0b01b-137">Ad hoc functions in scripts</span></span>

* <span data-ttu-id="0b01b-138">Значения, входящим в состав внутренней реализации модуля или тип</span><span class="sxs-lookup"><span data-stu-id="0b01b-138">Values making up the internal implementation of a module or type</span></span>

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a><span data-ttu-id="0b01b-139">Для параметров следует использовать camelCase</span><span class="sxs-lookup"><span data-stu-id="0b01b-139">Use camelCase for parameters</span></span>

<span data-ttu-id="0b01b-140">Все параметры следует использовать camelCase в соответствии с соглашениями об именовании .NET.</span><span class="sxs-lookup"><span data-stu-id="0b01b-140">All parameters should use camelCase in accordance with .NET naming conventions.</span></span>

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a><span data-ttu-id="0b01b-141">Используйте PascalCase для модулей</span><span class="sxs-lookup"><span data-stu-id="0b01b-141">Use PascalCase for modules</span></span>

<span data-ttu-id="0b01b-142">Все модули (верхнего уровня, внутренний, закрытый, вложенные) следует использовать PascalCase.</span><span class="sxs-lookup"><span data-stu-id="0b01b-142">All modules (top-level, internal, private, nested) should use PascalCase.</span></span>

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a><span data-ttu-id="0b01b-143">Используйте PascalCase для объявления типов, членов и меток</span><span class="sxs-lookup"><span data-stu-id="0b01b-143">Use PascalCase for type declarations, members, and labels</span></span>

<span data-ttu-id="0b01b-144">Классы, интерфейсы, структуры, перечисления, делегаты, записи и размеченные объединения должен быть назван с PascalCase.</span><span class="sxs-lookup"><span data-stu-id="0b01b-144">Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase.</span></span> <span data-ttu-id="0b01b-145">Элементы типов и метки для записи и размеченные объединения, также следует использовать PascalCase.</span><span class="sxs-lookup"><span data-stu-id="0b01b-145">Members within types and labels for records and discriminated unions should also use PascalCase.</span></span>

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

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a><span data-ttu-id="0b01b-146">Использовать PascalCase для конструкций, встроенными в .NET</span><span class="sxs-lookup"><span data-stu-id="0b01b-146">Use PascalCase for constructs intrinsic to .NET</span></span>

<span data-ttu-id="0b01b-147">Пространства имен, исключения, события и проект и`.dll` имена также следует использовать PascalCase.</span><span class="sxs-lookup"><span data-stu-id="0b01b-147">Namespaces, exceptions, events, and project/`.dll` names should also use PascalCase.</span></span> <span data-ttu-id="0b01b-148">Не только это себя потребления из других языков .NET более естественным для потребителей, согласуется с соглашения об именовании .NET, которые могут возникнуть.</span><span class="sxs-lookup"><span data-stu-id="0b01b-148">Not only does this make consumption from other .NET languages feel more natural to consumers, it's also consistent with .NET naming conventions that you are likely to encounter.</span></span>

### <a name="avoid-underscores-in-names"></a><span data-ttu-id="0b01b-149">Избегайте подчеркивания в именах</span><span class="sxs-lookup"><span data-stu-id="0b01b-149">Avoid underscores in names</span></span>

<span data-ttu-id="0b01b-150">Исторически некоторые библиотеки F # используется символ подчеркивания в именах.</span><span class="sxs-lookup"><span data-stu-id="0b01b-150">Historically, some F# libraries have used underscores in names.</span></span> <span data-ttu-id="0b01b-151">Тем не менее принимается больше не широко, так как он конфликтует с соглашения об именовании .NET.</span><span class="sxs-lookup"><span data-stu-id="0b01b-151">However, this is no longer widely accepted, partly because it clashes with .NET naming conventions.</span></span> <span data-ttu-id="0b01b-152">С другой стороны, некоторые программисты F # для использования подчеркивания сильно, частично Исторически сложилось так и обеспечения отказоустойчивости и уважение важен.</span><span class="sxs-lookup"><span data-stu-id="0b01b-152">That said, some F# programmers use underscores heavily, partly for historical reasons, and tolerance and respect is important.</span></span> <span data-ttu-id="0b01b-153">Однако имейте в виду, что стиль часто не нравилось с другими пользователями, имеется возможность выбрать его использование.</span><span class="sxs-lookup"><span data-stu-id="0b01b-153">However, be aware that the style is often disliked by others who have a choice about whether to use it.</span></span>

<span data-ttu-id="0b01b-154">Некоторые исключения включает взаимодействие с компонентами в машинном коде, где очень распространены символы подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="0b01b-154">Some exceptions includes interoperating with native components, where underscores are very common.</span></span>

### <a name="use-standard-f-operators"></a><span data-ttu-id="0b01b-155">Использовать стандартные операторы F #</span><span class="sxs-lookup"><span data-stu-id="0b01b-155">Use standard F# operators</span></span>

<span data-ttu-id="0b01b-156">Следующие операторы определены в стандартной библиотеке F # и должны использоваться вместо того чтобы определять эквиваленты.</span><span class="sxs-lookup"><span data-stu-id="0b01b-156">The following operators are defined in the F# standard library and should be used instead of defining equivalents.</span></span> <span data-ttu-id="0b01b-157">Рекомендуется использовать эти операторы, как он, как правило, чтобы сделать код более читаемым и идиоматическое.</span><span class="sxs-lookup"><span data-stu-id="0b01b-157">Using these operators is recommended as it tends to make code more readable and idiomatic.</span></span> <span data-ttu-id="0b01b-158">Возможно, разработчиков, имеющих опыт в OCaml или других функциональный язык программирования привыкли различные стили.</span><span class="sxs-lookup"><span data-stu-id="0b01b-158">Developers with a background in OCaml or other functional programming language may be accustomed to different idioms.</span></span> <span data-ttu-id="0b01b-159">В следующем списке перечислены рекомендуемые операторы F #.</span><span class="sxs-lookup"><span data-stu-id="0b01b-159">The following list summarizes the recommended F# operators.</span></span>

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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a><span data-ttu-id="0b01b-160">Используйте синтаксис префикс для универсальных шаблонов (`Foo<T>`) предпочтительнее, чем синтаксис постфиксная (`T Foo`)</span><span class="sxs-lookup"><span data-stu-id="0b01b-160">Use prefix syntax for generics (`Foo<T>`) in preference to postfix syntax (`T Foo`)</span></span>

<span data-ttu-id="0b01b-161">F # наследует стиль постфиксная ML именования универсальных типов (например, `int list`) и префиксом .NET style (например, `list<int>`).</span><span class="sxs-lookup"><span data-stu-id="0b01b-161">F# inherits both the postfix ML style of naming generic types (for example, `int list`) as well as the prefix .NET style (for example, `list<int>`).</span></span> <span data-ttu-id="0b01b-162">Предпочитаю стиль .NET, за исключением четырех определенных типов.</span><span class="sxs-lookup"><span data-stu-id="0b01b-162">Prefer the .NET style, except for four specific types:</span></span>

1. <span data-ttu-id="0b01b-163">Для F # список, используйте в постфиксной форме: `int list` вместо `list<int>`.</span><span class="sxs-lookup"><span data-stu-id="0b01b-163">For F# Lists, use the postfix form: `int list` rather than `list<int>`.</span></span>
2. <span data-ttu-id="0b01b-164">Для параметры F #, используйте в постфиксной форме: `int option` вместо `option<int>`.</span><span class="sxs-lookup"><span data-stu-id="0b01b-164">For F# Options, use the postfix form: `int option` rather than `option<int>`.</span></span>
3. <span data-ttu-id="0b01b-165">В F # массивы, используется имя синтаксические `int[]` вместо `int array` или `array<int>`.</span><span class="sxs-lookup"><span data-stu-id="0b01b-165">For F# arrays, use the syntactic name `int[]` rather than `int array` or `array<int>`.</span></span>
4. <span data-ttu-id="0b01b-166">Ссылочные ячейки, используйте `int ref` вместо `ref<int>` или `Ref<int>`.</span><span class="sxs-lookup"><span data-stu-id="0b01b-166">For Reference Cells, use `int ref` rather than `ref<int>` or `Ref<int>`.</span></span>

<span data-ttu-id="0b01b-167">Для всех других типов используйте форму префикс.</span><span class="sxs-lookup"><span data-stu-id="0b01b-167">For all other types, use the prefix form.</span></span>

## <a name="formatting-discriminated-union-declarations"></a><span data-ttu-id="0b01b-168">Форматирование размеченные объединения объявления</span><span class="sxs-lookup"><span data-stu-id="0b01b-168">Formatting discriminated union declarations</span></span>

<span data-ttu-id="0b01b-169">Отступ `|` в определении типа 4 пробелами:</span><span class="sxs-lookup"><span data-stu-id="0b01b-169">Indent `|` in type definition by 4 spaces:</span></span>

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

<span data-ttu-id="0b01b-170">Созданный экземпляр размеченные объединения, которые разбиваются по нескольким строкам следует предоставить новой области с отступами содержащиеся данные:</span><span class="sxs-lookup"><span data-stu-id="0b01b-170">Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:</span></span>

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

<span data-ttu-id="0b01b-171">Также может быть закрывающую скобку на новой строке:</span><span class="sxs-lookup"><span data-stu-id="0b01b-171">The closing parenthesis can also be on a new line:</span></span>

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-tuples"></a><span data-ttu-id="0b01b-172">Форматирование кортежи</span><span class="sxs-lookup"><span data-stu-id="0b01b-172">Formatting tuples</span></span>

<span data-ttu-id="0b01b-173">Создание экземпляра кортежа следует заключать в круглые скобки и разделители запятые внутри должен следовать пробелом, например: `(1, 2)`, `(x, y, z)`.</span><span class="sxs-lookup"><span data-stu-id="0b01b-173">A tuple instantiation should be parenthesized, and the delimiting commas within should be followed by a single space, for example: `(1, 2)`, `(x, y, z)`.</span></span>

<span data-ttu-id="0b01b-174">Общепринятая исключение — пропустить круглые скобки в сопоставлениях с шаблоном кортежей:</span><span class="sxs-lookup"><span data-stu-id="0b01b-174">A commonly accepted exception is to omit parentheses in pattern matching of tuples:</span></span>

```fsharp
let (x, y) = z // Destructuring

match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

## <a name="formatting-records"></a><span data-ttu-id="0b01b-175">Форматирование записей</span><span class="sxs-lookup"><span data-stu-id="0b01b-175">Formatting records</span></span>

<span data-ttu-id="0b01b-176">Короткие записи могут быть записаны в одной строке:</span><span class="sxs-lookup"><span data-stu-id="0b01b-176">Short records can be written in one line:</span></span>

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

<span data-ttu-id="0b01b-177">Для меток записей, которые больше времени, следует использовать новые строки:</span><span class="sxs-lookup"><span data-stu-id="0b01b-177">Records that are longer should use new lines for labels:</span></span>

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="0b01b-178">Размещение открывающей маркер на той же строке и закрытия маркер на новой строке будет нормально.</span><span class="sxs-lookup"><span data-stu-id="0b01b-178">Placing the opening token on the same line and the closing token on a new line is also fine:</span></span>

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

<span data-ttu-id="0b01b-179">Те же правила применяются для элементов списка и массива.</span><span class="sxs-lookup"><span data-stu-id="0b01b-179">The same rules apply for list and array elements.</span></span>

## <a name="formatting-lists-and-arrays"></a><span data-ttu-id="0b01b-180">Форматирование списки и массивы</span><span class="sxs-lookup"><span data-stu-id="0b01b-180">Formatting lists and arrays</span></span>

<span data-ttu-id="0b01b-181">Запись `x :: l` с пробелы вокруг `::` оператор (`::` инфиксные оператор, поэтому окружена пробелами) и `[1; 2; 3]` (`;` — разделитель, поэтому после пробела).</span><span class="sxs-lookup"><span data-stu-id="0b01b-181">Write `x :: l` with spaces around the `::` operator (`::` is an infix operator, hence surrounded by spaces) and `[1; 2; 3]` (`;` is a delimiter, hence followed by a space).</span></span>

<span data-ttu-id="0b01b-182">Всегда используйте по крайней мере один пробел между два различных оператора like фигурную скобку.</span><span class="sxs-lookup"><span data-stu-id="0b01b-182">Always use at least one space between two distinct brace-like operators.</span></span> <span data-ttu-id="0b01b-183">Например, оставьте пробел между `[` и `{`.</span><span class="sxs-lookup"><span data-stu-id="0b01b-183">For example, leave a space between a `[` and a `{`.</span></span>

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

<span data-ttu-id="0b01b-184">Списки и массивы, которые разбиты на несколько строк выполните аналогичные правила, как записи.</span><span class="sxs-lookup"><span data-stu-id="0b01b-184">Lists and arrays that split across multiple lines follow a similar rule as records do:</span></span>

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

## <a name="formatting-if-expressions"></a><span data-ttu-id="0b01b-185">Если форматировании выражений</span><span class="sxs-lookup"><span data-stu-id="0b01b-185">Formatting if expressions</span></span>

<span data-ttu-id="0b01b-186">Отступ условные выражения зависит от размеров выражений, составляющих их.</span><span class="sxs-lookup"><span data-stu-id="0b01b-186">Indentation of conditionals depends on the sizes of the expressions that make them up.</span></span> <span data-ttu-id="0b01b-187">Если `cond`, `e1` и `e2` небольшие, просто записывать их в одной строке:</span><span class="sxs-lookup"><span data-stu-id="0b01b-187">If `cond`, `e1` and `e2` are small, simply write them on one line:</span></span>

```fsharp
if cond then e1 else e2
```

<span data-ttu-id="0b01b-188">Если `e1` и `cond` небольшие, но `e2` большой:</span><span class="sxs-lookup"><span data-stu-id="0b01b-188">If `e1` and `cond` are small, but `e2` is large:</span></span>

```fsharp
if cond then e1
else
    e2
```

<span data-ttu-id="0b01b-189">Если `e1` и `cond` велики и `e2` мал:</span><span class="sxs-lookup"><span data-stu-id="0b01b-189">If `e1` and `cond` are large and `e2` is small:</span></span>

```fsharp
if cond then
    e1
else e2
```

<span data-ttu-id="0b01b-190">Если все выражения имеют большой размер:</span><span class="sxs-lookup"><span data-stu-id="0b01b-190">If all the expressions are large:</span></span>

```fsharp
if cond then
    e1
else
    e2
```

<span data-ttu-id="0b01b-191">Несколько условий с `elif` и `else` с отступом располагаются в той же области, как `if`:</span><span class="sxs-lookup"><span data-stu-id="0b01b-191">Multiple conditionals with `elif` and `else` are indented at the same scope as the `if`:</span></span>

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a><span data-ttu-id="0b01b-192">Шаблон сопоставления конструкции</span><span class="sxs-lookup"><span data-stu-id="0b01b-192">Pattern matching constructs</span></span>

<span data-ttu-id="0b01b-193">Используйте `|` для каждого предложения совпадения с без отступов.</span><span class="sxs-lookup"><span data-stu-id="0b01b-193">Use a `|` for each clause of a match with no indentation.</span></span> <span data-ttu-id="0b01b-194">Если выражение короткий, можно с помощью одной строки, если каждая часть выражения также является простым.</span><span class="sxs-lookup"><span data-stu-id="0b01b-194">If the expression is short, you can consider using a single line if each subexpression is also simple.</span></span>

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

<span data-ttu-id="0b01b-195">Если выражение справа сопоставления стрелка шаблона слишком велико, переместите его на следующую строку с отступом один шаг из `match` / `|`.</span><span class="sxs-lookup"><span data-stu-id="0b01b-195">If the expression on the right of the pattern matching arrow is too large, move it to the following line, indented one step from the `match`/`|`.</span></span>

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

<span data-ttu-id="0b01b-196">Шаблон сопоставления анонимных функций, начиная с `function`, обычно не создать отступы слишком далеко.</span><span class="sxs-lookup"><span data-stu-id="0b01b-196">Pattern matching of anonymous functions, starting by `function`, should generally not indent too far.</span></span> <span data-ttu-id="0b01b-197">Например следующим отступов одну область подходит:</span><span class="sxs-lookup"><span data-stu-id="0b01b-197">For example, indenting one scope as follows is fine:</span></span>

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

<span data-ttu-id="0b01b-198">Совпадение по шаблону в функции, определенные по `let` или `let rec` должен быть с отступом 4 пробелов после начала `let`, даже если `function` используется ключевое слово:</span><span class="sxs-lookup"><span data-stu-id="0b01b-198">Pattern matching in functions defined by `let` or `let rec` should be indented 4 spaces after starting of `let`, even if `function` keyword is used:</span></span>

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

<span data-ttu-id="0b01b-199">Не рекомендуется выравнивание кнопки со стрелками.</span><span class="sxs-lookup"><span data-stu-id="0b01b-199">We do not recommend aligning arrows.</span></span>

## <a name="formatting-trywith-expressions"></a><span data-ttu-id="0b01b-200">Форматирование try / with выражения</span><span class="sxs-lookup"><span data-stu-id="0b01b-200">Formatting try/with expressions</span></span>

<span data-ttu-id="0b01b-201">Тип исключения сопоставления шаблонов должно иметь отступ на том же уровне, как `with`.</span><span class="sxs-lookup"><span data-stu-id="0b01b-201">Pattern matching on the exception type should be indented at the same level as `with`.</span></span>

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

## <a name="formatting-function-parameter-application"></a><span data-ttu-id="0b01b-202">Применение параметра функции форматирования</span><span class="sxs-lookup"><span data-stu-id="0b01b-202">Formatting function parameter application</span></span>

<span data-ttu-id="0b01b-203">Как правило большинство приложений параметра функция выполняется в той же строке.</span><span class="sxs-lookup"><span data-stu-id="0b01b-203">In general, most function parameter application is done on the same line.</span></span>

<span data-ttu-id="0b01b-204">Если вы хотите применить параметры к функции на новой строке, отступ их на одну область.</span><span class="sxs-lookup"><span data-stu-id="0b01b-204">If you wish to apply parameters to a function on a new line, indent them by one scope.</span></span>

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

<span data-ttu-id="0b01b-205">Те же правила применяются для лямбда-выражений в качестве аргументов функции.</span><span class="sxs-lookup"><span data-stu-id="0b01b-205">The same guidelines apply for lambda expressions as function arguments.</span></span> <span data-ttu-id="0b01b-206">Если тело лямбда-выражении, тело может быть другая строка с отступом в одну область</span><span class="sxs-lookup"><span data-stu-id="0b01b-206">If the body of a lambda expression, the body can have another line, indented by one scope</span></span>

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

<span data-ttu-id="0b01b-207">Тем не менее если тело лямбда-выражения является более одной строки, рассмотрите возможность его факторизацию в отдельную функцию, которая вместо конструкции многострочного текста, применяется как один аргумент в функцию.</span><span class="sxs-lookup"><span data-stu-id="0b01b-207">However, if the body of a lambda expression is more than one line, consider factoring it out into a separate function rather than have a multi-line construct applied as a single argument to a function.</span></span>

### <a name="formatting-infix-operators"></a><span data-ttu-id="0b01b-208">Форматирование инфиксные операторы</span><span class="sxs-lookup"><span data-stu-id="0b01b-208">Formatting infix operators</span></span>

<span data-ttu-id="0b01b-209">Отдельные операторы пробелами.</span><span class="sxs-lookup"><span data-stu-id="0b01b-209">Separate operators by spaces.</span></span> <span data-ttu-id="0b01b-210">Очевидным исключения из этого правила являются `!` и `.` операторы.</span><span class="sxs-lookup"><span data-stu-id="0b01b-210">Obvious exceptions to this rule are the `!` and `.` operators.</span></span>

<span data-ttu-id="0b01b-211">Выражения инфиксные — ОК разметка того же столбца.</span><span class="sxs-lookup"><span data-stu-id="0b01b-211">Infix expressions are OK to lineup on same column:</span></span>

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a><span data-ttu-id="0b01b-212">Форматирование конвейерных операторов</span><span class="sxs-lookup"><span data-stu-id="0b01b-212">Formatting pipeline operators</span></span>

<span data-ttu-id="0b01b-213">Конвейер `|>` операторы должна выполняться под выражения, они работают.</span><span class="sxs-lookup"><span data-stu-id="0b01b-213">Pipeline `|>` operators should go underneath the expressions they operate on.</span></span>

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

### <a name="formatting-modules"></a><span data-ttu-id="0b01b-214">Модули форматирования</span><span class="sxs-lookup"><span data-stu-id="0b01b-214">Formatting modules</span></span>

<span data-ttu-id="0b01b-215">Код в локальном модуле должен иметь отступ относительно модуля, но код модуля верхнего уровня не должен иметь отступ.</span><span class="sxs-lookup"><span data-stu-id="0b01b-215">Code in a local module must be indented relative to the module, but code in a top-level module should not be indented.</span></span> <span data-ttu-id="0b01b-216">Элементы пространства имен не нужно иметь отступ.</span><span class="sxs-lookup"><span data-stu-id="0b01b-216">Namespace elements do not have to be indented.</span></span>

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

### <a name="formatting-object-expressions-and-interfaces"></a><span data-ttu-id="0b01b-217">Форматирование выражения объектов и интерфейсов</span><span class="sxs-lookup"><span data-stu-id="0b01b-217">Formatting object expressions and interfaces</span></span>

<span data-ttu-id="0b01b-218">Выражения объекта и интерфейсы должны быть выровнены с таким же образом `member` отступ после 4 пробела.</span><span class="sxs-lookup"><span data-stu-id="0b01b-218">Object expressions and interfaces should be aligned in the same way with `member` being indented after 4 spaces.</span></span>

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s : String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-whitespace-in-expressions"></a><span data-ttu-id="0b01b-219">Форматирование пробелов в выражениях</span><span class="sxs-lookup"><span data-stu-id="0b01b-219">Formatting whitespace in expressions</span></span>

<span data-ttu-id="0b01b-220">Избегайте лишних пробелов в выражениями языка F #.</span><span class="sxs-lookup"><span data-stu-id="0b01b-220">Avoid extraneous whitespace in F# expressions.</span></span>

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

<span data-ttu-id="0b01b-221">Именованные аргументы также не следует пространство вокруг `=`:</span><span class="sxs-lookup"><span data-stu-id="0b01b-221">Named arguments should also not have space surrounding the `=`:</span></span>

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```
