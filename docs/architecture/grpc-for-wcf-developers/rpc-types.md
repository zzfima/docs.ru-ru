---
title: Типы RPC-gRPC для разработчиков WCF
description: Проверка типов удаленного вызова процедур, поддерживаемого WCF, и их эквивалентов в gRPC
ms.date: 09/02/2019
ms.openlocfilehash: 58f097bac61395e6810155e8ae9a6bbf2219ec5e
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78675159"
---
# <a name="types-of-rpc"></a><span data-ttu-id="d8e0d-103">Типы RPC</span><span class="sxs-lookup"><span data-stu-id="d8e0d-103">Types of RPC</span></span>

<span data-ttu-id="d8e0d-104">Как разработчик Windows Communication Foundation (WCF) вы, вероятно, используете для работы со следующими типами удаленного вызова процедур (RPC):</span><span class="sxs-lookup"><span data-stu-id="d8e0d-104">As a Windows Communication Foundation (WCF) developer, you're probably used to dealing with the following types of remote procedure call (RPC):</span></span>

- <span data-ttu-id="d8e0d-105">Запрос или ответ</span><span class="sxs-lookup"><span data-stu-id="d8e0d-105">Request/reply</span></span>
- <span data-ttu-id="d8e0d-106">Устройства</span><span class="sxs-lookup"><span data-stu-id="d8e0d-106">Duplex:</span></span>
  - <span data-ttu-id="d8e0d-107">Односторонний дуплекс с сеансом</span><span class="sxs-lookup"><span data-stu-id="d8e0d-107">One-way duplex with session</span></span>
  - <span data-ttu-id="d8e0d-108">Полный дуплекс с сеансом</span><span class="sxs-lookup"><span data-stu-id="d8e0d-108">Full duplex with session</span></span>
- <span data-ttu-id="d8e0d-109">Односторонний</span><span class="sxs-lookup"><span data-stu-id="d8e0d-109">One-way</span></span>

<span data-ttu-id="d8e0d-110">Вы можете сопоставлять эти типы RPC довольно естественно с существующими концепциями gRPC.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-110">It's possible to map these RPC types fairly naturally to existing gRPC concepts.</span></span> <span data-ttu-id="d8e0d-111">В этой главе мы рассмотрим каждую из этих областей.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-111">This chapter will look at each of these areas in turn.</span></span> <span data-ttu-id="d8e0d-112">В [главе 5](migrate-wcf-to-grpc.md) более подробно рассматриваются аналогичные примеры.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-112">[Chapter 5](migrate-wcf-to-grpc.md) will explore similar examples in greater depth.</span></span>

| <span data-ttu-id="d8e0d-113">WCF</span><span class="sxs-lookup"><span data-stu-id="d8e0d-113">WCF</span></span> | <span data-ttu-id="d8e0d-114">gRPC</span><span class="sxs-lookup"><span data-stu-id="d8e0d-114">gRPC</span></span> |
| --- | ---- |
| <span data-ttu-id="d8e0d-115">Обычный запрос или ответ</span><span class="sxs-lookup"><span data-stu-id="d8e0d-115">Regular request/reply</span></span> | <span data-ttu-id="d8e0d-116">Унарный</span><span class="sxs-lookup"><span data-stu-id="d8e0d-116">Unary</span></span> |
| <span data-ttu-id="d8e0d-117">Дуплексная служба с сеансом с использованием интерфейса обратного вызова клиента</span><span class="sxs-lookup"><span data-stu-id="d8e0d-117">Duplex service with session using a client callback interface</span></span> | <span data-ttu-id="d8e0d-118">Потоковая передача сервера</span><span class="sxs-lookup"><span data-stu-id="d8e0d-118">Server streaming</span></span> |
| <span data-ttu-id="d8e0d-119">Полная дуплексная служба с сеансом</span><span class="sxs-lookup"><span data-stu-id="d8e0d-119">Full duplex service with session</span></span> | <span data-ttu-id="d8e0d-120">Двунаправленная потоковая передача</span><span class="sxs-lookup"><span data-stu-id="d8e0d-120">Bidirectional streaming</span></span> |
| <span data-ttu-id="d8e0d-121">Односторонние операции</span><span class="sxs-lookup"><span data-stu-id="d8e0d-121">One-way operations</span></span> | <span data-ttu-id="d8e0d-122">Потоковая передача клиента</span><span class="sxs-lookup"><span data-stu-id="d8e0d-122">Client streaming</span></span> |

