---
title: Выражения вычисления
description: Узнайте, как создать удобный синтаксис для написания вычислений в F# , которые могут быть упорядочены и объединены с помощью конструкций и привязок потока управления.
ms.date: 11/04/2019
ms.openlocfilehash: 4ff7def0ed3a46acd1b0b83b111f26f5d556071f
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569458"
---
# <a name="computation-expressions"></a><span data-ttu-id="aefdd-103">Выражения вычисления</span><span class="sxs-lookup"><span data-stu-id="aefdd-103">Computation Expressions</span></span>

<span data-ttu-id="aefdd-104">Вычислительные выражения F# в предоставляют удобный синтаксис для написания вычислений, которые могут быть упорядочены и объединены с помощью конструкций и привязок потока управления.</span><span class="sxs-lookup"><span data-stu-id="aefdd-104">Computation expressions in F# provide a convenient syntax for writing computations that can be sequenced and combined using control flow constructs and bindings.</span></span> <span data-ttu-id="aefdd-105">В зависимости от типа вычислительного выражения их можно представить как способ выражения составных, моноидс, нестандартных преобразователей и аппликативе операторов.</span><span class="sxs-lookup"><span data-stu-id="aefdd-105">Depending on the kind of computation expression, they can be thought of as a way to express monads, monoids, monad transformers, and applicative functors.</span></span> <span data-ttu-id="aefdd-106">Однако, в отличие от других языков (например *, в* Haskell), они не привязаны к одной абстракции и не полагаются на макросы или другие формы метапрограммирование для выполнения удобного и контекстно-чувствительного синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="aefdd-106">However, unlike other languages (such as *do-notation* in Haskell), they are not tied to a single abstraction, and do not rely on macros or other forms of metaprogramming to accomplish a convenient and context-sensitive syntax.</span></span>

## <a name="overview"></a><span data-ttu-id="aefdd-107">Обзор</span><span class="sxs-lookup"><span data-stu-id="aefdd-107">Overview</span></span>

<span data-ttu-id="aefdd-108">Вычисления могут принимать множество форм.</span><span class="sxs-lookup"><span data-stu-id="aefdd-108">Computations can take many forms.</span></span> <span data-ttu-id="aefdd-109">Наиболее распространенной формой вычислений является однопотоковое выполнение, которое легко понять и изменить.</span><span class="sxs-lookup"><span data-stu-id="aefdd-109">The most common form of computation is single-threaded execution, which is easy to understand and modify.</span></span> <span data-ttu-id="aefdd-110">Однако не все формы вычислений являются простым выполнением с одним потоком.</span><span class="sxs-lookup"><span data-stu-id="aefdd-110">However, not all forms of computation are as straightforward as single-threaded execution.</span></span> <span data-ttu-id="aefdd-111">Ниже приведены некоторые примеры таких ситуаций.</span><span class="sxs-lookup"><span data-stu-id="aefdd-111">Some examples include:</span></span>

- <span data-ttu-id="aefdd-112">Недетерминированные вычисления</span><span class="sxs-lookup"><span data-stu-id="aefdd-112">Non-deterministic computations</span></span>
- <span data-ttu-id="aefdd-113">Асинхронные вычисления</span><span class="sxs-lookup"><span data-stu-id="aefdd-113">Asynchronous computations</span></span>
- <span data-ttu-id="aefdd-114">Вычисления с эффективностью</span><span class="sxs-lookup"><span data-stu-id="aefdd-114">Effectful computations</span></span>
- <span data-ttu-id="aefdd-115">Регенеративные вычисления</span><span class="sxs-lookup"><span data-stu-id="aefdd-115">Generative computations</span></span>

<span data-ttu-id="aefdd-116">Как правило, существуют *зависящие от контекста* вычисления, которые необходимо выполнить в определенных частях приложения.</span><span class="sxs-lookup"><span data-stu-id="aefdd-116">More generally, there are *context-sensitive* computations that you must perform in certain parts of an application.</span></span> <span data-ttu-id="aefdd-117">Написание контекстно-зависимого кода может быть непростой задачей, так как легко «утечку» вычислений за пределами данного контекста без абстракций, чтобы предотвратить это.</span><span class="sxs-lookup"><span data-stu-id="aefdd-117">Writing context-sensitive code can be challenging, as it is easy to "leak" computations outside of a given context without abstractions to prevent you from doing so.</span></span> <span data-ttu-id="aefdd-118">Эти абстракции часто сложны в написании самих себя, т F# . е. у них есть обобщенный способ сделать это, называемый **вычислительными выражениями**.</span><span class="sxs-lookup"><span data-stu-id="aefdd-118">These abstractions are often challenging to write by yourself, which is why F# has a generalized way to do so called **computation expressions**.</span></span>

