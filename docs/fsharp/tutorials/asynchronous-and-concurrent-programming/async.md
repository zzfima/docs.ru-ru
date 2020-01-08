---
title: Асинхронное программирование
description: Узнайте, F# как обеспечивается чистая Поддержка асинхронность на основе модели программирования на уровне языка, полученной из основных концепций функционального программирования.
ms.date: 12/17/2018
ms.openlocfilehash: 471566befd69f330fb9254dbd57b19569d9f9ad3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344661"
---
# <a name="async-programming-in-f"></a><span data-ttu-id="c9db2-103">Асинхронное программирование в F\#</span><span class="sxs-lookup"><span data-stu-id="c9db2-103">Async programming in F\#</span></span>

<span data-ttu-id="c9db2-104">Асинхронное программирование — это механизм, который необходим для современных приложений по различным причинам.</span><span class="sxs-lookup"><span data-stu-id="c9db2-104">Asynchronous programming is a mechanism that is essential to modern applications for diverse reasons.</span></span> <span data-ttu-id="c9db2-105">Большинство разработчиков могут столкнуться с двумя основными вариантами использования:</span><span class="sxs-lookup"><span data-stu-id="c9db2-105">There are two primary use cases that most developers will encounter:</span></span>

- <span data-ttu-id="c9db2-106">Представление серверного процесса, который может обслуживать значительное количество одновременных входящих запросов, одновременно сокращая объем системных ресурсов, занятых во время обработки запроса, ожидающих входные данные из систем или служб извне этого процесса.</span><span class="sxs-lookup"><span data-stu-id="c9db2-106">Presenting a server process that can service a significant number of concurrent incoming requests, while minimizing the system resources occupied while request processing awaits inputs from systems or services external to that process</span></span>
- <span data-ttu-id="c9db2-107">Поддержание реагирующего пользовательского интерфейса или основного потока при одновременном выполнении фоновой работы</span><span class="sxs-lookup"><span data-stu-id="c9db2-107">Maintaining a responsive UI or main thread while concurrently progressing background work</span></span>

<span data-ttu-id="c9db2-108">Хотя фоновая работа часто занимается использованием нескольких потоков, важно учитывать концепцию Асинхронность и многопоточности отдельно.</span><span class="sxs-lookup"><span data-stu-id="c9db2-108">Although background work often does involve the utilization of multiple threads, it's important to consider the concepts of asynchrony and multi-threading separately.</span></span> <span data-ttu-id="c9db2-109">На самом деле, это отдельные проблемы, и одна из них не подразумевает другую.</span><span class="sxs-lookup"><span data-stu-id="c9db2-109">In fact, they are separate concerns, and one does not imply the other.</span></span> <span data-ttu-id="c9db2-110">Далее в этой статье подробно описывается это.</span><span class="sxs-lookup"><span data-stu-id="c9db2-110">What follows in this article describes this in more detail.</span></span>

## <a name="asynchrony-defined"></a><span data-ttu-id="c9db2-111">Определено асинхронность</span><span class="sxs-lookup"><span data-stu-id="c9db2-111">Asynchrony defined</span></span>

<span data-ttu-id="c9db2-112">Предыдущая точка — то, что асинхронность не зависит от использования нескольких потоков, стоит немного подробнее объяснить.</span><span class="sxs-lookup"><span data-stu-id="c9db2-112">The previous point - that asynchrony is independent of the utilization of multiple threads - is worth explaining a bit further.</span></span> <span data-ttu-id="c9db2-113">Существуют три концепции, которые иногда связаны, но строго независимы друг от друга:</span><span class="sxs-lookup"><span data-stu-id="c9db2-113">There are three concepts that are sometimes related, but strictly independent of one another:</span></span>

- <span data-ttu-id="c9db2-114">Параллелизма когда несколько вычислений выполняются в перекрывающиеся периоды времени.</span><span class="sxs-lookup"><span data-stu-id="c9db2-114">Concurrency; when multiple computations execute in overlapping time periods.</span></span>
- <span data-ttu-id="c9db2-115">Параллелизма Если несколько вычислений или несколько частей одного вычисления выполняются в точно одно и то же время.</span><span class="sxs-lookup"><span data-stu-id="c9db2-115">Parallelism; when multiple computations or several parts of a single computation run at exactly the same time.</span></span>
- <span data-ttu-id="c9db2-116">Асинхронность Если одно или несколько вычислений могут выполняться отдельно от основного потока программы.</span><span class="sxs-lookup"><span data-stu-id="c9db2-116">Asynchrony; when one or more computations can execute separately from the main program flow.</span></span>

<span data-ttu-id="c9db2-117">Все три являются ортогональными концепциями, но их можно легко увеличить, особенно если они используются совместно.</span><span class="sxs-lookup"><span data-stu-id="c9db2-117">All three are orthogonal concepts, but can be easily conflated, especially when they are used together.</span></span> <span data-ttu-id="c9db2-118">Например, может потребоваться параллельное выполнение нескольких асинхронных вычислений.</span><span class="sxs-lookup"><span data-stu-id="c9db2-118">For example, you may need to execute multiple asynchronous computations in parallel.</span></span> <span data-ttu-id="c9db2-119">Это не означает, что параллелизм или асинхронность предполагают друг друга.</span><span class="sxs-lookup"><span data-stu-id="c9db2-119">This does not mean that parallelism or asynchrony imply one another.</span></span>

<span data-ttu-id="c9db2-120">Если вы считаете, что етимологи слово «асинхронный», участвуют две части:</span><span class="sxs-lookup"><span data-stu-id="c9db2-120">If you consider the etymology of the word "asynchronous", there are two pieces involved:</span></span>

- <span data-ttu-id="c9db2-121">"a", что означает "not".</span><span class="sxs-lookup"><span data-stu-id="c9db2-121">"a", meaning "not".</span></span>
- <span data-ttu-id="c9db2-122">"Синхронное", означающее "в то же время".</span><span class="sxs-lookup"><span data-stu-id="c9db2-122">"synchronous", meaning "at the same time".</span></span>

<span data-ttu-id="c9db2-123">При совместном помещении этих двух терминов вы увидите, что "асинхронное" означает "не одновременно".</span><span class="sxs-lookup"><span data-stu-id="c9db2-123">When you put these two terms together, you'll see that "asynchronous" means "not at the same time".</span></span> <span data-ttu-id="c9db2-124">Вот и все!</span><span class="sxs-lookup"><span data-stu-id="c9db2-124">That's it!</span></span> <span data-ttu-id="c9db2-125">В этом определении не происходит неарифметического параллелизма или параллелизма.</span><span class="sxs-lookup"><span data-stu-id="c9db2-125">There is no implication of concurrency or parallelism in this definition.</span></span> <span data-ttu-id="c9db2-126">Это также справедливо и на практике.</span><span class="sxs-lookup"><span data-stu-id="c9db2-126">This is also true in practice.</span></span>

