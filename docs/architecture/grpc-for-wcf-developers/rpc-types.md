---
title: Типы RPC-gRPC для разработчиков WCF
description: Проверка типов удаленного вызова процедур, поддерживаемого WCF, и их эквивалентов в gRPC
ms.date: 09/02/2019
ms.openlocfilehash: 58f097bac61395e6810155e8ae9a6bbf2219ec5e
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503440"
---
# <a name="types-of-rpc"></a>Типы RPC

Как разработчик Windows Communication Foundation (WCF) вы, вероятно, используете для работы со следующими типами удаленного вызова процедур (RPC):

- Запрос или ответ
- Устройства
  - Односторонний дуплекс с сеансом
  - Полный дуплекс с сеансом
- Односторонний

Вы можете сопоставлять эти типы RPC довольно естественно с существующими концепциями gRPC. В этой главе мы рассмотрим каждую из этих областей. В [главе 5](migrate-wcf-to-grpc.md) более подробно рассматриваются аналогичные примеры.

| WCF | gRPC |
| --- | ---- |
| Обычный запрос или ответ | Унарный |
| Дуплексная служба с сеансом с использованием интерфейса обратного вызова клиента | Потоковая передача сервера |
| Полная дуплексная служба с сеансом | Двунаправленная потоковая передача |
| Односторонние операции | Потоковая передача клиента |

## <a name="requestreply"></a>Запрос или ответ

Для простых методов запроса/ответа, которые принимают и возвращают небольшие объемы данных, используйте простейший шаблон gRPC, унарный RPC.

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

Как видите, реализация метода унарной службы RPC gRPC аналогична реализации операции WCF. Разница заключается в том, что при использовании gRPC переопределяется метод базового класса вместо реализации интерфейса. На сервере gRPC базовые методы всегда возвращают <xref:System.Threading.Tasks.Task%601>, хотя клиент предоставляет как асинхронные, так и блокирующие методы для вызова службы.

## <a name="wcf-duplex-one-way-to-client"></a>Дуплексная среда WCF, один из способов клиента

Приложения WCF (с определенными привязками) могут создавать постоянное подключение между клиентом и сервером. Сервер может асинхронно передавать данные клиенту до тех пор, пока соединение не будет закрыто с помощью *интерфейса обратного вызова* , указанного в свойстве <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType>.

службы gRPC Services предоставляют аналогичные функции для потоков сообщений. Потоки не *точно* соответствуют службам дуплексной службы WCF с точки зрения реализации, но можно добиться того же результата.

### <a name="grpc-streaming"></a>Потоковая передача gRPC

gRPC поддерживает создание постоянных потоков от клиента к серверу и от сервера к клиенту. Оба типа потока могут быть активными одновременно. Эта возможность называется двунаправленной потоковой передачей. 

Потоки можно использовать для произвольного асинхронного обмена сообщениями с течением времени. Их также можно использовать для передачи больших наборов данных, которые слишком велики для создания и отправки в одном запросе или ответе.

В следующем примере показана потоковая передача на сервере RPC.

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

Этот серверный поток можно использовать в клиентском приложении, как показано в следующем коде:

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
> RPC-потоковая передача серверов полезна для служб в стиле подписки. Они также полезны при отправке больших наборов данных, если бы они были неэффективными или невозможно построить весь набор в памяти. Однако потоковые ответы не так быстро, как отправляют `repeated` поля в одном сообщении. Как правило, потоковая передача не должна использоваться для небольших наборов данных.

### <a name="differences-from-wcf"></a>Отличия от WCF

Служба дуплексной службы WCF использует интерфейс обратного вызова клиента, который может иметь несколько методов. Служба потоковой передачи на сервере gRPC может передавать сообщения только в одном потоке. Если требуется несколько методов, используйте тип сообщений с [любым полем или одним из полей](protobuf-any-oneof.md) для отправки различных сообщений, а также напишите код на стороне клиента, чтобы их обрабатывали.

В WCF класс [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) с сеансом хранится в активном состоянии до закрытия соединения. В рамках сеанса можно вызывать несколько методов. В gRPC `Task`, что метод реализации возвращает значение, не должно заканчиваться до закрытия соединения.

## <a name="wcf-one-way-operations-and-grpc-client-streaming"></a>Односторонние операции WCF и потоковая передача клиента gRPC

WCF предоставляет односторонние операции (помеченные `[OperationContract(IsOneWay = true)]`), которые возвращают подтверждение, относящееся к транспортному отметке. методы службы gRPC всегда возвращают ответ, даже если он пуст. Клиент всегда должен ожидать этот ответ. Для стиля обмена сообщениями «пожар-and-забыть» в gRPC можно создать службу потоковой передачи клиента.

### <a name="thing_logproto"></a>thing_log.

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

### <a name="thinglog-client-example"></a>Пример клиента Синглог

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

Можно использовать клиентские потоковые вызовы RPC для обмена сообщениями пожара и-забыть, как показано в предыдущем примере. Их также можно использовать для отправки очень больших наборов данных на сервер. То же самое предупреждение о производительности применяется: для наборов данных меньшего размера используйте `repeated` поля в обычных сообщениях.

## <a name="wcf-full-duplex-services"></a>Службы Full-дуплексного WCF

Двусторонняя привязка WCF поддерживает несколько односторонних операций с интерфейсом службы и интерфейсом обратного вызова клиента. Эта поддержка позволяет выполнять текущие диалоги между клиентом и сервером. gRPC поддерживает нечто подобное с двунаправленной потоковой передачей RPC, где оба параметра помечены модификатором `stream`.

### <a name="chatproto"></a>чат...

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

В предыдущем примере можно увидеть, что метод реализации получает поток запроса (`IAsyncStreamReader<MessageRequest>`) и поток ответа (`IServerStreamWriter<MessageResponse>`). Метод может считывать и записывать сообщения, пока соединение не будет закрыто.

### <a name="chatter-client"></a>Клиент chatter

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
>[Назад](wcf-bindings.md)
>[Вперед](metadata.md)
