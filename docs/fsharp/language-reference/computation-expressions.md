---
title: Выражения вычисления
description: Узнайте, как создать удобный синтаксис для записи вычислений F# , может быть виртуализированного и комбинированные с помощью управления привязок и конструкций потока.
ms.date: 07/27/2018
ms.openlocfilehash: 7524a42f8efb951be255ca6cc285740ef1fa12c3
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56093519"
---
# <a name="computation-expressions"></a><span data-ttu-id="bbc65-103">Выражения вычисления</span><span class="sxs-lookup"><span data-stu-id="bbc65-103">Computation Expressions</span></span>

<span data-ttu-id="bbc65-104">Выражения вычисления в F# предоставить удобный синтаксис для записи вычислений, которые можно упорядочивать и комбинировать с помощью привязок и конструкций потока управления.</span><span class="sxs-lookup"><span data-stu-id="bbc65-104">Computation expressions in F# provide a convenient syntax for writing computations that can be sequenced and combined using control flow constructs and bindings.</span></span> <span data-ttu-id="bbc65-105">В зависимости от типа вычислительного выражения они могут рассматриваться как способ выражения оболочки Monad, monoids, преобразователи monad и applicative функторы.</span><span class="sxs-lookup"><span data-stu-id="bbc65-105">Depending on the kind of computation expression, they can be thought of as a way to express monads, monoids, monad transformers, and applicative functors.</span></span> <span data-ttu-id="bbc65-106">Тем не менее, в отличие от других языках (таких как *нотации* в Haskell), они не привязаны к одну ограниченную абстракцию и не следует полагаться на макросов или других видов метапрограммирование для выполнения удобный и контекстно-зависимые синтаксис.</span><span class="sxs-lookup"><span data-stu-id="bbc65-106">However, unlike other languages (such as *do-notation* in Haskell), they are not tied to a single abstraction, and do not rely on macros or other forms of metaprogramming to accomplish a convenient and context-sensitive syntax.</span></span>

## <a name="overview"></a><span data-ttu-id="bbc65-107">Обзор</span><span class="sxs-lookup"><span data-stu-id="bbc65-107">Overview</span></span>

<span data-ttu-id="bbc65-108">Вычисления могут принимать различные формы.</span><span class="sxs-lookup"><span data-stu-id="bbc65-108">Computations can take many forms.</span></span> <span data-ttu-id="bbc65-109">Наиболее распространенная форма вычислений является однопоточным выполнением, который является простым для понимания и изменить.</span><span class="sxs-lookup"><span data-stu-id="bbc65-109">The most common form of computation is single-threaded execution, which is easy to understand and modify.</span></span> <span data-ttu-id="bbc65-110">Однако не все виды вычисления, так же просто, как однопоточного выполнения.</span><span class="sxs-lookup"><span data-stu-id="bbc65-110">However, not all forms of computation are as straightforward as single-threaded execution.</span></span> <span data-ttu-id="bbc65-111">Ниже приведены некоторые примеры таких ситуаций.</span><span class="sxs-lookup"><span data-stu-id="bbc65-111">Some examples include:</span></span>

* <span data-ttu-id="bbc65-112">Недетерминированные вычислений</span><span class="sxs-lookup"><span data-stu-id="bbc65-112">Non-deterministic computations</span></span>
* <span data-ttu-id="bbc65-113">Асинхронные вычисления</span><span class="sxs-lookup"><span data-stu-id="bbc65-113">Asynchronous computations</span></span>
* <span data-ttu-id="bbc65-114">Effectful вычислений</span><span class="sxs-lookup"><span data-stu-id="bbc65-114">Effectful computations</span></span>
* <span data-ttu-id="bbc65-115">Генерирующих вычислений</span><span class="sxs-lookup"><span data-stu-id="bbc65-115">Generative computations</span></span>

<span data-ttu-id="bbc65-116">Как правило, существуют *контекстно-зависимые* вычислений, которые необходимо выполнить в определенных частях приложения.</span><span class="sxs-lookup"><span data-stu-id="bbc65-116">More generally, there are *context-sensitive* computations that you must perform in certain parts of an application.</span></span> <span data-ttu-id="bbc65-117">Написание кода контекстно-зависимые может оказаться сложной задачей, как легко вызывал «утечку» вычислений за пределами данного контекста без абстракции, чтобы запретить делать это.</span><span class="sxs-lookup"><span data-stu-id="bbc65-117">Writing context-sensitive code can be challenging, as it is easy to "leak" computations outside of a given context without abstractions to prevent you from doing so.</span></span> <span data-ttu-id="bbc65-118">Эти абстракции часто трудно написать самостоятельно, поэтому F# имеет общий способ сделать так называемых **выражения вычисления**.</span><span class="sxs-lookup"><span data-stu-id="bbc65-118">These abstractions are often challenging to write by yourself, which is why F# has a generalized way to do so called **computation expressions**.</span></span>

<span data-ttu-id="bbc65-119">Выражения вычисления предложить универсальный синтаксис и абстракции модель для кодирования контекстно-зависимые вычислений.</span><span class="sxs-lookup"><span data-stu-id="bbc65-119">Computation expressions offer a uniform syntax and abstraction model for encoding context-sensitive computations.</span></span>

