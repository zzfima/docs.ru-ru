---
title: Выражения вычисления
description: Узнайте, как создать удобный синтаксис для написания вычислений в ФЗ, которые можно секвенировать и комбинировать с помощью конструкций и привязок потоков управления.
ms.date: 11/04/2019
ms.openlocfilehash: 55406cc12d9e6e890fe69d712f79486d23b84452
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401085"
---
# <a name="computation-expressions"></a><span data-ttu-id="2e5a9-103">Выражения вычисления</span><span class="sxs-lookup"><span data-stu-id="2e5a9-103">Computation Expressions</span></span>

<span data-ttu-id="2e5a9-104">Выражения вычислений в F-образном варианте обеспечивают удобный синтаксис для написания вычислений, которые можно секвенировать и комбинировать с помощью конструкций и переплетов потоков управления.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-104">Computation expressions in F# provide a convenient syntax for writing computations that can be sequenced and combined using control flow constructs and bindings.</span></span> <span data-ttu-id="2e5a9-105">В зависимости от вида вычислительного выражения, их можно рассматривать как способ выражения монад, моноиды, монадные трансформаторы и применимые фанкторы.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-105">Depending on the kind of computation expression, they can be thought of as a way to express monads, monoids, monad transformers, and applicative functors.</span></span> <span data-ttu-id="2e5a9-106">Однако, в отличие от других языков (таких как *do-notation* в Haskell), они не привязаны к одной абстракции, и не полагаются на макросы или другие формы метапрограммирования для выполнения удобного и чувствительного к контексту синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-106">However, unlike other languages (such as *do-notation* in Haskell), they are not tied to a single abstraction, and do not rely on macros or other forms of metaprogramming to accomplish a convenient and context-sensitive syntax.</span></span>

## <a name="overview"></a><span data-ttu-id="2e5a9-107">Обзор</span><span class="sxs-lookup"><span data-stu-id="2e5a9-107">Overview</span></span>

<span data-ttu-id="2e5a9-108">Вычисления могут принимать различные формы.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-108">Computations can take many forms.</span></span> <span data-ttu-id="2e5a9-109">Наиболее распространенной формой вычислений является однопоточное выполнение, которое легко понять и изменить.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-109">The most common form of computation is single-threaded execution, which is easy to understand and modify.</span></span> <span data-ttu-id="2e5a9-110">Однако не все формы вычислений так просты, как однопоточное выполнение.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-110">However, not all forms of computation are as straightforward as single-threaded execution.</span></span> <span data-ttu-id="2e5a9-111">Некоторые примеры:</span><span class="sxs-lookup"><span data-stu-id="2e5a9-111">Some examples include:</span></span>

- <span data-ttu-id="2e5a9-112">Недетерминированные вычисления</span><span class="sxs-lookup"><span data-stu-id="2e5a9-112">Non-deterministic computations</span></span>
- <span data-ttu-id="2e5a9-113">Асинхронные вычисления</span><span class="sxs-lookup"><span data-stu-id="2e5a9-113">Asynchronous computations</span></span>
- <span data-ttu-id="2e5a9-114">Эффективные вычисления</span><span class="sxs-lookup"><span data-stu-id="2e5a9-114">Effectful computations</span></span>
- <span data-ttu-id="2e5a9-115">Генеративные вычисления</span><span class="sxs-lookup"><span data-stu-id="2e5a9-115">Generative computations</span></span>

<span data-ttu-id="2e5a9-116">В более общем плане существуют чувствительные к *контексту* вычисления, которые необходимо выполнять в определенных частях приложения.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-116">More generally, there are *context-sensitive* computations that you must perform in certain parts of an application.</span></span> <span data-ttu-id="2e5a9-117">Написание чувствительного к контексту кода может быть сложной задачей, так как легко «утечка» вычислений за пределами данного контекста без абстракций, чтобы помешать вам сделать это.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-117">Writing context-sensitive code can be challenging, as it is easy to "leak" computations outside of a given context without abstractions to prevent you from doing so.</span></span> <span data-ttu-id="2e5a9-118">Эти абстракции часто сложно писать самостоятельно, поэтому у F-образного способа сделать так называемые **вычислительные выражения.**</span><span class="sxs-lookup"><span data-stu-id="2e5a9-118">These abstractions are often challenging to write by yourself, which is why F# has a generalized way to do so called **computation expressions**.</span></span>

