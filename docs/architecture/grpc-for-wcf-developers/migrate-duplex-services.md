---
title: Перенос служб дуплексной службы WCF в gRPC-gRPC для разработчиков WCF
description: Узнайте, как перенести различные формы службы двусторонней передачи данных WCF в gRPC Streaming Services.
ms.date: 09/02/2019
ms.openlocfilehash: e2248df20e5c2d8f96055d42ba684749251154bd
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971871"
---
# <a name="migrate-wcf-duplex-services-to-grpc"></a><span data-ttu-id="63cdb-103">Перенос дуплексных служб WCF в gRPC</span><span class="sxs-lookup"><span data-stu-id="63cdb-103">Migrate WCF duplex services to gRPC</span></span>

<span data-ttu-id="63cdb-104">Теперь, когда основные понятия есть, в этом разделе рассматриваются более сложные *потоковые* gRPC службы.</span><span class="sxs-lookup"><span data-stu-id="63cdb-104">Now that the basic concepts are in place, this section will look at the more complicated *streaming* gRPC services.</span></span>

<span data-ttu-id="63cdb-105">Существует несколько способов использования дуплексных служб в Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="63cdb-105">There are multiple ways to use duplex services in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="63cdb-106">Некоторые службы инициируются клиентом, а затем потоковая передача данных с сервера.</span><span class="sxs-lookup"><span data-stu-id="63cdb-106">Some services are initiated by the client and then they stream data from the server.</span></span> <span data-ttu-id="63cdb-107">Другие Дуплексные службы могут потребовать более интерактивного двустороннего взаимодействия, такого как классический пример калькулятора из документации по WCF.</span><span class="sxs-lookup"><span data-stu-id="63cdb-107">Other full-duplex services might involve more ongoing two-way communication like the classic "Calculator" example from the WCF documentation.</span></span> <span data-ttu-id="63cdb-108">В этой главе вы получите две возможные реализации WCF "биржевые котировки" и перенесите их в gRPC: один использует потоковую передачу RPC на сервере, а другой — через двунаправленный потоковую передачу RPC.</span><span class="sxs-lookup"><span data-stu-id="63cdb-108">This chapter will take two possible WCF "Stock Ticker" implementations and migrate them to gRPC: one using a server streaming RPC, and the other one using a bidirectional streaming RPC.</span></span>

## <a name="server-streaming-rpc"></a><span data-ttu-id="63cdb-109">Потоковая передача RPC сервера</span><span class="sxs-lookup"><span data-stu-id="63cdb-109">Server streaming RPC</span></span>

<span data-ttu-id="63cdb-110">В [примере решения WCF симплестокктиккер](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/SimpleStockTickerSample/wcf/SimpleStockTicker), *симплестоккприцетиккер*, существует дуплексная служба, в которой клиент запускает подключение со списком стандартных символов, а сервер использует *интерфейс обратного вызова* для отправки обновлений по мере их появления.</span><span class="sxs-lookup"><span data-stu-id="63cdb-110">In the [sample SimpleStockTicker WCF solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/SimpleStockTickerSample/wcf/SimpleStockTicker), *SimpleStockPriceTicker*, there's a duplex service where the client starts the connection with a list of stock symbols, and the server uses the *callback interface* to send updates as they become available.</span></span> <span data-ttu-id="63cdb-111">Клиент реализует этот интерфейс для реагирования на вызовы с сервера.</span><span class="sxs-lookup"><span data-stu-id="63cdb-111">The client implements that interface to respond to calls from the server.</span></span>

### <a name="the-wcf-solution"></a><span data-ttu-id="63cdb-112">Решение WCF</span><span class="sxs-lookup"><span data-stu-id="63cdb-112">The WCF solution</span></span>

<span data-ttu-id="63cdb-113">Решение WCF реализуется как саморазмещаемый сервер NetTCP в консольном приложении .NET Framework 4. x.</span><span class="sxs-lookup"><span data-stu-id="63cdb-113">The WCF solution is implemented as a self-hosted NetTCP server in a .NET Framework 4.x console application.</span></span>

#### <a name="the-servicecontract"></a><span data-ttu-id="63cdb-114">ServiceContract</span><span class="sxs-lookup"><span data-stu-id="63cdb-114">The ServiceContract</span></span>

