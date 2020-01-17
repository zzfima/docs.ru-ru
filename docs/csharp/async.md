---
title: Асинхронное программирование на C#
description: Сведения о модели асинхронного программирования на уровне языка C#, которая реализуется в .NET Core.
author: cartermp
ms.date: 06/20/2016
ms.technology: csharp-async
ms.assetid: b878c34c-a78f-419e-a594-a2b44fa521a4
ms.openlocfilehash: 38d7c856e9a536db9ef26349175ad440a49f5fe2
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713953"
---
# <a name="asynchronous-programming"></a><span data-ttu-id="5067f-103">Асинхронное программирование</span><span class="sxs-lookup"><span data-stu-id="5067f-103">Asynchronous programming</span></span>

<span data-ttu-id="5067f-104">Для решения задач, связанных с вводом-выводом (например, для запроса данных из сети или доступа к базе данных), желательно использовать асинхронное программирование.</span><span class="sxs-lookup"><span data-stu-id="5067f-104">If you have any I/O-bound needs (such as requesting data from a network or accessing a database), you'll want to utilize asynchronous programming.</span></span>  <span data-ttu-id="5067f-105">Если у вас есть код, ограниченный ресурсами процессора, например выполняющий сложные вычисления, то это также подходящий сценарий для асинхронного программирования.</span><span class="sxs-lookup"><span data-stu-id="5067f-105">You could also have CPU-bound code, such as performing an expensive calculation, which is also a good scenario for writing async code.</span></span>

<span data-ttu-id="5067f-106">В C# имеется модель асинхронного программирования, реализованная на уровне языка, которая позволяет легко писать асинхронный код, не прибегая к обратным вызовам или библиотекам, которые поддерживают асинхронность.</span><span class="sxs-lookup"><span data-stu-id="5067f-106">C# has a language-level asynchronous programming model which allows for easily writing asynchronous code without having to juggle callbacks or conform to a library which supports asynchrony.</span></span> <span data-ttu-id="5067f-107">Она строится на принципах [асинхронной модели на основе задач (TAP)](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span><span class="sxs-lookup"><span data-stu-id="5067f-107">It follows what is known as the [Task-based Asynchronous Pattern (TAP)](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span></span>

## <a name="basic-overview-of-the-asynchronous-model"></a><span data-ttu-id="5067f-108">Общий обзор асинхронной модели</span><span class="sxs-lookup"><span data-stu-id="5067f-108">Basic Overview of the Asynchronous Model</span></span>

<span data-ttu-id="5067f-109">В основе асинхронного программирования лежат объекты `Task` и `Task<T>`, которые моделируют асинхронные операции.</span><span class="sxs-lookup"><span data-stu-id="5067f-109">The core of async programming is the `Task` and `Task<T>` objects, which model asynchronous operations.</span></span>  <span data-ttu-id="5067f-110">Они поддерживаются ключевыми словами `async` и `await`.</span><span class="sxs-lookup"><span data-stu-id="5067f-110">They are supported by the `async` and `await` keywords.</span></span>  <span data-ttu-id="5067f-111">В большинстве случаев модель достаточно проста.</span><span class="sxs-lookup"><span data-stu-id="5067f-111">The model is fairly simple in most cases:</span></span>

<span data-ttu-id="5067f-112">Для кода, ограниченного производительностью ввода-вывода, с помощью `await` выполняется операция, которая возвращает объект `Task` или `Task<T>` внутри метода `async`.</span><span class="sxs-lookup"><span data-stu-id="5067f-112">For I/O-bound code, you `await` an operation which returns a `Task` or `Task<T>` inside of an `async` method.</span></span>

<span data-ttu-id="5067f-113">Для кода, ограниченного ресурсами процессора, с помощью `await` выполняется операция, которая запускается в фоновом потоке методом `Task.Run`.</span><span class="sxs-lookup"><span data-stu-id="5067f-113">For CPU-bound code, you `await` an operation which is started on a background thread with the `Task.Run` method.</span></span>

<span data-ttu-id="5067f-114">Именно с помощью ключевого слова `await` творится вся магия.</span><span class="sxs-lookup"><span data-stu-id="5067f-114">The `await` keyword is where the magic happens.</span></span> <span data-ttu-id="5067f-115">Оно передает управление вызывающему объекту метода, который выполнил `await`, позволяя, таким образом, пользовательскому интерфейсу или службе отвечать на запросы.</span><span class="sxs-lookup"><span data-stu-id="5067f-115">It yields control to the caller of the method that performed `await`, and it ultimately allows a UI to be responsive or a service to be elastic.</span></span>

<span data-ttu-id="5067f-116">Есть и другие подходы к написанию асинхронного кода без использования ключевых слов `async` и `await`. Их описание можно найти в приведенной выше статье, посвященной TAP. Однако далее в этом документе будут рассматриваться конструкции на уровне языка.</span><span class="sxs-lookup"><span data-stu-id="5067f-116">There are other ways to approach async code than `async` and `await` outlined in the TAP article linked above, but this document will focus on the language-level constructs from this point forward.</span></span>