<span data-ttu-id="2e5a9-119">Выражения вычислений предлагают единую модель синтаксиса и абстракции для кодирования чувствительных к контексту вычислений.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-119">Computation expressions offer a uniform syntax and abstraction model for encoding context-sensitive computations.</span></span>

<span data-ttu-id="2e5a9-120">Каждое выражение вычислений поддерживается типом *builder.*</span><span class="sxs-lookup"><span data-stu-id="2e5a9-120">Every computation expression is backed by a *builder* type.</span></span> <span data-ttu-id="2e5a9-121">Тип builder определяет операции, доступные для выражения вычислений.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-121">The builder type defines the operations that are available for the computation expression.</span></span> <span data-ttu-id="2e5a9-122">Смотрите [Создание нового типа выражения вычислений](computation-expressions.md#creating-a-new-type-of-computation-expression), который показывает, как создать пользовательское выражение вычислений.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-122">See [Creating a New Type of Computation Expression](computation-expressions.md#creating-a-new-type-of-computation-expression), which shows how to create a custom computation expression.</span></span>

### <a name="syntax-overview"></a><span data-ttu-id="2e5a9-123">Общие сведения о синтаксисе</span><span class="sxs-lookup"><span data-stu-id="2e5a9-123">Syntax overview</span></span>

<span data-ttu-id="2e5a9-124">Все вычислительные выражения имеют следующую форму:</span><span class="sxs-lookup"><span data-stu-id="2e5a9-124">All computation expressions have the following form:</span></span>

```fsharp
builder-expr { cexper }
```

<span data-ttu-id="2e5a9-125">где `builder-expr` находится имя типа builder, определяющего выражение вычислений, и `cexper` является выражением выражения вычислений.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-125">where `builder-expr` is the name of a builder type that defines the computation expression, and `cexper` is the expression body of the computation expression.</span></span> <span data-ttu-id="2e5a9-126">Например, `async` код выражения вычислений может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2e5a9-126">For example, `async` computation expression code can look like this:</span></span>

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

<span data-ttu-id="2e5a9-127">В вычислительном выражении имеется специальный дополнительный синтаксис, как показано в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-127">There is a special, additional syntax available within a computation expression, as shown in the previous example.</span></span> <span data-ttu-id="2e5a9-128">Возможны следующие формы выражения с помощью вычислительных выражений:</span><span class="sxs-lookup"><span data-stu-id="2e5a9-128">The following expression forms are possible with computation expressions:</span></span>

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

<span data-ttu-id="2e5a9-129">Каждое из этих ключевых слов и другие стандартные ключевые слова F's доступны только в выражении вычислений, если они были определены в типе резервного строителя.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-129">Each of these keywords, and other standard F# keywords are only available in a computation expression if they have been defined in the backing builder type.</span></span> <span data-ttu-id="2e5a9-130">Единственным исключением является, `match!`который сам по себе синтаксического сахара для использования `let!` следуют шаблон матч на результат.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-130">The only exception to this is `match!`, which is itself syntactic sugar for the use of `let!` followed by a pattern match on the result.</span></span>

<span data-ttu-id="2e5a9-131">Тип builder — это объект, определяющий специальные методы, определяющие способ объединения фрагментов выражения вычислений; то есть, его методы контролируют, как работает выражение вычислений.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-131">The builder type is an object that defines special methods that govern the way the fragments of the computation expression are combined; that is, its methods control how the computation expression behaves.</span></span> <span data-ttu-id="2e5a9-132">Другой способ описания класса builder заключается в том, чтобы сказать, что он позволяет настроить работу многих конструкций F, таких как петли и привязки.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-132">Another way to describe a builder class is to say that it enables you to customize the operation of many F# constructs, such as loops and bindings.</span></span>

### `let!`

<span data-ttu-id="2e5a9-133">Ключевое `let!` слово связывает результат вызова с другим выражением вычислений с именем:</span><span class="sxs-lookup"><span data-stu-id="2e5a9-133">The `let!` keyword binds the result of a call to another computation expression to a name:</span></span>

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

<span data-ttu-id="2e5a9-134">Если вы привяжете вызов `let`к экспрессии вычислений с, вы не получите результат выражения вычислений.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-134">If you bind the call to a computation expression with `let`, you will not get the result of the computation expression.</span></span> <span data-ttu-id="2e5a9-135">Вместо этого вы будете связаны значение *нереализованного* вызова, что выражение вычислений.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-135">Instead, you will have bound the value of the *unrealized* call to that computation expression.</span></span> <span data-ttu-id="2e5a9-136">Используйте `let!` для привязки к результату.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-136">Use `let!` to bind to the result.</span></span>

<span data-ttu-id="2e5a9-137">`let!`определяется `Bind(x, f)` участником по типу builder.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-137">`let!` is defined by the `Bind(x, f)` member on the builder type.</span></span>

### `do!`

<span data-ttu-id="2e5a9-138">Ключевое `do!` слово предназначено для вызова вычислительного выражения, которое возвращает `unit`тип типа -like (определяемый `Zero` участником в builder):</span><span class="sxs-lookup"><span data-stu-id="2e5a9-138">The `do!` keyword is for calling a computation expression that returns a `unit`-like type (defined by the `Zero` member on the builder):</span></span>

```fsharp
let doThingsAsync data url =
    async {
        do! submitData data url
        ...
    }
```

<span data-ttu-id="2e5a9-139">Для [рабочего процесса async](asynchronous-workflows.md) `Async<unit>`этот тип .</span><span class="sxs-lookup"><span data-stu-id="2e5a9-139">For the [async workflow](asynchronous-workflows.md), this type is `Async<unit>`.</span></span> <span data-ttu-id="2e5a9-140">Для других вычислений тип, скорее `CExpType<unit>`всего, будет .</span><span class="sxs-lookup"><span data-stu-id="2e5a9-140">For other computation expressions, the type is likely to be `CExpType<unit>`.</span></span>

<span data-ttu-id="2e5a9-141">`do!`определяется участником `Bind(x, f)` по типу `f` builder, `unit`где производится .</span><span class="sxs-lookup"><span data-stu-id="2e5a9-141">`do!` is defined by the `Bind(x, f)` member on the builder type, where `f` produces a `unit`.</span></span>

### `yield`

<span data-ttu-id="2e5a9-142">Ключевое `yield` слово предназначено для возвращения значения из выражения вычислений, <xref:System.Collections.Generic.IEnumerable%601>чтобы его можно было использовать как:</span><span class="sxs-lookup"><span data-stu-id="2e5a9-142">The `yield` keyword is for returning a value from the computation expression so that it can be consumed as an <xref:System.Collections.Generic.IEnumerable%601>:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

<span data-ttu-id="2e5a9-143">В большинстве случаев, он может быть опущен абонентов.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-143">In most cases, it can be omitted by callers.</span></span> <span data-ttu-id="2e5a9-144">Наиболее распространенный `yield` способ опустить это с оператором: `->`</span><span class="sxs-lookup"><span data-stu-id="2e5a9-144">The most common way to omit `yield` is with the `->` operator:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..10 -> i * i
    }

