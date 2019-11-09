---
title: Перенос служб дуплексной службы WCF в gRPC-gRPC для разработчиков WCF
description: Узнайте, как перенести различные формы службы двусторонней передачи данных WCF в gRPC Streaming Services.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 1702c9f7659f056af9009e81847f28c6e65b277c
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841483"
---
# <a name="migrate-wcf-duplex-services-to-grpc"></a>Перенос дуплексных служб WCF в gRPC

Теперь, когда основные понятия есть, в этом разделе рассматриваются более сложные *потоковые* gRPC службы.

Существует несколько способов использования дуплексных служб в Windows Communication Foundation (WCF). Некоторые службы инициируются клиентом, а затем потоковая передача данных с сервера. Другие Дуплексные службы могут потребовать более интерактивного двустороннего взаимодействия, такого как классический пример калькулятора из документации по WCF. В этой главе вы получите две возможные реализации WCF "биржевые котировки" и перенесите их в gRPC: один использует потоковую передачу RPC на сервере, а другой — через двунаправленный потоковую передачу RPC.

## <a name="server-streaming-rpc"></a>Потоковая передача RPC сервера

В [примере решения WCF симплестокктиккер](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/SimpleStockTickerSample/wcf/SimpleStockTicker), *симплестоккприцетиккер*, существует дуплексная служба, в которой клиент запускает подключение со списком стандартных символов, а сервер использует *интерфейс обратного вызова* для отправки обновлений по мере их появления. Клиент реализует этот интерфейс для реагирования на вызовы с сервера.

### <a name="the-wcf-solution"></a>Решение WCF

Решение WCF реализуется как саморазмещаемый сервер NetTCP в консольном приложении .NET Framework 4. x.

#### <a name="the-servicecontract"></a>ServiceContract

```csharp
[ServiceContract(SessionMode = SessionMode.Required, CallbackContract = typeof(ISimpleStockTickerCallback))]
public interface ISimpleStockTickerService
{
    [OperationContract(IsOneWay = true)]
    void Subscribe(string[] symbols);
}
```

Служба имеет один метод без типа возвращаемого значения, так как он будет использовать интерфейс обратного вызова `ISimpleStockTickerCallback` для отправки данных клиенту в режиме реального времени.

#### <a name="the-callback-interface"></a>Интерфейс обратного вызова

```csharp
[ServiceContract]
public interface ISimpleStockTickerCallback
{
    [OperationContract(IsOneWay = true)]
    void Update(string symbol, decimal price);
}
```

Реализации этих интерфейсов можно найти в решении, а также с фиктивными внешними зависимостями для предоставления тестовых данных.

### <a name="grpc-streaming"></a>Потоковая передача gRPC

GRPC способ обработки данных в режиме реального времени отличается. Вызов от клиента к серверу может создать постоянный поток, который можно отслеживать для сообщений, поступающих в асинхронный режим. Несмотря на различие, потоки могут быть более интуитивно понятным способом работы с этими данными и более актуальны в современном программировании с акцентом на LINQ, реактивные потоки, функциональное программирование и т. д.

Определение службы должно иметь два сообщения: одно для запроса и одно для потока. Служба возвращает поток сообщения `StockTickerUpdate` с помощью ключевого слова `stream` в объявлении `return`. Рекомендуется добавить `Timestamp` к обновлению, чтобы отобразить точное время изменения цены.

#### <a name="simple_stock_tickerproto"></a>simple_stock_ticker.

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.SimpleStockTickerServer.Protos";

import "google/protobuf/timestamp.proto";

package SimpleStockTickerServer;

service SimpleStockTicker {
  rpc Subscribe (SubscribeRequest) returns (stream StockTickerUpdate);
}

message SubscribeRequest {
  repeated string symbols = 1;
}

message StockTickerUpdate {
  string symbol = 1;
  int32 price_cents = 2;
  google.protobuf.Timestamp time = 3;
}
```

### <a name="implement-the-simplestockticker"></a>Реализация Симплестокктиккер

Повторно используйте имитацию `StockPriceSubscriber` из проекта WCF, скопировав три класса из библиотеки классов `TraderSys.StockMarket` в новую библиотеку классов .NET Standard в целевом решении. Чтобы лучше следовать рекомендациям, добавьте тип `Factory` для создания экземпляров и зарегистрируйте `IStockPriceSubscriberFactory` с помощью ASP.NET Core служб внедрения зависимостей.

#### <a name="the-factory-implementation"></a>Реализация фабрики

```csharp
public interface IStockPriceSubscriberFactory
{
    IStockPriceSubscriber GetSubscriber(string[] symbols);
}

