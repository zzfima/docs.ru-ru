---
title: Введение в функциональное программирование на F#
description: Изучение основ функционального программирования в F#.
ms.date: 10/29/2018
ms.openlocfilehash: 84022e58c0f17b9e9875402c653c31e494e940da
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772792"
---
# <a name="introduction-to-functional-programming-in-f"></a><span data-ttu-id="b88e7-103">Введение в функциональное программирование на языке f #\#</span><span class="sxs-lookup"><span data-stu-id="b88e7-103">Introduction to Functional Programming in F\#</span></span>

<span data-ttu-id="b88e7-104">Функциональное программирование является стилем, который делается упор на использование функций и постоянные данные.</span><span class="sxs-lookup"><span data-stu-id="b88e7-104">Functional programming is a style of programming that emphasizes the use of functions and immutable data.</span></span> <span data-ttu-id="b88e7-105">Типизированный функциональное программирование является функционального программирования в сочетании с статические типы, такие как с F#.</span><span class="sxs-lookup"><span data-stu-id="b88e7-105">Typed functional programming is when functional programming is combined with static types, such as with F#.</span></span> <span data-ttu-id="b88e7-106">Как правило в функциональном программировании выделены следующие понятия:</span><span class="sxs-lookup"><span data-stu-id="b88e7-106">In general, the following concepts are emphasized in functional programming:</span></span>

* <span data-ttu-id="b88e7-107">Функции как основными конструкциями, которые можно использовать</span><span class="sxs-lookup"><span data-stu-id="b88e7-107">Functions as the primary constructs you use</span></span>
* <span data-ttu-id="b88e7-108">Выражения вместо инструкций</span><span class="sxs-lookup"><span data-stu-id="b88e7-108">Expressions instead of statements</span></span>
* <span data-ttu-id="b88e7-109">Постоянные значения, переменные</span><span class="sxs-lookup"><span data-stu-id="b88e7-109">Immutable values over variables</span></span>
* <span data-ttu-id="b88e7-110">Декларативную модель программирования через императивного программирования</span><span class="sxs-lookup"><span data-stu-id="b88e7-110">Declarative programming over imperative programming</span></span>

<span data-ttu-id="b88e7-111">В этой серии, на них рассматриваются концепции и шаблоны в функционального программирования, используя F#.</span><span class="sxs-lookup"><span data-stu-id="b88e7-111">Throughout this series, you'll explore concepts and patterns in functional programming using F#.</span></span> <span data-ttu-id="b88e7-112">Кроме того, вы узнаете о некоторых F# слишком.</span><span class="sxs-lookup"><span data-stu-id="b88e7-112">Along the way, you'll learn some F# too.</span></span>

## <a name="terminology"></a><span data-ttu-id="b88e7-113">Терминология</span><span class="sxs-lookup"><span data-stu-id="b88e7-113">Terminology</span></span>

<span data-ttu-id="b88e7-114">Функциональное программирование, как и других парадигм программирования, в состав словаря, который со временем необходимо будет узнать.</span><span class="sxs-lookup"><span data-stu-id="b88e7-114">Functional programming, like other programming paradigms, comes with a vocabulary that you will eventually need to learn.</span></span> <span data-ttu-id="b88e7-115">Ниже приведены некоторые распространенные термины, вы увидите все время.</span><span class="sxs-lookup"><span data-stu-id="b88e7-115">Here are some common terms you'll see all of the time:</span></span>