## <a name="requestreply"></a><span data-ttu-id="d8e0d-123">Запрос или ответ</span><span class="sxs-lookup"><span data-stu-id="d8e0d-123">Request/reply</span></span>

<span data-ttu-id="d8e0d-124">Для простых методов запроса/ответа, которые принимают и возвращают небольшие объемы данных, используйте простейший шаблон gRPC, унарный RPC.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-124">For simple request/reply methods that take and return small amounts of data, use the simplest gRPC pattern, the unary RPC.</span></span>

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

<span data-ttu-id="d8e0d-125">Как видите, реализация метода унарной службы RPC gRPC аналогична реализации операции WCF.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-125">As you can see, implementing a gRPC unary RPC service method is similar to implementing a WCF operation.</span></span> <span data-ttu-id="d8e0d-126">Разница заключается в том, что при использовании gRPC переопределяется метод базового класса вместо реализации интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-126">The difference is that with gRPC, you override a base class method instead of implementing an interface.</span></span> <span data-ttu-id="d8e0d-127">На сервере gRPC базовые методы всегда возвращают <xref:System.Threading.Tasks.Task%601>, хотя клиент предоставляет как асинхронные, так и блокирующие методы для вызова службы.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-127">On the server, gRPC base methods always return <xref:System.Threading.Tasks.Task%601>, although the client provides both async and blocking methods to call the service.</span></span>

## <a name="wcf-duplex-one-way-to-client"></a><span data-ttu-id="d8e0d-128">Дуплексная среда WCF, один из способов клиента</span><span class="sxs-lookup"><span data-stu-id="d8e0d-128">WCF duplex, one way to client</span></span>

<span data-ttu-id="d8e0d-129">Приложения WCF (с определенными привязками) могут создавать постоянное подключение между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-129">WCF applications (with certain bindings) can create a persistent connection between client and server.</span></span> <span data-ttu-id="d8e0d-130">Сервер может асинхронно передавать данные клиенту до тех пор, пока соединение не будет закрыто с помощью *интерфейса обратного вызова* , указанного в свойстве <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-130">The server can asynchronously send data to the client until the connection is closed, by using a *callback interface* specified in the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> property.</span></span>

<span data-ttu-id="d8e0d-131">службы gRPC Services предоставляют аналогичные функции для потоков сообщений.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-131">gRPC services provide similar functionality with message streams.</span></span> <span data-ttu-id="d8e0d-132">Потоки не *точно* соответствуют службам дуплексной службы WCF с точки зрения реализации, но можно добиться того же результата.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-132">Streams don't map *exactly* to WCF duplex services in terms of implementation, but you can achieve the same results.</span></span>

### <a name="grpc-streaming"></a><span data-ttu-id="d8e0d-133">Потоковая передача gRPC</span><span class="sxs-lookup"><span data-stu-id="d8e0d-133">gRPC streaming</span></span>

<span data-ttu-id="d8e0d-134">gRPC поддерживает создание постоянных потоков от клиента к серверу и от сервера к клиенту.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-134">gRPC supports the creation of persistent streams from client to server, and from server to client.</span></span> <span data-ttu-id="d8e0d-135">Оба типа потока могут быть активными одновременно.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-135">Both types of stream can be active concurrently.</span></span> <span data-ttu-id="d8e0d-136">Эта возможность называется двунаправленной потоковой передачей.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-136">This ability is called bidirectional streaming.</span></span> 

<span data-ttu-id="d8e0d-137">Потоки можно использовать для произвольного асинхронного обмена сообщениями с течением времени.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-137">You can use streams for arbitrary, asynchronous messaging over time.</span></span> <span data-ttu-id="d8e0d-138">Их также можно использовать для передачи больших наборов данных, которые слишком велики для создания и отправки в одном запросе или ответе.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-138">Or you can use them for passing large datasets that are too big to generate and send in a single request or response.</span></span>