public class StockPriceSubscriberFactory : IStockPriceSubscriberFactory
{
    public IStockPriceSubscriber GetSubscriber(string[] symbols)
    {
        return new StockPriceSubscriber(symbols);
    }
}
```

#### <a name="registering-the-factory"></a>Регистрация фабрики

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddGrpc();
    services.AddSingleton<IStockPriceSubscriberFactory, StockPriceSubscriberFactory>();
}
```

Теперь этот класс можно использовать для реализации службы gRPC Стокктиккер.

#### <a name="stocktickerservicecs"></a>StockTickerService.cs

```csharp
public class StockTickerService : Protos.SimpleStockTicker.SimpleStockTickerBase
{
    private readonly IStockPriceSubscriberFactory _subscriberFactory;

    public StockTickerService(IStockPriceSubscriberFactory subscriberFactory)
    {
        _subscriberFactory = subscriberFactory;
    }

    public override async Task Subscribe(SubscribeRequest request, IServerStreamWriter<StockTickerUpdate> responseStream, ServerCallContext context)
    {
        var subscriber = _subscriberFactory.GetSubscriber(request.Symbols.ToArray());

        subscriber.Update += async (sender, args) =>
            await WriteUpdateAsync(responseStream, args.Symbol, args.Price);

        await AwaitCancellation(context.CancellationToken);
    }

    private async Task WriteUpdateAsync(IServerStreamWriter<StockTickerUpdate> stream, string symbol, decimal price)
    {
        try
        {
            await stream.WriteAsync(new StockTickerUpdate
            {
                Symbol = symbol,
                PriceCents = (int)(price * 100),
                Time = Timestamp.FromDateTimeOffset(DateTimeOffset.UtcNow)
            });
        }
        catch (Exception e)
        {
            // Handle any errors due to broken connection etc.
            _logger.LogError($"Failed to write message: {e.Message}");
        }
    }

    private static Task AwaitCancellation(CancellationToken token)
    {
        var completion = new TaskCompletionSource<object>();
        token.Register(() => completion.SetResult(null));
        return completion.Task;
    }
}
```

Как видите, хотя объявление в файле `.proto` говорит, что метод возвращает поток `StockTickerUpdate` сообщений, на самом деле он возвращает `Task`обычный. Задание создания потока обрабатывается созданным кодом и библиотеками среды выполнения gRPC, которые предоставляют поток ответов `IServerStreamWriter<StockTickerUpdate>`, готовый к использованию.

В отличие от двусторонней службы WCF, где экземпляр класса службы хранится в активном состоянии при открытом соединении, служба gRPC использует возвращенную задачу для поддержания активности службы. Задача не должна завершаться, пока соединение не будет закрыто.

Служба может определить, когда клиент закрыл подключение, используя `CancellationToken` из `ServerCallContext`. Простой статический метод, `AwaitCancellation`, используется для создания задачи, которая завершается при отмене маркера.

В методе `Subscribe` получите `StockPriceSubscriber` и добавьте обработчик событий, записывающий данные в поток ответа. Затем дождитесь закрытия соединения, прежде чем немедленно выпустить `subscriber`, чтобы предотвратить попытку записи данных в закрытый поток.

Метод `WriteUpdateAsync` имеет `try`/`catch`, обрабатывающий ошибки, которые могут возникнуть при записи сообщения в поток. Это важное обстоятельство в постоянных подключениях по сетям, которые могут быть нарушены в любой миллисекунде, независимо от того, есть ли проблема в любом случае.

### <a name="using-the-stocktickerservice-from-a-client-application"></a>Использование Стокктиккерсервице из клиентского приложения

Выполните те же действия из предыдущего раздела, чтобы создать общую библиотеку классов клиента из файла `.proto`. В этом примере имеется консольное приложение .NET Core 3,0, которое демонстрирует использование клиента.

#### <a name="example-programcs"></a>Пример Program.cs