* <span data-ttu-id="b88e7-116">**Функция** -функция представляет собой конструкцию, будет преобразовано в выходное при заданном входном.</span><span class="sxs-lookup"><span data-stu-id="b88e7-116">**Function** - A function is a construct that will produce an output when given an input.</span></span> <span data-ttu-id="b88e7-117">Более формально, его _сопоставляет_ набор из одного элемента к другому набору.</span><span class="sxs-lookup"><span data-stu-id="b88e7-117">More formally, it _maps_ an item from one set to another set.</span></span> <span data-ttu-id="b88e7-118">Этот формализм она поднимается в конкретных во многих отношениях, особенно при использовании функции, которые работают с коллекциями данных.</span><span class="sxs-lookup"><span data-stu-id="b88e7-118">This formalism is lifted into the concrete in many ways, especially when using functions that operate on collections of data.</span></span> <span data-ttu-id="b88e7-119">Это наиболее основных (и важный) концепции функционального программирования.</span><span class="sxs-lookup"><span data-stu-id="b88e7-119">It is the most basic (and important) concept in functional programming.</span></span> 
* <span data-ttu-id="b88e7-120">**Выражение** -выражение — это конструкция, в коде, который создает значение.</span><span class="sxs-lookup"><span data-stu-id="b88e7-120">**Expression** - An expression is a construct in code that produces a value.</span></span> <span data-ttu-id="b88e7-121">В F#, это значение должно быть привязаны или явным образом игнорировать.</span><span class="sxs-lookup"><span data-stu-id="b88e7-121">In F#, this value must be bound or explicitly ignored.</span></span> <span data-ttu-id="b88e7-122">Выражения могут быть просто заменены вызов функции.</span><span class="sxs-lookup"><span data-stu-id="b88e7-122">An expression can be trivially replaced by a function call.</span></span>
* <span data-ttu-id="b88e7-123">**Чистота** -чистоты является свойством функции, таким образом, что его возвращаемое значение всегда является одинаковым для те же аргументы, и что его вычисление не имеет побочных эффектов.</span><span class="sxs-lookup"><span data-stu-id="b88e7-123">**Purity** - Purity is a property of a function such that its return value is always the same for the same arguments, and that its evaluation has no side effects.</span></span> <span data-ttu-id="b88e7-124">Чистая функция полностью зависит от своих аргументов.</span><span class="sxs-lookup"><span data-stu-id="b88e7-124">A pure function depends entirely on its arguments.</span></span>
* <span data-ttu-id="b88e7-125">**Ссылочной прозрачности** -ссылочной прозрачности является свойством выражений таким образом, что они могут быть заменены свои выходные данные без влияния на поведение программы.</span><span class="sxs-lookup"><span data-stu-id="b88e7-125">**Referential Transparency** - Referential Transparency is a property of expressions such that they can be replaced with their output without affecting a program's behavior.</span></span>
* <span data-ttu-id="b88e7-126">**Неизменность** -постоянство означает, что значение не может быть изменен на месте.</span><span class="sxs-lookup"><span data-stu-id="b88e7-126">**Immutability** - Immutability means that a value cannot be changed in-place.</span></span> <span data-ttu-id="b88e7-127">Это отличает их от переменных, которые можно изменить на месте.</span><span class="sxs-lookup"><span data-stu-id="b88e7-127">This is in contrast with variables, which can change in place.</span></span>

## <a name="examples"></a><span data-ttu-id="b88e7-128">Примеры</span><span class="sxs-lookup"><span data-stu-id="b88e7-128">Examples</span></span>

<span data-ttu-id="b88e7-129">В следующих примерах демонстрируется следующих базовых понятиях.</span><span class="sxs-lookup"><span data-stu-id="b88e7-129">The following examples demonstrate these core concepts.</span></span>

### <a name="functions"></a><span data-ttu-id="b88e7-130">Функции</span><span class="sxs-lookup"><span data-stu-id="b88e7-130">Functions</span></span>

<span data-ttu-id="b88e7-131">Наиболее распространенные и основные конструкции функционального программирования является функция.</span><span class="sxs-lookup"><span data-stu-id="b88e7-131">The most common and fundamental construct in functional programming is the function.</span></span> <span data-ttu-id="b88e7-132">Ниже приведен простой функции, которая добавляет 1 к целое число.</span><span class="sxs-lookup"><span data-stu-id="b88e7-132">Here's a simple function that adds 1 to an integer:</span></span>

```fsharp
let addOne x = x + 1
```

<span data-ttu-id="b88e7-133">Сигнатура типа выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b88e7-133">Its type signature is as follows:</span></span>

```fsharp
val addOne: x:int -> int
```