```csharp
[ServiceContract(SessionMode = SessionMode.Required, CallbackContract = typeof(ISimpleStockTickerCallback))]
public interface ISimpleStockTickerService
{
    [OperationContract(IsOneWay = true)]
    void Subscribe(string[] symbols);
}
```

<span data-ttu-id="63cdb-115">Служба имеет один метод без типа возвращаемого значения, так как он будет использовать интерфейс обратного вызова `ISimpleStockTickerCallback` для отправки данных клиенту в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="63cdb-115">The service has a single method with no return type, because it will be using the callback interface `ISimpleStockTickerCallback` to send data to the client in real time.</span></span>

#### <a name="the-callback-interface"></a><span data-ttu-id="63cdb-116">Интерфейс обратного вызова</span><span class="sxs-lookup"><span data-stu-id="63cdb-116">The callback interface</span></span>

```csharp
[ServiceContract]
public interface ISimpleStockTickerCallback
{
    [OperationContract(IsOneWay = true)]
    void Update(string symbol, decimal price);
}
```

<span data-ttu-id="63cdb-117">Реализации этих интерфейсов можно найти в решении, а также с фиктивными внешними зависимостями для предоставления тестовых данных.</span><span class="sxs-lookup"><span data-stu-id="63cdb-117">The implementations of these interfaces can be found in the solution, along with faked external dependencies to provide test data.</span></span>

### <a name="grpc-streaming"></a><span data-ttu-id="63cdb-118">Потоковая передача gRPC</span><span class="sxs-lookup"><span data-stu-id="63cdb-118">gRPC streaming</span></span>

<span data-ttu-id="63cdb-119">GRPC способ обработки данных в режиме реального времени отличается.</span><span class="sxs-lookup"><span data-stu-id="63cdb-119">The gRPC way of handling real-time data is different.</span></span> <span data-ttu-id="63cdb-120">Вызов от клиента к серверу может создать постоянный поток, который можно отслеживать для сообщений, поступающих в асинхронный режим.</span><span class="sxs-lookup"><span data-stu-id="63cdb-120">A call from client to server can create a persistent stream, which can be monitored for messages arriving asynchronously.</span></span> <span data-ttu-id="63cdb-121">Несмотря на различие, потоки могут быть более интуитивно понятным способом работы с этими данными и более актуальны в современном программировании с акцентом на LINQ, реактивные потоки, функциональное программирование и т. д.</span><span class="sxs-lookup"><span data-stu-id="63cdb-121">Despite the difference, streams can be a more intuitive way of dealing with this data and are more relevant in modern programming with the emphasis on LINQ, Reactive Streams, functional programming, and so on.</span></span>

<span data-ttu-id="63cdb-122">Определение службы должно иметь два сообщения: одно для запроса и одно для потока.</span><span class="sxs-lookup"><span data-stu-id="63cdb-122">The service definition needs two messages: one for the request, and one for the stream.</span></span> <span data-ttu-id="63cdb-123">Служба возвращает поток сообщения `StockTickerUpdate` с помощью ключевого слова `stream` в объявлении `return`.</span><span class="sxs-lookup"><span data-stu-id="63cdb-123">The service returns a stream of the `StockTickerUpdate` message using the `stream` keyword in its `return` declaration.</span></span> <span data-ttu-id="63cdb-124">Рекомендуется добавить `Timestamp` к обновлению, чтобы отобразить точное время изменения цены.</span><span class="sxs-lookup"><span data-stu-id="63cdb-124">It's recommended that you add a `Timestamp` to the update to show the exact time the price changed.</span></span>

#### <a name="simple_stock_tickerproto"></a><span data-ttu-id="63cdb-125">simple_stock_ticker.</span><span class="sxs-lookup"><span data-stu-id="63cdb-125">simple_stock_ticker.proto</span></span>

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

### <a name="implement-the-simplestockticker"></a><span data-ttu-id="63cdb-126">Реализация Симплестокктиккер</span><span class="sxs-lookup"><span data-stu-id="63cdb-126">Implement the SimpleStockTicker</span></span>

