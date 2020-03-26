---
title: Типы RPC - gRPC для разработчиков WCF
description: Обзор типов удаленного вызова процедуры, поддерживаемого WCF, и их эквивалентов в gRPC
ms.date: 09/02/2019
ms.openlocfilehash: 40c0779dc015904e9dabbb448075e3c5aa5dc49a
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111092"
---
# <a name="types-of-rpc"></a><span data-ttu-id="2241e-103">Типы RPC</span><span class="sxs-lookup"><span data-stu-id="2241e-103">Types of RPC</span></span>

<span data-ttu-id="2241e-104">Как разработчик Фонда коммуникации Windows (WCF), вы, вероятно, привыкли иметь дело со следующими типами удаленного вызова процедуры (RPC):</span><span class="sxs-lookup"><span data-stu-id="2241e-104">As a Windows Communication Foundation (WCF) developer, you're probably used to dealing with the following types of remote procedure call (RPC):</span></span>

- <span data-ttu-id="2241e-105">Запрос/ответ</span><span class="sxs-lookup"><span data-stu-id="2241e-105">Request/reply</span></span>
- <span data-ttu-id="2241e-106">Дуплекс:</span><span class="sxs-lookup"><span data-stu-id="2241e-106">Duplex:</span></span>
  - <span data-ttu-id="2241e-107">Односторонний дуплекс с сеансом</span><span class="sxs-lookup"><span data-stu-id="2241e-107">One-way duplex with session</span></span>
  - <span data-ttu-id="2241e-108">Полный дуплекс с сеансом</span><span class="sxs-lookup"><span data-stu-id="2241e-108">Full duplex with session</span></span>
- <span data-ttu-id="2241e-109">Односторонний</span><span class="sxs-lookup"><span data-stu-id="2241e-109">One-way</span></span>

<span data-ttu-id="2241e-110">Это возможно, чтобы сопоставить эти типы RPC довольно естественно к существующим концепциям gRPC.</span><span class="sxs-lookup"><span data-stu-id="2241e-110">It's possible to map these RPC types fairly naturally to existing gRPC concepts.</span></span> <span data-ttu-id="2241e-111">В этой главе будет рассматриваться каждая из этих областей в свою очередь.</span><span class="sxs-lookup"><span data-stu-id="2241e-111">This chapter will look at each of these areas in turn.</span></span> <span data-ttu-id="2241e-112">[В главе 5](migrate-wcf-to-grpc.md) будут более подробно рассмотрены аналогичные примеры.</span><span class="sxs-lookup"><span data-stu-id="2241e-112">[Chapter 5](migrate-wcf-to-grpc.md) will explore similar examples in greater depth.</span></span>

| <span data-ttu-id="2241e-113">WCF</span><span class="sxs-lookup"><span data-stu-id="2241e-113">WCF</span></span> | <span data-ttu-id="2241e-114">gRPC</span><span class="sxs-lookup"><span data-stu-id="2241e-114">gRPC</span></span> |
| --- | ---- |
| <span data-ttu-id="2241e-115">Регулярный запрос/ответ</span><span class="sxs-lookup"><span data-stu-id="2241e-115">Regular request/reply</span></span> | <span data-ttu-id="2241e-116">Унарный</span><span class="sxs-lookup"><span data-stu-id="2241e-116">Unary</span></span> |
| <span data-ttu-id="2241e-117">Служба Duplex с сеансом с использованием интерфейса обратного вызова клиента</span><span class="sxs-lookup"><span data-stu-id="2241e-117">Duplex service with session using a client callback interface</span></span> | <span data-ttu-id="2241e-118">Потоковая передача серверов</span><span class="sxs-lookup"><span data-stu-id="2241e-118">Server streaming</span></span> |
| <span data-ttu-id="2241e-119">Полный дуплексный сервис с сеансом</span><span class="sxs-lookup"><span data-stu-id="2241e-119">Full duplex service with session</span></span> | <span data-ttu-id="2241e-120">Двунаправленная потоковая передача</span><span class="sxs-lookup"><span data-stu-id="2241e-120">Bidirectional streaming</span></span> |
| <span data-ttu-id="2241e-121">Односторонние операции</span><span class="sxs-lookup"><span data-stu-id="2241e-121">One-way operations</span></span> | <span data-ttu-id="2241e-122">Потоковая передача клиентов</span><span class="sxs-lookup"><span data-stu-id="2241e-122">Client streaming</span></span> |

## <a name="requestreply"></a><span data-ttu-id="2241e-123">Запрос/ответ</span><span class="sxs-lookup"><span data-stu-id="2241e-123">Request/reply</span></span>

