---
title: Введение в функциональное программирование на F#
description: Изучите основы функционального программирования в F#.
ms.date: 10/29/2018
ms.openlocfilehash: e1a0edc61dbe13012c48e166d490e22ebc70d6a0
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424702"
---
# <a name="introduction-to-functional-programming-in-f"></a><span data-ttu-id="63792-103">Введение в функциональное программирование в F\#</span><span class="sxs-lookup"><span data-stu-id="63792-103">Introduction to Functional Programming in F\#</span></span>

<span data-ttu-id="63792-104">Функциональное программирование — это стиль программирования, который подчеркивает использование функций и неизменяемых данных.</span><span class="sxs-lookup"><span data-stu-id="63792-104">Functional programming is a style of programming that emphasizes the use of functions and immutable data.</span></span> <span data-ttu-id="63792-105">Типизированное функциональное программирование — это то, что функциональное программирование сочетается со F#статическими типами, например с.</span><span class="sxs-lookup"><span data-stu-id="63792-105">Typed functional programming is when functional programming is combined with static types, such as with F#.</span></span> <span data-ttu-id="63792-106">Как правило, в функциональном программировании используются следующие понятия:</span><span class="sxs-lookup"><span data-stu-id="63792-106">In general, the following concepts are emphasized in functional programming:</span></span>

* <span data-ttu-id="63792-107">Функции в качестве основных используемых конструкций</span><span class="sxs-lookup"><span data-stu-id="63792-107">Functions as the primary constructs you use</span></span>
* <span data-ttu-id="63792-108">Выражения вместо операторов</span><span class="sxs-lookup"><span data-stu-id="63792-108">Expressions instead of statements</span></span>
* <span data-ttu-id="63792-109">Неизменяемые значения для переменных</span><span class="sxs-lookup"><span data-stu-id="63792-109">Immutable values over variables</span></span>
* <span data-ttu-id="63792-110">Декларативное программирование по императивному программированию</span><span class="sxs-lookup"><span data-stu-id="63792-110">Declarative programming over imperative programming</span></span>

<span data-ttu-id="63792-111">В этой серии вы ознакомитесь с основными понятиями и шаблонами в F#функциональном программировании с помощью.</span><span class="sxs-lookup"><span data-stu-id="63792-111">Throughout this series, you'll explore concepts and patterns in functional programming using F#.</span></span> <span data-ttu-id="63792-112">Кроме того, вы также узнаете F# об этом.</span><span class="sxs-lookup"><span data-stu-id="63792-112">Along the way, you'll learn some F# too.</span></span>

## <a name="terminology"></a><span data-ttu-id="63792-113">Терминология</span><span class="sxs-lookup"><span data-stu-id="63792-113">Terminology</span></span>

<span data-ttu-id="63792-114">Функциональное программирование, как и другие парадигмы программирования, сопровождается словарем, который со временем потребуется изучить.</span><span class="sxs-lookup"><span data-stu-id="63792-114">Functional programming, like other programming paradigms, comes with a vocabulary that you will eventually need to learn.</span></span> <span data-ttu-id="63792-115">Ниже приведены некоторые распространенные термины, которые можно увидеть все время:</span><span class="sxs-lookup"><span data-stu-id="63792-115">Here are some common terms you'll see all of the time:</span></span>