<span data-ttu-id="c9db2-127">На практике асинхронные вычисления в F# запланированы на выполнение независимо от основной последовательности программы.</span><span class="sxs-lookup"><span data-stu-id="c9db2-127">In practical terms, asynchronous computations in F# are scheduled to execute independently of the main program flow.</span></span> <span data-ttu-id="c9db2-128">Это не подразумевает параллелизм или параллелизм, а также не подразумевает, что вычисления всегда выполняются в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="c9db2-128">This doesn't imply concurrency or parallelism, nor does it imply that a computation always happens in the background.</span></span> <span data-ttu-id="c9db2-129">Фактически асинхронные вычисления могут даже выполняться синхронно, в зависимости от природы вычислений и среды, в которой выполняется вычисление.</span><span class="sxs-lookup"><span data-stu-id="c9db2-129">In fact, asynchronous computations can even execute synchronously, depending on the nature of the computation and the environment the computation is executing in.</span></span>

<span data-ttu-id="c9db2-130">Основная мысльа заключается в том, что асинхронные вычисления не зависят от основного потока программы.</span><span class="sxs-lookup"><span data-stu-id="c9db2-130">The main takeaway you should have is that asynchronous computations are independent of the main program flow.</span></span> <span data-ttu-id="c9db2-131">Хотя существует несколько гарантий относительно того, когда и как выполняется асинхронное вычисление, существует ряд подходов к координации и планированию.</span><span class="sxs-lookup"><span data-stu-id="c9db2-131">Although there are few guarantees about when or how an asynchronous computation executes, there are some approaches to orchestrating and scheduling them.</span></span> <span data-ttu-id="c9db2-132">Оставшаяся часть этой статьи посвящена основным понятиям F# Асинхронность и использованию типов, функций и выражений, встроенных в. F#</span><span class="sxs-lookup"><span data-stu-id="c9db2-132">The rest of this article explores core concepts for F# asynchrony and how to use the types, functions, and expressions built into F#.</span></span>

## <a name="core-concepts"></a><span data-ttu-id="c9db2-133">Основные понятия</span><span class="sxs-lookup"><span data-stu-id="c9db2-133">Core concepts</span></span>

<span data-ttu-id="c9db2-134">В F#асинхронное программирование основано на трех основных понятиях:</span><span class="sxs-lookup"><span data-stu-id="c9db2-134">In F#, asynchronous programming is centered around three core concepts:</span></span>

- <span data-ttu-id="c9db2-135">Тип `Async<'T>`, представляющий Составное асинхронное вычисление.</span><span class="sxs-lookup"><span data-stu-id="c9db2-135">The `Async<'T>` type, which represents a composable asynchronous computation.</span></span>
- <span data-ttu-id="c9db2-136">Функции модуля `Async`, которые позволяют планировать асинхронную работу, создавать асинхронные вычисления и преобразовывать асинхронные результаты.</span><span class="sxs-lookup"><span data-stu-id="c9db2-136">The `Async` module functions, which let you schedule asynchronous work, compose asynchronous computations, and transform asynchronous results.</span></span>
- <span data-ttu-id="c9db2-137">`async { }` [вычислительное выражение](../../language-reference/computation-expressions.md), предоставляющее удобный синтаксис для создания асинхронных вычислений и управления ими.</span><span class="sxs-lookup"><span data-stu-id="c9db2-137">The `async { }` [computation expression](../../language-reference/computation-expressions.md), which provides a convenient syntax for building and controlling asynchronous computations.</span></span>

<span data-ttu-id="c9db2-138">Эти три концепции можно увидеть в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="c9db2-138">You can see these three concepts in the following example:</span></span>

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    printTotalFileBytes "path-to-file.txt"
    |> Async.RunSynchronously

    Console.Read() |> ignore
    0
```

<span data-ttu-id="c9db2-139">В примере функция `printTotalFileBytes` имеет тип `string -> Async<unit>`.</span><span class="sxs-lookup"><span data-stu-id="c9db2-139">In the example, the `printTotalFileBytes` function is of type `string -> Async<unit>`.</span></span> <span data-ttu-id="c9db2-140">Вызов функции фактически не выполняет асинхронное вычисление.</span><span class="sxs-lookup"><span data-stu-id="c9db2-140">Calling the function does not actually execute the asynchronous computation.</span></span> <span data-ttu-id="c9db2-141">Вместо этого он возвращает `Async<unit>`, который выступает в качестве *спецификации* работы, выполняемой асинхронно.</span><span class="sxs-lookup"><span data-stu-id="c9db2-141">Instead, it returns an `Async<unit>` that acts as a *specification* of the work that is to execute asynchronously.</span></span> <span data-ttu-id="c9db2-142">Он вызывает `Async.AwaitTask` в своем тексте, который преобразует результат <xref:System.IO.File.WriteAllBytesAsync%2A> в соответствующий тип.</span><span class="sxs-lookup"><span data-stu-id="c9db2-142">It calls `Async.AwaitTask` in its body, which converts the result of <xref:System.IO.File.WriteAllBytesAsync%2A> to an appropriate type.</span></span>

<span data-ttu-id="c9db2-143">Еще одна важная строка — вызов `Async.RunSynchronously`.</span><span class="sxs-lookup"><span data-stu-id="c9db2-143">Another important line is the call to `Async.RunSynchronously`.</span></span> <span data-ttu-id="c9db2-144">Это одна из функций запуска асинхронного модуля, которые необходимо вызвать, если необходимо выполнить F# асинхронное вычисление.</span><span class="sxs-lookup"><span data-stu-id="c9db2-144">This is one of the Async module starting functions that you'll need to call if you want to actually execute an F# asynchronous computation.</span></span>

<span data-ttu-id="c9db2-145">Это фундаментальное различие в стиле C#/Visual Basic `async` программировании.</span><span class="sxs-lookup"><span data-stu-id="c9db2-145">This is a fundamental difference with the C#/Visual Basic style of `async` programming.</span></span> <span data-ttu-id="c9db2-146">В F#асинхронные вычисления можно рассматривать как **холодные задачи**.</span><span class="sxs-lookup"><span data-stu-id="c9db2-146">In F#, asynchronous computations can be thought of as **Cold tasks**.</span></span> <span data-ttu-id="c9db2-147">Они должны быть явным образом запущены для фактического выполнения.</span><span class="sxs-lookup"><span data-stu-id="c9db2-147">They must be explicitly started to actually execute.</span></span> <span data-ttu-id="c9db2-148">Это имеет некоторые преимущества, так как позволяет объединять и последовательно выполнять асинхронную работу гораздо проще, C# чем в или Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c9db2-148">This has some advantages, as it allows you to combine and sequence asynchronous work much more easily than in C# or Visual Basic.</span></span>

## <a name="combine-asynchronous-computations"></a><span data-ttu-id="c9db2-149">Объединение асинхронных вычислений</span><span class="sxs-lookup"><span data-stu-id="c9db2-149">Combine asynchronous computations</span></span>

<span data-ttu-id="c9db2-150">Ниже приведен пример, который строится на основе предыдущего путем объединения вычислений:</span><span class="sxs-lookup"><span data-stu-id="c9db2-150">Here is an example that builds upon the previous one by combining computations:</span></span>

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    argv
    |> Array.map printTotalFileBytes
    |> Async.Parallel
    |> Async.Ignore
    |> Async.RunSynchronously

    0
```

