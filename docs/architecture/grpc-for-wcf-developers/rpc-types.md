---
title: Типы RPC-gRPC для разработчиков WCF
description: Проверка типов удаленного вызова процедур, поддерживаемого WCF, и их эквивалентов в gRPC
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: ce5bf03b01dff3f7bb201ff08c9065abc2e58360
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841381"
---
# <a name="types-of-rpc"></a><span data-ttu-id="6152e-103">Типы RPC</span><span class="sxs-lookup"><span data-stu-id="6152e-103">Types of RPC</span></span>

<span data-ttu-id="6152e-104">Как разработчик Windows Communication Foundation (WCF) вы, вероятно, используете для работы со следующими типами удаленного вызова процедур (RPC):</span><span class="sxs-lookup"><span data-stu-id="6152e-104">As a Windows Communication Foundation (WCF) developer, you're probably used to dealing with the following types of Remote Procedure Call (RPC):</span></span>

- <span data-ttu-id="6152e-105">Запрос-ответ</span><span class="sxs-lookup"><span data-stu-id="6152e-105">Request/Reply</span></span>
- <span data-ttu-id="6152e-106">Устройства</span><span class="sxs-lookup"><span data-stu-id="6152e-106">Duplex:</span></span>
  - <span data-ttu-id="6152e-107">Односторонний дуплекс с сеансом</span><span class="sxs-lookup"><span data-stu-id="6152e-107">One-way duplex with session</span></span>
  - <span data-ttu-id="6152e-108">Полный дуплекс с сеансом</span><span class="sxs-lookup"><span data-stu-id="6152e-108">Full duplex with session</span></span>
- <span data-ttu-id="6152e-109">Односторонний</span><span class="sxs-lookup"><span data-stu-id="6152e-109">One-way</span></span>

<span data-ttu-id="6152e-110">Вы можете сопоставлять эти типы RPC довольно естественно с существующими концепциями gRPC, и в этой главе будет рассмотрена каждая из этих областей.</span><span class="sxs-lookup"><span data-stu-id="6152e-110">It's possible to map these RPC types fairly naturally to existing gRPC concepts and this chapter will look at each of these areas in turn.</span></span> <span data-ttu-id="6152e-111">Аналогичные примеры будут рассмотрены гораздо более подробно в [главе 5](migrate-wcf-to-grpc.md).</span><span class="sxs-lookup"><span data-stu-id="6152e-111">Similar examples will be explored in much greater depth in [Chapter 5](migrate-wcf-to-grpc.md).</span></span>

| <span data-ttu-id="6152e-112">WCF</span><span class="sxs-lookup"><span data-stu-id="6152e-112">WCF</span></span> | <span data-ttu-id="6152e-113">gRPC</span><span class="sxs-lookup"><span data-stu-id="6152e-113">gRPC</span></span> |
| --- | ---- |
| <span data-ttu-id="6152e-114">Обычный запрос или ответ</span><span class="sxs-lookup"><span data-stu-id="6152e-114">Regular request/reply</span></span> | <span data-ttu-id="6152e-115">Унарный</span><span class="sxs-lookup"><span data-stu-id="6152e-115">Unary</span></span> |
| <span data-ttu-id="6152e-116">Дуплексная служба с сеансом с использованием интерфейса обратного вызова клиента</span><span class="sxs-lookup"><span data-stu-id="6152e-116">Duplex service with session using a client callback interface</span></span> | <span data-ttu-id="6152e-117">Потоковая передача сервера</span><span class="sxs-lookup"><span data-stu-id="6152e-117">Server streaming</span></span> |
| <span data-ttu-id="6152e-118">Полная дуплексная служба с сеансом</span><span class="sxs-lookup"><span data-stu-id="6152e-118">Full duplex service with session</span></span> | <span data-ttu-id="6152e-119">Двунаправленная потоковая передача</span><span class="sxs-lookup"><span data-stu-id="6152e-119">Bidirectional streaming</span></span> |
| <span data-ttu-id="6152e-120">Односторонние операции</span><span class="sxs-lookup"><span data-stu-id="6152e-120">One-way operations</span></span> | <span data-ttu-id="6152e-121">Потоковая передача клиента</span><span class="sxs-lookup"><span data-stu-id="6152e-121">Client streaming</span></span> |