<span data-ttu-id="2241e-124">Для простых методов запроса/ответа, которые принимают и возвращают небольшие объемы данных, используйте простейшую модель gRPC, неассосудную RPC.</span><span class="sxs-lookup"><span data-stu-id="2241e-124">For simple request/reply methods that take and return small amounts of data, use the simplest gRPC pattern, the unary RPC.</span></span>

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

<span data-ttu-id="2241e-125">Как вы можете видеть, реализация необезратого метода обслуживания GRPC аналогична реализации операции WCF.</span><span class="sxs-lookup"><span data-stu-id="2241e-125">As you can see, implementing a gRPC unary RPC service method is similar to implementing a WCF operation.</span></span> <span data-ttu-id="2241e-126">Разница в том, что с gRPC вы переопределить метод базового класса вместо реализации интерфейса.</span><span class="sxs-lookup"><span data-stu-id="2241e-126">The difference is that with gRPC, you override a base class method instead of implementing an interface.</span></span> <span data-ttu-id="2241e-127">На сервере всегда возвращаются <xref:System.Threading.Tasks.Task%601>базовые методы gRPC, хотя клиент предоставляет как async, так и методы блокировки для вызова службы.</span><span class="sxs-lookup"><span data-stu-id="2241e-127">On the server, gRPC base methods always return <xref:System.Threading.Tasks.Task%601>, although the client provides both async and blocking methods to call the service.</span></span>

## <a name="wcf-duplex-one-way-to-client"></a><span data-ttu-id="2241e-128">WCF дуплекс, один из способов клиента</span><span class="sxs-lookup"><span data-stu-id="2241e-128">WCF duplex, one way to client</span></span>

<span data-ttu-id="2241e-129">Приложения WCF (с определенными привязками) могут создать постоянное соединение между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="2241e-129">WCF applications (with certain bindings) can create a persistent connection between client and server.</span></span> <span data-ttu-id="2241e-130">Сервер может асинхронно отправлять данные клиенту до тех пор, пока соединение <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> не будет закрыто, используя *интерфейс обратного вызова,* указанный в свойстве.</span><span class="sxs-lookup"><span data-stu-id="2241e-130">The server can asynchronously send data to the client until the connection is closed, by using a *callback interface* specified in the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> property.</span></span>

<span data-ttu-id="2241e-131">службы gRPC предоставляют аналогичную функциональность с потоками сообщений.</span><span class="sxs-lookup"><span data-stu-id="2241e-131">gRPC services provide similar functionality with message streams.</span></span> <span data-ttu-id="2241e-132">Потоки не отображаются *точно* к дуплексным службам WCF с точки зрения реализации, но вы можете достичь тех же результатов.</span><span class="sxs-lookup"><span data-stu-id="2241e-132">Streams don't map *exactly* to WCF duplex services in terms of implementation, but you can achieve the same results.</span></span>

### <a name="grpc-streaming"></a><span data-ttu-id="2241e-133">gRPC потоковое</span><span class="sxs-lookup"><span data-stu-id="2241e-133">gRPC streaming</span></span>

<span data-ttu-id="2241e-134">gRPC поддерживает создание постоянных потоков от клиента к серверу и от сервера к клиенту.</span><span class="sxs-lookup"><span data-stu-id="2241e-134">gRPC supports the creation of persistent streams from client to server, and from server to client.</span></span> <span data-ttu-id="2241e-135">Оба типа потока могут быть активными одновременно.</span><span class="sxs-lookup"><span data-stu-id="2241e-135">Both types of stream can be active concurrently.</span></span> <span data-ttu-id="2241e-136">Эта способность называется двунаправленной потоковой передачей.</span><span class="sxs-lookup"><span data-stu-id="2241e-136">This ability is called bidirectional streaming.</span></span>

<span data-ttu-id="2241e-137">Вы можете использовать потоки для произвольных, асинхронных сообщений с течением времени.</span><span class="sxs-lookup"><span data-stu-id="2241e-137">You can use streams for arbitrary, asynchronous messaging over time.</span></span> <span data-ttu-id="2241e-138">Или вы можете использовать их для передачи больших наборов данных, которые слишком велики для генерации и отправки одного запроса или ответа.</span><span class="sxs-lookup"><span data-stu-id="2241e-138">Or you can use them for passing large datasets that are too big to generate and send in a single request or response.</span></span>

<span data-ttu-id="2241e-139">В следующем примере показан rPC, потокую серверов.</span><span class="sxs-lookup"><span data-stu-id="2241e-139">The following example shows a server-streaming RPC.</span></span>

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

