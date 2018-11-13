---
title: Введение в функциональное программирование на F#
description: Изучение основ функционального программирования в F#.
ms.date: 10/29/2018
ms.openlocfilehash: d4a9bb0cd826b41aca96e12e2bcb5aab80c18eb4
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2018
ms.locfileid: "25724481"
---
# <a name="introduction-to-functional-programming-in-f"></a><span data-ttu-id="b5c33-103">Введение в функциональное программирование на F#</span><span class="sxs-lookup"><span data-stu-id="b5c33-103">Introduction to Functional Programming in F#</span></span> #

<span data-ttu-id="b5c33-104">Функциональное программирование является стилем, который делается упор на использование функций и постоянные данные.</span><span class="sxs-lookup"><span data-stu-id="b5c33-104">Functional programming is a style of programming that emphasizes the use of functions and immutable data.</span></span> <span data-ttu-id="b5c33-105">Типизированный функциональное программирование является функционального программирования в сочетании с статические типы, такие как с F#.</span><span class="sxs-lookup"><span data-stu-id="b5c33-105">Typed functional programming is when functional programming is combined with static types, such as with F#.</span></span> <span data-ttu-id="b5c33-106">Как правило в функциональном программировании выделены следующие понятия:</span><span class="sxs-lookup"><span data-stu-id="b5c33-106">In general, the following concepts are emphasized in functional programming:</span></span>

* <span data-ttu-id="b5c33-107">Функции как основными конструкциями, которые можно использовать</span><span class="sxs-lookup"><span data-stu-id="b5c33-107">Functions as the primary constructs you use</span></span>
* <span data-ttu-id="b5c33-108">Выражения вместо инструкций</span><span class="sxs-lookup"><span data-stu-id="b5c33-108">Expressions instead of statements</span></span>
* <span data-ttu-id="b5c33-109">Постоянные значения, переменные</span><span class="sxs-lookup"><span data-stu-id="b5c33-109">Immutable values over variables</span></span>
* <span data-ttu-id="b5c33-110">Декларативную модель программирования через императивного программирования</span><span class="sxs-lookup"><span data-stu-id="b5c33-110">Declarative programming over imperative programming</span></span>

<span data-ttu-id="b5c33-111">В этой серии, на них рассматриваются концепции и шаблоны в функционального программирования, используя F#.</span><span class="sxs-lookup"><span data-stu-id="b5c33-111">Throughout this series, you'll explore concepts and patterns in functional programming using F#.</span></span> <span data-ttu-id="b5c33-112">Кроме того, вы узнаете о некоторых F# слишком.</span><span class="sxs-lookup"><span data-stu-id="b5c33-112">Along the way, you'll learn some F# too.</span></span>

## <a name="terminology"></a><span data-ttu-id="b5c33-113">Терминология</span><span class="sxs-lookup"><span data-stu-id="b5c33-113">Terminology</span></span>

<span data-ttu-id="b5c33-114">Функциональное программирование, как и других парадигм программирования, в состав словаря, который со временем необходимо будет узнать.</span><span class="sxs-lookup"><span data-stu-id="b5c33-114">Functional programming, like other programming paradigms, comes with a vocabulary that you will eventually need to learn.</span></span> <span data-ttu-id="b5c33-115">Ниже приведены некоторые распространенные термины, вы увидите все время.</span><span class="sxs-lookup"><span data-stu-id="b5c33-115">Here are some common terms you'll see all of the time:</span></span>