<span data-ttu-id="c9db2-151">Как видите, функция `main` имеет довольно много вызовов.</span><span class="sxs-lookup"><span data-stu-id="c9db2-151">As you can see, the `main` function has quite a few more calls made.</span></span> <span data-ttu-id="c9db2-152">По сути, он выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="c9db2-152">Conceptually, it does the following:</span></span>

1. <span data-ttu-id="c9db2-153">Преобразуйте аргументы командной строки в `Async<unit>` вычисления с `Array.map`.</span><span class="sxs-lookup"><span data-stu-id="c9db2-153">Transform the command-line arguments into `Async<unit>` computations with `Array.map`.</span></span>
2. <span data-ttu-id="c9db2-154">Создайте `Async<'T[]>`, который планирует и запускает `printTotalFileBytes` вычисления параллельно при запуске.</span><span class="sxs-lookup"><span data-stu-id="c9db2-154">Create an `Async<'T[]>` that schedules and runs the `printTotalFileBytes` computations in parallel when it runs.</span></span>
3. <span data-ttu-id="c9db2-155">Создайте `Async<unit>`, который будет выполнять параллельное вычисление и игнорировать его результат.</span><span class="sxs-lookup"><span data-stu-id="c9db2-155">Create an `Async<unit>` that will run the parallel computation and ignore its result.</span></span>
4. <span data-ttu-id="c9db2-156">Явным образом запустите Последнее вычисление с `Async.RunSynchronously` и заблокируйте его до завершения.</span><span class="sxs-lookup"><span data-stu-id="c9db2-156">Explicitly run the last computation with `Async.RunSynchronously` and block until it is completes.</span></span>

<span data-ttu-id="c9db2-157">При запуске этой программы `printTotalFileBytes` выполняется параллельно для каждого аргумента командной строки.</span><span class="sxs-lookup"><span data-stu-id="c9db2-157">When this program runs, `printTotalFileBytes` runs in parallel for each command-line argument.</span></span> <span data-ttu-id="c9db2-158">Поскольку асинхронные вычисления выполняются независимо от последовательности программ, порядок, в котором они печатаются, не задаются и завершается.</span><span class="sxs-lookup"><span data-stu-id="c9db2-158">Because asynchronous computations execute independently of program flow, there is no order in which they print their information and finish executing.</span></span> <span data-ttu-id="c9db2-159">Вычисления будут планироваться параллельно, но их порядок выполнения не гарантируется.</span><span class="sxs-lookup"><span data-stu-id="c9db2-159">The computations will be scheduled in parallel, but their order of execution is not guaranteed.</span></span>

## <a name="sequence-asynchronous-computations"></a><span data-ttu-id="c9db2-160">Асинхронные вычисления последовательности</span><span class="sxs-lookup"><span data-stu-id="c9db2-160">Sequence asynchronous computations</span></span>

<span data-ttu-id="c9db2-161">Поскольку `Async<'T>` является спецификацией работы, а не выполняемой ранее задачей, можно легко выполнять более сложные преобразования.</span><span class="sxs-lookup"><span data-stu-id="c9db2-161">Because `Async<'T>` is a specification of work rather than an already-running task, you can perform more intricate transformations easily.</span></span> <span data-ttu-id="c9db2-162">Ниже приведен пример, покоторому набор асинхронных вычислений помещается в последовательность, чтобы они выполнялись один за другим.</span><span class="sxs-lookup"><span data-stu-id="c9db2-162">Here is an example that sequences a set of Async computations so they execute one after another.</span></span>

```fsharp
let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    argv
    |> Array.map printTotalFileBytes
    |> Async.Sequential
    |> Async.Ignore
    |> Async.RunSynchronously
    |> ignore
```

<span data-ttu-id="c9db2-163">Это запланирует `printTotalFileBytes` выполняться в порядке элементов `argv` вместо того, чтобы планировать их параллельно.</span><span class="sxs-lookup"><span data-stu-id="c9db2-163">This will schedule `printTotalFileBytes` to execute in the order of the elements of `argv` rather than scheduling them in parallel.</span></span> <span data-ttu-id="c9db2-164">Поскольку следующий элемент не будет планироваться до тех пор, пока не завершится выполнение последнего вычисления, вычисления будут упорядочены таким, что в их выполнении не будет перекрываться.</span><span class="sxs-lookup"><span data-stu-id="c9db2-164">Because the next item will not be scheduled until after the last computation has finished executing, the computations are sequenced such that there is no overlap in their execution.</span></span>

## <a name="important-async-module-functions"></a><span data-ttu-id="c9db2-165">Важные функции асинхронного модуля</span><span class="sxs-lookup"><span data-stu-id="c9db2-165">Important Async module functions</span></span>

<span data-ttu-id="c9db2-166">При написании асинхронного кода F# в обычно взаимодействует с платформой, которая обрабатывает планирование вычислений.</span><span class="sxs-lookup"><span data-stu-id="c9db2-166">When you write async code in F# you'll usually interact with a framework that handles scheduling of computations for you.</span></span> <span data-ttu-id="c9db2-167">Однако это не всегда так, поэтому рекомендуется изучить различные начальные функции для планирования асинхронной работы.</span><span class="sxs-lookup"><span data-stu-id="c9db2-167">However, this is not always the case, so it is good to learn the various starting functions to schedule asynchronous work.</span></span>

<span data-ttu-id="c9db2-168">Поскольку F# асинхронные вычисления являются _спецификацией_ работы, а не представлением уже выполненной работы, они должны быть явно запущены с помощью начальной функции.</span><span class="sxs-lookup"><span data-stu-id="c9db2-168">Because F# asynchronous computations are a _specification_ of work rather than a representation of work that is already executing, they must be explicitly started with a starting function.</span></span> <span data-ttu-id="c9db2-169">Существует множество [функций асинхронного запуска](https://msdn.microsoft.com/library/ee370232.aspx) , которые полезны в разных контекстах.</span><span class="sxs-lookup"><span data-stu-id="c9db2-169">There are many [Async starting functions](https://msdn.microsoft.com/library/ee370232.aspx) that are helpful in different contexts.</span></span> <span data-ttu-id="c9db2-170">В следующем разделе описаны некоторые из наиболее распространенных начальных функций.</span><span class="sxs-lookup"><span data-stu-id="c9db2-170">The following section describes some of the more common starting functions.</span></span>