<span data-ttu-id="2241e-140">Этот поток серверов можно использовать из клиентского приложения, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="2241e-140">This server stream can be consumed from a client application, as shown in the following code:</span></span>

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
> <span data-ttu-id="2241e-141">RFC, потоковые передачи серверов, полезны для служб в стиле подписки.</span><span class="sxs-lookup"><span data-stu-id="2241e-141">Server-streaming RPCs are useful for subscription-style services.</span></span> <span data-ttu-id="2241e-142">Они также полезны для отправки больших наборов данных, когда было бы неэффективно или невозможно создать весь набор данных в памяти.</span><span class="sxs-lookup"><span data-stu-id="2241e-142">They're also useful for sending large datasets when it would be inefficient or impossible to build the entire dataset in memory.</span></span> <span data-ttu-id="2241e-143">Однако потоковые ответы не `repeated` так быстро, как отправка полей в одном сообщении.</span><span class="sxs-lookup"><span data-stu-id="2241e-143">However, streaming responses isn't as fast as sending `repeated` fields in a single message.</span></span> <span data-ttu-id="2241e-144">Как правило, потоковая передача не должна использоваться для небольших наборов данных.</span><span class="sxs-lookup"><span data-stu-id="2241e-144">As a rule, streaming shouldn't be used for small datasets.</span></span>

### <a name="differences-from-wcf"></a><span data-ttu-id="2241e-145">Отличия от WCF</span><span class="sxs-lookup"><span data-stu-id="2241e-145">Differences from WCF</span></span>

<span data-ttu-id="2241e-146">Служба дуплексов WCF использует интерфейс обратного вызова клиента, который может иметь несколько методов.</span><span class="sxs-lookup"><span data-stu-id="2241e-146">A WCF duplex service uses a client callback interface that can have multiple methods.</span></span> <span data-ttu-id="2241e-147">Служба потоковой передачи серверов gRPC может отправлять сообщения только по одному потоку.</span><span class="sxs-lookup"><span data-stu-id="2241e-147">A gRPC server-streaming service can only send messages over a single stream.</span></span> <span data-ttu-id="2241e-148">Если вам нужно несколько методов, используйте тип сообщения с [любым полем или полем для](protobuf-any-oneof.md) отправки различных сообщений и напишите код в клиенте для их обработки.</span><span class="sxs-lookup"><span data-stu-id="2241e-148">If you need multiple methods, use a message type with either [an Any field or a oneof field](protobuf-any-oneof.md) to send different messages, and write code in the client to handle them.</span></span>

<span data-ttu-id="2241e-149">В WCF класс [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) с сеансом сохраняется до тех пор, пока соединение не будет закрыто.</span><span class="sxs-lookup"><span data-stu-id="2241e-149">In WCF, the [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) class with the session is kept alive until the connection is closed.</span></span> <span data-ttu-id="2241e-150">Несколько методов могут быть вызваны в рамках сеанса.</span><span class="sxs-lookup"><span data-stu-id="2241e-150">Multiple methods can be called within the session.</span></span> <span data-ttu-id="2241e-151">В gRPC `Task` возврат метода реализации не должен заканчиваться до тех пор, пока соединение не будет закрыто.</span><span class="sxs-lookup"><span data-stu-id="2241e-151">In gRPC, the `Task` that the implementation method returns shouldn't finish until the connection is closed.</span></span>

## <a name="wcf-one-way-operations-and-grpc-client-streaming"></a><span data-ttu-id="2241e-152">Операции с односторонним способом WCF и потоковая передача клиентов gRPC</span><span class="sxs-lookup"><span data-stu-id="2241e-152">WCF one-way operations and gRPC client streaming</span></span>

<span data-ttu-id="2241e-153">WCF предоставляет односторонние операции `[OperationContract(IsOneWay = true)]`(отмеченные), которые возвращают транспортно-специфическое подтверждение.</span><span class="sxs-lookup"><span data-stu-id="2241e-153">WCF provides one-way operations (marked with `[OperationContract(IsOneWay = true)]`) that return a transport-specific acknowledgment.</span></span> <span data-ttu-id="2241e-154">методы службы gRPC всегда возвращают ответ, даже если он пуст.</span><span class="sxs-lookup"><span data-stu-id="2241e-154">gRPC service methods always return a response, even if it's empty.</span></span> <span data-ttu-id="2241e-155">Клиент всегда должен ждать этого ответа.</span><span class="sxs-lookup"><span data-stu-id="2241e-155">The client should always await that response.</span></span> <span data-ttu-id="2241e-156">Для "огонь и забыть" стиль обмена сообщениями в gRPC, вы можете создать клиент потокового сервиса.</span><span class="sxs-lookup"><span data-stu-id="2241e-156">For the "fire-and-forget" style of messaging in gRPC, you can create a client streaming service.</span></span>

