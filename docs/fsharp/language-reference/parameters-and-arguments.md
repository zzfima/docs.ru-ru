---
title: Параметры и аргументы
description: Узнайте о поддержке языка F-языка для определения параметров и передачи аргументов функциям, методам и свойствам.
ms.date: 12/04/2019
ms.openlocfilehash: b234ef939128e7cf09d35f9580d4d5010d7dc639
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401055"
---
# <a name="parameters-and-arguments"></a><span data-ttu-id="0c187-103">Параметры и аргументы</span><span class="sxs-lookup"><span data-stu-id="0c187-103">Parameters and Arguments</span></span>

<span data-ttu-id="0c187-104">Эта тема описывает языковую поддержку для определения параметров и передачи аргументов функциям, методам и свойствам.</span><span class="sxs-lookup"><span data-stu-id="0c187-104">This topic describes language support for defining parameters and passing arguments to functions, methods, and properties.</span></span> <span data-ttu-id="0c187-105">Она включает в себя информацию о том, как пройти по ссылке, и как определить и использовать методы, которые могут принимать переменное количество аргументов.</span><span class="sxs-lookup"><span data-stu-id="0c187-105">It includes information about how to pass by reference, and how to define and use methods that can take a variable number of arguments.</span></span>

## <a name="parameters-and-arguments"></a><span data-ttu-id="0c187-106">Параметры и аргументы</span><span class="sxs-lookup"><span data-stu-id="0c187-106">Parameters and Arguments</span></span>

<span data-ttu-id="0c187-107">*Параметр* термина используется для описания имен значений, которые должны быть предоставлены.</span><span class="sxs-lookup"><span data-stu-id="0c187-107">The term *parameter* is used to describe the names for values that are expected to be supplied.</span></span> <span data-ttu-id="0c187-108">Термин *аргумент* используется для значений, предусмотренных для каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="0c187-108">The term *argument* is used for the values provided for each parameter.</span></span>

<span data-ttu-id="0c187-109">Параметры могут быть указаны в tuple или карри форме, или в некоторой комбинации из двух.</span><span class="sxs-lookup"><span data-stu-id="0c187-109">Parameters can be specified in tuple or curried form, or in some combination of the two.</span></span> <span data-ttu-id="0c187-110">Вы можете передавать аргументы, используя явное имя параметра.</span><span class="sxs-lookup"><span data-stu-id="0c187-110">You can pass arguments by using an explicit parameter name.</span></span> <span data-ttu-id="0c187-111">Параметры методов могут быть определены как факультативные и учитываются значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0c187-111">Parameters of methods can be specified as optional and given a default value.</span></span>

## <a name="parameter-patterns"></a><span data-ttu-id="0c187-112">Шаблоны параметров</span><span class="sxs-lookup"><span data-stu-id="0c187-112">Parameter Patterns</span></span>

<span data-ttu-id="0c187-113">Параметры, поставляемые в функции и методы, в целом представляют узоры, разделенные пробелами.</span><span class="sxs-lookup"><span data-stu-id="0c187-113">Parameters supplied to functions and methods are, in general, patterns separated by spaces.</span></span> <span data-ttu-id="0c187-114">Это означает, что в принципе любой из шаблонов, описанных в [выражениях соответствия,](match-expressions.md) может быть использован в списке параметров для функции или члена.</span><span class="sxs-lookup"><span data-stu-id="0c187-114">This means that, in principle, any of the patterns described in [Match Expressions](match-expressions.md) can be used in a parameter list for a function or member.</span></span>

<span data-ttu-id="0c187-115">Методы обычно используют форму tuple проходя аргументы.</span><span class="sxs-lookup"><span data-stu-id="0c187-115">Methods usually use the tuple form of passing arguments.</span></span> <span data-ttu-id="0c187-116">Это обеспечивает более четкий результат с точки зрения других языков .NET, поскольку форма tuple соответствует способу передаваемых аргументов в методах .NET.</span><span class="sxs-lookup"><span data-stu-id="0c187-116">This achieves a clearer result from the perspective of other .NET languages because the tuple form matches the way arguments are passed in .NET methods.</span></span>

<span data-ttu-id="0c187-117">Форма карри чаще всего используется с функциями, созданными с помощью `let` переплетов.</span><span class="sxs-lookup"><span data-stu-id="0c187-117">The curried form is most often used with functions created by using `let` bindings.</span></span>