for sq in squares do
    printfn "%d" sq
```

<span data-ttu-id="2e5a9-145">Для более сложных выражений, которые могут дать много различных значений, и, возможно, условно, просто опуская ключевое слово может сделать:</span><span class="sxs-lookup"><span data-stu-id="2e5a9-145">For more complex expressions that might yield many different values, and perhaps conditionally, simply omitting the keyword can do:</span></span>

```fsharp
let weekdays includeWeekend =
    seq {
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then
            "Saturday"
            "Sunday"
    }
```

<span data-ttu-id="2e5a9-146">Как и в том, что ключевое [слово доходности в C,](../../csharp/language-reference/keywords/yield.md)каждый элемент в выражении вычислений возвращается, так как он итерирован.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-146">As with the [yield keyword in C#](../../csharp/language-reference/keywords/yield.md), each element in the computation expression is yielded back as it is iterated.</span></span>

<span data-ttu-id="2e5a9-147">`yield`определяется участником `Yield(x)` по типу `x` builder, где элемент должен уступить.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-147">`yield` is defined by the `Yield(x)` member on the builder type, where `x` is the item to yield back.</span></span>

### `yield!`

<span data-ttu-id="2e5a9-148">Ключевое `yield!` слово предназначено для выравнивания коллекции значений из вычислительного выражения:</span><span class="sxs-lookup"><span data-stu-id="2e5a9-148">The `yield!` keyword is for flattening a collection of values from a computation expression:</span></span>

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

<span data-ttu-id="2e5a9-149">При оценке вызываемые `yield!` выражения вычислений будут иметь свои элементы, которые будут отступать один за одним, уплощение результата.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-149">When evaluated, the computation expression called by `yield!` will have its items yielded back one-by-one, flattening the result.</span></span>

<span data-ttu-id="2e5a9-150">`yield!`определяется участником `YieldFrom(x)` по типу `x` builder, где находится собрание значений.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-150">`yield!` is defined by the `YieldFrom(x)` member on the builder type, where `x` is a collection of values.</span></span>

<span data-ttu-id="2e5a9-151">В `yield` `yield!` отличие от , должны быть четко указаны.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-151">Unlike `yield`, `yield!` must be explicitly specified.</span></span> <span data-ttu-id="2e5a9-152">Его поведение не подразумевается в выражениях вычислений.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-152">Its behavior isn't implicit in computation expressions.</span></span>

### `return`

<span data-ttu-id="2e5a9-153">Ключевое `return` слово обертывает значение в типе, соответствующем выражению вычислений.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-153">The `return` keyword wraps a value in the type corresponding to the computation expression.</span></span> <span data-ttu-id="2e5a9-154">Помимо использования `yield`вычислительных выражений, он используется для "завершения" вычислительного выражения:</span><span class="sxs-lookup"><span data-stu-id="2e5a9-154">Aside from computation expressions using `yield`, it is used to "complete" a computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="2e5a9-155">`return`определяется участником `Return(x)` на типе `x` builder, где находится элемент для обертывания.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-155">`return` is defined by the `Return(x)` member on the builder type, where `x` is the item to wrap.</span></span>

### `return!`

<span data-ttu-id="2e5a9-156">Ключевое `return!` слово реализует значение выражения вычислений и обертывания, которые приводят к типу, соответствующему выражению вычислений:</span><span class="sxs-lookup"><span data-stu-id="2e5a9-156">The `return!` keyword realizes the value of a computation expression and wraps that result in the type corresponding to the computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="2e5a9-157">`return!`определяется участником `ReturnFrom(x)` на типе `x` builder, где находится другое выражение вычислений.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-157">`return!` is defined by the `ReturnFrom(x)` member on the builder type, where `x` is another computation expression.</span></span>

### `match!`

<span data-ttu-id="2e5a9-158">Ключевое `match!` слово позволяет ввести вызов в другое выражение вычислений и шаблон соответствия по его результату:</span><span class="sxs-lookup"><span data-stu-id="2e5a9-158">The `match!` keyword allows you to inline a call to another computation expression and pattern match on its result:</span></span>

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

<span data-ttu-id="2e5a9-159">При вызове вычислительного `match!`выражения с помощью, он `let!`будет понимать результат вызова, как .</span><span class="sxs-lookup"><span data-stu-id="2e5a9-159">When calling a computation expression with `match!`, it will realize the result of the call like `let!`.</span></span> <span data-ttu-id="2e5a9-160">Это часто используется при вызове вычислительного выражения, где результат является [необязательным.](options.md)</span><span class="sxs-lookup"><span data-stu-id="2e5a9-160">This is often used when calling a computation expression where the result is an [optional](options.md).</span></span>

## <a name="built-in-computation-expressions"></a><span data-ttu-id="2e5a9-161">Встроенные вычислительные выражения</span><span class="sxs-lookup"><span data-stu-id="2e5a9-161">Built-in computation expressions</span></span>

<span data-ttu-id="2e5a9-162">В базовой библиотеке F-образной физики определены три встроенных вычисления: [экспрессии последовательности,](sequences.md) [асинхронные рабочие процессы](asynchronous-workflows.md)и [экспрессии запросов.](query-expressions.md)</span><span class="sxs-lookup"><span data-stu-id="2e5a9-162">The F# core library defines three built-in computation expressions: [Sequence Expressions](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Query Expressions](query-expressions.md).</span></span>

## <a name="creating-a-new-type-of-computation-expression"></a><span data-ttu-id="2e5a9-163">Создание нового типа вычислительного выражения</span><span class="sxs-lookup"><span data-stu-id="2e5a9-163">Creating a New Type of Computation Expression</span></span>

<span data-ttu-id="2e5a9-164">Характеристики собственных вычислений можно определить, создав класс строителя и определив определенные специальные методы в классе.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-164">You can define the characteristics of your own computation expressions by creating a builder class and defining certain special methods on the class.</span></span> <span data-ttu-id="2e5a9-165">Класс builder может дополнительно определить методы, перечисленные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-165">The builder class can optionally define the methods as listed in the following table.</span></span>

<span data-ttu-id="2e5a9-166">В следующей таблице описаны методы, которые могут быть использованы в классе строителей рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-166">The following table describes methods that can be used in a workflow builder class.</span></span>

|<span data-ttu-id="2e5a9-167">**Метод**</span><span class="sxs-lookup"><span data-stu-id="2e5a9-167">**Method**</span></span>|<span data-ttu-id="2e5a9-168">**Типичная подпись (ы)**</span><span class="sxs-lookup"><span data-stu-id="2e5a9-168">**Typical signature(s)**</span></span>|<span data-ttu-id="2e5a9-169">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2e5a9-169">**Description**</span></span>|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|<span data-ttu-id="2e5a9-170">Вызывается `let!` `do!` и в вычислительных выражениях.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-170">Called for `let!` and `do!` in computation expressions.</span></span>|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|<span data-ttu-id="2e5a9-171">Оберните выражение вычислений в качестве функции.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-171">Wraps a computation expression as a function.</span></span>|
|`Return`|`'T -> M<'T>`|<span data-ttu-id="2e5a9-172">Вызывается `return` в вычислительных выражениях.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-172">Called for `return` in computation expressions.</span></span>|
|`ReturnFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="2e5a9-173">Вызывается `return!` в вычислительных выражениях.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-173">Called for `return!` in computation expressions.</span></span>|
|`Run`|<span data-ttu-id="2e5a9-174">`M<'T> -> M<'T>` или</span><span class="sxs-lookup"><span data-stu-id="2e5a9-174">`M<'T> -> M<'T>` or</span></span><br /><br />`M<'T> -> 'T`|<span data-ttu-id="2e5a9-175">Выполняет вычисление выражения.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-175">Executes a computation expression.</span></span>|
|`Combine`|<span data-ttu-id="2e5a9-176">`M<'T> * M<'T> -> M<'T>` или</span><span class="sxs-lookup"><span data-stu-id="2e5a9-176">`M<'T> * M<'T> -> M<'T>` or</span></span><br /><br />`M<unit> * M<'T> -> M<'T>`|<span data-ttu-id="2e5a9-177">Требуется секвенирование в вычислительных выражениях.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-177">Called for sequencing in computation expressions.</span></span>|
|`For`|<span data-ttu-id="2e5a9-178">`seq<'T> * ('T -> M<'U>) -> M<'U>` или</span><span class="sxs-lookup"><span data-stu-id="2e5a9-178">`seq<'T> * ('T -> M<'U>) -> M<'U>` or</span></span><br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|<span data-ttu-id="2e5a9-179">Вызывается `for...do` выражения в выражениях вычислений.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-179">Called for `for...do` expressions in computation expressions.</span></span>|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|<span data-ttu-id="2e5a9-180">Вызывается `try...finally` выражения в выражениях вычислений.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-180">Called for `try...finally` expressions in computation expressions.</span></span>|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|<span data-ttu-id="2e5a9-181">Вызывается `try...with` выражения в выражениях вычислений.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-181">Called for `try...with` expressions in computation expressions.</span></span>|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'T :> IDisposable`|<span data-ttu-id="2e5a9-182">Вызывается `use` привязки в вычислительных выражениях.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-182">Called for `use` bindings in computation expressions.</span></span>|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|<span data-ttu-id="2e5a9-183">Вызывается `while...do` выражения в выражениях вычислений.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-183">Called for `while...do` expressions in computation expressions.</span></span>|
|`Yield`|`'T -> M<'T>`|<span data-ttu-id="2e5a9-184">Вызывается `yield` выражения в выражениях вычислений.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-184">Called for `yield` expressions in computation expressions.</span></span>|
|`YieldFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="2e5a9-185">Вызывается `yield!` выражения в выражениях вычислений.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-185">Called for `yield!` expressions in computation expressions.</span></span>|
|`Zero`|`unit -> M<'T>`|<span data-ttu-id="2e5a9-186">Вызывается `else` пустые `if...then` ветви выражений в вычислительных выражениях.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-186">Called for empty `else` branches of `if...then` expressions in computation expressions.</span></span>|
|`Quote`|`Quotations.Expr<'T> -> Quotations.Expr<'T>`|<span data-ttu-id="2e5a9-187">Означает, что выражение вычислений `Run` передается участнику в качестве цитаты.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-187">Indicates that the computation expression is passed to the `Run` member as a quotation.</span></span> <span data-ttu-id="2e5a9-188">Он переводит все экземпляры вычислений в цитату.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-188">It translates all instances of a computation into a quotation.</span></span>|

