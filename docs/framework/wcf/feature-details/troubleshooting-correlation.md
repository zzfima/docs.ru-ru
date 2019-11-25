---
title: Устранение неполадок корреляции
ms.date: 03/30/2017
ms.assetid: 98003875-233d-4512-a688-4b2a1b0b5371
ms.openlocfilehash: be48a55a87d199829de4038e7e2a7642c102acf2
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976018"
---
# <a name="troubleshooting-correlation"></a>Устранение неполадок корреляции
Корреляция позволяет сопоставлять сообщения службы рабочего процесса друг с другом и с нужным экземпляром рабочего процесса. Если же корреляция настроена неправильно, то сообщения не будут приниматься и приложения будут работать неправильно. В этом разделе даны общие сведения о нескольких методах устранения неполадок корреляции, а также перечислен ряд распространенных проблем, которые возникают при использовании корреляции.

## <a name="handle-the-unknownmessagereceived-event"></a>Обработка события UnknownMessageReceived
 Событие <xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived> происходит, когда служба получает неизвестное сообщение, в том числе сообщение, для которого не удается выполнить корреляцию с существующим экземпляром. Для резидентных служб это событие можно обрабатывать в ведущем приложении.

```csharp
host.UnknownMessageReceived += delegate(object sender, UnknownMessageReceivedEventArgs e)
{
    Console.WriteLine("Unknown Message Received:");
    Console.WriteLine(e.Message);
};
```

 Для служб, размещенных на веб-сервере, это событие можно обработать, создав класс, производный от <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory>, и переопределив метод <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory.CreateWorkflowServiceHost%2A>.

```csharp
class CustomFactory : WorkflowServiceHostFactory
{
    protected override WorkflowServiceHost CreateWorkflowServiceHost(Activity activity, Uri[] baseAddresses)
    {
        // Create the WorkflowServiceHost.
        WorkflowServiceHost host = new WorkflowServiceHost(activity, baseAddresses);

        // Handle the UnknownMessageReceived event.
        host.UnknownMessageReceived += delegate(object sender, UnknownMessageReceivedEventArgs e)
        {
            Console.WriteLine("Unknown Message Received:");
            Console.WriteLine(e.Message);
        };

        return host;
    }
}
```

 Затем этот настраиваемый объект <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory> можно указать в файле `svc` для службы.

`<% @ServiceHost Language="C#" Service="OrderServiceWorkflow" Factory="CustomFactory" %>`

 Когда вызывается этот обработчик, сообщение можно получить через свойство <xref:System.ServiceModel.UnknownMessageReceivedEventArgs.Message%2A> объекта <xref:System.ServiceModel.UnknownMessageReceivedEventArgs>. Оно будет выглядеть следующим образом.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header>
    <To s:mustUnderstand="1" xmlns="http://schemas.microsoft.com/ws/2005/05/addressing/none">http://localhost:8080/OrderService</To>
    <Action s:mustUnderstand="1" xmlns="http://schemas.microsoft.com/ws/2005/05/addressing/none">http://tempuri.org/IService/AddItem</Action>
  </s:Header>
  <s:Body>
    <AddItem xmlns="http://tempuri.org/">
      <Item>Books</Item>
    </AddItem>
  </s:Body>