<span data-ttu-id="0c187-118">Следующие псевдокод показывает примеры tuple и карри аргументы.</span><span class="sxs-lookup"><span data-stu-id="0c187-118">The following pseudocode shows examples of tuple and curried arguments.</span></span>

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

<span data-ttu-id="0c187-119">Комбинированные формы возможны, когда некоторые аргументы находятся в tuples, а некоторые нет.</span><span class="sxs-lookup"><span data-stu-id="0c187-119">Combined forms are possible when some arguments are in tuples and some are not.</span></span>

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

<span data-ttu-id="0c187-120">Другие шаблоны также могут быть использованы в списках параметров, но если шаблон параметра не соответствует всем возможным входным моментам, может быть неполное совпадение во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="0c187-120">Other patterns can also be used in parameter lists, but if the parameter pattern does not match all possible inputs, there might be an incomplete match at run time.</span></span> <span data-ttu-id="0c187-121">Исключение `MatchFailureException` создается, когда значение аргумента не соответствует шаблонам, указанным в списке параметров.</span><span class="sxs-lookup"><span data-stu-id="0c187-121">The exception `MatchFailureException` is generated when the value of an argument does not match the patterns specified in the parameter list.</span></span> <span data-ttu-id="0c187-122">Компилятор выдает предупреждение, когда шаблон параметра позволяет неполные совпадения.</span><span class="sxs-lookup"><span data-stu-id="0c187-122">The compiler issues a warning when a parameter pattern allows for incomplete matches.</span></span> <span data-ttu-id="0c187-123">По крайней мере, один другой шаблон обычно полезен для списков параметров, и это шаблон подстановочных знаков.</span><span class="sxs-lookup"><span data-stu-id="0c187-123">At least one other pattern is commonly useful for parameter lists, and that is the wildcard pattern.</span></span> <span data-ttu-id="0c187-124">Шаблон подстановочных знаков используется в списке параметров, когда вы просто хотите игнорировать любые аргументы, которые поставляются.</span><span class="sxs-lookup"><span data-stu-id="0c187-124">You use the wildcard pattern in a parameter list when you simply want to ignore any arguments that are supplied.</span></span> <span data-ttu-id="0c187-125">Следующий код иллюстрирует использование шаблона подстановочных знаков в списке аргументов.</span><span class="sxs-lookup"><span data-stu-id="0c187-125">The following code illustrates the use of the wildcard pattern in an argument list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

<span data-ttu-id="0c187-126">Шаблон подстановочного знака может быть полезен всякий раз, когда вам не нужны аргументы, передаваемые, например, в основной точке входа в программу, когда вас не интересуют аргументы командной строки, которые обычно поставляются в виде массива строки, как в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="0c187-126">The wildcard pattern can be useful whenever you do not need the arguments passed in, such as in the main entry point to a program, when you are not interested in the command-line arguments that are normally supplied as a string array, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

<span data-ttu-id="0c187-127">Другими шаблонами, которые иногда используются в аргументах, являются `as` шаблон и идентификаторы, связанные с дискриминируемыми союзами и активными шаблонами.</span><span class="sxs-lookup"><span data-stu-id="0c187-127">Other patterns that are sometimes used in arguments are the `as` pattern, and identifier patterns associated with discriminated unions and active patterns.</span></span> <span data-ttu-id="0c187-128">Вы можете использовать шаблон единого дискриминируемого союза следующим образом.</span><span class="sxs-lookup"><span data-stu-id="0c187-128">You can use the single-case discriminated union pattern as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

<span data-ttu-id="0c187-129">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="0c187-129">The output is as follows.</span></span>