* <span data-ttu-id="b5c33-116">**Функция** -функция представляет собой конструкцию, будет преобразовано в выходное при заданном входном.</span><span class="sxs-lookup"><span data-stu-id="b5c33-116">**Function** - A function is a construct that will produce an output when given an input.</span></span> <span data-ttu-id="b5c33-117">Более формально, его _сопоставляет_ набор из одного элемента к другому набору.</span><span class="sxs-lookup"><span data-stu-id="b5c33-117">More formally, it _maps_ an item from one set to another set.</span></span> <span data-ttu-id="b5c33-118">Этот формализм она поднимается в конкретных во многих отношениях, особенно при использовании функции, которые работают с коллекциями данных.</span><span class="sxs-lookup"><span data-stu-id="b5c33-118">This formalism is lifted into the concrete in many ways, especially when using functions that operate on collections of data.</span></span> <span data-ttu-id="b5c33-119">Это наиболее основных (и важный) концепции функционального программирования.</span><span class="sxs-lookup"><span data-stu-id="b5c33-119">It is the most basic (and important) concept in functional programming.</span></span> 
* <span data-ttu-id="b5c33-120">**Выражение** -выражение — это конструкция, в коде, который создает значение.</span><span class="sxs-lookup"><span data-stu-id="b5c33-120">**Expression** - An expression is a construct in code that produces a value.</span></span> <span data-ttu-id="b5c33-121">В F#, это значение должно быть привязаны или явным образом игнорировать.</span><span class="sxs-lookup"><span data-stu-id="b5c33-121">In F#, this value must be bound or explicitly ignored.</span></span> <span data-ttu-id="b5c33-122">Выражения могут быть просто заменены вызов функции.</span><span class="sxs-lookup"><span data-stu-id="b5c33-122">An expression can be trivially replaced by a function call.</span></span>
* <span data-ttu-id="b5c33-123">**Чистота** -чистоты является свойством функции, таким образом, что его возвращаемое значение всегда является одинаковым для те же аргументы, и что его вычисление не имеет побочных эффектов.</span><span class="sxs-lookup"><span data-stu-id="b5c33-123">**Purity** - Purity is a property of a function such that its return value is always the same for the same arguments, and that its evaluation has no side effects.</span></span> <span data-ttu-id="b5c33-124">Чистая функция полностью зависит от своих аргументов.</span><span class="sxs-lookup"><span data-stu-id="b5c33-124">A pure function depends entirely on its arguments.</span></span>
* <span data-ttu-id="b5c33-125">**Ссылочной прозрачности** -ссылочной прозрачности является свойством выражений таким образом, что они могут быть заменены свои выходные данные без влияния на поведение программы.</span><span class="sxs-lookup"><span data-stu-id="b5c33-125">**Referential Transparency** - Referential Transparency is a property of expressions such that they can be replaced with their output without affecting a program's behavior.</span></span>
* <span data-ttu-id="b5c33-126">**Неизменность** -постоянство означает, что значение не может быть изменен на месте.</span><span class="sxs-lookup"><span data-stu-id="b5c33-126">**Immutability** - Immutability means that a value cannot be changed in-place.</span></span> <span data-ttu-id="b5c33-127">Это отличает их от переменных, которые можно изменить на месте.</span><span class="sxs-lookup"><span data-stu-id="b5c33-127">This is in contrast with variables, which can change in place.</span></span>

## <a name="examples"></a><span data-ttu-id="b5c33-128">Примеры</span><span class="sxs-lookup"><span data-stu-id="b5c33-128">Examples</span></span>

<span data-ttu-id="b5c33-129">В следующих примерах демонстрируется следующих базовых понятиях.</span><span class="sxs-lookup"><span data-stu-id="b5c33-129">The following examples demonstrate these core concepts.</span></span>

### <a name="functions"></a><span data-ttu-id="b5c33-130">Функции</span><span class="sxs-lookup"><span data-stu-id="b5c33-130">Functions</span></span>

<span data-ttu-id="b5c33-131">Наиболее распространенные и основные конструкции функционального программирования является функция.</span><span class="sxs-lookup"><span data-stu-id="b5c33-131">The most common and fundamental construct in functional programming is the function.</span></span> <span data-ttu-id="b5c33-132">Ниже приведен простой функции, которая добавляет 1 к целое число.</span><span class="sxs-lookup"><span data-stu-id="b5c33-132">Here's a simple function that adds 1 to an integer:</span></span>

```fsharp
let addOne x = x + 1
```

<span data-ttu-id="b5c33-133">Сигнатура типа выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b5c33-133">Its type signature is as follows:</span></span>

```fsharp
val addOne: x:int -> int
```

<span data-ttu-id="b5c33-134">Подпись может быть прочитан как, «`addOne` принимает `int` с именем `x` и создаст `int`«.</span><span class="sxs-lookup"><span data-stu-id="b5c33-134">The signature can be read as, "`addOne` accepts an `int` named `x` and will produce an `int`".</span></span> <span data-ttu-id="b5c33-135">Более формально `addOne` — _сопоставление_ значение из набора целых чисел в набор целых чисел.</span><span class="sxs-lookup"><span data-stu-id="b5c33-135">More formally, `addOne` is _mapping_ a value from the set of integers to the set of integers.</span></span> <span data-ttu-id="b5c33-136">`->` Токен указывает на это сопоставление.</span><span class="sxs-lookup"><span data-stu-id="b5c33-136">The `->` token signifies this mapping.</span></span> <span data-ttu-id="b5c33-137">В F#, обычно можно посмотреть на сигнатуру функции, чтобы понять, что она делает.</span><span class="sxs-lookup"><span data-stu-id="b5c33-137">In F#, you can usually look at the function signature to get a sense for what it does.</span></span>