* <span data-ttu-id="63792-116">**Function** — функция — это конструкция, которая выдает выходные данные при наличии входных данных.</span><span class="sxs-lookup"><span data-stu-id="63792-116">**Function** - A function is a construct that will produce an output when given an input.</span></span> <span data-ttu-id="63792-117">Более формально он _сопоставляет_ элемент из одного набора с другим набором.</span><span class="sxs-lookup"><span data-stu-id="63792-117">More formally, it _maps_ an item from one set to another set.</span></span> <span data-ttu-id="63792-118">Этот формальный метод ликвидируется в конкретную часть, особенно при использовании функций, которые работают с коллекциями данных.</span><span class="sxs-lookup"><span data-stu-id="63792-118">This formalism is lifted into the concrete in many ways, especially when using functions that operate on collections of data.</span></span> <span data-ttu-id="63792-119">Это наиболее простое (и важное) понятие в функциональном программировании.</span><span class="sxs-lookup"><span data-stu-id="63792-119">It is the most basic (and important) concept in functional programming.</span></span>
* <span data-ttu-id="63792-120">**Expression** — выражение — это конструкция в коде, которая создает значение.</span><span class="sxs-lookup"><span data-stu-id="63792-120">**Expression** - An expression is a construct in code that produces a value.</span></span> <span data-ttu-id="63792-121">В F#это значение должно быть привязано или явно игнорироваться.</span><span class="sxs-lookup"><span data-stu-id="63792-121">In F#, this value must be bound or explicitly ignored.</span></span> <span data-ttu-id="63792-122">Выражение может быть тривиально заменено вызовом функции.</span><span class="sxs-lookup"><span data-stu-id="63792-122">An expression can be trivially replaced by a function call.</span></span>
* <span data-ttu-id="63792-123">**Чистота** — это свойство функции таким, что возвращаемое значение всегда одинаково для одних и тех же аргументов, и его оценка не имеет побочных эффектов.</span><span class="sxs-lookup"><span data-stu-id="63792-123">**Purity** - Purity is a property of a function such that its return value is always the same for the same arguments, and that its evaluation has no side effects.</span></span> <span data-ttu-id="63792-124">Чистая функция полностью зависит от своих аргументов.</span><span class="sxs-lookup"><span data-stu-id="63792-124">A pure function depends entirely on its arguments.</span></span>
* <span data-ttu-id="63792-125">**Ссылочная** прозрачность — это свойство выражений таким образом, что их можно заменить на выходные данные, не влияя на поведение программы.</span><span class="sxs-lookup"><span data-stu-id="63792-125">**Referential Transparency** - Referential Transparency is a property of expressions such that they can be replaced with their output without affecting a program's behavior.</span></span>
* <span data-ttu-id="63792-126">**Неизменность** — это значение не может быть изменено на месте.</span><span class="sxs-lookup"><span data-stu-id="63792-126">**Immutability** - Immutability means that a value cannot be changed in-place.</span></span> <span data-ttu-id="63792-127">Это отличается от переменных, которые могут измениться на месте.</span><span class="sxs-lookup"><span data-stu-id="63792-127">This is in contrast with variables, which can change in place.</span></span>

## <a name="examples"></a><span data-ttu-id="63792-128">Примеры</span><span class="sxs-lookup"><span data-stu-id="63792-128">Examples</span></span>

<span data-ttu-id="63792-129">В следующих примерах демонстрируются эти основные понятия.</span><span class="sxs-lookup"><span data-stu-id="63792-129">The following examples demonstrate these core concepts.</span></span>

### <a name="functions"></a><span data-ttu-id="63792-130">Функции</span><span class="sxs-lookup"><span data-stu-id="63792-130">Functions</span></span>

<span data-ttu-id="63792-131">Наиболее распространенной и фундаментальной конструкцией функционального программирования является функция.</span><span class="sxs-lookup"><span data-stu-id="63792-131">The most common and fundamental construct in functional programming is the function.</span></span> <span data-ttu-id="63792-132">Вот простая функция, которая добавляет 1 к целому числу:</span><span class="sxs-lookup"><span data-stu-id="63792-132">Here's a simple function that adds 1 to an integer:</span></span>

```fsharp
let addOne x = x + 1
```

<span data-ttu-id="63792-133">Сигнатура его типа выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="63792-133">Its type signature is as follows:</span></span>

```fsharp
val addOne: x:int -> int
```