### <a name="asyncstartchild"></a><span data-ttu-id="c9db2-171">Async. Стартчилд</span><span class="sxs-lookup"><span data-stu-id="c9db2-171">Async.StartChild</span></span>

<span data-ttu-id="c9db2-172">Запускает дочерние вычисления в асинхронном вычислении.</span><span class="sxs-lookup"><span data-stu-id="c9db2-172">Starts a child computation within an asynchronous computation.</span></span> <span data-ttu-id="c9db2-173">Это позволяет параллельно выполнять несколько асинхронных вычислений.</span><span class="sxs-lookup"><span data-stu-id="c9db2-173">This allows multiple asynchronous computations to be executed concurrently.</span></span> <span data-ttu-id="c9db2-174">Дочерние вычисления совместно используют токен отмены с родительскими вычислениями.</span><span class="sxs-lookup"><span data-stu-id="c9db2-174">The child computation shares a cancellation token with the parent computation.</span></span> <span data-ttu-id="c9db2-175">Если родительские вычисления отменены, дочерние вычисления также отменяются.</span><span class="sxs-lookup"><span data-stu-id="c9db2-175">If the parent computation is canceled, the child computation is also canceled.</span></span>

<span data-ttu-id="c9db2-176">Сигнатура:</span><span class="sxs-lookup"><span data-stu-id="c9db2-176">Signature:</span></span>

```fsharp
computation: Async<'T> - timeout: ?int -> Async<Async<'T>>
```

<span data-ttu-id="c9db2-177">Когда следует использовать:</span><span class="sxs-lookup"><span data-stu-id="c9db2-177">When to use:</span></span>

- <span data-ttu-id="c9db2-178">Если требуется одновременное выполнение нескольких асинхронных вычислений, а не по одному, но не запланированных параллельно.</span><span class="sxs-lookup"><span data-stu-id="c9db2-178">When you want to execute multiple asynchronous computations concurrently rather than one at a time, but not have them scheduled in parallel.</span></span>
- <span data-ttu-id="c9db2-179">Если вы хотите привязать время существования дочернего вычисления к отношению к родительскому вычислению.</span><span class="sxs-lookup"><span data-stu-id="c9db2-179">When you wish to tie the lifetime of a child computation to that of a parent computation.</span></span>

<span data-ttu-id="c9db2-180">Что следует отслеживать:</span><span class="sxs-lookup"><span data-stu-id="c9db2-180">What to watch out for:</span></span>

- <span data-ttu-id="c9db2-181">Запуск нескольких вычислений с `Async.StartChild` не так же, как параллельное планирование.</span><span class="sxs-lookup"><span data-stu-id="c9db2-181">Starting multiple computations with `Async.StartChild` isn't the same as scheduling them in parallel.</span></span> <span data-ttu-id="c9db2-182">Если вы хотите запланировать вычисления параллельно, используйте `Async.Parallel`.</span><span class="sxs-lookup"><span data-stu-id="c9db2-182">If you wish to schedule computations in parallel, use `Async.Parallel`.</span></span>
- <span data-ttu-id="c9db2-183">Отмена родительских вычислений приведет к срабатыванию отмены всех запущенных дочерних вычислений.</span><span class="sxs-lookup"><span data-stu-id="c9db2-183">Canceling a parent computation will trigger cancellation of all child computations it started.</span></span>

### <a name="asyncstartimmediate"></a><span data-ttu-id="c9db2-184">Async. Стартиммедиате</span><span class="sxs-lookup"><span data-stu-id="c9db2-184">Async.StartImmediate</span></span>

<span data-ttu-id="c9db2-185">Выполняет асинхронное вычисление, немедленно запуская в текущем потоке операционной системы.</span><span class="sxs-lookup"><span data-stu-id="c9db2-185">Runs an asynchronous computation, starting immediately on the current operating system thread.</span></span> <span data-ttu-id="c9db2-186">Это полезно, если необходимо обновить что-либо в вызывающем потоке во время вычисления.</span><span class="sxs-lookup"><span data-stu-id="c9db2-186">This is helpful if you need to update something on the calling thread during the computation.</span></span> <span data-ttu-id="c9db2-187">Например, если асинхронное вычисление должно обновить пользовательский интерфейс (например, обновление индикатора выполнения), то `Async.StartImmediate` следует использовать.</span><span class="sxs-lookup"><span data-stu-id="c9db2-187">For example, if an asynchronous computation must update a UI (such as updating a progress bar), then `Async.StartImmediate` should be used.</span></span>

<span data-ttu-id="c9db2-188">Сигнатура:</span><span class="sxs-lookup"><span data-stu-id="c9db2-188">Signature:</span></span>

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="c9db2-189">Когда следует использовать:</span><span class="sxs-lookup"><span data-stu-id="c9db2-189">When to use:</span></span>

- <span data-ttu-id="c9db2-190">Когда необходимо обновить что-либо в вызывающем потоке в середине асинхронного вычисления.</span><span class="sxs-lookup"><span data-stu-id="c9db2-190">When you need to update something on the calling thread in the middle of an asynchronous computation.</span></span>

<span data-ttu-id="c9db2-191">Что следует отслеживать:</span><span class="sxs-lookup"><span data-stu-id="c9db2-191">What to watch out for:</span></span>

- <span data-ttu-id="c9db2-192">Код асинхронного вычисления будет выполняться в любом потоке, для которого выполняется планирование.</span><span class="sxs-lookup"><span data-stu-id="c9db2-192">Code in the asynchronous computation will run on whatever thread one happens to be scheduled on.</span></span> <span data-ttu-id="c9db2-193">Это может быть проблематичным, если поток имеет какой-то секрет, например поток пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="c9db2-193">This can be problematic if that thread is in some way sensitive, such as a UI thread.</span></span> <span data-ttu-id="c9db2-194">В таких случаях `Async.StartImmediate`, скорее всего, будет неприемлемым для использования.</span><span class="sxs-lookup"><span data-stu-id="c9db2-194">In such cases, `Async.StartImmediate` is likely inappropriate to use.</span></span>

### <a name="asyncstartastask"></a><span data-ttu-id="c9db2-195">Async. Стартастаск</span><span class="sxs-lookup"><span data-stu-id="c9db2-195">Async.StartAsTask</span></span>

<span data-ttu-id="c9db2-196">Выполняет вычисление в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="c9db2-196">Executes a computation in the thread pool.</span></span> <span data-ttu-id="c9db2-197">Возвращает <xref:System.Threading.Tasks.Task%601>, который будет выполнен в соответствующем состоянии после завершения вычисления (создает результат, вызывает исключение или возвращает значение Cancel).</span><span class="sxs-lookup"><span data-stu-id="c9db2-197">Returns a <xref:System.Threading.Tasks.Task%601> that will be completed on the corresponding state once the computation terminates (produces the result, throws exception, or gets canceled).</span></span> <span data-ttu-id="c9db2-198">Если токен отмены не указан, используется токен отмены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c9db2-198">If no cancellation token is provided, then the default cancellation token is used.</span></span>