<span data-ttu-id="b5c33-138">Таким образом, почему важен подпись?</span><span class="sxs-lookup"><span data-stu-id="b5c33-138">So, why is the signature important?</span></span> <span data-ttu-id="b5c33-139">В типизированных функционального программирования, реализации функции меньше часто важным, чем фактический тип подписи!</span><span class="sxs-lookup"><span data-stu-id="b5c33-139">In typed functional programming, the implementation of a function is often less important than the actual type signature!</span></span> <span data-ttu-id="b5c33-140">Тот факт, `addOne` добавляет значение в целое число 1 интересен во время выполнения, но при создании программы, тот факт, что он принимает и возвращает `int` является что информирует о том, как его можно использовать эту функцию.</span><span class="sxs-lookup"><span data-stu-id="b5c33-140">The fact that `addOne` adds the value 1 to an integer is interesting at runtime, but when you are constructing a program, the fact that it accepts and returns an `int` is what informs how you will actually use this function.</span></span> <span data-ttu-id="b5c33-141">Кроме того, как только эта функция правильно (по отношению к его сигнатура типа), диагностики проблем можно сделать только в теле `addOne` функции.</span><span class="sxs-lookup"><span data-stu-id="b5c33-141">Furthermore, once you use this function correctly (with respect to its type signature), diagnosing any problems can be done only within the body of the `addOne` function.</span></span> <span data-ttu-id="b5c33-142">Это движущая сила типизированный функционального программирования.</span><span class="sxs-lookup"><span data-stu-id="b5c33-142">This is the impetus behind typed functional programming.</span></span>

### <a name="expressions"></a><span data-ttu-id="b5c33-143">Выражения</span><span class="sxs-lookup"><span data-stu-id="b5c33-143">Expressions</span></span>

<span data-ttu-id="b5c33-144">Выражения — это конструкции, которые возвращают значения.</span><span class="sxs-lookup"><span data-stu-id="b5c33-144">Expressions are constructs that evaluate to a value.</span></span> <span data-ttu-id="b5c33-145">В отличие от инструкции, которые выполняют действия, выражения можно рассматривать выполняет действие, которое возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="b5c33-145">In contrast to statements, which perform an action, expressions can be thought of performing an action that gives back a value.</span></span> <span data-ttu-id="b5c33-146">Выражения используются почти всегда пользу инструкций в функциональном программировании.</span><span class="sxs-lookup"><span data-stu-id="b5c33-146">Expressions are almost always used in favor of statements in functional programming.</span></span>

<span data-ttu-id="b5c33-147">Рассмотрим функцию предыдущих `addOne`.</span><span class="sxs-lookup"><span data-stu-id="b5c33-147">Consider the previous function, `addOne`.</span></span> <span data-ttu-id="b5c33-148">Тело `addOne` — это выражение:</span><span class="sxs-lookup"><span data-stu-id="b5c33-148">The body of `addOne` is an expression:</span></span>

```fsharp
// 'x + 1' is an expression!
let addOne x = x + 1
```

<span data-ttu-id="b5c33-149">Она является результатом этого выражения, который определяет тип результата `addOne` функции.</span><span class="sxs-lookup"><span data-stu-id="b5c33-149">It is the result of this expression that defines the result type of the `addOne` function.</span></span> <span data-ttu-id="b5c33-150">Например, выражение, которое представляет эта функция может измениться на быть другого типа, например `string`:</span><span class="sxs-lookup"><span data-stu-id="b5c33-150">For example, the expression that makes up this function could be changed to be a different type, such as a `string`:</span></span>

```fsharp
let addOne x = x.ToString() + "1"
```

<span data-ttu-id="b5c33-151">Подпись функции теперь является:</span><span class="sxs-lookup"><span data-stu-id="b5c33-151">The signature of the function is now:</span></span>

```fsharp
val addOne: x:'a -> string
```