```console
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

<span data-ttu-id="0c187-130">Активные шаблоны могут быть полезны в качестве параметров, например, при преобразовании аргумента в желаемый формат, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="0c187-130">Active patterns can be useful as parameters, for example, when transforming an argument into a desired format, as in the following example:</span></span>

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

<span data-ttu-id="0c187-131">Шаблон можно `as` использовать для хранения совмещенных значений в качестве локального значения, как показано в следующей строке кода.</span><span class="sxs-lookup"><span data-stu-id="0c187-131">You can use the `as` pattern to store a matched value as a local value, as is shown in the following line of code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

<span data-ttu-id="0c187-132">Другой шаблон, который используется время от времени является функция, которая оставляет последний аргумент безымянным, предоставляя, как тело функции, выражение lambda, который сразу же выполняет шаблон совпадают на неявном аргументе.</span><span class="sxs-lookup"><span data-stu-id="0c187-132">Another pattern that is used occasionally is a function that leaves the last argument unnamed by providing, as the body of the function, a lambda expression that immediately performs a pattern match on the implicit argument.</span></span> <span data-ttu-id="0c187-133">Примером этого является следующая строка кода.</span><span class="sxs-lookup"><span data-stu-id="0c187-133">An example of this is the following line of code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

<span data-ttu-id="0c187-134">Этот код определяет функцию, которая принимает `true` общий список `false` и возвращается, если список пуст, и в противном случае.</span><span class="sxs-lookup"><span data-stu-id="0c187-134">This code defines a function that takes a generic list and returns `true` if the list is empty, and `false` otherwise.</span></span> <span data-ttu-id="0c187-135">Использование таких методов может сделать код более трудным для чтения.</span><span class="sxs-lookup"><span data-stu-id="0c187-135">The use of such techniques can make code more difficult to read.</span></span>

<span data-ttu-id="0c187-136">Иногда шаблоны, связанные с неполными совпадениями, полезны, например, если вы знаете, что в списках программы есть только три элемента, можно использовать шаблон, подобный следующему в списке параметров.</span><span class="sxs-lookup"><span data-stu-id="0c187-136">Occasionally, patterns that involve incomplete matches are useful, for example, if you know that the lists in your program have only three elements, you might use a pattern like the following in a parameter list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

<span data-ttu-id="0c187-137">Использование шаблонов, которые имеют неполные совпадения лучше всего зарезервированы для быстрого прототипирования и других временных применений.</span><span class="sxs-lookup"><span data-stu-id="0c187-137">The use of patterns that have incomplete matches is best reserved for quick prototyping and other temporary uses.</span></span> <span data-ttu-id="0c187-138">Компилятор выдаст предупреждение для такого кода.</span><span class="sxs-lookup"><span data-stu-id="0c187-138">The compiler will issue a warning for such code.</span></span> <span data-ttu-id="0c187-139">Такие закономерности не могут охватывать общий случай всех возможных входных данных и поэтому не подходят для компонентных AIS.</span><span class="sxs-lookup"><span data-stu-id="0c187-139">Such patterns cannot cover the general case of all possible inputs and therefore are not suitable for component APIs.</span></span>

## <a name="named-arguments"></a><span data-ttu-id="0c187-140">Именованные аргументы</span><span class="sxs-lookup"><span data-stu-id="0c187-140">Named Arguments</span></span>

<span data-ttu-id="0c187-141">Аргументы для методов могут быть указаны по позиции в списке аргументов, разделенных запятой, или они могут быть переданы методу явно, предоставив имя, за которым следует равный знак и значение, которое должно быть передано.</span><span class="sxs-lookup"><span data-stu-id="0c187-141">Arguments for methods can be specified by position in a comma-separated argument list, or they can be passed to a method explicitly by providing the name, followed by an equal sign and the value to be passed in.</span></span> <span data-ttu-id="0c187-142">Если указано, указывая имя, они могут отображаться в другом порядке, чем в декларации.</span><span class="sxs-lookup"><span data-stu-id="0c187-142">If specified by providing the name, they can appear in a different order from that used in the declaration.</span></span>

<span data-ttu-id="0c187-143">Названные аргументы могут сделать код более читаемым и более адаптируемым к определенным типам изменений в API, таким как переупорядочение параметров метода.</span><span class="sxs-lookup"><span data-stu-id="0c187-143">Named arguments can make code more readable and more adaptable to certain types of changes in the API, such as a reordering of method parameters.</span></span>

<span data-ttu-id="0c187-144">Именованные аргументы допускаются `let`только для методов, а не для связанных функций, значений функций или выражений лямбды.</span><span class="sxs-lookup"><span data-stu-id="0c187-144">Named arguments are allowed only for methods, not for `let`-bound functions, function values, or lambda expressions.</span></span>

<span data-ttu-id="0c187-145">Следующий пример кода демонстрирует использование названных аргументов.</span><span class="sxs-lookup"><span data-stu-id="0c187-145">The following code example demonstrates the use of named arguments.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

<span data-ttu-id="0c187-146">При вызове к конструктору класса можно установить значения свойств класса, используя синтаксис, аналогичный тому, который используется из названных аргументов.</span><span class="sxs-lookup"><span data-stu-id="0c187-146">In a call to a class constructor, you can set the values of properties of the class by using a syntax similar to that of named arguments.</span></span> <span data-ttu-id="0c187-147">Следующий пример показывает этот синтаксис.</span><span class="sxs-lookup"><span data-stu-id="0c187-147">The following example shows this syntax.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="0c187-148">Для получения дополнительной [информации, см.](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05)</span><span class="sxs-lookup"><span data-stu-id="0c187-148">For more information, see [Constructors (F#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).</span></span>

## <a name="optional-parameters"></a><span data-ttu-id="0c187-149">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="0c187-149">Optional Parameters</span></span>

<span data-ttu-id="0c187-150">Можно указать дополнительный параметр для метода, используя вопросительный знак перед именем параметра.</span><span class="sxs-lookup"><span data-stu-id="0c187-150">You can specify an optional parameter for a method by using a question mark in front of the parameter name.</span></span> <span data-ttu-id="0c187-151">Дополнительные параметры интерпретируются как тип опции F, так что вы можете запрашивать их `match` в `Some` `None`обычном порядке, что типы опций запрашиваются, с помощью выражения с и .</span><span class="sxs-lookup"><span data-stu-id="0c187-151">Optional parameters are interpreted as the F# option type, so you can query them in the regular way that option types are queried, by using a `match` expression with `Some` and `None`.</span></span> <span data-ttu-id="0c187-152">Дополнительные параметры допускаются только на членах, `let` а не на функциях, созданных с помощью привязок.</span><span class="sxs-lookup"><span data-stu-id="0c187-152">Optional parameters are permitted only on members, not on functions created by using `let` bindings.</span></span>

<span data-ttu-id="0c187-153">Вы можете передать существующие дополнительные значения методу `?arg=Some(3)` `?arg=arg`по имени параметра, например `?arg=None` или .</span><span class="sxs-lookup"><span data-stu-id="0c187-153">You can pass existing optional values to method by parameter name, such as `?arg=None` or `?arg=Some(3)` or `?arg=arg`.</span></span> <span data-ttu-id="0c187-154">Это может быть полезно при создании метода, который передает дополнительные аргументы другому методу.</span><span class="sxs-lookup"><span data-stu-id="0c187-154">This can be useful when building a method that passes optional arguments to another method.</span></span>

<span data-ttu-id="0c187-155">Вы также можете `defaultArg`использовать функцию, которая устанавливает значение по умолчанию факультативного аргумента.</span><span class="sxs-lookup"><span data-stu-id="0c187-155">You can also use a function `defaultArg`, which sets a default value of an optional argument.</span></span> <span data-ttu-id="0c187-156">Функция `defaultArg` принимает дополнительный параметр в качестве первого аргумента, а значение по умолчанию — второй.</span><span class="sxs-lookup"><span data-stu-id="0c187-156">The `defaultArg` function takes the optional parameter as the first argument and the default value as the second.</span></span>

<span data-ttu-id="0c187-157">Следующий пример иллюстрирует использование факультативных параметров.</span><span class="sxs-lookup"><span data-stu-id="0c187-157">The following example illustrates the use of optional parameters.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

<span data-ttu-id="0c187-158">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="0c187-158">The output is as follows.</span></span>

```console
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
```

<span data-ttu-id="0c187-159">Для целей C и Visual Basic interop вы `[<Optional; DefaultParameterValue<(...)>]` можете использовать атрибуты в F, так что абоненты будут рассматривать аргумент как необязательный.</span><span class="sxs-lookup"><span data-stu-id="0c187-159">For the purposes of C# and Visual Basic interop you can use the attributes `[<Optional; DefaultParameterValue<(...)>]` in F#, so that callers will see an argument as optional.</span></span> <span data-ttu-id="0c187-160">Это эквивалентно определению аргумента как факультативного в C, как и в `MyMethod(int i = 3)`.</span><span class="sxs-lookup"><span data-stu-id="0c187-160">This is equivalent to defining the argument as optional in C# as in `MyMethod(int i = 3)`.</span></span>

```fsharp
open System
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue("Hello world")>] message) =
        printfn "%s" message