<span data-ttu-id="aefdd-119">Вычислительные выражения предлагают единый синтаксис и модель абстракции для кодирования зависящих от контекста вычислений.</span><span class="sxs-lookup"><span data-stu-id="aefdd-119">Computation expressions offer a uniform syntax and abstraction model for encoding context-sensitive computations.</span></span>

<span data-ttu-id="aefdd-120">Каждое вычислительное выражение поддерживается типом *построителя* .</span><span class="sxs-lookup"><span data-stu-id="aefdd-120">Every computation expression is backed by a *builder* type.</span></span> <span data-ttu-id="aefdd-121">Тип построителя определяет операции, доступные для вычислительного выражения.</span><span class="sxs-lookup"><span data-stu-id="aefdd-121">The builder type defines the operations that are available for the computation expression.</span></span> <span data-ttu-id="aefdd-122">См. раздел [Создание нового типа вычислительного выражения](computation-expressions.md#creating-a-new-type-of-computation-expression), в котором показано, как создать пользовательское вычислительное выражение.</span><span class="sxs-lookup"><span data-stu-id="aefdd-122">See [Creating a New Type of Computation Expression](computation-expressions.md#creating-a-new-type-of-computation-expression), which shows how to create a custom computation expression.</span></span>

### <a name="syntax-overview"></a><span data-ttu-id="aefdd-123">Обзор синтаксиса</span><span class="sxs-lookup"><span data-stu-id="aefdd-123">Syntax overview</span></span>

<span data-ttu-id="aefdd-124">Все выражения вычислений имеют следующий вид:</span><span class="sxs-lookup"><span data-stu-id="aefdd-124">All computation expressions have the following form:</span></span>

```fsharp
builder-expr { cexper }
```

<span data-ttu-id="aefdd-125">где `builder-expr` — имя типа построителя, определяющего вычислительное выражение, а `cexper` — тело выражения вычисления.</span><span class="sxs-lookup"><span data-stu-id="aefdd-125">where `builder-expr` is the name of a builder type that defines the computation expression, and `cexper` is the expression body of the computation expression.</span></span> <span data-ttu-id="aefdd-126">Например, `async` код выражения вычисления может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="aefdd-126">For example, `async` computation expression code can look like this:</span></span>

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

<span data-ttu-id="aefdd-127">В вычислительном выражении доступен Специальный дополнительный синтаксис, как показано в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="aefdd-127">There is a special, additional syntax available within a computation expression, as shown in the previous example.</span></span> <span data-ttu-id="aefdd-128">В выражениях вычислений возможны следующие формы выражений:</span><span class="sxs-lookup"><span data-stu-id="aefdd-128">The following expression forms are possible with computation expressions:</span></span>

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

<span data-ttu-id="aefdd-129">Каждое из этих ключевых слов и другие стандартные F# ключевые слова доступны только в вычислительном выражении, если они были определены в типе построителя резервных копий.</span><span class="sxs-lookup"><span data-stu-id="aefdd-129">Each of these keywords, and other standard F# keywords are only available in a computation expression if they have been defined in the backing builder type.</span></span> <span data-ttu-id="aefdd-130">Единственным исключением из этого является `match!`, которое само по себе является синтаксическим SugarCRM для использования `let!`, за которым следует соответствие шаблона в результате.</span><span class="sxs-lookup"><span data-stu-id="aefdd-130">The only exception to this is `match!`, which is itself syntactic sugar for the use of `let!` followed by a pattern match on the result.</span></span>

<span data-ttu-id="aefdd-131">Тип построителя — это объект, который определяет специальные методы, определяющие способ объединения фрагментов вычислительного выражения. то есть его методы управляют тем, как работает вычислительное выражение.</span><span class="sxs-lookup"><span data-stu-id="aefdd-131">The builder type is an object that defines special methods that govern the way the fragments of the computation expression are combined; that is, its methods control how the computation expression behaves.</span></span> <span data-ttu-id="aefdd-132">Другой способ описать класс построителя — сказать, что он позволяет настраивать работу многих F# конструкций, таких как циклы и привязки.</span><span class="sxs-lookup"><span data-stu-id="aefdd-132">Another way to describe a builder class is to say that it enables you to customize the operation of many F# constructs, such as loops and bindings.</span></span>

### `let!`

<span data-ttu-id="aefdd-133">Ключевое слово `let!` привязывает результат вызова другого вычислительного выражения к имени:</span><span class="sxs-lookup"><span data-stu-id="aefdd-133">The `let!` keyword binds the result of a call to another computation expression to a name:</span></span>

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

<span data-ttu-id="aefdd-134">При привязке вызова к вычислительному выражению с `let`не будет получен результат вычисления выражения.</span><span class="sxs-lookup"><span data-stu-id="aefdd-134">If you bind the call to a computation expression with `let`, you will not get the result of the computation expression.</span></span> <span data-ttu-id="aefdd-135">Вместо этого вы привязываете значение *нереализованного* вызова к этому вычислительному выражению.</span><span class="sxs-lookup"><span data-stu-id="aefdd-135">Instead, you will have bound the value of the *unrealized* call to that computation expression.</span></span> <span data-ttu-id="aefdd-136">Для привязки к результату используйте `let!`.</span><span class="sxs-lookup"><span data-stu-id="aefdd-136">Use `let!` to bind to the result.</span></span>

<span data-ttu-id="aefdd-137">`let!` определяется членом `Bind(x, f)` в типе построителя.</span><span class="sxs-lookup"><span data-stu-id="aefdd-137">`let!` is defined by the `Bind(x, f)` member on the builder type.</span></span>

### `do!`

<span data-ttu-id="aefdd-138">Ключевое слово `do!` предназначено для вызова вычислительного выражения, возвращающего тип, схожий с `unit`(определяется элементом `Zero` в построителе):</span><span class="sxs-lookup"><span data-stu-id="aefdd-138">The `do!` keyword is for calling a computation expression that returns a `unit`-like type (defined by the `Zero` member on the builder):</span></span>

```fsharp
let doThingsAsync data url =
    async {
        do! submitData data url
        ...
    }
```

<span data-ttu-id="aefdd-139">Для [асинхронного рабочего процесса](asynchronous-workflows.md)этот тип `Async<unit>`.</span><span class="sxs-lookup"><span data-stu-id="aefdd-139">For the [async workflow](asynchronous-workflows.md), this type is `Async<unit>`.</span></span> <span data-ttu-id="aefdd-140">Для других вычислительных выражений тип, скорее всего, будет `CExpType<unit>`.</span><span class="sxs-lookup"><span data-stu-id="aefdd-140">For other computation expressions, the type is likely to be `CExpType<unit>`.</span></span>

<span data-ttu-id="aefdd-141">`do!` определяется членом `Bind(x, f)` в типе построителя, где `f` создает `unit`.</span><span class="sxs-lookup"><span data-stu-id="aefdd-141">`do!` is defined by the `Bind(x, f)` member on the builder type, where `f` produces a `unit`.</span></span>

### `yield`

<span data-ttu-id="aefdd-142">Ключевое слово `yield` используется для возвращения значения из вычислительного выражения, чтобы его можно было использовать как <xref:System.Collections.Generic.IEnumerable%601>:</span><span class="sxs-lookup"><span data-stu-id="aefdd-142">The `yield` keyword is for returning a value from the computation expression so that it can be consumed as an <xref:System.Collections.Generic.IEnumerable%601>:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

<span data-ttu-id="aefdd-143">В большинстве случаев его можно опустить вызывающими методами.</span><span class="sxs-lookup"><span data-stu-id="aefdd-143">In most cases, it can be omitted by callers.</span></span> <span data-ttu-id="aefdd-144">Наиболее распространенным способом опустить `yield` является оператор `->`:</span><span class="sxs-lookup"><span data-stu-id="aefdd-144">The most common way to omit `yield` is with the `->` operator:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..10 -> i * i
    }

