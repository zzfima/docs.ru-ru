---
title: Использование асинхронного шаблона, основанного на задачах
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- .NET Framework, and TAP
- asynchronous design patterns, .NET Framework
- TAP, .NET Framework support for
- Task-based Asynchronous Pattern, .NET Framework support for
- .NET Framework, asynchronous design patterns
ms.assetid: 033cf871-ae24-433d-8939-7a3793e547bf
ms.openlocfilehash: f80e6ae520ab03c0f5f4edc30c0b7102193ee6c5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73139813"
---
# <a name="consuming-the-task-based-asynchronous-pattern"></a>Использование асинхронного шаблона, основанного на задачах

При работе асинхронными операциями с использованием асинхронного шаблона, основанного на задачах, можно использовать обратные вызовы для реализации неблокирующего ожидания.  Для задач это достигается с помощью таких методов, как <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType>. Поддержка асинхронных операций на основе языка скрывает обратные вызовы, разрешая асинхронным операциям находиться в режиме ожидания в нормальном потоке управления, а код, созданный компилятором, предоставляет поддержку на том же уровне API.

## <a name="suspending-execution-with-await"></a>Приостановление выполнения с помощью Await
 Начиная с версии .NET Framework 4.5 для асинхронного ожидания объектов [ и ](../../csharp/language-reference/operators/await.md) можно использовать ключевое слово [await](../../visual-basic/language-reference/operators/await-operator.md) (в C#) и <xref:System.Threading.Tasks.Task>оператор Await<xref:System.Threading.Tasks.Task%601> (в Visual Basic). Когда вы ожидаете <xref:System.Threading.Tasks.Task>, выражение `await` имеет тип `void`. Когда вы ожидаете <xref:System.Threading.Tasks.Task%601>, выражение `await` имеет тип `TResult`. Выражение `await` должно находиться в теле асинхронного метода. Дополнительные сведения о поддержке языков C# и Visual Basic в .NET Framework 4.5 см. в спецификациях языка C# и Visual Basic.

 На самом деле функция ожидания реализуется с помощью установки обратного вызова для задачи с помощью продолжения.  Этот обратный вызов возобновляет асинхронный методы в точке остановки. При возобновлении асинхронного метода, если ожидаемая операция была завершена успешно и имела тип <xref:System.Threading.Tasks.Task%601>, возвращается ее значение `TResult`.  Если ожидаемая операция <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601> завершилась с состоянием <xref:System.Threading.Tasks.TaskStatus.Canceled>, создается исключение <xref:System.OperationCanceledException>.  Если ожидаемая операция <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601> завершилась с состоянием <xref:System.Threading.Tasks.TaskStatus.Faulted>, создается вызвавшее эту проблему исключение. `Task` может завершиться с ошибкой из-за нескольких исключений, но распространяется только одно из этих исключений. Тем не менее, свойство <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> возвращает исключение <xref:System.AggregateException> с полным списком ошибок.

 Если контекст синхронизации (объект <xref:System.Threading.SynchronizationContext>) связан с потоком, который во время приостановки выполнял асинхронный метод (например, если свойство <xref:System.Threading.SynchronizationContext.Current%2A?displayProperty=nameWithType> имеет значение, отличное от `null`), асинхронный метод возобновляется в том же контексте синхронизации, для чего вызывается метод <xref:System.Threading.SynchronizationContext.Post%2A> этого контекста. В противном случае он полагается на планировщик задач (объект <xref:System.Threading.Tasks.TaskScheduler>), который использовался в момент приостановки. Обычно это планировщик по умолчанию (<xref:System.Threading.Tasks.TaskScheduler.Default%2A?displayProperty=nameWithType>), который нацелен на пул потоков. Этот планировщик задач определяет, следует ли возобновить приостановленную асинхронную операцию в тот момент, в который она была завершена, или следует ли запланировать возобновление. Планировщик по умолчанию обычно разрешает продолжение выполнения в потоке, который был завершен операцией.

 При вызове асинхронного метода он синхронно выполняет тело функции до первого выражения await для ожидаемого экземпляра, которое еще не было завершено, и в этот момент управление передается вызывающему объекту. Если асинхронный метод не возвращает `void`, в качестве представления текущего вычисления возвращается объект <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601>. В асинхронном методе, который возвращает значение, отличное от void, при обнаружении выражения return или при достижении окончания метода задача завершается в конечном состоянии <xref:System.Threading.Tasks.TaskStatus.RanToCompletion>. Если асинхронный метод теряет управление из-за необработанного исключения, задача завершается в состоянии <xref:System.Threading.Tasks.TaskStatus.Faulted>. Если же это исключение является <xref:System.OperationCanceledException>, задача завершается в состоянии <xref:System.Threading.Tasks.TaskStatus.Canceled>. Таким образом, результат или исключение в конечном счете будут сформированы.

 Существует несколько важных вариантов такого поведения.  Для повышения производительности, если к моменту ожидания задачи оказывается, что задача уже завершена, то управление не освобождается и функция продолжает выполнение.  Кроме того, возврат к исходному контексту не всегда желателен, и такое поведение можно изменить. Подробное описание приведено в следующем разделе.

### <a name="configuring-suspension-and-resumption-with-yield-and-configureawait"></a>Настройка приостановки и возобновления с помощью Yield и ConfigureAwait
 Существуют методы, которые позволяют получить больший контроль над выполнением асинхронного метода. Например, вы можете использовать метод <xref:System.Threading.Tasks.Task.Yield%2A?displayProperty=nameWithType> для внедрения точки приостановки в асинхронный метод:

```csharp
public class Task : …
{
    public static YieldAwaitable Yield();
    …
}
```

 Это аналогично асинхронному размещению или планированию возврата в текущий контекст.

```csharp
Task.Run(async delegate
{
    for(int i=0; i<1000000; i++)
    {
        await Task.Yield(); // fork the continuation into a separate work item
        ...
    }
});
```

 Также можно использовать метод <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType> для более точного контроля над приостановкой и возобновлением в асинхронном методе.  Как упоминалось ранее, по умолчанию текущий контекст записывается в момент приостановки асинхронного метода и используется для вызова продолжения асинхронного метода при возобновлении.  Во многих случаях это именно то поведение, к которому вы стремитесь.  В других случаях можно не заботиться о контексте продолжения. Для повышения производительности нужно избегать подобного размещения обратно в исходный контекст.  Для этого воспользуйтесь методом <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType>, чтобы сообщить операции await о том, что перехватывать и возобновлять контекст не нужно, и вместо этого необходимо продолжить выполнение в той точке, в которой завершилась ожидаемая асинхронная операция.

```csharp
await someTask.ConfigureAwait(continueOnCapturedContext:false);
```

## <a name="canceling-an-asynchronous-operation"></a>Отмена асинхронной операции
 Начиная с .NET Framework 4, методы TAP, которые поддерживают отмену, предоставляют по крайней мере одну перегрузку, которая принимает маркер отмены (объект <xref:System.Threading.CancellationToken>).

 Маркер отмены создается с помощью источника маркеров отмены (объект <xref:System.Threading.CancellationTokenSource>).  Свойство <xref:System.Threading.CancellationTokenSource.Token%2A> источника возвращает маркер отмены, который будет передаваться при вызове метода <xref:System.Threading.CancellationTokenSource.Cancel%2A> источника.  Например, если вы хотите скачать одну веб-страницу и при этом иметь возможность отменить операцию, создайте объект <xref:System.Threading.CancellationTokenSource>, передайте его маркер методу TAP и вызовите метод источника <xref:System.Threading.CancellationTokenSource.Cancel%2A>, когда нужно будет отменить операцию.

```csharp
var cts = new CancellationTokenSource();
string result = await DownloadStringAsync(url, cts.Token);
… // at some point later, potentially on another thread
cts.Cancel();
```

 Чтобы отменить несколько асинхронных вызовов, можно передать один и тот же маркер всем вызовам.

```csharp
var cts = new CancellationTokenSource();
    IList<string> results = await Task.WhenAll(from url in urls select DownloadStringAsync(url, cts.Token));
    // at some point later, potentially on another thread
    …
    cts.Cancel();
```

 Также можно передать один и тот же маркер выбранному подмножеству операций.

```csharp
var cts = new CancellationTokenSource();
    byte [] data = await DownloadDataAsync(url, cts.Token);
    await SaveToDiskAsync(outputPath, data, CancellationToken.None);
    … // at some point later, potentially on another thread
    cts.Cancel();
```

 Запрос на отмену может быть запущен из любого потока.

 Значение <xref:System.Threading.CancellationToken.None%2A?displayProperty=nameWithType> можно передать любому методу, который принимает маркер отмены. Это будет означать, что отмена никогда не будет запрашиваться.  В результате свойство <xref:System.Threading.CancellationToken.CanBeCanceled%2A?displayProperty=nameWithType> будет возвращать `false`, и вызываемый метод сможет принять меры для оптимизации.  Для тестирования также можно передать маркер отмены, для которого уже была выполнена отмена. Этот маркер инициализируется с помощью конструктора, который принимает логическое значение, означающее, следует ли запустить маркер в уже отмененном или неотменяемом состоянии.

 У такого подхода к отмене есть несколько преимуществ.

- Один и тот же маркер отмены можно передать в любое количество асинхронных и синхронных операций.

- Один и тот же запрос отмены можно распространить на любое количество прослушивателей.

- Разработчик асинхронного интерфейса API имеет полный контроль над тем, можно ли разрешить запрос отмены и когда ее можно применить.

- Код, который использует этот интерфейс API, может выборочно определять асинхронные вызовы, на которые будут распространены запросы отмены.

## <a name="monitoring-progress"></a>Наблюдение за ходом выполнения
 Некоторые асинхронные методы предоставляют сведения о ходе выполнения с помощью интерфейса хода выполнения, который передается в асинхронный метод.  Например, рассмотрим функцию, которая асинхронно загружает строку текста, одновременно обновляя сведения о ходе загрузки, которые включают долю уже загруженной части строки в процентах ко всей строке.  Этот метод можно использовать в приложении WPF следующим образом.

```csharp
private async void btnDownload_Click(object sender, RoutedEventArgs e)
{
    btnDownload.IsEnabled = false;
    try
    {
        txtResult.Text = await DownloadStringAsync(txtUrl.Text,
            new Progress<int>(p => pbDownloadProgress.Value = p));
    }
    finally { btnDownload.IsEnabled = true; }
}
```

<a name="combinators"></a>
## <a name="using-the-built-in-task-based-combinators"></a>Использование внутренних блоков объединения задач
 В пространстве имен <xref:System.Threading.Tasks> предусмотрено несколько способов объединять задачи и работать с ними.

### <a name="taskrun"></a>Task.Run
 Класс <xref:System.Threading.Tasks.Task> содержит несколько методов <xref:System.Threading.Tasks.Task.Run%2A>, которые позволяют легко разгрузить задачи в формате <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601> в пул потоков, например так:

```csharp
public async void button1_Click(object sender, EventArgs e)
{
    textBox1.Text = await Task.Run(() =>
    {
        // … do compute-bound work here
        return answer;
    });
}
```

 Некоторые из этих методов <xref:System.Threading.Tasks.Task.Run%2A>, например перегрузка <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType>, являются ссылкой на метод <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType>.  Другие перегрузки, например <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType>, позволяют использовать await в разгруженных задачах, например так:

```csharp
public async void button1_Click(object sender, EventArgs e)
{
    pictureBox1.Image = await Task.Run(async() =>
    {
        using(Bitmap bmp1 = await DownloadFirstImageAsync())
        using(Bitmap bmp2 = await DownloadSecondImageAsync())
        return Mashup(bmp1, bmp2);
    });
}
```

 Эти перегрузки логически эквивалентны вызову метода <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> в сочетании с методом расширения <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>из библиотеки параллельных задач.

### <a name="taskfromresult"></a>Task.FromResult
 Используйте метод <xref:System.Threading.Tasks.Task.FromResult%2A> в ситуациях, когда данные уже могут быть доступны и их достаточно возвратить в <xref:System.Threading.Tasks.Task%601> из метода, возвращающего задачу.

```csharp
public Task<int> GetValueAsync(string key)
{
    int cachedValue;
    return TryGetCachedValue(out cachedValue) ?
        Task.FromResult(cachedValue) :
        GetValueAsyncInternal();
}

private async Task<int> GetValueAsyncInternal(string key)
{
    …
}
```

### <a name="taskwhenall"></a>Task.WhenAll
 Используйте метод <xref:System.Threading.Tasks.Task.WhenAll%2A> для асинхронного ожидания нескольких асинхронных операций, которые представлены в виде задач.  У этого метода есть несколько перегрузок, которые поддерживают набор неуниверсальных задач или неоднородный набор универсальных задач (например, асинхронное ожидание нескольких операций, возвращающих void, или асинхронное ожидание несколько методов, возвращающих значение (при этом эти значения могут быть разных типов)), а также поддерживают единый набор универсальных задач (например, асинхронное ожидание нескольких методов, которые возвращают `TResult`).

 Предположим, что вы хотите отправить сообщения по электронной почте нескольким клиентам. Отправку сообщений можно перекрывать, чтобы не ожидать завершения отправки одного сообщения перед отправкой следующего. Также можно узнать, были ли выполнены операции отправки и возникли ли ошибки.

```csharp
IEnumerable<Task> asyncOps = from addr in addrs select SendMailAsync(addr);
await Task.WhenAll(asyncOps);
```

 Этот код не обрабатывает возможные исключения явным образом, но позволяет им распространяться из метода `await` на задачу, полученную от <xref:System.Threading.Tasks.Task.WhenAll%2A>.  Для обработки исключений можно использовать следующий код.

```csharp
IEnumerable<Task> asyncOps = from addr in addrs select SendMailAsync(addr);
try
{
    await Task.WhenAll(asyncOps);
}
catch(Exception exc)
{
    ...
}
```

 В этом случае при сбое любой асинхронной операции все исключения объединяются в одно исключение <xref:System.AggregateException>, которое сохраняется в <xref:System.Threading.Tasks.Task>, возвращаемом из метода <xref:System.Threading.Tasks.Task.WhenAll%2A>.  Однако с помощью ключевого слова `await` распространяется только одно из этих исключений.  Если вы хотите изучить все исключения, можно переписать предыдущий код следующим образом.

```csharp
Task [] asyncOps = (from addr in addrs select SendMailAsync(addr)).ToArray();
try
{
    await Task.WhenAll(asyncOps);
}
catch(Exception exc)
{
    foreach(Task faulted in asyncOps.Where(t => t.IsFaulted))
    {
        … // work with faulted and faulted.Exception
    }
}
```

 Рассмотрим в качестве примера асинхронную загрузку нескольких файлов из Интернета.  В этом случае все асинхронные операции имеют результаты одного типа, и к этим результатам легко получить доступ.

```csharp
string [] pages = await Task.WhenAll(
    from url in urls select DownloadStringAsync(url));
```

 Можно использовать те же способы обработки исключений, которые были рассмотрены в предыдущем сценарии с возвратом void.

```csharp
Task [] asyncOps =
    (from url in urls select DownloadStringAsync(url)).ToArray();
try
{
    string [] pages = await Task.WhenAll(asyncOps);
    ...
}
catch(Exception exc)
{
    foreach(Task<string> faulted in asyncOps.Where(t => t.IsFaulted))
    {
        … // work with faulted and faulted.Exception
    }
}
```

### <a name="taskwhenany"></a>Task.WhenAny
 Используйте метод <xref:System.Threading.Tasks.Task.WhenAny%2A> для асинхронного ожидания завершения одной из нескольких асинхронных операций, которые представлены в виде задач.  Этот метод допускает четыре основных варианта использования.

- Избыточность: многократный запуск одной операции и выбор первой завершенной операции (например, обращение к нескольким веб-сервисам котировок акций с целью получить один результат и выбор операции, которая завершилась первой).

- Чередование: запуск и ожидание завершения нескольких операций, но обработка операций по мере выполнения.

- Регулирование: добавление новых операций по мере завершения предыдущих.  Это расширение сценария с чередованием.

- Ранняя остановка: например, операция, представленная задачей t1, может сгруппироваться в задачу <xref:System.Threading.Tasks.Task.WhenAny%2A> с другой задачей t2, после чего можно ожидать задачу <xref:System.Threading.Tasks.Task.WhenAny%2A>. Например, задача t2 может представлять завершение ожидания, отмену или другой сигнал, требующий завершения задачи <xref:System.Threading.Tasks.Task.WhenAny%2A> до завершения задачи t1.

#### <a name="redundancy"></a>Избыточность
 Рассмотрим случай, когда вам требуется принять решение о необходимости покупки акций.  Существует несколько стандартных веб-служб с рекомендациями по покупке акций, которым вы доверяете, но в зависимости от ежедневной нагрузки каждая из этих служб иногда может работать медленно.  Для получения уведомлений о завершении любой операции можно использовать метод <xref:System.Threading.Tasks.Task.WhenAny%2A>:

```csharp
var recommendations = new List<Task<bool>>()
{
    GetBuyRecommendation1Async(symbol),
    GetBuyRecommendation2Async(symbol),
    GetBuyRecommendation3Async(symbol)
};
Task<bool> recommendation = await Task.WhenAny(recommendations);
if (await recommendation) BuyStock(symbol);
```

 В отличие от <xref:System.Threading.Tasks.Task.WhenAll%2A>, который возвращает распакованные результаты всех успешно выполненных задач, <xref:System.Threading.Tasks.Task.WhenAny%2A> возвращает завершенную задачу. Если задача завершилась сбоем, важно знать, что она завершилась сбоем, а если она завершилась успешно, важно знать, с какой задачей связано возвращаемое значение.  Поэтому необходимо получить доступ к результату, возвращаемому задачей, или продолжить ожидание, как показано в данном примере.

 Как и в случае с <xref:System.Threading.Tasks.Task.WhenAll%2A>, необходимо поддерживать исключения.  Так как вы получаете управление от завершенной задачи, вы можете подождать, пока не будут распространены ошибки для возвращенной задачи и `try/catch` их соответствующим образом.

```csharp
Task<bool> [] recommendations = …;
while(recommendations.Count > 0)
{
    Task<bool> recommendation = await Task.WhenAny(recommendations);
    try
    {
        if (await recommendation) BuyStock(symbol);
        break;
    }
    catch(WebException exc)
    {
        recommendations.Remove(recommendation);
    }
}
```

 Кроме того, даже если первая задача завершается успешно, следующие задачи могут завершиться сбоем.  В этом случае есть несколько вариантов обработки исключений: можно ждать, пока не завершатся все задачи, используя метод <xref:System.Threading.Tasks.Task.WhenAll%2A>, или решить, что все исключения важны и должны быть записаны в журнал.  В этом случае используется продолжение для получения уведомлений об успешном завершении задач.

```csharp
foreach(Task recommendation in recommendations)
{
    var ignored = recommendation.ContinueWith(
        t => { if (t.IsFaulted) Log(t.Exception); });
}
```

 или

```csharp
foreach(Task recommendation in recommendations)
{
    var ignored = recommendation.ContinueWith(
        t => Log(t.Exception), TaskContinuationOptions.OnlyOnFaulted);
}
```

 или даже:

```csharp
private static async void LogCompletionIfFailed(IEnumerable<Task> tasks)
{
    foreach(var task in tasks)
    {
        try { await task; }
        catch(Exception exc) { Log(exc); }
    }
}
…
LogCompletionIfFailed(recommendations);
```

 Наконец, вы можете отменить все остальные операции.

```csharp
var cts = new CancellationTokenSource();
var recommendations = new List<Task<bool>>()
{
    GetBuyRecommendation1Async(symbol, cts.Token),
    GetBuyRecommendation2Async(symbol, cts.Token),
    GetBuyRecommendation3Async(symbol, cts.Token)
};

Task<bool> recommendation = await Task.WhenAny(recommendations);
cts.Cancel();
if (await recommendation) BuyStock(symbol);
```

#### <a name="interleaving"></a>Чередование
 Рассмотрим ситуацию, в которой вы загружаете изображения из Интернета и обрабатываете каждое изображение (например, добавляете изображение в элемент управления пользовательского интерфейса).  Обработку изображений необходимо выполнять последовательно в потоке пользовательского интерфейса, но загружать их следует по возможности параллельно. Кроме того, для добавления изображений в пользовательский интерфейс не стоит ждать, пока все они будут загружены — удобнее добавлять каждое изображение после его загрузки.

```csharp
List<Task<Bitmap>> imageTasks =
    (from imageUrl in urls select GetBitmapAsync(imageUrl)).ToList();
while(imageTasks.Count > 0)
{
    try
    {
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);
        imageTasks.Remove(imageTask);

        Bitmap image = await imageTask;
        panel.AddImage(image);
    }
    catch{}
}
```

 Также вы можете применить чередование к сценарию, который подразумевает интенсивную вычислительную обработку пула загруженных изображений <xref:System.Threading.ThreadPool>, например так:

```csharp
List<Task<Bitmap>> imageTasks =
    (from imageUrl in urls select GetBitmapAsync(imageUrl)
         .ContinueWith(t => ConvertImage(t.Result)).ToList();
while(imageTasks.Count > 0)
{
    try
    {
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);
        imageTasks.Remove(imageTask);

        Bitmap image = await imageTask;
        panel.AddImage(image);
    }
    catch{}
}
```

#### <a name="throttling"></a>Регулирование
 Рассмотрим пример с чередованием с тем исключением, что на этот раз пользователь загружает так много изображений, что загрузку необходимо регулировать; например, вы можете ограничить максимальное количество параллельных загрузок. Для этого можно запустить подмножество асинхронных операций.  По завершении операций можно запускать дополнительные операции, которые займут их место.

```csharp
const int CONCURRENCY_LEVEL = 15;
Uri [] urls = …;
int nextIndex = 0;
var imageTasks = new List<Task<Bitmap>>();
while(nextIndex < CONCURRENCY_LEVEL && nextIndex < urls.Length)
{
    imageTasks.Add(GetBitmapAsync(urls[nextIndex]));
    nextIndex++;
}

while(imageTasks.Count > 0)
{
    try
    {
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);
        imageTasks.Remove(imageTask);

        Bitmap image = await imageTask;
        panel.AddImage(image);
    }
    catch(Exception exc) { Log(exc); }

    if (nextIndex < urls.Length)
    {
        imageTasks.Add(GetBitmapAsync(urls[nextIndex]));
        nextIndex++;
    }
}
```

#### <a name="early-bailout"></a>Ранняя остановка
 Рассмотрим, что вы асинхронно ожидаете завершения операции и одновременно отвечаете на запрос отмены пользователя (например, если пользователь нажал кнопку "Отмена"). Этот сценарий иллюстрируется в следующем коде.

```csharp
private CancellationTokenSource m_cts;

public void btnCancel_Click(object sender, EventArgs e)
{
    if (m_cts != null) m_cts.Cancel();
}

public async void btnRun_Click(object sender, EventArgs e)
{
    m_cts = new CancellationTokenSource();
    btnRun.Enabled = false;
    try
    {
        Task<Bitmap> imageDownload = GetBitmapAsync(txtUrl.Text);
        await UntilCompletionOrCancellation(imageDownload, m_cts.Token);
        if (imageDownload.IsCompleted)
        {
            Bitmap image = await imageDownload;
            panel.AddImage(image);
        }
        else imageDownload.ContinueWith(t => Log(t));
    }
    finally { btnRun.Enabled = true; }
}

private static async Task UntilCompletionOrCancellation(
    Task asyncOp, CancellationToken ct)
{
    var tcs = new TaskCompletionSource<bool>();
    using(ct.Register(() => tcs.TrySetResult(true)))
        await Task.WhenAny(asyncOp, tcs.Task);
    return asyncOp;
}
```

 В этой реализации сразу же после отмены загрузки отображается пользовательский интерфейс, но базовые асинхронные операции не отменяются.  В качестве альтернативы можно отменить ожидающие операции после отмены загрузки, но не отображать пользовательский интерфейс, пока операции на самом деле не завершатся (возможно, из-за раннего завершения, вызванного запросом отмены).

```csharp
private CancellationTokenSource m_cts;

public async void btnRun_Click(object sender, EventArgs e)
{
    m_cts = new CancellationTokenSource();

    btnRun.Enabled = false;
    try
    {
        Task<Bitmap> imageDownload = GetBitmapAsync(txtUrl.Text, m_cts.Token);
        await UntilCompletionOrCancellation(imageDownload, m_cts.Token);
        Bitmap image = await imageDownload;
        panel.AddImage(image);
    }
    catch(OperationCanceledException) {}
    finally { btnRun.Enabled = true; }
}
```

 Еще один пример ранней остановки предполагает использование метода <xref:System.Threading.Tasks.Task.WhenAny%2A> в сочетании с методом <xref:System.Threading.Tasks.Task.Delay%2A>, как описано в следующем разделе.

### <a name="taskdelay"></a>Task.Delay
 Метод <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> позволяет приостановить выполнение асинхронного метода.  Это удобно для реализации различных функций, включая создание циклов опроса и задержку обработки ввода пользователя на заданный период времени.  Метод <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> также можно использовать в сочетании с <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> для ограничения времени ожидания await.

 Если на выполнение задачи, которая является частью большой асинхронной операции (например, веб-служба ASP.NET), требуется слишком много времени, то это может негативно сказаться на всей операции, особенно если это приведет к неудачному завершению операции.  Поэтому важно иметь возможность задавать время ожидания для асинхронных операций.  Синхронные методы <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType> и <xref:System.Threading.Tasks.Task.WaitAny%2A?displayProperty=nameWithType> принимают значения времени ожидания, а соответствующий метод <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType>/<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> и ранее упомянутый <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>/<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> — нет.  Вместо этого вы можете совместно использовать <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> и <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> для ограничения времени ожидания.

 Например, предположим, что вы хотите загрузить приложение и отключить пользовательский интерфейс на время загрузки. Однако если загрузка занимает слишком много времени, вы можете отменить загрузку и вернуться в пользовательский интерфейс.

```csharp
public async void btnDownload_Click(object sender, EventArgs e)
{
    btnDownload.Enabled = false;
    try
    {
        Task<Bitmap> download = GetBitmapAsync(url);
        if (download == await Task.WhenAny(download, Task.Delay(3000)))
        {
            Bitmap bmp = await download;
            pictureBox.Image = bmp;
            status.Text = "Downloaded";
        }
        else
        {
            pictureBox.Image = null;
            status.Text = "Timed out";
            var ignored = download.ContinueWith(
                t => Trace("Task finally completed"));
        }
    }
    finally { btnDownload.Enabled = true; }
}
```

 Это же применимо и скачиванию нескольких файлов, так как <xref:System.Threading.Tasks.Task.WhenAll%2A> возвращает задачу:

```csharp
public async void btnDownload_Click(object sender, RoutedEventArgs e)
{
    btnDownload.Enabled = false;
    try
    {
        Task<Bitmap[]> downloads =
            Task.WhenAll(from url in urls select GetBitmapAsync(url));
        if (downloads == await Task.WhenAny(downloads, Task.Delay(3000)))
        {
            foreach(var bmp in downloads) panel.AddImage(bmp);
            status.Text = "Downloaded";
        }
        else
        {
            status.Text = "Timed out";
            downloads.ContinueWith(t => Log(t));
        }
    }
    finally { btnDownload.Enabled = true; }
}
```

## <a name="building-task-based-combinators"></a>Создание блоков объединения на основе задач
 Поскольку задача может полностью представлять асинхронную операцию и предоставляет синхронные и асинхронные функции для соединения с операцией, получения ее результатов и т. д., то вы можете создавать полезные библиотеки блоков объединения, которые объединяют задачи для создания шаблонов большего размера.  Как уже обсуждалось в предыдущем разделе, в платформе .NET Framework есть несколько встроенных блоков объединения, но вы можете создать и собственные. В следующих разделах приведено несколько примеров возможных методов и типов блоков объединения.

### <a name="retryonfault"></a>RetryOnFault
 Во многих ситуациях может потребоваться повторить операцию, если предыдущая попытка завершилась неудачно.  Для решения этой задачи в синхронном коде можно использовать вспомогательный метод, например `RetryOnFault` в следующем примере.

```csharp
public static T RetryOnFault<T>(
    Func<T> function, int maxTries)
{
    for(int i=0; i<maxTries; i++)
    {
        try { return function(); }
        catch { if (i == maxTries-1) throw; }
    }
    return default(T);
}
```

 Вы можете создать почти такой же вспомогательный метод для асинхронных операций, которые реализованы в TAP и таким образом вернуть задачи.

```csharp
public static async Task<T> RetryOnFault<T>(
    Func<Task<T>> function, int maxTries)
{
    for(int i=0; i<maxTries; i++)
    {
        try { return await function().ConfigureAwait(false); }
        catch { if (i == maxTries-1) throw; }
    }
    return default(T);
}
```

 Этот блок объединения также можно использовать для анализа повторных попыток в логике приложения.

```csharp
// Download the URL, trying up to three times in case of failure
string pageContents = await RetryOnFault(
    () => DownloadStringAsync(url), 3);
```

 Функцию `RetryOnFault` можно улучшить. Например, функция может принимать другой `Func<Task>`, который будет вызываться между повторными попытками, чтобы определить, когда операцию нужно повторить.

```csharp
public static async Task<T> RetryOnFault<T>(
    Func<Task<T>> function, int maxTries, Func<Task> retryWhen)
{
    for(int i=0; i<maxTries; i++)
    {
        try { return await function().ConfigureAwait(false); }
        catch { if (i == maxTries-1) throw; }
        await retryWhen().ConfigureAwait(false);
    }
    return default(T);
}
```

 Чтобы подождать одну секунду перед повтором операции, эту функцию можно использовать следующим образом.

```csharp
// Download the URL, trying up to three times in case of failure,
// and delaying for a second between retries
string pageContents = await RetryOnFault(
    () => DownloadStringAsync(url), 3, () => Task.Delay(1000));
```

### <a name="needonlyone"></a>NeedOnlyOne
 В некоторых случаях для повышения задержки и вероятности успешного завершения операции можно воспользоваться преимуществами избыточности.  Рассмотрим несколько веб-служб, которые предоставляют котировки акций в разное время дня, и каждая служба обеспечивает различный уровень качества и время отклика.  Чтобы справиться с неравномерным характером поступления данных, вы можете отправлять запросы ко всем веб-службам и при получении ответа от одной из веб-служб отменять оставшиеся запросы.  Вы можете реализовать вспомогательную функцию для более удобной реализации этого распространенного шаблона с запуском нескольких операций, ожидания завершения любой операции и последующей отмены остальных. Функция `NeedOnlyOne` в следующем примере иллюстрирует этот сценарий.

```csharp
public static async Task<T> NeedOnlyOne(
    params Func<CancellationToken,Task<T>> [] functions)
{
    var cts = new CancellationTokenSource();
    var tasks = (from function in functions
                 select function(cts.Token)).ToArray();
    var completed = await Task.WhenAny(tasks).ConfigureAwait(false);
    cts.Cancel();
    foreach(var task in tasks)
    {
        var ignored = task.ContinueWith(
            t => Log(t), TaskContinuationOptions.OnlyOnFaulted);
    }
    return completed;
}
```

 Затем можно использовать эту функцию следующим образом.

```csharp
double currentPrice = await NeedOnlyOne(
    ct => GetCurrentPriceFromServer1Async("msft", ct),
    ct => GetCurrentPriceFromServer2Async("msft", ct),
    ct => GetCurrentPriceFromServer3Async("msft", ct));
```

### <a name="interleaved-operations"></a>Операции с чередованием
 При использовании метода <xref:System.Threading.Tasks.Task.WhenAny%2A> для поддержки сценария чередования при работе с очень большими наборами задач существует потенциальная проблема производительности. Каждый вызов <xref:System.Threading.Tasks.Task.WhenAny%2A> приводит к регистрации продолжения в каждой задаче. Для N задач это приводит к созданию O(N<sup>2</sup>) продолжений в течение времени существования операции чередования. При работе с большим набором задач можно использовать комбинатор (`Interleaved` в следующем примере), чтобы решить проблему производительности:

```csharp
static IEnumerable<Task<T>> Interleaved<T>(IEnumerable<Task<T>> tasks)
{
    var inputTasks = tasks.ToList();
    var sources = (from _ in Enumerable.Range(0, inputTasks.Count)
                   select new TaskCompletionSource<T>()).ToList();
    int nextTaskIndex = -1;
    foreach (var inputTask in inputTasks)
    {
        inputTask.ContinueWith(completed =>
        {
            var source = sources[Interlocked.Increment(ref nextTaskIndex)];
            if (completed.IsFaulted)
                source.TrySetException(completed.Exception.InnerExceptions);
            else if (completed.IsCanceled)
                source.TrySetCanceled();
            else
                source.TrySetResult(completed.Result);
        }, CancellationToken.None,
           TaskContinuationOptions.ExecuteSynchronously,
           TaskScheduler.Default);
    }
    return from source in sources
           select source.Task;
}
```

 Затем с помощью блоков объединения можно объединять результаты задач по мере их завершения.

```csharp
IEnumerable<Task<int>> tasks = ...;
foreach(var task in Interleaved(tasks))
{
    int result = await task;
    …
}
```

### <a name="whenallorfirstexception"></a>WhenAllOrFirstException
 В некоторых сценариях распределения и объединения вы можете ожидать, пока одна из задач в наборе не завершится сбоем, в этом случае ожидание прекращается, так как выдается исключение.  Для этого можно использовать такой блок объединения как `WhenAllOrFirstException`, как в следующем примере.

```csharp
public static Task<T[]> WhenAllOrFirstException<T>(IEnumerable<Task<T>> tasks)
{
    var inputs = tasks.ToList();
    var ce = new CountdownEvent(inputs.Count);
    var tcs = new TaskCompletionSource<T[]>();

    Action<Task> onCompleted = (Task completed) =>
    {
        if (completed.IsFaulted)
            tcs.TrySetException(completed.Exception.InnerExceptions);
        if (ce.Signal() && !tcs.Task.IsCompleted)
            tcs.TrySetResult(inputs.Select(t => t.Result).ToArray());
    };

    foreach (var t in inputs) t.ContinueWith(onCompleted);
    return tcs.Task;
}
```

## <a name="building-task-based-data-structures"></a>Создание структур данных на основе задач
 Кроме возможности создавать блоки объединения на основе задач, <xref:System.Threading.Tasks.Task> и <xref:System.Threading.Tasks.Task%601> имеют структуру данных, которая представляет результаты асинхронной операции и необходимую синхронизацию для объединения, что делает их очень мощным инструментом для создания пользовательских структур данных для асинхронных сценариев.

### <a name="asynccache"></a>AsyncCache
 Одним из важных аспектов задачи является то, что ее можно передать нескольким потребителям, каждый из которых может ожидать ее, регистрировать продолжения для этой задачи, получать ее результат или исключения (для <xref:System.Threading.Tasks.Task%601>) и т. д.  Благодаря этому <xref:System.Threading.Tasks.Task> и <xref:System.Threading.Tasks.Task%601> идеально подходят для асинхронной инфраструктуры кэширования.  Ниже приведен пример небольшого, но мощного асинхронного кэша, созданного на основе <xref:System.Threading.Tasks.Task%601>:

```csharp
public class AsyncCache<TKey, TValue>
{
    private readonly Func<TKey, Task<TValue>> _valueFactory;
    private readonly ConcurrentDictionary<TKey, Lazy<Task<TValue>>> _map;

    public AsyncCache(Func<TKey, Task<TValue>> valueFactory)
    {
        if (valueFactory == null) throw new ArgumentNullException("loader");
        _valueFactory = valueFactory;
        _map = new ConcurrentDictionary<TKey, Lazy<Task<TValue>>>();
    }

    public Task<TValue> this[TKey key]
    {
        get
        {
            if (key == null) throw new ArgumentNullException("key");
            return _map.GetOrAdd(key, toAdd =>
                new Lazy<Task<TValue>>(() => _valueFactory(toAdd))).Value;
        }
    }
}
```

 Класс [AsyncCache\<TKey,TValue](https://devblogs.microsoft.com/pfxteam/parallelextensionsextras-tour-12-asynccache/) в качестве делегата своего конструктора принимает функцию, которая принимает значение `TKey` и возвращает значение <xref:System.Threading.Tasks.Task%601>.  Ранее запрошенные из кэша значения хранятся во внутреннем словаре, и `AsyncCache` гарантирует, что для одного ключа создается только одна задача, даже при одновременном доступе к кэшу.

 Например, можно создать кэш для загруженных веб-страниц.

```csharp
private AsyncCache<string,string> m_webPages =
    new AsyncCache<string,string>(DownloadStringAsync);
```

 Затем можно использовать этот кэш в асинхронных методах каждый раз, когда вам потребуется содержимое какой-либо веб-страницы. Класс `AsyncCache` гарантирует, что будет загружено минимальное число страниц, и кэширует результаты.

```csharp
private async void btnDownload_Click(object sender, RoutedEventArgs e)
{
    btnDownload.IsEnabled = false;
    try
    {
        txtContents.Text = await m_webPages["https://www.microsoft.com"];
    }
    finally { btnDownload.IsEnabled = true; }
}
```

### <a name="asyncproducerconsumercollection"></a>AsyncProducerConsumerCollection
 Задачи также можно использовать для создания структур данных для координации асинхронных действий.  Рассмотрим один из классических шаблонов параллельных систем: производитель/потребитель.  В этой схеме производители создают данные, которые используются потребителями и производители и потребители могут работать параллельно. Например, потребитель обрабатывает элемент 1, который ранее был создан производителем, который в это же время создает элемент 2.  Для схемы "производитель/потребитель" в любом случае потребуется некоторая структура данных, в которой будут храниться объекты, создаваемые производителем. Эта структура необходима для того, чтобы потребитель мог узнать о новых данных и получить их, когда они будут доступны.

 Вот простая структура данных на основе задач, которая позволяет использовать асинхронные методы в качестве производителей и потребителей.

```csharp
public class AsyncProducerConsumerCollection<T>
{
    private readonly Queue<T> m_collection = new Queue<T>();
    private readonly Queue<TaskCompletionSource<T>> m_waiting =
        new Queue<TaskCompletionSource<T>>();

    public void Add(T item)
    {
        TaskCompletionSource<T> tcs = null;
        lock (m_collection)
        {
            if (m_waiting.Count > 0) tcs = m_waiting.Dequeue();
            else m_collection.Enqueue(item);
        }
        if (tcs != null) tcs.TrySetResult(item);
    }

    public Task<T> Take()
    {
        lock (m_collection)
        {
            if (m_collection.Count > 0)
            {
                return Task.FromResult(m_collection.Dequeue());
            }
            else
            {
                var tcs = new TaskCompletionSource<T>();
                m_waiting.Enqueue(tcs);
                return tcs.Task;
            }
        }
    }
}
```

 С этой структурой данных на месте можно написать следующий код.

```csharp
private static AsyncProducerConsumerCollection<int> m_data = …;
…
private static async Task ConsumerAsync()
{
    while(true)
    {
        int nextItem = await m_data.Take();
        ProcessNextItem(nextItem);
    }
}
…
private static void Produce(int data)
{
    m_data.Add(data);
}
```

Пространство имен <xref:System.Threading.Tasks.Dataflow> включает также тип <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>, который можно использовать аналогичным образом, но не создавая пользовательский тип коллекции:

```csharp
private static BufferBlock<int> m_data = …;
…
private static async Task ConsumerAsync()
{
    while(true)
    {
        int nextItem = await m_data.ReceiveAsync();
        ProcessNextItem(nextItem);
    }
}
…
private static void Produce(int data)
{
    m_data.Post(data);
}
```

> [!NOTE]
> Пространство имен <xref:System.Threading.Tasks.Dataflow> доступно в .NET Framework 4.5 через **NuGet**. Чтобы установить сборку, которая содержит пространство имен <xref:System.Threading.Tasks.Dataflow>, откройте проект в Visual Studio, в меню "Проект" выберите пункт **Управление пакетами NuGet** и найдите в Интернете пакет Microsoft.Tpl.Dataflow.

## <a name="see-also"></a>См. также раздел

- [Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (Асинхронный шаблон, основанный на задачах (TAP))
- [Реализация асинхронной модели на основе задач](../../../docs/standard/asynchronous-programming-patterns/implementing-the-task-based-asynchronous-pattern.md)
- [Взаимодействие с другими асинхронными шаблонами и типами](../../../docs/standard/asynchronous-programming-patterns/interop-with-other-asynchronous-patterns-and-types.md)