## <a name="requestreply"></a><span data-ttu-id="6152e-122">Запрос или ответ</span><span class="sxs-lookup"><span data-stu-id="6152e-122">Request/reply</span></span>

<span data-ttu-id="6152e-123">Для простых методов запроса/ответа, которые принимают и возвращают небольшие объемы данных, используйте простейший шаблон gRPC, унарный RPC.</span><span class="sxs-lookup"><span data-stu-id="6152e-123">For simple request/reply methods that take and return small amounts of data, use the simplest gRPC pattern, the unary RPC.</span></span>

```protobuf
service Things {
    rpc Get(GetThingRequest) returns (GetThingResponse);
}
```

```csharp
public class ThingService : Things.ThingsBase
{
    public override async Task<GetThingResponse> Get(GetThingRequest request, ServerCallContext context)
    {
        // Get thing from database
        return new GetThingResponse { Thing = thing };
    }
}
```

```csharp
public async Task ShowThing(int thingId)
{
    var thing = await _thingsClient.GetAsync(new GetThingRequest { ThingId = thingId });
    Console.WriteLine($"{thing.Name}");
}
```

<span data-ttu-id="6152e-124">Как видите, реализация метода унарной службы RPC gRPC очень похожа на реализацию операции WCF, за исключением того, что с gRPC переопределяется метод базового класса вместо реализации интерфейса.</span><span class="sxs-lookup"><span data-stu-id="6152e-124">As you can see, implementing a gRPC unary RPC service method is very similar to implementing a WCF operation, except that with gRPC you override a base class method instead of implementing an interface.</span></span> <span data-ttu-id="6152e-125">Обратите внимание, что на сервере базовые методы gRPC всегда возвращают <xref:System.Threading.Tasks.Task%601>, хотя клиент предоставляет как асинхронные, так и блокирующие методы для вызова службы.</span><span class="sxs-lookup"><span data-stu-id="6152e-125">Note that on the server, gRPC base methods always return a <xref:System.Threading.Tasks.Task%601>, although the client provides both async and blocking methods to call the service.</span></span>

## <a name="wcf-duplex-one-way-to-client"></a><span data-ttu-id="6152e-126">Дуплексный, односторонний клиент WCF</span><span class="sxs-lookup"><span data-stu-id="6152e-126">WCF duplex, one-way to client</span></span>

<span data-ttu-id="6152e-127">Приложения WCF (с определенными привязками) могут создавать постоянное подключение между клиентом и сервером, а сервер может асинхронно передавать данные клиенту до закрытия соединения, используя *интерфейс обратного вызова* , указанный в свойстве <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6152e-127">WCF applications (with certain bindings) can create a persistent connection between client and server, and the server can asynchronously send data to the client until the connection is closed, using a *callback interface* specified in the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> property.</span></span>

<span data-ttu-id="6152e-128">службы gRPC Services предоставляют аналогичные функции для потоков сообщений.</span><span class="sxs-lookup"><span data-stu-id="6152e-128">gRPC services provide similar functionality with message streams.</span></span> <span data-ttu-id="6152e-129">Потоки не *точно* соответствуют службам дуплексной службы WCF с точки зрения реализации, но эти же результаты могут быть достигнуты.</span><span class="sxs-lookup"><span data-stu-id="6152e-129">Streams don't map *exactly* to WCF duplex services in terms of implementation, but the same results can be achieved.</span></span>

### <a name="grpc-streaming"></a><span data-ttu-id="6152e-130">Потоковая передача gRPC</span><span class="sxs-lookup"><span data-stu-id="6152e-130">gRPC streaming</span></span>

<span data-ttu-id="6152e-131">gRPC поддерживает создание постоянных потоков от клиента к серверу и от сервера к клиенту.</span><span class="sxs-lookup"><span data-stu-id="6152e-131">gRPC supports the creation of persistent streams from client to server, and from server to client.</span></span> <span data-ttu-id="6152e-132">Оба типа потока могут быть активными одновременно. Это называется двунаправленной потоковой передачей.</span><span class="sxs-lookup"><span data-stu-id="6152e-132">Both types of stream may be active concurrently; this is called bidirectional streaming.</span></span> <span data-ttu-id="6152e-133">Потоки могут использоваться для произвольного асинхронного обмена сообщениями по времени или для передачи больших наборов данных, которые слишком велики для создания и отправки в одном запросе или ответе.</span><span class="sxs-lookup"><span data-stu-id="6152e-133">Streams can be used for arbitrary, asynchronous messaging over time, or for passing large datasets that are too big to generate and send in a single request or response.</span></span>