<span data-ttu-id="b88e7-134">Подпись может быть прочитан как, «`addOne` принимает `int` с именем `x` и создаст `int`«.</span><span class="sxs-lookup"><span data-stu-id="b88e7-134">The signature can be read as, "`addOne` accepts an `int` named `x` and will produce an `int`".</span></span> <span data-ttu-id="b88e7-135">Более формально `addOne` — _сопоставление_ значение из набора целых чисел в набор целых чисел.</span><span class="sxs-lookup"><span data-stu-id="b88e7-135">More formally, `addOne` is _mapping_ a value from the set of integers to the set of integers.</span></span> <span data-ttu-id="b88e7-136">`->` Токен указывает на это сопоставление.</span><span class="sxs-lookup"><span data-stu-id="b88e7-136">The `->` token signifies this mapping.</span></span> <span data-ttu-id="b88e7-137">В F#, обычно можно посмотреть на сигнатуру функции, чтобы понять, что она делает.</span><span class="sxs-lookup"><span data-stu-id="b88e7-137">In F#, you can usually look at the function signature to get a sense for what it does.</span></span>

<span data-ttu-id="b88e7-138">Таким образом, почему важен подпись?</span><span class="sxs-lookup"><span data-stu-id="b88e7-138">So, why is the signature important?</span></span> <span data-ttu-id="b88e7-139">В типизированных функционального программирования, реализации функции меньше часто важным, чем фактический тип подписи!</span><span class="sxs-lookup"><span data-stu-id="b88e7-139">In typed functional programming, the implementation of a function is often less important than the actual type signature!</span></span> <span data-ttu-id="b88e7-140">Тот факт, `addOne` добавляет значение в целое число 1 интересен во время выполнения, но при создании программы, тот факт, что он принимает и возвращает `int` является что информирует о том, как его можно использовать эту функцию.</span><span class="sxs-lookup"><span data-stu-id="b88e7-140">The fact that `addOne` adds the value 1 to an integer is interesting at runtime, but when you are constructing a program, the fact that it accepts and returns an `int` is what informs how you will actually use this function.</span></span> <span data-ttu-id="b88e7-141">Кроме того, как только эта функция правильно (по отношению к его сигнатура типа), диагностики проблем можно сделать только в теле `addOne` функции.</span><span class="sxs-lookup"><span data-stu-id="b88e7-141">Furthermore, once you use this function correctly (with respect to its type signature), diagnosing any problems can be done only within the body of the `addOne` function.</span></span> <span data-ttu-id="b88e7-142">Это движущая сила типизированный функционального программирования.</span><span class="sxs-lookup"><span data-stu-id="b88e7-142">This is the impetus behind typed functional programming.</span></span>

### <a name="expressions"></a><span data-ttu-id="b88e7-143">Выражения</span><span class="sxs-lookup"><span data-stu-id="b88e7-143">Expressions</span></span>

<span data-ttu-id="b88e7-144">Выражения — это конструкции, которые возвращают значения.</span><span class="sxs-lookup"><span data-stu-id="b88e7-144">Expressions are constructs that evaluate to a value.</span></span> <span data-ttu-id="b88e7-145">В отличие от инструкции, которые выполняют действия, выражения можно рассматривать выполняет действие, которое возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="b88e7-145">In contrast to statements, which perform an action, expressions can be thought of performing an action that gives back a value.</span></span> <span data-ttu-id="b88e7-146">Выражения используются почти всегда пользу инструкций в функциональном программировании.</span><span class="sxs-lookup"><span data-stu-id="b88e7-146">Expressions are almost always used in favor of statements in functional programming.</span></span>

<span data-ttu-id="b88e7-147">Рассмотрим функцию предыдущих `addOne`.</span><span class="sxs-lookup"><span data-stu-id="b88e7-147">Consider the previous function, `addOne`.</span></span> <span data-ttu-id="b88e7-148">Тело `addOne` — это выражение:</span><span class="sxs-lookup"><span data-stu-id="b88e7-148">The body of `addOne` is an expression:</span></span>

```fsharp
// 'x + 1' is an expression!
let addOne x = x + 1
```

<span data-ttu-id="b88e7-149">Она является результатом этого выражения, который определяет тип результата `addOne` функции.</span><span class="sxs-lookup"><span data-stu-id="b88e7-149">It is the result of this expression that defines the result type of the `addOne` function.</span></span> <span data-ttu-id="b88e7-150">Например, выражение, которое представляет эта функция может измениться на быть другого типа, например `string`:</span><span class="sxs-lookup"><span data-stu-id="b88e7-150">For example, the expression that makes up this function could be changed to be a different type, such as a `string`:</span></span>