```csharp
class Program
{
    static async Task Main(string[] args)
    {
        using var channel = GrpcChannel.ForAddress("https://localhost:5001");
        var client = new SimpleStockTicker.SimpleStockTickerClient(channel);

        var request = new SubscribeRequest();
        request.Symbols.AddRange(args);

        using var stream = client.Subscribe(request);

        var tokenSource = new CancellationTokenSource();

        var task = DisplayAsync(stream.ResponseStream, tokenSource.Token);

        WaitForExitKey();

        tokenSource.Cancel();
        await task;
    }
}
```

В этом случае метод `Subscribe` на созданном клиенте не является асинхронным. Поток создается и пригоден к использованию, так как его `MoveNext`ный метод является асинхронным и при первом вызове он не будет выполнен до тех пор, пока соединение не будет активно.

Поток передается асинхронному `DisplayAsync` методу. Затем приложение ожидает нажатия пользователем клавиши, затем отменяет `DisplayAsync` метод и ожидает завершения задачи перед выходом.

> [!NOTE]
> Этот код использует новый C# 8-я объявление с использованием синтаксиса для удаления потока и канала при выходе из метода `Main`. Это небольшое изменение, но хорошо, что сокращает отступы и пустые строки.

#### <a name="consume-the-stream"></a>Использование потока

WCF использует интерфейсы обратного вызова, чтобы разрешить серверу вызывать методы непосредственно на клиенте. потоки gRPC работают по-разному. Клиент проходит по возвращенному потоку и обрабатывает сообщения так, как будто они были возвращены из локального метода, возвращающего `IEnumerable`.

Тип `IAsyncStreamReader<T>` работает примерно так же, как `IEnumerator<T>`: существует метод `MoveNext`, возвращающий значение true, если имеется больше данных, и свойство `Current`, возвращающее Последнее значение. Единственное отличие заключается в том, что метод `MoveNext` возвращает `Task<bool>`, а не только `bool`. Метод расширения `ReadAllAsync` создает оболочку для потока в стандартном C# 8 `IAsyncEnumerable`, который можно использовать с новым синтаксисом `await foreach`.

```csharp
static async Task DisplayAsync(IAsyncStreamReader<StockTickerUpdate> stream, CancellationToken token)
{
    try
    {
        await foreach (var update in stream.ReadAllAsync(token))
        {
            Console.WriteLine($"{update.Symbol}: {update.Price}");
        }
    }
    catch (RpcException e) when (e.StatusCode == StatusCode.Cancelled)
    {
        return;
    }
    catch (OperationCanceledException)
    {
        Console.WriteLine("Finished.");
    }
}
```