<span data-ttu-id="63792-134">Сигнатура может считаться "`addOne` принимает `int` с именем `x` и создает `int`".</span><span class="sxs-lookup"><span data-stu-id="63792-134">The signature can be read as, "`addOne` accepts an `int` named `x` and will produce an `int`".</span></span> <span data-ttu-id="63792-135">Более формально, `addOne` _сопоставляет_ значение из набора целых чисел с набором целых чисел.</span><span class="sxs-lookup"><span data-stu-id="63792-135">More formally, `addOne` is _mapping_ a value from the set of integers to the set of integers.</span></span> <span data-ttu-id="63792-136">Маркер `->` обозначает это сопоставление.</span><span class="sxs-lookup"><span data-stu-id="63792-136">The `->` token signifies this mapping.</span></span> <span data-ttu-id="63792-137">В F#можно просмотреть сигнатуру функции, чтобы понять, что она делает.</span><span class="sxs-lookup"><span data-stu-id="63792-137">In F#, you can usually look at the function signature to get a sense for what it does.</span></span>

<span data-ttu-id="63792-138">Итак, почему сигнатура важна?</span><span class="sxs-lookup"><span data-stu-id="63792-138">So, why is the signature important?</span></span> <span data-ttu-id="63792-139">В типизированном функциональном программировании реализация функции часто менее важна, чем фактическая сигнатура типа!</span><span class="sxs-lookup"><span data-stu-id="63792-139">In typed functional programming, the implementation of a function is often less important than the actual type signature!</span></span> <span data-ttu-id="63792-140">Тот факт, что `addOne` добавляет значение 1 к целому числу, интересно во время выполнения, но при создании программы тот факт, что он принимает и возвращает `int`, — это то, что именно будет использоваться для этой функции.</span><span class="sxs-lookup"><span data-stu-id="63792-140">The fact that `addOne` adds the value 1 to an integer is interesting at runtime, but when you are constructing a program, the fact that it accepts and returns an `int` is what informs how you will actually use this function.</span></span> <span data-ttu-id="63792-141">Кроме того, после правильного использования этой функции (по отношению к сигнатуре типа) Диагностика проблем может быть выполнена только в теле функции `addOne`.</span><span class="sxs-lookup"><span data-stu-id="63792-141">Furthermore, once you use this function correctly (with respect to its type signature), diagnosing any problems can be done only within the body of the `addOne` function.</span></span> <span data-ttu-id="63792-142">Это стимула за типизированное функциональное программирование.</span><span class="sxs-lookup"><span data-stu-id="63792-142">This is the impetus behind typed functional programming.</span></span>

### <a name="expressions"></a><span data-ttu-id="63792-143">Выражения</span><span class="sxs-lookup"><span data-stu-id="63792-143">Expressions</span></span>

<span data-ttu-id="63792-144">Выражения — это конструкции, результатом вычисления которых является значение.</span><span class="sxs-lookup"><span data-stu-id="63792-144">Expressions are constructs that evaluate to a value.</span></span> <span data-ttu-id="63792-145">В отличие от операторов, выполняющих действие, выражения можно считать выполнением действия, которое возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="63792-145">In contrast to statements, which perform an action, expressions can be thought of performing an action that gives back a value.</span></span> <span data-ttu-id="63792-146">Выражения почти всегда используются в пользу операторов в функциональном программировании.</span><span class="sxs-lookup"><span data-stu-id="63792-146">Expressions are almost always used in favor of statements in functional programming.</span></span>

<span data-ttu-id="63792-147">Рассмотрим предыдущую функцию, `addOne`.</span><span class="sxs-lookup"><span data-stu-id="63792-147">Consider the previous function, `addOne`.</span></span> <span data-ttu-id="63792-148">Тело `addOne` является выражением:</span><span class="sxs-lookup"><span data-stu-id="63792-148">The body of `addOne` is an expression:</span></span>

```fsharp
// 'x + 1' is an expression!
let addOne x = x + 1
```

<span data-ttu-id="63792-149">Это результат выражения, определяющего тип результата функции `addOne`.</span><span class="sxs-lookup"><span data-stu-id="63792-149">It is the result of this expression that defines the result type of the `addOne` function.</span></span> <span data-ttu-id="63792-150">Например, выражение, составляющее эту функцию, может быть изменено на другой тип, например `string`:</span><span class="sxs-lookup"><span data-stu-id="63792-150">For example, the expression that makes up this function could be changed to be a different type, such as a `string`:</span></span>

```fsharp
let addOne x = x.ToString() + "1"
```