<span data-ttu-id="b5c33-152">С момента любого типа в F# может иметь `ToString()` для нее тип `x` стала универсального (вызывается [Автоматическое обобщение](../language-reference/generics/automatic-generalization.md)), и результирующим типом является `string`.</span><span class="sxs-lookup"><span data-stu-id="b5c33-152">Since any type in F# can have `ToString()` called on it, the type of `x` has been made generic (called [Automatic Generalization](../language-reference/generics/automatic-generalization.md)), and the resultant type is a `string`.</span></span>

<span data-ttu-id="b5c33-153">Выражения не только тела функции.</span><span class="sxs-lookup"><span data-stu-id="b5c33-153">Expressions are not just the bodies of functions.</span></span> <span data-ttu-id="b5c33-154">Может иметь выражений, возвращающих значение, которое можно использовать в другом месте.</span><span class="sxs-lookup"><span data-stu-id="b5c33-154">You can have expressions that produce a value you use elsewhere.</span></span> <span data-ttu-id="b5c33-155">Он общий `if`:</span><span class="sxs-lookup"><span data-stu-id="b5c33-155">A common one is `if`:</span></span>

```fsharp
// Checks if 'x' is odd by using the mod operator
let isOdd x = x % 2 <> 0

let addOneIfOdd input =
    let result =
        if isOdd input then
            input + 1
        else
            input

    result
```

<span data-ttu-id="b5c33-156">`if` Выражение создает значение с именем `result`.</span><span class="sxs-lookup"><span data-stu-id="b5c33-156">The `if` expression produces a value called `result`.</span></span> <span data-ttu-id="b5c33-157">Обратите внимание, что можно опустить `result` полностью, что делает `if` выражение текст из `addOneIfOdd` функции.</span><span class="sxs-lookup"><span data-stu-id="b5c33-157">Note that you could omit `result` entirely, making the `if` expression the body of the `addOneIfOdd` function.</span></span> <span data-ttu-id="b5c33-158">Следует помнить о выражениях ключевой момент заключается в том, что они создают значение.</span><span class="sxs-lookup"><span data-stu-id="b5c33-158">The key thing to remember about expressions is that they produce a value.</span></span>

<span data-ttu-id="b5c33-159">Есть особый тип `unit`, используемый при нет ничего для возврата.</span><span class="sxs-lookup"><span data-stu-id="b5c33-159">There is a special type, `unit`, that is used when there is nothing to return.</span></span> <span data-ttu-id="b5c33-160">Например рассмотрим Эта простая функция:</span><span class="sxs-lookup"><span data-stu-id="b5c33-160">For example, consider this simple function:</span></span>

```fsharp
let printString (str: string) =
    printfn "String is: %s" s
```

<span data-ttu-id="b5c33-161">Подпись выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b5c33-161">The signature looks like this:</span></span>

```fsharp
val printString: str:string -> unit
```

<span data-ttu-id="b5c33-162">`unit` Тип указывает, что фактическое значение не возвращается.</span><span class="sxs-lookup"><span data-stu-id="b5c33-162">The `unit` type indicates that there is no actual value being returned.</span></span> <span data-ttu-id="b5c33-163">Это полезно при наличии подпрограмму, которая должна «рабочая», несмотря на наличие значения, которое можно вернуть в результате этой работы.</span><span class="sxs-lookup"><span data-stu-id="b5c33-163">This is useful when you have a routine that must "do work" despite having no value to return as a result of that work.</span></span>

<span data-ttu-id="b5c33-164">Это существенно отличаются от императивного программирования, где эквивалент `if` конструкция является оператором, и создание значения часто выполняется с помощью изменения переменных.</span><span class="sxs-lookup"><span data-stu-id="b5c33-164">This is in sharp contrast to imperative programming, where the equivalent `if` construct is a statement, and producing values is often done with mutating variables.</span></span> <span data-ttu-id="b5c33-165">Например, в C#, код может быть написан следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b5c33-165">For example, in C#, the code might be written like this:</span></span>

```csharp
bool IsOdd(int x) => x % 2 != 0;

int AddOneIfOdd(int input)
{
    var result = input;

    if (IsOdd(input))
    {
        result = input + 1;
    }

    return result;
}
```

<span data-ttu-id="b5c33-166">Следует отметить, что C# и других языков в стиле C поддерживают [троичное выражение](../../csharp/language-reference/operators/conditional-operator.md), что позволяет условного программирование на основе выражения.</span><span class="sxs-lookup"><span data-stu-id="b5c33-166">It's worth noting that C# and other C-style languages do support the [ternary expression](../../csharp/language-reference/operators/conditional-operator.md), which allows for expression-based conditional programming.</span></span>