> [!TIP]
> В разделе о [клиентских библиотеках](client-libraries.md#iobservable) в конце этой главы рассматривается добавление метода расширения и классов для переноса `IAsyncStreamReader<T>` в `IObservable<T>` для разработчиков, использующих реактивные шаблоны программирования.

Опять же, перехватите исключения, так как это может привести к сбою в работе сети, а также <xref:System.OperationCanceledException>, которые неизбежно будут вызываться, так как код использует <xref:System.Threading.CancellationToken> для разбиения цикла. Тип `RpcException` имеет много полезной информации об ошибках среды выполнения gRPC, включая `StatusCode`. Дополнительные сведения см. в разделе [ *Обработка ошибок* в главе 4](error-handling.md).

## <a name="bidirectional-streaming"></a>Двунаправленная потоковая передача

Высокодуплексная служба WCF обеспечивает асинхронный обмен сообщениями в режиме реального времени в обоих направлениях. В примере потоковой передачи сервера клиент запускает запрос, а затем получает поток обновлений. Более новая версия этой службы позволит клиенту добавлять и удалять акции из списка без необходимости приостанавливаться и создавать новую подписку. Эта функциональность реализована в [примере решения фуллстокктиккер](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/wcf/FullStockTicker).

Интерфейс `IFullStockTickerService` предоставляет три метода:

- `Subscribe` запускает подключение.
- `AddSymbol` добавляет символ акции для просмотра.
- `RemoveSymbol` удаляет символ из наблюдаемого списка.

```csharp
[ServiceContract(SessionMode = SessionMode.Required, CallbackContract = typeof(IFullStockTickerCallback))]
public interface IFullStockTickerService
{
    [OperationContract(IsOneWay = true)]
    void Subscribe();

    [OperationContract(IsOneWay = true)]
    void AddSymbol(string symbol);

    [OperationContract(IsOneWay = true)]
    void RemoveSymbol(string symbol);
}
```

Интерфейс обратного вызова остается прежним.

Реализация этого шаблона в gRPC менее проста, так как теперь существует два потока данных с передачей сообщений: от клиента к серверу и от сервера к клиенту. Невозможно использовать несколько методов для реализации операции добавления и удаления, но в одном потоке можно передать более одного типа сообщений, используя либо `Any` тип, либо `oneof` ключевое слово, которые были описаны в [главе 3](protobuf-any-oneof.md).

В случае, когда существует конкретный набор допустимых типов, `oneof` является лучшим способом. Используйте `ActionMessage`, который может содержать либо `AddSymbolRequest`, либо `RemoveSymbolRequest`.

```protobuf
message ActionMessage {
  oneof action {
    AddSymbolRequest add = 1;
    RemoveSymbolRequest remove = 2;
  }
}

message AddSymbolRequest {
  string symbol = 1;
}

message RemoveSymbolRequest {
  string symbol = 1;
}
```

Объявите двунаправленную службу потоковой передачи, которая принимает поток `ActionMessage` сообщений.

```protobuf
service FullStockTicker {
  rpc Subscribe (stream ActionMessage) returns (stream StockTickerUpdate);
}
```

Реализация для этой службы аналогична предыдущему примеру, за исключением того, что первый параметр метода `Subscribe` теперь является `IAsyncStreamReader<ActionMessage>`, который можно использовать для обработки запросов `Add` и `Remove`.

```csharp
public override async Task Subscribe(IAsyncStreamReader<ActionMessage> requestStream, IServerStreamWriter<StockTickerUpdate> responseStream, ServerCallContext context)
{
    using var subscriber = _subscriberFactory.GetSubscriber();

    subscriber.Update += async (sender, args) =>
        await WriteUpdateAsync(responseStream, args.Symbol, args.Price);

    var actionsTask = HandleActions(requestStream, subscriber, context.CancellationToken);

    _logger.LogInformation("Subscription started.");
    await AwaitCancellation(context.CancellationToken);

    try { await actionsTask; } catch { /* Ignored */ }

    _logger.LogInformation("Subscription finished.");
}

private async Task WriteUpdateAsync(IServerStreamWriter<StockTickerUpdate> stream, string symbol, decimal price)
{
    try
    {
        await stream.WriteAsync(new StockTickerUpdate
        {
            Symbol = symbol,
            PriceCents = (int)(price * 100),
            Time = Timestamp.FromDateTimeOffset(DateTimeOffset.UtcNow)
        });
    }
    catch (Exception e)
    {
        // Handle any errors due to broken connection etc.
        _logger.LogError($"Failed to write message: {e.Message}");
    }
}

private static Task AwaitCancellation(CancellationToken token)
{
    var completion = new TaskCompletionSource<object>();
    token.Register(() => completion.SetResult(null));
    return completion.Task;
}
```

Класс `ActionMessage`, который gRPC был создан для нас, гарантирует, что только одно из свойств `Add` и `Remove` можно задать, и найти, какой именно из них `null` является допустимым способом определения того, какой тип сообщения используется, но есть и лучший способ. Создание кода также создает `enum ActionOneOfCase` в классе `ActionMessage`, который выглядит следующим образом:

```csharp
public enum ActionOneofCase {
    None = 0,
    Add = 1,
    Remove = 2,
}
```

Свойство, `ActionCase`ное для объекта `ActionMessage`, можно использовать с инструкцией `switch`, чтобы определить, какое поле задается.

```csharp
private async Task HandleActions(IAsyncStreamReader<ActionMessage> requestStream, IFullStockPriceSubscriber subscriber, CancellationToken token)
{
    await foreach (var action in requestStream.ReadAllAsync(token))
    {
        switch (action.ActionCase)
        {
            case ActionMessage.ActionOneofCase.None:
                _logger.LogWarning("No Action specified.");
                break;
            case ActionMessage.ActionOneofCase.Add:
                subscriber.Add(action.Add.Symbol);
                break;
            case ActionMessage.ActionOneofCase.Remove:
                subscriber.Remove(action.Remove.Symbol);
                break;
            default:
                _logger.LogWarning($"Unknown Action '{action.ActionCase}'.");
                break;
        }
    }
}
```

> [!TIP]
> В инструкции `switch` имеется `default` регистр, который регистрирует предупреждение при обнаружении неизвестного значения `ActionOneOfCase`. Это может быть полезно в том случае, если клиент использует более позднюю версию файла `.proto`, который добавил дополнительные действия. Это одна из причин того, что использование `switch` лучше, чем тестирование `null` на известных полях.

### <a name="use-the-fullstocktickerservice-from-a-client-application"></a>Использование Фуллстокктиккерсервице из клиентского приложения

Для демонстрации использования этого более сложного клиента используется простое приложение WPF .NET Core 3,0. Полное приложение можно найти на сайте [GitHub](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTicker).

Клиент используется в классе `MainWindowViewModel`, который получает экземпляр типа `FullStockTicker.FullStockTickerClient` из внедрения зависимостей.

```csharp
public class MainWindowViewModel : IAsyncDisposable, INotifyPropertyChanged
{
    private readonly FullStockTicker.FullStockTickerClient _client;
    private readonly AsyncDuplexStreamingCall<ActionMessage, StockTickerUpdate> _duplexStream;
    private readonly CancellationTokenSource _cancellationTokenSource;
    private readonly Task _responseTask;
    private string _addSymbol;

    public MainWindowViewModel(FullStockTicker.FullStockTickerClient client)
    {
        _cancellationTokenSource = new CancellationTokenSource();
        _client = client;
        _duplexStream = _client.Subscribe();
        _responseTask = HandleResponsesAsync(_cancellationTokenSource.Token);

        AddCommand = new AsyncCommand(Add, CanAdd);
    }
```

Объект, возвращаемый методом `client.Subscribe()`, теперь является экземпляром типа библиотеки gRPC `AsyncDuplexStreamingCall<TRequest, TResponse>`, который предоставляет `RequestStream` для отправки запросов на сервер, а также `ResponseStream` для обработки ответов.

Поток запроса используется из некоторых методов `ICommand` WPF для добавления и удаления символов. Для каждой операции задайте соответствующее поле для объекта `ActionMessage`.

```csharp
private async Task Add()
{
    if (CanAdd())
    {
        await _duplexStream.RequestStream.WriteAsync(new ActionMessage {Add = new AddSymbolRequest {Symbol = AddSymbol}});
    }
}

public async Task Remove(PriceViewModel priceViewModel)
{
    await _duplexStream.RequestStream.WriteAsync(new ActionMessage {Remove = new RemoveSymbolRequest {Symbol = priceViewModel.Symbol}});
    Prices.Remove(priceViewModel);
}
```

> [!IMPORTANT]
> При установке значения поля `oneof` в сообщении автоматически очищаются все ранее установленные поля.

Поток ответов обрабатывается в методе `async`, а `Task` возвращаемого объекта удерживается для удаления при закрытии окна.

```csharp
private async Task HandleResponsesAsync(CancellationToken token)
{
    var stream = _duplexStream.ResponseStream;

    try
    {
        await foreach (var update in stream.ReadAllAsync(token))
        {
            var price = Prices.FirstOrDefault(p => p.Symbol.Equals(update.Symbol));
            if (price == null)
            {
                price = new PriceViewModel(this) {Symbol = update.Symbol, Price = update.PriceCents / 100m};
                Prices.Add(price);
            }
            else
            {
                price.Price = update.PriceCents / 100m;
            }
        }
    }
    catch (OperationCancelledException) { }
}
```

### <a name="client-clean-up"></a>Очистка клиента

Когда окно закрывается и `MainWindowViewModel` удаляется (из `Closed` события `MainWindow`), рекомендуется правильно ликвидировать объект `AsyncDuplexStreamingCall`. В частности, для корректного закрытия потока на сервере необходимо вызвать метод `CompleteAsync` в `RequestStream`. В следующем примере показан метод `DisposeAsync` из примера представления-модели:

```csharp
public ValueTask DisposeAsync()
{
    try
    {
        await _duplexStream.RequestStream.CompleteAsync().ConfigureAwait(false);
        await _responseTask.ConfigureAwait(false);
    }
    finally
    {
        _duplexStream.Dispose();
    }
}
```

Закрытие потоков запросов позволяет серверу своевременно удалять собственные ресурсы. Это повышает эффективность и масштабируемость служб и предотвращает исключения.

>[!div class="step-by-step"]
>[Назад](migrate-request-reply.md)
>[Вперед](streaming-versus-repeated.md)