<span data-ttu-id="63792-151">Теперь сигнатура функции:</span><span class="sxs-lookup"><span data-stu-id="63792-151">The signature of the function is now:</span></span>

```fsharp
val addOne: x:'a -> string
```

<span data-ttu-id="63792-152">Поскольку для любого типа F# в может быть вызван `ToString()`, тип `x` был сделан универсальным (называемым [автоматической обобщением](../language-reference/generics/automatic-generalization.md)), а результирующий тип — `string`.</span><span class="sxs-lookup"><span data-stu-id="63792-152">Since any type in F# can have `ToString()` called on it, the type of `x` has been made generic (called [Automatic Generalization](../language-reference/generics/automatic-generalization.md)), and the resultant type is a `string`.</span></span>

<span data-ttu-id="63792-153">Выражения — это не только тела функций.</span><span class="sxs-lookup"><span data-stu-id="63792-153">Expressions are not just the bodies of functions.</span></span> <span data-ttu-id="63792-154">Можно использовать выражения, которые возвращают значение, которое используется в других местах.</span><span class="sxs-lookup"><span data-stu-id="63792-154">You can have expressions that produce a value you use elsewhere.</span></span> <span data-ttu-id="63792-155">Общий `if`:</span><span class="sxs-lookup"><span data-stu-id="63792-155">A common one is `if`:</span></span>

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

<span data-ttu-id="63792-156">`if` выражение создает значение с именем `result`.</span><span class="sxs-lookup"><span data-stu-id="63792-156">The `if` expression produces a value called `result`.</span></span> <span data-ttu-id="63792-157">Обратите внимание, что можно полностью опустить `result`, сделав `if` выражение телом функции `addOneIfOdd`.</span><span class="sxs-lookup"><span data-stu-id="63792-157">Note that you could omit `result` entirely, making the `if` expression the body of the `addOneIfOdd` function.</span></span> <span data-ttu-id="63792-158">Ключевым моментом, который следует помнить о выражениях, является то, что они создают значение.</span><span class="sxs-lookup"><span data-stu-id="63792-158">The key thing to remember about expressions is that they produce a value.</span></span>

<span data-ttu-id="63792-159">Существует специальный тип, `unit`, который используется при отсутствии возвращаемых результатов.</span><span class="sxs-lookup"><span data-stu-id="63792-159">There is a special type, `unit`, that is used when there is nothing to return.</span></span> <span data-ttu-id="63792-160">Например, рассмотрим эту простую функцию:</span><span class="sxs-lookup"><span data-stu-id="63792-160">For example, consider this simple function:</span></span>

```fsharp
let printString (str: string) =
    printfn "String is: %s" str
```

<span data-ttu-id="63792-161">Подпись выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="63792-161">The signature looks like this:</span></span>

```fsharp
val printString: str:string -> unit
```

<span data-ttu-id="63792-162">Тип `unit` указывает, что фактическое значение не возвращается.</span><span class="sxs-lookup"><span data-stu-id="63792-162">The `unit` type indicates that there is no actual value being returned.</span></span> <span data-ttu-id="63792-163">Это полезно, если у вас есть подпрограммы, которые должны «работать», несмотря на отсутствие значения, возвращаемого в результате этой работы.</span><span class="sxs-lookup"><span data-stu-id="63792-163">This is useful when you have a routine that must "do work" despite having no value to return as a result of that work.</span></span>

<span data-ttu-id="63792-164">Это очень четкое отличие от императивного программирования, где эквивалентная `if` конструкция является оператором, а создание значений часто осуществляется с помощью изменения переменных.</span><span class="sxs-lookup"><span data-stu-id="63792-164">This is in sharp contrast to imperative programming, where the equivalent `if` construct is a statement, and producing values is often done with mutating variables.</span></span> <span data-ttu-id="63792-165">Например, в C#код может быть написан следующим образом:</span><span class="sxs-lookup"><span data-stu-id="63792-165">For example, in C#, the code might be written like this:</span></span>

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

