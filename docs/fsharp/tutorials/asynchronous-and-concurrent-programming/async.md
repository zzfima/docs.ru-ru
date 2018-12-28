---
title: Асинхронное программирование
description: Узнайте, как F# асинхронного программирования можно выполнить посредством модель языка программирования, простой в использовании и естественный язык.
ms.date: 06/20/2016
ms.openlocfilehash: e18697708741eef066a76bbffe35882f3639bb68
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53614484"
---
# <a name="async-programming-in-f"></a><span data-ttu-id="75490-103">Асинхронное программирование вF#</span><span class="sxs-lookup"><span data-stu-id="75490-103">Async Programming in F#</span></span> #

> [!NOTE]
> <span data-ttu-id="75490-104">В этой статье были обнаружены некоторые неточности.</span><span class="sxs-lookup"><span data-stu-id="75490-104">Some inaccuracies have been discovered in this article.</span></span>  <span data-ttu-id="75490-105">Она переписывается.</span><span class="sxs-lookup"><span data-stu-id="75490-105">It is being rewritten.</span></span>  <span data-ttu-id="75490-106">См. в разделе [проблема № 666](https://github.com/dotnet/docs/issues/666) Дополнительные сведения об изменениях.</span><span class="sxs-lookup"><span data-stu-id="75490-106">See [Issue #666](https://github.com/dotnet/docs/issues/666) to learn about the changes.</span></span>

<span data-ttu-id="75490-107">Асинхронное программирование в F# решается с помощью модели программирования уровня языка должна быть простой в использовании и естественный язык.</span><span class="sxs-lookup"><span data-stu-id="75490-107">Async programming in F# can be accomplished through a language-level programming model designed to be easy to use and natural to the language.</span></span>

<span data-ttu-id="75490-108">Основой асинхронного программирования в F# — `Async<'T>`, представление работы, который можно активировать для выполнения в фоновом режиме, где `'T` — либо тип, возвращаемый через специальную `return` ключевое слово или `unit` если асинхронный рабочий процесс не имеет результатов для возврата.</span><span class="sxs-lookup"><span data-stu-id="75490-108">The core of async programming in F# is `Async<'T>`, a representation of work that can be triggered to run in the background, where `'T` is either the type returned via the special `return` keyword or `unit` if the async workflow has no result to return.</span></span>

<span data-ttu-id="75490-109">Ключевым принципом, чтобы понять, является тип выражение async `Async<'T>`, который является просто _спецификации_ выполняться в контексте асинхронной работы.</span><span class="sxs-lookup"><span data-stu-id="75490-109">The key concept to understand is that an async expression’s type is `Async<'T>`, which is merely a _specification_ of work to be done in an asynchronous context.</span></span> <span data-ttu-id="75490-110">Он не будет работать, пока не запустить ее явно с помощью одного из начала функции (такие как `Async.RunSynchronously`).</span><span class="sxs-lookup"><span data-stu-id="75490-110">It is not executed until you explicitly start it with one of the starting functions (such as `Async.RunSynchronously`).</span></span> <span data-ttu-id="75490-111">Несмотря на то, что это другой способ думать о работу, в конечном итоге довольно проста, на практике.</span><span class="sxs-lookup"><span data-stu-id="75490-111">Although this is a different way of thinking about doing work, it ends up being quite simple in practice.</span></span>

<span data-ttu-id="75490-112">Например предположим, что вы хотите скачать код HTML из dotnetfoundation.org без блокирования основного потока.</span><span class="sxs-lookup"><span data-stu-id="75490-112">For example, say you wanted to download the HTML from dotnetfoundation.org without blocking the main thread.</span></span> <span data-ttu-id="75490-113">Его можно сделать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="75490-113">You can accomplish it like this:</span></span>

```fsharp
open System
open System.Net

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()

        // Execution of fetchHtmlAsync won't continue until the result
        // of AsyncDownloadString is bound.
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

let html = "https://dotnetfoundation.org" |> fetchHtmlAsync |> Async.RunSynchronously
printfn "%s" html
```

<span data-ttu-id="75490-114">Вот и все!</span><span class="sxs-lookup"><span data-stu-id="75490-114">And that’s it!</span></span> <span data-ttu-id="75490-115">Несмотря на использование `async`, `let!`, и `return`, это просто нормально F# кода.</span><span class="sxs-lookup"><span data-stu-id="75490-115">Aside from the use of `async`, `let!`, and `return`, this is just normal F# code.</span></span>

<span data-ttu-id="75490-116">Существует несколько синтаксических конструкций, которые стоит обратить внимание:</span><span class="sxs-lookup"><span data-stu-id="75490-116">There are a few syntactical constructs which are worth noting:</span></span>

*   <span data-ttu-id="75490-117">`let!` Привязывает результат выражения async (выполняющегося в другом контексте).</span><span class="sxs-lookup"><span data-stu-id="75490-117">`let!` binds the result of an async expression (which runs on another context).</span></span>
*   <span data-ttu-id="75490-118">`use!` работает аналогично `let!`, но удаляет ее связанных ресурсов в том случае, когда оно выходит за пределы области.</span><span class="sxs-lookup"><span data-stu-id="75490-118">`use!` works just like `let!`, but disposes its bound resources when it goes out of scope.</span></span>
*   <span data-ttu-id="75490-119">`do!` будет ожидать асинхронный рабочий процесс, который не возвращает ничего.</span><span class="sxs-lookup"><span data-stu-id="75490-119">`do!` will await an async workflow which doesn’t return anything.</span></span>
*   <span data-ttu-id="75490-120">`return` просто возвращает результат из асинхронного выражения.</span><span class="sxs-lookup"><span data-stu-id="75490-120">`return` simply returns a result from an async expression.</span></span>
*   <span data-ttu-id="75490-121">`return!` выполняет другой асинхронный рабочий процесс и возвращает его возвращаемое значение в результате.</span><span class="sxs-lookup"><span data-stu-id="75490-121">`return!` executes another async workflow and returns its return value as a result.</span></span>

<span data-ttu-id="75490-122">Кроме того обычные `let`, `use`, и `do` ключевые слова могут использоваться вместе со асинхронные версии, так же, как это было бы в обычной функции.</span><span class="sxs-lookup"><span data-stu-id="75490-122">Additionally, normal `let`, `use`, and `do` keywords can be used alongside the async versions just as they would in a normal function.</span></span>

## <a name="how-to-start-async-code-in-f"></a><span data-ttu-id="75490-123">Запуск асинхронного кода вF#</span><span class="sxs-lookup"><span data-stu-id="75490-123">How to start Async Code in F#</span></span> #

<span data-ttu-id="75490-124">Как уже упоминалось, асинхронный код представляет собой спецификацию должны быть выполнены в другом контексте, который должен быть явным образом запущено.</span><span class="sxs-lookup"><span data-stu-id="75490-124">As mentioned earlier, async code is a specification of work to be done in another context which needs to be explicitly started.</span></span> <span data-ttu-id="75490-125">Ниже приведены два основных способа выполнения этой задачи:</span><span class="sxs-lookup"><span data-stu-id="75490-125">Here are two primary ways to accomplish this:</span></span>

1.  <span data-ttu-id="75490-126">`Async.RunSynchronously` запускается поток async в другом потоке и ожидает его результат.</span><span class="sxs-lookup"><span data-stu-id="75490-126">`Async.RunSynchronously` will start an async workflow on another thread and await its result.</span></span>

```fsharp
open System
open System.Net

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

 // Execution will pause until fetchHtmlAsync finishes
 let html = "https://dotnetfoundation.org" |> fetchHtmlAsync |> Async.RunSynchronously

 // you actually have the result from fetchHtmlAsync now!
 printfn "%s" html
 ```

2.  <span data-ttu-id="75490-127">`Async.Start` Запуск рабочего процесса async в другом потоке и будет **не** ожидает его результат.</span><span class="sxs-lookup"><span data-stu-id="75490-127">`Async.Start` will start an async workflow on another thread, and will **not** await its result.</span></span>

```fsharp
open System
open System.Net
  
let uploadDataAsync url data = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        webClient.UploadStringAsync(uri, data)
    }

let workflow = uploadDataAsync "https://url-to-upload-to.com" "hello, world!"

// Execution will continue after calling this!
Async.Start(workflow)

printfn "%s" "uploadDataAsync is running in the background..."
 ```

<span data-ttu-id="75490-128">Существуют другие способы запуска асинхронного рабочего процесса, доступного для конкретных сценариев.</span><span class="sxs-lookup"><span data-stu-id="75490-128">There are other ways to start an async workflow available for more specific scenarios.</span></span> <span data-ttu-id="75490-129">Они подробно описаны [справочника по Async](https://msdn.microsoft.com/library/ee370232.aspx).</span><span class="sxs-lookup"><span data-stu-id="75490-129">They are detailed [in the Async reference](https://msdn.microsoft.com/library/ee370232.aspx).</span></span>

### <a name="a-note-on-threads"></a><span data-ttu-id="75490-130">Примечание о потоках</span><span class="sxs-lookup"><span data-stu-id="75490-130">A Note on Threads</span></span>

<span data-ttu-id="75490-131">Фраза «в другом потоке» упомянутой выше, но очень важно знать, что **это не означает, что асинхронных рабочих потоков являются фасадом для многопоточности**.</span><span class="sxs-lookup"><span data-stu-id="75490-131">The phrase "on another thread" is mentioned above, but it is important to know that **this does not mean that async workflows are a facade for multithreading**.</span></span> <span data-ttu-id="75490-132">Рабочий процесс фактически «переходит» между потоками, заимствуя их для небольшой объем выполнять полезную работу.</span><span class="sxs-lookup"><span data-stu-id="75490-132">The workflow actually "jumps" between threads, borrowing them for a small amount of time to do useful work.</span></span> <span data-ttu-id="75490-133">Когда поток async эффективно «ожидает» (например, ожидания сетевого вызова, чтобы он возвращал нечто), любой поток, который он займов во время освобождается до перейдите выполнять полезную работу на что-то еще.</span><span class="sxs-lookup"><span data-stu-id="75490-133">When an async workflow is effectively "waiting" (for example, waiting for a network call to return something), any thread it was borrowing at the time is freed up to go do useful work on something else.</span></span> <span data-ttu-id="75490-134">Это позволяет асинхронных рабочих потоков для использования системы, в которой они выполняются так же эффективно и делает их особенно высоки сценариях с большим количеством операций ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="75490-134">This allows async workflows to utilize the system they run on as effectively as possible, and makes them especially strong for high-volume I/O scenarios.</span></span>

## <a name="how-to-add-parallelism-to-async-code"></a><span data-ttu-id="75490-135">Добавление параллелизма в асинхронный код</span><span class="sxs-lookup"><span data-stu-id="75490-135">How to Add Parallelism to Async Code</span></span>

<span data-ttu-id="75490-136">Иногда можно требуется для выполнения нескольких асинхронных заданий в параллельном режиме, собирать их результаты и интерпретировать их каким-либо образом.</span><span class="sxs-lookup"><span data-stu-id="75490-136">Sometimes you may need to perform multiple asynchronous jobs in parallel, collect their results, and interpret them in some way.</span></span> <span data-ttu-id="75490-137">`Async.Parallel` позволяет это сделать без необходимости использования библиотеки параллельных задач, на которой будет включать в себя необходимости приводимое `Task<'T>` и `Async<'T>` типов.</span><span class="sxs-lookup"><span data-stu-id="75490-137">`Async.Parallel` allows you to do this without needing to use the Task Parallel Library, which would involve needing to coerce `Task<'T>` and `Async<'T>` types.</span></span>

<span data-ttu-id="75490-138">Следующий пример будет использоваться `Async.Parallel` Чтобы загрузить HTML-код из четырех популярных сайтов в параллельном режиме, дождитесь завершения выполнения этих задач и затем напечатайте HTML, который был загружен.</span><span class="sxs-lookup"><span data-stu-id="75490-138">The following example will use `Async.Parallel` to download the HTML from four popular sites in parallel, wait for those tasks to complete, and then print the HTML which was downloaded.</span></span>

```fsharp
open System
open System.Net

let urlList = 
    [ "https://www.microsoft.com"
      "https://www.google.com"
      "https://www.amazon.com"
      "https://www.facebook.com" ]

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

let getHtmlList urls =
    urls
    |> Seq.map fetchHtmlAsync   // Build an Async<'T> for each site
    |> Async.Parallel           // Returns an Async<'T []>
    |> Async.RunSynchronously   // Wait for the result of the parallel work

let htmlList = getHtmlList urlList

// We now have the downloaded HTML for each site!
for html in htmlList do
    printfn "%s" html
```

## <a name="important-info-and-advice"></a><span data-ttu-id="75490-139">Важные сведения и советы</span><span class="sxs-lookup"><span data-stu-id="75490-139">Important Info and Advice</span></span>

*   <span data-ttu-id="75490-140">Добавьте «Async» в конец любой функции, которые вы будете использовать</span><span class="sxs-lookup"><span data-stu-id="75490-140">Append "Async" to the end of any functions you’ll consume</span></span>

 <span data-ttu-id="75490-141">Несмотря на то, что это просто соглашения об именовании, он облегчить как возможность обнаружения API.</span><span class="sxs-lookup"><span data-stu-id="75490-141">Although this is just a naming convention, it does make things like API discoverability easier.</span></span> <span data-ttu-id="75490-142">Особенно в том случае, если существуют синхронные и асинхронные версии той же подпрограммы, рекомендуется явно указать, который выполняется асинхронно с помощью имени.</span><span class="sxs-lookup"><span data-stu-id="75490-142">Particularly if there are synchronous and asynchronous versions of the same routine, it’s a good idea to explicitly state which is asynchronous via the name.</span></span>

*   <span data-ttu-id="75490-143">Прослушайте компилятор!</span><span class="sxs-lookup"><span data-stu-id="75490-143">Listen to the compiler!</span></span>

 <span data-ttu-id="75490-144">F#в компилятор очень строгие, делая практически невозможно сделать что-то беспокоят как синхронное выполнение кода «async».</span><span class="sxs-lookup"><span data-stu-id="75490-144">F#’s compiler is very strict, making it nearly impossible to do something troubling like run "async" code synchronously.</span></span> <span data-ttu-id="75490-145">Если вам встретится предупреждение, это знак, что код не будет выполняться, как вы считаете, что будет происходить.</span><span class="sxs-lookup"><span data-stu-id="75490-145">If you come across a warning, that’s a sign that the code won’t execute how you think it will.</span></span> <span data-ttu-id="75490-146">Если компилятор может сделать удачного, код скорее всего будет выполнен должным образом.</span><span class="sxs-lookup"><span data-stu-id="75490-146">If you can make the compiler happy, your code will most likely execute as expected.</span></span>

## <a name="for-the-cvb-programmer-looking-into-f"></a><span data-ttu-id="75490-147">Для C#и Visual Basic программист, рассматриваяF#</span><span class="sxs-lookup"><span data-stu-id="75490-147">For the C#/VB Programmer Looking Into F#</span></span> #

<span data-ttu-id="75490-148">В этом разделе предполагается, что вы знакомы с моделью async в C#/VB.</span><span class="sxs-lookup"><span data-stu-id="75490-148">This section assumes you’re familiar with the async model in C#/VB.</span></span> <span data-ttu-id="75490-149">Если вы не, [асинхронного программирования в C# ](../../../csharp/async.md) является отправной точкой.</span><span class="sxs-lookup"><span data-stu-id="75490-149">If you are not, [Async Programming in C#](../../../csharp/async.md) is a starting point.</span></span>

<span data-ttu-id="75490-150">Есть фундаментальные различия между C#модели асинхронного и Visual Basic и F# асинхронной модели.</span><span class="sxs-lookup"><span data-stu-id="75490-150">There is a fundamental difference between the C#/VB async model and the F# async model.</span></span>

<span data-ttu-id="75490-151">При вызове функции, которая возвращает `Task` или `Task<'T>`, это задание уже началось выполнение.</span><span class="sxs-lookup"><span data-stu-id="75490-151">When you call a function which returns a `Task` or `Task<'T>`, that job has already begun execution.</span></span> <span data-ttu-id="75490-152">Дескриптор, возвращенный представляет задание уже выполняющейся асинхронной.</span><span class="sxs-lookup"><span data-stu-id="75490-152">The handle returned represents an already-running asynchronous job.</span></span> <span data-ttu-id="75490-153">Напротив, при вызове асинхронной функции F#, `Async<'a>` возвращается представляет задание, которое будет иметь **создан** в определенный момент.</span><span class="sxs-lookup"><span data-stu-id="75490-153">In contrast, when you call an async function in F#, the `Async<'a>` returned represents a job which will be **generated** at some point.</span></span> <span data-ttu-id="75490-154">Основные сведения об этой модели обладает широкими возможностями, так как он позволяет асинхронных заданий в F# объединять в цепочку, выполняется по условию и запускаться с большей степенью детализации в элемент управления.</span><span class="sxs-lookup"><span data-stu-id="75490-154">Understanding this model is powerful, because it allows for asynchronous jobs in F# to be chained together easier, performed conditionally, and be started with a finer grain of control.</span></span>

<span data-ttu-id="75490-155">Существует несколько других сходства и различия, следует отметить.</span><span class="sxs-lookup"><span data-stu-id="75490-155">There are a few other similarities and differences worth noting.</span></span>

### <a name="similarities"></a><span data-ttu-id="75490-156">Сходства</span><span class="sxs-lookup"><span data-stu-id="75490-156">Similarities</span></span>

*   <span data-ttu-id="75490-157">`let!`, `use!`, и `do!` аналогичны `await` при вызове задание async изнутри `async{ }` блока.</span><span class="sxs-lookup"><span data-stu-id="75490-157">`let!`, `use!`, and `do!` are analogous to `await` when calling an async job from within an `async{ }` block.</span></span>

 <span data-ttu-id="75490-158">Три ключевых слова можно использовать только в пределах `async { }` блока, подобно тому, как `await` может быть вызван только внутри `async` метод.</span><span class="sxs-lookup"><span data-stu-id="75490-158">The three keywords can only be used within an `async { }` block, similar to how `await` can only be invoked inside an `async` method.</span></span> <span data-ttu-id="75490-159">Короче говоря `let!` применяется для записи и использовании результате `use!` является прежним, но для чего-нибудь, ресурсы которых следует удаляются после его использования, и `do!` применяется для ожидания для асинхронных рабочего процесса без возвращаемого значения, чтобы завершить Прежде чем продолжить.</span><span class="sxs-lookup"><span data-stu-id="75490-159">In short, `let!` is for when you want to capture and use a result, `use!` is the same but for something whose resources should get cleaned after it’s used, and `do!` is for when you want to wait for an async workflow with no return value to finish before moving on.</span></span>

*   <span data-ttu-id="75490-160">F#поддерживает параллелизм данных аналогичным образом.</span><span class="sxs-lookup"><span data-stu-id="75490-160">F# supports data-parallelism in a similar way.</span></span>

 <span data-ttu-id="75490-161">Несмотря на то, что она работает очень по-разному, `Async.Parallel` соответствует `Task.WhenAll` для сценария реагируя результаты набор заданий async после их полного завершения.</span><span class="sxs-lookup"><span data-stu-id="75490-161">Although it operates very differently, `Async.Parallel` corresponds to `Task.WhenAll` for the scenario of wanting the results of a set of async jobs when they all complete.</span></span>

### <a name="differences"></a><span data-ttu-id="75490-162">Различия</span><span class="sxs-lookup"><span data-stu-id="75490-162">Differences</span></span>

*   <span data-ttu-id="75490-163">Вложенные `let!` не разрешено, в отличие от вложенных `await`</span><span class="sxs-lookup"><span data-stu-id="75490-163">Nested `let!` is not allowed, unlike nested `await`</span></span>

 <span data-ttu-id="75490-164">В отличие от `await`, которой могут быть вложенными неопределенно долгое время, `let!` не может и должен иметь результат привязан перед его использованием внутрь другой `let!`, `do!`, или `use!`.</span><span class="sxs-lookup"><span data-stu-id="75490-164">Unlike `await`, which can be nested indefinitely, `let!` cannot and must have its result bound before using it inside of another `let!`, `do!`, or `use!`.</span></span>

*   <span data-ttu-id="75490-165">Поддержка отмены проще в F# чем в C#/VB.</span><span class="sxs-lookup"><span data-stu-id="75490-165">Cancellation support is simpler in F# than in C#/VB.</span></span>

 <span data-ttu-id="75490-166">Поддержка отмены задачи во время его выполнения C#и Visual Basic требуется выполнить проверку `IsCancellationRequested` свойства или вызов `ThrowIfCancellationRequested()` на `CancellationToken` объект, который передается в асинхронный метод.</span><span class="sxs-lookup"><span data-stu-id="75490-166">Supporting cancellation of a task midway through its execution in C#/VB requires checking the `IsCancellationRequested` property or calling `ThrowIfCancellationRequested()` on a `CancellationToken` object that’s passed into the async method.</span></span>

<span data-ttu-id="75490-167">Напротив F# более естественным образом будет поддерживать отмену асинхронных рабочих потоков.</span><span class="sxs-lookup"><span data-stu-id="75490-167">In contrast, F# async workflows are more naturally cancellable.</span></span> <span data-ttu-id="75490-168">Отмена является простой трехшаговый процесс.</span><span class="sxs-lookup"><span data-stu-id="75490-168">Cancellation is a simple three-step process.</span></span>

1.  <span data-ttu-id="75490-169">Создайте объект `CancellationTokenSource`.</span><span class="sxs-lookup"><span data-stu-id="75490-169">Create a new `CancellationTokenSource`.</span></span>
2.  <span data-ttu-id="75490-170">Передайте его в функция запуска.</span><span class="sxs-lookup"><span data-stu-id="75490-170">Pass it into a starting function.</span></span>
3.  <span data-ttu-id="75490-171">Вызовите `Cancel` в маркере.</span><span class="sxs-lookup"><span data-stu-id="75490-171">Call `Cancel` on the token.</span></span>

<span data-ttu-id="75490-172">Пример</span><span class="sxs-lookup"><span data-stu-id="75490-172">Example:</span></span>

```fsharp
open System.Threading

// Create a workflow which will loop forever.
let workflow =
    async {
        while true do
            printfn "Working..."
            do! Async.Sleep 1000
    }
    
let tokenSource = new CancellationTokenSource()

// Start the workflow in the background
Async.Start (workflow, tokenSource.Token)

// Executing the next line will stop the workflow
tokenSource.Cancel()
```

<span data-ttu-id="75490-173">Вот и все!</span><span class="sxs-lookup"><span data-stu-id="75490-173">And that’s it!</span></span>

## <a name="further-resources"></a><span data-ttu-id="75490-174">Дополнительные ресурсы:</span><span class="sxs-lookup"><span data-stu-id="75490-174">Further resources:</span></span>

*   [<span data-ttu-id="75490-175">Асинхронных рабочих потоков на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="75490-175">Async Workflows on MSDN</span></span>](https://msdn.microsoft.com/library/dd233250.aspx)
*   [<span data-ttu-id="75490-176">Асинхронные последовательностей дляF#</span><span class="sxs-lookup"><span data-stu-id="75490-176">Asynchronous Sequences for F#</span></span>](https://fsprojects.github.io/FSharp.Control.AsyncSeq/library/AsyncSeq.html)
*   [<span data-ttu-id="75490-177">F#Служебные программы данных HTTP</span><span class="sxs-lookup"><span data-stu-id="75490-177">F# Data HTTP Utilities</span></span>](https://fsharp.github.io/FSharp.Data/library/Http.html)