<span data-ttu-id="c9db2-199">Сигнатура:</span><span class="sxs-lookup"><span data-stu-id="c9db2-199">Signature:</span></span>

```fsharp
computation: Async<'T> - taskCreationOptions: ?TaskCreationOptions - cancellationToken: ?CancellationToken -> Task<'T>
```

<span data-ttu-id="c9db2-200">Когда следует использовать:</span><span class="sxs-lookup"><span data-stu-id="c9db2-200">When to use:</span></span>

- <span data-ttu-id="c9db2-201">Когда необходимо вызвать API .NET, который требует <xref:System.Threading.Tasks.Task%601> для представления результата асинхронного вычисления.</span><span class="sxs-lookup"><span data-stu-id="c9db2-201">When you need to call into a .NET API that expects a <xref:System.Threading.Tasks.Task%601> to represent the result of an asynchronous computation.</span></span>

<span data-ttu-id="c9db2-202">Что следует отслеживать:</span><span class="sxs-lookup"><span data-stu-id="c9db2-202">What to watch out for:</span></span>

- <span data-ttu-id="c9db2-203">Этот вызов выделит дополнительный объект `Task`, который может увеличить издержки, если он часто используется.</span><span class="sxs-lookup"><span data-stu-id="c9db2-203">This call will allocate an additional `Task` object, which can increase overhead if it is used often.</span></span>

### <a name="asyncparallel"></a><span data-ttu-id="c9db2-204">Async. Parallel</span><span class="sxs-lookup"><span data-stu-id="c9db2-204">Async.Parallel</span></span>

<span data-ttu-id="c9db2-205">Планирует параллельное выполнение последовательности асинхронных вычислений.</span><span class="sxs-lookup"><span data-stu-id="c9db2-205">Schedules a sequence of asynchronous computations to be executed in parallel.</span></span> <span data-ttu-id="c9db2-206">Степень параллелизма может при необходимости настраиваться и регулироваться путем указания параметра `maxDegreesOfParallelism`.</span><span class="sxs-lookup"><span data-stu-id="c9db2-206">The degree of parallelism can be optionally tuned/throttled by specifying the `maxDegreesOfParallelism` parameter.</span></span>

<span data-ttu-id="c9db2-207">Сигнатура:</span><span class="sxs-lookup"><span data-stu-id="c9db2-207">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> - ?maxDegreesOfParallelism: int -> Async<'T[]>
```

<span data-ttu-id="c9db2-208">Когда следует использовать:</span><span class="sxs-lookup"><span data-stu-id="c9db2-208">When to use it:</span></span>

- <span data-ttu-id="c9db2-209">Значение, если необходимо одновременно запустить набор вычислений и не иметь никакой зависимости от их порядка выполнения.</span><span class="sxs-lookup"><span data-stu-id="c9db2-209">If you need to run a set of computations at the same time and have no reliance on their order of execution.</span></span>
- <span data-ttu-id="c9db2-210">Значение, если не требуется использовать результаты вычислений, запланированных параллельно, пока все они не будут завершены.</span><span class="sxs-lookup"><span data-stu-id="c9db2-210">If you don't require results from computations scheduled in parallel until they have all completed.</span></span>

<span data-ttu-id="c9db2-211">Что следует отслеживать:</span><span class="sxs-lookup"><span data-stu-id="c9db2-211">What to watch out for:</span></span>

- <span data-ttu-id="c9db2-212">Доступ к результирующему массиву значений можно получить только после завершения всех вычислений.</span><span class="sxs-lookup"><span data-stu-id="c9db2-212">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="c9db2-213">Вычисления будут выполняться, но они получат расписание.</span><span class="sxs-lookup"><span data-stu-id="c9db2-213">Computations will be run however they end up getting scheduled.</span></span> <span data-ttu-id="c9db2-214">Это означает, что нельзя полагаться на порядок их выполнения.</span><span class="sxs-lookup"><span data-stu-id="c9db2-214">This means you cannot rely on their order of their execution.</span></span>

### <a name="asyncsequential"></a><span data-ttu-id="c9db2-215">Асинхронный. последовательный</span><span class="sxs-lookup"><span data-stu-id="c9db2-215">Async.Sequential</span></span>

<span data-ttu-id="c9db2-216">Планирует выполнение последовательности асинхронных вычислений в том порядке, в котором они передаются.</span><span class="sxs-lookup"><span data-stu-id="c9db2-216">Schedules a sequence of asynchronous computations to be executed in the order that they are passed.</span></span> <span data-ttu-id="c9db2-217">Будут выполнены первые вычисления, далее и т. д.</span><span class="sxs-lookup"><span data-stu-id="c9db2-217">The first computation will be executed, then the next, and so on.</span></span> <span data-ttu-id="c9db2-218">Вычисления не будут выполняться параллельно.</span><span class="sxs-lookup"><span data-stu-id="c9db2-218">No computations will be executed in parallel.</span></span>

<span data-ttu-id="c9db2-219">Сигнатура:</span><span class="sxs-lookup"><span data-stu-id="c9db2-219">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> -> Async<'T[]>
```

<span data-ttu-id="c9db2-220">Когда следует использовать:</span><span class="sxs-lookup"><span data-stu-id="c9db2-220">When to use it:</span></span>

- <span data-ttu-id="c9db2-221">Значение, если необходимо выполнить несколько вычислений по порядку.</span><span class="sxs-lookup"><span data-stu-id="c9db2-221">If you need to execute multiple computations in order.</span></span>

<span data-ttu-id="c9db2-222">Что следует отслеживать:</span><span class="sxs-lookup"><span data-stu-id="c9db2-222">What to watch out for:</span></span>

- <span data-ttu-id="c9db2-223">Доступ к результирующему массиву значений можно получить только после завершения всех вычислений.</span><span class="sxs-lookup"><span data-stu-id="c9db2-223">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="c9db2-224">Вычисления будут выполняться в том порядке, в котором они передаются в эту функцию, что может означать, что больше времени должно пройти до возврата результатов.</span><span class="sxs-lookup"><span data-stu-id="c9db2-224">Computations will be run in the order that they are passed to this function, which can mean that more time will elapse before the results are returned.</span></span>

### <a name="asyncawaittask"></a><span data-ttu-id="c9db2-225">Async. Аваиттаск</span><span class="sxs-lookup"><span data-stu-id="c9db2-225">Async.AwaitTask</span></span>

<span data-ttu-id="c9db2-226">Возвращает асинхронное вычисление, которое ожидает завершения заданного <xref:System.Threading.Tasks.Task%601> и возвращает его результат в виде `Async<'T>`</span><span class="sxs-lookup"><span data-stu-id="c9db2-226">Returns an asynchronous computation that waits for the given <xref:System.Threading.Tasks.Task%601> to complete and returns its result as an `Async<'T>`</span></span>