<span data-ttu-id="63792-166">Стоит отметить, что C# и другие языки в стиле C поддерживают [выражение ternary](../../csharp/language-reference/operators/conditional-operator.md), которое обеспечивает условное программирование на основе выражений.</span><span class="sxs-lookup"><span data-stu-id="63792-166">It's worth noting that C# and other C-style languages do support the [ternary expression](../../csharp/language-reference/operators/conditional-operator.md), which allows for expression-based conditional programming.</span></span>

<span data-ttu-id="63792-167">В функциональном программировании редко изменяются значения с помощью операторов.</span><span class="sxs-lookup"><span data-stu-id="63792-167">In functional programming, it is rare to mutate values with statements.</span></span> <span data-ttu-id="63792-168">Хотя некоторые функциональные языки поддерживают инструкции и изменения, использование этих концепций в функциональном программировании не является распространенным.</span><span class="sxs-lookup"><span data-stu-id="63792-168">Although some functional languages support statements and mutation, it is not common to use these concepts in functional programming.</span></span>

### <a name="pure-functions"></a><span data-ttu-id="63792-169">Чистые функции</span><span class="sxs-lookup"><span data-stu-id="63792-169">Pure functions</span></span>

<span data-ttu-id="63792-170">Как упоминалось ранее, чистые функции — это функции, которые:</span><span class="sxs-lookup"><span data-stu-id="63792-170">As previously mentioned, pure functions are functions that:</span></span>

* <span data-ttu-id="63792-171">Всегда вычисляют одно и то же значение для одних и тех же входных данных.</span><span class="sxs-lookup"><span data-stu-id="63792-171">Always evaluate to the same value for the same input.</span></span>
* <span data-ttu-id="63792-172">Не имеют побочных эффектов.</span><span class="sxs-lookup"><span data-stu-id="63792-172">Have no side effects.</span></span>

<span data-ttu-id="63792-173">В этом контексте удобнее рассматривать математические функции.</span><span class="sxs-lookup"><span data-stu-id="63792-173">It is helpful to think of mathematical functions in this context.</span></span> <span data-ttu-id="63792-174">В математике функции зависят только от своих аргументов и не имеют побочных эффектов.</span><span class="sxs-lookup"><span data-stu-id="63792-174">In mathematics, functions depend only on their arguments and do not have any side effects.</span></span> <span data-ttu-id="63792-175">В математической функции `f(x) = x + 1`значение `f(x)` зависит только от значения `x`.</span><span class="sxs-lookup"><span data-stu-id="63792-175">In the mathematical function `f(x) = x + 1`, the value of `f(x)` depends only on the value of `x`.</span></span> <span data-ttu-id="63792-176">Чистые функции функционального программирования одинаковы.</span><span class="sxs-lookup"><span data-stu-id="63792-176">Pure functions in functional programming are the same way.</span></span>

<span data-ttu-id="63792-177">При написании чистой функции функция должна зависеть только от своих аргументов и не выполнять никаких действий, которые приводят к побочному результату.</span><span class="sxs-lookup"><span data-stu-id="63792-177">When writing a pure function, the function must depend only on its arguments and not perform any action that results in a side effect.</span></span>

<span data-ttu-id="63792-178">Ниже приведен пример функции, не являющейся чистой, так как она зависит от глобального изменяемого состояния:</span><span class="sxs-lookup"><span data-stu-id="63792-178">Here is an example of a non-pure function because it depends on global, mutable state:</span></span>

```fsharp
let mutable value = 1

let addOneToValue x = x + value
```

<span data-ttu-id="63792-179">Функция `addOneToValue` очевидной, поскольку `value` может быть изменена в любое время, чтобы иметь другое значение, отличное от 1.</span><span class="sxs-lookup"><span data-stu-id="63792-179">The `addOneToValue` function is clearly impure, because `value` could be changed at any time to have a different value than 1.</span></span> <span data-ttu-id="63792-180">Этот шаблон в зависимости от глобального значения следует избегать в функциональном программировании.</span><span class="sxs-lookup"><span data-stu-id="63792-180">This pattern of depending on a global value is to be avoided in functional programming.</span></span>