<span data-ttu-id="d8e0d-139">В следующем примере показана потоковая передача на сервере RPC.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-139">The following example shows a server-streaming RPC.</span></span>

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

<span data-ttu-id="d8e0d-140">Этот серверный поток можно использовать в клиентском приложении, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="d8e0d-140">This server stream can be consumed from a client application, as shown in the following code:</span></span>

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
> <span data-ttu-id="d8e0d-141">RPC-потоковая передача серверов полезна для служб в стиле подписки.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-141">Server-streaming RPCs are useful for subscription-style services.</span></span> <span data-ttu-id="d8e0d-142">Они также полезны при отправке больших наборов данных, если бы они были неэффективными или невозможно построить весь набор в памяти.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-142">They're also useful for sending large datasets when it would be inefficient or impossible to build the entire dataset in memory.</span></span> <span data-ttu-id="d8e0d-143">Однако потоковые ответы не так быстро, как отправляют `repeated` поля в одном сообщении.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-143">However, streaming responses isn't as fast as sending `repeated` fields in a single message.</span></span> <span data-ttu-id="d8e0d-144">Как правило, потоковая передача не должна использоваться для небольших наборов данных.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-144">As a rule, streaming shouldn't be used for small datasets.</span></span>

### <a name="differences-from-wcf"></a><span data-ttu-id="d8e0d-145">Отличия от WCF</span><span class="sxs-lookup"><span data-stu-id="d8e0d-145">Differences from WCF</span></span>

<span data-ttu-id="d8e0d-146">Служба дуплексной службы WCF использует интерфейс обратного вызова клиента, который может иметь несколько методов.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-146">A WCF duplex service uses a client callback interface that can have multiple methods.</span></span> <span data-ttu-id="d8e0d-147">Служба потоковой передачи на сервере gRPC может передавать сообщения только в одном потоке.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-147">A gRPC server-streaming service can only send messages over a single stream.</span></span> <span data-ttu-id="d8e0d-148">Если требуется несколько методов, используйте тип сообщений с [любым полем или одним из полей](protobuf-any-oneof.md) для отправки различных сообщений, а также напишите код на стороне клиента, чтобы их обрабатывали.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-148">If you need multiple methods, use a message type with either [an Any field or a oneof field](protobuf-any-oneof.md) to send different messages, and write code in the client to handle them.</span></span>

<span data-ttu-id="d8e0d-149">В WCF класс [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) с сеансом хранится в активном состоянии до закрытия соединения.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-149">In WCF, the [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) class with the session is kept alive until the connection is closed.</span></span> <span data-ttu-id="d8e0d-150">В рамках сеанса можно вызывать несколько методов.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-150">Multiple methods can be called within the session.</span></span> <span data-ttu-id="d8e0d-151">В gRPC `Task`, что метод реализации возвращает значение, не должно заканчиваться до закрытия соединения.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-151">In gRPC, the `Task` that the implementation method returns shouldn't finish until the connection is closed.</span></span>

## <a name="wcf-one-way-operations-and-grpc-client-streaming"></a><span data-ttu-id="d8e0d-152">Односторонние операции WCF и потоковая передача клиента gRPC</span><span class="sxs-lookup"><span data-stu-id="d8e0d-152">WCF one-way operations and gRPC client streaming</span></span>

<span data-ttu-id="d8e0d-153">WCF предоставляет односторонние операции (помеченные `[OperationContract(IsOneWay = true)]`), которые возвращают подтверждение, относящееся к транспортному отметке.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-153">WCF provides one-way operations (marked with `[OperationContract(IsOneWay = true)]`) that return a transport-specific acknowledgement.</span></span> <span data-ttu-id="d8e0d-154">методы службы gRPC всегда возвращают ответ, даже если он пуст.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-154">gRPC service methods always return a response, even if it's empty.</span></span> <span data-ttu-id="d8e0d-155">Клиент всегда должен ожидать этот ответ.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-155">The client should always await that response.</span></span> <span data-ttu-id="d8e0d-156">Для стиля обмена сообщениями «пожар-and-забыть» в gRPC можно создать службу потоковой передачи клиента.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-156">For the "fire-and-forget" style of messaging in gRPC, you can create a client streaming service.</span></span>