</s:Envelope>
```

 Проверка сообщений, передаваемых в обработчик события <xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived>, может помочь понять, почему не выполнена корреляция сообщения с экземпляром службы рабочего процесса.

## <a name="use-tracking-to-monitor-the-progress-of-the-workflow"></a>Использование отслеживания для наблюдения за ходом рабочего процесса
 Отслеживание позволяет наблюдать за ходом рабочего процесса. По умолчанию записи отслеживания создаются для событий жизненного цикла рабочего процесса, событий жизненного цикла действия, распространения ошибок и возобновления закладок. Кроме того, настраиваемые действия могут создавать настраиваемые записи отслеживания. При устранении неполадок корреляции наиболее полезны записи отслеживания действий, записи возобновления закладок и записи распространения ошибок. Записи отслеживания действий позволяют определить текущий ход выполнения рабочего процесса и выявить действие обмена сообщения, которое в данный момент ожидает сообщений. Записи возобновления закладок полезны, поскольку в них указывается, что сообщение получено рабочим процессом, а в записях распространения ошибок регистрируются все ошибки в рабочем процессе. Чтобы включить отслеживание, укажите нужный объект <xref:System.Activities.Tracking.TrackingParticipant> в свойстве <xref:System.ServiceModel.Activities.WorkflowServiceHost.WorkflowExtensions%2A> объекта <xref:System.ServiceModel.Activities.WorkflowServiceHost>. В следующем примере `ConsoleTrackingParticipant` (из примера [настраиваемого отслеживания](../../../../docs/framework/windows-workflow-foundation/samples/custom-tracking.md) ) настраивается с помощью профиля отслеживания по умолчанию.

```csharp
host.WorkflowExtensions.Add(new ConsoleTrackingParticipant());
```

 Участник отслеживания, такой как ConsoleTrackingParticipant, удобен для резидентных служб рабочего процесса с окном консоли. Для службы, размещенной в Интернете, следует использовать участника отслеживания, который записывает данные отслеживания в долговременное хранилище, например встроенные <xref:System.Activities.Tracking.EtwTrackingParticipant>или пользовательский участник отслеживания, который записывает данные в файл.

 Дополнительные сведения об отслеживании и настройке отслеживания для службы рабочего процесса, размещенной в веб-среде, см. в разделе [Отслеживание и трассировка рабочих процессов](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md), [Настройка отслеживания для рабочего процесса](../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md)и примеры [отслеживания &#91;примеров&#93; WF](../../../../docs/framework/windows-workflow-foundation/samples/tracking.md) .

## <a name="use-wcf-tracing"></a>Использование трассировки WCF
 Трассировка WCF отслеживает поток входящих и исходящих сообщений для службы рабочего процесса. Данные такой трассировки удобны при устранении неполадок корреляции, особенно для корреляции по содержимому. Чтобы включить трассировку, укажите нужные прослушиватели трассировки в разделе `system.diagnostics` файла `web.config` для службы рабочего процесса, размещенной на веб-сервере, или файла `app.config` для резидентной службы рабочего процесса. Чтобы включить содержимое сообщений в файл трассировки, укажите значение `true` для атрибута `logEntireMessage` в элементе `messageLogging` в разделе `diagnostics` объекта `system.serviceModel`. В следующем примере для данных трассировки, включая содержимое сообщений, задается запись в файл с именем `service.svclog`.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.diagnostics>
    <sources>
      <source name="System.ServiceModel" switchValue="Information" propagateActivity="true">
        <listeners>
          <add name="corr"/>
        </listeners>
      </source>
      <source name="System.ServiceModel.MessageLogging">
        <listeners>
          <add name="corr"/>
        </listeners>
      </source>
    </sources>

    <sharedListeners>
      <add name="corr" type="System.Diagnostics.XmlWriterTraceListener" initializeData="c:\logs\service.svclog">
      </add>
    </sharedListeners>
  </system.diagnostics>

  <system.serviceModel>
    <diagnostics>
      <messageLogging logEntireMessage="true" logMalformedMessages="false"
         logMessagesAtServiceLevel="false" logMessagesAtTransportLevel="true" maxSizeOfMessageToLog="2147483647">
      </messageLogging>
    </diagnostics>
  </system.serviceModel>
</configuration>
```

 Чтобы просмотреть сведения о трассировке, содержащиеся в `service.svclog`, используется [средство просмотра трассировки службы (SvcTraceViewer. exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) . Оно особенно полезно при устранении неполадок корреляции по содержимому, поскольку можно просматривать содержимое сообщений, точно определять переданные данные и проверять соответствие <xref:System.ServiceModel.CorrelationQuery> для корреляции по содержимому. Дополнительные сведения о трассировке WCF см. в разделе [Service Trace Viewer Tool (SvcTraceViewer. exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md), [Настройка трассировки](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)и [Использование трассировки для устранения неполадок в приложении](../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).

## <a name="common-context-exchange-correlation-issues"></a>Распространенные проблемы корреляции обмена контекстом
 Для правильной работы некоторых типов корреляции необходимо использовать определенный тип привязки. Примерами служат корреляция по схеме «запрос-ответ», где требуется двусторонняя привязка, такая как <xref:System.ServiceModel.BasicHttpBinding>, и корреляция обмена контекстом, для которой требуется привязка на основе контекста, такая как <xref:System.ServiceModel.BasicHttpContextBinding>. Большинство привязок поддерживают двусторонние операции, поэтому проблема совместимости редко возникает для корреляции по схеме «запрос-ответ», однако существует лишь небольшое число привязок на основе контекста, включая <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding> и <xref:System.ServiceModel.NetTcpContextBinding>. Если не используется одна из этих привязок, то первый вызов службы рабочего процесса завершится успешно, однако последующие вызовы завершатся ошибкой со следующим исключением <xref:System.ServiceModel.FaultException>.

```output
There is no context attached to the incoming message for the service
and the current operation is not marked with "CanCreateInstance = true".
In order to communicate with this service check whether the incoming binding
supports the context protocol and has a valid context initialized.
```

 Данные контекста, используемые для корреляции контекста, можно вернуть из <xref:System.ServiceModel.Activities.SendReply> в действие <xref:System.ServiceModel.Activities.Receive>, которое инициализирует корреляцию контекста, если используется двусторонняя операция, или указать в вызывающем объекте в случае односторонней операции. Если контекст не отправляется вызывающим объектом и не возвращается службой рабочего процесса, то при вызове последующей операции будет возвращаться исключение <xref:System.ServiceModel.FaultException>, описанное ранее.

## <a name="common-request-reply-correlation-issues"></a>Распространенные проблемы корреляции по схеме «запрос-ответ»
 Корреляция "запрос-ответ" используется с парой <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> для реализации двусторонней операции в службе рабочего процесса и с парой <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply>, которая вызывает двустороннюю операцию в другой веб-службе. При вызове двусторонней операции в службе WCF эта служба может быть традиционной процедурой службы WCF, основанной на коде, или службой рабочего процесса. Для корреляции «запрос-ответ» необходимо использовать двустороннюю привязку, такую как <xref:System.ServiceModel.BasicHttpBinding>, и операции должны быть двусторонними.

 Если служба рабочего процесса поддерживает параллельные операции или перекрываются <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> или <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply>, то неявное управление маркерами корреляции, предоставляемое <xref:System.ServiceModel.Activities.WorkflowServiceHost>, может быть недостаточно, особенно в сценариях с высокой нагрузкой, и сообщения могут неправильно маршрутизироваться. Чтобы предотвратить эту проблему, рекомендуется всегда явно указывать <xref:System.ServiceModel.Activities.CorrelationHandle> при использовании корреляции «запрос-ответ». При использовании шаблонов **SendAndReceiveReply** и **ReceiveAndSendReply** из раздела Обмен сообщениями **области элементов** в конструкторе рабочих процессов по умолчанию явно настраивается <xref:System.ServiceModel.Activities.CorrelationHandle>. Если рабочий процесс создается из программного кода, то дескриптор <xref:System.ServiceModel.Activities.CorrelationHandle> указывается в свойстве <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> первого действия из пары. В следующем примере действие <xref:System.ServiceModel.Activities.Receive> настраивается с явным дескриптором <xref:System.ServiceModel.Activities.CorrelationInitializer.CorrelationHandle%2A>, указанным в <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>.

```csharp
Variable<CorrelationHandle> RRHandle = new Variable<CorrelationHandle>();

Receive StartOrder = new Receive
{
    CanCreateInstance = true,
    ServiceContractName = OrderContractName,
    OperationName = "StartOrder",
    CorrelationInitializers =
    {
        new RequestReplyCorrelationInitializer
        {
            CorrelationHandle = RRHandle
        }
    }
};

SendReply ReplyToStartOrder = new SendReply
{
    Request = StartOrder,
    Content = ... // Contains the return value, if any.
};

// Construct a workflow using StartOrder and ReplyToStartOrder.
```

 Не допускается использование сохраняемости между парой <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> или парой <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply>. Создается зона несохраняемости, которая существует до завершения обоих действий. Если действие, например действие Delay, находится в этой зоне несохраняемости и вызывает переход рабочего процесса в состояние бездействия, рабочий поток не будет сохранен, даже если узел настроен на сохранение рабочих потоков после их перехода в состояние бездействия. Если действие, например действие Persist, пытается выполнить явное сохранение в зоне несохраняемости, формируется неустранимое исключение, выполнение рабочего процесса прерывается, а вызывающему возвращается исключение <xref:System.ServiceModel.FaultException>. Сообщение о неустранимом исключении: «System.InvalidOperationException: действия Persist не могут содержаться в блоках несохраняемости». Это исключение не возвращается вызывающему, его можно обнаружить, если включено отслеживание. Сообщение об исключении <xref:System.ServiceModel.FaultException>, возвращаемое вызывающему: «Операцию выполнить не удалось, потому что рабочий процесс '5836145b-7da2-49d0-a052-a49162adeab6' завершился».

 Дополнительные сведения о корреляции запросов и ответов см. в разделе [запрос-ответ](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md).

## <a name="common-content-correlation-issues"></a>Распространенные проблемы корреляции по содержимому
 Корреляция по содержимому применяется, если служба рабочего процесса получает несколько сообщений, а нужный экземпляр определяется по некоторому фрагменту данных в передаваемых сообщениях. При корреляции по содержимому такие данные в сообщении, например номер заказчика или идентификатор заказа, используются для маршрутизации сообщений в нужный экземпляр рабочего процесса. В этом разделе описан ряд распространенных проблем, которые возникают при использовании корреляции по содержимому.

### <a name="ensure-the-identifying-data-is-unique"></a>Убедитесь, что определяющие данные уникальны
 Данные, используемые для идентификации экземпляра, хэшируются в ключ корреляции. Необходимо обеспечить уникальность данных, используемых для корреляции. В противном случае в хэшированном ключе могут возникнуть конфликты, которые приведут к неправильной маршрутизации сообщений. Например, корреляция на основе только имени заказчика может вызвать конфликт, так как возможно наличие заказчиков с одинаковыми именами. Двоеточие (:) не должно встречаться в данных, используемых для корреляции сообщений, так как оно уже применяется в качестве разделителя ключа и значения в запросе сообщения, формирующих строку, которая затем хэшируется. Если используется сохраняемость, убедитесь, что текущие определяющие данные не используются в ранее сохраненном экземпляре. Эту проблему можно выявить, временно отключив сохраняемость. С помощью трассировки WCF можно просмотреть вычисленный ключ корреляции. Такая трассировка полезна в отладке проблем с ключом корреляции.

### <a name="race-conditions"></a>Конфликты
 Между получением сообщения службой и инициализацией корреляции проходит некоторое время, в течение которого последующие сообщения будут пропускаться. Если служба рабочего процесса инициализирует корреляцию по содержимому с использованием данных, переданных от клиента через одностороннюю операцию, а вызывающий объект немедленно отправляет последующие сообщения, то такие сообщения будут пропускаться в течение этого интервала. Чтобы избежать этого, используйте для инициализации корреляции двустороннюю операцию или используйте действие <xref:System.ServiceModel.Activities.TransactedReceiveScope>.

### <a name="correlation-query-issues"></a>Проблемы с запросами корреляции
 Запросы корреляции указывают, какие данные в сообщении используются для корреляции сообщения. Эти данные указываются с помощью запроса XPath. Если сообщения в службу не доставляются, хотя ошибки не обнаруживаются, то одним из приемов диагностики является указание вместо запроса XPath литерального значения, совпадающего со значением данных сообщения. Чтобы указать литеральное значение, используйте функцию `string`. В следующем примере <xref:System.ServiceModel.MessageQuerySet> настраивается для использования литерального значения `11445` для `OrderId`, а запрос XPath помещается в комментарий.

```csharp
MessageQuerySet = new MessageQuerySet
{
    {
        "OrderId",
        //new XPathMessageQuery("sm:body()/tempuri:StartOrderResponse/tempuri:OrderId")
        new XPathMessageQuery("string('11445')")
    }
}
```

 Если запрос XPath настроен неправильно, в результате чего данные о корреляции не возвращаются, возвращается ошибка со следующим сообщением: «Запрос корреляции возвратил пустой результирующий набор. Проверьте правильность настройки запросов корреляции для данной конечной точки». Одним из быстрых способов решения этой проблемы является замена запроса XPath на литеральное значение, как описано в предыдущем разделе. Эта проблема может возникнуть при использовании построителя запросов XPath в диалоговых окнах **Добавление инициализаторов корреляции** или **определения CorrelatesOn** , когда служба рабочего процесса использует контракты сообщений. В следующем примере определяется класс контракта сообщения.

```csharp
[MessageContract]
public class AddItemMessage
{
    [MessageHeader]
    public string CartId;

    [MessageBodyMember]
    public string Item;
}
```

 В рабочем процессе этот контракт сообщения используется действием <xref:System.ServiceModel.Activities.Receive>. Идентификатор `CartId` в заголовке сообщения используется для корреляции сообщения с правильным экземпляром. Если запрос XPath, возвращающий идентификатор `CartId`, создается с помощью диалоговых окон корреляции в конструкторе рабочих процессов, формируется следующий неверный запрос XPath.

```
sm:body()/xg0:AddItemMessage/xg0:CartId
```

 Этот запрос XPath был бы правильным, если бы действие <xref:System.ServiceModel.Activities.Receive> использовало параметры для данных, но, поскольку оно использует контракт сообщения, запрос является неверным. Следующий запрос XPath является правильным для получения идентификатора `CartId` из заголовка.

```
sm:header()/tempuri:CartId
```

Это можно проверить, изучив текст сообщения.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header>
    <Action s:mustUnderstand="1" xmlns="http://schemas.microsoft.com/ws/2005/05/addressing/none">http://tempuri.org/IService/AddItem</Action>
    <h:CartId xmlns:h="http://tempuri.org/">80c95b41-c98d-4660-a6c1-99412206e54c</h:CartId>
  </s:Header>
  <s:Body>
    <AddItemMessage xmlns="http://tempuri.org/">
      <Item>Books</Item>
    </AddItemMessage>
  </s:Body>
</s:Envelope>
```

В следующем примере показано действие <xref:System.ServiceModel.Activities.Receive>, настроенное для операции `AddItem`, использующей предыдущий контракт сообщения для получения данных. Запрос XPath настроен правильно.

```xaml
<Receive CorrelatesWith="[CCHandle] OperationName="AddItem" ServiceContractName="p:IService">
  <Receive.CorrelatesOn>
    <XPathMessageQuery x:Key="key1">
      <XPathMessageQuery.Namespaces>
        <ssx:XPathMessageContextMarkup>
          <x:String x:Key="xg0">http://schemas.datacontract.org/2004/07/MessageContractWFService</x:String>
        </ssx:XPathMessageContextMarkup>
      </XPathMessageQuery.Namespaces>sm:header()/tempuri:CartId</XPathMessageQuery>
  </Receive.CorrelatesOn>
  <ReceiveMessageContent DeclaredMessageType="m:AddItemMessage">
    <p1:OutArgument x:TypeArguments="m:AddItemMessage">[AddItemMessage]</p1:OutArgument>
  </ReceiveMessageContent>
</Receive>
```