<span data-ttu-id="c9db2-227">Сигнатура:</span><span class="sxs-lookup"><span data-stu-id="c9db2-227">Signature:</span></span>

```fsharp
task: Task<'T>  -> Async<'T>
```

<span data-ttu-id="c9db2-228">Когда следует использовать:</span><span class="sxs-lookup"><span data-stu-id="c9db2-228">When to use:</span></span>

- <span data-ttu-id="c9db2-229">При использовании API-интерфейса .NET, возвращающего <xref:System.Threading.Tasks.Task%601> в F# асинхронном вычислении.</span><span class="sxs-lookup"><span data-stu-id="c9db2-229">When you are consuming a .NET API that returns a <xref:System.Threading.Tasks.Task%601> within an F# asynchronous computation.</span></span>

<span data-ttu-id="c9db2-230">Что следует отслеживать:</span><span class="sxs-lookup"><span data-stu-id="c9db2-230">What to watch out for:</span></span>

- <span data-ttu-id="c9db2-231">Исключения упаковываются в <xref:System.AggregateException> соответствии с соглашением о библиотеке параллельных задач, и это отличается от асинхронного отображения F# исключений.</span><span class="sxs-lookup"><span data-stu-id="c9db2-231">Exceptions are wrapped in <xref:System.AggregateException> following the convention of the Task Parallel Library, and this is different from how F# async generally surfaces exceptions.</span></span>

### <a name="asynccatch"></a><span data-ttu-id="c9db2-232">Async. catch</span><span class="sxs-lookup"><span data-stu-id="c9db2-232">Async.Catch</span></span>

<span data-ttu-id="c9db2-233">Создает асинхронное вычисление, которое выполняет заданный `Async<'T>`, возвращая `Async<Choice<'T, exn>>`.</span><span class="sxs-lookup"><span data-stu-id="c9db2-233">Creates an asynchronous computation that executes a given `Async<'T>`, returning an `Async<Choice<'T, exn>>`.</span></span> <span data-ttu-id="c9db2-234">Если заданная `Async<'T>` успешно завершается, возвращается `Choice1Of2` с результирующим значением.</span><span class="sxs-lookup"><span data-stu-id="c9db2-234">If the given `Async<'T>` completes successfully, then a `Choice1Of2` is returned with the resultant value.</span></span> <span data-ttu-id="c9db2-235">Если перед завершением создается исключение, возвращается `Choice2of2` с вызванным исключением.</span><span class="sxs-lookup"><span data-stu-id="c9db2-235">If an exception is thrown before it completes, then a `Choice2of2` is returned with the raised exception.</span></span> <span data-ttu-id="c9db2-236">Если он используется в асинхронном вычислении, который состоит из многих вычислений, и одно из этих вычислений создает исключение, охватывающие вычисления будут полностью остановлены.</span><span class="sxs-lookup"><span data-stu-id="c9db2-236">If it is used on an asynchronous computation that is itself composed of many computations, and one of those computations throws an exception, the encompassing computation will be stopped entirely.</span></span>

<span data-ttu-id="c9db2-237">Сигнатура:</span><span class="sxs-lookup"><span data-stu-id="c9db2-237">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<Choice<'T, exn>>
```

<span data-ttu-id="c9db2-238">Когда следует использовать:</span><span class="sxs-lookup"><span data-stu-id="c9db2-238">When to use:</span></span>

- <span data-ttu-id="c9db2-239">При выполнении асинхронной работы, которая может завершиться с исключением, и необходимо обойти это исключение в вызывающем объекте.</span><span class="sxs-lookup"><span data-stu-id="c9db2-239">When you are performing asynchronous work that may fail with an exception and you want to handle that exception in the caller.</span></span>

<span data-ttu-id="c9db2-240">Что следует отслеживать:</span><span class="sxs-lookup"><span data-stu-id="c9db2-240">What to watch out for:</span></span>

- <span data-ttu-id="c9db2-241">При использовании Объединенных или последовательных асинхронных вычислений охватывающие вычисления будут полностью прекращаться, если одно из внутренних вычислений выдаст исключение.</span><span class="sxs-lookup"><span data-stu-id="c9db2-241">When using combined or sequenced asynchronous computations, the encompassing computation will fully stop if one of its "internal" computations throws an exception.</span></span>

### <a name="asyncignore"></a><span data-ttu-id="c9db2-242">Async. Ignore</span><span class="sxs-lookup"><span data-stu-id="c9db2-242">Async.Ignore</span></span>

<span data-ttu-id="c9db2-243">Создает асинхронное вычисление, которое выполняет заданное вычисление и игнорирует его результат.</span><span class="sxs-lookup"><span data-stu-id="c9db2-243">Creates an asynchronous computation that runs the given computation and ignores its result.</span></span>

<span data-ttu-id="c9db2-244">Сигнатура:</span><span class="sxs-lookup"><span data-stu-id="c9db2-244">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<unit>
```

<span data-ttu-id="c9db2-245">Когда следует использовать:</span><span class="sxs-lookup"><span data-stu-id="c9db2-245">When to use:</span></span>

- <span data-ttu-id="c9db2-246">При наличии асинхронного вычисления, результат которого не требуется.</span><span class="sxs-lookup"><span data-stu-id="c9db2-246">When you have an asynchronous computation whose result is not needed.</span></span> <span data-ttu-id="c9db2-247">Это аналогично коду `ignore` для неасинхронного кода.</span><span class="sxs-lookup"><span data-stu-id="c9db2-247">This is analogous to the `ignore` code for non-asynchronous code.</span></span>

<span data-ttu-id="c9db2-248">Что следует отслеживать:</span><span class="sxs-lookup"><span data-stu-id="c9db2-248">What to watch out for:</span></span>

- <span data-ttu-id="c9db2-249">Если необходимо использовать `Async.Start` или другую функцию, для которой требуется `Async<unit>`, рассмотрите возможность отмены результата.</span><span class="sxs-lookup"><span data-stu-id="c9db2-249">If you must use this because you wish to use `Async.Start` or another function that requires `Async<unit>`, consider if discarding the result is okay to do.</span></span> <span data-ttu-id="c9db2-250">Отмена результатов в соответствии с сигнатурой типа не должна выполняться обычно.</span><span class="sxs-lookup"><span data-stu-id="c9db2-250">Discarding results just to fit a type signature should not generally be done.</span></span>

### <a name="asyncrunsynchronously"></a><span data-ttu-id="c9db2-251">Async. RunSynchronously нельзя вызывать</span><span class="sxs-lookup"><span data-stu-id="c9db2-251">Async.RunSynchronously</span></span>

<span data-ttu-id="c9db2-252">Выполняет асинхронное вычисление и ожидает его результат в вызывающем потоке.</span><span class="sxs-lookup"><span data-stu-id="c9db2-252">Runs an asynchronous computation and awaits its result on the calling thread.</span></span> <span data-ttu-id="c9db2-253">Этот вызов блокируется.</span><span class="sxs-lookup"><span data-stu-id="c9db2-253">This call is blocking.</span></span>

