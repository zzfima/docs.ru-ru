---
title: "Consuming the Task-based Asynchronous Pattern | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".NET Framework, and TAP"
  - "asynchronous design patterns, .NET Framework"
  - "TAP, .NET Framework support for"
  - "Task-based Asynchronous Pattern, .NET Framework support for"
  - ".NET Framework, asynchronous design patterns"
ms.assetid: 033cf871-ae24-433d-8939-7a3793e547bf
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Consuming the Task-based Asynchronous Pattern
При использовании основанного на задачах асинхронного шаблона \(TAP\) для работы с асинхронными операциями можно использовать обратные вызовы для достижения ожидания без блокировки.  Для задач это достигается с помощью таких методов, как <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=fullName>.  Языковая асинхронная поддержка скрывает обратные вызовы, позволяя ожидать асинхронные операции в нормальном потоке выполнения с помощью созданного компилятором кода.  
  
## Приостановка выполнения с помощью Await  
 Начиная с [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], можно использовать ключевое слово [await](../Topic/await%20\(C%23%20Reference\).md) в C\# и [Оператор Await](../Topic/Await%20Operator%20\(Visual%20Basic\).md) в Visual Basic, чтобы осуществить асинхронное ожидание объектов <xref:System.Threading.Tasks.Task> и <xref:System.Threading.Tasks.Task%601>.  Если ожидается <xref:System.Threading.Tasks.Task>, выражение `await` имеет тип `void`.  Если ожидается <xref:System.Threading.Tasks.Task%601>, выражение `await` имеет тип `TResult`.  Выражение `await` должно использоваться внутри тела асинхронного метода.  Дополнительные сведения о поддержке языке C\# и Visual Basic в [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] см. в спецификации языка C\# и Visual Basic.  
  
 На внутреннем уровне await с помощью возобновления устанавливает обратный вызов для задачи.  Этот обратный вызов возобновит асинхронный метод с момента приостановки.  При возобновлении асинхронного метода, если ожидаемая операция успешно завершилась и являлась <xref:System.Threading.Tasks.Task%601>, то будет возвращен `TResult`.  Если ожидаемая операция <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601> завершилась состоянием <xref:System.Threading.Tasks.TaskStatus>, то создается исключение <xref:System.OperationCanceledException>.  Если ожидаемая операция <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601> завершилась состоянием <xref:System.Threading.Tasks.TaskStatus>, то создается исключение, соответствующее ошибке.  `Task` может завершиться с ошибкой в результате нескольких исключений, но только одно из этих исключений распространяется.  Однако свойство <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=fullName> возвращает исключение <xref:System.AggregateException>, которое содержит все ошибки.  
  
 Если контекст синхронизации \(объект <xref:System.Threading.SynchronizationContext> \) связан с потоком, который выполнял асинхронный метод во время приостановки \(например, если свойство <xref:System.Threading.SynchronizationContext.Current%2A?displayProperty=fullName> не `null`\), то асинхронный метод возобновляется в том же контексте синхронизации с помощью метода контекста <xref:System.Threading.SynchronizationContext.Post%2A>.  В противном случае он полагается на планировщик задач \(объект <xref:System.Threading.Tasks.TaskScheduler> \), который был текущим во время приостановки.  Обычно это планировщик задач по умолчанию \(<xref:System.Threading.Tasks.TaskScheduler.Default%2A?displayProperty=fullName>\), который предназначен для пула потоков.  Этот планировщик задач определяет, должна ли находящаяся в ожидании асинхронная операция возобновится с того места, где была завершена, или должно быть запланировано возобновление.  Планировщик по умолчанию обычно разрешает возобновление запуска завершенной ожидаемой операции на потоке.  
  
 Асинхронный метод синхронно выполняет тело функции вплоть до первого выражения await для способного к ожиданию экземпляра, который еще не завершен, и на этом месте вызов возвращается вызывающему объекту.  Если асинхронный метод не возвращает `void`, то объект <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601> возвращается для представления текущих вычислительных операций.  В возвращающем значение асинхронном методе, если обнаружен оператор return или достигнут конец тела метода, то задача завершается в конечном состоянии <xref:System.Threading.Tasks.TaskStatus>.  Если необработанное исключение приводит к выходу из тела асинхронного метода, то задача завершается в состоянии Faulted \(если этим исключением является <xref:System.Threading.Tasks.TaskStatus>.  Если создается исключение <xref:System.OperationCanceledException>, то задача заканчивается в состоянии <xref:System.Threading.Tasks.TaskStatus>.  Таким образом, результат или исключение в итоге будет опубликованы.  
  
 Существует несколько важных вариантов описываемого поведения.  По соображениям производительности, если задача уже завершена к моменту, когда она является ожидаемой, управление не будет передано, и функция будет продолжать выполнение.  Кроме того, возврат к исходному контексту не всегда является желаемым поведением и оно может быть изменено; более подробно об этом написано в следующем разделе.  
  
### Настройка приостановки и возобновления с помощью Yield и ConfigureAwait  
 Некоторые члены дают больший контроль над выполнением асинхронного метода.  Например, можно использовать метод <xref:System.Threading.Tasks.Task.Yield%2A?displayProperty=fullName> который может быть использован для вставки точки передачи управления в асинхронный метод:  
  
```csharp  
public class Task : …  
{  
    public static YieldAwaitable Yield();  
    …  
}  
  
```  
  
 Это эквивалентно асинхронной передаче данных или планированию обратно на текущий контекст.  
  
```csharp  
Task.Run(async  delegate  
{  
    for(int i=0; i<1000000; i++)  
    {  
        await Task.Yield(); // fork the continuation into a separate work item  
        ...  
    }  
});  
  
```  
  
 Можно также использовать метод <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=fullName> для лучшего контроля над приостановкой и возобновлением в асинхронном методе.  Как упоминалось ранее, по умолчанию текущий контекст захватывается в тот момент времени, когда асинхронный метод приостановлен, и этот захваченный контекст используется для вызова продолжения асинхронного метода при возобновлении.  Во многих случаях это подходящее поведение.  В других случаях можно не заботиться о контексте продолжения и можно достичь более высокой производительности, избегая передачи обратно в исходный контекст.  Чтобы воспользоваться этим, можно использовать метод <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=fullName> для информирования операции await о запрете захвата и возобновления в контексте и о возобновление выполнения в любой момент, когда ожидаемая асинхронная операция завершилась:  
  
```csharp  
await someTask.ConfigureAwait(continueOnCapturedContext:false);  
  
```  
  
## Отмена асинхронной операции  
 Начиная с [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], TAP\-методы, поддерживающие отмену, предоставляют хотя бы одну перегрузку, которая принимает токен отмены \(объект <xref:System.Threading.CancellationToken> \).  
  
 Токен отмены создается с помощью источника токена отмены \(объект <xref:System.Threading.CancellationTokenSource> \).  Свойство <xref:System.Threading.CancellationTokenSource.Token%2A> источника получает токен отмены, который будет получать сигнал, когда будет вызываться метод <xref:System.Threading.CancellationTokenSource.Cancel%2A> источника.  Например, если нужно загрузить одну веб\-страницу и требуется возможность отмены операции, создайте объект <xref:System.Threading.CancellationTokenSource>, передайте его токен TAP\-методу, и затем вызовите метод источника <xref:System.Threading.CancellationTokenSource.Cancel%2A> , если нужно отменить операцию.  
  
```csharp  
var cts = new CancellationTokenSource();  
string result = await DownloadStringAsync(url, cts.Token);  
… // at some point later, potentially on another thread  
cts.Cancel();  
  
```  
  
 Для отмены нескольких асинхронных вызовов этот же токен может быть передан во все вызовы:  
  
```csharp  
var cts = new CancellationTokenSource();  
    IList<string> results = await Task.WhenAll(from url in urls select DownloadStringAsync(url, cts.Token));  
    // at some point later, potentially on another thread  
    …  
    cts.Cancel();  
  
```  
  
 Или можно передать один и тот же токен выбранному подмножеству операций:  
  
```csharp  
var cts = new CancellationTokenSource();  
    byte [] data = await DownloadDataAsync(url, cts.Token);  
    await SaveToDiskAsync(outputPath, data, CancellationToken.None);  
    … // at some point later, potentially on another thread  
    cts.Cancel();  
  
```  
  
 Запросы отмены могут быть запущены из любого потока.  
  
 Можно передать значение <xref:System.Threading.CancellationToken.None%2A?displayProperty=fullName> любому методу, чтобы указать, что отмена никогда не будет запрошена.  Это приводит к тому, что свойство <xref:System.Threading.CancellationToken.CanBeCanceled%2A?displayProperty=fullName> вернет `false` и вызванный метод может быть соответствующие оптимизирован.  В целях тестирования можно также передавать предварительно отмененный токен отмены, который создается с помощью конструктора, принимающего логическое значение, указывающее, должен ли токен создаваться в уже отмененном или не отмененном состоянии.  
  
 Этот подход к отмене имеет несколько преимуществ:  
  
-   Можно передать один и тот же токен отмены к любому числу синхронных и асинхронных операций.  
  
-   Один и тот же запрос отмены может быть распространен на любое количество слушателей.  
  
-   Разработчик асинхронного API полностью контролирует возможность запроса отмены и где отмена может вступить в силу.  
  
-   Код, который использует API, может выборочно указать асинхронные вызовы, на которые будут распространятся запросы отмены.  
  
## Наблюдение за ходом выполнения  
 Некоторый асинхронные методы предоставляют ход выполнения через интерфейс хода выполнения, передаваемый в асинхронный метод.  Например, рассмотрим функцию, которая асинхронно загружает строку текста и в процессе работы вызывает обновления выполнения, которое включает процент завершенных загрузок до завершения данного момента.  Такой метод может быть используется в приложении Windows Presentation Foundation \(WPF\) следующим образом:  
  
```csharp  
private async  void btnDownload_Click(object sender, RoutedEventArgs e)    
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
## Использование встроенных комбинаторов, основанных на задачах  
 Пространство имен <xref:System.Threading.Tasks> включает несколько методов для составления задач и работы с ними.  
  
### Task.Run  
 Класс <xref:System.Threading.Tasks.Task> предоставляет несколько методов <xref:System.Threading.Tasks.Task.Run%2A>, такие как <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601> , позволяющие легко выгрузить работу из пула потоков, например:  
  
```csharp  
public async  void button1_Click(object sender, EventArgs e)  
{  
    textBox1.Text = await Task.Run(() =>  
    {  
        // … do compute-bound work here  
        return answer;  
    });  
}  
  
```  
  
 Некоторые из этих методов <xref:System.Threading.Tasks.Task.Run%2A>, например перегрузка <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=fullName>, существуют как условные обозначения для метода <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=fullName>.  Другие перегрузки, такие как <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=fullName>, позволяют использовать await с выгружаемой работой, например:  
  
```csharp  
public async  void button1_Click(object sender, EventArgs e)  
{  
    pictureBox1.Image = await Task.Run(async() =>  
    {  
        using(Bitmap bmp1 = await DownloadFirstImageAsync())  
        using(Bitmap bmp2 = await DownloadSecondImageAsync())  
        return Mashup(bmp1, bmp2);  
    });  
}  
```  
  
 Такие перегрузки логически эквивалентны использованию метода <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=fullName> совместно с методом расширения <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> в библиотеке параллельных задач.  
  
### Task.FromResult  
 Используйте метод <xref:System.Threading.Tasks.Task.FromResult%2A> в сценариях, где данные могут быть уже доступны и их нужно вернуть из возвращающего задачу метода, вызываемого в <xref:System.Threading.Tasks.Task%601>:  
  
```csharp  
public Task<int> GetValueAsync(string key)  
{  
    int cachedValue;  
    return TryGetCachedValue(out cachedValue) ?  
        Task.FromResult(cachedValue) :  
        GetValueAsyncInternal();  
}  
  
private async  Task<int> GetValueAsyncInternal(string key)  
{  
    …  
}  
  
```  
  
### Task.WhenAll  
 Используйте асинхронный метод <xref:System.Threading.Tasks.Task.WhenAll%2A> для ожидания нескольких асинхронных операций, которые представлены в виде задачи.  Метод имеет несколько перегруженных вариантов, которые поддерживают множество не универсальных задач или неоднородное множество универсальных задач \(например, асинхронное ожидание нескольких операций, не возвращающих результат, либо асинхронное ожидание нескольких методов, возвращающих значения, в которых каждое из значений может быть различного типа\), а так же однородное множество универсальных задач \(например, асинхронное ожидание нескольких методов, возвращающих `TResult`\).  
  
 Допустим, необходимо отправить почтовые сообщения нескольким клиентам.  Можно перекрывать отправку сообщений, чтобы не ждать, когда завершится отправка одного, чтобы отправить следующее.  Также можно узнать, когда завершилась операция отправки и произошли ли какие\-либо ошибки:  
  
```csharp  
IEnumerable<Task> asyncOps = from addr in addrs select SendMailAsync(addr);  
await Task.WhenAll(asyncOps);  
  
```  
  
 Этот код явно не обрабатывает исключения, которые могут произойти, но позволяет распространить исключения из `await` на результирующую задачу из <xref:System.Threading.Tasks.Task.WhenAll%2A>.  Для обработки исключений можно использовать следующий код:  
  
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
  
 В этом случае, если асинхронная операция завершается неудачей, все исключения будут объединены в исключении <xref:System.AggregateException>, которое хранится в объекте <xref:System.Threading.Tasks.Task>, который возвращается из метода <xref:System.Threading.Tasks.Task.WhenAll%2A>.  Однако только одно из этих исключений распространится при помощи ключевого слова `await`.  Если нужно просмотреть все исключения, то можно переписать предыдущий код следующим образом:  
  
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
  
 Рассмотрим пример с загрузкой нескольких файлов из Интернета в асинхронном режиме.  В этом случае все асинхронные операции имеют одинаковые типы результатов, а получить доступ к результатам легко:  
  
```csharp  
string [] pages = await Task.WhenAll(  
    from url in urls select DownloadStringAsync(url));  
```  
  
 Можно использовать те же методы обработки ошибок, которые обсуждались в предыдущем void\-сценарии:  
  
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
  
### Task.WhenAny  
 Можно использовать метод <xref:System.Threading.Tasks.Task.WhenAny%2A> для асинхронного ожидания лишь одной из нескольких асинхронных операций, представленных в качестве задачи.  Этот метод используется для четырех основных вариантов действий:  
  
-   Избыточность: многократный запуск одной операции и выбор той операции из запущенных, которая завершилась первой \(например, связываться с несколькими веб\-сервисами котировки акции и ожидать первый завершенный запрос\).  
  
-   Чередование: запуск нескольких операций и ожидание завершения их всех, причем обработка их производится по мере того, как они завершаются.  
  
-   Регулирование: начало новых операций по мере завершения уже выполняющихся.  Это является расширением сценария чередования.  
  
-   Ранняя остановка: например, операция, представленная задачей t1, может группироваться в задачу <xref:System.Threading.Tasks.Task.WhenAny%2A> с другой задачей t2, вы можете ожидать задачу <xref:System.Threading.Tasks.Task.WhenAny%2A>.  Задача t2 может представлять собою истечение времени ожидания, отмену или какой\-либо другой сигнал, который приведет к завершению задачи <xref:System.Threading.Tasks.Task.WhenAny%2A> до завершения t1.  
  
#### Избыточность  
 Рассмотрим случай, когда необходимо решить, нужно ли покупать акцию.  Доступно несколько рекомендующих акции веб\-служб, которым можно доверять, но ежедневная загрузка данных каждой службы может происходить достаточно медленно в разные моменты времени.  Можно использовать метод <xref:System.Threading.Tasks.Task.WhenAny%2A> для получения уведомления при завершении любой операции.  
  
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
  
 В отличие от <xref:System.Threading.Tasks.Task.WhenAll%2A>, который в случае успешного завершения всех задач возвращает список развернутых результатов, <xref:System.Threading.Tasks.Task.WhenAny%2A> возвращает задачу, которая была завершена.  Если задача завершается неудачей, важно иметь возможность узнать об ошибке, и если задача завершается успешно, важно иметь возможность определить, какая задача связана с возвращённым значением.  Поэтому необходимо получить доступ к результату, возвращаемому задачей, или продолжить ожидать, как это сделано в данном примере.  
  
 Как и в случае с <xref:System.Threading.Tasks.Task.WhenAll%2A>, необходимо иметь возможность обрабатывать исключения.  В результате возврата завершенной задачи можно ожидать у возвращаемой задачи наличие распространяемых ошибок и перехватить их, используя `try/catch`, например следующим образом:  
  
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
  
 Кроме того, даже если первая задача завершается успешно, дальнейшие задачи могут завершиться с ошибкой.  На этом этапе имеется несколько вариантов обработки исключений: можно ждать, пока не завершатся все задачи, используя метод <xref:System.Threading.Tasks.Task.WhenAll%2A>, или можно решить, что все исключения важны и должны быть записаны в журнал.  Для этого можно использовать продолжения непосредственно для получения уведомления об асинхронном завершении задач:  
  
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
  
```  
private static async  void LogCompletionIfFailed(IEnumerable<Task> tasks)  
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
  
 Наконец, можно отменить все остальные операции:  
  
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
  
#### Чередование  
 Рассмотрим случай, когда нужно загрузить изображения из сети и произвести обработку каждого изображения \(например, добавление его к элементу управления пользовательского интерфейса\).  Необходимо выполнить обработку последовательно в потоке пользовательского интерфейса, но загрузка там, где возможно, должна осуществляться параллельно.  Кроме того, не следует удерживать добавление изображений в пользовательский интерфейс до тех пор, пока они все не загрузятся, а следует добавлять их после завершения:  
  
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
  
 Также можно применять чередование к сценарию, содержащему интенсивную обработку загруженных изображений в <xref:System.Threading.ThreadPool>, например:  
  
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
  
#### Регулирование  
 Рассмотрим пример использования чередования, за исключением такого случая, что пользователь загружает настолько большое количество изображений, что загрузки должны быть явно ограниченны.  Чтобы добиться этого, можно запустить подмножество асинхронных операций.  Например, когда операция завершается, дополнительная операция может быть запущена на ее месте:  
  
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
  
#### Ранняя аварийная остановка  
 Рассмотрим асинхронный режим ожидания завершения операции при одновременном отклике на пользовательский запрос отмены \(например, при нажатии на кнопку отмены\).  Следующий код иллюстрирует этот сценарий:  
  
```csharp  
private CancellationTokenSource m_cts;   
  
public void btnCancel_Click(object sender, EventArgs e)  
{  
    if (m_cts != null) m_cts.Cancel();  
}  
  
public async  void btnRun_Click(object sender, EventArgs e)  
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
  
private static async  Task UntilCompletionOrCancellation(  
    Task asyncOp, CancellationToken ct)  
{  
    var tcs = new TaskCompletionSource<bool>();  
    using(ct.Register(() => tcs.TrySetResult(true)))  
        await Task.WhenAny(asyncOp, tcs.Task);  
    return asyncOp;  
}  
  
```  
  
 Эта реализация заново включает пользовательский интерфейс, как только будет решено произвести аварийную остановку, но без отмены основных асинхронных операций.  Другим вариантом будет отмена ожидающих операций при решении произвести аварийную остановку, однако без использования восстановления пользовательского интерфейса до тех пор, пока не будут завершены операции, благодаря возможному раннему завершению, либо благодаря запросу на отмену:  
  
```csharp  
private CancellationTokenSource m_cts;  
  
public async  void btnRun_Click(object sender, EventArgs e)  
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
  
 Другой пример раннего аварийная остановка включает в себя использование метода <xref:System.Threading.Tasks.Task.WhenAny%2A> совместно с методом <xref:System.Threading.Tasks.Task.Delay%2A>, как описано в следующем разделе.  
  
### Task.Delay  
 Можно использовать метод <xref:System.Threading.Tasks.Task.Delay%2A> для вставки пауз в выполнение асинхронного метода.  Это полезно для различных функциональных возможностей, включая создание циклов опроса и задержки обработки пользовательского ввода на заданный интервал времени.  Метод <xref:System.Threading.Tasks.Task.Delay%2A> также может быть полезен в сочетании с <xref:System.Threading.Tasks.Task.WhenAny%2A> для реализации истечения времени ожидания.  
  
 Если задача, которая является частью большой асинхронной операции \(например: веб\-служба ASP.NET\), слишком долго завершается, время выполнения общей операции может снизиться, особенно если операция завершилась неудачей.  Поэтому важно иметь возможность устанавливать время ожидания для асинхронной операции.  Синхронные методы <xref:System.Threading.Tasks.Task.Wait%2A>, <xref:System.Threading.Tasks.Task.%2A> WaitAll?qualifyHint=False&autoUpgrade=True и <xref:System.Threading.Tasks.Task.%2A> WaitAny?qualifyHint=False&autoUpgrade=True принимают значения времени ожидания, но соответствующий метод <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A>\/<xref:System.Threading.Tasks.Task.WhenAny%2A>, ранее упомянутый <xref:System.Threading.Tasks.Task.WhenAll%2A> и  <xref:System.Threading.Tasks.Task.WhenAny%2A> \- нет.  Вместо этого можно использовать комбинацию <xref:System.Threading.Tasks.Task.Delay%2A> и <xref:System.Threading.Tasks.Task.WhenAny%2A> для реализации истечения времени ожидания.  
  
 Например, пусть в приложении с пользовательским интерфейсом нужно загрузить изображение и отключить пользовательский интерфейс на время, пока оно загружается.  Однако если загрузка занимает слишком много времени, то нужно повторно активировать пользовательский интерфейс и отменить загрузку:  
  
```csharp  
public async  void btnDownload_Click(object sender, EventArgs e)  
{  
    btnDownload.Enabled = false;  
    try  
    {  
        Task<Bitmap> download = GetBitmapAsync(url);  
        if (download == await Task.WhenAny(download, Task.Delay(3000)))  
        {  
            Bitmap bmp = await download;  
            pictureBox.Image = bmp;  
            status.Text = “Downloaded”;  
        }  
        else  
        {  
            pictureBox.Image = null;  
            status.Text = “Timed out”;  
            var ignored = download.ContinueWith(  
                t => Trace(“Task finally completed”));  
        }  
    }  
    finally { btnDownload.Enabled = true; }  
}  
  
```  
  
 Это тоже применяется к нескольким загрузкам, поскольку <xref:System.Threading.Tasks.Task.WhenAll%2A> возвращает задачу:  
  
```csharp  
public async  void btnDownload_Click(object sender, RoutedEventArgs e)  
{  
    btnDownload.Enabled = false;  
    try  
    {  
        Task<Bitmap[]> downloads =   
            Task.WhenAll(from url in urls select GetBitmapAsync(url));  
        if (downloads == await Task.WhenAny(downloads, Task.Delay(3000)))  
        {  
            foreach(var bmp in downloads) panel.AddImage(bmp);  
            status.Text = “Downloaded”;  
        }  
        else  
        {  
            status.Text = “Timed out”;  
            downloads.ContinueWith(t => Log(t));  
        }  
    }  
    finally { btnDownload.Enabled = true; }  
}  
  
```  
  
## Построение основанных на задачах комбинаторов  
 В результате возможности задачи полностью представлять асинхронную операцию и предоставлять синхронные и асинхронные возможности для соединения с операцией, извлекающей результаты и т. п., стало возможным создать полезные библиотеки комбинаторов, объединяющих задачи для построения больших шаблонов.  Как упоминалось в предыдущем разделе этого документа, платформа .NET Framework включает несколько встроенных комбинаторов, но можно создать собственные комбинаторы.  В следующих разделах приведены несколько примеров возможных методов и типов комбинаторов.  
  
### RetryOnFault  
 Во многих случаях может понадобиться повторить операцию, если предыдущая попытка завершается неудачей.  Для синхронного кода можно создать вспомогательный метод `RetryOnFault`, как показано в следующем примере:  
  
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
  
 Можно создать практически идентичный вспомогательный метод для асинхронных операций, которые реализован с применением TAP и, таким образом, вернуть задачи:  
  
```csharp  
public static async  Task<T> RetryOnFault<T>(  
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
  
 Затем можно использовать этот комбинатор для реализации повторных попыток в логике приложения; например:  
  
```csharp  
// Download the URL, trying up to three times in case of failure  
string pageContents = await RetryOnFault(  
    () => DownloadStringAsync(url), 3);  
  
```  
  
 Можно ещё более расширить функцию `RetryOnFault`.  Например, функция может принимать другой `Func<Task>`, который будет вызван между повторными попытками для определения момента, когда нужно попытаться выполнить операцию снова; например:  
  
```csharp  
public static async  Task<T> RetryOnFault<T>(  
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
  
 Можно использовать функцию следующим образом, для ожидания в течение секунды перед повторной попыткой выполнения операции:  
  
```csharp  
// Download the URL, trying up to three times in case of failure,  
// and delaying for a second between retries  
string pageContents = await RetryOnFault(  
    () => DownloadStringAsync(url), 3, () => Task.Delay(1000));  
  
```  
  
### NeedOnlyOne  
 Иногда можно воспользоваться преимуществами избыточности для уменьшения задержки и увеличения вероятности успешного завершения операции.  Рассмотрим несколько веб\-служб, которые обеспечивают биржевыми котировками, но в разное время дня каждая из служб может предоставлять различные уровни качества и различное время ответа.  Чтобы справится с такими колебаниями, можно обращаться с запросами ко всем веб\-службам и после получении ответа от одной отменить остальные запросы.  Можно реализовать вспомогательную функцию для упрощения реализации общего шаблона запуска нескольких операций, ожидания завершения одной из них, а затем отмены всех остальных.  Функция `NeedOnlyOne` в следующем примере демонстрирует этот сценарий:  
  
```csharp  
public static async  Task<T> NeedOnlyOne(  
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
  
 Можно использовать данную функцию следующим образом:  
  
```csharp  
double currentPrice = await NeedOnlyOne(  
    ct => GetCurrentPriceFromServer1Async(“msft”, ct),  
    ct => GetCurrentPriceFromServer2Async(“msft”, ct),  
    ct => GetCurrentPriceFromServer3Async(“msft”, ct));  
```  
  
### Операции с чередованием  
 Существует потенциальная проблема производительности с использованием метода <xref:System.Threading.Tasks.Task.WhenAny%2A> для поддержки сценария чередования при использовании очень больших наборов задач.  Каждый вызов <xref:System.Threading.Tasks.Task.WhenAny%2A> приводит к регистрировании продолжения для каждой задачи.  Для N задач, это приводит к O\(N2\) продолжений, созданных за время существования операцией чередования.  При работе с большим набором задач, можно использовать комбинатор \(`Interleaved` в следующем примере\), чтобы решить проблемы производительности:  
  
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
  
 Можно использовать комбинатор для обработки результатов задач при их завершении, например:  
  
```csharp  
IEnumerable<Task<int>> tasks = ...;  
foreach(var task in Interleaved(tasks))  
{  
    int result = await task;  
    …  
}  
```  
  
### WhenAllOrFirstException  
 В определенных сценариях разбрасывания\/сбора, может потребоваться ожидание всех задач в множестве, кроме законченных с ошибкой, ожидание которых необходимо прервать при возникновении исключения.  Это можно выполнить с помощью метода комбинатора, такого как `WhenAllOrFirstException` в следующем примере:  
  
```csharp  
public static Task<T[]> WhenAllOrFirstException<T>(IEnumerable<Task<T>> tasks)  
{  
    var inputs = tasks.ToList();  
    var ce = new CountdownEvent(inputs.Count);  
    var tcs = new TaskCompletionSource<T[]>();  
  
    Action<Task> onCompleted = (Task completed) =>  
    {  
        if (completed.IsFaulted)   
            tcs.TrySetException(completed.Exception.InnerExceptions);  
        if (ce.Signal() && !tcs.Task.IsCompleted)  
            tcs.TrySetResult(inputs.Select(t => t.Result).ToArray());  
    };  
  
    foreach (var t in inputs) t.ContinueWith(onCompleted);  
    return tcs.Task;  
}  
  
```  
  
## Построение основанных на задачах структур данных  
 В дополнение к возможности создания основанных на задачах комбинаторов, наличие структуры данных в <xref:System.Threading.Tasks.Task> и <xref:System.Threading.Tasks.Task%601>, которая представляет собой одновременно результаты асинхронной операции и необходимую синхронизации для их объединения, делает её очень мощным типом, на котором строятся пользовательские структуры данных для использования в асинхронных сценариях.  
  
### AsyncCache  
 Одним важным аспектом задачи является то, что она может быть передана нескольким потребителям, все из которых могут ожидать ее, регистрировать ее возобновления, получать ее результаты или исключения \(в случае <xref:System.Threading.Tasks.Task%601>\) и т. д.  Это делает <xref:System.Threading.Tasks.Task> и <xref:System.Threading.Tasks.Task%601> особенно подходящими для использования в асинхронной инфраструктуре кэширования.  Ниже представлен небольшой, но мощный асинхронный кэш, построенный на основе <xref:System.Threading.Tasks.Task%601>:  
  
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
  
 Класс [AsyncCache\<TKey,TValue\>](http://go.microsoft.com/fwlink/p/?LinkId=251941) принимает в качестве делегата в свой конструктор функцию, которая принимает `TKey` и возвращает <xref:System.Threading.Tasks.Task%601>.  Все предыдущие значения, к которым производится обращение из кэша хранятся во внутреннем словаре `AsyncCache`, гарантирующем, что только одна задача генерируется для каждого ключа, даже если поддерживается одновременный доступ к кэшу.  
  
 Например, можно создать кэш для загруженных веб\-страниц:  
  
```csharp  
private AsyncCache<string,string> m_webPages =   
    new AsyncCache<string,string>(DownloadStringAsync);  
  
```  
  
 Этот кэш можно использовать в асинхронных методах, когда требуется содержимое веб\-страницы.  Класс `AsyncCache` гарантирует загрузку как можно меньшего числа страниц и кэширует результаты.  
  
```csharp  
private async  void btnDownload_Click(object sender, RoutedEventArgs e)   
{  
    btnDownload.IsEnabled = false;  
    try  
    {  
        txtContents.Text = await m_webPages["http://www.microsoft.com"];  
    }  
    finally { btnDownload.IsEnabled = true; }  
}  
  
```  
  
### AsyncProducerConsumerCollection  
 Можно также использовать задачи для создания структур данных для координации асинхронных действий.  Рассмотрим один из классических параллельных шаблонов разработки: производитель\/потребитель.  В этом шаблоне производители создают данные, которые используются потребителями, причем производители и потребители могут выполняться параллельно.  Например, потребитель обрабатывает предмет 1, который был сгенерирован производителем, в данный момент создающим предмет 2. Для шаблона производитель\/потребитель вам в любом случае нужна некоторая структура данных, в которой будут храниться объекты, созданные производителем, таким образом, чтобы потребитель мог быть извещен о новых данных и мог получить к ним доступ.  
  
 Ниже приведена простая структура данных, построенная на основе задач, которая делает доступными асинхронные методы, используемые в качестве потребителей и производителей:  
  
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
  
 Используя эту структуру данных, можно написать следующий код:  
  
```csharp  
private static AsyncProducerConsumerCollection<int> m_data = …;  
…  
private static async  Task ConsumerAsync()  
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
  
 Пространство имен <xref:System.Threading.Tasks.Dataflow> включает тип <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>, который можно использовать таким же образом, но без построения пользовательского типа коллекции:  
  
```csharp  
private static BufferBlock<int> m_data = …;  
…  
private static async  Task ConsumerAsync()  
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
>  Пространство имен <xref:System.Threading.Tasks.Dataflow> доступно в [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] через **NuGet**.  Для установки сборки, содержащей пространство имен <xref:System.Threading.Tasks.Dataflow>, откройте проект в [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], выберите **Управление пакетами NuGet** из меню проекта и найдите пакет Microsoft.Tpl.Dataflow в Интернете.  
  
## См. также  
 [Task\-based Asynchronous Pattern \(TAP\)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)   
 [Implementing the Task\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/implementing-the-task-based-asynchronous-pattern.md)   
 [Interop with Other Asynchronous Patterns and Types](../../../docs/standard/asynchronous-programming-patterns/interop-with-other-asynchronous-patterns-and-types.md)