### <a name="thing_logproto"></a><span data-ttu-id="2241e-157">thing_log.прото</span><span class="sxs-lookup"><span data-stu-id="2241e-157">thing_log.proto</span></span>

```protobuf
service ThingLog {
  rpc OpenConnection(stream Thing) returns (ConnectionClosedResponse);
}
```

### <a name="thinglogservicecs"></a><span data-ttu-id="2241e-158">ThingLogService.cs</span><span class="sxs-lookup"><span data-stu-id="2241e-158">ThingLogService.cs</span></span>

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

### <a name="thinglog-client-example"></a><span data-ttu-id="2241e-159">Пример клиента ThingLog</span><span class="sxs-lookup"><span data-stu-id="2241e-159">ThingLog client example</span></span>

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

<span data-ttu-id="2241e-160">Для обмена сообщениями, как показано в предыдущем примере, можно использовать потоковых RRP для потоковой передачи огня и забвения.</span><span class="sxs-lookup"><span data-stu-id="2241e-160">You can use client-streaming RPCs for fire-and-forget messaging, as shown in the previous example.</span></span> <span data-ttu-id="2241e-161">Вы также можете использовать их для отправки очень больших наборов данных на сервер.</span><span class="sxs-lookup"><span data-stu-id="2241e-161">You can also use them for sending very large datasets to the server.</span></span> <span data-ttu-id="2241e-162">То же предупреждение о производительности применяется: `repeated` для небольших наборов данных, использовать поля в регулярных сообщениях.</span><span class="sxs-lookup"><span data-stu-id="2241e-162">The same warning about performance applies: for smaller datasets, use `repeated` fields in regular messages.</span></span>

## <a name="wcf-full-duplex-services"></a><span data-ttu-id="2241e-163">Услуги WCF полного дуплекса</span><span class="sxs-lookup"><span data-stu-id="2241e-163">WCF full-duplex services</span></span>

<span data-ttu-id="2241e-164">Связывание дуплекса WCF поддерживает несколько односторонних операций как на интерфейсе службы, так и на интерфейсе обратного вызова клиента.</span><span class="sxs-lookup"><span data-stu-id="2241e-164">WCF duplex binding supports multiple one-way operations on both the service interface and the client callback interface.</span></span> <span data-ttu-id="2241e-165">Эта поддержка позволяет вести постоянные разговоры между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="2241e-165">This support allows ongoing conversations between client and server.</span></span> <span data-ttu-id="2241e-166">gRPC поддерживает нечто подобное с двунаправленными потоковыми RFC, где оба параметра отмечены модификатором. `stream`</span><span class="sxs-lookup"><span data-stu-id="2241e-166">gRPC supports something similar with bidirectional streaming RPCs, where both parameters are marked with the `stream` modifier.</span></span>

### <a name="chatproto"></a><span data-ttu-id="2241e-167">chat.proto</span><span class="sxs-lookup"><span data-stu-id="2241e-167">chat.proto</span></span>

```protobuf
service Chatter {
    rpc Connect(stream IncomingMessage) returns (stream OutgoingMessage);
}
```

### <a name="chatterservicecs"></a><span data-ttu-id="2241e-168">ChatterService.cs</span><span class="sxs-lookup"><span data-stu-id="2241e-168">ChatterService.cs</span></span>

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

<span data-ttu-id="2241e-169">В предыдущем примере можно увидеть, что метод реализации`IAsyncStreamReader<MessageRequest>`получает как поток`IServerStreamWriter<MessageResponse>`запросов () и поток ответов ().</span><span class="sxs-lookup"><span data-stu-id="2241e-169">In the previous example, you can see that the implementation method receives both a request stream (`IAsyncStreamReader<MessageRequest>`) and a response stream (`IServerStreamWriter<MessageResponse>`).</span></span> <span data-ttu-id="2241e-170">Метод может читать и писать сообщения до тех пор, пока соединение не будет закрыто.</span><span class="sxs-lookup"><span data-stu-id="2241e-170">The method can read and write messages until the connection is closed.</span></span>

### <a name="chatter-client"></a><span data-ttu-id="2241e-171">Чат-клиент</span><span class="sxs-lookup"><span data-stu-id="2241e-171">Chatter client</span></span>

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
><span data-ttu-id="2241e-172">[Предыдущий](wcf-bindings.md)
>[Следующий](metadata.md)</span><span class="sxs-lookup"><span data-stu-id="2241e-172">[Previous](wcf-bindings.md)
[Next](metadata.md)</span></span>