```fsharp
let addOne x = x.ToString() + "1"
```

<span data-ttu-id="b88e7-151">Подпись функции теперь является:</span><span class="sxs-lookup"><span data-stu-id="b88e7-151">The signature of the function is now:</span></span>

```fsharp
val addOne: x:'a -> string
```

<span data-ttu-id="b88e7-152">С момента любого типа в F# может иметь `ToString()` для нее тип `x` стала универсального (вызывается [Автоматическое обобщение](../language-reference/generics/automatic-generalization.md)), и результирующим типом является `string`.</span><span class="sxs-lookup"><span data-stu-id="b88e7-152">Since any type in F# can have `ToString()` called on it, the type of `x` has been made generic (called [Automatic Generalization](../language-reference/generics/automatic-generalization.md)), and the resultant type is a `string`.</span></span>

<span data-ttu-id="b88e7-153">Выражения не только тела функции.</span><span class="sxs-lookup"><span data-stu-id="b88e7-153">Expressions are not just the bodies of functions.</span></span> <span data-ttu-id="b88e7-154">Может иметь выражений, возвращающих значение, которое можно использовать в другом месте.</span><span class="sxs-lookup"><span data-stu-id="b88e7-154">You can have expressions that produce a value you use elsewhere.</span></span> <span data-ttu-id="b88e7-155">Он общий `if`:</span><span class="sxs-lookup"><span data-stu-id="b88e7-155">A common one is `if`:</span></span>

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

<span data-ttu-id="b88e7-156">`if` Выражение создает значение с именем `result`.</span><span class="sxs-lookup"><span data-stu-id="b88e7-156">The `if` expression produces a value called `result`.</span></span> <span data-ttu-id="b88e7-157">Обратите внимание, что можно опустить `result` полностью, что делает `if` выражение текст из `addOneIfOdd` функции.</span><span class="sxs-lookup"><span data-stu-id="b88e7-157">Note that you could omit `result` entirely, making the `if` expression the body of the `addOneIfOdd` function.</span></span> <span data-ttu-id="b88e7-158">Следует помнить о выражениях ключевой момент заключается в том, что они создают значение.</span><span class="sxs-lookup"><span data-stu-id="b88e7-158">The key thing to remember about expressions is that they produce a value.</span></span>

<span data-ttu-id="b88e7-159">Есть особый тип `unit`, используемый при нет ничего для возврата.</span><span class="sxs-lookup"><span data-stu-id="b88e7-159">There is a special type, `unit`, that is used when there is nothing to return.</span></span> <span data-ttu-id="b88e7-160">Например рассмотрим Эта простая функция:</span><span class="sxs-lookup"><span data-stu-id="b88e7-160">For example, consider this simple function:</span></span>

```fsharp
let printString (str: string) =
    printfn "String is: %s" str
```

<span data-ttu-id="b88e7-161">Подпись выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b88e7-161">The signature looks like this:</span></span>

```fsharp
val printString: str:string -> unit
```

<span data-ttu-id="b88e7-162">`unit` Тип указывает, что фактическое значение не возвращается.</span><span class="sxs-lookup"><span data-stu-id="b88e7-162">The `unit` type indicates that there is no actual value being returned.</span></span> <span data-ttu-id="b88e7-163">Это полезно при наличии подпрограмму, которая должна «рабочая», несмотря на наличие значения, которое можно вернуть в результате этой работы.</span><span class="sxs-lookup"><span data-stu-id="b88e7-163">This is useful when you have a routine that must "do work" despite having no value to return as a result of that work.</span></span>

<span data-ttu-id="b88e7-164">Это существенно отличаются от императивного программирования, где эквивалент `if` конструкция является оператором, и создание значения часто выполняется с помощью изменения переменных.</span><span class="sxs-lookup"><span data-stu-id="b88e7-164">This is in sharp contrast to imperative programming, where the equivalent `if` construct is a statement, and producing values is often done with mutating variables.</span></span> <span data-ttu-id="b88e7-165">Например, в C#, код может быть написан следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b88e7-165">For example, in C#, the code might be written like this:</span></span>

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