<span data-ttu-id="c9db2-254">Сигнатура:</span><span class="sxs-lookup"><span data-stu-id="c9db2-254">Signature:</span></span>

```fsharp
computation: Async<'T> - timeout: ?int - cancellationToken: ?CancellationToken -> 'T
```

<span data-ttu-id="c9db2-255">Когда следует использовать:</span><span class="sxs-lookup"><span data-stu-id="c9db2-255">When to use it:</span></span>

- <span data-ttu-id="c9db2-256">Если это необходимо, используйте его только один раз в приложении — в точке входа исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="c9db2-256">If you need it, use it only once in an application - at the entry point for an executable.</span></span>
- <span data-ttu-id="c9db2-257">Если вы не следите за производительностью и хотите выполнить набор других асинхронных операций одновременно.</span><span class="sxs-lookup"><span data-stu-id="c9db2-257">When you don't care about performance and want to execute a set of other asynchronous operations at once.</span></span>

<span data-ttu-id="c9db2-258">Что следует отслеживать:</span><span class="sxs-lookup"><span data-stu-id="c9db2-258">What to watch out for:</span></span>

- <span data-ttu-id="c9db2-259">Вызов `Async.RunSynchronously` блокирует вызывающий поток до завершения выполнения.</span><span class="sxs-lookup"><span data-stu-id="c9db2-259">Calling `Async.RunSynchronously` blocks the calling thread until the execution completes.</span></span>

### <a name="asyncstart"></a><span data-ttu-id="c9db2-260">Async. Start</span><span class="sxs-lookup"><span data-stu-id="c9db2-260">Async.Start</span></span>

<span data-ttu-id="c9db2-261">Запускает асинхронное вычисление в пуле потоков, которое возвращает `unit`.</span><span class="sxs-lookup"><span data-stu-id="c9db2-261">Starts an asynchronous computation in the thread pool that returns `unit`.</span></span> <span data-ttu-id="c9db2-262">Не ждет своего результата.</span><span class="sxs-lookup"><span data-stu-id="c9db2-262">Doesn't wait for its result.</span></span> <span data-ttu-id="c9db2-263">Вложенные вычисления, запущенные с `Async.Start`, запускаются полностью независимо от родительских вычислений, которые вызвали их.</span><span class="sxs-lookup"><span data-stu-id="c9db2-263">Nested computations started with `Async.Start` are started completely independently of the parent computation that called them.</span></span> <span data-ttu-id="c9db2-264">Их время существования не привязано к какому-либо родительскому вычислению.</span><span class="sxs-lookup"><span data-stu-id="c9db2-264">Their lifetime is not tied to any parent computation.</span></span> <span data-ttu-id="c9db2-265">Если родительские вычисления отменены, дочерние вычисления не отменяются.</span><span class="sxs-lookup"><span data-stu-id="c9db2-265">If the parent computation is canceled, no child computations are cancelled.</span></span>

<span data-ttu-id="c9db2-266">Сигнатура:</span><span class="sxs-lookup"><span data-stu-id="c9db2-266">Signature:</span></span>

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="c9db2-267">Используйте только в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="c9db2-267">Use only when:</span></span>

- <span data-ttu-id="c9db2-268">Имеется асинхронное вычисление, которое не дает результата и/или требует обработки одного из них.</span><span class="sxs-lookup"><span data-stu-id="c9db2-268">You have an asynchronous computation that doesn't yield a result and/or require processing of one.</span></span>
- <span data-ttu-id="c9db2-269">Вам не нужно знать, когда завершается асинхронное вычисление.</span><span class="sxs-lookup"><span data-stu-id="c9db2-269">You don't need to know when an asynchronous computation completes.</span></span>
- <span data-ttu-id="c9db2-270">Вы не волнует, на каком потоке выполняется асинхронное вычисление.</span><span class="sxs-lookup"><span data-stu-id="c9db2-270">You don't care which thread an asynchronous computation runs on.</span></span>
- <span data-ttu-id="c9db2-271">У вас нет необходимости учитывать исключения, возникшие в результате выполнения задачи, и сообщать о них.</span><span class="sxs-lookup"><span data-stu-id="c9db2-271">You don't have any need to be aware of or report exceptions resulting from the task.</span></span>

<span data-ttu-id="c9db2-272">Что следует отслеживать:</span><span class="sxs-lookup"><span data-stu-id="c9db2-272">What to watch out for:</span></span>

- <span data-ttu-id="c9db2-273">Исключения, вызванные вычислениями, запущенными с `Async.Start`, не распространяются на вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="c9db2-273">Exceptions raised by computations started with `Async.Start` aren't propagated to the caller.</span></span> <span data-ttu-id="c9db2-274">Стек вызовов будет полностью развернут.</span><span class="sxs-lookup"><span data-stu-id="c9db2-274">The call stack will be completely unwound.</span></span>
- <span data-ttu-id="c9db2-275">Любая работа (например, вызов `printfn`), запущенная с `Async.Start`, не приведет к выполнению этого действия в основном потоке выполнения программы.</span><span class="sxs-lookup"><span data-stu-id="c9db2-275">Any effectful work (such as calling `printfn`) started with `Async.Start` won't cause the effect to happen on the main thread of a program's execution.</span></span>

## <a name="interoperate-with-net"></a><span data-ttu-id="c9db2-276">Взаимодействие с .NET</span><span class="sxs-lookup"><span data-stu-id="c9db2-276">Interoperate with .NET</span></span>

<span data-ttu-id="c9db2-277">Возможно, вы работаете с библиотекой или C# базой кода .NET, которая использует асинхронное программирование в стиле [async/await](../../../standard/async.md).</span><span class="sxs-lookup"><span data-stu-id="c9db2-277">You may be working with a .NET library or C# codebase that uses [async/await](../../../standard/async.md)-style asynchronous programming.</span></span> <span data-ttu-id="c9db2-278">Поскольку C# и большинство библиотек .NET используют типы <xref:System.Threading.Tasks.Task%601> и <xref:System.Threading.Tasks.Task> в качестве основных абстракций, а не `Async<'T>`, необходимо пересекать границы между этими двумя подходами и асинхронность.</span><span class="sxs-lookup"><span data-stu-id="c9db2-278">Because C# and the majority of .NET libraries use the <xref:System.Threading.Tasks.Task%601> and <xref:System.Threading.Tasks.Task> types as their core abstractions rather than `Async<'T>`, you must cross a boundary between these two approaches to asynchrony.</span></span>

### <a name="how-to-work-with-net-async-and-taskt"></a><span data-ttu-id="c9db2-279">Как работать с .NET Async и `Task<T>`</span><span class="sxs-lookup"><span data-stu-id="c9db2-279">How to work with .NET async and `Task<T>`</span></span>