<span data-ttu-id="63cdb-127">Повторно используйте имитацию `StockPriceSubscriber` из проекта WCF, скопировав три класса из библиотеки классов `TraderSys.StockMarket` в новую библиотеку классов .NET Standard в целевом решении.</span><span class="sxs-lookup"><span data-stu-id="63cdb-127">Reuse the fake `StockPriceSubscriber` from the WCF project by copying the three classes from the `TraderSys.StockMarket` class library into a new .NET Standard class library in the target solution.</span></span> <span data-ttu-id="63cdb-128">Чтобы лучше следовать рекомендациям, добавьте тип `Factory` для создания экземпляров и зарегистрируйте `IStockPriceSubscriberFactory` с помощью ASP.NET Core служб внедрения зависимостей.</span><span class="sxs-lookup"><span data-stu-id="63cdb-128">To better follow best practices, add a `Factory` type to create instances of it and register the `IStockPriceSubscriberFactory` with ASP.NET Core's dependency injection services.</span></span>

#### <a name="the-factory-implementation"></a><span data-ttu-id="63cdb-129">Реализация фабрики</span><span class="sxs-lookup"><span data-stu-id="63cdb-129">The factory implementation</span></span>

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

#### <a name="registering-the-factory"></a><span data-ttu-id="63cdb-130">Регистрация фабрики</span><span class="sxs-lookup"><span data-stu-id="63cdb-130">Registering the factory</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddGrpc();
    services.AddSingleton<IStockPriceSubscriberFactory, StockPriceSubscriberFactory>();
}
```

<span data-ttu-id="63cdb-131">Теперь этот класс можно использовать для реализации службы gRPC Стокктиккер.</span><span class="sxs-lookup"><span data-stu-id="63cdb-131">Now, this class can be used to implement the gRPC StockTicker service.</span></span>

#### <a name="stocktickerservicecs"></a><span data-ttu-id="63cdb-132">StockTickerService.cs</span><span class="sxs-lookup"><span data-stu-id="63cdb-132">StockTickerService.cs</span></span>

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

<span data-ttu-id="63cdb-133">Как видите, хотя объявление в файле `.proto` говорит, что метод возвращает поток `StockTickerUpdate` сообщений, на самом деле он возвращает `Task`обычный.</span><span class="sxs-lookup"><span data-stu-id="63cdb-133">As you can see, although the declaration in the `.proto` file says the method "returns" a stream of `StockTickerUpdate` messages, in fact it returns a vanilla `Task`.</span></span> <span data-ttu-id="63cdb-134">Задание создания потока обрабатывается созданным кодом и библиотеками среды выполнения gRPC, которые предоставляют поток ответов `IServerStreamWriter<StockTickerUpdate>`, готовый к использованию.</span><span class="sxs-lookup"><span data-stu-id="63cdb-134">The job of creating the stream is handled by the generated code and the gRPC runtime libraries, which provide the `IServerStreamWriter<StockTickerUpdate>` response stream, ready to use.</span></span>

<span data-ttu-id="63cdb-135">В отличие от двусторонней службы WCF, где экземпляр класса службы хранится в активном состоянии при открытом соединении, служба gRPC использует возвращенную задачу для поддержания активности службы.</span><span class="sxs-lookup"><span data-stu-id="63cdb-135">Unlike a WCF duplex service, where the instance of the service class is kept alive while the connection is open, the gRPC service uses the returned Task to keep the service alive.</span></span> <span data-ttu-id="63cdb-136">Задача не должна завершаться, пока соединение не будет закрыто.</span><span class="sxs-lookup"><span data-stu-id="63cdb-136">The Task shouldn't complete until the connection is closed.</span></span>

<span data-ttu-id="63cdb-137">Служба может определить, когда клиент закрыл подключение, используя `CancellationToken` из `ServerCallContext`.</span><span class="sxs-lookup"><span data-stu-id="63cdb-137">The service can tell when the client has closed the connection by using the `CancellationToken` from the `ServerCallContext`.</span></span> <span data-ttu-id="63cdb-138">Простой статический метод, `AwaitCancellation`, используется для создания задачи, которая завершается при отмене маркера.</span><span class="sxs-lookup"><span data-stu-id="63cdb-138">A simple static method, `AwaitCancellation`, is used to create a Task that completes when the token is canceled.</span></span>

<span data-ttu-id="63cdb-139">В методе `Subscribe` получите `StockPriceSubscriber` и добавьте обработчик событий, записывающий данные в поток ответа.</span><span class="sxs-lookup"><span data-stu-id="63cdb-139">In the `Subscribe` method, then, get a `StockPriceSubscriber` and add an event handler that writes to the response stream.</span></span> <span data-ttu-id="63cdb-140">Затем дождитесь закрытия соединения, прежде чем немедленно выпустить `subscriber`, чтобы предотвратить попытку записи данных в закрытый поток.</span><span class="sxs-lookup"><span data-stu-id="63cdb-140">Then wait for the connection to be closed, before immediately disposing the `subscriber` to prevent it trying to write data to the closed stream.</span></span>

<span data-ttu-id="63cdb-141">Метод `WriteUpdateAsync` имеет `try`/`catch`, обрабатывающий ошибки, которые могут возникнуть при записи сообщения в поток.</span><span class="sxs-lookup"><span data-stu-id="63cdb-141">The `WriteUpdateAsync` method has a `try`/`catch` block to handle any errors that might happen when writing a message to the stream.</span></span> <span data-ttu-id="63cdb-142">Это важное обстоятельство в постоянных подключениях по сетям, которые могут быть нарушены в любой миллисекунде, независимо от того, есть ли проблема в любом случае.</span><span class="sxs-lookup"><span data-stu-id="63cdb-142">This is an important consideration in persistent connections over networks, which could be broken at any millisecond, whether intentionally or because of a failure somewhere.</span></span>

### <a name="using-the-stocktickerservice-from-a-client-application"></a><span data-ttu-id="63cdb-143">Использование Стокктиккерсервице из клиентского приложения</span><span class="sxs-lookup"><span data-stu-id="63cdb-143">Using the StockTickerService from a client application</span></span>

<span data-ttu-id="63cdb-144">Выполните те же действия из предыдущего раздела, чтобы создать общую библиотеку классов клиента из файла `.proto`.</span><span class="sxs-lookup"><span data-stu-id="63cdb-144">Follow the same steps in the previous section to create a shareable client class library from the `.proto` file.</span></span> <span data-ttu-id="63cdb-145">В этом примере имеется консольное приложение .NET Core 3,0, которое демонстрирует использование клиента.</span><span class="sxs-lookup"><span data-stu-id="63cdb-145">In the sample, there's a .NET Core 3.0 console application that demonstrates how to use the client.</span></span>

#### <a name="example-programcs"></a><span data-ttu-id="63cdb-146">Пример Program.cs</span><span class="sxs-lookup"><span data-stu-id="63cdb-146">Example Program.cs</span></span>

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

<span data-ttu-id="63cdb-147">В этом случае метод `Subscribe` на созданном клиенте не является асинхронным.</span><span class="sxs-lookup"><span data-stu-id="63cdb-147">In this case, the `Subscribe` method on the generated client isn't asynchronous.</span></span> <span data-ttu-id="63cdb-148">Поток создается и пригоден к использованию, так как его `MoveNext`ный метод является асинхронным и при первом вызове он не будет выполнен до тех пор, пока соединение не будет активно.</span><span class="sxs-lookup"><span data-stu-id="63cdb-148">The stream is created and usable right away, because its `MoveNext` method is asynchronous and the first time it's called it won't complete until the connection is alive.</span></span>

<span data-ttu-id="63cdb-149">Поток передается асинхронному `DisplayAsync` методу. Затем приложение ожидает нажатия пользователем клавиши, затем отменяет `DisplayAsync` метод и ожидает завершения задачи перед выходом.</span><span class="sxs-lookup"><span data-stu-id="63cdb-149">The stream is passed to an async `DisplayAsync` method; the application then waits for the user to press a key, then cancels the `DisplayAsync` method and waits for the task to complete before exiting.</span></span>

> [!NOTE]
> <span data-ttu-id="63cdb-150">Этот код использует новый C# 8-я объявление с использованием синтаксиса для удаления потока и канала при выходе из метода `Main`.</span><span class="sxs-lookup"><span data-stu-id="63cdb-150">This code is using the new C# 8 "using declaration" syntax to dispose of the stream and the channel when the `Main` method exits.</span></span> <span data-ttu-id="63cdb-151">Это небольшое изменение, но хорошо, что сокращает отступы и пустые строки.</span><span class="sxs-lookup"><span data-stu-id="63cdb-151">It's a small change, but a nice one that reduces indentations and empty lines.</span></span>

#### <a name="consume-the-stream"></a><span data-ttu-id="63cdb-152">Использование потока</span><span class="sxs-lookup"><span data-stu-id="63cdb-152">Consume the stream</span></span>

<span data-ttu-id="63cdb-153">WCF использует интерфейсы обратного вызова, чтобы разрешить серверу вызывать методы непосредственно на клиенте.</span><span class="sxs-lookup"><span data-stu-id="63cdb-153">WCF used callback interfaces to allow the server to call methods directly on the client.</span></span> <span data-ttu-id="63cdb-154">потоки gRPC работают по-разному.</span><span class="sxs-lookup"><span data-stu-id="63cdb-154">gRPC streams work differently.</span></span> <span data-ttu-id="63cdb-155">Клиент проходит по возвращенному потоку и обрабатывает сообщения так, как будто они были возвращены из локального метода, возвращающего `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="63cdb-155">The client iterates over the returned stream and processes messages, just as though they were returned from a local method returning an `IEnumerable`.</span></span>