<span data-ttu-id="b5c33-167">В функциональном программировании очень редко изменяемая значений с помощью инструкций.</span><span class="sxs-lookup"><span data-stu-id="b5c33-167">In functional programming, it is rare to mutate values with statements.</span></span> <span data-ttu-id="b5c33-168">Несмотря на то, что некоторые функциональные языки поддерживают операторы и изменений, обычно не использовать эти концепции в функциональном программировании.</span><span class="sxs-lookup"><span data-stu-id="b5c33-168">Although some functional languages support statements and mutation, it is not common to use these concepts in functional programming.</span></span>

### <a name="pure-functions"></a><span data-ttu-id="b5c33-169">Чистые функции</span><span class="sxs-lookup"><span data-stu-id="b5c33-169">Pure functions</span></span>

<span data-ttu-id="b5c33-170">Как упоминалось ранее, чистые функции являются функции, которые:</span><span class="sxs-lookup"><span data-stu-id="b5c33-170">As previously mentioned, pure functions are functions that:</span></span>

* <span data-ttu-id="b5c33-171">Всегда возвращают значение то же значение для того же входа.</span><span class="sxs-lookup"><span data-stu-id="b5c33-171">Always evaluate to the same value for the same input.</span></span>
* <span data-ttu-id="b5c33-172">Не имеют побочных эффектов.</span><span class="sxs-lookup"><span data-stu-id="b5c33-172">Have no side effects.</span></span>

<span data-ttu-id="b5c33-173">Это можно представить математические функции в этом контексте.</span><span class="sxs-lookup"><span data-stu-id="b5c33-173">It is helpful to think of mathematical functions in this context.</span></span> <span data-ttu-id="b5c33-174">В математике функции зависят только от их аргументов и не оказывает никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="b5c33-174">In mathematics, functions depend only on their arguments and do not have any side effects.</span></span> <span data-ttu-id="b5c33-175">Математические функции `f(x) = x + 1`, значение `f(x)` зависит только от значение `x`.</span><span class="sxs-lookup"><span data-stu-id="b5c33-175">In the mathematical function `f(x) = x + 1`, the value of `f(x)` depends only on the value of `x`.</span></span> <span data-ttu-id="b5c33-176">Чистые функции в функциональном программировании являются одинаково.</span><span class="sxs-lookup"><span data-stu-id="b5c33-176">Pure functions in functional programming are the same way.</span></span>

<span data-ttu-id="b5c33-177">При написании чистой функции, функция должна зависеть только от своих аргументов и не выполнять никаких действий, которые приводят к побочный эффект.</span><span class="sxs-lookup"><span data-stu-id="b5c33-177">When writing a pure function, the function must depend only on its arguments and not perform any action that results in a side effect.</span></span>

<span data-ttu-id="b5c33-178">Вот пример функция, изменяющая, так как он зависит от состояния глобального, изменяемый:</span><span class="sxs-lookup"><span data-stu-id="b5c33-178">Here is an example of a non-pure function because it depends on global, mutable state:</span></span>

```fsharp
let mutable value = 1

let addOneToValue x = x + value
```

<span data-ttu-id="b5c33-179">`addOneToValue` Функция четко "нечистыми", так как `value` могут быть изменены в любое время, чтобы иметь разное значение 1.</span><span class="sxs-lookup"><span data-stu-id="b5c33-179">The `addOneToValue` function is clearly impure, because `value` could be changed at any time to have a different value than 1.</span></span> <span data-ttu-id="b5c33-180">Этот шаблон в зависимости от глобальное значение — избегать в функциональном программировании.</span><span class="sxs-lookup"><span data-stu-id="b5c33-180">This pattern of depending on a global value is to be avoided in functional programming.</span></span>

<span data-ttu-id="b5c33-181">Вот еще один пример функции, не являющийся чистым, так как он выполняет побочный эффект:</span><span class="sxs-lookup"><span data-stu-id="b5c33-181">Here is another example of a non-pure function, because it performs a side effect:</span></span>

```fsharp
let addOneToValue x = 
    printfn "x is %d" x
    x + 1
```