<span data-ttu-id="2e5a9-189">Многие методы в классе строителей используют `M<'T>` и возвращают конструкцию, которая обычно является отдельно определенным типом, который `Async<'T>` характеризует вид вычислений, комбинируется, например, для асинхронных рабочих процессов и `Seq<'T>` для рабочих процессов последовательности.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-189">Many of the methods in a builder class use and return an `M<'T>` construct, which is typically a separately defined type that characterizes the kind of computations being combined, for example, `Async<'T>` for asynchronous workflows and `Seq<'T>` for sequence workflows.</span></span> <span data-ttu-id="2e5a9-190">Подписи этих методов позволяют объединять и вкладывать друг с другом, так что объект рабочего процесса, возвращенный из одной конструкции, может быть передан другой.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-190">The signatures of these methods enable them to be combined and nested with each other, so that the workflow object returned from one construct can be passed to the next.</span></span> <span data-ttu-id="2e5a9-191">Компилятор, когда он разбирает выражение вычислений, преобразует выражение в ряд вложенных вызовов функции, используя методы в предыдущей таблице и код в выражении вычислений.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-191">The compiler, when it parses a computation expression, converts the expression into a series of nested function calls by using the methods in the preceding table and the code in the computation expression.</span></span>

<span data-ttu-id="2e5a9-192">Вложенное выражение имеет следующую форму:</span><span class="sxs-lookup"><span data-stu-id="2e5a9-192">The nested expression is of the following form:</span></span>

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