for sq in squares do
    printfn "%d" sq
```

<span data-ttu-id="aefdd-145">Для более сложных выражений, которые могут выдавать множество различных значений, и, возможно, условный, просто Пропуск ключевого слова может выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="aefdd-145">For more complex expressions that might yield many different values, and perhaps conditionally, simply omitting the keyword can do:</span></span>

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

<span data-ttu-id="aefdd-146">Как и в случае с [ключевым C#словом yield в ](../../csharp/language-reference/keywords/yield.md), каждый элемент в вычислительном выражении получает обратную передачу по мере выполнения итерации.</span><span class="sxs-lookup"><span data-stu-id="aefdd-146">As with the [yield keyword in C#](../../csharp/language-reference/keywords/yield.md), each element in the computation expression is yielded back as it is iterated.</span></span>

<span data-ttu-id="aefdd-147">`yield` определяется членом `Yield(x)` в типе построителя, где `x` — это элемент, который необходимо вернуть.</span><span class="sxs-lookup"><span data-stu-id="aefdd-147">`yield` is defined by the `Yield(x)` member on the builder type, where `x` is the item to yield back.</span></span>

### `yield!`

<span data-ttu-id="aefdd-148">Ключевое слово `yield!` предназначено для выравнивания коллекции значений из вычислительного выражения:</span><span class="sxs-lookup"><span data-stu-id="aefdd-148">The `yield!` keyword is for flattening a collection of values from a computation expression:</span></span>

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

<span data-ttu-id="aefdd-149">При вычислении вычислительное выражение, вызываемое `yield!`, будет возвращать возвращенные элементы по одному, сведеня результат.</span><span class="sxs-lookup"><span data-stu-id="aefdd-149">When evaluated, the computation expression called by `yield!` will have its items yielded back one-by-one, flattening the result.</span></span>

<span data-ttu-id="aefdd-150">`yield!` определяется членом `YieldFrom(x)` в типе построителя, где `x` является коллекцией значений.</span><span class="sxs-lookup"><span data-stu-id="aefdd-150">`yield!` is defined by the `YieldFrom(x)` member on the builder type, where `x` is a collection of values.</span></span>

<span data-ttu-id="aefdd-151">В отличие от `yield`, необходимо явно указать `yield!`.</span><span class="sxs-lookup"><span data-stu-id="aefdd-151">Unlike `yield`, `yield!` must be explicitly specified.</span></span> <span data-ttu-id="aefdd-152">Его поведение не является неявным в вычислительных выражениях.</span><span class="sxs-lookup"><span data-stu-id="aefdd-152">Its behavior isn't implicit in computation expressions.</span></span>

### `return`

<span data-ttu-id="aefdd-153">Ключевое слово `return` заключает в оболочку значение в типе, соответствующем вычислительному выражению.</span><span class="sxs-lookup"><span data-stu-id="aefdd-153">The `return` keyword wraps a value in the type corresponding to the computation expression.</span></span> <span data-ttu-id="aefdd-154">Помимо вычислительных выражений, использующих `yield`, оно используется для полного выражения вычислений:</span><span class="sxs-lookup"><span data-stu-id="aefdd-154">Aside from computation expressions using `yield`, it is used to "complete" a computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="aefdd-155">`return` определяется членом `Return(x)` в типе построителя, где `x` — это элемент для переноса.</span><span class="sxs-lookup"><span data-stu-id="aefdd-155">`return` is defined by the `Return(x)` member on the builder type, where `x` is the item to wrap.</span></span>

### `return!`

<span data-ttu-id="aefdd-156">Ключевое слово `return!` вычисляет значение вычислительного выражения и заключает результат в тип, соответствующий вычислительному выражению:</span><span class="sxs-lookup"><span data-stu-id="aefdd-156">The `return!` keyword realizes the value of a computation expression and wraps that result in the type corresponding to the computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="aefdd-157">`return!` определяется членом `ReturnFrom(x)` в типе построителя, где `x` является другим вычислительным выражением.</span><span class="sxs-lookup"><span data-stu-id="aefdd-157">`return!` is defined by the `ReturnFrom(x)` member on the builder type, where `x` is another computation expression.</span></span>

### `match!`

<span data-ttu-id="aefdd-158">Ключевое слово `match!` позволяет встроено вызвать в другое вычислительное выражение и сопоставить шаблон с его результатом:</span><span class="sxs-lookup"><span data-stu-id="aefdd-158">The `match!` keyword allows you to inline a call to another computation expression and pattern match on its result:</span></span>

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

<span data-ttu-id="aefdd-159">При вызове вычислительного выражения с `match!`будет выдаваться результат такого вызова, как `let!`.</span><span class="sxs-lookup"><span data-stu-id="aefdd-159">When calling a computation expression with `match!`, it will realize the result of the call like `let!`.</span></span> <span data-ttu-id="aefdd-160">Это часто используется при вызове вычислительного выражения, в котором результат является [необязательным](options.md).</span><span class="sxs-lookup"><span data-stu-id="aefdd-160">This is often used when calling a computation expression where the result is an [optional](options.md).</span></span>

## <a name="built-in-computation-expressions"></a><span data-ttu-id="aefdd-161">Встроенные вычислительные выражения</span><span class="sxs-lookup"><span data-stu-id="aefdd-161">Built-in computation expressions</span></span>

<span data-ttu-id="aefdd-162">F# Базовая библиотека определяет три встроенных вычислительных выражения: [выражения последовательности](sequences.md), [асинхронные рабочие процессы](asynchronous-workflows.md)и [выражения запросов](query-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="aefdd-162">The F# core library defines three built-in computation expressions: [Sequence Expressions](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Query Expressions](query-expressions.md).</span></span>

## <a name="creating-a-new-type-of-computation-expression"></a><span data-ttu-id="aefdd-163">Создание нового типа вычислительного выражения</span><span class="sxs-lookup"><span data-stu-id="aefdd-163">Creating a New Type of Computation Expression</span></span>

<span data-ttu-id="aefdd-164">Вы можете определить характеристики собственных вычислительных выражений, создав класс построителя и определив определенные специальные методы в классе.</span><span class="sxs-lookup"><span data-stu-id="aefdd-164">You can define the characteristics of your own computation expressions by creating a builder class and defining certain special methods on the class.</span></span> <span data-ttu-id="aefdd-165">Класс построителя может дополнительно определять методы, перечисленные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="aefdd-165">The builder class can optionally define the methods as listed in the following table.</span></span>

<span data-ttu-id="aefdd-166">В следующей таблице описаны методы, которые можно использовать в классе построителя рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="aefdd-166">The following table describes methods that can be used in a workflow builder class.</span></span>

|<span data-ttu-id="aefdd-167">**Метод**</span><span class="sxs-lookup"><span data-stu-id="aefdd-167">**Method**</span></span>|<span data-ttu-id="aefdd-168">**Типичные подписи**</span><span class="sxs-lookup"><span data-stu-id="aefdd-168">**Typical signature(s)**</span></span>|<span data-ttu-id="aefdd-169">**Описание**</span><span class="sxs-lookup"><span data-stu-id="aefdd-169">**Description**</span></span>|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|<span data-ttu-id="aefdd-170">Вызывается для `let!` и `do!` в вычислительных выражениях.</span><span class="sxs-lookup"><span data-stu-id="aefdd-170">Called for `let!` and `do!` in computation expressions.</span></span>|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|<span data-ttu-id="aefdd-171">Заключает в оболочку вычислительное выражение как функцию.</span><span class="sxs-lookup"><span data-stu-id="aefdd-171">Wraps a computation expression as a function.</span></span>|
|`Return`|`'T -> M<'T>`|<span data-ttu-id="aefdd-172">Вызывается для `return` в вычислительных выражениях.</span><span class="sxs-lookup"><span data-stu-id="aefdd-172">Called for `return` in computation expressions.</span></span>|
|`ReturnFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="aefdd-173">Вызывается для `return!` в вычислительных выражениях.</span><span class="sxs-lookup"><span data-stu-id="aefdd-173">Called for `return!` in computation expressions.</span></span>|
|`Run`|<span data-ttu-id="aefdd-174">`M<'T> -> M<'T>` или</span><span class="sxs-lookup"><span data-stu-id="aefdd-174">`M<'T> -> M<'T>` or</span></span><br /><br />`M<'T> -> 'T`|<span data-ttu-id="aefdd-175">Выполняет вычислительное выражение.</span><span class="sxs-lookup"><span data-stu-id="aefdd-175">Executes a computation expression.</span></span>|
|`Combine`|<span data-ttu-id="aefdd-176">`M<'T> * M<'T> -> M<'T>` или</span><span class="sxs-lookup"><span data-stu-id="aefdd-176">`M<'T> * M<'T> -> M<'T>` or</span></span><br /><br />`M<unit> * M<'T> -> M<'T>`|<span data-ttu-id="aefdd-177">Вызывается для виртуализации в вычислительных выражениях.</span><span class="sxs-lookup"><span data-stu-id="aefdd-177">Called for sequencing in computation expressions.</span></span>|
|`For`|<span data-ttu-id="aefdd-178">`seq<'T> * ('T -> M<'U>) -> M<'U>` или</span><span class="sxs-lookup"><span data-stu-id="aefdd-178">`seq<'T> * ('T -> M<'U>) -> M<'U>` or</span></span><br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|<span data-ttu-id="aefdd-179">Вызывается для `for...do` выражений в вычислительных выражениях.</span><span class="sxs-lookup"><span data-stu-id="aefdd-179">Called for `for...do` expressions in computation expressions.</span></span>|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|<span data-ttu-id="aefdd-180">Вызывается для `try...finally` выражений в вычислительных выражениях.</span><span class="sxs-lookup"><span data-stu-id="aefdd-180">Called for `try...finally` expressions in computation expressions.</span></span>|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|<span data-ttu-id="aefdd-181">Вызывается для `try...with` выражений в вычислительных выражениях.</span><span class="sxs-lookup"><span data-stu-id="aefdd-181">Called for `try...with` expressions in computation expressions.</span></span>|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'T :> IDisposable`|<span data-ttu-id="aefdd-182">Вызывается для `use` привязок в вычислительных выражениях.</span><span class="sxs-lookup"><span data-stu-id="aefdd-182">Called for `use` bindings in computation expressions.</span></span>|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|<span data-ttu-id="aefdd-183">Вызывается для `while...do` выражений в вычислительных выражениях.</span><span class="sxs-lookup"><span data-stu-id="aefdd-183">Called for `while...do` expressions in computation expressions.</span></span>|
|`Yield`|`'T -> M<'T>`|<span data-ttu-id="aefdd-184">Вызывается для `yield` выражений в вычислительных выражениях.</span><span class="sxs-lookup"><span data-stu-id="aefdd-184">Called for `yield` expressions in computation expressions.</span></span>|
|`YieldFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="aefdd-185">Вызывается для `yield!` выражений в вычислительных выражениях.</span><span class="sxs-lookup"><span data-stu-id="aefdd-185">Called for `yield!` expressions in computation expressions.</span></span>|
|`Zero`|`unit -> M<'T>`|<span data-ttu-id="aefdd-186">Вызывается для пустых `else` ветвей `if...then` выражений в вычислительных выражениях.</span><span class="sxs-lookup"><span data-stu-id="aefdd-186">Called for empty `else` branches of `if...then` expressions in computation expressions.</span></span>|
|`Quote`|`Quotations.Expr<'T> -> Quotations.Expr<'T>`|<span data-ttu-id="aefdd-187">Указывает, что вычислительное выражение передается в элемент `Run` в качестве предложения.</span><span class="sxs-lookup"><span data-stu-id="aefdd-187">Indicates that the computation expression is passed to the `Run` member as a quotation.</span></span> <span data-ttu-id="aefdd-188">Он преобразует все экземпляры вычислений в кавычки.</span><span class="sxs-lookup"><span data-stu-id="aefdd-188">It translates all instances of a computation into a quotation.</span></span>|