<span data-ttu-id="b5c33-182">Несмотря на то, что эта функция не зависит от глобальное значение, он записывает значение `x` в выходные данные программы.</span><span class="sxs-lookup"><span data-stu-id="b5c33-182">Although this function does not depend on a global value, it writes the value of `x` to the output of the program.</span></span> <span data-ttu-id="b5c33-183">Несмотря на то, что нет ничего плохого таким образом, это означает, что функция не является чисто.</span><span class="sxs-lookup"><span data-stu-id="b5c33-183">Although there is nothing inherently wrong with doing this, it does mean that the function is not pure.</span></span>

<span data-ttu-id="b5c33-184">Удаление `printfn` инструкции наконец делает функцию чисто:</span><span class="sxs-lookup"><span data-stu-id="b5c33-184">Removing the `printfn` statement finally makes the function pure:</span></span>

```fsharp
let addOneToValue x = x + 1
```

<span data-ttu-id="b5c33-185">Несмотря на то, что данная функция не является по своей природе _лучше_ прежней версией с `printfn` инструкции, это гарантирует, что все этой функции будет возвращать значение.</span><span class="sxs-lookup"><span data-stu-id="b5c33-185">Although this function is not inherently _better_ than the previous version with the `printfn` statement, it does guarantee that all this function does is return a value.</span></span> <span data-ttu-id="b5c33-186">При вызове этой функции функцию один раз или 1 миллиарда раз будет по-прежнему результат, в то же самое: просто результатом является значение.</span><span class="sxs-lookup"><span data-stu-id="b5c33-186">Calling this function once or 1 billion times will still result in the same thing: just producing a value.</span></span> <span data-ttu-id="b5c33-187">Эта предсказуемость полезно в функциональное программирование, так как это означает, что любой чистой функции со ссылочным прозрачен.</span><span class="sxs-lookup"><span data-stu-id="b5c33-187">This predictability is valuable in functional programming, as it means that any pure function is referentially transparent.</span></span>

### <a name="referential-transparency"></a><span data-ttu-id="b5c33-188">Ссылочной прозрачности</span><span class="sxs-lookup"><span data-stu-id="b5c33-188">Referential Transparency</span></span>

<span data-ttu-id="b5c33-189">Ссылочной прозрачности является свойством выражения и функции.</span><span class="sxs-lookup"><span data-stu-id="b5c33-189">Referential transparency is a property of expressions and functions.</span></span> <span data-ttu-id="b5c33-190">Для выражения со ссылочным прозрачным должен иметь возможность заменить его результирующее значение без изменения ее поведения.</span><span class="sxs-lookup"><span data-stu-id="b5c33-190">For an expression to be referentially transparent, it must be able to be replaced with its resulting value without changing the program's behavior.</span></span> <span data-ttu-id="b5c33-191">Все чистые функции являются со ссылочным прозрачными.</span><span class="sxs-lookup"><span data-stu-id="b5c33-191">All pure functions are referentially transparent.</span></span>

<span data-ttu-id="b5c33-192">Как и в чистые функции может быть полезным подумать об ссылочной прозрачности с точки зрения математические.</span><span class="sxs-lookup"><span data-stu-id="b5c33-192">As with pure functions, it can be helpful to think of referential transparency from a mathematical perspective.</span></span> <span data-ttu-id="b5c33-193">В математическое выражение `y = f(x)`, `f(x)` могут быть заменены результат функции и по-прежнему будет равно `y`.</span><span class="sxs-lookup"><span data-stu-id="b5c33-193">In the mathematical expression `y = f(x)`, `f(x)` can be replaced by the result of the function and it will still be equal to `y`.</span></span> <span data-ttu-id="b5c33-194">Это относится и к ссылочной прозрачности в функциональном программировании.</span><span class="sxs-lookup"><span data-stu-id="b5c33-194">This is equally true for referential transparency in functional programming.</span></span>

<span data-ttu-id="b5c33-195">Рассмотрите возможность вызова ранее определенный `addOneIfOdd` функцию дважды:</span><span class="sxs-lookup"><span data-stu-id="b5c33-195">Consider calling the previously defined `addOneIfOdd` function twice:</span></span>

```fsharp
// Checks if 'x' is odd by using the mod operator
let isOdd x = x % 2 <> 0

let addOneIfOdd input =
    let result =
        if isOdd input then
            input + 1
        else
            input

    result

let res1 = addOneIffOdd 1 // Produces 2
let res2 = addOneIffOdd 2 // Produces 2
```