<span data-ttu-id="2e5a9-193">В приведенном выше коде вызовы `Run` и `Delay` опущены, если они не определены в классе builder выражения вычислений.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-193">In the above code, the calls to `Run` and `Delay` are omitted if they are not defined in the computation expression builder class.</span></span> <span data-ttu-id="2e5a9-194">Тело выражения вычисления, здесь обозначается как `{| cexpr |}`, переводится в вызовы, связанные с методами класса строитель переводы, описанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-194">The body of the computation expression, here denoted as `{| cexpr |}`, is translated into calls involving the methods of the builder class by the translations described in the following table.</span></span> <span data-ttu-id="2e5a9-195">Выражение `{| cexpr |}` вычислений определяется рекурсивно в соответствии с этими переводами, где `expr` является выражением F и `cexpr` является вычислительным выражением.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-195">The computation expression `{| cexpr |}` is defined recursively according to these translations where `expr` is an F# expression and `cexpr` is a computation expression.</span></span>

|<span data-ttu-id="2e5a9-196">Выражение</span><span class="sxs-lookup"><span data-stu-id="2e5a9-196">Expression</span></span>|<span data-ttu-id="2e5a9-197">Перевод</span><span class="sxs-lookup"><span data-stu-id="2e5a9-197">Translation</span></span>|
|----------|-----------|
|<code>{ let binding in cexpr }</code>|<code>let binding in {&#124; cexpr &#124;}</code>|
|<code>{ let! pattern = expr in cexpr }</code>|<code>builder.Bind(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{ do! expr in cexpr }</code>|<code>builder.Bind(expr, (fun () -> {&#124; cexpr &#124;}))</code>|
|<code>{ yield expr }</code>|`builder.Yield(expr)`|
|<code>{ yield! expr }</code>|`builder.YieldFrom(expr)`|
|<code>{ return expr }</code>|`builder.Return(expr)`|
|<code>{ return! expr }</code>|`builder.ReturnFrom(expr)`|
|<code>{ use pattern = expr in cexpr }</code>|<code>builder.Using(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{ use! value = expr in cexpr }</code>|<code>builder.Bind(expr, (fun value -> builder.Using(value, (fun value -> { cexpr }))))</code>|
|<code>{ if expr then cexpr0 &#124;}</code>|<code>if expr then { cexpr0 } else builder.Zero()</code>|
|<code>{ if expr then cexpr0 else cexpr1 &#124;}</code>|<code>if expr then { cexpr0 } else { cexpr1 }</code>|
|<code>{ match expr with &#124; pattern_i -> cexpr_i }</code>|<code>match expr with &#124; pattern_i -> { cexpr_i }</code>|
|<code>{ for pattern in expr do cexpr }</code>|<code>builder.For(enumeration, (fun pattern -> { cexpr }))</code>|
|<code>{ for identifier = expr1 to expr2 do cexpr }</code>|<code>builder.For(enumeration, (fun identifier -> { cexpr }))</code>|
|<code>{ while expr do cexpr }</code>|<code>builder.While(fun () -> expr, builder.Delay({ cexpr }))</code>|
|<code>{ try cexpr with &#124; pattern_i -> expr_i }</code>|<code>builder.TryWith(builder.Delay({ cexpr }), (fun value -> match value with &#124; pattern_i -> expr_i &#124; exn -> reraise exn)))</code>|
|<code>{ try cexpr finally expr }</code>|<code>builder.TryFinally(builder.Delay( { cexpr }), (fun () -> expr))</code>|
|<code>{ cexpr1; cexpr2 }</code>|<code>builder.Combine({ cexpr1 }, { cexpr2 })</code>|
|<code>{ other-expr; cexpr }</code>|<code>expr; { cexpr }</code>|
|<code>{ other-expr }</code>|`expr; builder.Zero()`|

<span data-ttu-id="2e5a9-198">В предыдущей `other-expr` таблице описывается выражение, которое в противном случае не перечислено в таблице.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-198">In the previous table, `other-expr` describes an expression that is not otherwise listed in the table.</span></span> <span data-ttu-id="2e5a9-199">Классу строителя не нужно реализовывать все методы и поддерживать все переводы, перечисленные в предыдущей таблице.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-199">A builder class does not need to implement all of the methods and support all of the translations listed in the previous table.</span></span> <span data-ttu-id="2e5a9-200">Те конструкции, которые не реализованы, недоступны в вычислительных выражениях этого типа.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-200">Those constructs that are not implemented are not available in computation expressions of that type.</span></span> <span data-ttu-id="2e5a9-201">Например, если вы не хотите `use` поддерживать ключевое слово в выражениях вычислений, `Use` вы можете пропустить определение в классе builder.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-201">For example, if you do not want to support the `use` keyword in your computation expressions, you can omit the definition of `Use` in your builder class.</span></span>

<span data-ttu-id="2e5a9-202">Следующий пример кода показывает выражение вычислений, которое инкапсулирует вычисление как ряд шагов, которые можно оценить на один шаг за один раз.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-202">The following code example shows a computation expression that encapsulates a computation as a series of steps that can be evaluated one step at a time.</span></span> <span data-ttu-id="2e5a9-203">Дискриминируемый `OkOrException`тип союза, кодирует состояние ошибки выражения, оцениваемые до сих пор.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-203">A discriminated union type, `OkOrException`, encodes the error state of the expression as evaluated so far.</span></span> <span data-ttu-id="2e5a9-204">Этот код демонстрирует несколько типичных шаблонов, которые можно использовать в выражениях вычислений, например шаблонные реализации некоторых методов builder.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-204">This code demonstrates several typical patterns that you can use in your computation expressions, such as boilerplate implementations of some of the builder methods.</span></span>

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

<span data-ttu-id="2e5a9-205">Выражение вычислений имеет базовый тип, который возвращает выражение.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-205">A computation expression has an underlying type, which the expression returns.</span></span> <span data-ttu-id="2e5a9-206">Базовый тип может представлять вычисленный результат или задержку вычислений, которые могут быть выполнены, или он может обеспечить способ итерации через некоторый тип коллекции.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-206">The underlying type may represent a computed result or a delayed computation that can be performed, or it may provide a way to iterate through some type of collection.</span></span> <span data-ttu-id="2e5a9-207">В предыдущем примере базовый тип был **в конечном итоге**.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-207">In the previous example, the underlying type was **Eventually**.</span></span> <span data-ttu-id="2e5a9-208">Для выражения последовательности базовый <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>тип .</span><span class="sxs-lookup"><span data-stu-id="2e5a9-208">For a sequence expression, the underlying type is <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2e5a9-209">Для выражения запроса базовый тип <xref:System.Linq.IQueryable?displayProperty=nameWithType>— это .</span><span class="sxs-lookup"><span data-stu-id="2e5a9-209">For a query expression, the underlying type is <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2e5a9-210">Для асинхронного рабочего процесса базовый тип [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span><span class="sxs-lookup"><span data-stu-id="2e5a9-210">For an asynchronous workflow, the underlying type is [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span></span> <span data-ttu-id="2e5a9-211">Объект `Async` представляет работу, которую предстоит выполнить для вычисления результата.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-211">The `Async` object represents the work to be performed to compute the result.</span></span> <span data-ttu-id="2e5a9-212">Например, вы [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) призываете выполнить вычисление и вернуть результат.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-212">For example, you call [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) to execute a computation and return the result.</span></span>

## <a name="custom-operations"></a><span data-ttu-id="2e5a9-213">Пользовательские операции</span><span class="sxs-lookup"><span data-stu-id="2e5a9-213">Custom Operations</span></span>

<span data-ttu-id="2e5a9-214">Можно определить пользовательскую операцию на вычислительном выражении и использовать пользовательскую операцию в качестве оператора в выражении вычислений.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-214">You can define a custom operation on a computation expression and use a custom operation as an operator in a computation expression.</span></span> <span data-ttu-id="2e5a9-215">Например, можно включить оператора запроса в выражение запроса.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-215">For example, you can include a query operator in a query expression.</span></span> <span data-ttu-id="2e5a9-216">При определении пользовательской операции необходимо определить доходность и методы в выражении вычислений.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-216">When you define a custom operation, you must define the Yield and For methods in the computation expression.</span></span> <span data-ttu-id="2e5a9-217">Чтобы определить пользовательскую операцию, поместите ее в класс builder [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19)для выражения вычислений, а затем примените .</span><span class="sxs-lookup"><span data-stu-id="2e5a9-217">To define a custom operation, put it in a builder class for the computation expression, and then apply the [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span></span> <span data-ttu-id="2e5a9-218">Этот атрибут использует строку в качестве аргумента, то есть имя, которое будет использоваться в пользовательской операции.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-218">This attribute takes a string as an argument, which is the name to be used in a custom operation.</span></span> <span data-ttu-id="2e5a9-219">Это имя вступает в сферу применения в начале вступительной скобки вычислительного выражения.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-219">This name comes into scope at the start of the opening curly brace of the computation expression.</span></span> <span data-ttu-id="2e5a9-220">Поэтому не следует использовать идентификаторы с тем же именем, что и пользовательская операция в этом блоке.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-220">Therefore, you shouldn’t use identifiers that have the same name as a custom operation in this block.</span></span> <span data-ttu-id="2e5a9-221">Например, избегайте использования идентификаторов, таких как `all` или `last` в выражениях запросов.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-221">For example, avoid the use of identifiers such as `all` or `last` in query expressions.</span></span>

### <a name="extending-existing-builders-with-new-custom-operations"></a><span data-ttu-id="2e5a9-222">Расширение существующих строителей с новыми пользовательскими операциями</span><span class="sxs-lookup"><span data-stu-id="2e5a9-222">Extending existing Builders with new Custom Operations</span></span>

<span data-ttu-id="2e5a9-223">Если у вас уже есть класс builder, его пользовательские операции могут быть расширены из-за пределов этого класса builder.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-223">If you already have a builder class, its custom operations can be extended from outside of this builder class.</span></span> <span data-ttu-id="2e5a9-224">Расширения должны быть объявлены в модулях.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-224">Extensions must be declared in modules.</span></span> <span data-ttu-id="2e5a9-225">Пространства имен не могут содержать члены расширения, за исключением того же файла и той же группы декларации пространства имен, где определяется тип.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-225">Namespaces cannot contain extension members except in the same file and the same namespace declaration group where the type is defined.</span></span>

<span data-ttu-id="2e5a9-226">Следующий пример показывает расширение `Microsoft.FSharp.Linq.QueryBuilder` существующего класса.</span><span class="sxs-lookup"><span data-stu-id="2e5a9-226">The following example shows the extension of the existing `Microsoft.FSharp.Linq.QueryBuilder` class.</span></span>

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member _.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a><span data-ttu-id="2e5a9-227">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2e5a9-227">See also</span></span>

- [<span data-ttu-id="2e5a9-228">Ссылка на язык F</span><span class="sxs-lookup"><span data-stu-id="2e5a9-228">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="2e5a9-229">Асинхронные рабочие потоки</span><span class="sxs-lookup"><span data-stu-id="2e5a9-229">Asynchronous Workflows</span></span>](asynchronous-workflows.md)
- [<span data-ttu-id="2e5a9-230">Последовательности</span><span class="sxs-lookup"><span data-stu-id="2e5a9-230">Sequences</span></span>](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)
- [<span data-ttu-id="2e5a9-231">Выражения запросов</span><span class="sxs-lookup"><span data-stu-id="2e5a9-231">Query Expressions</span></span>](query-expressions.md)