### <a name="io-bound-example-downloading-data-from-a-web-service"></a><span data-ttu-id="5067f-117">Пример с ограниченной производительностью ввода-вывода: скачивание данных из веб-службы</span><span class="sxs-lookup"><span data-stu-id="5067f-117">I/O-Bound Example: Downloading data from a web service</span></span>

<span data-ttu-id="5067f-118">При нажатии кнопки может требоваться скачать некоторые данные из веб-службы, не блокируя поток пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="5067f-118">You may need to download some data from a web service when a button is pressed, but don’t want to block the UI thread.</span></span> <span data-ttu-id="5067f-119">Это можно сделать очень просто:</span><span class="sxs-lookup"><span data-stu-id="5067f-119">It can be accomplished simply like this:</span></span>

```csharp
private readonly HttpClient _httpClient = new HttpClient();

downloadButton.Clicked += async (o, e) =>
{
    // This line will yield control to the UI as the request
    // from the web service is happening.
    //
    // The UI thread is now free to perform other work.
    var stringData = await _httpClient.GetStringAsync(URL);
    DoSomethingWithData(stringData);
};
```

<span data-ttu-id="5067f-120">Вот и все!</span><span class="sxs-lookup"><span data-stu-id="5067f-120">And that’s it!</span></span> <span data-ttu-id="5067f-121">В коде выражается намерение (скачивание некоторых данных в асинхронном режиме), и при этом не приходится выполнять запутанные операции с объектами Task.</span><span class="sxs-lookup"><span data-stu-id="5067f-121">The code expresses the intent (downloading some data asynchronously) without getting bogged down in interacting with Task objects.</span></span>

### <a name="cpu-bound-example-performing-a-calculation-for-a-game"></a><span data-ttu-id="5067f-122">Пример с ограниченными ресурсами процессора: выполнение вычислений для игры</span><span class="sxs-lookup"><span data-stu-id="5067f-122">CPU-bound Example: Performing a Calculation for a Game</span></span>

<span data-ttu-id="5067f-123">Предположим, вы разрабатываете игру для мобильных устройств, в которой при нажатии кнопки может наноситься урон множеству противников на экране.</span><span class="sxs-lookup"><span data-stu-id="5067f-123">Say you're writing a mobile game where pressing a button can inflict damage on many enemies on the screen.</span></span>  <span data-ttu-id="5067f-124">Расчет урона может потреблять много ресурсов. Если производить его в потоке пользовательского интерфейса, то на это время игра может приостанавливаться!</span><span class="sxs-lookup"><span data-stu-id="5067f-124">Performing the damage calculation can be expensive, and doing it on the UI thread would make the game appear to pause as the calculation is performed!</span></span>

<span data-ttu-id="5067f-125">Оптимальный способ — запустить фоновый поток, который выполняет задачу с помощью `Task.Run`, а затем ожидает результат с помощью `await`.</span><span class="sxs-lookup"><span data-stu-id="5067f-125">The best way to handle this is to start a background thread which does the work using `Task.Run`, and `await` its result.</span></span>  <span data-ttu-id="5067f-126">Таким образом обеспечится плавная работа пользовательского интерфейса в процессе вычисления.</span><span class="sxs-lookup"><span data-stu-id="5067f-126">This will allow the UI to feel smooth as the work is being done.</span></span>

```csharp
private DamageResult CalculateDamageDone()
{
    // Code omitted:
    //
    // Does an expensive calculation and returns
    // the result of that calculation.
}

calculateButton.Clicked += async (o, e) =>
{
    // This line will yield control to the UI while CalculateDamageDone()
    // performs its work.  The UI thread is free to perform other work.
    var damageResult = await Task.Run(() => CalculateDamageDone());
    DisplayDamage(damageResult);
};
```

<span data-ttu-id="5067f-127">Вот и все!</span><span class="sxs-lookup"><span data-stu-id="5067f-127">And that's it!</span></span>  <span data-ttu-id="5067f-128">В этом коде четко выражается назначение события нажатия кнопки, фоновым потоком не требуется управлять вручную, и он выполняется без блокировки.</span><span class="sxs-lookup"><span data-stu-id="5067f-128">This code cleanly expresses the intent of the button's click event, it doesn't require managing a background thread manually, and it does so in a non-blocking way.</span></span>

### <a name="what-happens-under-the-covers"></a><span data-ttu-id="5067f-129">Что происходит на внутреннем уровне</span><span class="sxs-lookup"><span data-stu-id="5067f-129">What happens under the covers</span></span>