<span data-ttu-id="b5c33-196">Можно заменить каждого вызова функции в теле функции, заменив аргумент `input` с каждым из значений:</span><span class="sxs-lookup"><span data-stu-id="b5c33-196">We can replace each function call with the function body, substituting the argument `input` with each value:</span></span>

```fsharp
// Checks if 'x' is odd by using the mod operator
let isOdd x = x % 2 <> 0

let addOneIfOdd input =
    let result =
        if isOdd input then
            input + 1
        else
            input

    result

let res1 =
    let result =
        if isOdd 1 then
            1 + 1
        else
            1

    result
let res2 =
    let result =
        if isOdd 2 then
            2 + 1
        else
            2

    result
```

<span data-ttu-id="b5c33-197">Оба `res1` и `res2` имеют одинаковое значение, как если бы вызывалась функция, означает, что `addOneIfOdd` со ссылочным прозрачно!</span><span class="sxs-lookup"><span data-stu-id="b5c33-197">Both `res1` and `res2` have the same value as if the function was called, indicating that `addOneIfOdd` is referentially transparent!</span></span>

<span data-ttu-id="b5c33-198">Кроме того функции не нужно быть чистым, также были со ссылочным прозрачными.</span><span class="sxs-lookup"><span data-stu-id="b5c33-198">Additionally, a function doesn't have to be pure to also be referentially transparent.</span></span> <span data-ttu-id="b5c33-199">Рассмотрите предыдущее определение `addOneTovalue`:</span><span class="sxs-lookup"><span data-stu-id="b5c33-199">Consider a previous definition of  `addOneTovalue`:</span></span>

```fsharp
let addOneToValue x = 
    printfn "x is %d" x
    x + 1
```

<span data-ttu-id="b5c33-200">Каждый вызов этой функции можно заменить его телом и того, что будет происходить каждый раз:</span><span class="sxs-lookup"><span data-stu-id="b5c33-200">Any call to this function can also be replaced by its body and the same things will happen each time:</span></span>

* <span data-ttu-id="b5c33-201">Значение, перед добавлением к, выводится в выходные данные</span><span class="sxs-lookup"><span data-stu-id="b5c33-201">The value, prior to being added to, is printed to the output</span></span>
* <span data-ttu-id="b5c33-202">Значение имеет 1 добавляется при</span><span class="sxs-lookup"><span data-stu-id="b5c33-202">The value has 1 added to it</span></span>

<span data-ttu-id="b5c33-203">При программировании в F#, часто бывает ссылочной прозрачности, цель, а не чистоты.</span><span class="sxs-lookup"><span data-stu-id="b5c33-203">When programming in F#, it is often referential transparency that is the goal, rather than purity.</span></span> <span data-ttu-id="b5c33-204">Тем не менее рекомендуется по-прежнему записываемый чистых функций, когда это возможно.</span><span class="sxs-lookup"><span data-stu-id="b5c33-204">However, it is still good practice to write pure functions when you can.</span></span>

### <a name="immutability"></a><span data-ttu-id="b5c33-205">Неизменность</span><span class="sxs-lookup"><span data-stu-id="b5c33-205">Immutability</span></span>

<span data-ttu-id="b5c33-206">Наконец одним из фундаментальных понятий типизированный функционального программирования является неизменяемости.</span><span class="sxs-lookup"><span data-stu-id="b5c33-206">Finally, one of the most fundamental concepts of typed functional programming is immutability.</span></span> <span data-ttu-id="b5c33-207">В F#, все значения являются неизменяемыми по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b5c33-207">In F#, all values are immutable by default.</span></span> <span data-ttu-id="b5c33-208">Это означает, что они не могут быть изменяемые локально, если только вы явным образом пометить их как изменяемые.</span><span class="sxs-lookup"><span data-stu-id="b5c33-208">That means they cannot be mutated in-place unless you explicitly mark them as mutable.</span></span>

<span data-ttu-id="b5c33-209">На практике работы с неизменяемыми значениями означает, что изменить ваш подход к программированию из «Необходимо изменить что-то», чтобы «мне нужно создать новое значение».</span><span class="sxs-lookup"><span data-stu-id="b5c33-209">In practice, working with immutable values means that you change your approach to programming from, "I need to change something", to "I need to produce a new value".</span></span>

<span data-ttu-id="b5c33-210">Например добавление 1 значение означает, что результатом является новый значение, не изменения существующего:</span><span class="sxs-lookup"><span data-stu-id="b5c33-210">For example, adding 1 to a value means producing a new value, not mutating the existing one:</span></span>