<span data-ttu-id="aefdd-189">Многие методы в классе построителя используют и возвращают `M<'T>` конструкцию, которая обычно представляет собой отдельный определяемый тип, который характеризует тип объединяемых вычислений, например `Async<'T>` для асинхронных рабочих процессов и `Seq<'T>` для рабочих процессов последовательности.</span><span class="sxs-lookup"><span data-stu-id="aefdd-189">Many of the methods in a builder class use and return an `M<'T>` construct, which is typically a separately defined type that characterizes the kind of computations being combined, for example, `Async<'T>` for asynchronous workflows and `Seq<'T>` for sequence workflows.</span></span> <span data-ttu-id="aefdd-190">Сигнатуры этих методов позволяют объединять и вкладывать друг в друга, чтобы объект рабочего процесса, возвращенный из одной конструкции, можно было передать далее.</span><span class="sxs-lookup"><span data-stu-id="aefdd-190">The signatures of these methods enable them to be combined and nested with each other, so that the workflow object returned from one construct can be passed to the next.</span></span> <span data-ttu-id="aefdd-191">Компилятор при синтаксическом анализе вычислительного выражения преобразует выражение в ряд вложенных вызовов функций, используя методы из предыдущей таблицы и код в вычислительном выражении.</span><span class="sxs-lookup"><span data-stu-id="aefdd-191">The compiler, when it parses a computation expression, converts the expression into a series of nested function calls by using the methods in the preceding table and the code in the computation expression.</span></span>