<span data-ttu-id="5067f-130">Выполнение асинхронных операций связано со множеством элементов.</span><span class="sxs-lookup"><span data-stu-id="5067f-130">There's a lot of moving pieces where asynchronous operations are concerned.</span></span>  <span data-ttu-id="5067f-131">Если вы хотите знать внутренние принципы работы объектов `Task` и `Task<T>`, обратитесь за дополнительными сведениями к статье [Подробный обзор асинхронного программирования](../standard/async-in-depth.md).</span><span class="sxs-lookup"><span data-stu-id="5067f-131">If you're curious about what's happening underneath the covers of `Task` and `Task<T>`, checkout the [Async in-depth](../standard/async-in-depth.md) article for more information.</span></span>

<span data-ttu-id="5067f-132">С точки зрения C#, компилятор преобразовывает код в конечный автомат, который контролирует такие моменты, как передача выполнения при достижении `await` и возобновление выполнения после завершения фонового задания.</span><span class="sxs-lookup"><span data-stu-id="5067f-132">On the C# side of things, the compiler transforms your code into a state machine which keeps track of things like yielding execution when an `await` is reached and resuming execution when a background job has finished.</span></span>

<span data-ttu-id="5067f-133">Если вас интересует теория, это реализация [модели асинхронности на основе обещаний](https://en.wikipedia.org/wiki/Futures_and_promises).</span><span class="sxs-lookup"><span data-stu-id="5067f-133">For the theoretically-inclined, this is an implementation of the [Promise Model of asynchrony](https://en.wikipedia.org/wiki/Futures_and_promises).</span></span>

## <a name="key-pieces-to-understand"></a><span data-ttu-id="5067f-134">Ключевые моменты для понимания</span><span class="sxs-lookup"><span data-stu-id="5067f-134">Key Pieces to Understand</span></span>

* <span data-ttu-id="5067f-135">Асинхронный код можно использовать как при ограниченной производительности ввода-вывода, так и при ограниченных ресурсах процессора, но по-разному в каждом случае.</span><span class="sxs-lookup"><span data-stu-id="5067f-135">Async code can be used for both I/O-bound and CPU-bound code, but differently for each scenario.</span></span>
* <span data-ttu-id="5067f-136">В асинхронном коде используются конструкции `Task<T>` и `Task`, которые служат для моделирования задач, выполняемых в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="5067f-136">Async code uses `Task<T>` and `Task`, which are constructs used to model work being done in the background.</span></span>
* <span data-ttu-id="5067f-137">Ключевое слово `async` делает метод асинхронным, что позволяет использовать в его теле ключевое слово `await`.</span><span class="sxs-lookup"><span data-stu-id="5067f-137">The `async` keyword turns a method into an async method, which allows you to use the `await` keyword in its body.</span></span>
* <span data-ttu-id="5067f-138">Когда применяется ключевое слово `await`, оно приостанавливает выполнение вызывающего метода и передает управление обратно вызывающему объекту, пока не будет завершена ожидаемая задача.</span><span class="sxs-lookup"><span data-stu-id="5067f-138">When the `await` keyword is applied, it suspends the calling method and yields control back to its caller until the awaited task is complete.</span></span>
* <span data-ttu-id="5067f-139">`await` можно использовать только внутри асинхронного метода.</span><span class="sxs-lookup"><span data-stu-id="5067f-139">`await` can only be used inside an async method.</span></span>

## <a name="recognize-cpu-bound-and-io-bound-work"></a><span data-ttu-id="5067f-140">Определение задач, ограниченных ресурсами процессора и производительностью ввода-вывода</span><span class="sxs-lookup"><span data-stu-id="5067f-140">Recognize CPU-Bound and I/O-Bound Work</span></span>

<span data-ttu-id="5067f-141">В первых двух примерах этого руководства было показано, как можно использовать `async` и `await` для выполнения задач, ограниченных производительностью ввода-вывода и ресурсами процессора.</span><span class="sxs-lookup"><span data-stu-id="5067f-141">The first two examples of this guide showed how you can use `async` and `await` for I/O-bound and CPU-bound work.</span></span>  <span data-ttu-id="5067f-142">Крайне важно уметь идентифицировать такие задачи, так как они могут существенно повлиять на производительность кода и привести к неправильному использованию некоторых конструкций.</span><span class="sxs-lookup"><span data-stu-id="5067f-142">It's key that you can identify when a job you need to do is I/O-bound or CPU-bound, because it can greatly affect the performance of your code and could potentially lead to misusing certain constructs.</span></span>

<span data-ttu-id="5067f-143">Перед написанием любого кода нужно ответить на два вопроса.</span><span class="sxs-lookup"><span data-stu-id="5067f-143">Here are two questions you should ask before you write any code:</span></span>

1. <span data-ttu-id="5067f-144">Будет ли код "ожидать" чего-либо, например данных из базы данных?</span><span class="sxs-lookup"><span data-stu-id="5067f-144">Will your code be "waiting" for something, such as data from a database?</span></span>

    <span data-ttu-id="5067f-145">Если ответ утвердительный, то ваша задача **ограничена производительностью ввода-вывода**.</span><span class="sxs-lookup"><span data-stu-id="5067f-145">If your answer is "yes", then your work is **I/O-bound**.</span></span>

2. <span data-ttu-id="5067f-146">Будет ли код выполнять очень сложные вычисления?</span><span class="sxs-lookup"><span data-stu-id="5067f-146">Will your code be performing a very expensive computation?</span></span>

    <span data-ttu-id="5067f-147">Если ответ утвердительный, то задача **ограничена ресурсами процессора**.</span><span class="sxs-lookup"><span data-stu-id="5067f-147">If you answered "yes", then your work is **CPU-bound**.</span></span>

<span data-ttu-id="5067f-148">Если ваша задача **ограничена производительностью ввода-вывода**, используйте `async` и `await` *без* `Task.Run`.</span><span class="sxs-lookup"><span data-stu-id="5067f-148">If the work you have is **I/O-bound**, use `async` and `await` *without* `Task.Run`.</span></span>  <span data-ttu-id="5067f-149">Библиотеку параллельных задач использовать *не следует*.</span><span class="sxs-lookup"><span data-stu-id="5067f-149">You *should not* use the Task Parallel Library.</span></span>  <span data-ttu-id="5067f-150">Причина этого указана в статье [Подробный обзор асинхронного программирования](../standard/async-in-depth.md).</span><span class="sxs-lookup"><span data-stu-id="5067f-150">The reason for this is outlined in the [Async in Depth article](../standard/async-in-depth.md).</span></span>

<span data-ttu-id="5067f-151">Если ваша задача **ограничена ресурсами процессора** и вам важна скорость реагирования, используйте `async` и `await`, но перенесите выполнение задачи в другой поток *с* `Task.Run`.</span><span class="sxs-lookup"><span data-stu-id="5067f-151">If the work you have is **CPU-bound** and you care about responsiveness, use `async` and `await` but spawn the work off on another thread *with* `Task.Run`.</span></span>  <span data-ttu-id="5067f-152">Если к задаче применим параллелизм, также следует рассмотреть возможность использования [библиотеки параллельных задач](../standard/parallel-programming/task-parallel-library-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="5067f-152">If the work is appropriate for concurrency and parallelism, you should also consider using the [Task Parallel Library](../standard/parallel-programming/task-parallel-library-tpl.md).</span></span>

<span data-ttu-id="5067f-153">Кроме того, всегда следует оценивать выполнение кода.</span><span class="sxs-lookup"><span data-stu-id="5067f-153">Additionally, you should always measure the execution of your code.</span></span>  <span data-ttu-id="5067f-154">Например, затраты на выполнение задачи, ограниченной ресурсами процессора, могут оказаться не столь высокими, как накладные расходы, связанные с переключениями контекста при многопоточности.</span><span class="sxs-lookup"><span data-stu-id="5067f-154">For example, you may find yourself in a situation where your CPU-bound work is not costly enough compared with the overhead of context switches when multithreading.</span></span>  <span data-ttu-id="5067f-155">Каждый вариант имеет свои недостатки, поэтому следует выбрать наиболее компромиссный вариант в вашей ситуации.</span><span class="sxs-lookup"><span data-stu-id="5067f-155">Every choice has its tradeoff, and you should pick the correct tradeoff for your situation.</span></span>

## <a name="more-examples"></a><span data-ttu-id="5067f-156">Дополнительные примеры</span><span class="sxs-lookup"><span data-stu-id="5067f-156">More Examples</span></span>

<span data-ttu-id="5067f-157">В приведенных ниже примерах демонстрируются различные способы написания асинхронного кода на C#.</span><span class="sxs-lookup"><span data-stu-id="5067f-157">The following examples demonstrate various ways you can write async code in C#.</span></span>  <span data-ttu-id="5067f-158">Они охватывают несколько сценариев, с которыми вы можете столкнуться.</span><span class="sxs-lookup"><span data-stu-id="5067f-158">They cover a few different scenarios you may come across.</span></span>

### <a name="extracting-data-from-a-network"></a><span data-ttu-id="5067f-159">Извлечение данных из сети</span><span class="sxs-lookup"><span data-stu-id="5067f-159">Extracting Data from a Network</span></span>

<span data-ttu-id="5067f-160">Этот фрагмент кода скачивает код HTML с главной страницы [сайта www.dotnetfoundation.org](https://www.dotnetfoundation.org) и подсчитывает число вхождений в него строки ".NET".</span><span class="sxs-lookup"><span data-stu-id="5067f-160">This snippet downloads the HTML from the homepage at [www.dotnetfoundation.org](https://www.dotnetfoundation.org) and counts the number of times the string ".NET" occurs in the HTML.</span></span>  <span data-ttu-id="5067f-161">С помощью ASP.NET MVC определяется метод веб-контроллера, который выполняет эту задачу, и возвращается число.</span><span class="sxs-lookup"><span data-stu-id="5067f-161">It uses ASP.NET MVC to define a web controller method which performs this task, returning the number.</span></span>

> [!NOTE]
> <span data-ttu-id="5067f-162">Если вы планируете проанализировать HTML в рабочем коде, не используйте регулярные выражения.</span><span class="sxs-lookup"><span data-stu-id="5067f-162">If you plan on doing HTML parsing in production code, don't use regular expressions.</span></span> <span data-ttu-id="5067f-163">Используйте библиотеку анализа.</span><span class="sxs-lookup"><span data-stu-id="5067f-163">Use a parsing library instead.</span></span>

```csharp
private readonly HttpClient _httpClient = new HttpClient();

[HttpGet]
[Route("DotNetCount")]
public async Task<int> GetDotNetCountAsync()
{
    // Suspends GetDotNetCountAsync() to allow the caller (the web server)
    // to accept another request, rather than blocking on this one.
    var html = await _httpClient.GetStringAsync("https://dotnetfoundation.org");

    return Regex.Matches(html, @"\.NET").Count;
}
```

<span data-ttu-id="5067f-164">Вот аналогичный код для универсального приложения для Windows, который выполняет ту же задачу при нажатии кнопки:</span><span class="sxs-lookup"><span data-stu-id="5067f-164">Here's the same scenario written for a Universal Windows App, which performs the same task when a Button is pressed:</span></span>

```csharp
private readonly HttpClient _httpClient = new HttpClient();

private async void SeeTheDotNets_Click(object sender, RoutedEventArgs e)
{
    // Capture the task handle here so we can await the background task later.
    var getDotNetFoundationHtmlTask = _httpClient.GetStringAsync("https://www.dotnetfoundation.org");

    // Any other work on the UI thread can be done here, such as enabling a Progress Bar.
    // This is important to do here, before the "await" call, so that the user
    // sees the progress bar before execution of this method is yielded.
    NetworkProgressBar.IsEnabled = true;
    NetworkProgressBar.Visibility = Visibility.Visible;

    // The await operator suspends SeeTheDotNets_Click, returning control to its caller.
    // This is what allows the app to be responsive and not block the UI thread.
    var html = await getDotNetFoundationHtmlTask;
    int count = Regex.Matches(html, @"\.NET").Count;

    DotNetCountLabel.Text = $"Number of .NETs on dotnetfoundation.org: {count}";

    NetworkProgressBar.IsEnabled = false;
    NetworkProgressBar.Visibility = Visibility.Collapsed;
}
```

### <a name="waiting-for-multiple-tasks-to-complete"></a><span data-ttu-id="5067f-165">Ожидание выполнения нескольких задач</span><span class="sxs-lookup"><span data-stu-id="5067f-165">Waiting for Multiple Tasks to Complete</span></span>

<span data-ttu-id="5067f-166">Может возникнуть ситуация, когда несколько фрагментов данных должны извлекаться одновременно.</span><span class="sxs-lookup"><span data-stu-id="5067f-166">You may find yourself in a situation where you need to retrieve multiple pieces of data concurrently.</span></span>  <span data-ttu-id="5067f-167">Интерфейс API `Task` содержит два метода, `Task.WhenAll` и `Task.WhenAny`, которые позволяют писать асинхронный код, выполняющий неблокирующее ожидание для нескольких фоновых заданий.</span><span class="sxs-lookup"><span data-stu-id="5067f-167">The `Task` API contains two methods, `Task.WhenAll` and `Task.WhenAny` which allow you to write asynchronous code which performs a non-blocking wait on multiple background jobs.</span></span>

<span data-ttu-id="5067f-168">В этом примере показано, как можно получить данные `User` для набора `userId`.</span><span class="sxs-lookup"><span data-stu-id="5067f-168">This example shows how you might grab `User` data for a set of `userId`s.</span></span>

```csharp
public async Task<User> GetUserAsync(int userId)
{
    // Code omitted:
    //
    // Given a user Id {userId}, retrieves a User object corresponding
    // to the entry in the database with {userId} as its Id.
}

public static async Task<IEnumerable<User>> GetUsersAsync(IEnumerable<int> userIds)
{
    var getUserTasks = new List<Task<User>>();

    foreach (int userId in userIds)
    {
        getUserTasks.Add(GetUserAsync(userId));
    }

    return await Task.WhenAll(getUserTasks);
}
```

<span data-ttu-id="5067f-169">Вот более лаконичный вариант этого кода, написанный с использованием LINQ:</span><span class="sxs-lookup"><span data-stu-id="5067f-169">Here's another way to write this a bit more succinctly, using LINQ:</span></span>

```csharp
public async Task<User> GetUserAsync(int userId)
{
    // Code omitted:
    //
    // Given a user Id {userId}, retrieves a User object corresponding
    // to the entry in the database with {userId} as its Id.
}

public static async Task<User[]> GetUsersAsync(IEnumerable<int> userIds)
{
    var getUserTasks = userIds.Select(id => GetUserAsync(id));
    return await Task.WhenAll(getUserTasks);
}
```

<span data-ttu-id="5067f-170">Хотя размер кода меньше, будьте осторожны при использовании LINQ в сочетании с асинхронным кодом.</span><span class="sxs-lookup"><span data-stu-id="5067f-170">Although it's less code, take care when mixing LINQ with asynchronous code.</span></span>  <span data-ttu-id="5067f-171">Так как в LINQ используется отложенное выполнение, асинхронные вызовы будут выполняться не немедленно, как в цикле `foreach()`, если только вы не производите принудительную итерацию созданной последовательности с помощью вызова `.ToList()` или `.ToArray()`.</span><span class="sxs-lookup"><span data-stu-id="5067f-171">Because LINQ uses deferred (lazy) execution, async calls won't happen immediately as they do in a `foreach()` loop unless you force the generated sequence to iterate with a call to `.ToList()` or `.ToArray()`.</span></span>

## <a name="important-info-and-advice"></a><span data-ttu-id="5067f-172">Важные сведения и советы</span><span class="sxs-lookup"><span data-stu-id="5067f-172">Important Info and Advice</span></span>

<span data-ttu-id="5067f-173">Хотя принципы асинхронного программирования сравнительно просты, необходимо учитывать ряд моментов, чтобы избежать непредвиденных результатов.</span><span class="sxs-lookup"><span data-stu-id="5067f-173">Although async programming is relatively straightforward, there are some details to keep in mind which can prevent unexpected behavior.</span></span>

* <span data-ttu-id="5067f-174">**В методах `async` должно присутствовать ключевое слово** `await` **. В противном случае результат не будет получен.**</span><span class="sxs-lookup"><span data-stu-id="5067f-174">`async` **methods need to have an** `await` **keyword in their body or they will never yield!**</span></span>

<span data-ttu-id="5067f-175">Это важно помнить.</span><span class="sxs-lookup"><span data-stu-id="5067f-175">This is important to keep in mind.</span></span>  <span data-ttu-id="5067f-176">Если ключевое слово `await` не используется в теле метода `async`, компилятор C# выдаст предупреждение, но код скомпилируется и будет выполняться, как обычный метод.</span><span class="sxs-lookup"><span data-stu-id="5067f-176">If `await` is not used in the body of an `async` method, the C# compiler will generate a warning, but the code will compile and run as if it were a normal method.</span></span>  <span data-ttu-id="5067f-177">Обратите также внимание на то, что это очень неэффективно, так как конечный автомат, созданный компилятором C# для асинхронного метода, не будет выполнять никакой работы.</span><span class="sxs-lookup"><span data-stu-id="5067f-177">Note that this would also be incredibly inefficient, as the state machine generated by the C# compiler for the async method would not be accomplishing anything.</span></span>

* <span data-ttu-id="5067f-178">**К имени каждого создаваемого асинхронного метода следует добавлять суффикс Async.**</span><span class="sxs-lookup"><span data-stu-id="5067f-178">**You should add "Async" as the suffix of every async method name you write.**</span></span>

<span data-ttu-id="5067f-179">Это соглашение применяется в .NET для различения синхронных и асинхронных методов.</span><span class="sxs-lookup"><span data-stu-id="5067f-179">This is the convention used in .NET to more-easily differentiate synchronous and asynchronous methods.</span></span> <span data-ttu-id="5067f-180">Обратите внимание, что это необязательно для некоторых методов, которые не вызываются в вашем коде явным образом (например, для обработчиков событий или методов веб-контроллеров).</span><span class="sxs-lookup"><span data-stu-id="5067f-180">Note that certain methods which aren’t explicitly called by your code (such as event handlers or web controller methods) don’t necessarily apply.</span></span> <span data-ttu-id="5067f-181">Так как они не вызываются в коде явно, требования к их именованию не так строги.</span><span class="sxs-lookup"><span data-stu-id="5067f-181">Because these are not explicitly called by your code, being explicit about their naming isn’t as important.</span></span>

* <span data-ttu-id="5067f-182">`async void` **следует использовать только для обработчиков событий.**</span><span class="sxs-lookup"><span data-stu-id="5067f-182">`async void` **should only be used for event handlers.**</span></span>

<span data-ttu-id="5067f-183">`async void` — это единственный способ обеспечить работу асинхронных обработчиков событий, так как у событий нет типов возвращаемых значений (поэтому они не могут использовать `Task` и `Task<T>`).</span><span class="sxs-lookup"><span data-stu-id="5067f-183">`async void` is the only way to allow asynchronous event handlers to work because events do not have return types (thus cannot make use of `Task` and `Task<T>`).</span></span> <span data-ttu-id="5067f-184">Любые иные способы применения `async void` не предусмотрены моделью TAP и могут создавать указанные ниже проблемы.</span><span class="sxs-lookup"><span data-stu-id="5067f-184">Any other use of `async void` does not follow the TAP model and can be challenging to use, such as:</span></span>

* <span data-ttu-id="5067f-185">Исключения, вызываемые в методе `async void`, невозможно перехватывать вне этого метода.</span><span class="sxs-lookup"><span data-stu-id="5067f-185">Exceptions thrown in an `async void` method can’t be caught outside of that method.</span></span>
* <span data-ttu-id="5067f-186">Методы `async void` очень трудно тестировать.</span><span class="sxs-lookup"><span data-stu-id="5067f-186">`async void` methods are very difficult to test.</span></span>
* <span data-ttu-id="5067f-187">Методы `async void` могут иметь негативные побочные эффекты, если вызывающий объект не предполагает, что они являются асинхронными.</span><span class="sxs-lookup"><span data-stu-id="5067f-187">`async void` methods can cause bad side effects if the caller isn’t expecting them to be async.</span></span>

* <span data-ttu-id="5067f-188">**Будьте осторожны при использовании асинхронных лямбда-выражений в выражениях LINQ**</span><span class="sxs-lookup"><span data-stu-id="5067f-188">**Tread carefully when using async lambdas in LINQ expressions**</span></span>

<span data-ttu-id="5067f-189">Для лямбда-выражений в LINQ применяется отложенное выполнение. Это означает, что код может прекратить выполнение в тот момент, когда вы этого не ожидаете.</span><span class="sxs-lookup"><span data-stu-id="5067f-189">Lambda expressions in LINQ use deferred execution, meaning code could end up executing at a time when you’re not expecting it to.</span></span> <span data-ttu-id="5067f-190">Неправильное использование блокирующих задач при этом может привести к взаимоблокировке.</span><span class="sxs-lookup"><span data-stu-id="5067f-190">The introduction of blocking tasks into this can easily result in a deadlock if not written correctly.</span></span> <span data-ttu-id="5067f-191">Кроме того, вложение такого асинхронного кода может усложнить анализ выполнения кода.</span><span class="sxs-lookup"><span data-stu-id="5067f-191">Additionally, the nesting of asynchronous code like this can also make it more difficult to reason about the execution of the code.</span></span> <span data-ttu-id="5067f-192">Асинхронное выполнение и LINQ — эффективные средства, но использовать их следует с максимальной осторожностью и ясным пониманием того, что вы делаете.</span><span class="sxs-lookup"><span data-stu-id="5067f-192">Async and LINQ are powerful, but should be used together as carefully and clearly as possible.</span></span>

* <span data-ttu-id="5067f-193">**При написании кода ожидание задач следует реализовывать без блокирования**</span><span class="sxs-lookup"><span data-stu-id="5067f-193">**Write code that awaits Tasks in a non-blocking manner**</span></span>

<span data-ttu-id="5067f-194">Блокирование текущего потока в целях ожидания завершения задачи может привести к взаимоблокировкам и блокированию потоков контекста, из-за чего может требоваться значительно более сложная обработка ошибок.</span><span class="sxs-lookup"><span data-stu-id="5067f-194">Blocking the current thread as a means to wait for a Task to complete can result in deadlocks and blocked context threads, and can require significantly more complex error-handling.</span></span> <span data-ttu-id="5067f-195">В приведенной ниже таблице даются рекомендации по реализации ожидания задач без блокировки.</span><span class="sxs-lookup"><span data-stu-id="5067f-195">The following table provides guidance on how to deal with waiting for Tasks in a non-blocking way:</span></span>

| <span data-ttu-id="5067f-196">Рекомендуемый способ</span><span class="sxs-lookup"><span data-stu-id="5067f-196">Use this...</span></span> | <span data-ttu-id="5067f-197">Нерекомендуемый способ</span><span class="sxs-lookup"><span data-stu-id="5067f-197">Instead of this...</span></span> | <span data-ttu-id="5067f-198">Задача</span><span class="sxs-lookup"><span data-stu-id="5067f-198">When wishing to do this</span></span> |
| --- | --- | --- |
| `await` | <span data-ttu-id="5067f-199">`Task.Wait` или `Task.Result`</span><span class="sxs-lookup"><span data-stu-id="5067f-199">`Task.Wait` or `Task.Result`</span></span> | <span data-ttu-id="5067f-200">Получение результата фоновой задачи</span><span class="sxs-lookup"><span data-stu-id="5067f-200">Retrieving the result of a background task</span></span> |
| `await Task.WhenAny` | `Task.WaitAny` | <span data-ttu-id="5067f-201">Ожидание завершения выполнения любой задачи</span><span class="sxs-lookup"><span data-stu-id="5067f-201">Waiting for any task to complete</span></span> |
| `await Task.WhenAll` | `Task.WaitAll` | <span data-ttu-id="5067f-202">Ожидание завершения выполнения всех задач</span><span class="sxs-lookup"><span data-stu-id="5067f-202">Waiting for all tasks to complete</span></span> |
| `await Task.Delay` | `Thread.Sleep` | <span data-ttu-id="5067f-203">Ожидание в течение заданного времени</span><span class="sxs-lookup"><span data-stu-id="5067f-203">Waiting for a period of time</span></span> |

* <span data-ttu-id="5067f-204">**Пишите код с менее строгим отслеживанием состояния**</span><span class="sxs-lookup"><span data-stu-id="5067f-204">**Write less stateful code**</span></span>

<span data-ttu-id="5067f-205">Старайтесь, чтобы выполнение кода не зависело от состояния глобальных объектов или выполнения определенных методов.</span><span class="sxs-lookup"><span data-stu-id="5067f-205">Don’t depend on the state of global objects or the execution of certain methods.</span></span> <span data-ttu-id="5067f-206">Оно должно зависеть только от возвращаемых методами значений.</span><span class="sxs-lookup"><span data-stu-id="5067f-206">Instead, depend only on the return values of methods.</span></span> <span data-ttu-id="5067f-207">Почему?</span><span class="sxs-lookup"><span data-stu-id="5067f-207">Why?</span></span>

* <span data-ttu-id="5067f-208">Код будет проще анализировать.</span><span class="sxs-lookup"><span data-stu-id="5067f-208">Code will be easier to reason about.</span></span>
* <span data-ttu-id="5067f-209">Код будет проще тестировать.</span><span class="sxs-lookup"><span data-stu-id="5067f-209">Code will be easier to test.</span></span>
* <span data-ttu-id="5067f-210">Гораздо проще будет сочетать асинхронный и синхронный код.</span><span class="sxs-lookup"><span data-stu-id="5067f-210">Mixing async and synchronous code is far simpler.</span></span>
* <span data-ttu-id="5067f-211">Как правило, можно полностью избежать состояний гонки.</span><span class="sxs-lookup"><span data-stu-id="5067f-211">Race conditions can typically be avoided altogether.</span></span>
* <span data-ttu-id="5067f-212">Зависимость от возвращаемых значений упрощает согласование асинхронного кода.</span><span class="sxs-lookup"><span data-stu-id="5067f-212">Depending on return values makes coordinating async code simple.</span></span>
* <span data-ttu-id="5067f-213">Дополнительным преимуществом является то, что такой код хорошо работает с внедрением зависимостей.</span><span class="sxs-lookup"><span data-stu-id="5067f-213">(Bonus) it works really well with dependency injection.</span></span>

<span data-ttu-id="5067f-214">Следует стремиться к достижению полной или почти полной [ссылочной прозрачности](https://en.wikipedia.org/wiki/Referential_transparency_%28computer_science%29) в коде.</span><span class="sxs-lookup"><span data-stu-id="5067f-214">A recommended goal is to achieve complete or near-complete [Referential Transparency](https://en.wikipedia.org/wiki/Referential_transparency_%28computer_science%29) in your code.</span></span> <span data-ttu-id="5067f-215">Результатом будет высокий уровень предсказуемости базы кода, а также ее пригодности для тестирования и обслуживания.</span><span class="sxs-lookup"><span data-stu-id="5067f-215">Doing so will result in an extremely predictable, testable, and maintainable codebase.</span></span>

## <a name="other-resources"></a><span data-ttu-id="5067f-216">Другие ресурсы</span><span class="sxs-lookup"><span data-stu-id="5067f-216">Other Resources</span></span>

* <span data-ttu-id="5067f-217">В статье [Подробный обзор асинхронного программирования](../standard/async-in-depth.md) приводятся дополнительные сведения о принципах работы задач.</span><span class="sxs-lookup"><span data-stu-id="5067f-217">[Async in-depth](../standard/async-in-depth.md) provides more information about how Tasks work.</span></span>
* [<span data-ttu-id="5067f-218">Асинхронное программирование с использованием ключевых слов Async и Await (C#)</span><span class="sxs-lookup"><span data-stu-id="5067f-218">Asynchronous programming with async and await (C#)</span></span>](./programming-guide/concepts/async/index.md)
* <span data-ttu-id="5067f-219">Эпизод [Six Essential Tips for Async](https://channel9.msdn.com/Series/Three-Essential-Tips-for-Async) (Шесть важных советов по асинхронному программированию) с Лусианом Вышиком (Lucian Wischik) — это отличный ресурс по асинхронному программированию.</span><span class="sxs-lookup"><span data-stu-id="5067f-219">Lucian Wischik's [Six Essential Tips for Async](https://channel9.msdn.com/Series/Three-Essential-Tips-for-Async) are a wonderful resource for async programming</span></span>