<span data-ttu-id="b88e7-166">Следует отметить, что C# и других языков в стиле C поддерживают [троичное выражение](../../csharp/language-reference/operators/conditional-operator.md), что позволяет условного программирование на основе выражения.</span><span class="sxs-lookup"><span data-stu-id="b88e7-166">It's worth noting that C# and other C-style languages do support the [ternary expression](../../csharp/language-reference/operators/conditional-operator.md), which allows for expression-based conditional programming.</span></span>

<span data-ttu-id="b88e7-167">В функциональном программировании очень редко изменяемая значений с помощью инструкций.</span><span class="sxs-lookup"><span data-stu-id="b88e7-167">In functional programming, it is rare to mutate values with statements.</span></span> <span data-ttu-id="b88e7-168">Несмотря на то, что некоторые функциональные языки поддерживают операторы и изменений, обычно не использовать эти концепции в функциональном программировании.</span><span class="sxs-lookup"><span data-stu-id="b88e7-168">Although some functional languages support statements and mutation, it is not common to use these concepts in functional programming.</span></span>

### <a name="pure-functions"></a><span data-ttu-id="b88e7-169">Чистые функции</span><span class="sxs-lookup"><span data-stu-id="b88e7-169">Pure functions</span></span>

<span data-ttu-id="b88e7-170">Как упоминалось ранее, чистые функции являются функции, которые:</span><span class="sxs-lookup"><span data-stu-id="b88e7-170">As previously mentioned, pure functions are functions that:</span></span>

* <span data-ttu-id="b88e7-171">Всегда возвращают значение то же значение для того же входа.</span><span class="sxs-lookup"><span data-stu-id="b88e7-171">Always evaluate to the same value for the same input.</span></span>
* <span data-ttu-id="b88e7-172">Не имеют побочных эффектов.</span><span class="sxs-lookup"><span data-stu-id="b88e7-172">Have no side effects.</span></span>

<span data-ttu-id="b88e7-173">Это можно представить математические функции в этом контексте.</span><span class="sxs-lookup"><span data-stu-id="b88e7-173">It is helpful to think of mathematical functions in this context.</span></span> <span data-ttu-id="b88e7-174">В математике функции зависят только от их аргументов и не оказывает никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="b88e7-174">In mathematics, functions depend only on their arguments and do not have any side effects.</span></span> <span data-ttu-id="b88e7-175">Математические функции `f(x) = x + 1`, значение `f(x)` зависит только от значение `x`.</span><span class="sxs-lookup"><span data-stu-id="b88e7-175">In the mathematical function `f(x) = x + 1`, the value of `f(x)` depends only on the value of `x`.</span></span> <span data-ttu-id="b88e7-176">Чистые функции в функциональном программировании являются одинаково.</span><span class="sxs-lookup"><span data-stu-id="b88e7-176">Pure functions in functional programming are the same way.</span></span>

<span data-ttu-id="b88e7-177">При написании чистой функции, функция должна зависеть только от своих аргументов и не выполнять никаких действий, которые приводят к побочный эффект.</span><span class="sxs-lookup"><span data-stu-id="b88e7-177">When writing a pure function, the function must depend only on its arguments and not perform any action that results in a side effect.</span></span>

<span data-ttu-id="b88e7-178">Вот пример функция, изменяющая, так как он зависит от состояния глобального, изменяемый:</span><span class="sxs-lookup"><span data-stu-id="b88e7-178">Here is an example of a non-pure function because it depends on global, mutable state:</span></span>

```fsharp
let mutable value = 1

let addOneToValue x = x + value
```

<span data-ttu-id="b88e7-179">`addOneToValue` Функция четко "нечистыми", так как `value` могут быть изменены в любое время, чтобы иметь разное значение 1.</span><span class="sxs-lookup"><span data-stu-id="b88e7-179">The `addOneToValue` function is clearly impure, because `value` could be changed at any time to have a different value than 1.</span></span> <span data-ttu-id="b88e7-180">Этот шаблон в зависимости от глобальное значение — избегать в функциональном программировании.</span><span class="sxs-lookup"><span data-stu-id="b88e7-180">This pattern of depending on a global value is to be avoided in functional programming.</span></span>