<span data-ttu-id="6152e-134">В следующем примере показана потоковая передача RPC сервера.</span><span class="sxs-lookup"><span data-stu-id="6152e-134">The following example shows a server streaming RPC.</span></span>

```protobuf
service ClockStreamer {
    rpc Subscribe(ClockSubscribeRequest) returns (stream ClockMessage);
}
```

```csharp
public class ClockStreamerService : ClockStreamer.ClockStreamerBase
{
    public override async Task Subscribe(ClockSubscribeRequest request,
        IServerStreamWriter<ClockMessage> responseStream,
        ServerCallContext context)
    {
        while (!context.CancellationToken.IsCancellationRequested)
        {
            var time = DateTimeOffset.UtcNow;
            await responseStream.WriteAsync(new ClockMessage { message = $"The time is {time:t}." });
            await Task.Delay(TimeSpan.FromSeconds(10), context.CancellationToken);
        }
    }
}
```

<span data-ttu-id="6152e-135">Этот серверный поток может быть использован из клиентского приложения, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="6152e-135">This server stream could be consumed from a client application as shown in the following code:</span></span>

```csharp
public async Task TellTheTimeAsync(CancellationToken token)
{
    var channel = GrpcChannel.ForAddress("https://localhost:5001");
    var client = new ClockStreamer.ClockStreamerClient(channel);

    var request = new ClockSubscribeRequest();
    var response = client.Subscribe(request);

    await foreach (var update in response.ResponseStream.ReadAllAsync(token))
    {
        Console.WriteLine(update.Message);
    }
}
```

> [!NOTE]
> <span data-ttu-id="6152e-136">Серверная потоковая передача RPC полезна для служб в стиле подписки, а также для отправки очень больших наборов данных в случае неэффективной или невозможности построить весь набор в памяти.</span><span class="sxs-lookup"><span data-stu-id="6152e-136">Server streaming RPCs are useful for subscription-style services, and also for sending very large datasets when it would be inefficient or impossible to build the entire dataset in memory.</span></span> <span data-ttu-id="6152e-137">Однако потоковые ответы не так быстро, как отправляют `repeated` поля в одном сообщении, поэтому для небольших наборов данных не следует использовать потоковую передачу правила.</span><span class="sxs-lookup"><span data-stu-id="6152e-137">However, streaming responses isn't as fast as sending `repeated` fields in a single message, so as a rule streaming shouldn't be used for small datasets.</span></span>

### <a name="differences-to-wcf"></a><span data-ttu-id="6152e-138">Отличия от WCF</span><span class="sxs-lookup"><span data-stu-id="6152e-138">Differences to WCF</span></span>

<span data-ttu-id="6152e-139">Служба дуплексной службы WCF использует интерфейс обратного вызова клиента, который может иметь несколько методов.</span><span class="sxs-lookup"><span data-stu-id="6152e-139">A WCF duplex service uses a client callback interface that can have multiple methods.</span></span> <span data-ttu-id="6152e-140">Служба потоковой передачи сервера gRPC может передавать сообщения только в одном потоке.</span><span class="sxs-lookup"><span data-stu-id="6152e-140">A gRPC server streaming service can only send messages over a single stream.</span></span> <span data-ttu-id="6152e-141">Если требуется несколько методов, используйте тип сообщений с [любым полем или одним из полей](protobuf-any-oneof.md) для отправки различных сообщений, а также напишите код на стороне клиента, чтобы их обрабатывали.</span><span class="sxs-lookup"><span data-stu-id="6152e-141">If you need multiple methods, use a message type with either [an Any field or a oneof field](protobuf-any-oneof.md) to send different messages, and write code in the client to handle them.</span></span>

<span data-ttu-id="6152e-142">В WCF класс [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) с сеансом хранится в активном состоянии до закрытия соединения, и в рамках сеанса может быть вызвано несколько методов.</span><span class="sxs-lookup"><span data-stu-id="6152e-142">In WCF, the [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) class with the session is kept alive until the connection is closed, and multiple methods may be called within the session.</span></span> <span data-ttu-id="6152e-143">В gRPC `Task`, возвращаемые методом реализации, не должны завершаться до тех пор, пока соединение не будет закрыто.</span><span class="sxs-lookup"><span data-stu-id="6152e-143">In gRPC, the `Task` returned by the implementation method shouldn't complete until the connection is closed.</span></span>