<span data-ttu-id="aefdd-192">Вложенное выражение имеет следующий вид:</span><span class="sxs-lookup"><span data-stu-id="aefdd-192">The nested expression is of the following form:</span></span>

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

<span data-ttu-id="aefdd-193">В приведенном выше коде вызовы `Run` и `Delay` опущены, если они не определены в классе построителя вычислительных выражений.</span><span class="sxs-lookup"><span data-stu-id="aefdd-193">In the above code, the calls to `Run` and `Delay` are omitted if they are not defined in the computation expression builder class.</span></span> <span data-ttu-id="aefdd-194">Текст вычислительного выражения, обозначенный как `{| cexpr |}`, преобразуется в вызовы, в которых используются методы класса Builder, с помощью переводов, описанных в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="aefdd-194">The body of the computation expression, here denoted as `{| cexpr |}`, is translated into calls involving the methods of the builder class by the translations described in the following table.</span></span> <span data-ttu-id="aefdd-195">Выражение вычисления `{| cexpr |}` определяется рекурсивно в соответствии с этими переводами, где `expr` является F# выражением, а `cexpr` является вычислительным выражением.</span><span class="sxs-lookup"><span data-stu-id="aefdd-195">The computation expression `{| cexpr |}` is defined recursively according to these translations where `expr` is an F# expression and `cexpr` is a computation expression.</span></span>