<span data-ttu-id="63792-181">Ниже приведен еще один пример функции, не являющейся чистой, поскольку она выполняет побочный результат:</span><span class="sxs-lookup"><span data-stu-id="63792-181">Here is another example of a non-pure function, because it performs a side effect:</span></span>

```fsharp
let addOneToValue x =
    printfn "x is %d" x
    x + 1
```

<span data-ttu-id="63792-182">Хотя эта функция не зависит от глобального значения, она записывает значение `x` в выходные данные программы.</span><span class="sxs-lookup"><span data-stu-id="63792-182">Although this function does not depend on a global value, it writes the value of `x` to the output of the program.</span></span> <span data-ttu-id="63792-183">Хотя в этом нет ничего плохого, это означает, что функция не является чистой.</span><span class="sxs-lookup"><span data-stu-id="63792-183">Although there is nothing inherently wrong with doing this, it does mean that the function is not pure.</span></span> <span data-ttu-id="63792-184">Если другая часть программы зависит от объекта, внешнего для программы, например выходного буфера, то вызов этой функции может повлиять на другую часть программы.</span><span class="sxs-lookup"><span data-stu-id="63792-184">If another part of your program depends on something external to the program, such as the output buffer, then calling this function can affect that other part of your program.</span></span>

<span data-ttu-id="63792-185">Удаление оператора `printfn` делает функцию чистой:</span><span class="sxs-lookup"><span data-stu-id="63792-185">Removing the `printfn` statement makes the function pure:</span></span>

```fsharp
let addOneToValue x = x + 1
```

<span data-ttu-id="63792-186">Несмотря на то что эта функция не является _более лучшей_ по сравнению с предыдущей версией с помощью оператора `printfn`, она гарантирует, что вся эта функция возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="63792-186">Although this function is not inherently _better_ than the previous version with the `printfn` statement, it does guarantee that all this function does is return a value.</span></span> <span data-ttu-id="63792-187">При вызове этой функции любое количество раз дает тот же результат: он просто создает значение.</span><span class="sxs-lookup"><span data-stu-id="63792-187">Calling this function any number of times produces the same result: it just produces a value.</span></span> <span data-ttu-id="63792-188">Предсказуемость, предоставляемая чистотой, — это что-то множество функциональных программистов, которые стремится.</span><span class="sxs-lookup"><span data-stu-id="63792-188">The predictability given by purity is something many functional programmers strive for.</span></span>

### <a name="immutability"></a><span data-ttu-id="63792-189">Неизменяемости</span><span class="sxs-lookup"><span data-stu-id="63792-189">Immutability</span></span>

<span data-ttu-id="63792-190">Наконец, одна из самых фундаментальных концепций типизированного функционального программирования — неизменяемость.</span><span class="sxs-lookup"><span data-stu-id="63792-190">Finally, one of the most fundamental concepts of typed functional programming is immutability.</span></span> <span data-ttu-id="63792-191">В F#все значения по умолчанию являются неизменяемыми.</span><span class="sxs-lookup"><span data-stu-id="63792-191">In F#, all values are immutable by default.</span></span> <span data-ttu-id="63792-192">Это означает, что их нельзя изменить на месте, если явно не помечать их как изменяемые.</span><span class="sxs-lookup"><span data-stu-id="63792-192">That means they cannot be mutated in-place unless you explicitly mark them as mutable.</span></span>

<span data-ttu-id="63792-193">На практике работа с неизменяемыми значениями означает, что вы меняете подход на программирование с «мне нужно изменить что-нибудь» на «мне нужно получить новое значение».</span><span class="sxs-lookup"><span data-stu-id="63792-193">In practice, working with immutable values means that you change your approach to programming from, "I need to change something", to "I need to produce a new value".</span></span>

<span data-ttu-id="63792-194">Например, добавление 1 к значению означает создание нового значения, а не изменение существующего.</span><span class="sxs-lookup"><span data-stu-id="63792-194">For example, adding 1 to a value means producing a new value, not mutating the existing one:</span></span>

```fsharp
let value = 1
let secondValue = value + 1
```