## <a name="wcf-one-way-operations-and-grpc-client-streaming"></a><span data-ttu-id="6152e-144">Односторонние операции WCF и потоковая передача клиента gRPC</span><span class="sxs-lookup"><span data-stu-id="6152e-144">WCF one-way operations and gRPC client streaming</span></span>

<span data-ttu-id="6152e-145">WCF предоставляет односторонние операции (помеченные `[OperationContract(IsOneWay = true)]`), которые возвращают подтверждение, относящееся к транспортному отметке.</span><span class="sxs-lookup"><span data-stu-id="6152e-145">WCF provides one-way operations (marked with `[OperationContract(IsOneWay = true)]`) that return a transport-specific acknowledgement.</span></span> <span data-ttu-id="6152e-146">методы службы gRPC всегда возвращают ответ, даже если он пуст, и клиент всегда должен ожидать этот ответ.</span><span class="sxs-lookup"><span data-stu-id="6152e-146">gRPC service methods always return a response, even if it's empty, and the client should always await that response.</span></span> <span data-ttu-id="6152e-147">Для сообщений с стилем "пожар-and-забыть" в gRPC можно создать службу потоковой передачи клиента.</span><span class="sxs-lookup"><span data-stu-id="6152e-147">For "fire-and-forget" style messaging in gRPC, you can create a client streaming service.</span></span>

### <a name="thing_logproto"></a><span data-ttu-id="6152e-148">thing_log.</span><span class="sxs-lookup"><span data-stu-id="6152e-148">thing_log.proto</span></span>

```protobuf
service ThingLog {
  rpc OpenConnection(stream Thing) returns (ConnectionClosedResponse);
}
```

### <a name="thinglogservicecs"></a><span data-ttu-id="6152e-149">ThingLogService.cs</span><span class="sxs-lookup"><span data-stu-id="6152e-149">ThingLogService.cs</span></span>

```csharp
public class ThingLogService : Protos.ThingLog.ThingLogBase
{
    private static readonly ConnectionClosedResponse EmptyResponse = new ConnectionClosedResponse();
    private readonly ILogger<ThingLogService> _logger;
    public ThingLogService(ILogger<ThingLogService> logger)
    {
        _logger = logger;
    }

    public override async Task<CompletedResponse> OpenConnection(IAsyncStreamReader<Thing> requestStream, ServerCallContext context)
    {
        while (await requestStream.MoveNext(context.CancellationToken))
        {
            _logger.LogInformation(requestStream.Current.Description);
        }
        return EmptyResponse;
    }
}
```

### <a name="thinglog-client-example"></a><span data-ttu-id="6152e-150">Пример клиента Синглог</span><span class="sxs-lookup"><span data-stu-id="6152e-150">ThingLog client example</span></span>

```csharp
public class ThingLogger : IAsyncDisposable
{
    private readonly ThingLog.ThingLogClient _client;
    private readonly AsyncClientStreamingCall<ThingLogRequest, CompletedResponse> _stream;

    public ThingLogger(ThingLog.ThingLogClient client)
    {
        _client = client;
        _stream = client.OpenConnection();
    }

    public async Task WriteAsync(string description)
    {
        await _stream.RequestStream.WriteAsync(new Thing
        {
            Description = description,
            Time = Timestamp.FromDateTimeOffset(DateTimeOffset.UtcNow)
        });
    }

    public async ValueTask DisposeAsync()
    {
        await _stream.RequestStream.CompleteAsync();
        _stream.Dispose();
    }
}
```

<span data-ttu-id="6152e-151">Опять же, можно использовать потоковую передачу RPC для сообщений о пожаре и забыть, как показано в предыдущем примере, но также для отправки очень больших наборов данных на сервер.</span><span class="sxs-lookup"><span data-stu-id="6152e-151">Again, client streaming RPCs can be used for fire-and-forget messaging as shown in the previous example, but also for sending very large datasets to the server.</span></span> <span data-ttu-id="6152e-152">То же самое предупреждение о производительности применяется: для наборов данных меньшего размера используйте `repeated` поля в обычных сообщениях.</span><span class="sxs-lookup"><span data-stu-id="6152e-152">The same warning about performance applies: for smaller datasets, use `repeated` fields in regular messages.</span></span>