<span data-ttu-id="bbc65-120">Каждое выражение вычисления реализуется *построитель* типа.</span><span class="sxs-lookup"><span data-stu-id="bbc65-120">Every computation expression is backed by a *builder* type.</span></span> <span data-ttu-id="bbc65-121">Тип построителя определяет операции, доступные для вычисления выражения.</span><span class="sxs-lookup"><span data-stu-id="bbc65-121">The builder type defines the operations that are available for the computation expression.</span></span> <span data-ttu-id="bbc65-122">См. в разделе [Создание нового типа из вычислительного выражения](computation-expressions.md#creating-a-new-type-of-computation-expression), показано, как создать пользовательский вычислительного выражения.</span><span class="sxs-lookup"><span data-stu-id="bbc65-122">See [Creating a New Type of Computation Expression](computation-expressions.md#creating-a-new-type-of-computation-expression), which shows how to create a custom computation expression.</span></span>

### <a name="syntax-overview"></a><span data-ttu-id="bbc65-123">Общие сведения о синтаксисе</span><span class="sxs-lookup"><span data-stu-id="bbc65-123">Syntax overview</span></span>

<span data-ttu-id="bbc65-124">Все выражения вычисления иметь следующий вид:</span><span class="sxs-lookup"><span data-stu-id="bbc65-124">All computation expressions have the following form:</span></span>

```
builder-expr { cexper }
```

<span data-ttu-id="bbc65-125">где `builder-expr` имя тип построителя, который определяет вычислительного выражения, и `cexper` является тело выражения вычислительного выражения.</span><span class="sxs-lookup"><span data-stu-id="bbc65-125">where `builder-expr` is the name of a builder type that defines the computation expression, and `cexper` is the expression body of the computation expression.</span></span> <span data-ttu-id="bbc65-126">Например `async` вычисление выражения кода может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="bbc65-126">For example, `async` computation expression code can look like this:</span></span>

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

<span data-ttu-id="bbc65-127">Нет специальных, дополнительный синтаксис в выражении вычисления, как показано в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="bbc65-127">There is a special, additional syntax available within a computation expression, as shown in the previous example.</span></span> <span data-ttu-id="bbc65-128">С помощью вычислительных выражений возможны следующие выражения формы:</span><span class="sxs-lookup"><span data-stu-id="bbc65-128">The following expression forms are possible with computation expressions:</span></span>

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

<span data-ttu-id="bbc65-129">Каждый из этих ключевых слов и других стандартных F# ключевые слова в выражение вычисления доступны, если они не были определены в резервный тип построителя.</span><span class="sxs-lookup"><span data-stu-id="bbc65-129">Each of these keywords, and other standard F# keywords are only available in a computation expression if they have been defined in the backing builder type.</span></span> <span data-ttu-id="bbc65-130">Единственное исключение — `match!`, который сам является синтаксическая сладость для применения `let!` следуют шаблону на результат.</span><span class="sxs-lookup"><span data-stu-id="bbc65-130">The only exception to this is `match!`, which is itself syntactic sugar for the use of `let!` followed by a pattern match on the result.</span></span>

<span data-ttu-id="bbc65-131">Тип построителя — это объект, определяющий специальные методы, которые управляют способом объединенные фрагменты вычислительного выражения; то есть его методы управления, работой вычислительного выражения.</span><span class="sxs-lookup"><span data-stu-id="bbc65-131">The builder type is an object that defines special methods that govern the way the fragments of the computation expression are combined; that is, its methods control how the computation expression behaves.</span></span> <span data-ttu-id="bbc65-132">Класс построителя другим способом является сказать, что он позволяет настраивать операцию многих F# конструкции, такие как циклы и привязки.</span><span class="sxs-lookup"><span data-stu-id="bbc65-132">Another way to describe a builder class is to say that it enables you to customize the operation of many F# constructs, such as loops and bindings.</span></span>

### `let!`

<span data-ttu-id="bbc65-133">`let!` Ключевое слово привязывает результат вызова другого выражения вычисления с именем:</span><span class="sxs-lookup"><span data-stu-id="bbc65-133">The `let!` keyword binds the result of a call to another computation expression to a name:</span></span>

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

<span data-ttu-id="bbc65-134">Привязка вызов вычислительного выражения с `let`, вы не получите результат вычисления выражения.</span><span class="sxs-lookup"><span data-stu-id="bbc65-134">If you bind the call to a computation expression with `let`, you will not get the result of the computation expression.</span></span> <span data-ttu-id="bbc65-135">Вместо этого будет привязано значение *нереализованных* вызвать для этого вычисления выражения.</span><span class="sxs-lookup"><span data-stu-id="bbc65-135">Instead, you will have bound the value of the *unrealized* call to that computation expression.</span></span> <span data-ttu-id="bbc65-136">Используйте `let!` для привязки к результату.</span><span class="sxs-lookup"><span data-stu-id="bbc65-136">Use `let!` to bind to the result.</span></span>

<span data-ttu-id="bbc65-137">`let!` определяется `Bind(x, f)` элемент для типа построителя.</span><span class="sxs-lookup"><span data-stu-id="bbc65-137">`let!` is defined by the `Bind(x, f)` member on the builder type.</span></span>

### `do!`

<span data-ttu-id="bbc65-138">`do!` Ключевое слово является для вызов вычислительного выражения, которая возвращает `unit`-тип, такие как (определяется `Zero` член в построителе):</span><span class="sxs-lookup"><span data-stu-id="bbc65-138">The `do!` keyword is for calling a computation expression that returns a `unit`-like type (defined by the `Zero` member on the builder):</span></span>

```fsharp
let doThingsAsync data url =
    async {
        do! submitData data url
        ...
    }
```

<span data-ttu-id="bbc65-139">Для [асинхронный рабочий процесс](asynchronous-workflows.md), этот тип является `Async<unit>`.</span><span class="sxs-lookup"><span data-stu-id="bbc65-139">For the [async workflow](asynchronous-workflows.md), this type is `Async<unit>`.</span></span> <span data-ttu-id="bbc65-140">Для других вычислительных выражениях, вероятно, будет тип `CExpType<unit>`.</span><span class="sxs-lookup"><span data-stu-id="bbc65-140">For other computation expressions, the type is likely to be `CExpType<unit>`.</span></span>

<span data-ttu-id="bbc65-141">`do!` определяется `Bind(x, f)` члену в тип построителя, где `f` создает `unit`.</span><span class="sxs-lookup"><span data-stu-id="bbc65-141">`do!` is defined by the `Bind(x, f)` member on the builder type, where `f` produces a `unit`.</span></span>

### `yield`

<span data-ttu-id="bbc65-142">`yield` Ключевое слово является для возврата значения из вычислительного выражения таким образом, чтобы он мог использоваться в качестве <xref:System.Collections.Generic.IEnumerable%601>:</span><span class="sxs-lookup"><span data-stu-id="bbc65-142">The `yield` keyword is for returning a value from the computation expression so that it can be consumed as an <xref:System.Collections.Generic.IEnumerable%601>:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

<span data-ttu-id="bbc65-143">Как и в [yield-ключевое слово в C#](../../csharp/language-reference/keywords/yield.md), каждый элемент в вычислительном выражении передается обратно в том случае, как будет выполнен.</span><span class="sxs-lookup"><span data-stu-id="bbc65-143">As with the [yield keyword in C#](../../csharp/language-reference/keywords/yield.md), each element in the computation expression is yielded back as it is iterated.</span></span>

<span data-ttu-id="bbc65-144">`yield` определяется `Yield(x)` члену в тип построителя, где `x` является элементом, чтобы получить обратно.</span><span class="sxs-lookup"><span data-stu-id="bbc65-144">`yield` is defined by the `Yield(x)` member on the builder type, where `x` is the item to yield back.</span></span>

### `yield!`

<span data-ttu-id="bbc65-145">`yield!` Ключевое слово является выравнивания коллекция значений из вычислительного выражения:</span><span class="sxs-lookup"><span data-stu-id="bbc65-145">The `yield!` keyword is for flattening a collection of values from a computation expression:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..3 -> i * i
    }

let cubes =
    seq {
        for i in 1..3 -> i * i * i
    }

let squaresAndCubes =
    seq {
        yield! squares
        yield! cubes
    }

printfn "%A" squaresAndCubes // Prints - 1; 4; 9; 1; 8; 27
```

<span data-ttu-id="bbc65-146">Вызывается при вычислении выражения вычисления `yield!` будет иметь свои элементы, полученная назад по одному, выравнивание результата.</span><span class="sxs-lookup"><span data-stu-id="bbc65-146">When evaluated, the computation expression called by `yield!` will have its items yielded back one-by-one, flattening the result.</span></span>

<span data-ttu-id="bbc65-147">`yield!` определяется `YieldFrom(x)` члену в тип построителя, где `x` является коллекцией значений.</span><span class="sxs-lookup"><span data-stu-id="bbc65-147">`yield!` is defined by the `YieldFrom(x)` member on the builder type, where `x` is a collection of values.</span></span>

### `return`

<span data-ttu-id="bbc65-148">`return` Ключевое слово заключает значение в тип, соответствующий вычислительного выражения.</span><span class="sxs-lookup"><span data-stu-id="bbc65-148">The `return` keyword wraps a value in the type corresponding to the computation expression.</span></span> <span data-ttu-id="bbc65-149">Помимо вычисления выражений, с помощью `yield`, он используется на «выполнено» вычислительного выражения:</span><span class="sxs-lookup"><span data-stu-id="bbc65-149">Aside from computation expressions using `yield`, it is used to "complete" a computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="bbc65-150">`return` определяется `Return(x)` члену в тип построителя, где `x` — это элемент программы-оболочки.</span><span class="sxs-lookup"><span data-stu-id="bbc65-150">`return` is defined by the `Return(x)` member on the builder type, where `x` is the item to wrap.</span></span>

### `return!`

<span data-ttu-id="bbc65-151">`return!` Ключевое слово понимает, что значение выражения вычисления и помещает результат в тип, соответствующий вычислительное выражение:</span><span class="sxs-lookup"><span data-stu-id="bbc65-151">The `return!` keyword realizes the value of a computation expression and wraps that result in the type corresponding to the computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="bbc65-152">`return!` определяется `ReturnFrom(x)` члену в тип построителя, где `x` является другой вычислительного выражения.</span><span class="sxs-lookup"><span data-stu-id="bbc65-152">`return!` is defined by the `ReturnFrom(x)` member on the builder type, where `x` is another computation expression.</span></span>

### `match!`

<span data-ttu-id="bbc65-153">Начиная с F# 4.5, `match!` ключевое слово позволяет встроенный вызов другой вычисления выражений и шаблон сопоставления по его результат:</span><span class="sxs-lookup"><span data-stu-id="bbc65-153">Starting with F# 4.5, the `match!` keyword allows you to inline a call to another computation expression and pattern match on its result:</span></span>

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

<span data-ttu-id="bbc65-154">При вызове вычислительного выражения с `match!`, он увидит, результат вызова как `let!`.</span><span class="sxs-lookup"><span data-stu-id="bbc65-154">When calling a computation expression with `match!`, it will realize the result of the call like `let!`.</span></span> <span data-ttu-id="bbc65-155">Это часто используется при вызове вычислительного выражения, результат [необязательно](options.md).</span><span class="sxs-lookup"><span data-stu-id="bbc65-155">This is often used when calling a computation expression where the result is an [optional](options.md).</span></span>

## <a name="built-in-computation-expressions"></a><span data-ttu-id="bbc65-156">Встроенные вычислительные выражения</span><span class="sxs-lookup"><span data-stu-id="bbc65-156">Built-in computation expressions</span></span>

<span data-ttu-id="bbc65-157">F# Библиотека ядра определяет три встроенных вычисление выражения: [Последовательность выражений](sequences.md), [асинхронные рабочие потоки](asynchronous-workflows.md), и [выражения запросов](query-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="bbc65-157">The F# core library defines three built-in computation expressions: [Sequence Expressions](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Query Expressions](query-expressions.md).</span></span>

## <a name="creating-a-new-type-of-computation-expression"></a><span data-ttu-id="bbc65-158">Создание нового типа вычислительного выражения</span><span class="sxs-lookup"><span data-stu-id="bbc65-158">Creating a New Type of Computation Expression</span></span>

<span data-ttu-id="bbc65-159">Можно определить характеристики собственных вычислительных выражений, создав класс построителя и определив специальные методы в классе.</span><span class="sxs-lookup"><span data-stu-id="bbc65-159">You can define the characteristics of your own computation expressions by creating a builder class and defining certain special methods on the class.</span></span> <span data-ttu-id="bbc65-160">Класс построителя при необходимости можно определить методы, перечисленные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="bbc65-160">The builder class can optionally define the methods as listed in the following table.</span></span>

<span data-ttu-id="bbc65-161">Ниже перечислены методы, которые могут использоваться в классе построитель рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="bbc65-161">The following table describes methods that can be used in a workflow builder class.</span></span>

|<span data-ttu-id="bbc65-162">**Метод**</span><span class="sxs-lookup"><span data-stu-id="bbc65-162">**Method**</span></span>|<span data-ttu-id="bbc65-163">**Типичные сигнатуры**</span><span class="sxs-lookup"><span data-stu-id="bbc65-163">**Typical signature(s)**</span></span>|<span data-ttu-id="bbc65-164">**Описание**</span><span class="sxs-lookup"><span data-stu-id="bbc65-164">**Description**</span></span>|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|<span data-ttu-id="bbc65-165">Вызывается для `let!` и `do!` в вычислительные выражения.</span><span class="sxs-lookup"><span data-stu-id="bbc65-165">Called for `let!` and `do!` in computation expressions.</span></span>|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|<span data-ttu-id="bbc65-166">Создает оболочку вычислительного выражения в виде функции.</span><span class="sxs-lookup"><span data-stu-id="bbc65-166">Wraps a computation expression as a function.</span></span>|
|`Return`|`'T -> M<'T>`|<span data-ttu-id="bbc65-167">Вызывается для `return` в вычислительные выражения.</span><span class="sxs-lookup"><span data-stu-id="bbc65-167">Called for `return` in computation expressions.</span></span>|
|`ReturnFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="bbc65-168">Вызывается для `return!` в вычислительные выражения.</span><span class="sxs-lookup"><span data-stu-id="bbc65-168">Called for `return!` in computation expressions.</span></span>|
|`Run`|<span data-ttu-id="bbc65-169">`M<'T> -> M<'T>` или</span><span class="sxs-lookup"><span data-stu-id="bbc65-169">`M<'T> -> M<'T>` or</span></span><br /><br />`M<'T> -> 'T`|<span data-ttu-id="bbc65-170">Выполняет выражение вычисления.</span><span class="sxs-lookup"><span data-stu-id="bbc65-170">Executes a computation expression.</span></span>|
|`Combine`|<span data-ttu-id="bbc65-171">`M<'T> * M<'T> -> M<'T>` или</span><span class="sxs-lookup"><span data-stu-id="bbc65-171">`M<'T> * M<'T> -> M<'T>` or</span></span><br /><br />`M<unit> * M<'T> -> M<'T>`|<span data-ttu-id="bbc65-172">Вызывается для последовательности в вычислительные выражения.</span><span class="sxs-lookup"><span data-stu-id="bbc65-172">Called for sequencing in computation expressions.</span></span>|
|`For`|<span data-ttu-id="bbc65-173">`seq<'T> * ('T -> M<'U>) -> M<'U>` или</span><span class="sxs-lookup"><span data-stu-id="bbc65-173">`seq<'T> * ('T -> M<'U>) -> M<'U>` or</span></span><br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|<span data-ttu-id="bbc65-174">Вызывается для `for...do` в вычислительных выражениях.</span><span class="sxs-lookup"><span data-stu-id="bbc65-174">Called for `for...do` expressions in computation expressions.</span></span>|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|<span data-ttu-id="bbc65-175">Вызывается для `try...finally` в вычислительных выражениях.</span><span class="sxs-lookup"><span data-stu-id="bbc65-175">Called for `try...finally` expressions in computation expressions.</span></span>|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|<span data-ttu-id="bbc65-176">Вызывается для `try...with` в вычислительных выражениях.</span><span class="sxs-lookup"><span data-stu-id="bbc65-176">Called for `try...with` expressions in computation expressions.</span></span>|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'U :> IDisposable`|<span data-ttu-id="bbc65-177">Вызывается для `use` привязок в вычислительные выражения.</span><span class="sxs-lookup"><span data-stu-id="bbc65-177">Called for `use` bindings in computation expressions.</span></span>|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|<span data-ttu-id="bbc65-178">Вызывается для `while...do` в вычислительных выражениях.</span><span class="sxs-lookup"><span data-stu-id="bbc65-178">Called for `while...do` expressions in computation expressions.</span></span>|
|`Yield`|`'T -> M<'T>`|<span data-ttu-id="bbc65-179">Вызывается для `yield` в вычислительных выражениях.</span><span class="sxs-lookup"><span data-stu-id="bbc65-179">Called for `yield` expressions in computation expressions.</span></span>|
|`YieldFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="bbc65-180">Вызывается для `yield!` в вычислительных выражениях.</span><span class="sxs-lookup"><span data-stu-id="bbc65-180">Called for `yield!` expressions in computation expressions.</span></span>|
|`Zero`|`unit -> M<'T>`|<span data-ttu-id="bbc65-181">Вызывается для пустых `else` ветвей `if...then` в вычислительных выражениях.</span><span class="sxs-lookup"><span data-stu-id="bbc65-181">Called for empty `else` branches of `if...then` expressions in computation expressions.</span></span>|
|`Quote`|`Quotations.Expr<'T> -> Quotations.Expr<'T>`|<span data-ttu-id="bbc65-182">Указывает, что вычислительное выражение передается `Run` член как предложения.</span><span class="sxs-lookup"><span data-stu-id="bbc65-182">Indicates that the computation expression is passed to the `Run` member as a quotation.</span></span> <span data-ttu-id="bbc65-183">Он преобразует все экземпляры вычислительных ресурсов, в кавычки.</span><span class="sxs-lookup"><span data-stu-id="bbc65-183">It translates all instances of a computation into a quotation.</span></span>|

<span data-ttu-id="bbc65-184">Многие методы в класс построителя используют и возвращают `M<'T>` construct, который обычно представляет собой отдельно определенный тип, характеризующий вид объединяемых вычислений, например, `Async<'T>` асинхронные рабочие процессы и `Seq<'T>` для рабочих процессов последовательности.</span><span class="sxs-lookup"><span data-stu-id="bbc65-184">Many of the methods in a builder class use and return an `M<'T>` construct, which is typically a separately defined type that characterizes the kind of computations being combined, for example, `Async<'T>` for asynchronous workflows and `Seq<'T>` for sequence workflows.</span></span> <span data-ttu-id="bbc65-185">Сигнатуры методов включите их следует объединить и вложенными друг с другом, для объекта рабочего процесса, возвращаемых из одной конструкции, которые могут передаваться на следующий.</span><span class="sxs-lookup"><span data-stu-id="bbc65-185">The signatures of these methods enable them to be combined and nested with each other, so that the workflow object returned from one construct can be passed to the next.</span></span> <span data-ttu-id="bbc65-186">Когда компилятор анализирует вычислительное выражение, преобразует выражение в серию вложенные вызовы функций с помощью методов в приведенной выше таблице и код в вычислительном выражении.</span><span class="sxs-lookup"><span data-stu-id="bbc65-186">The compiler, when it parses a computation expression, converts the expression into a series of nested function calls by using the methods in the preceding table and the code in the computation expression.</span></span>

<span data-ttu-id="bbc65-187">Вложенное выражение имеет следующую форму:</span><span class="sxs-lookup"><span data-stu-id="bbc65-187">The nested expression is of the following form:</span></span>

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

<span data-ttu-id="bbc65-188">В приведенном выше коде вызовы `Run` и `Delay` пропускаются, если они не определены в классе построитель вычисления выражения.</span><span class="sxs-lookup"><span data-stu-id="bbc65-188">In the above code, the calls to `Run` and `Delay` are omitted if they are not defined in the computation expression builder class.</span></span> <span data-ttu-id="bbc65-189">Тело выражения вычисление, обозначенное здесь как `{| cexpr |}`, преобразуется в вызовы с участием методов класса построителя посредством преобразований, приведенных в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="bbc65-189">The body of the computation expression, here denoted as `{| cexpr |}`, is translated into calls involving the methods of the builder class by the translations described in the following table.</span></span> <span data-ttu-id="bbc65-190">Вычислительное выражение `{| cexpr |}` определяется рекурсивно в соответствии с этих переводов где `expr` — F# выражение и `cexpr` представляет собой выражение вычисления.</span><span class="sxs-lookup"><span data-stu-id="bbc65-190">The computation expression `{| cexpr |}` is defined recursively according to these translations where `expr` is an F# expression and `cexpr` is a computation expression.</span></span>

|<span data-ttu-id="bbc65-191">Выражение</span><span class="sxs-lookup"><span data-stu-id="bbc65-191">Expression</span></span>|<span data-ttu-id="bbc65-192">Перевод</span><span class="sxs-lookup"><span data-stu-id="bbc65-192">Translation</span></span>|
|----------|-----------|
|<code>{&#124; let binding in cexpr &#124;}</code>|<code>let binding in {&#124; cexpr &#124;}</code>|
|<code>{&#124; let! pattern = expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; do! expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun () -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; yield expr &#124;}</code>|`builder.Yield(expr)`|
|<code>{&#124; yield! expr &#124;}</code>|`builder.YieldFrom(expr)`|
|<code>{&#124; return expr &#124;}</code>|`builder.Return(expr)`|
|<code>{&#124; return! expr &#124;}</code>|`builder.ReturnFrom(expr)`|
|<code>{&#124; use pattern = expr in cexpr &#124;}</code>|<code>builder.Using(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; use! value = expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun value -> builder.Using(value, (fun value -> {&#124; cexpr &#124;}))))</code>|
|<code>{&#124; if expr then cexpr0 &#124;}</code>|<code>if expr then {&#124; cexpr0 &#124;} else binder.Zero()</code>|
|<code>{&#124; if expr then cexpr0 else cexpr1 &#124;}</code>|<code>if expr then {&#124; cexpr0 &#124;} else {&#124; cexpr1 &#124;}</code>|
|<code>{&#124; match expr with &#124; pattern_i -> cexpr_i &#124;}</code>|<code>match expr with &#124; pattern_i -> {&#124; cexpr_i &#124;}</code>|
|<code>{&#124; for pattern in expr do cexpr &#124;}</code>|<code>builder.For(enumeration, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; for identifier = expr1 to expr2 do cexpr &#124;}</code>|<code>builder.For(enumeration, (fun identifier -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; while expr do cexpr &#124;}</code>|<code>builder.While(fun () -> expr), builder.Delay({&#124;cexpr &#124;})</code>|
|<code>{&#124; try cexpr with &#124; pattern_i -> expr_i &#124;}</code>|<code>builder.TryWith(builder.Delay({&#124; cexpr &#124;}), (fun value -> match value with &#124; pattern_i -> expr_i &#124; exn -> reraise exn)))</code>|
|<code>{&#124; try cexpr finally expr &#124;}</code>|<code>builder.TryFinally(builder.Delay( {&#124; cexpr &#124;}), (fun () -> expr))</code>|
|<code>{&#124; cexpr1; cexpr2 &#124;}</code>|<code>builder.Combine({&#124;cexpr1 &#124;}, {&#124; cexpr2 &#124;})</code>|
|<code>{&#124; other-expr; cexpr &#124;}</code>|<code>expr; {&#124; cexpr &#124;}</code>|
|<code>{&#124; other-expr &#124;}</code>|`expr; builder.Zero()`|

<span data-ttu-id="bbc65-193">В предыдущей таблице `other-expr` соответствует выражению, в противном случае отсутствует в таблице.</span><span class="sxs-lookup"><span data-stu-id="bbc65-193">In the previous table, `other-expr` describes an expression that is not otherwise listed in the table.</span></span> <span data-ttu-id="bbc65-194">Класс построителя не требуется реализовывать все методы обеспечения поддержки преобразований, приведенных в предыдущей таблице.</span><span class="sxs-lookup"><span data-stu-id="bbc65-194">A builder class does not need to implement all of the methods and support all of the translations listed in the previous table.</span></span> <span data-ttu-id="bbc65-195">Эти конструкции, которые не реализованы недоступны в вычислительные выражения этого типа.</span><span class="sxs-lookup"><span data-stu-id="bbc65-195">Those constructs that are not implemented are not available in computation expressions of that type.</span></span> <span data-ttu-id="bbc65-196">Например, если вы не хотите поддерживать `use` ключевое слово в вычисление выражения, можно опустить определение `Use` в классе построителя.</span><span class="sxs-lookup"><span data-stu-id="bbc65-196">For example, if you do not want to support the `use` keyword in your computation expressions, you can omit the definition of `Use` in your builder class.</span></span>

<span data-ttu-id="bbc65-197">В следующем примере кода показано выражение вычисления, инкапсулирующий вычисление вычисленному один шаг ряд шагов, которые могут быть одновременно.</span><span class="sxs-lookup"><span data-stu-id="bbc65-197">The following code example shows a computation expression that encapsulates a computation as a series of steps that can be evaluated one step at a time.</span></span> <span data-ttu-id="bbc65-198">Объект размеченные объединения типа `OkOrException`, кодирует состояние ошибки, выражения, вычисленному на данный момент.</span><span class="sxs-lookup"><span data-stu-id="bbc65-198">A discriminated union type, `OkOrException`, encodes the error state of the expression as evaluated so far.</span></span> <span data-ttu-id="bbc65-199">Этот код демонстрирует несколько типичных шаблонов, которые можно использовать в выражениях вычисления, такие как стандартный реализации некоторых методов построителя.</span><span class="sxs-lookup"><span data-stu-id="bbc65-199">This code demonstrates several typical patterns that you can use in your computation expressions, such as boilerplate implementations of some of the builder methods.</span></span>

```fsharp
// Computations that can be run step by step
type Eventually<'T> =
    | Done of 'T
    | NotYetDone of (unit -> Eventually<'T>)

module Eventually =
    // The bind for the computations. Append 'func' to the
    // computation.
    let rec bind func expr =
        match expr with
        | Done value -> func value
        | NotYetDone work -> NotYetDone (fun () -> bind func (work()))

    // Return the final value wrapped in the Eventually type.
    let result value = Done value

    type OkOrException<'T> =
        | Ok of 'T
        | Exception of System.Exception

    // The catch for the computations. Stitch try/with throughout
    // the computation, and return the overall result as an OkOrException.
    let rec catch expr =
        match expr with
        | Done value -> result (Ok value)
        | NotYetDone work ->
            NotYetDone (fun () ->
                let res = try Ok(work()) with | exn -> Exception exn
                match res with
                | Ok cont -> catch cont // note, a tailcall
                | Exception exn -> result (Exception exn))

    // The delay operator.
    let delay func = NotYetDone (fun () -> func())

    // The stepping action for the computations.
    let step expr =
        match expr with
        | Done _ -> expr
        | NotYetDone func -> func ()

    // The rest of the operations are boilerplate.
    // The tryFinally operator.
    // This is boilerplate in terms of "result", "catch", and "bind".
    let tryFinally expr compensation =
        catch (expr)
        |> bind (fun res -> 
            compensation();
            match res with
            | Ok value -> result value
            | Exception exn -> raise exn)

    // The tryWith operator.
    // This is boilerplate in terms of "result", "catch", and "bind".
    let tryWith exn handler =
        catch exn
        |> bind (function Ok value -> result value | Exception exn -> handler exn)

    // The whileLoop operator.
    // This is boilerplate in terms of "result" and "bind".
    let rec whileLoop pred body =
        if pred() then body |> bind (fun _ -> whileLoop pred body)
        else result ()

    // The sequential composition operator.
    // This is boilerplate in terms of "result" and "bind".
    let combine expr1 expr2 =
        expr1 |> bind (fun () -> expr2)

    // The using operator.
    let using (resource: #System.IDisposable) func =
        tryFinally (func resource) (fun () -> resource.Dispose())

    // The forLoop operator.
    // This is boilerplate in terms of "catch", "result", and "bind".
    let forLoop (collection:seq<_>) func =
        let ie = collection.GetEnumerator()
        tryFinally 
            (whileLoop 
                (fun () -> ie.MoveNext()) 
                (delay (fun () -> let value = ie.Current in func value)))
            (fun () -> ie.Dispose())

// The builder class.
type EventuallyBuilder() =
    member x.Bind(comp, func) = Eventually.bind func comp
    member x.Return(value) = Eventually.result value
    member x.ReturnFrom(value) = value
    member x.Combine(expr1, expr2) = Eventually.combine expr1 expr2
    member x.Delay(func) = Eventually.delay func
    member x.Zero() = Eventually.result ()
    member x.TryWith(expr, handler) = Eventually.tryWith expr handler
    member x.TryFinally(expr, compensation) = Eventually.tryFinally expr compensation
    member x.For(coll:seq<_>, func) = Eventually.forLoop coll func
    member x.Using(resource, expr) = Eventually.using resource expr

let eventually = new EventuallyBuilder()

let comp = eventually {
    for x in 1..2 do
        printfn " x = %d" x
    return 3 + 4 }

// Try the remaining lines in F# interactive to see how this
// computation expression works in practice.
let step x = Eventually.step x

// returns "NotYetDone <closure>"
comp |> step

// prints "x = 1"
// returns "NotYetDone <closure>"
comp |> step |> step

// prints "x = 1"
// prints "x = 2"
// returns "Done 7"
comp |> step |> step |> step |> step 
```

<span data-ttu-id="bbc65-200">Вычислительное выражение имеет базовый тип, который возвращает выражение.</span><span class="sxs-lookup"><span data-stu-id="bbc65-200">A computation expression has an underlying type, which the expression returns.</span></span> <span data-ttu-id="bbc65-201">Базовый тип может представлять вычисленный результат или отложенное вычисление, которое может быть выполнена, или обеспечивают способ итерации по коллекции какого-либо рода.</span><span class="sxs-lookup"><span data-stu-id="bbc65-201">The underlying type may represent a computed result or a delayed computation that can be performed, or it may provide a way to iterate through some type of collection.</span></span> <span data-ttu-id="bbc65-202">В предыдущем примере, был базовый тип **со временем**.</span><span class="sxs-lookup"><span data-stu-id="bbc65-202">In the previous example, the underlying type was **Eventually**.</span></span> <span data-ttu-id="bbc65-203">Для выражения последовательности, базовым типом является <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bbc65-203">For a sequence expression, the underlying type is <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="bbc65-204">Для выражения запроса, базовым типом является <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bbc65-204">For a query expression, the underlying type is <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="bbc65-205">Для асинхронных рабочих процессов, базовым типом является [ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span><span class="sxs-lookup"><span data-stu-id="bbc65-205">For an asynchronous workflow, the underlying type is [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span></span> <span data-ttu-id="bbc65-206">`Async` Объект представляет работу, выполняемую для вычисления результата.</span><span class="sxs-lookup"><span data-stu-id="bbc65-206">The `Async` object represents the work to be performed to compute the result.</span></span> <span data-ttu-id="bbc65-207">Например, можно вызвать метод [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) для выполнения вычислений и возвращают результат.</span><span class="sxs-lookup"><span data-stu-id="bbc65-207">For example, you call [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) to execute a computation and return the result.</span></span>

## <a name="custom-operations"></a><span data-ttu-id="bbc65-208">Пользовательские операции</span><span class="sxs-lookup"><span data-stu-id="bbc65-208">Custom Operations</span></span>

<span data-ttu-id="bbc65-209">Можно определить пользовательскую операцию вычисления выражения и использовать пользовательскую операцию в качестве оператора в выражение вычисления.</span><span class="sxs-lookup"><span data-stu-id="bbc65-209">You can define a custom operation on a computation expression and use a custom operation as an operator in a computation expression.</span></span> <span data-ttu-id="bbc65-210">Например можно включить оператор запроса в выражении запроса.</span><span class="sxs-lookup"><span data-stu-id="bbc65-210">For example, you can include a query operator in a query expression.</span></span> <span data-ttu-id="bbc65-211">При определении пользовательской операции, необходимо определить доход и для методов в выражение вычисления.</span><span class="sxs-lookup"><span data-stu-id="bbc65-211">When you define a custom operation, you must define the Yield and For methods in the computation expression.</span></span> <span data-ttu-id="bbc65-212">Чтобы определить пользовательскую операцию, поместить его в класс построителя для вычисления выражения, а затем применить [ `CustomOperationAttribute` ](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span><span class="sxs-lookup"><span data-stu-id="bbc65-212">To define a custom operation, put it in a builder class for the computation expression, and then apply the [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span></span> <span data-ttu-id="bbc65-213">Этот атрибут принимает строку в качестве аргумента, которое является именем для использования в пользовательской операции.</span><span class="sxs-lookup"><span data-stu-id="bbc65-213">This attribute takes a string as an argument, which is the name to be used in a custom operation.</span></span> <span data-ttu-id="bbc65-214">Это имя поступает в область действия в начале открывающая фигурная скобка вычислительного выражения.</span><span class="sxs-lookup"><span data-stu-id="bbc65-214">This name comes into scope at the start of the opening curly brace of the computation expression.</span></span> <span data-ttu-id="bbc65-215">Таким образом не следует использовать идентификаторы, которые имеют имя, совпадающее с именем пользовательской операции в этом блоке.</span><span class="sxs-lookup"><span data-stu-id="bbc65-215">Therefore, you shouldn’t use identifiers that have the same name as a custom operation in this block.</span></span> <span data-ttu-id="bbc65-216">Например, такие как избежать использования идентификаторов `all` или `last` в выражениях запросов.</span><span class="sxs-lookup"><span data-stu-id="bbc65-216">For example, avoid the use of identifiers such as `all` or `last` in query expressions.</span></span>

### <a name="extending-existing-builders-with-new-custom-operations"></a><span data-ttu-id="bbc65-217">Расширение существующего построители с новых пользовательских операций</span><span class="sxs-lookup"><span data-stu-id="bbc65-217">Extending existing Builders with new Custom Operations</span></span>

<span data-ttu-id="bbc65-218">Если у вас уже есть класс построителя, можно расширить его пользовательских операций из вне данного класса построителя.</span><span class="sxs-lookup"><span data-stu-id="bbc65-218">If you already have a builder class, its custom operations can be extended from outside of this builder class.</span></span> <span data-ttu-id="bbc65-219">Расширения необходимо объявлять в модулях.</span><span class="sxs-lookup"><span data-stu-id="bbc65-219">Extensions must be declared in modules.</span></span> <span data-ttu-id="bbc65-220">Пространства имен не может содержать члены расширений, за исключением в файле одной и той же группе объявление пространства имен, где определен тип.</span><span class="sxs-lookup"><span data-stu-id="bbc65-220">Namespaces cannot contain extension members except in the same file and the same namespace declaration group where the type is defined.</span></span>

<span data-ttu-id="bbc65-221">В следующем примере показано расширение существующего `Microsoft.FSharp.Linq.QueryBuilder` класса.</span><span class="sxs-lookup"><span data-stu-id="bbc65-221">The following example shows the extension of the existing `Microsoft.FSharp.Linq.QueryBuilder` class.</span></span>

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member __.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a><span data-ttu-id="bbc65-222">См. также</span><span class="sxs-lookup"><span data-stu-id="bbc65-222">See also</span></span>

- [<span data-ttu-id="bbc65-223">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="bbc65-223">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="bbc65-224">Асинхронные рабочие потоки</span><span class="sxs-lookup"><span data-stu-id="bbc65-224">Asynchronous Workflows</span></span>](asynchronous-workflows.md)
- [<span data-ttu-id="bbc65-225">Последовательности</span><span class="sxs-lookup"><span data-stu-id="bbc65-225">Sequences</span></span>](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)
- [<span data-ttu-id="bbc65-226">Выражения запросов</span><span class="sxs-lookup"><span data-stu-id="bbc65-226">Query Expressions</span></span>](query-expressions.md)
