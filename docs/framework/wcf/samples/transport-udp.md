---
title: 'Транспорт: UDP'
ms.date: 03/30/2017
ms.assetid: 738705de-ad3e-40e0-b363-90305bddb140
ms.openlocfilehash: fab15b1d4dab61de37f4b609a6e43c5f4a32fb75
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "74138687"
---
# <a name="transport-udp"></a>Транспорт: UDP
В примере транспорта UDP демонстрируется реализация одноадресной и многоадресной рассылки по протоколу UDP в качестве настраиваемого транспорта Windows Communication Foundation (WCF). В этом примере описывается рекомендуемая процедура создания пользовательского транспорта в WCF с помощью платформы Channel и следующих рекомендаций по WCF. Для создания пользовательского транспорта выполните следующие действия.  
  
1. Определите, какие из [шаблонов обмена сообщениями](#MessageExchangePatterns) каналов (IOutputChannel, IInputChannel, IDuplexChannel, IRequestChannel или IReplyChannel) будут поддерживаться для ChannelFactory и ChannelListener. Затем решите, поддерживать ли связанные с сеансами разновидности указанных интерфейсов.  
  
2. Создайте фабрику и прослушиватель каналов, которые поддерживают выбранный шаблон обмена сообщениями.  
  
3. Убедитесь, что все исключения, связанные с сетью, нормализованы в соответствующий класс, унаследованный от <xref:System.ServiceModel.CommunicationException>.  
  
4. Добавьте элемент [> привязки\<](../../configure-apps/file-schema/wcf/bindings.md) , который добавляет пользовательский транспорт в стек каналов. Дополнительные сведения см. [в разделе Добавление элемента привязки](#AddingABindingElement).  
  
5. Добавьте раздел расширения элементов привязки, чтобы представить новый элемент привязки системе конфигурации.  
  
6. Добавьте расширения метаданных, чтобы сообщить о возможностях в другие конечные точки.  
  
7. Добавьте привязку, которая предварительно настраивает стек элементов привязки в соответствии с четко определенным профилем. Дополнительные сведения см. [в разделе Добавление стандартной привязки](#AddingAStandardBinding).  
  
8. Добавьте раздел привязки и элемент конфигурации привязки, чтобы представить привязку системе конфигурации. Дополнительные сведения см. в разделе [Добавление поддержки конфигурации](#AddingConfigurationSupport).  
  
<a name="MessageExchangePatterns"></a>   
## <a name="message-exchange-patterns"></a>Шаблоны обмена сообщениями  
 При создании пользовательского транспорта в первую очередь решите, какие шаблоны обмена сообщениями требуются для транспорта. Можно выбирать из трех шаблонов обмена сообщениями.  
  
- Датаграмма (IInputChannel/IOutputChannel)  
  
     При использовании шаблона обмена сообщениями "датаграмма" клиент отправляет сообщения, используя принцип "отправить и забыть". В этом случае требуется внешнее подтверждение успешной доставки. Сообщение может быть потеряно при передаче и может не достичь службы. Если операция отправки успешно выполняется на стороне клиента, это не гарантирует, что удаленная конечная точка получит сообщение. Датаграмма - фундаментальный элемент обмена сообщениями, на основе которого можно строить собственные протоколы, в том числе надежные и безопасные. Каналы датаграмм клиентов реализуют интерфейс <xref:System.ServiceModel.Channels.IOutputChannel>, а каналы датаграмм служб - интерфейс <xref:System.ServiceModel.Channels.IInputChannel>.  
  
- Запрос-ответ (IRequestChannel/IReplyChannel)  
  
     При использовании этого шаблона происходит отправка сообщения и получение ответа. Шаблон состоит из пар «запрос-ответ». Примеры вызовов "запрос-ответ" - удаленные вызовы процедур и запросы GET браузера. Этот шаблон также называют полудуплексным. При использовании этого шаблона обмена сообщениями каналы клиентов реализуют интерфейс <xref:System.ServiceModel.Channels.IRequestChannel>, а каналы служб - интерфейс <xref:System.ServiceModel.Channels.IReplyChannel>.  
  
- Дуплекс (IDuplexChannel)  
  
     Дуплексный шаблон обмена сообщениями позволяет клиенту отправлять произвольное количество сообщений и принимать их в произвольном порядке. Применение дуплексного шаблона похоже на разговор по телефону, когда каждое произносимое слово является сообщением. Поскольку в данном случае принимать и отправлять сообщения могут обе стороны, каналы клиента и службы реализуют интерфейс <xref:System.ServiceModel.Channels.IDuplexChannel>.  
  
 Каждый из этих шаблонов обмена сообщениями также поддерживает сеансы. Канал, поддерживающий сеансы, содержит функции для согласования всех сообщений, отправляемых и принимаемых через канал. Шаблон "запрос-ответ" является отдельным сеансом из двух сообщений, поскольку запрос и ответ связаны друг с другом. В отличие от него в поддерживающем сеансы шаблоне "запрос-ответ" предполагается, что все пары "запрос-ответ" в канале связаны друг с другом. Таким образом, можно выбирать один из шести шаблонов: датаграмма, "запрос-ответ", дуплекс, датаграмма с поддержкой сеансов, "запрос-ответ" с поддержкой сеансов и дуплекс с поддержкой сеансов.  
  
> [!NOTE]
> Для транспорта по протоколу UDP единственным поддерживаемым шаблоном обмена сообщениями является датаграмма, поскольку структура протокола UDP основана на принципе "отправить и забыть".  
  
### <a name="the-icommunicationobject-and-the-wcf-object-lifecycle"></a>Жизненный цикл ICommunicationObject и объектов WCF  
 В WCF имеется общий конечный автомат, используемый для управления жизненным циклом объектов, таких как <xref:System.ServiceModel.Channels.IChannel>, <xref:System.ServiceModel.Channels.IChannelFactory>и <xref:System.ServiceModel.Channels.IChannelListener>, которые используются для связи. Эти объекты взаимодействий могут находиться в пяти состояниях. Эти состояния, приведенные ниже, представлены перечислением <xref:System.ServiceModel.CommunicationState>.  
  
- Создано: это состояние <xref:System.ServiceModel.ICommunicationObject> при первом создании экземпляра. Ввод и вывод в этом состоянии не происходит.  
  
- Открытие: объекты переходят в это состояние при вызове <xref:System.ServiceModel.ICommunicationObject.Open%2A>. В этот момент свойства перестают быть изменяемыми, и могут начинаться ввод и вывод. Переход в это состояние возможен только из состояния Created.  
  
- Opened: в это состояние объекты переходят по окончании процесса открытия. Переход в это состояние возможен только из состояния Opening. С этого момента объект полностью пригоден для передачи сообщений.  
  
- Закрытие: объекты переходят в это состояние при вызове <xref:System.ServiceModel.ICommunicationObject.Close%2A> для корректного завершения работы. Переход в это состояние возможен только из состояния Opened.  
  
- Closed: в состоянии Closed объекты использовать нельзя. В общем случае большинство конфигураций доступны для изучения, но никакие взаимодействия происходить не могут. Это состояние равнозначно удалению.  
  
- Faulted: в состоянии Faulted объекты доступны для изучения, но их нельзя использовать. Объекты переходят в это состояние при возникновении неустранимой ошибки. Единственным допустимым переходом из этого состояния является состояние `Closed`.  
  
 Есть события, возникающие при каждом изменении состояния. Метод <xref:System.ServiceModel.ICommunicationObject.Abort%2A> может быть вызван в любое время и приводит к тому, что объект переходит сразу из текущего состояния в состояние Closed. Вызов <xref:System.ServiceModel.ICommunicationObject.Abort%2A> прекращает любую незаконченную работу.  
  
<a name="ChannelAndChannelListener"></a>   
## <a name="channel-factory-and-channel-listener"></a>Фабрика каналов и прослушиватель каналов  
 Следующий этап создания пользовательского транспорта - реализация <xref:System.ServiceModel.Channels.IChannelFactory> для каналов клиентов и <xref:System.ServiceModel.Channels.IChannelListener> для каналов служб. Уровень канала использует шаблон фабрики для создания каналов. WCF предоставляет вспомогательные методы базового класса для этого процесса.  
  
- Класс <xref:System.ServiceModel.Channels.CommunicationObject> реализует интерфейс <xref:System.ServiceModel.ICommunicationObject> и принудительно создает конечный автомат, описанный ранее на шаге 2. 

- Класс <xref:System.ServiceModel.Channels.ChannelManagerBase> реализует <xref:System.ServiceModel.Channels.CommunicationObject> и предоставляет унифицированный базовый класс для <xref:System.ServiceModel.Channels.ChannelFactoryBase> и <xref:System.ServiceModel.Channels.ChannelListenerBase>. Класс <xref:System.ServiceModel.Channels.ChannelManagerBase> работает совместно с классом <xref:System.ServiceModel.Channels.ChannelBase> - базовым классом, реализующим интерфейс <xref:System.ServiceModel.Channels.IChannel>.  
  
- Класс <xref:System.ServiceModel.Channels.ChannelFactoryBase> реализует <xref:System.ServiceModel.Channels.ChannelManagerBase> и <xref:System.ServiceModel.Channels.IChannelFactory> и объединяет перегрузки `CreateChannel` в один `OnCreateChannel` абстрактный метод.  
  
- Класс <xref:System.ServiceModel.Channels.ChannelListenerBase> реализует <xref:System.ServiceModel.Channels.IChannelListener>. Он отвечает за базовое управление состоянием.  
  
 В этом образце реализация фабрики содержится в UdpChannelFactory.cs, а реализация прослушивателя содержится в UdpChannelListener.cs. Реализации <xref:System.ServiceModel.Channels.IChannel> находятся в UdpOutputChannel.cs и UdpInputChannel.cs.  
  
### <a name="the-udp-channel-factory"></a>Фабрика канала UDP  
 Фабрика`UdpChannelFactory` наследуется от класса <xref:System.ServiceModel.Channels.ChannelFactoryBase>. В образце переопределяется метод <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A> для обеспечения доступа к версии сообщения кодировщика сообщений. Также переопределяется метод <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A>, позволяющий убрать созданный экземпляр класса <xref:System.ServiceModel.Channels.BufferManager> при переходе конечного автомата в другое состояние.  
  
#### <a name="the-udp-output-channel"></a>Выходной канал UDP  
 Класс`UdpOutputChannel` реализует интерфейс <xref:System.ServiceModel.Channels.IOutputChannel>. Конструктор проверяет аргументы и создает целевой объект <xref:System.Net.EndPoint> на основании переданного ему адреса <xref:System.ServiceModel.EndpointAddress>.  
  
```csharp
this.socket = new Socket(this.remoteEndPoint.AddressFamily, SocketType.Dgram, ProtocolType.Udp);  
```  
  
 Канал может быть закрыт правильно или неправильно. При верном закрытии канала сокет закрывается и вызывается метод `OnClose` базового класса. Если при этом создается исключение, инфраструктура вызывает метод `Abort`, чтоб обеспечить очистку канала.  
  
```csharp
this.socket.Close(0);  
```  
  
 Затем мы реализуем `Send()` и `BeginSend()`/`EndSend()`. Реализация делится на две принципиальные части. Сначала сообщение сериализуется в байтовый массив.  
  
```csharp
ArraySegment<byte> messageBuffer = EncodeMessage(message);  
```  
  
 Затем получившиеся данные отправляются по сети.  
  
```csharp
this.socket.SendTo(messageBuffer.Array, messageBuffer.Offset, messageBuffer.Count, SocketFlags.None, this.remoteEndPoint);  
```  
  
### <a name="the-udpchannellistener"></a>Класс UdpChannelListener  
 `UdpChannelListener`, который реализуется в примере, является производным от класса <xref:System.ServiceModel.Channels.ChannelListenerBase>. Он использует один UDP-сокет для приема датаграмм. Метод `OnOpen` принимает данные через UDP-сокет в асинхронном цикле. Затем данные преобразуются в сообщения с помощью системы кодирования сообщений.  
  
```csharp
message = MessageEncoderFactory.Encoder.ReadMessage(new ArraySegment<byte>(buffer, 0, count), bufferManager);  
```  
  
 Поскольку один канал датаграмм представляет сообщения, приходящие из нескольких источников, `UdpChannelListener` - одноэлементный прослушиватель. Существует, по крайней мере, одна активная <xref:System.ServiceModel.Channels.IChannel>, связанная с этим прослушивателем за раз. В образце создается новый экземпляр только в том случае, если канал, возвращенный методом `AcceptChannel`, был впоследствии освобожден. Когда сообщение принято, оно ставится в очередь в этот одноэлементный канал.  
  
#### <a name="udpinputchannel"></a>UdpInputChannel  
 Класс `UdpInputChannel` реализует `IInputChannel`. Он состоит из очереди входящих сообщений, которая заполняется сокетом прослушивателя `UdpChannelListener`. Эти сообщения выводятся из очереди методом `IInputChannel.Receive`.  
  
<a name="AddingABindingElement"></a>   
## <a name="adding-a-binding-element"></a>Добавление элемента привязки  
 После создания фабрики и каналы нужно предоставить среде выполнения ServiceModel через привязку. Привязка - это коллекция элементов привязки, представляющая стек связи для адреса службы. Каждый элемент в стеке представлен [\<привязкой >](../../configure-apps/file-schema/wcf/bindings.md) элемента.  
  
 В этом примере в качестве элемента привязки выступает элемент `UdpTransportBindingElement`, являющийся производным элемента <xref:System.ServiceModel.Channels.TransportBindingElement>. Он переопределяет следующие методы создания фабрик, связанных с привязкой.  
  
```csharp
public IChannelFactory<TChannel> BuildChannelFactory<TChannel>(BindingContext context)  
{  
    return (IChannelFactory<TChannel>)(object)new UdpChannelFactory(this, context);  
}  
  
public IChannelListener<TChannel> BuildChannelListener<TChannel>(BindingContext context)  
{  
    return (IChannelListener<TChannel>)(object)new UdpChannelListener(this, context);  
}  
```  
  
 Он также содержит члены для клонирования элемента `BindingElement` и возврата схемы (soap.udp).  
  
## <a name="adding-metadata-support-for-a-transport-binding-element"></a>Добавление поддержки метаданных для элемента привязки транспорта  
 Для интеграции в систему метаданных транспорт должен поддерживать как импорт, так и экспорт политики. Это позволяет нам создавать клиенты привязок с помощью [средства служебной программы метаданных ServiceModel (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
### <a name="adding-wsdl-support"></a>Добавление поддержки WSDL  
 За экспорт и импорт адресов в метаданных отвечает элемент привязки транспорта. При использовании привязки протокола SOAP элемент привязки транспорта должен также экспортировать в метаданных правильный URI (универсальный код ресурса) транспорта.  
  
#### <a name="wsdl-export"></a>Экспорт WSDL  
 Для экспорта адресов элемент `UdpTransportBindingElement` реализует интерфейс `IWsdlExportExtension`. Метод `ExportEndpoint` добавляет правильные сведения об адресации в порт WSDL.  
  
```csharp
if (context.WsdlPort != null)  
{  
    AddAddressToWsdlPort(context.WsdlPort, context.Endpoint.Address, encodingBindingElement.MessageVersion.Addressing);  
}  
```  
  
 Реализация метода `UdpTransportBindingElement` в элементе `ExportEndpoint` также экспортирует URI транспорта, когда конечная точка использует привязку SOAP.  
  
```csharp
WsdlNS.SoapBinding soapBinding = GetSoapBinding(context, exporter);  
if (soapBinding != null)  
{  
    soapBinding.Transport = UdpPolicyStrings.UdpNamespace;  
}  
```  
  
#### <a name="wsdl-import"></a>Импорт WSDL  
 Для расширения системы импорта WSDL для обработки импорта адресов нужно добавить в файл конфигурации средства Svcutil.exe следующую конфигурацию, как показано в файле Svcutil.exe.config.  
  
```xml
<configuration>  
  <system.serviceModel>  
    <client>  
      <metadata>  
        <wsdlImporters>  
          <extension type=" Microsoft.ServiceModel.Samples.UdpBindingElementImporter, UdpTransport" />  
        </policyImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 При запуске Svcutil.exe существует два варианта обеспечить загрузку программой расширений импорта WSDL:  
  
1. Укажите файл Svcutil. exe в нашем файле конфигурации с помощью файла/Свкутилконфиг:\<>.  
  
2. добавить раздел конфигурации в файл Svcutil.exe.config, находящийся в том же каталоге, что и файл Svcutil.exe.  
  
 Тип `UdpBindingElementImporter` реализует интерфейс `IWsdlImportExtension`. Метод `ImportEndpoint` импортирует адрес из порта WSDL.  
  
```csharp
BindingElementCollection bindingElements = context.Endpoint.Binding.CreateBindingElements();  
TransportBindingElement transportBindingElement = bindingElements.Find<TransportBindingElement>();  
if (transportBindingElement is UdpTransportBindingElement)  
{  
    ImportAddress(context);  
}  
```  
  
### <a name="adding-policy-support"></a>Добавление поддержки политик  
 Пользовательский элемент привязки может экспортировать утверждения политики в привязке WSDL для конечной точки службы, чтобы показать возможности этого элемента привязки.  
  
#### <a name="policy-export"></a>Экспорт политики  
 Тип `UdpTransportBindingElement` реализует `IPolicyExportExtension` для добавления поддержки политики экспорта. В результате класс `System.ServiceModel.MetadataExporter` включает элемент `UdpTransportBindingElement` при формировании политики для любой привязки, в которую он входит.  
  
 В методе `IPolicyExportExtension.ExportPolicy` добавляется утверждение для UDP и еще одно утверждение, если используется режим многоадресной рассылки. Это связано с тем, что режим многоадресной рассылки влияет на построение стека связи и, следовательно, должен быть согласован обеими сторонами.  
  
```csharp
ICollection<XmlElement> bindingAssertions = context.GetBindingAssertions();  
XmlDocument xmlDocument = new XmlDocument();  
bindingAssertions.Add(xmlDocument.CreateElement(  
UdpPolicyStrings.Prefix, UdpPolicyStrings.TransportAssertion, UdpPolicyStrings.UdpNamespace));  
if (Multicast)  
{  
    bindingAssertions.Add(xmlDocument.CreateElement(
        UdpPolicyStrings.Prefix, 
        UdpPolicyStrings.MulticastAssertion, 
        UdpPolicyStrings.UdpNamespace));  
}  
```  
  
 Поскольку пользовательские элементы привязки транспорта отвечают за обработку адресов, реализация `IPolicyExportExtension` в элементе `UdpTransportBindingElement` должна также обрабатывать экспорт соответствующих утверждений политики WS-Addressing для указания используемой версии WS-Addressing.  
  
```csharp
AddWSAddressingAssertion(context, encodingBindingElement.MessageVersion.Addressing);  
```  
  
#### <a name="policy-import"></a>Импорт политики  
 Чтобы расширить систему импорта политик, нужно добавить в файл конфигурации Svcutil.exe следующую конфигурацию, как показано в файле Svcutil.exe.config.  
  
```xml
<configuration>  
  <system.serviceModel>  
    <client>  
      <metadata>  
        <policyImporters>  
          <extension type=" Microsoft.ServiceModel.Samples.UdpBindingElementImporter, UdpTransport" />  
        </policyImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 Затем мы реализуем интерфейс `IPolicyImporterExtension` из зарегистрированного нами класса (`UdpBindingElementImporter`). В методе `ImportPolicy()` нужно рассмотреть утверждения в нашем пространстве имен и обработать предназначенные для формирования транспорта и проверки, является ли он многоадресным. Кроме того, нужно удалить обрабатываемые утверждения из списка утверждений привязки. И опять при запуске Svcutil.exe существует два варианта интеграции:  
  
1. Укажите файл Svcutil. exe в нашем файле конфигурации с помощью файла/Свкутилконфиг:\<>.  
  
2. добавить раздел конфигурации в файл Svcutil.exe.config, находящийся в том же каталоге, что и файл Svcutil.exe.  
  
<a name="AddingAStandardBinding"></a>   
## <a name="adding-a-standard-binding"></a>Добавление стандартной привязки  
 Элемент привязки можно использовать двумя следующими способами.  
  
- С помощью пользовательской привязки: пользовательская привязка позволяет пользователю создать собственную привязку на основе произвольного набора элементов привязки.  
  
- С помощью предусмотренной в составе системы привязки, включающей наш элемент привязки. WCF предоставляет ряд этих определяемых системой привязок, таких как `BasicHttpBinding`, `NetTcpBinding`и `WsHttpBinding`. Каждая из них связана с четко определенным профилем.  
  
 В этом образце реализуется профиль привязки в `SampleProfileUdpBinding`, производном от <xref:System.ServiceModel.Channels.Binding>. Привязка `SampleProfileUdpBinding` содержит до четырех элементов привязки: `UdpTransportBindingElement`, `TextMessageEncodingBindingElement CompositeDuplexBindingElement` и `ReliableSessionBindingElement`.  
  
```csharp
public override BindingElementCollection CreateBindingElements()  
{     
    BindingElementCollection bindingElements = new BindingElementCollection();  
    if (ReliableSessionEnabled)  
    {  
        bindingElements.Add(session);  
        bindingElements.Add(compositeDuplex);  
    }  
    bindingElements.Add(encoding);  
    bindingElements.Add(transport);  
    return bindingElements.Clone();  
}  
```  
  
### <a name="adding-a-custom-standard-binding-importer"></a>Добавление пользовательского импортера стандартной привязки  
 Svcutil.exe и тип `WsdlImporter` по умолчанию распознают и импортируют определенные системой привязки. В противном случае привязка импортируется как экземпляр `CustomBinding`. Чтобы Svcutil.exe и тип `WsdlImporter` могли импортировать привязку `SampleProfileUdpBinding`, тип `UdpBindingElementImporter` также выступает в качестве пользовательского импортера стандартной привязки.  
  
 Пользовательский импортер стандартной привязки реализует метод `ImportEndpoint` в интерфейсе `IWsdlImportExtension`, чтобы проверить импортированный из метаданных экземпляр класса `CustomBinding` и определить, мог ли он быть сформирован определенной стандартной привязкой.  
  
```csharp
if (context.Endpoint.Binding is CustomBinding)  
{  
    Binding binding;  
    if (transportBindingElement is UdpTransportBindingElement)  
    {  
        //if TryCreate is true, the CustomBinding will be replace by a SampleProfileUdpBinding in the  
        //generated config file for better typed generation.  
        if (SampleProfileUdpBinding.TryCreate(bindingElements, out binding))  
        {  
            binding.Name = context.Endpoint.Binding.Name;  
            binding.Namespace = context.Endpoint.Binding.Namespace;  
            context.Endpoint.Binding = binding;  
        }  
    }  
}  
```  
  
 Как правило, реализация пользовательского импортера стандартной привязки предусматривает проверку свойств импортированных элементов привязки на предмет того, что изменены только свойства, которые могли быть заданы стандартной привязкой, а все остальные свойства имеют значения по умолчанию. Простейшая стратегия для реализации импортера стандартной привязки - создать экземпляр стандартной привязки, распространить на экземпляр стандартной привязки свойства из элементов привязки, поддерживаемые стандартной привязкой, и затем сравнить элементы привязки из стандартной привязки с импортированными элементами привязки.  
  
<a name="AddingConfigurationSupport"></a>   
## <a name="adding-configuration-support"></a>Добавление поддержки конфигурации  
 Для предоставления транспорта через конфигурацию нужно реализовать два раздела конфигурации. Первый - элемент `BindingElementExtensionElement` для `UdpTransportBindingElement`. За счет этого реализации `CustomBinding` могут ссылаться на наш элемент привязки. Второй - `Configuration` для `SampleProfileUdpBinding`.  
  
### <a name="binding-element-extension-element"></a>Элемент привязки элемента Extension  
 Раздел `UdpTransportElement` — это `BindingElementExtensionElement`, который предоставляет `UdpTransportBindingElement` системе конфигурации. С помощью нескольких простых переопределений в примере определяется имя раздела конфигурации, тип элемента привязки и способ создания элемента привязки. Затем можно зарегистрировать раздел расширения в файле конфигурации, как показано в следующем коде.  
  
```xml
<configuration>  
  <system.serviceModel>  
    <extensions>  
      <bindingElementExtensions>  
        <add name="udpTransport" type="Microsoft.ServiceModel.Samples.UdpTransportElement, UdpTransport />  
      </bindingElementExtensions>  
    </extensions>  
  </system.serviceModel>  
</configuration>  
```  
  
 На расширение можно ссылаться из пользовательских привязок, чтобы использовать в качестве транспорта протокол UDP.  
  
```xml
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <customBinding>  
       <binding configurationName="UdpCustomBinding">  
         <udpTransport/>  
       </binding>  
      </customBinding>  
    </bindings>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="binding-section"></a>Раздел привязки  
 Раздел `SampleProfileUdpBindingCollectionElement` — это `StandardBindingCollectionElement`, который предоставляет `SampleProfileUdpBinding` системе конфигурации. Основная часть реализации делегируется классу `SampleProfileUdpBindingConfigurationElement`, наследуемому от класса `StandardBindingElement`. `SampleProfileUdpBindingConfigurationElement` имеет свойства, соответствующие свойствам `SampleProfileUdpBinding`и функциям, которые сопоставляются с привязкой `ConfigurationElement`. Наконец, метод `OnApplyConfiguration` в классе `SampleProfileUdpBinding` переопределяется, как показано в следующем образце кода.  
  
```csharp
protected override void OnApplyConfiguration(string configurationName)  
{  
    if (binding == null)
        throw new ArgumentNullException("binding");

    if (binding.GetType() != typeof(SampleProfileUdpBinding))
    {
        throw new ArgumentException(string.Format(CultureInfo.CurrentCulture,
            "Invalid type for binding. Expected type: {0}. Type passed in: {1}.",
            typeof(SampleProfileUdpBinding).AssemblyQualifiedName,
            binding.GetType().AssemblyQualifiedName));
    }
    SampleProfileUdpBinding udpBinding = (SampleProfileUdpBinding)binding;

    udpBinding.OrderedSession = this.OrderedSession;
    udpBinding.ReliableSessionEnabled = this.ReliableSessionEnabled;
    udpBinding.SessionInactivityTimeout = this.SessionInactivityTimeout;
    if (this.ClientBaseAddress != null)
        udpBinding.ClientBaseAddress = ClientBaseAddress;
}
```  
  
 Для регистрации этого обработчика в системе конфигурации в соответствующий файл конфигурации добавляется следующий раздел.  
  
```xml
<configuration>  
  <configSections>  
     <sectionGroup name="system.serviceModel">  
        <sectionGroup name="bindings">  
          <section name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport />  
        </sectionGroup>  
     </sectionGroup>  
  </configSections>  
</configuration>  
```  
  
 После этого на него можно сослаться из раздела конфигурации serviceModel.  
  
```xml
<configuration>  
  <system.serviceModel>  
    <client>  
      <endpoint configurationName="calculator"  
                address="soap.udp://localhost:8001/"   
                bindingConfiguration="CalculatorServer"  
                binding="sampleProfileUdpBinding"   
                contract= "Microsoft.ServiceModel.Samples.ICalculatorContract">  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="the-udp-test-service-and-client"></a>Тестовые служба и клиент UDP  
 Тестовый код для использования этого примера транспорта находится в каталогах UdpTestService и UdpTestClient. Код службы состоит из двух тестов. Один из них настраивает привязки и конечные точки из кода, а другой - через конфигурацию. Оба теста используют две конечных точки. Одна конечная точка использует `SampleUdpProfileBinding` с [\<reliableSession >](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) установить в `true`. Другая конечная точка использует пользовательскую привязку с классом `UdpTransportBindingElement`. Это эквивалентно использованию `SampleUdpProfileBinding` с [\<reliableSession >](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) установленным в `false`. Оба теста создают службу, добавляют для каждой привязки конечную точку, открывают службу и ожидают нажатия пользователем клавиши ВВОД перед тем, как закрыть службу.  
  
 При запуске приложения тестирования службы появится результат следующего вида.  
  
```console
Testing Udp From Code.  
Service is started from code...  
Press <ENTER> to terminate the service and start service from config...  
```  
  
 Затем можно выполнить приложение тестирования клиента относительно опубликованных конечных точек. Приложение тестирования клиента создает клиент для каждой конечной точки и отправляет им по пять сообщений. Клиент получает следующий результат.  
  
```console
Testing Udp From Imported Files Generated By SvcUtil.  
0  
3  
6  
9  
12  
Press <ENTER> to complete test.  
```  
  
 Полные результаты службы таковы.  
  
```console
Service is started from code...  
Press <ENTER> to terminate the service and start service from config...  
Hello, world!  
Hello, world!  
Hello, world!  
Hello, world!  
Hello, world!  
   adding 0 + 0  
   adding 1 + 2  
   adding 2 + 4  
   adding 3 + 6  
   adding 4 + 8  
```  
  
 Для выполнения клиентского приложения относительно конечных точек, опубликованных с помощью конфигурации, нажмите в службе клавишу ВВОД и снова запустите тестовый клиент. Служба должна предоставить следующие результаты.  
  
```console
Testing Udp From Config.  
Service is started from config...  
Press <ENTER> to terminate the service and exit...  
```  
  
 Повторное выполнение клиента дает такие же результаты.  
  
 Для восстановления кода клиента и конфигурации с помощью Svcutil.exe запустите приложение службы и выполните следующий файл Svcutil.exe из корневого каталога образца.  
  
```console
svcutil http://localhost:8000/udpsample/ /reference:UdpTransport\bin\UdpTransport.dll /svcutilConfig:svcutil.exe.config  
```  
  
 Обратите внимание, что Svcutil.exe не создает конфигурацию расширения привязки для `SampleProfileUdpBinding`, поэтому ее нужно добавить вручную.  
  
```xml
<configuration>  
  <system.serviceModel>      
    <extensions>  
      <!-- This was added manually because svcutil.exe does not add this extension to the file -->  
      <bindingExtensions>  
        <add name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport" />  
      </bindingExtensions>  
    </extensions>  
  </system.serviceModel>  
</configuration>  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Чтобы выполнить сборку решения, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
3. См. раздел "Тестовые служба и клиент UDP" выше.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Transport\Udp`
