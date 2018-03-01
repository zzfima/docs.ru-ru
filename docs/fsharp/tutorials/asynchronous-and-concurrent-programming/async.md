---
title: "Асинхронное программирование на F #"
description: "Узнайте, как асинхронное программирование на F # выполняется через модель уровня языка программирования, просты в использовании и естественный язык."
keywords: .NET, .NET Core
author: cartermp
ms.author: phcart
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f9196bfc-b8a8-4d33-8b53-0dcbd58a69d8
ms.openlocfilehash: c3fde46e804b7acac78d3ce5454a3c6f806e24e7
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2018
---
# <a name="async-programming-in-f"></a><span data-ttu-id="8d354-104">Асинхронное программирование на F #</span><span class="sxs-lookup"><span data-stu-id="8d354-104">Async Programming in F#</span></span> #

> [!NOTE]
> <span data-ttu-id="8d354-105">В этой статье были обнаружены некоторые неточности.</span><span class="sxs-lookup"><span data-stu-id="8d354-105">Some inaccuracies have been discovered in this article.</span></span>  <span data-ttu-id="8d354-106">Он перезаписывается.</span><span class="sxs-lookup"><span data-stu-id="8d354-106">It is being rewritten.</span></span>  <span data-ttu-id="8d354-107">В разделе [проблема #666](https://github.com/dotnet/docs/issues/666) Дополнительные сведения об изменениях.</span><span class="sxs-lookup"><span data-stu-id="8d354-107">See [Issue #666](https://github.com/dotnet/docs/issues/666) to learn about the changes.</span></span>

<span data-ttu-id="8d354-108">Асинхронное программирование на F # можно сделать с помощью модели программирования уровня языка в использовании и естественный язык.</span><span class="sxs-lookup"><span data-stu-id="8d354-108">Async programming in F# can be accomplished through a language-level programming model designed to be easy to use and natural to the language.</span></span>

<span data-ttu-id="8d354-109">Асинхронное программирование на F # лежит `Async<'T>`, представление работы, которая запускается в фоновом режиме, где `'T` — либо тип, возвращаемый через специальные `return` ключевое слово или `unit` если асинхронный рабочий процесс не имеет результат, возвращаемый.</span><span class="sxs-lookup"><span data-stu-id="8d354-109">The core of async programming in F# is `Async<'T>`, a representation of work that can be triggered to run in the background, where `'T` is either the type returned via the special `return` keyword or `unit` if the async workflow has no result to return.</span></span>

<span data-ttu-id="8d354-110">Ключевым принципом, чтобы понять, является тип выражение async `Async<'T>`, который является просто _спецификации_ выполняться в контексте асинхронной работы.</span><span class="sxs-lookup"><span data-stu-id="8d354-110">The key concept to understand is that an async expression’s type is `Async<'T>`, which is merely a _specification_ of work to be done in an asynchronous context.</span></span> <span data-ttu-id="8d354-111">Не выполняется, пока не запустить ее явно с помощью одного из начала функции (такие как `Async.RunSynchronously`).</span><span class="sxs-lookup"><span data-stu-id="8d354-111">It is not executed until you explicitly start it with one of the starting functions (such as `Async.RunSynchronously`).</span></span> <span data-ttu-id="8d354-112">Несмотря на то, что это другим способом обдумывания выполняет работу, он получилась довольно просто на практике.</span><span class="sxs-lookup"><span data-stu-id="8d354-112">Although this is a different way of thinking about doing work, it ends up being quite simple in practice.</span></span>

<span data-ttu-id="8d354-113">Например предположим, что требуется загрузить dotnetfoundation.org HTML-код, не блокируя основной поток.</span><span class="sxs-lookup"><span data-stu-id="8d354-113">For example, say you wanted to download the HTML from dotnetfoundation.org without blocking the main thread.</span></span> <span data-ttu-id="8d354-114">Вы можете добиться следующим образом.</span><span class="sxs-lookup"><span data-stu-id="8d354-114">You can accomplish it like this:</span></span>

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

<span data-ttu-id="8d354-115">Вот и все!</span><span class="sxs-lookup"><span data-stu-id="8d354-115">And that’s it!</span></span> <span data-ttu-id="8d354-116">Помимо использования `async`, `let!`, и `return`, это просто обычный код F #.</span><span class="sxs-lookup"><span data-stu-id="8d354-116">Aside from the use of `async`, `let!`, and `return`, this is just normal F# code.</span></span>

<span data-ttu-id="8d354-117">Существует несколько синтаксических конструкций, которые стоит обратить внимание:</span><span class="sxs-lookup"><span data-stu-id="8d354-117">There are a few syntactical constructs which are worth noting:</span></span>

*   <span data-ttu-id="8d354-118">`let!` Привязывает результат выражения async (выполняемый для другого контекста).</span><span class="sxs-lookup"><span data-stu-id="8d354-118">`let!` binds the result of an async expression (which runs on another context).</span></span>
*   <span data-ttu-id="8d354-119">`use!` работает аналогично `let!`, но удаляет его связанных ресурсов, когда он покидает область действия.</span><span class="sxs-lookup"><span data-stu-id="8d354-119">`use!` works just like `let!`, but disposes its bound resources when it goes out of scope.</span></span>
*   <span data-ttu-id="8d354-120">`do!` будет ожидать асинхронный рабочий процесс, который не возвращает ничего.</span><span class="sxs-lookup"><span data-stu-id="8d354-120">`do!` will await an async workflow which doesn’t return anything.</span></span>
*   <span data-ttu-id="8d354-121">`return` просто возвращает результат вычисления выражения async.</span><span class="sxs-lookup"><span data-stu-id="8d354-121">`return` simply returns a result from an async expression.</span></span>
*   <span data-ttu-id="8d354-122">`return!` выполняет другой асинхронный рабочий процесс и возвращает его возвращаемое значение в результате.</span><span class="sxs-lookup"><span data-stu-id="8d354-122">`return!` executes another async workflow and returns its return value as a result.</span></span>

<span data-ttu-id="8d354-123">Кроме того обычные `let`, `use`, и `do` ключевые слова могут использоваться вместе с асинхронные версии так же, как в обычной функции.</span><span class="sxs-lookup"><span data-stu-id="8d354-123">Additionally, normal `let`, `use`, and `do` keywords can be used alongside the async versions just as they would in a normal function.</span></span>

## <a name="how-to-start-async-code-in-f"></a><span data-ttu-id="8d354-124">Запуск асинхронного кода в F #</span><span class="sxs-lookup"><span data-stu-id="8d354-124">How to start Async Code in F#</span></span> #

<span data-ttu-id="8d354-125">Как упоминалось ранее, асинхронного кода представляет собой спецификацию для работы в другом контексте, который должен быть явным образом запущено.</span><span class="sxs-lookup"><span data-stu-id="8d354-125">As mentioned earlier, async code is a specification of work to be done in another context which needs to be explicitly started.</span></span> <span data-ttu-id="8d354-126">Ниже приведены два основных способа для решения этой задачи:</span><span class="sxs-lookup"><span data-stu-id="8d354-126">Here are two primary ways to accomplish this:</span></span>

1.  <span data-ttu-id="8d354-127">`Async.RunSynchronously` запускается это асинхронный рабочий процесс в другом потоке и ожидает его результат.</span><span class="sxs-lookup"><span data-stu-id="8d354-127">`Async.RunSynchronously` will start an async workflow on another thread and await its result.</span></span>

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

2.  <span data-ttu-id="8d354-128">`Async.Start` запустить рабочий процесс async в другом потоке и будет **не** ожидает его результат.</span><span class="sxs-lookup"><span data-stu-id="8d354-128">`Async.Start` will start an async workflow on another thread, and will **not** await its result.</span></span>

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

<span data-ttu-id="8d354-129">Существуют другие способы запуска асинхронного рабочего процесса, доступного для более конкретных сценариев.</span><span class="sxs-lookup"><span data-stu-id="8d354-129">There are other ways to start an async workflow available for more specific scenarios.</span></span> <span data-ttu-id="8d354-130">Дополнительные сведения [в справочнике по Async](https://msdn.microsoft.com/library/ee370232.aspx).</span><span class="sxs-lookup"><span data-stu-id="8d354-130">They are detailed [in the Async reference](https://msdn.microsoft.com/library/ee370232.aspx).</span></span>

### <a name="a-note-on-threads"></a><span data-ttu-id="8d354-131">Примечание в потоках</span><span class="sxs-lookup"><span data-stu-id="8d354-131">A Note on Threads</span></span>

<span data-ttu-id="8d354-132">Выше фразу «в другом потоке», но важно знать, что **это не означает, что асинхронные рабочие процессы являются оболочкой для многопоточности**.</span><span class="sxs-lookup"><span data-stu-id="8d354-132">The phrase "on another thread" is mentioned above, but it is important to know that **this does not mean that async workflows are a facade for multithreading**.</span></span> <span data-ttu-id="8d354-133">Рабочий процесс фактически» происходит переключение» между потоками, займов их для небольшой объем времени для выполнения требуемых задач.</span><span class="sxs-lookup"><span data-stu-id="8d354-133">The workflow actually "jumps" between threads, borrowing them for a small amount of time to do useful work.</span></span> <span data-ttu-id="8d354-134">Когда это асинхронный рабочий процесс фактически «ожидание» (например, для сетевой вызов, чтобы он возвращал нечто ожидания), любой поток, который он займов во время освобождается до нормальной работе перейдите на что-нибудь другое.</span><span class="sxs-lookup"><span data-stu-id="8d354-134">When an async workflow is effectively "waiting" (for example, waiting for a network call to return something), any thread it was borrowing at the time is freed up to go do useful work on something else.</span></span> <span data-ttu-id="8d354-135">Это позволяет асинхронные рабочие процессы для использования системы, они так же эффективно, как можно запускать и делает их особенно строгую для сценариев большого объема операций ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="8d354-135">This allows async workflows to utilize the system they run on as effectively as possible, and makes them especially strong for high-volume I/O scenarios.</span></span>

## <a name="how-to-add-parallelism-to-async-code"></a><span data-ttu-id="8d354-136">Добавление параллелизма асинхронного кода</span><span class="sxs-lookup"><span data-stu-id="8d354-136">How to Add Parallelism to Async Code</span></span>

<span data-ttu-id="8d354-137">Иногда можно требуется для выполнения нескольких асинхронных заданий в параллельном режиме, собирать их результаты и интерпретировать их иным образом.</span><span class="sxs-lookup"><span data-stu-id="8d354-137">Sometimes you may need to perform multiple asynchronous jobs in parallel, collect their results, and interpret them in some way.</span></span> <span data-ttu-id="8d354-138">`Async.Parallel` позволяет сделать это без необходимости использования библиотеки параллельных задач, которой будет применяться для присвоения `Task<'T>` и `Async<'T>` типов.</span><span class="sxs-lookup"><span data-stu-id="8d354-138">`Async.Parallel` allows you to do this without needing to use the Task Parallel Library, which would involve needing to coerce `Task<'T>` and `Async<'T>` types.</span></span>

<span data-ttu-id="8d354-139">Следующий пример будет использовать `Async.Parallel` для загрузки HTML из четырех популярных сайтов в параллельном режиме, дождитесь завершения выполнения этих задач, а затем напечатать HTML, который был загружен.</span><span class="sxs-lookup"><span data-stu-id="8d354-139">The following example will use `Async.Parallel` to download the HTML from four popular sites in parallel, wait for those tasks to complete, and then print the HTML which was downloaded.</span></span>

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

## <a name="important-info-and-advice"></a><span data-ttu-id="8d354-140">Важные сведения и советы</span><span class="sxs-lookup"><span data-stu-id="8d354-140">Important Info and Advice</span></span>

*   <span data-ttu-id="8d354-141">Добавьте «Async» в конец любой функции, которые вы будете использовать</span><span class="sxs-lookup"><span data-stu-id="8d354-141">Append "Async" to the end of any functions you’ll consume</span></span>

 <span data-ttu-id="8d354-142">Несмотря на то, что это просто соглашение об именовании, он облегчить как возможность обнаружения API.</span><span class="sxs-lookup"><span data-stu-id="8d354-142">Although this is just a naming convention, it does make things like API discoverability easier.</span></span> <span data-ttu-id="8d354-143">Особенно в том случае, если существует синхронные и асинхронные версии ту же подпрограмму, рекомендуется явно указать, который является асинхронным, через имя.</span><span class="sxs-lookup"><span data-stu-id="8d354-143">Particularly if there are synchronous and asynchronous versions of the same routine, it’s a good idea to explicitly state which is asynchronous via the name.</span></span>

*   <span data-ttu-id="8d354-144">Прослушивание компилятор!</span><span class="sxs-lookup"><span data-stu-id="8d354-144">Listen to the compiler!</span></span>

 <span data-ttu-id="8d354-145">Очень строгие компилятор F #, сделав его практически невозможно сделать что-нибудь troubling как код «async» синхронное выполнение.</span><span class="sxs-lookup"><span data-stu-id="8d354-145">F#’s compiler is very strict, making it nearly impossible to do something troubling like run "async" code synchronously.</span></span> <span data-ttu-id="8d354-146">Если попадаться предупреждение, это знак, что код не будет выполняться, как вы считаете, что будет происходить.</span><span class="sxs-lookup"><span data-stu-id="8d354-146">If you come across a warning, that’s a sign that the code won’t execute how you think it will.</span></span> <span data-ttu-id="8d354-147">Если компилятор может сделать довольными, код будет выполнен скорее должным образом.</span><span class="sxs-lookup"><span data-stu-id="8d354-147">If you can make the compiler happy, your code will most likely execute as expected.</span></span>

## <a name="for-the-cvb-programmer-looking-into-f"></a><span data-ttu-id="8d354-148">Для программистов C# и Visual Basic, разобраться в F #</span><span class="sxs-lookup"><span data-stu-id="8d354-148">For the C#/VB Programmer Looking Into F#</span></span> #

<span data-ttu-id="8d354-149">В этом разделе предполагается, вы уже знакомы с моделью асинхронного в C# или Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8d354-149">This section assumes you’re familiar with the async model in C#/VB.</span></span> <span data-ttu-id="8d354-150">Если вы не, [асинхронного программирования в C#](../../../csharp/async.md) является отправной точкой.</span><span class="sxs-lookup"><span data-stu-id="8d354-150">If you are not, [Async Programming in C#](../../../csharp/async.md) is a starting point.</span></span>

<span data-ttu-id="8d354-151">Нет принципиальное отличие модель языка C# и Visual Basic async модели асинхронного F #.</span><span class="sxs-lookup"><span data-stu-id="8d354-151">There is a fundamental difference between the C#/VB async model and the F# async model.</span></span>

<span data-ttu-id="8d354-152">При вызове функции, которая возвращает `Task` или `Task<'T>`, уже началось выполнение этого задания.</span><span class="sxs-lookup"><span data-stu-id="8d354-152">When you call a function which returns a `Task` or `Task<'T>`, that job has already begun execution.</span></span> <span data-ttu-id="8d354-153">Дескриптор, возвращенный представляет асинхронную задание уже выполняется.</span><span class="sxs-lookup"><span data-stu-id="8d354-153">The handle returned represents an already-running asynchronous job.</span></span> <span data-ttu-id="8d354-154">Напротив, при вызове функцию с модификатором async в языке F # `Async<'a>` возвращается представляет задание, которое будет иметь **создан** в определенный момент.</span><span class="sxs-lookup"><span data-stu-id="8d354-154">In contrast, when you call an async function in F#, the `Async<'a>` returned represents a job which will be **generated** at some point.</span></span> <span data-ttu-id="8d354-155">Основные сведения об этой модели обладает широкими возможностями, так как она допускает асинхронных заданий в языке F # для связывать друг с другом, выполнять условно и работы с большей степенью гранулярности элемента управления.</span><span class="sxs-lookup"><span data-stu-id="8d354-155">Understanding this model is powerful, because it allows for asynchronous jobs in F# to be chained together easier, performed conditionally, and be started with a finer grain of control.</span></span>

<span data-ttu-id="8d354-156">Существует несколько других сходства и различия отметить.</span><span class="sxs-lookup"><span data-stu-id="8d354-156">There are a few other similarities and differences worth noting.</span></span>

### <a name="similarities"></a><span data-ttu-id="8d354-157">Сходства</span><span class="sxs-lookup"><span data-stu-id="8d354-157">Similarities</span></span>

*   <span data-ttu-id="8d354-158">`let!`, `use!`, и `do!` аналогичны `await` при вызове асинхронного задания изнутри `async{ }` блока.</span><span class="sxs-lookup"><span data-stu-id="8d354-158">`let!`, `use!`, and `do!` are analogous to `await` when calling an async job from within an `async{ }` block.</span></span>

 <span data-ttu-id="8d354-159">Три ключевых слова можно использовать только в пределах `async { }` блока, подобно тому, как `await` может быть вызван только внутри `async` метод.</span><span class="sxs-lookup"><span data-stu-id="8d354-159">The three keywords can only be used within an `async { }` block, similar to how `await` can only be invoked inside an `async` method.</span></span> <span data-ttu-id="8d354-160">Иными словами `let!` Если необходимо для сбора и использования результата, то для `use!` является прежним, но для других операций, ресурсы которого следует получить удаляются после его использования, и `do!` удобно для, если нужно подождать, пока это асинхронный рабочий процесс без возвращаемого значения для завершения Прежде чем продолжить.</span><span class="sxs-lookup"><span data-stu-id="8d354-160">In short, `let!` is for when you want to capture and use a result, `use!` is the same but for something whose resources should get cleaned after it’s used, and `do!` is for when you want to wait for an async workflow with no return value to finish before moving on.</span></span>

*   <span data-ttu-id="8d354-161">F # поддерживает параллелизм данных аналогичным образом.</span><span class="sxs-lookup"><span data-stu-id="8d354-161">F# supports data-parallelism in a similar way.</span></span>

 <span data-ttu-id="8d354-162">Несмотря на то, что он работает очень по-разному, `Async.Parallel` соответствует `Task.WhenAll` сценарий Желательное результатов набора асинхронных заданий, если все они завершаются.</span><span class="sxs-lookup"><span data-stu-id="8d354-162">Although it operates very differently, `Async.Parallel` corresponds to `Task.WhenAll` for the scenario of wanting the results of a set of async jobs when they all complete.</span></span>

### <a name="differences"></a><span data-ttu-id="8d354-163">Различия</span><span class="sxs-lookup"><span data-stu-id="8d354-163">Differences</span></span>

*   <span data-ttu-id="8d354-164">Вложенные `let!` не разрешено, в отличие от вложенных `await`</span><span class="sxs-lookup"><span data-stu-id="8d354-164">Nested `let!` is not allowed, unlike nested `await`</span></span>

 <span data-ttu-id="8d354-165">В отличие от `await`, которой могут быть вложенными неопределенно долгое время, `let!` невозможно, необходимо его результат привязаны перед его использованием внутри другой `let!`, `do!`, или `use!`.</span><span class="sxs-lookup"><span data-stu-id="8d354-165">Unlike `await`, which can be nested indefinitely, `let!` cannot and must have its result bound before using it inside of another `let!`, `do!`, or `use!`.</span></span>

*   <span data-ttu-id="8d354-166">Поддержка отмены проще в языке F # чем в C# или Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8d354-166">Cancellation support is simpler in F# than in C#/VB.</span></span>

 <span data-ttu-id="8d354-167">Поддержка отмены середине выполнения задачи в C# и Visual Basic требуется выполнить проверку `IsCancellationRequested` свойства или метода `ThrowIfCancellationRequested()` на `CancellationToken` объект, который передается в асинхронный метод.</span><span class="sxs-lookup"><span data-stu-id="8d354-167">Supporting cancellation of a task midway through its execution in C#/VB requires checking the `IsCancellationRequested` property or calling `ThrowIfCancellationRequested()` on a `CancellationToken` object that’s passed into the async method.</span></span>

<span data-ttu-id="8d354-168">Напротив F # асинхронные рабочие процессы — это более естественным образом поддерживать отмену.</span><span class="sxs-lookup"><span data-stu-id="8d354-168">In contrast, F# async workflows are more naturally cancellable.</span></span> <span data-ttu-id="8d354-169">Отмена выполняется простой трехшаговый процесс.</span><span class="sxs-lookup"><span data-stu-id="8d354-169">Cancellation is a simple three-step process.</span></span>

1.  <span data-ttu-id="8d354-170">Создайте объект `CancellationTokenSource`.</span><span class="sxs-lookup"><span data-stu-id="8d354-170">Create a new `CancellationTokenSource`.</span></span>
2.  <span data-ttu-id="8d354-171">Передайте его в начала функции.</span><span class="sxs-lookup"><span data-stu-id="8d354-171">Pass it into a starting function.</span></span>
3.  <span data-ttu-id="8d354-172">Вызов `Cancel` на маркер.</span><span class="sxs-lookup"><span data-stu-id="8d354-172">Call `Cancel` on the token.</span></span>

<span data-ttu-id="8d354-173">Пример</span><span class="sxs-lookup"><span data-stu-id="8d354-173">Example:</span></span>

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

let token = new CancellationTokenSource()
Async.Start (workflow, token)

// Immediately cancel uploadDataAsync after it's been started.
token.Cancel()
```

<span data-ttu-id="8d354-174">Вот и все!</span><span class="sxs-lookup"><span data-stu-id="8d354-174">And that’s it!</span></span>

## <a name="further-resources"></a><span data-ttu-id="8d354-175">Дополнительные ресурсы:</span><span class="sxs-lookup"><span data-stu-id="8d354-175">Further resources:</span></span>

*   [<span data-ttu-id="8d354-176">Асинхронные рабочие процессы в MSDN</span><span class="sxs-lookup"><span data-stu-id="8d354-176">Async Workflows on MSDN</span></span>](https://msdn.microsoft.com/library/dd233250.aspx)
*   [<span data-ttu-id="8d354-177">Асинхронные последовательностей для F #</span><span class="sxs-lookup"><span data-stu-id="8d354-177">Asynchronous Sequences for F#</span></span>](https://fsprojects.github.io/FSharp.Control.AsyncSeq/library/AsyncSeq.html)
*   [<span data-ttu-id="8d354-178">Служебные программы F # данных HTTP</span><span class="sxs-lookup"><span data-stu-id="8d354-178">F# Data HTTP Utilities</span></span>](https://fsharp.github.io/FSharp.Data/library/Http.html)