## <a name="wcf-full-duplex-services"></a><span data-ttu-id="6152e-153">Службы полноценного дуплекса WCF</span><span class="sxs-lookup"><span data-stu-id="6152e-153">WCF full duplex services</span></span>

<span data-ttu-id="6152e-154">Двусторонняя привязка WCF поддерживает несколько односторонних операций с интерфейсом службы и интерфейсом обратного вызова клиента, что позволяет выполнять текущие диалоги между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="6152e-154">WCF duplex binding supports multiple one-way operations on both the service interface and the client callback interface, allowing ongoing conversations between client and server.</span></span> <span data-ttu-id="6152e-155">gRPC поддерживает нечто подобное с двунаправленной потоковой передачей RPC, где оба параметра помечены модификатором `stream`.</span><span class="sxs-lookup"><span data-stu-id="6152e-155">gRPC supports something similar with bidirectional streaming RPCs, where both parameters are marked with the `stream` modifier.</span></span>

### <a name="chatproto"></a><span data-ttu-id="6152e-156">чат...</span><span class="sxs-lookup"><span data-stu-id="6152e-156">chat.proto</span></span>

```protobuf
service Chatter {
    rpc Connect(stream IncomingMessage) returns (stream OutgoingMessage);
}
```

### <a name="chatterservicecs"></a><span data-ttu-id="6152e-157">ChatterService.cs</span><span class="sxs-lookup"><span data-stu-id="6152e-157">ChatterService.cs</span></span>

```csharp
public class ChatterService : Chatter.ChatterBase
{
    private readonly IChatHub _hub;

    public ChatterService(IChatHub hub)
    {
        _hub = hub;
    }

    public override async Task Connect(IAsyncStreamReader<MessageRequest> requestStream, IServerStreamWriter<MessageResponse> responseStream, ServerCallContext context)
    {
        _hub.MessageReceived += async (sender, args) =>
            await responseStream.WriteAsync(new MessageResponse {Text = args.Message});

        while (await requestStream.MoveNext(context.CancellationToken))
        {
            await _hub.SendAsync(requestStream.Current.Text);
        }
    }
}
```

<span data-ttu-id="6152e-158">В предыдущем примере можно увидеть, что метод реализации получает поток запроса (`IAsyncStreamReader<MessageRequest>`) и поток ответа (`IServerStreamWriter<MessageResponse>`) и может считывать и записывать сообщения, пока соединение не будет закрыто.</span><span class="sxs-lookup"><span data-stu-id="6152e-158">In the previous example, you can see that the implementation method receives both a request stream (`IAsyncStreamReader<MessageRequest>`) and a response stream (`IServerStreamWriter<MessageResponse>`), and can read and write messages until the connection is closed.</span></span>

### <a name="chatter-client"></a><span data-ttu-id="6152e-159">Клиент chatter</span><span class="sxs-lookup"><span data-stu-id="6152e-159">Chatter client</span></span>

```csharp
public class Chat : IAsyncDisposable
{
    private readonly Chatter.ChatterClient _client;
    private readonly AsyncDuplexStreamingCall<MessageRequest, MessageResponse> _stream;
    private readonly CancellationTokenSource _cancellationTokenSource;
    private readonly Task _readTask;

    public Chat(Chatter.ChatterClient client)
    {
        _client = client;
        _stream = _client.Connect();
        _cancellationTokenSource = new CancellationTokenSource();
        _readTask = ReadAsync(_cancellationTokenSource.Token);
    }

    public async Task SendAsync(string message)
    {
        await _stream.RequestStream.WriteAsync(new MessageRequest {Text = message});
    }

    private async Task ReadAsync(CancellationToken token)
    {
        while (await _stream.ResponseStream.MoveNext(token))
        {
            Console.WriteLine(_stream.ResponseStream.Current.Text);
        }
    }

    public async ValueTask DisposeAsync()
    {
        await _stream.RequestStream.CompleteAsync();
        await _readTask;
        _stream.Dispose();
    }
}
```

>[!div class="step-by-step"]
><span data-ttu-id="6152e-160">[Назад](wcf-bindings.md)
>[Вперед](metadata.md)</span><span class="sxs-lookup"><span data-stu-id="6152e-160">[Previous](wcf-bindings.md)
[Next](metadata.md)</span></span>