<span data-ttu-id="63cdb-156">Тип `IAsyncStreamReader<T>` работает примерно так же, как `IEnumerator<T>`: существует метод `MoveNext`, возвращающий значение true, если имеется больше данных, и свойство `Current`, возвращающее Последнее значение.</span><span class="sxs-lookup"><span data-stu-id="63cdb-156">The `IAsyncStreamReader<T>` type works much like an `IEnumerator<T>`: there's a `MoveNext` method that will return true as long as there's more data, and a `Current` property that returns the latest value.</span></span> <span data-ttu-id="63cdb-157">Единственное отличие заключается в том, что метод `MoveNext` возвращает `Task<bool>`, а не только `bool`.</span><span class="sxs-lookup"><span data-stu-id="63cdb-157">The only difference is that the `MoveNext` method returns a `Task<bool>` instead of just a `bool`.</span></span> <span data-ttu-id="63cdb-158">Метод расширения `ReadAllAsync` создает оболочку для потока в стандартном C# 8 `IAsyncEnumerable`, который можно использовать с новым синтаксисом `await foreach`.</span><span class="sxs-lookup"><span data-stu-id="63cdb-158">The `ReadAllAsync` extension method wraps the stream in a standard C# 8 `IAsyncEnumerable` that can be used with the new `await foreach` syntax.</span></span>

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
> <span data-ttu-id="63cdb-159">В разделе о [клиентских библиотеках](client-libraries.md#iobservable) в конце этой главы рассматривается добавление метода расширения и классов для переноса `IAsyncStreamReader<T>` в `IObservable<T>` для разработчиков, использующих реактивные шаблоны программирования.</span><span class="sxs-lookup"><span data-stu-id="63cdb-159">The section on [client libraries](client-libraries.md#iobservable) at the end of this chapter looks at how to add an extension method and classes to wrap `IAsyncStreamReader<T>` in an `IObservable<T>` for developers using reactive programming patterns.</span></span>

<span data-ttu-id="63cdb-160">Опять же, перехватите исключения, так как это может привести к сбою в работе сети, а также <xref:System.OperationCanceledException>, которые неизбежно будут вызываться, так как код использует <xref:System.Threading.CancellationToken> для разбиения цикла.</span><span class="sxs-lookup"><span data-stu-id="63cdb-160">Again, be careful to catch exceptions here because of the possibility of network failure, as well as the <xref:System.OperationCanceledException> that will inevitably be thrown because the code is using a <xref:System.Threading.CancellationToken> to break the loop.</span></span> <span data-ttu-id="63cdb-161">Тип `RpcException` имеет много полезной информации об ошибках среды выполнения gRPC, включая `StatusCode`.</span><span class="sxs-lookup"><span data-stu-id="63cdb-161">The `RpcException` type has a lot of useful information about gRPC runtime errors, including the `StatusCode`.</span></span> <span data-ttu-id="63cdb-162">Дополнительные сведения см. в разделе [ *Обработка ошибок* в главе 4](error-handling.md).</span><span class="sxs-lookup"><span data-stu-id="63cdb-162">For more information, see [*Error handling* in Chapter 4](error-handling.md).</span></span>

## <a name="bidirectional-streaming"></a><span data-ttu-id="63cdb-163">Двунаправленная потоковая передача</span><span class="sxs-lookup"><span data-stu-id="63cdb-163">Bidirectional streaming</span></span>

<span data-ttu-id="63cdb-164">Высокодуплексная служба WCF обеспечивает асинхронный обмен сообщениями в режиме реального времени в обоих направлениях.</span><span class="sxs-lookup"><span data-stu-id="63cdb-164">A WCF full-duplex service allows for asynchronous, real-time messaging in both directions.</span></span> <span data-ttu-id="63cdb-165">В примере потоковой передачи сервера клиент запускает запрос, а затем получает поток обновлений.</span><span class="sxs-lookup"><span data-stu-id="63cdb-165">In the server streaming example, the client starts a request, then receives a stream of updates.</span></span> <span data-ttu-id="63cdb-166">Более новая версия этой службы позволит клиенту добавлять и удалять акции из списка без необходимости приостанавливаться и создавать новую подписку.</span><span class="sxs-lookup"><span data-stu-id="63cdb-166">A better version of that service would allow the client to add and remove stocks from the list without having to stop and create a new subscription.</span></span> <span data-ttu-id="63cdb-167">Эта функциональность реализована в [примере решения фуллстокктиккер](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/wcf/FullStockTicker).</span><span class="sxs-lookup"><span data-stu-id="63cdb-167">That functionality has been implemented in the [FullStockTicker sample solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/wcf/FullStockTicker).</span></span>

<span data-ttu-id="63cdb-168">Интерфейс `IFullStockTickerService` предоставляет три метода:</span><span class="sxs-lookup"><span data-stu-id="63cdb-168">The `IFullStockTickerService` interface provides three methods:</span></span>

- <span data-ttu-id="63cdb-169">`Subscribe` запускает подключение.</span><span class="sxs-lookup"><span data-stu-id="63cdb-169">`Subscribe` starts the connection.</span></span>
- <span data-ttu-id="63cdb-170">`AddSymbol` добавляет символ акции для просмотра.</span><span class="sxs-lookup"><span data-stu-id="63cdb-170">`AddSymbol` adds a stock symbol to watch.</span></span>
- <span data-ttu-id="63cdb-171">`RemoveSymbol` удаляет символ из наблюдаемого списка.</span><span class="sxs-lookup"><span data-stu-id="63cdb-171">`RemoveSymbol` removes a symbol from the watched list.</span></span>

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

<span data-ttu-id="63cdb-172">Интерфейс обратного вызова остается прежним.</span><span class="sxs-lookup"><span data-stu-id="63cdb-172">The callback interface remains the same.</span></span>

<span data-ttu-id="63cdb-173">Реализация этого шаблона в gRPC менее проста, так как теперь существует два потока данных с передачей сообщений: от клиента к серверу и от сервера к клиенту.</span><span class="sxs-lookup"><span data-stu-id="63cdb-173">Implementing this pattern in gRPC is less straightforward, because there are now two streams of data with messages being passed: one from client to server, and another from server to client.</span></span> <span data-ttu-id="63cdb-174">Невозможно использовать несколько методов для реализации операции добавления и удаления, но в одном потоке можно передать более одного типа сообщений, используя либо `Any` тип, либо `oneof` ключевое слово, которые были описаны в [главе 3](protobuf-any-oneof.md).</span><span class="sxs-lookup"><span data-stu-id="63cdb-174">It isn't possible to use multiple methods to implement the Add and Remove operation, but more than one type of message can be passed on a single stream, using either the `Any` type or `oneof` keyword, which were covered in [Chapter 3](protobuf-any-oneof.md).</span></span>

<span data-ttu-id="63cdb-175">В случае, когда существует конкретный набор допустимых типов, `oneof` является лучшим способом.</span><span class="sxs-lookup"><span data-stu-id="63cdb-175">For a case where there's a specific set of types that are acceptable, `oneof` is a better way to go.</span></span> <span data-ttu-id="63cdb-176">Используйте `ActionMessage`, который может содержать либо `AddSymbolRequest`, либо `RemoveSymbolRequest`.</span><span class="sxs-lookup"><span data-stu-id="63cdb-176">Use an `ActionMessage` that can hold either an `AddSymbolRequest` or a `RemoveSymbolRequest`.</span></span>

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

<span data-ttu-id="63cdb-177">Объявите двунаправленную службу потоковой передачи, которая принимает поток `ActionMessage` сообщений.</span><span class="sxs-lookup"><span data-stu-id="63cdb-177">Declare a bi-directional streaming service that takes a stream of `ActionMessage` messages.</span></span>

```protobuf
service FullStockTicker {
  rpc Subscribe (stream ActionMessage) returns (stream StockTickerUpdate);
}
```

<span data-ttu-id="63cdb-178">Реализация для этой службы аналогична предыдущему примеру, за исключением того, что первый параметр метода `Subscribe` теперь является `IAsyncStreamReader<ActionMessage>`, который можно использовать для обработки запросов `Add` и `Remove`.</span><span class="sxs-lookup"><span data-stu-id="63cdb-178">The implementation for this service is similar to the previous example, except the first parameter of the `Subscribe` method is now an `IAsyncStreamReader<ActionMessage>`, which can be used to handle the `Add` and `Remove` requests.</span></span>

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

<span data-ttu-id="63cdb-179">Класс `ActionMessage`, который gRPC был создан для нас, гарантирует, что только одно из свойств `Add` и `Remove` можно задать, и найти, какой именно из них `null` является допустимым способом определения того, какой тип сообщения используется, но есть и лучший способ.</span><span class="sxs-lookup"><span data-stu-id="63cdb-179">The `ActionMessage` class that gRPC has generated for us guarantees that only one of the `Add` and `Remove` properties can be set, and finding which one isn't `null` is a valid way of finding which type of message is used, but there's a better way.</span></span> <span data-ttu-id="63cdb-180">Создание кода также создает `enum ActionOneOfCase` в классе `ActionMessage`, который выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="63cdb-180">The code generation also created an `enum ActionOneOfCase` in the `ActionMessage` class, which looks like this:</span></span>

```csharp
public enum ActionOneofCase {
    None = 0,
    Add = 1,
    Remove = 2,
}
```

<span data-ttu-id="63cdb-181">Свойство, `ActionCase`ное для объекта `ActionMessage`, можно использовать с инструкцией `switch`, чтобы определить, какое поле задается.</span><span class="sxs-lookup"><span data-stu-id="63cdb-181">The property `ActionCase` on the `ActionMessage` object can be used with a `switch` statement to determine which field is set.</span></span>

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
> <span data-ttu-id="63cdb-182">В инструкции `switch` имеется `default` регистр, который регистрирует предупреждение при обнаружении неизвестного значения `ActionOneOfCase`.</span><span class="sxs-lookup"><span data-stu-id="63cdb-182">The `switch` statement has a `default` case that logs a warning if an unknown `ActionOneOfCase` value is encountered.</span></span> <span data-ttu-id="63cdb-183">Это может быть полезно в том случае, если клиент использует более позднюю версию файла `.proto`, который добавил дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="63cdb-183">This could be useful in indicating that a client is using a later version of the `.proto` file which has added more actions.</span></span> <span data-ttu-id="63cdb-184">Это одна из причин того, что использование `switch` лучше, чем тестирование `null` на известных полях.</span><span class="sxs-lookup"><span data-stu-id="63cdb-184">This is one reason why using a `switch` is better than testing for `null` on known fields.</span></span>

### <a name="use-the-fullstocktickerservice-from-a-client-application"></a><span data-ttu-id="63cdb-185">Использование Фуллстокктиккерсервице из клиентского приложения</span><span class="sxs-lookup"><span data-stu-id="63cdb-185">Use the FullStockTickerService from a client application</span></span>

<span data-ttu-id="63cdb-186">Для демонстрации использования этого более сложного клиента используется простое приложение WPF .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="63cdb-186">There's a simple .NET Core 3.0 WPF application to demonstrate use of this more complex client.</span></span> <span data-ttu-id="63cdb-187">Полное приложение можно найти на сайте [GitHub](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTicker).</span><span class="sxs-lookup"><span data-stu-id="63cdb-187">The full application can be found [on GitHub](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTicker).</span></span>

<span data-ttu-id="63cdb-188">Клиент используется в классе `MainWindowViewModel`, который получает экземпляр типа `FullStockTicker.FullStockTickerClient` из внедрения зависимостей.</span><span class="sxs-lookup"><span data-stu-id="63cdb-188">The client is used in the `MainWindowViewModel` class, which gets an instance of the `FullStockTicker.FullStockTickerClient` type from dependency injection.</span></span>

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

<span data-ttu-id="63cdb-189">Объект, возвращаемый методом `client.Subscribe()`, теперь является экземпляром типа библиотеки gRPC `AsyncDuplexStreamingCall<TRequest, TResponse>`, который предоставляет `RequestStream` для отправки запросов на сервер, а также `ResponseStream` для обработки ответов.</span><span class="sxs-lookup"><span data-stu-id="63cdb-189">The object returned by the `client.Subscribe()` method is now an instance of the gRPC library type `AsyncDuplexStreamingCall<TRequest, TResponse>`, which provides a `RequestStream` for sending requests to the server, and a `ResponseStream` for handling responses.</span></span>

<span data-ttu-id="63cdb-190">Поток запроса используется из некоторых методов `ICommand` WPF для добавления и удаления символов.</span><span class="sxs-lookup"><span data-stu-id="63cdb-190">The request stream is used from some WPF `ICommand` methods to add and remove symbols.</span></span> <span data-ttu-id="63cdb-191">Для каждой операции задайте соответствующее поле для объекта `ActionMessage`.</span><span class="sxs-lookup"><span data-stu-id="63cdb-191">For each operation, set the relevant field on an `ActionMessage` object:</span></span>

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
> <span data-ttu-id="63cdb-192">При установке значения поля `oneof` в сообщении автоматически очищаются все ранее установленные поля.</span><span class="sxs-lookup"><span data-stu-id="63cdb-192">Setting a `oneof` field's value on a message automatically clears any fields that have been previously set.</span></span>

<span data-ttu-id="63cdb-193">Поток ответов обрабатывается в методе `async`, а `Task` возвращаемого объекта удерживается для удаления при закрытии окна.</span><span class="sxs-lookup"><span data-stu-id="63cdb-193">The stream of responses is handled in an `async` method, and the `Task` it returns is held to be disposed when the window is closed.</span></span>

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

### <a name="client-clean-up"></a><span data-ttu-id="63cdb-194">Очистка клиента</span><span class="sxs-lookup"><span data-stu-id="63cdb-194">Client clean-up</span></span>

<span data-ttu-id="63cdb-195">Когда окно закрывается и `MainWindowViewModel` удаляется (из `Closed` события `MainWindow`), рекомендуется правильно ликвидировать объект `AsyncDuplexStreamingCall`.</span><span class="sxs-lookup"><span data-stu-id="63cdb-195">When the window is closed and the `MainWindowViewModel` is disposed (from the `Closed` event of `MainWindow`), it's recommended that you properly dispose the `AsyncDuplexStreamingCall` object.</span></span> <span data-ttu-id="63cdb-196">В частности, для корректного закрытия потока на сервере необходимо вызвать метод `CompleteAsync` в `RequestStream`.</span><span class="sxs-lookup"><span data-stu-id="63cdb-196">In particular, the `CompleteAsync` method on the `RequestStream` should be called to gracefully close the stream on the server.</span></span> <span data-ttu-id="63cdb-197">В следующем примере показан метод `DisposeAsync` из примера представления-модели:</span><span class="sxs-lookup"><span data-stu-id="63cdb-197">The following example shows the `DisposeAsync` method from the sample view-model:</span></span>

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

<span data-ttu-id="63cdb-198">Закрытие потоков запросов позволяет серверу своевременно удалять собственные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="63cdb-198">Closing request streams enables the server to dispose of its own resources in a timely manner.</span></span> <span data-ttu-id="63cdb-199">Это повышает эффективность и масштабируемость служб и предотвращает исключения.</span><span class="sxs-lookup"><span data-stu-id="63cdb-199">This improves the efficiency and scalability of services and prevents exceptions.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="63cdb-200">[Назад](migrate-request-reply.md)
>[Вперед](streaming-versus-repeated.md)</span><span class="sxs-lookup"><span data-stu-id="63cdb-200">[Previous](migrate-request-reply.md)
[Next](streaming-versus-repeated.md)</span></span>