<span data-ttu-id="c9db2-280">Работа с библиотеками асинхронных вычислений .NET и баз кода, использующих <xref:System.Threading.Tasks.Task%601> (то есть асинхронные вычисления, которые имеют возвращаемые значения), проста F#и имеет встроенную поддержку.</span><span class="sxs-lookup"><span data-stu-id="c9db2-280">Working with .NET async libraries and codebases that use <xref:System.Threading.Tasks.Task%601> (that is, async computations that have return values) is straightforward and has built-in support with F#.</span></span>

<span data-ttu-id="c9db2-281">Для ожидания асинхронного вычисления .NET можно использовать функцию `Async.AwaitTask`:</span><span class="sxs-lookup"><span data-stu-id="c9db2-281">You can use the `Async.AwaitTask` function to await a .NET asynchronous computation:</span></span>

```fsharp
let getValueFromLibrary param =
    async {
        let! value = DotNetLibrary.GetValueAsync param |> Async.AwaitTask
        return value
    }
```

<span data-ttu-id="c9db2-282">Функцию `Async.StartAsTask` можно использовать для передачи асинхронных вычислений вызывающему объекту .NET:</span><span class="sxs-lookup"><span data-stu-id="c9db2-282">You can use the `Async.StartAsTask` function to pass an asynchronous computation to a .NET caller:</span></span>

```fsharp
let computationForCaller param =
    async {
        let! result = getAsyncResult param
        return result
    } |> Async.StartAsTask
```

### <a name="how-to-work-with-net-async-and-task"></a><span data-ttu-id="c9db2-283">Как работать с .NET Async и `Task`</span><span class="sxs-lookup"><span data-stu-id="c9db2-283">How to work with .NET async and `Task`</span></span>

<span data-ttu-id="c9db2-284">Для работы с API, которые используют <xref:System.Threading.Tasks.Task> (то есть асинхронные вычисления .NET, которые не возвращают значение), может потребоваться добавить дополнительную функцию, которая преобразует `Async<'T>` в <xref:System.Threading.Tasks.Task>:</span><span class="sxs-lookup"><span data-stu-id="c9db2-284">To work with APIs that use <xref:System.Threading.Tasks.Task> (that is, .NET async computations that do not return a value), you may need to add an additional function that will convert an `Async<'T>` to a <xref:System.Threading.Tasks.Task>:</span></span>

```fsharp
module Async =
    // Async<unit> -> Task
    let startTaskFromAsyncUnit (comp: Async<unit>) =
        Async.StartAsTask comp :> Task
```

<span data-ttu-id="c9db2-285">Уже существует `Async.AwaitTask`, принимающая <xref:System.Threading.Tasks.Task> в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="c9db2-285">There is already an `Async.AwaitTask` that accepts a <xref:System.Threading.Tasks.Task> as input.</span></span> <span data-ttu-id="c9db2-286">С помощью этой и ранее определенной функции `startTaskFromAsyncUnit` можно запускать и ожидать <xref:System.Threading.Tasks.Task> типов из F# асинхронных вычислений.</span><span class="sxs-lookup"><span data-stu-id="c9db2-286">With this and the previously defined `startTaskFromAsyncUnit` function, you can start and await <xref:System.Threading.Tasks.Task> types from an F# async computation.</span></span>

## <a name="relationship-to-multi-threading"></a><span data-ttu-id="c9db2-287">Связь с многопоточностью</span><span class="sxs-lookup"><span data-stu-id="c9db2-287">Relationship to multi-threading</span></span>

<span data-ttu-id="c9db2-288">Несмотря на то, что в этой статье упоминается потоковая ситуация, необходимо помнить о двух важных вещах.</span><span class="sxs-lookup"><span data-stu-id="c9db2-288">Although threading is mentioned throughout this article, there are two important things to remember:</span></span>

1. <span data-ttu-id="c9db2-289">Нет сходства между асинхронным вычислением и потоком, если только явно не запущен в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="c9db2-289">There is no affinity between an asynchronous computation and a thread, unless explicitly started on the current thread.</span></span>
1. <span data-ttu-id="c9db2-290">Асинхронное программирование F# в не является абстракцией для многопоточности.</span><span class="sxs-lookup"><span data-stu-id="c9db2-290">Asynchronous programming in F# is not an abstraction for multi-threading.</span></span>

<span data-ttu-id="c9db2-291">Например, вычисление может фактически выполняться в потоке вызывающего объекта в зависимости от природы работы.</span><span class="sxs-lookup"><span data-stu-id="c9db2-291">For example, a computation may actually run on its caller's thread, depending on the nature of the work.</span></span> <span data-ttu-id="c9db2-292">Вычисления могут также "переходить" между потоками, позаимствование их в течение небольшого количества времени для выполнения полезной работы в период ожидания (например, при передаче сетевого вызова).</span><span class="sxs-lookup"><span data-stu-id="c9db2-292">A computation could also "jump" between threads, borrowing them for a small amount of time to do useful work in between periods of "waiting" (such as when a network call is in transit).</span></span>

<span data-ttu-id="c9db2-293">Хотя F# предоставляет некоторые возможности для запуска асинхронного вычисления в текущем потоке (или явно не в текущем потоке), асинхронность обычно не связан с конкретной стратегией потоков.</span><span class="sxs-lookup"><span data-stu-id="c9db2-293">Although F# provides some abilities to start an asynchronous computation on the current thread (or explicitly not on the current thread), asynchrony generally is not associated with a particular threading strategy.</span></span>

## <a name="see-also"></a><span data-ttu-id="c9db2-294">См. также:</span><span class="sxs-lookup"><span data-stu-id="c9db2-294">See also</span></span>

- [<span data-ttu-id="c9db2-295">F# Асинхронная модель программирования</span><span class="sxs-lookup"><span data-stu-id="c9db2-295">The F# Asynchronous Programming Model</span></span>](https://www.microsoft.com/research/publication/the-f-asynchronous-programming-model)
- [<span data-ttu-id="c9db2-296">F# Асинхронное руководством по Jet. com</span><span class="sxs-lookup"><span data-stu-id="c9db2-296">Jet.com's F# Async Guide</span></span>](https://medium.com/jettech/f-async-guide-eb3c8a2d180a)
- [<span data-ttu-id="c9db2-297">F#для получения удовольствия и асинхронного программного программирования прибыли</span><span class="sxs-lookup"><span data-stu-id="c9db2-297">F# for fun and profit's Asynchronous Programming guide</span></span>](https://fsharpforfunandprofit.com/posts/concurrency-async-and-parallel/)
- [<span data-ttu-id="c9db2-298">Асинхронные C# в F#и: асинхронные проблемы вC#</span><span class="sxs-lookup"><span data-stu-id="c9db2-298">Async in C# and F#: Asynchronous gotchas in C#</span></span>](http://tomasp.net/blog/csharp-async-gotchas.aspx/)