<span data-ttu-id="63792-195">В F#следующий код **не** изменяет функцию `value`. Вместо этого он выполняет проверку на равенство:</span><span class="sxs-lookup"><span data-stu-id="63792-195">In F#, the following code does **not** mutate the `value` function; instead, it performs an equality check:</span></span>

```fsharp
let value = 1
value = value + 1 // Produces a 'bool' value!
```

<span data-ttu-id="63792-196">Некоторые языки функционального программирования не поддерживают изменения вообще.</span><span class="sxs-lookup"><span data-stu-id="63792-196">Some functional programming languages do not support mutation at all.</span></span> <span data-ttu-id="63792-197">В F#поддерживается, но не является поведением по умолчанию для значений.</span><span class="sxs-lookup"><span data-stu-id="63792-197">In F#, it is supported, but it is not the default behavior for values.</span></span>

<span data-ttu-id="63792-198">Эта концепция расширяется еще до структур данных.</span><span class="sxs-lookup"><span data-stu-id="63792-198">This concept extends even further to data structures.</span></span> <span data-ttu-id="63792-199">В функциональном программировании неизменяемые структуры данных, такие как наборы (и многие другие), имеют разную реализацию, чем может быть изначально ожидать.</span><span class="sxs-lookup"><span data-stu-id="63792-199">In functional programming, immutable data structures such as sets (and many more) have a different implementation than you might initially expect.</span></span> <span data-ttu-id="63792-200">По сути, что-то вроде добавления элемента в набор не изменяет набор, он создает _Новый_ набор с добавленным значением.</span><span class="sxs-lookup"><span data-stu-id="63792-200">Conceptually, something like adding an item to a set does not change the set, it produces a _new_ set with the added value.</span></span> <span data-ttu-id="63792-201">На самом деле это часто достигается с помощью другой структуры данных, которая позволяет эффективно отслеживать значение, чтобы в результате можно было получить соответствующее представление данных.</span><span class="sxs-lookup"><span data-stu-id="63792-201">Under the covers, this is often accomplished by a different data structure that allows for efficiently tracking a value so that the appropriate representation of the data can be given as a result.</span></span>

<span data-ttu-id="63792-202">Этот стиль работы со значениями и структурами данных является критически важным, так как он заставляет обрабатывать любые операции, которые изменяют что-то, как при создании новой версии.</span><span class="sxs-lookup"><span data-stu-id="63792-202">This style of working with values and data structures is critical, as it forces you to treat any operation that modifies something as if it creates a new version of that thing.</span></span> <span data-ttu-id="63792-203">Это позволяет обеспечить единообразие в программах, таких как равенство и сравнение.</span><span class="sxs-lookup"><span data-stu-id="63792-203">This allows for things like equality and comparability to be consistent in your programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="63792-204">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="63792-204">Next steps</span></span>

<span data-ttu-id="63792-205">В следующем разделе будут тщательно рассмотрены функции, а также различные способы их использования в функциональном программировании.</span><span class="sxs-lookup"><span data-stu-id="63792-205">The next section will thoroughly cover functions, exploring different ways you can use them in functional programming.</span></span>

<span data-ttu-id="63792-206">[Функции первого класса](first-class-functions.md) анализируют функции глубоко, показывая, как их можно использовать в различных контекстах.</span><span class="sxs-lookup"><span data-stu-id="63792-206">[First-class functions](first-class-functions.md) explores functions deeply, showing how you can use them in various contexts.</span></span>

## <a name="further-reading"></a><span data-ttu-id="63792-207">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="63792-207">Further reading</span></span>

<span data-ttu-id="63792-208">[Помышление функционального](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) ряда — еще один отличный ресурс для изучения функционального F#программирования с помощью.</span><span class="sxs-lookup"><span data-stu-id="63792-208">The [Thinking Functionally](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) series is another great resource to learn about functional programming with F#.</span></span> <span data-ttu-id="63792-209">В нем рассматриваются основы функционального программирования на практичном и удобном для чтения виде, с использованием F# функций для иллюстрации концепций.</span><span class="sxs-lookup"><span data-stu-id="63792-209">It covers fundamentals of functional programming in a pragmatic and easy-to-read way, using F# features to illustrate the concepts.</span></span>
