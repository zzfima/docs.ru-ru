---
title: Фрагментация канала
ms.date: 03/30/2017
ms.assetid: e4d53379-b37c-4b19-8726-9cc914d5d39f
ms.openlocfilehash: 3811f7e7229dec1a46585a558b96f94bb202902f
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716033"
---
# <a name="chunking-channel"></a>Фрагментация канала

При отправке больших сообщений с помощью Windows Communication Foundation (WCF) часто желательно ограничить объем памяти, используемой для буферизации этих сообщений. Одним из возможных решений является потоковая передача тела сообщения (предполагая, что основной объем данных содержится в теле сообщения). Однако для некоторых протоколов требуется буферизация всего сообщения. Например, при надежном обмене сообщениями и необходимости обеспечения безопасности. Другим возможным решением является разделение большого сообщения на маленькие, называемые фрагментами, и отправка этих фрагментов поочередно с последующим восстановлением большого сообщения на получающей стороне. Приложение может выполнить фрагментацию и дефрагментацию самостоятельно или воспользоваться пользовательским каналом. В примере канала фрагментации показано, как можно использовать пользовательский протокол или многоуровневый канал для фрагментации и дефрагментации сообщений произвольного большого размера.

Фрагментация всегда должна применяться только после полного создания сообщения для отправки. Канал фрагментации всегда должен располагаться под каналом безопасности и каналом надежного сеанса.

> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\ChunkingChannel`

## <a name="chunking-channel-assumptions-and-limitations"></a>Канал фрагментации: допущения и ограничения

### <a name="message-structure"></a>Структура сообщения

Предполагается, что фрагментируемые сообщения, передаваемые в канал фрагментации, имеют следующую структуру.

```xml
<soap:Envelope ...>
  <!-- headers -->
  <soap:Body>
    <operationElement>
      <paramElement>data to be chunked</paramElement>
    </operationElement>
  </soap:Body>
</soap:Envelope>
```

При использовании пространства имен ServiceModel входные сообщения операций контракта, в которых используется один входной параметр, соответствуют этой форме сообщения. Аналогичным образом, выходные сообщения операций контракта, в которых имеется один выходной параметр или одно возвращаемое значение, соответствуют этой форме сообщения. Ниже приводятся примеры таких операций.

```csharp
[ServiceContract]
interface ITestService
{
    [OperationContract]
    Stream EchoStream(Stream stream);

    [OperationContract]
    Stream DownloadStream();

    [OperationContract(IsOneWay = true)]
    void UploadStream(Stream stream);
}
```

### <a name="sessions"></a>Сеансы

Требуется, чтобы сообщения доставлялись в канал фрагментации ровно один раз в порядке доставки сообщений (фрагментов). Это означает, что базовый стек канала должен быть сеансовым. Сеансы могу предоставляться транспортом (например, транспортом TCP) или сеансовым каналом протокола (например, каналом ReliableSession).

### <a name="asynchronous-send-and-receive"></a>Асинхронные отправка и получение

Методы асинхронной отправки и получения не реализуются в этой версии образца канала фрагментации.

## <a name="chunking-protocol"></a>Протокол фрагментации

Канал фрагментации определяет протокол, указывающий начало и конец последовательностей фрагментов, а также порядковый номер каждого фрагмента. В следующих трех примерах сообщений показаны исходное сообщение, фрагментированное сообщение и конечное сообщение с комментариями, описывающими основные аспекты.

### <a name="start-message"></a>Исходное сообщение

```xml
<s:Envelope xmlns:a="http://www.w3.org/2005/08/addressing"
            xmlns:s="http://www.w3.org/2003/05/soap-envelope">
  <s:Header>
<!--Original message action is replaced with a chunking-specific action. -->
    <a:Action s:mustUnderstand="1">http://samples.microsoft.com/chunkingAction</a:Action>
<!--
Original message is assigned a unique id that is transmitted
in a MessageId header. Note that this is different from the WS-Addressing MessageId header.
-->
    <MessageId s:mustUnderstand="1" xmlns="http://samples.microsoft.com/chunking">