```fsharp
let value = 1
let secondValue = value + 1
```

<span data-ttu-id="b5c33-211">В F#, показано в следующем коде **не** изменяет `value` функции; вместо этого он выполняет проверку равенства:</span><span class="sxs-lookup"><span data-stu-id="b5c33-211">In F#, the following code does **not** mutate the `value` function; instead, it performs an equality check:</span></span>

```fsharp
let value = 1
value = value + 1 // Produces a 'bool' value!
```

<span data-ttu-id="b5c33-212">Некоторые языки функционального программирования вообще не поддерживают изменения.</span><span class="sxs-lookup"><span data-stu-id="b5c33-212">Some functional programming languages do not support mutation at all.</span></span> <span data-ttu-id="b5c33-213">В F#, он поддерживается, но не значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b5c33-213">In F#, it is supported, but it is not the default behavior for values.</span></span>

<span data-ttu-id="b5c33-214">Эта концепция расширяет еще дальше структур данных.</span><span class="sxs-lookup"><span data-stu-id="b5c33-214">This concept extends even further to data structures.</span></span> <span data-ttu-id="b5c33-215">В функциональном программировании неизменяемых структур данных такие как наборы (и многих других) имеют другую реализацию, чем изначально может ожидать.</span><span class="sxs-lookup"><span data-stu-id="b5c33-215">In functional programming, immutable data structures such as sets (and many more) have a different implementation than you might initially expect.</span></span> <span data-ttu-id="b5c33-216">По сути, что-то, как добавить элемент в набор не приводит к изменению набора, он создает _новый_ набор с выгод.</span><span class="sxs-lookup"><span data-stu-id="b5c33-216">Conceptually, something like adding an item to a set does not change the set, it produces a _new_ set with the added value.</span></span> <span data-ttu-id="b5c33-217">На самом деле это часто выполняется с другой структурой данных, позволяющий для эффективного отслеживания значение таким образом, чтобы в результате можно предоставить подходящее представление данных.</span><span class="sxs-lookup"><span data-stu-id="b5c33-217">Under the covers, this is often accomplished by a different data structure that allows for efficiently tracking a value so that the appropriate representation of the data can be given as a result.</span></span>

<span data-ttu-id="b5c33-218">Этот стиль работы со значениями и структур данных крайне важен, как приходится обрабатывать любая операция, изменяющая что-то, как если бы он создает новую версию от этого.</span><span class="sxs-lookup"><span data-stu-id="b5c33-218">This style of working with values and data structures is critical, as it forces you to treat any operation that modifies something as if it creates a new version of that thing.</span></span> <span data-ttu-id="b5c33-219">Это позволяет выполнять такие проверки на равенство и сравнимость согласованности в программах.</span><span class="sxs-lookup"><span data-stu-id="b5c33-219">This allows for things like equality and comparability to be consistent in your programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b5c33-220">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="b5c33-220">Next steps</span></span>

<span data-ttu-id="b5c33-221">Следующий раздел тщательно будут рассмотрены функции, исследует различные способы, их можно использовать в функциональном программировании.</span><span class="sxs-lookup"><span data-stu-id="b5c33-221">The next section will thoroughly cover functions, exploring different ways you can use them in functional programming.</span></span>

<span data-ttu-id="b5c33-222">[Функций первого класса](first-class-functions.md) рассматриваются функции глубоко, показывающий, как их можно использовать в различных контекстах.</span><span class="sxs-lookup"><span data-stu-id="b5c33-222">[First-class functions](first-class-functions.md) explores functions deeply, showing how you can use them in various contexts.</span></span>

## <a name="further-reading"></a><span data-ttu-id="b5c33-223">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="b5c33-223">Further reading</span></span>

<span data-ttu-id="b5c33-224">[Мышления функционально](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) series – это еще один интересный ресурс, чтобы узнать о функциональное программирование на F#.</span><span class="sxs-lookup"><span data-stu-id="b5c33-224">The [Thinking Functionally](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) series is another great resource to learn about functional programming with F#.</span></span> <span data-ttu-id="b5c33-225">Он охватывает основы функционального программирования в смысле практичные и простые для чтения, с помощью F# функции, чтобы продемонстрировать основные понятия.</span><span class="sxs-lookup"><span data-stu-id="b5c33-225">It covers fundamentals of functional programming in a pragmatic and easy-to-read way, using F# features to illustrate the concepts.</span></span>