<span data-ttu-id="b88e7-181">Вот еще один пример функции, не являющийся чистым, так как он выполняет побочный эффект:</span><span class="sxs-lookup"><span data-stu-id="b88e7-181">Here is another example of a non-pure function, because it performs a side effect:</span></span>

```fsharp
let addOneToValue x = 
    printfn "x is %d" x
    x + 1
```

<span data-ttu-id="b88e7-182">Несмотря на то, что эта функция не зависит от глобальное значение, он записывает значение `x` в выходные данные программы.</span><span class="sxs-lookup"><span data-stu-id="b88e7-182">Although this function does not depend on a global value, it writes the value of `x` to the output of the program.</span></span> <span data-ttu-id="b88e7-183">Несмотря на то, что нет ничего плохого таким образом, это означает, что функция не является чисто.</span><span class="sxs-lookup"><span data-stu-id="b88e7-183">Although there is nothing inherently wrong with doing this, it does mean that the function is not pure.</span></span> <span data-ttu-id="b88e7-184">Если другой части программы зависит от программы, например выходной буфер, внешними факторами, затем вызов этой функции может повлиять на этот другой части программы.</span><span class="sxs-lookup"><span data-stu-id="b88e7-184">If another part of your program depends on something external to the program, such as the output buffer, then calling this function can affect that other part of your program.</span></span>

<span data-ttu-id="b88e7-185">Удаление `printfn` инструкция делает функцию чисто:</span><span class="sxs-lookup"><span data-stu-id="b88e7-185">Removing the `printfn` statement makes the function pure:</span></span>

```fsharp
let addOneToValue x = x + 1
```

<span data-ttu-id="b88e7-186">Несмотря на то, что данная функция не является по своей природе _лучше_ прежней версией с `printfn` инструкции, это гарантирует, что все этой функции будет возвращать значение.</span><span class="sxs-lookup"><span data-stu-id="b88e7-186">Although this function is not inherently _better_ than the previous version with the `printfn` statement, it does guarantee that all this function does is return a value.</span></span> <span data-ttu-id="b88e7-187">Вызов этой функции любое количество раз дает тот же результат: он просто создает значение.</span><span class="sxs-lookup"><span data-stu-id="b88e7-187">Calling this function any number of times produces the same result: it just produces a value.</span></span> <span data-ttu-id="b88e7-188">Предсказуемость, выданный чистоты является то, что многие функциональные программисты Стремитесь к.</span><span class="sxs-lookup"><span data-stu-id="b88e7-188">The predictability given by purity is something many functional programmers strive for.</span></span>

### <a name="immutability"></a><span data-ttu-id="b88e7-189">Неизменность</span><span class="sxs-lookup"><span data-stu-id="b88e7-189">Immutability</span></span>

<span data-ttu-id="b88e7-190">Наконец одним из фундаментальных понятий типизированный функционального программирования является неизменяемости.</span><span class="sxs-lookup"><span data-stu-id="b88e7-190">Finally, one of the most fundamental concepts of typed functional programming is immutability.</span></span> <span data-ttu-id="b88e7-191">В F#, все значения являются неизменяемыми по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b88e7-191">In F#, all values are immutable by default.</span></span> <span data-ttu-id="b88e7-192">Это означает, что они не могут быть изменяемые локально, если только вы явным образом пометить их как изменяемые.</span><span class="sxs-lookup"><span data-stu-id="b88e7-192">That means they cannot be mutated in-place unless you explicitly mark them as mutable.</span></span>

<span data-ttu-id="b88e7-193">На практике работы с неизменяемыми значениями означает, что изменить ваш подход к программированию из «Необходимо изменить что-то», чтобы «мне нужно создать новое значение».</span><span class="sxs-lookup"><span data-stu-id="b88e7-193">In practice, working with immutable values means that you change your approach to programming from, "I need to change something", to "I need to produce a new value".</span></span>

<span data-ttu-id="b88e7-194">Например добавление 1 значение означает, что результатом является новый значение, не изменения существующего:</span><span class="sxs-lookup"><span data-stu-id="b88e7-194">For example, adding 1 to a value means producing a new value, not mutating the existing one:</span></span>

```fsharp
let value = 1
let secondValue = value + 1
```