53f183ee-04aa-44a0-b8d3-e45224563109
</MessageId>
<!--
ChunkingStart header signals the start of a chunked message.
-->
    <ChunkingStart s:mustUnderstand="1" i:nil="true" xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://samples.microsoft.com/chunking" />
<!--
Original message action is transmitted in OriginalAction.
This is required to re-create the original message on the other side.
-->
    <OriginalAction xmlns="http://samples.microsoft.com/chunking">
http://tempuri.org/ITestService/EchoStream
    </OriginalAction>
   <!--
    All original message headers are included here.
   -->
  </s:Header>
  <s:Body>
<!--
Chunking assumes this structure of Body content:
<element>
  <childelement>large data to be chunked<childelement>
</element>
The start message contains just <element> and <childelement> without
the data to be chunked.
-->
    <EchoStream xmlns="http://tempuri.org/">
      <stream />
    </EchoStream>
  </s:Body>
</s:Envelope>
```

### <a name="chunk-message"></a>Фрагментированное сообщение

```xml
<s:Envelope
  xmlns:a="http://www.w3.org/2005/08/addressing"
  xmlns:s="http://www.w3.org/2003/05/soap-envelope">
  <s:Header>
   <!--
    All chunking protocol messages have this action.
   -->
    <a:Action s:mustUnderstand="1">
      http://samples.microsoft.com/chunkingAction
    </a:Action>
<!--
Same as MessageId in the start message. The GUID indicates which original message this chunk belongs to.
-->
    <MessageId s:mustUnderstand="1"
               xmlns="http://samples.microsoft.com/chunking">
      53f183ee-04aa-44a0-b8d3-e45224563109
    </MessageId>
<!--
The sequence number of the chunk.
This number restarts at 1 with each new sequence of chunks.
-->
    <ChunkNumber s:mustUnderstand="1"
                 xmlns="http://samples.microsoft.com/chunking">
      1096
    </ChunkNumber>
  </s:Header>
  <s:Body>
<!--
The chunked data is wrapped in a chunk element.
The encoding of this data (and the entire message)
depends on the encoder used. The chunking channel does not mandate an encoding.
-->
    <chunk xmlns="http://samples.microsoft.com/chunking">
kfSr2QcBlkHTvQ==
    </chunk>
  </s:Body>
</s:Envelope>
```

### <a name="end-message"></a>Конечное сообщение

```xml
<s:Envelope xmlns:a="http://www.w3.org/2005/08/addressing"
            xmlns:s="http://www.w3.org/2003/05/soap-envelope">
  <s:Header>
    <a:Action s:mustUnderstand="1">
      http://samples.microsoft.com/chunkingAction
    </a:Action>
<!--
Same as MessageId in the start message. The GUID indicates which original message this chunk belongs to.
-->
    <MessageId s:mustUnderstand="1"
               xmlns="http://samples.microsoft.com/chunking">
      53f183ee-04aa-44a0-b8d3-e45224563109
    </MessageId>
<!--
ChunkingEnd header signals the end of a chunk sequence.
-->
    <ChunkingEnd s:mustUnderstand="1" i:nil="true"
                 xmlns:i="http://www.w3.org/2001/XMLSchema-instance"
                 xmlns="http://samples.microsoft.com/chunking" />
<!--
ChunkingEnd messages have a sequence number.
-->
    <ChunkNumber s:mustUnderstand="1"
                 xmlns="http://samples.microsoft.com/chunking">
      79
    </ChunkNumber>
  </s:Header>
  <s:Body>
<!--
The ChunkingEnd message has the same <element><childelement> structure
as the ChunkingStart message.
-->
    <EchoStream xmlns="http://tempuri.org/">
      <stream />
    </EchoStream>
  </s:Body>