|<span data-ttu-id="aefdd-196">Выражение</span><span class="sxs-lookup"><span data-stu-id="aefdd-196">Expression</span></span>|<span data-ttu-id="aefdd-197">Преобразование</span><span class="sxs-lookup"><span data-stu-id="aefdd-197">Translation</span></span>|
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
|<code>{ if expr then cexpr0 &#124;}</code>|<code>if expr then { cexpr0 } else binder.Zero()</code>|
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

<span data-ttu-id="aefdd-198">В предыдущей таблице `other-expr` описывает выражение, которое не указано в таблице в других случаях.</span><span class="sxs-lookup"><span data-stu-id="aefdd-198">In the previous table, `other-expr` describes an expression that is not otherwise listed in the table.</span></span> <span data-ttu-id="aefdd-199">Классу построителя не требуется реализовывать все методы и поддерживать все переводы, перечисленные в предыдущей таблице.</span><span class="sxs-lookup"><span data-stu-id="aefdd-199">A builder class does not need to implement all of the methods and support all of the translations listed in the previous table.</span></span> <span data-ttu-id="aefdd-200">Эти конструкции, которые не реализованы, недоступны в вычислительных выражениях этого типа.</span><span class="sxs-lookup"><span data-stu-id="aefdd-200">Those constructs that are not implemented are not available in computation expressions of that type.</span></span> <span data-ttu-id="aefdd-201">Например, если не требуется поддерживать ключевое слово `use` в вычислительных выражениях, можно опустить определение `Use` в классе построителя.</span><span class="sxs-lookup"><span data-stu-id="aefdd-201">For example, if you do not want to support the `use` keyword in your computation expressions, you can omit the definition of `Use` in your builder class.</span></span>

<span data-ttu-id="aefdd-202">В следующем примере кода показано вычислительное выражение, которое инкапсулирует вычисление в виде последовательности шагов, которые можно оценить по одному шагу за раз.</span><span class="sxs-lookup"><span data-stu-id="aefdd-202">The following code example shows a computation expression that encapsulates a computation as a series of steps that can be evaluated one step at a time.</span></span> <span data-ttu-id="aefdd-203">Тип размеченного объединения, `OkOrException`, кодирует состояние ошибки выражения, как было оценено до сих пор.</span><span class="sxs-lookup"><span data-stu-id="aefdd-203">A discriminated union type, `OkOrException`, encodes the error state of the expression as evaluated so far.</span></span> <span data-ttu-id="aefdd-204">Этот код демонстрирует несколько типовых шаблонов, которые можно использовать в вычислительных выражениях, таких как стандартные реализации некоторых методов построителя.</span><span class="sxs-lookup"><span data-stu-id="aefdd-204">This code demonstrates several typical patterns that you can use in your computation expressions, such as boilerplate implementations of some of the builder methods.</span></span>

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

<span data-ttu-id="aefdd-205">Вычислительное выражение имеет базовый тип, который возвращает выражение.</span><span class="sxs-lookup"><span data-stu-id="aefdd-205">A computation expression has an underlying type, which the expression returns.</span></span> <span data-ttu-id="aefdd-206">Базовый тип может представлять вычисленный результат или отложенное вычисление, которое может быть выполнено, или может предоставить способ итерации некоторого типа коллекции.</span><span class="sxs-lookup"><span data-stu-id="aefdd-206">The underlying type may represent a computed result or a delayed computation that can be performed, or it may provide a way to iterate through some type of collection.</span></span> <span data-ttu-id="aefdd-207">В предыдущем примере базовый тип был в **конечном итоге**.</span><span class="sxs-lookup"><span data-stu-id="aefdd-207">In the previous example, the underlying type was **Eventually**.</span></span> <span data-ttu-id="aefdd-208">Для выражения последовательности базовым типом является <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="aefdd-208">For a sequence expression, the underlying type is <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="aefdd-209">Для выражения запроса базовый тип <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="aefdd-209">For a query expression, the underlying type is <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="aefdd-210">Для асинхронного рабочего процесса базовый тип [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span><span class="sxs-lookup"><span data-stu-id="aefdd-210">For an asynchronous workflow, the underlying type is [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span></span> <span data-ttu-id="aefdd-211">Объект `Async` представляет работу, которую необходимо выполнить для вычисления результата.</span><span class="sxs-lookup"><span data-stu-id="aefdd-211">The `Async` object represents the work to be performed to compute the result.</span></span> <span data-ttu-id="aefdd-212">Например, вызовите [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) , чтобы выполнить вычисление и вернуть результат.</span><span class="sxs-lookup"><span data-stu-id="aefdd-212">For example, you call [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) to execute a computation and return the result.</span></span>

## <a name="custom-operations"></a><span data-ttu-id="aefdd-213">Пользовательские операции</span><span class="sxs-lookup"><span data-stu-id="aefdd-213">Custom Operations</span></span>

<span data-ttu-id="aefdd-214">Можно определить пользовательскую операцию в вычислительном выражении и использовать настраиваемую операцию в качестве оператора в вычислительном выражении.</span><span class="sxs-lookup"><span data-stu-id="aefdd-214">You can define a custom operation on a computation expression and use a custom operation as an operator in a computation expression.</span></span> <span data-ttu-id="aefdd-215">Например, оператор запроса можно включить в выражение запроса.</span><span class="sxs-lookup"><span data-stu-id="aefdd-215">For example, you can include a query operator in a query expression.</span></span> <span data-ttu-id="aefdd-216">При определении пользовательской операции необходимо определить методы yield и for в вычислительном выражении.</span><span class="sxs-lookup"><span data-stu-id="aefdd-216">When you define a custom operation, you must define the Yield and For methods in the computation expression.</span></span> <span data-ttu-id="aefdd-217">Чтобы определить пользовательскую операцию, добавьте ее в класс построителя для вычислительного выражения, а затем примените [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span><span class="sxs-lookup"><span data-stu-id="aefdd-217">To define a custom operation, put it in a builder class for the computation expression, and then apply the [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span></span> <span data-ttu-id="aefdd-218">Этот атрибут принимает строку в качестве аргумента, который является именем, используемым в пользовательской операции.</span><span class="sxs-lookup"><span data-stu-id="aefdd-218">This attribute takes a string as an argument, which is the name to be used in a custom operation.</span></span> <span data-ttu-id="aefdd-219">Это имя поступает в область в начале открывающей фигурной скобки вычислительного выражения.</span><span class="sxs-lookup"><span data-stu-id="aefdd-219">This name comes into scope at the start of the opening curly brace of the computation expression.</span></span> <span data-ttu-id="aefdd-220">Поэтому не следует использовать идентификаторы, имена которых совпадают с именами пользовательских операций в этом блоке.</span><span class="sxs-lookup"><span data-stu-id="aefdd-220">Therefore, you shouldn’t use identifiers that have the same name as a custom operation in this block.</span></span> <span data-ttu-id="aefdd-221">Например, Избегайте использования идентификаторов, таких как `all` или `last` в выражениях запросов.</span><span class="sxs-lookup"><span data-stu-id="aefdd-221">For example, avoid the use of identifiers such as `all` or `last` in query expressions.</span></span>

### <a name="extending-existing-builders-with-new-custom-operations"></a><span data-ttu-id="aefdd-222">Расширение существующих построителей с помощью новых настраиваемых операций</span><span class="sxs-lookup"><span data-stu-id="aefdd-222">Extending existing Builders with new Custom Operations</span></span>

<span data-ttu-id="aefdd-223">Если у вас уже есть класс построителя, его пользовательские операции можно расширить за пределами этого класса построителя.</span><span class="sxs-lookup"><span data-stu-id="aefdd-223">If you already have a builder class, its custom operations can be extended from outside of this builder class.</span></span> <span data-ttu-id="aefdd-224">Расширения должны быть объявлены в модулях.</span><span class="sxs-lookup"><span data-stu-id="aefdd-224">Extensions must be declared in modules.</span></span> <span data-ttu-id="aefdd-225">Пространства имен не могут содержать элементы Extension, кроме в том же файле и в той же группе объявлений пространства имен, где определен тип.</span><span class="sxs-lookup"><span data-stu-id="aefdd-225">Namespaces cannot contain extension members except in the same file and the same namespace declaration group where the type is defined.</span></span>

<span data-ttu-id="aefdd-226">В следующем примере показано расширение существующего класса `Microsoft.FSharp.Linq.QueryBuilder`.</span><span class="sxs-lookup"><span data-stu-id="aefdd-226">The following example shows the extension of the existing `Microsoft.FSharp.Linq.QueryBuilder` class.</span></span>

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member _.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a><span data-ttu-id="aefdd-227">См. также:</span><span class="sxs-lookup"><span data-stu-id="aefdd-227">See also</span></span>

- [<span data-ttu-id="aefdd-228">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="aefdd-228">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="aefdd-229">Асинхронные рабочие потоки</span><span class="sxs-lookup"><span data-stu-id="aefdd-229">Asynchronous Workflows</span></span>](asynchronous-workflows.md)
- [<span data-ttu-id="aefdd-230">Последовательности</span><span class="sxs-lookup"><span data-stu-id="aefdd-230">Sequences</span></span>](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)
- [<span data-ttu-id="aefdd-231">Выражения запросов</span><span class="sxs-lookup"><span data-stu-id="aefdd-231">Query Expressions</span></span>](query-expressions.md)