<span data-ttu-id="b88e7-195">В F#, показано в следующем коде **не** изменяет `value` функции; вместо этого он выполняет проверку равенства:</span><span class="sxs-lookup"><span data-stu-id="b88e7-195">In F#, the following code does **not** mutate the `value` function; instead, it performs an equality check:</span></span>

```fsharp
let value = 1
value = value + 1 // Produces a 'bool' value!
```

<span data-ttu-id="b88e7-196">Некоторые языки функционального программирования вообще не поддерживают изменения.</span><span class="sxs-lookup"><span data-stu-id="b88e7-196">Some functional programming languages do not support mutation at all.</span></span> <span data-ttu-id="b88e7-197">В F#, он поддерживается, но не значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b88e7-197">In F#, it is supported, but it is not the default behavior for values.</span></span>

<span data-ttu-id="b88e7-198">Эта концепция расширяет еще дальше структур данных.</span><span class="sxs-lookup"><span data-stu-id="b88e7-198">This concept extends even further to data structures.</span></span> <span data-ttu-id="b88e7-199">В функциональном программировании неизменяемых структур данных такие как наборы (и многих других) имеют другую реализацию, чем изначально может ожидать.</span><span class="sxs-lookup"><span data-stu-id="b88e7-199">In functional programming, immutable data structures such as sets (and many more) have a different implementation than you might initially expect.</span></span> <span data-ttu-id="b88e7-200">По сути, что-то, как добавить элемент в набор не приводит к изменению набора, он создает _новый_ набор с выгод.</span><span class="sxs-lookup"><span data-stu-id="b88e7-200">Conceptually, something like adding an item to a set does not change the set, it produces a _new_ set with the added value.</span></span> <span data-ttu-id="b88e7-201">На самом деле это часто выполняется с другой структурой данных, позволяющий для эффективного отслеживания значение таким образом, чтобы в результате можно предоставить подходящее представление данных.</span><span class="sxs-lookup"><span data-stu-id="b88e7-201">Under the covers, this is often accomplished by a different data structure that allows for efficiently tracking a value so that the appropriate representation of the data can be given as a result.</span></span>

<span data-ttu-id="b88e7-202">Этот стиль работы со значениями и структур данных крайне важен, как приходится обрабатывать любая операция, изменяющая что-то, как если бы он создает новую версию от этого.</span><span class="sxs-lookup"><span data-stu-id="b88e7-202">This style of working with values and data structures is critical, as it forces you to treat any operation that modifies something as if it creates a new version of that thing.</span></span> <span data-ttu-id="b88e7-203">Это позволяет выполнять такие проверки на равенство и сравнимость согласованности в программах.</span><span class="sxs-lookup"><span data-stu-id="b88e7-203">This allows for things like equality and comparability to be consistent in your programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b88e7-204">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="b88e7-204">Next steps</span></span>

<span data-ttu-id="b88e7-205">Следующий раздел тщательно будут рассмотрены функции, исследует различные способы, их можно использовать в функциональном программировании.</span><span class="sxs-lookup"><span data-stu-id="b88e7-205">The next section will thoroughly cover functions, exploring different ways you can use them in functional programming.</span></span>

<span data-ttu-id="b88e7-206">[Функций первого класса](first-class-functions.md) рассматриваются функции глубоко, показывающий, как их можно использовать в различных контекстах.</span><span class="sxs-lookup"><span data-stu-id="b88e7-206">[First-class functions](first-class-functions.md) explores functions deeply, showing how you can use them in various contexts.</span></span>

## <a name="further-reading"></a><span data-ttu-id="b88e7-207">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="b88e7-207">Further reading</span></span>

<span data-ttu-id="b88e7-208">[Мышления функционально](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) series – это еще один интересный ресурс, чтобы узнать о функциональное программирование на F#.</span><span class="sxs-lookup"><span data-stu-id="b88e7-208">The [Thinking Functionally](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) series is another great resource to learn about functional programming with F#.</span></span> <span data-ttu-id="b88e7-209">Он охватывает основы функционального программирования в смысле практичные и простые для чтения, с помощью F# функции, чтобы продемонстрировать основные понятия.</span><span class="sxs-lookup"><span data-stu-id="b88e7-209">It covers fundamentals of functional programming in a pragmatic and easy-to-read way, using F# features to illustrate the concepts.</span></span>