</s:Envelope>
```

## <a name="chunking-channel-architecture"></a>Архитектура канала фрагментации

Канал фрагментации является каналом `IDuplexSessionChannel`, следующим стандартной архитектуре каналов на высоком уровне. `ChunkingBindingElement` может выполнить построение `ChunkingChannelFactory` и `ChunkingChannelListener`. `ChunkingChannelFactory` создает экземпляры `ChunkingChannel` при соответствующем запросе. `ChunkingChannelListener` создает экземпляры `ChunkingChannel`, когда принимается новый внутренний канал. `ChunkingChannel` отвечает за отправку и получение сообщений.

На следующем более низком уровне `ChunkingChannel` основывается на нескольких компонентах для реализации протокола фрагментации. На отправляющей стороне канал использует пользовательский <xref:System.Xml.XmlDictionaryWriter>, называемый `ChunkingWriter`, который непосредственно выполняет фрагментацию. `ChunkingWriter` непосредственно использует внутренний канал для отправки фрагментов данных. Использование пользовательского средства записи `XmlDictionaryWriter` позволяет отправлять фрагменты одновременно с записью большого тела исходного сообщения. Это означает, что все исходное сообщение не буферизуется.

![Схема, на которой показана архитектура отправки канала фрагментации.](./media/chunking-channel/chunking-channel-send.gif)

На получающей стороне `ChunkingChannel` извлекает сообщения из внутреннего канала и передает их в пользовательский <xref:System.Xml.XmlDictionaryReader>, называемый `ChunkingReader`, который восстанавливает исходное сообщение из входящих фрагментов данных. `ChunkingChannel` выступает в роли оболочки `ChunkingReader` в пользовательской реализации `Message`, называемой `ChunkingMessage`, и возвращает это сообщение на уровень выше. Данное сочетание `ChunkingReader` и `ChunkingMessage` позволяет дефрагментировать текст исходного сообщения в процессе его считывания вышележащим уровнем вместо необходимости помещения в буфер всего текста исходного сообщения. `ChunkingReader` имеет очередь, в которой буферизуются входящие фрагменты данных, пока их количество не достигнет заданного. При достижении максимального количества средство чтения ожидает, пока сообщения не будут извлечены из очереди вышестоящим уровнем (то есть прочитаны из тела исходного сообщения) или пока не истечет время ожидания получения максимального количества сообщений.

![Схема, на которой показана архитектура получения канала фрагментации.](./media/chunking-channel/chunking-channel-receive.gif)

## <a name="chunking-programming-model"></a>Модель программирования фрагментации

Разработчики службы могут указать, какие сообщения фрагментируются с применением атрибута `ChunkingBehavior` к операциям в контракте. Атрибут предоставляет свойство `AppliesTo`, позволяющее разработчику указать, применяется ли фрагментация к входящему или исходящему сообщению или к обоим сообщениям. В следующем примере показано применение атрибута `ChunkingBehavior`.

```csharp
[ServiceContract]
interface ITestService
{
    [OperationContract]
    [ChunkingBehavior(ChunkingAppliesTo.Both)]
    Stream EchoStream(Stream stream);

    [OperationContract]
    [ChunkingBehavior(ChunkingAppliesTo.OutMessage)]
    Stream DownloadStream();

