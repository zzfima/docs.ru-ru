---
title: Типы RPC - gRPC для разработчиков WCF
description: Обзор типов удаленного вызова процедуры, поддерживаемого WCF, и их эквивалентов в gRPC
ms.date: 09/02/2019
ms.openlocfilehash: b9d4ce7cae693ed7904229483cbccfe3b299b640
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401787"
---
# <a name="types-of-rpc"></a>Типы RPC

Как разработчик Фонда коммуникации Windows (WCF), вы, вероятно, привыкли иметь дело со следующими типами удаленного вызова процедуры (RPC):

- Запрос/ответ
- Дуплекс:
  - Односторонний дуплекс с сеансом
  - Полный дуплекс с сеансом
- Односторонний

Это возможно, чтобы сопоставить эти типы RPC довольно естественно к существующим концепциям gRPC. В этой главе будет рассматриваться каждая из этих областей в свою очередь. [В главе 5](migrate-wcf-to-grpc.md) будут более подробно рассмотрены аналогичные примеры.

| WCF | gRPC |
| --- | ---- |
| Регулярный запрос/ответ | Унарный |
| Служба Duplex с сеансом с использованием интерфейса обратного вызова клиента | Потоковая передача серверов |
| Полный дуплексный сервис с сеансом | Двунаправленная потоковая передача |
| Односторонние операции | Потоковая передача клиентов |

## <a name="requestreply"></a>Запрос/ответ

Для простых методов запроса/ответа, которые принимают и возвращают небольшие объемы данных, используйте простейшую модель gRPC, неассосудную RPC.

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

Как вы можете видеть, реализация необезратого метода обслуживания GRPC аналогична реализации операции WCF. Разница в том, что с gRPC вы переопределить метод базового класса вместо реализации интерфейса. На сервере всегда возвращаются <xref:System.Threading.Tasks.Task%601>базовые методы gRPC, хотя клиент предоставляет как async, так и методы блокировки для вызова службы.

## <a name="wcf-duplex-one-way-to-client"></a>WCF дуплекс, один из способов клиента

Приложения WCF (с определенными привязками) могут создать постоянное соединение между клиентом и сервером. Сервер может асинхронно отправлять данные клиенту до тех пор, пока соединение <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> не будет закрыто, используя *интерфейс обратного вызова,* указанный в свойстве.

службы gRPC предоставляют аналогичную функциональность с потоками сообщений. Потоки не отображаются *точно* к дуплексным службам WCF с точки зрения реализации, но вы можете достичь тех же результатов.

### <a name="grpc-streaming"></a>gRPC потоковое

gRPC поддерживает создание постоянных потоков от клиента к серверу и от сервера к клиенту. Оба типа потока могут быть активными одновременно. Эта способность называется двунаправленной потоковой передачей.

Вы можете использовать потоки для произвольных, асинхронных сообщений с течением времени. Или вы можете использовать их для передачи больших наборов данных, которые слишком велики для генерации и отправки одного запроса или ответа.

В следующем примере показан rPC, потокую серверов.

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

Этот поток серверов можно использовать из клиентского приложения, как показано в следующем коде:

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
> RFC, потоковые передачи серверов, полезны для служб в стиле подписки. Они также полезны для отправки больших наборов данных, когда было бы неэффективно или невозможно создать весь набор данных в памяти. Однако потоковые ответы не `repeated` так быстро, как отправка полей в одном сообщении. Как правило, потоковая передача не должна использоваться для небольших наборов данных.

### <a name="differences-from-wcf"></a>Отличия от WCF

Служба дуплексов WCF использует интерфейс обратного вызова клиента, который может иметь несколько методов. Служба потоковой передачи серверов gRPC может отправлять сообщения только по одному потоку. Если вам нужно несколько методов, используйте тип сообщения с [любым полем или полем для](protobuf-any-oneof.md) отправки различных сообщений и напишите код в клиенте для их обработки.

В WCF класс [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) с сеансом сохраняется до тех пор, пока соединение не будет закрыто. Несколько методов могут быть вызваны в рамках сеанса. В gRPC `Task` возврат метода реализации не должен заканчиваться до тех пор, пока соединение не будет закрыто.

## <a name="wcf-one-way-operations-and-grpc-client-streaming"></a>Операции с односторонним способом WCF и потоковая передача клиентов gRPC

WCF предоставляет односторонние операции `[OperationContract(IsOneWay = true)]`(отмеченные), которые возвращают подтверждение транспортного специфичного. методы службы gRPC всегда возвращают ответ, даже если он пуст. Клиент всегда должен ждать этого ответа. Для "огонь и забыть" стиль обмена сообщениями в gRPC, вы можете создать клиент потокового сервиса.

### <a name="thing_logproto"></a>thing_log.прото

```protobuf
service ThingLog {
  rpc OpenConnection(stream Thing) returns (ConnectionClosedResponse);
}
```

### <a name="thinglogservicecs"></a>ThingLogService.cs

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

### <a name="thinglog-client-example"></a>Пример клиента ThingLog

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

Для обмена сообщениями, как показано в предыдущем примере, можно использовать потоковых RRP для потоковой передачи огня и забвения. Вы также можете использовать их для отправки очень больших наборов данных на сервер. То же предупреждение о производительности применяется: `repeated` для небольших наборов данных, использовать поля в регулярных сообщениях.

## <a name="wcf-full-duplex-services"></a>Услуги WCF полного дуплекса

Связывание дуплекса WCF поддерживает несколько односторонних операций как на интерфейсе службы, так и на интерфейсе обратного вызова клиента. Эта поддержка позволяет вести постоянные разговоры между клиентом и сервером. gRPC поддерживает нечто подобное с двунаправленными потоковыми RFC, где оба параметра отмечены модификатором. `stream`

### <a name="chatproto"></a>chat.proto

```protobuf
service Chatter {
    rpc Connect(stream IncomingMessage) returns (stream OutgoingMessage);
}
```

### <a name="chatterservicecs"></a>ChatterService.cs

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

В предыдущем примере можно увидеть, что метод реализации`IAsyncStreamReader<MessageRequest>`получает как поток`IServerStreamWriter<MessageResponse>`запросов () и поток ответов (). Метод может читать и писать сообщения до тех пор, пока соединение не будет закрыто.

### <a name="chatter-client"></a>Чат-клиент

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
>[Предыдущий](wcf-bindings.md)
>[Следующий](metadata.md)