```

<span data-ttu-id="0c187-161">Можно также указать новый объект в качестве значения параметра по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0c187-161">You can also specify a new object as a default parameter value.</span></span> <span data-ttu-id="0c187-162">Например, `Foo` вместо этого у `CancellationToken` участника может быть дополнительный в качестве ввода:</span><span class="sxs-lookup"><span data-stu-id="0c187-162">For example, the `Foo` member could have an optional `CancellationToken` as input instead:</span></span>

```fsharp
open System.Threading
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue(CancellationToken())>] ct: CancellationToken) =
        printfn "%A" ct
```

<span data-ttu-id="0c187-163">Значение, приведенное `DefaultParameterValue` в качестве аргумента, должно соответствовать типу параметра.</span><span class="sxs-lookup"><span data-stu-id="0c187-163">The value given as argument to `DefaultParameterValue` must match the type of the parameter.</span></span> <span data-ttu-id="0c187-164">Например, не допускается следующее:</span><span class="sxs-lookup"><span data-stu-id="0c187-164">For example, the following is not allowed:</span></span>

```fsharp
type C =
    static member Wrong([<Optional; DefaultParameterValue("string")>] i:int) = ()
```

<span data-ttu-id="0c187-165">В этом случае компилятор генерирует предупреждение и полностью проигнорирует оба атрибута.</span><span class="sxs-lookup"><span data-stu-id="0c187-165">In this case, the compiler generates a warning and will ignore both attributes altogether.</span></span> <span data-ttu-id="0c187-166">Обратите внимание, `null` что значение по умолчанию должно быть аннотировано к типу, так `[<Optional; DefaultParameterValue(null:obj)>] o:obj`как в противном случае компилятор вычеркивает неправильный тип, т.е.</span><span class="sxs-lookup"><span data-stu-id="0c187-166">Note that the default value `null` needs to be type-annotated, as otherwise the compiler infers the wrong type, i.e. `[<Optional; DefaultParameterValue(null:obj)>] o:obj`.</span></span>

## <a name="passing-by-reference"></a><span data-ttu-id="0c187-167">Проходя мимо Справки</span><span class="sxs-lookup"><span data-stu-id="0c187-167">Passing by Reference</span></span>

<span data-ttu-id="0c187-168">Прохождение значения F-значения по ссылке включает в себя [byrefs](byrefs.md), которые управляются типами указателей.</span><span class="sxs-lookup"><span data-stu-id="0c187-168">Passing an F# value by reference involves [byrefs](byrefs.md), which are managed pointer types.</span></span> <span data-ttu-id="0c187-169">Руководство по типу для использования заключается в следующем:</span><span class="sxs-lookup"><span data-stu-id="0c187-169">Guidance for which type to use is as follows:</span></span>

- <span data-ttu-id="0c187-170">Используйте, `inref<'T>` если вам нужно только прочитать указатель.</span><span class="sxs-lookup"><span data-stu-id="0c187-170">Use `inref<'T>` if you only need to read the pointer.</span></span>
- <span data-ttu-id="0c187-171">Используйте, `outref<'T>` если вам нужно только написать в указатель.</span><span class="sxs-lookup"><span data-stu-id="0c187-171">Use `outref<'T>` if you only need to write to the pointer.</span></span>
- <span data-ttu-id="0c187-172">Используйте, `byref<'T>` если вам нужно как читать, так и писать в указатель.</span><span class="sxs-lookup"><span data-stu-id="0c187-172">Use `byref<'T>` if you need to both read from and write to the pointer.</span></span>

```fsharp
let example1 (x: inref<int>) = printfn "It's %d" x