    [OperationContract(IsOneWay=true)]
    [ChunkingBehavior(ChunkingAppliesTo.InMessage)]
    void UploadStream(Stream stream);

}
```

В этой модели программирования `ChunkingBindingElement` компилирует список универсальных кодов ресурса (URI) действия, в котором определяются фрагментируемые сообщения. Действие каждого исходящего сообщения сопоставляется с этим списком для определения, фрагментируется ли сообщение или отправляется непосредственно.

## <a name="implementing-the-send-operation"></a>Реализация операции отправки

На высоком уровне операция отправки вначале проверяет, следует ли фрагментировать исходящее сообщение, и, если фрагментация не требуется, отправляет сообщение непосредственно по внутреннему каналу.

Если сообщение должно быть фрагментировано, операция отправки создает новое средство записи `ChunkingWriter` и вызывает `WriteBodyContents` для исходящего сообщения, передавая его в `ChunkingWriter`. Затем `ChunkingWriter` выполняет фрагментацию сообщения (с копированием заголовков исходного сообщения в начальный фрагмент сообщения) и отправляет фрагменты по внутреннему каналу.

Следует отметить следующие моменты.

- Операция отправки сначала вызывает `ThrowIfDisposedOrNotOpened`, чтобы убедиться в том, что `CommunicationState` - открыто.

- Операция отправки синхронизируется таким образом, что во время каждого сеанса может быть отправлено только одно сообщение. Существует событие `ManualResetEvent` с именем `sendingDone`, которое сбрасывается при отправке фрагментированного сообщения. Это событие задается при отправке последнего фрагмента сообщения. Перед отправкой исходящего сообщения метод отправки ожидает задания этого события.

- Метод отправки блокирует `CommunicationObject.ThisLock` для предотвращения изменения состояния синхронизации при отправке. См. документацию по <xref:System.ServiceModel.Channels.CommunicationObject> для получения дополнительной информации о конечных автоматах и состояниях <xref:System.ServiceModel.Channels.CommunicationObject>.

- Время ожидания, передаваемое в метод отправки, используется как время ожидания выполнения всей операции отправки, то есть отправки всех фрагментов.

- Пользовательская разработка <xref:System.Xml.XmlDictionaryWriter> выбрана с целью избежать буферизации всего тела исходного сообщения. При необходимости применить <xref:System.Xml.XmlDictionaryReader> к телу сообщения, используя `message.GetReaderAtBodyContents`, была бы выполнена буферизация всего тела сообщения. Вместо этого у нас есть пользовательский <xref:System.Xml.XmlDictionaryWriter>, который передается `message.WriteBodyContents`. Так как сообщение вызывает WriteBase64 для средства записи, средство записи упаковывает фрагменты в сообщения и отправляет их по внутреннему каналу. WriteBase64 выполняет блокировку пока фрагмент не будет отправлен.

## <a name="implementing-the-receive-operation"></a>Реализация операции получения

На высоком уровне операция получения сперва проверяет, что входящее сообщение не является `null` и его действием является `ChunkingAction`. Если сообщение не соответствует обоим указанным критериям, оно возвращается из операции получения без изменений. В противном случае операция получения создает новое средство чтения `ChunkingReader` и новое `ChunkingMessage`, для которого оно является оболочкой (вызывая `GetNewChunkingMessage`). Перед возвратом нового `ChunkingMessage`, операция получения использует поток из пула потоков для выполнения операции `ReceiveChunkLoop`, которая вызывает в цикле метод `innerChannel.Receive` и передает фрагменты в `ChunkingReader`, пока не будет получен последний фрагмент сообщения или не истечет время ожидания выполнения операции получения.

Следует отметить следующие моменты.

- Аналогично операции отправки, операция получения сначала вызывает `ThrowIfDisposedOrNotOepned`, чтобы убедиться в том, что `CommunicationState` - открыто.

- Операция получения также синхронизируется таким образом, что во время каждого сеанса может быть получено только одно сообщение. Это особенно важно, так как после того, как получен начальный фрагмент сообщения, ожидается, что все последующие сообщения являются фрагментами этой новой последовательности фрагментов до получения конечного фрагмента сообщения. Операция получения не может извлекать сообщения из внутреннего канала до тех пор, пока все фрагменты сообщения, дефрагментируемого в настоящий момент, не будут получены. Чтобы выполнить это действие, операция получения использует событие `ManualResetEvent` с именем `currentMessageCompleted`, которое задается при получении последнего фрагмента сообщения и сбрасывается при получении нового начального фрагмента сообщения.

- В отличие от операции отправки, операция получения не препятствует синхронизированным переходам между состояниями при получении. Например, операция "Закрыть" может быть вызвана при выполнении операции получения; она будет выполнена по окончании получения исходного сообщения или по истечении заданного времени ожидания.

- Время ожидания, передаваемое в метод получения, используется как время ожидания выполнения всей операции получения, то есть получения всех фрагментов.

- Если уровень, считывающий сообщение, считывает тело сообщения с частотой более низкой, чем частота входящих фрагментов сообщения, `ChunkingReader` выполняет буферизацию входящих фрагментов до предела, установленного `ChunkingBindingElement.MaxBufferedChunks`. При достижении заданного предела фрагменты не извлекаются из более низкого уровня до тех пор, пока не будет считан буферизованный фрагмент или не истечет время ожидания выполнения операции получения.

## <a name="communicationobject-overrides"></a>CommunicationObject - переопределения

### <a name="onopen"></a>OnOpen

`OnOpen` вызывает `innerChannel.Open`, чтобы открыть внутренний канал.

### <a name="onclose"></a>OnClose

`OnClose` сначала задает `stopReceive` значение `true`, чтобы указать, что требуется остановить выполняющийся `ReceiveChunkLoop`. Затем он ожидает `receiveStopped` <xref:System.Threading.ManualResetEvent>, который задается при остановке `ReceiveChunkLoop`. Предполагая, что `ReceiveChunkLoop` остановится в течение заданного времени ожидания, `OnClose` вызывает `innerChannel.Close` с остающимся временем ожидания.

### <a name="onabort"></a>OnAbort

`OnAbort` вызывает `innerChannel.Abort`, чтобы прервать внутренний канал. Если имеется выполняемый `ReceiveChunkLoop`, он возвращает исключение от выполняемого вызова `innerChannel.Receive`.

### <a name="onfaulted"></a>OnFaulted

Для `ChunkingChannel` не требуется специальное поведение при возникновении ошибки в канале, поэтому `OnFaulted` не переопределяется.

## <a name="implementing-channel-factory"></a>Реализация фабрики каналов

`ChunkingChannelFactory` отвечает за создание экземпляров каналов `ChunkingDuplexSessionChannel` и выполнение каскадных переходов состояний в фабрику внутренних каналов.

`OnCreateChannel` использует фабрику внутренних каналов для создания внутреннего канала `IDuplexSessionChannel`. Затем метод создает новый `ChunkingDuplexSessionChannel`, передавая ему этот внутренний канал вместе со списком действий фрагментируемых сообщений и максимальным количеством фрагментов, буферизуемых при получении. Список фрагментируемых сообщений и максимальное количество буферизуемых фрагментов - это два параметра, передаваемые `ChunkingChannelFactory` в его конструкторе. В разделе об `ChunkingBindingElement` описывается, откуда возникают эти значения.

Методы `OnOpen`, `OnClose`, `OnAbort` и их асинхронные эквиваленты вызывают соответствующий метод перехода между состояниями в фабрике внутренних каналов.

## <a name="implementing-channel-listener"></a>Реализация прослушивателя каналов

`ChunkingChannelListener` является оболочкой прослушивателя внутренних каналов. Его основной функцией, помимо делегирования вызовов в прослушиватель внутренних каналов, является создание новой программы-оболочки `ChunkingDuplexSessionChannels` для каналов, принимаемых из прослушивателя внутренних каналов. Это выполняется в методах `OnAcceptChannel` и `OnEndAcceptChannel`. Созданная `ChunkingDuplexSessionChannel` передается во внутренний канал вместе с другими ранее описанными параметрами.

## <a name="implementing-binding-element-and-binding"></a>Реализация элемента привязки и привязки

Элемент `ChunkingBindingElement` отвечает за создание фабрики `ChunkingChannelFactory` и прослушивателя `ChunkingChannelListener`. `ChunkingBindingElement` проверяет, что T в `CanBuildChannelFactory`\<T > и `CanBuildChannelListener`\<T > относится к типу `IDuplexSessionChannel` (единственный канал, поддерживаемый каналом фрагментирования) и что другие элементы привязки в привязке поддерживают этот тип канала.

`BuildChannelFactory`\<T > сначала проверяет, можно ли построить запрошенный тип канала, а затем получает список действий с сообщениями, которые будут фрагментированы. Дополнительные сведения см. в следующем разделе. Затем метод создает новую фабрику `ChunkingChannelFactory`, передавая ей фабрику внутренних каналов (возвращенную из `context.BuildInnerChannelFactory<IDuplexSessionChannel>`), список действий фрагментируемых сообщений и максимальное количество буферизуемых фрагментов. Максимальное количество фрагментов определяется свойством `MaxBufferedChunks`, предоставляемым `ChunkingBindingElement`.

`BuildChannelListener<T>` имеет аналогичную реализацию для создания прослушивателя `ChunkingChannelListener` и передаче его прослушивателю внутреннего канала.

Пример привязки включен в пример `TcpChunkingBinding`. Эта привязка состоит из двух элементов привязки: `TcpTransportBindingElement` и `ChunkingBindingElement`. Помимо предоставления свойства `MaxBufferedChunks`, привязка также задает некоторые свойства `TcpTransportBindingElement`, например `MaxReceivedMessageSize` (задает ему значение `ChunkingUtils.ChunkSize` + 100 КБ байтов для заголовков).

`TcpChunkingBinding` также реализует `IBindingRuntimePreferences` и возвращает значение "true" из метода `ReceiveSynchronously`, означающее, что реализуются только синхронные вызовы операции получения.

### <a name="determining-which-messages-to-chunk"></a>Какие сообщения следует фрагментировать

Канал фрагментации фрагментирует только сообщения, определенные посредством атрибута `ChunkingBehavior`. Класс `ChunkingBehavior` реализует метод `IOperationBehavior` и реализуется с помощью вызова метода `AddBindingParameter`. В этом методе `ChunkingBehavior` проверяет значение свойства `AppliesTo` (`InMessage`, `OutMessage` или обоих), чтобы определить, какие сообщения следует фрагментировать. Затем он возвращает действие для каждого сообщения (из коллекции сообщений в `OperationDescription`) и добавляет их в коллекцию строк, содержащуюся в экземпляре `ChunkingBindingParameter`. Затем он добавляет этот параметр `ChunkingBindingParameter` в предоставленную коллекцию `BindingParameterCollection`.

`BindingParameterCollection` передается внутри `BindingContext` каждому элементу привязки в привязке при построении этим элементом привязки фабрики каналов или прослушивателя каналов. Реализация `ChunkingBindingElement``BuildChannelFactory<T>` и `BuildChannelListener<T>` извлекать это `ChunkingBindingParameter` из `BindingContext’`, `BindingParameterCollection`. Коллекция действий, содержащихся в параметре `ChunkingBindingParameter`, затем передается в фабрику `ChunkingChannelFactory` или прослушиватель `ChunkingChannelListener`, которые, в свою очередь, передают ее в канал `ChunkingDuplexSessionChannel`.

## <a name="running-the-sample"></a>Запуск примера

#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца

1. Установите ASP.NET 4,0 с помощью следующей команды.

    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

3. Чтобы выполнить сборку решения, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).

4. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).

5. Сначала запустите файл Service.exe, затем Client.exe и наблюдайте результат в обоих окнах консоли.

При выполнении этого образца ожидаются следующие выходные данные.

Клиент:

```console
Press enter when service is available

 > Sent chunk 1 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 2 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 3 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 4 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 5 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 6 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 7 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 8 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 9 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 10 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 1 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 2 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 3 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 4 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 5 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 6 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 7 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 8 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 9 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 10 of message 5b226ad5-c088-4988-b737-6a565e0563dd
```

Сервер.

```console
Service started, press enter to exit
 < Received chunk 1 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 2 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 3 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 4 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 5 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 6 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 7 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 8 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 9 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 10 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 1 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 2 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 3 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 4 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 5 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 6 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 7 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 8 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 9 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 10 of message 5b226ad5-c088-4988-b737-6a565e0563dd
```