### <a name="thing_logproto"></a><span data-ttu-id="d8e0d-157">thing_log.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-157">thing_log.proto</span></span>

```protobuf
service ThingLog {
  rpc OpenConnection(stream Thing) returns (ConnectionClosedResponse);
}
```

### <a name="thinglogservicecs"></a><span data-ttu-id="d8e0d-158">ThingLogService.cs</span><span class="sxs-lookup"><span data-stu-id="d8e0d-158">ThingLogService.cs</span></span>

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

### <a name="thinglog-client-example"></a><span data-ttu-id="d8e0d-159">Пример клиента Синглог</span><span class="sxs-lookup"><span data-stu-id="d8e0d-159">ThingLog client example</span></span>

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

<span data-ttu-id="d8e0d-160">Можно использовать клиентские потоковые вызовы RPC для обмена сообщениями пожара и-забыть, как показано в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-160">You can use client-streaming RPCs for fire-and-forget messaging, as shown in the previous example.</span></span> <span data-ttu-id="d8e0d-161">Их также можно использовать для отправки очень больших наборов данных на сервер.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-161">You can also use them for sending very large datasets to the server.</span></span> <span data-ttu-id="d8e0d-162">То же самое предупреждение о производительности применяется: для наборов данных меньшего размера используйте `repeated` поля в обычных сообщениях.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-162">The same warning about performance applies: for smaller datasets, use `repeated` fields in regular messages.</span></span>

## <a name="wcf-full-duplex-services"></a><span data-ttu-id="d8e0d-163">Службы Full-дуплексного WCF</span><span class="sxs-lookup"><span data-stu-id="d8e0d-163">WCF full-duplex services</span></span>

<span data-ttu-id="d8e0d-164">Двусторонняя привязка WCF поддерживает несколько односторонних операций с интерфейсом службы и интерфейсом обратного вызова клиента.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-164">WCF duplex binding supports multiple one-way operations on both the service interface and the client callback interface.</span></span> <span data-ttu-id="d8e0d-165">Эта поддержка позволяет выполнять текущие диалоги между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-165">This support allows ongoing conversations between client and server.</span></span> <span data-ttu-id="d8e0d-166">gRPC поддерживает нечто подобное с двунаправленной потоковой передачей RPC, где оба параметра помечены модификатором `stream`.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-166">gRPC supports something similar with bidirectional streaming RPCs, where both parameters are marked with the `stream` modifier.</span></span>

### <a name="chatproto"></a><span data-ttu-id="d8e0d-167">чат...</span><span class="sxs-lookup"><span data-stu-id="d8e0d-167">chat.proto</span></span>

```protobuf
service Chatter {
    rpc Connect(stream IncomingMessage) returns (stream OutgoingMessage);
}
```

### <a name="chatterservicecs"></a><span data-ttu-id="d8e0d-168">ChatterService.cs</span><span class="sxs-lookup"><span data-stu-id="d8e0d-168">ChatterService.cs</span></span>

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

<span data-ttu-id="d8e0d-169">В предыдущем примере можно увидеть, что метод реализации получает поток запроса (`IAsyncStreamReader<MessageRequest>`) и поток ответа (`IServerStreamWriter<MessageResponse>`).</span><span class="sxs-lookup"><span data-stu-id="d8e0d-169">In the previous example, you can see that the implementation method receives both a request stream (`IAsyncStreamReader<MessageRequest>`) and a response stream (`IServerStreamWriter<MessageResponse>`).</span></span> <span data-ttu-id="d8e0d-170">Метод может считывать и записывать сообщения, пока соединение не будет закрыто.</span><span class="sxs-lookup"><span data-stu-id="d8e0d-170">The method can read and write messages until the connection is closed.</span></span>

### <a name="chatter-client"></a><span data-ttu-id="d8e0d-171">Клиент chatter</span><span class="sxs-lookup"><span data-stu-id="d8e0d-171">Chatter client</span></span>

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
><span data-ttu-id="d8e0d-172">[Назад](wcf-bindings.md)
>[Вперед](metadata.md)</span><span class="sxs-lookup"><span data-stu-id="d8e0d-172">[Previous](wcf-bindings.md)
[Next](metadata.md)</span></span>