let example2 (x: outref<int>) = x <- x + 1

let example3 (x: byref<int>) =
    printfn "It'd %d" x
    x <- x + 1

let test () =
    // No need to make it mutable, since it's read-only
    let x = 1
    example1 &x

    // Needs to be mutable, since we write to it
    let mutable y = 2
    example2 &y
    example3 &y // Now 'y' is 3
```

<span data-ttu-id="0c187-173">Поскольку параметр является указателем и значение изменяется, любые изменения значения сохраняются после выполнения функции.</span><span class="sxs-lookup"><span data-stu-id="0c187-173">Because the parameter is a pointer and the value is mutable, any changes to the value are retained after the execution of the function.</span></span>

<span data-ttu-id="0c187-174">Для хранения любых `out` параметров в методах библиотеки .NET можно использовать tuple в качестве значения возврата.</span><span class="sxs-lookup"><span data-stu-id="0c187-174">You can use a tuple as a return value to store any `out` parameters in .NET library methods.</span></span> <span data-ttu-id="0c187-175">Кроме того, можно `out` рассматривать параметр как `byref` параметр.</span><span class="sxs-lookup"><span data-stu-id="0c187-175">Alternatively, you can treat the `out` parameter as a `byref` parameter.</span></span> <span data-ttu-id="0c187-176">Следующий пример кода иллюстрирует оба способа.</span><span class="sxs-lookup"><span data-stu-id="0c187-176">The following code example illustrates both ways.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a><span data-ttu-id="0c187-177">Массивы параметров</span><span class="sxs-lookup"><span data-stu-id="0c187-177">Parameter Arrays</span></span>

<span data-ttu-id="0c187-178">Иногда необходимо определить функцию, которая принимает произвольное количество параметров неоднородного типа.</span><span class="sxs-lookup"><span data-stu-id="0c187-178">Occasionally it is necessary to define a function that takes an arbitrary number of parameters of heterogeneous type.</span></span> <span data-ttu-id="0c187-179">Было бы нецелесообразно создавать все возможные перегруженные методы для учета всех типов, которые могут быть использованы.</span><span class="sxs-lookup"><span data-stu-id="0c187-179">It would not be practical to create all the possible overloaded methods to account for all the types that could be used.</span></span> <span data-ttu-id="0c187-180">Реализации .NET обеспечивают поддержку таких методов через функцию параметра.</span><span class="sxs-lookup"><span data-stu-id="0c187-180">The .NET implementations provide support for such methods through the parameter array feature.</span></span> <span data-ttu-id="0c187-181">Метод, который принимает массив параметров в своей подписи, может быть предоставлен с произвольным числом параметров.</span><span class="sxs-lookup"><span data-stu-id="0c187-181">A method that takes a parameter array in its signature can be provided with an arbitrary number of parameters.</span></span> <span data-ttu-id="0c187-182">Параметры помещаются в массив.</span><span class="sxs-lookup"><span data-stu-id="0c187-182">The parameters are put into an array.</span></span> <span data-ttu-id="0c187-183">Тип элементов массива определяет типы параметров, которые могут быть переданы функции.</span><span class="sxs-lookup"><span data-stu-id="0c187-183">The type of the array elements determines the parameter types that can be passed to the function.</span></span> <span data-ttu-id="0c187-184">Если вы определяете `System.Object` массив параметров с типом элемента, то клиентский код может передавать значения любого типа.</span><span class="sxs-lookup"><span data-stu-id="0c187-184">If you define the parameter array with `System.Object` as the element type, then client code can pass values of any type.</span></span>

<span data-ttu-id="0c187-185">В F-области параметры могут быть определены только в методах.</span><span class="sxs-lookup"><span data-stu-id="0c187-185">In F#, parameter arrays can only be defined in methods.</span></span> <span data-ttu-id="0c187-186">Они не могут быть использованы в автономных функциях или функциях, которые определяются в модулях.</span><span class="sxs-lookup"><span data-stu-id="0c187-186">They cannot be used in standalone functions or functions that are defined in modules.</span></span>

<span data-ttu-id="0c187-187">Вы определяете массив параметров с помощью атрибута. `ParamArray`</span><span class="sxs-lookup"><span data-stu-id="0c187-187">You define a parameter array by using the `ParamArray` attribute.</span></span> <span data-ttu-id="0c187-188">Атрибут `ParamArray` может быть применен только к последнему параметру.</span><span class="sxs-lookup"><span data-stu-id="0c187-188">The `ParamArray` attribute can only be applied to the last parameter.</span></span>

<span data-ttu-id="0c187-189">Следующий код иллюстрирует как вызов метода .NET, который принимает массив параметров, так и определение типа в F-, который имеет метод, который принимает массив параметров.</span><span class="sxs-lookup"><span data-stu-id="0c187-189">The following code illustrates both calling a .NET method that takes a parameter array and the definition of a type in F# that has a method that takes a parameter array.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

<span data-ttu-id="0c187-190">При запуске в проекте вывод предыдущего кода:</span><span class="sxs-lookup"><span data-stu-id="0c187-190">When run in a project, the output of the previous code is as follows:</span></span>

```console
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a><span data-ttu-id="0c187-191">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0c187-191">See also</span></span>

- [<span data-ttu-id="0c187-192">Членов</span><span class="sxs-lookup"><span data-stu-id="0c187-192">Members</span></span>](./members/index.md)
