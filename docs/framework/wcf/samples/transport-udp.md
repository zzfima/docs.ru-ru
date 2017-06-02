---
title: "Транспорт: UDP | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 738705de-ad3e-40e0-b363-90305bddb140
caps.latest.revision: 48
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 48
---
# Транспорт: UDP
В образце транспорта UDP демонстрируется реализация одноадресного и многоадресного протокола UDP в качестве пользовательского транспорта [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].В образце описана процедура, предлагаемая для создания пользовательского транспорта в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с помощью инфраструктуры канала и согласно рекомендациям [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].Для создания пользовательского транспорта выполните следующие действия.  
  
1.  Выберите шаблон из [Шаблоны обмена сообщениями](#MessageExchangePatterns) \(IOutputChannel, IInputChannel, IDuplexChannel, IRequestChannel или IReplyChannel\), которые будут поддерживать ChannelFactory и ChannelListener.Затем решите, поддерживать ли связанные с сеансами разновидности указанных интерфейсов.  
  
2.  Создайте фабрику и прослушиватель каналов, которые поддерживают выбранный шаблон обмена сообщениями.  
  
3.  Убедитесь, что все исключения, связанные с сетью, нормализованы в соответствующий класс, унаследованный от <xref:System.ServiceModel.CommunicationException>.  
  
4.  Добавьте элемент [\<привязка\>](../../../../docs/framework/misc/binding.md), добавляющий пользовательский транспорт в стек каналов.Дополнительные сведения см. в разделе [Добавление элемента привязки](#AddingABindingElement).  
  
5.  Добавьте раздел расширения элементов привязки, чтобы представить новый элемент привязки системе конфигурации.  
  
6.  Добавьте расширения метаданных, чтобы сообщить о возможностях в другие конечные точки.  
  
7.  Добавьте привязку, которая предварительно настраивает стек элементов привязки в соответствии с четко определенным профилем.Дополнительные сведения см. в разделе [Добавление стандартной привязки](#AddingAStandardBinding).  
  
8.  Добавьте раздел привязки и элемент конфигурации привязки, чтобы представить привязку системе конфигурации.Дополнительные сведения см. в разделе [Добавление поддержки конфигурации](#AddingConfigurationSupport).  
  
<a name="MessageExchangePatterns"></a>   
## Шаблоны обмена сообщениями  
 При создании пользовательского транспорта в первую очередь решите, какие шаблоны обмена сообщениями требуются для транспорта.Можно выбирать из трех шаблонов обмена сообщениями.  
  
-   Датаграмма \(IInputChannel\/IOutputChannel\)  
  
     При использовании шаблона обмена сообщениями "датаграмма" клиент отправляет сообщения, используя принцип "отправить и забыть".В этом случае требуется внешнее подтверждение успешной доставки.Сообщение может быть потеряно при передаче и может не достичь службы.Если операция отправки успешно выполняется на стороне клиента, это не гарантирует, что удаленная конечная точка получит сообщение.Датаграмма — фундаментальный элемент обмена сообщениями, на основе которого можно строить собственные протоколы, в том числе надежные и безопасные.Каналы датаграмм клиентов реализуют интерфейс <xref:System.ServiceModel.Channels.IOutputChannel>, а каналы датаграмм служб — интерфейс <xref:System.ServiceModel.Channels.IInputChannel>.  
  
-   Запрос\-ответ \(IRequestChannel\/IReplyChannel\)  
  
     При использовании этого шаблона происходит отправка сообщения и получение ответа.Шаблон состоит из пар «запрос\-ответ».Примеры вызовов "запрос\-ответ" — удаленные вызовы процедур и запросы GET браузера.Этот шаблон также называют полудуплексным.При использовании этого шаблона обмена сообщениями каналы клиентов реализуют интерфейс <xref:System.ServiceModel.Channels.IRequestChannel>, а каналы служб — интерфейс <xref:System.ServiceModel.Channels.IReplyChannel>.  
  
-   Дуплекс \(IDuplexChannel\)  
  
     Дуплексный шаблон обмена сообщениями позволяет клиенту отправлять произвольное количество сообщений и принимать их в произвольном порядке.Применение дуплексного шаблона похоже на разговор по телефону, когда каждое произносимое слово является сообщением.Поскольку в данном случае принимать и отправлять сообщения могут обе стороны, каналы клиента и службы реализуют интерфейс <xref:System.ServiceModel.Channels.IDuplexChannel>.  
  
 Каждый из этих шаблонов обмена сообщениями также поддерживает сеансы.Канал, поддерживающий сеансы, содержит функции для согласования всех сообщений, отправляемых и принимаемых через канал.Шаблон "запрос\-ответ" является отдельным сеансом из двух сообщений, поскольку запрос и ответ связаны друг с другом.В отличие от него в поддерживающем сеансы шаблоне "запрос\-ответ" предполагается, что все пары "запрос\-ответ" в канале связаны друг с другом.Таким образом, можно выбирать один из шести шаблонов: датаграмма, "запрос\-ответ", дуплекс, датаграмма с поддержкой сеансов, "запрос\-ответ" с поддержкой сеансов и дуплекс с поддержкой сеансов.  
  
> [!NOTE]
>  Для транспорта по протоколу UDP единственным поддерживаемым шаблоном обмена сообщениями является датаграмма, поскольку структура протокола UDP основана на принципе "отправить и забыть".  
  
### Жизненный цикл ICommunicationObject и объектов WCF  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] содержит общий конечный автомат для управления жизненным циклом таких объектов, как <xref:System.ServiceModel.Channels.IChannel>, <xref:System.ServiceModel.Channels.IChannelFactory> и <xref:System.ServiceModel.Channels.IChannelListener>, которые используются для взаимодействия.Эти объекты взаимодействий могут находиться в пяти состояниях.Эти состояния, приведенные ниже, представлены перечислением <xref:System.ServiceModel.CommunicationState>.  
  
-   Created. Это состояние объекта <xref:System.ServiceModel.ICommunicationObject> при первом создании его экземпляра.Ввод и вывод в этом состоянии не происходит.  
  
-   Opening. Объекты переходят в это состояние при вызове метода <xref:System.ServiceModel.ICommunicationObject.Open%2A>.В этот момент свойства перестают быть изменяемыми, и могут начинаться ввод и вывод.Переход в это состояние возможен только из состояния Created.  
  
-   Opened: в это состояние объекты переходят по окончании процесса открытия.Переход в это состояние возможен только из состояния Opening.С этого момента объект полностью пригоден для передачи сообщений.  
  
-   Closing. Объекты переходят в это состояние при вызове метода <xref:System.ServiceModel.ICommunicationObject.Close%2A> для правильного завершения работы.Переход в это состояние возможен только из состояния Opened.  
  
-   Closed: в состоянии Closed объекты использовать нельзя.В общем случае большинство конфигураций доступны для изучения, но никакие взаимодействия происходить не могут.Это состояние равнозначно удалению.  
  
-   Faulted: в состоянии Faulted объекты доступны для изучения, но их нельзя использовать.Объекты переходят в это состояние при возникновении неустранимой ошибки.Из этого состояния возможен переход только в состояние `Closed`.  
  
 Есть события, возникающие при каждом изменении состояния.Метод <xref:System.ServiceModel.ICommunicationObject.Abort%2A> можно вызывать в любой момент. При его вызове объект немедленно переходит из текущего состояния в состояние Closed.Вызов <xref:System.ServiceModel.ICommunicationObject.Abort%2A> прекращает любую незаконченную работу.  
  
<a name="ChannelAndChannelListener"></a>   
## Фабрика каналов и прослушиватель каналов  
 Следующий этап создания пользовательского транспорта — реализация <xref:System.ServiceModel.Channels.IChannelFactory> для каналов клиентов и <xref:System.ServiceModel.Channels.IChannelListener> для каналов служб.Уровень канала использует шаблон фабрики для создания каналов.В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предусмотрены вспомогательные базовые классы для этого процесса.  
  
-   Класс <xref:System.ServiceModel.Channels.CommunicationObject> реализует интерфейс <xref:System.ServiceModel.ICommunicationObject> и принудительно создает конечный автомат, описанный ранее на шаге 2.  
  
-   Класс ``<xref:System.ServiceModel.Channels.ChannelManagerBase> реализует <xref:System.ServiceModel.Channels.CommunicationObject> и предоставляет универсальный базовый класс для <xref:System.ServiceModel.Channels.ChannelFactoryBase> и <xref:System.ServiceModel.Channels.ChannelListenerBase>.Класс <xref:System.ServiceModel.Channels.ChannelManagerBase> работает совместно с классом <xref:System.ServiceModel.Channels.ChannelBase> — базовым классом, реализующим интерфейс <xref:System.ServiceModel.Channels.IChannel>.  
  
-   Класс``<xref:System.ServiceModel.Channels.ChannelFactoryBase> реализует класс <xref:System.ServiceModel.Channels.ChannelManagerBase> и интерфейс <xref:System.ServiceModel.Channels.IChannelFactory> и объединяет перегрузки `CreateChannel` в один абстрактный метод `OnCreateChannel`.  
  
-   Класс <xref:System.ServiceModel.Channels.ChannelListenerBase> реализует интерфейс <xref:System.ServiceModel.Channels.IChannelListener>.Он отвечает за базовое управление состоянием.  
  
 В этом образце реализация фабрики содержится в UdpChannelFactory.cs, а реализация прослушивателя содержится в UdpChannelListener.cs.Реализации <xref:System.ServiceModel.Channels.IChannel> находятся в UdpOutputChannel.cs и UdpInputChannel.cs.  
  
### Фабрика канала UDP  
 Фабрика `UdpChannelFactory` наследуется от класса <xref:System.ServiceModel.Channels.ChannelFactoryBase>.В образце переопределяется метод <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A> для обеспечения доступа к версии сообщения кодировщика сообщений.Также переопределяется метод <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A>, позволяющий убрать созданный экземпляр класса <xref:System.ServiceModel.Channels.BufferManager> при переходе конечного автомата в другое состояние.  
  
#### Выходной канал UDP  
 Класс `UdpOutputChannel` реализует интерфейс <xref:System.ServiceModel.Channels.IOutputChannel>.Конструктор проверяет аргументы и создает целевой объект <xref:System.Net.EndPoint> на основании переданного ему адреса <xref:System.ServiceModel.EndpointAddress>.  
  
```  
this.socket = new Socket(this.remoteEndPoint.AddressFamily, SocketType.Dgram, ProtocolType.Udp);  
  
```  
  
 Канал может быть закрыт правильно или неправильно.При верном закрытии канала сокет закрывается и вызывается метод `OnClose` базового класса.Если при этом создается исключение, инфраструктура вызывает метод `Abort`, чтоб обеспечить очистку канала.  
  
```  
this.socket.Close(0);  
  
```  
  
 Затем реализуются `Send()` и `BeginSend()`\/`EndSend()`.Реализация делится на две принципиальные части.Сначала сообщение сериализуется в байтовый массив.  
  
```  
ArraySegment<byte> messageBuffer = EncodeMessage(message);  
  
```  
  
 Затем получившиеся данные отправляются по сети.  
  
```  
this.socket.SendTo(messageBuffer.Array, messageBuffer.Offset, messageBuffer.Count, SocketFlags.None, this.remoteEndPoint);  
```  
  
### Класс UdpChannelListener  
 Класс``UdpChannelListener, реализованный в образце, унаследован от класса <xref:System.ServiceModel.Channels.ChannelListenerBase>.Он использует один UDP\-сокет для приема датаграмм.Метод `OnOpen` принимает данные через UDP\-сокет в асинхронном цикле.Затем данные преобразуются в сообщения с помощью системы кодирования сообщений.  
  
```  
message = MessageEncoderFactory.Encoder.ReadMessage(new ArraySegment<byte>(buffer, 0, count), bufferManager);  
```  
  
 Поскольку один канал датаграмм представляет сообщения, приходящие из нескольких источников, `UdpChannelListener` — одноэлементный прослушиватель.С этим прослушивателем в каждый момент времени может быть связано не более одного активного интерфейса <xref:System.ServiceModel.Channels.IChannel>``.В образце создается новый экземпляр только в том случае, если канал, возвращенный методом `AcceptChannel`, был впоследствии освобожден.Когда сообщение принято, оно ставится в очередь в этот одноэлементный канал.  
  
#### UdpInputChannel  
 Класс `UdpInputChannel` реализует интерфейс `IInputChannel`.Он состоит из очереди входящих сообщений, которая заполняется сокетом прослушивателя `UdpChannelListener`.Эти сообщения удаляются из очереди с помощью метода `IInputChannel.Receive```.  
  
<a name="AddingABindingElement"></a>   
## Добавление элемента привязки  
 После создания фабрики и каналы нужно предоставить среде выполнения ServiceModel через привязку.Привязка — это коллекция элементов привязки, представляющая стек связи для адреса службы.Каждый элемент стека представлен элементом [\<привязка\>](../../../../docs/framework/misc/binding.md).  
  
 В этом образце в качестве элемента привязки выступает элемент `UdpTransportBindingElement`, являющийся производным элемента <xref:System.ServiceModel.Channels.TransportBindingElement>.Он переопределяет следующие методы создания фабрик, связанных с привязкой.  
  
```  
public IChannelFactory<TChannel> BuildChannelFactory<TChannel>(BindingContext context)  
{  
            return (IChannelFactory<TChannel>)(object)new UdpChannelFactory(this, context);  
}  
  
public IChannelListener<TChannel> BuildChannelListener<TChannel>(BindingContext context)  
{  
            return (IChannelListener<TChannel>)(object)new UdpChannelListener(this, context);  
}  
```  
  
 Он также содержит члены для клонирования элемента `BindingElement` и возврата схемы \(soap.udp\).  
  
## Добавление поддержки метаданных для элемента привязки транспорта  
 Для интеграции в систему метаданных транспорт должен поддерживать как импорт, так и экспорт политики.Это позволяет создавать клиенты привязки с помощью средства [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
### Добавление поддержки WSDL  
 За экспорт и импорт адресов в метаданных отвечает элемент привязки транспорта.При использовании привязки протокола SOAP элемент привязки транспорта должен также экспортировать в метаданных правильный URI \(универсальный код ресурса\) транспорта.  
  
#### Экспорт WSDL  
 Для экспорта адресов элемент `UdpTransportBindingElement` реализует интерфейс `IWsdlExportExtension`.Метод `ExportEndpoint` добавляет правильные адреса в порт WSDL.  
  
```  
if (context.WsdlPort != null)  
{  
    AddAddressToWsdlPort(context.WsdlPort, context.Endpoint.Address, encodingBindingElement.MessageVersion.Addressing);  
}  
```  
  
 Реализация метода `ExportEndpoint` в элементе `UdpTransportBindingElement` также экспортирует URI транспорта, когда конечная точка использует привязку SOAP.  
  
```  
WsdlNS.SoapBinding soapBinding = GetSoapBinding(context, exporter);  
if (soapBinding != null)  
{  
    soapBinding.Transport = UdpPolicyStrings.UdpNamespace;  
}  
```  
  
#### Импорт WSDL  
 Для расширения системы импорта WSDL для обработки импорта адресов нужно добавить в файл конфигурации средства Svcutil.exe следующую конфигурацию, как показано в файле Svcutil.exe.config.  
  
```  
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
  
1.  Указать Svcutil.exe на файл конфигурации с помощью параметра \/SvcutilConfig:\<file\>.  
  
2.  Добавить раздел конфигурации в файл Svcutil.exe.config, находящийся в том же каталоге, что и файл Svcutil.exe.  
  
 Тип `UdpBindingElementImporter` реализует интерфейс `IWsdlImportExtension`.Метод `ImportEndpoint` импортирует адрес из порта WSDL.  
  
```  
BindingElementCollection bindingElements = context.Endpoint.Binding.CreateBindingElements();  
TransportBindingElement transportBindingElement = bindingElements.Find<TransportBindingElement>();  
if (transportBindingElement is UdpTransportBindingElement)  
{  
    ImportAddress(context);  
}  
```  
  
### Добавление поддержки политик  
 Пользовательский элемент привязки может экспортировать утверждения политики в привязке WSDL для конечной точки службы, чтобы показать возможности этого элемента привязки.  
  
#### Экспорт политики  
 Тип `UdpTransportBindingElement` реализует интерфейс ```IPolicyExportExtension` для добавления поддержки экспорта политик.В результате класс `System.ServiceModel.MetadataExporter` включает элемент `UdpTransportBindingElement` при формировании политики для любой привязки, в которую он входит.  
  
 В методе `IPolicyExportExtension.ExportPolicy` добавляется утверждение для UDP и еще одно утверждение, если используется режим многоадресной рассылки.Это связано с тем, что режим многоадресной рассылки влияет на построение стека связи и, следовательно, должен быть согласован обеими сторонами.  
  
```  
ICollection<XmlElement> bindingAssertions = context.GetBindingAssertions();  
XmlDocument xmlDocument = new XmlDocument();  
bindingAssertions.Add(xmlDocument.CreateElement(  
UdpPolicyStrings.Prefix, UdpPolicyStrings.TransportAssertion, UdpPolicyStrings.UdpNamespace));  
if (Multicast)  
{  
    bindingAssertions.Add(xmlDocument.CreateElement(  
UdpPolicyStrings.Prefix, UdpPolicyStrings.MulticastAssertion,     UdpPolicyStrings.UdpNamespace));  
}  
```  
  
 Поскольку пользовательские элементы привязки транспорта отвечают за обработку адресов, реализация `IPolicyExportExtension` в элементе `UdpTransportBindingElement` должна также обрабатывать экспорт соответствующих утверждений политики WS\-Addressing для указания используемой версии WS\-Addressing.  
  
```  
AddWSAddressingAssertion(context, encodingBindingElement.MessageVersion.Addressing);  
```  
  
#### Импорт политики  
 Чтобы расширить систему импорта политик, нужно добавить в файл конфигурации Svcutil.exe следующую конфигурацию, как показано в файле Svcutil.exe.config.  
  
```  
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
  
 Затем мы реализуем интерфейс `IPolicyImporterExtension` из зарегистрированного нами класса \(`UdpBindingElementImporter`\).В методе `ImportPolicy()` нужно рассмотреть утверждения в нашем пространстве имен и обработать предназначенные для формирования транспорта и проверки, является ли он многоадресным.Кроме того, нужно удалить обрабатываемые утверждения из списка утверждений привязки.И опять при запуске Svcutil.exe существует два варианта интеграции:  
  
1.  Указать Svcutil.exe на файл конфигурации с помощью параметра \/SvcutilConfig:\<file\>.  
  
2.  Добавить раздел конфигурации в файл Svcutil.exe.config, находящийся в том же каталоге, что и файл Svcutil.exe.  
  
<a name="AddingAStandardBinding"></a>   
## Добавление стандартной привязки  
 Элемент привязки можно использовать двумя следующими способами.  
  
-   С помощью пользовательской привязки: пользовательская привязка позволяет пользователю создать собственную привязку на основе произвольного набора элементов привязки.  
  
-   С помощью привязки, предоставленной системой, включающей наш элемент привязки.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предоставляет несколько таких привязок, определенных системой, например `NetTcpBinding`, `BasicHttpBinding`, и `WsHttpBinding`.Каждая из них связана с четко определенным профилем.  
  
 В этом образце реализуется профиль привязки в `SampleProfileUdpBinding`, производном от <xref:System.ServiceModel.Channels.Binding>.Привязка `SampleProfileUdpBinding` содержит до четырех элементов привязки: `UdpTransportBindingElement`, `TextMessageEncodingBindingElement CompositeDuplexBindingElement` и `ReliableSessionBindingElement`.  
  
```  
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
  
### Добавление пользовательского импортера стандартной привязки  
 Svcutil.exe и тип `WsdlImporter` по умолчанию распознают и импортируют определенные системой привязки.В противном случае привязка импортируется как экземпляр `CustomBinding`.Чтобы Svcutil.exe и тип `WsdlImporter` могли импортировать привязку `SampleProfileUdpBinding`, тип `UdpBindingElementImporter` также выступает в качестве пользовательского импортера стандартной привязки.  
  
 Пользовательский импортер стандартной привязки реализует метод `ImportEndpoint` в интерфейсе `IWsdlImportExtension`, чтобы проверить импортированный из метаданных экземпляр класса `CustomBinding` и определить, мог ли он быть сформирован определенной стандартной привязкой.  
  
```  
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
  
 Как правило, реализация пользовательского импортера стандартной привязки предусматривает проверку свойств импортированных элементов привязки на предмет того, что изменены только свойства, которые могли быть заданы стандартной привязкой, а все остальные свойства имеют значения по умолчанию.Простейшая стратегия для реализации импортера стандартной привязки — создать экземпляр стандартной привязки, распространить на экземпляр стандартной привязки свойства из элементов привязки, поддерживаемые стандартной привязкой, и затем сравнить элементы привязки из стандартной привязки с импортированными элементами привязки.  
  
<a name="AddingConfigurationSupport"></a>   
## Добавление поддержки конфигурации  
 Для предоставления транспорта через конфигурацию нужно реализовать два раздела конфигурации.Первый — элемент `BindingElementExtensionElement` для `UdpTransportBindingElement`.За счет этого реализации `CustomBinding` могут ссылаться на наш элемент привязки.Второй — `Configuration` для `SampleProfileUdpBinding`.  
  
### Элемент привязки элемента Extension  
 `` раздел```UdpTransportElement` — это элемент `BindingElementExtensionElement`, который предоставляет элемент привязки `UdpTransportBindingElement` системе конфигурации.С помощью нескольких простых переопределений в примере определяется имя раздела конфигурации, тип элемента привязки и способ создания элемента привязки.Затем можно зарегистрировать раздел расширения в файле конфигурации, как показано в следующем коде.  
  
```  
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
  
```  
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
  
### Раздел привязки  
 Раздел `SampleProfileUdpBindingCollectionElement` — это элемент `StandardBindingCollectionElement`, который предоставляет элемент `SampleProfileUdpBinding` системе конфигурации.Основная часть реализации делегируется классу `SampleProfileUdpBindingConfigurationElement`, наследуемому от класса `StandardBindingElement`.Класс `SampleProfileUdpBindingConfigurationElement` имеет свойства, соответствующие свойствам класса `SampleProfileUdpBinding`, и обеспечивает сопоставление привязки `ConfigurationElement` .Наконец, метод `OnApplyConfiguration` в классе `SampleProfileUdpBinding` переопределяется, как показано в следующем образце кода.  
  
```  
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
  
```  
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
  
```  
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
  
## Тестовые служба и клиент UDP  
 Тестовый код для использования этого образца транспорта находится в каталогах UdpTestService и UdpTestClient.Код службы состоит из двух тестов. Один из них настраивает привязки и конечные точки из кода, а другой — через конфигурацию.Оба теста используют две конечных точки.Одна конечная точка использует `SampleUdpProfileBinding` со значением [\<reliableSession\>](http://msdn.microsoft.com/ru-ru/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b), равным `true`.Другая конечная точка использует пользовательскую привязку с классом `UdpTransportBindingElement`.Это равнозначно использованию `SampleUdpProfileBinding` со значением [\<reliableSession\>](http://msdn.microsoft.com/ru-ru/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b), равным `false`.Оба теста создают службу, добавляют для каждой привязки конечную точку, открывают службу и ожидают нажатия пользователем клавиши ВВОД перед тем, как закрыть службу.  
  
 При запуске приложения тестирования службы появится результат следующего вида.  
  
```  
Testing Udp From Code.  
Service is started from code...  
Press <ENTER> to terminate the service and start service from config...  
```  
  
 Затем можно выполнить приложение тестирования клиента относительно опубликованных конечных точек.Приложение тестирования клиента создает клиент для каждой конечной точки и отправляет им по пять сообщений.Клиент получает следующий результат.  
  
```  
Testing Udp From Imported Files Generated By SvcUtil.  
0  
3  
6  
9  
12  
Press <ENTER> to complete test.  
```  
  
 Полные результаты службы таковы.  
  
```  
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
  
 Для выполнения клиентского приложения относительно конечных точек, опубликованных с помощью конфигурации, нажмите в службе клавишу ВВОД и снова запустите тестовый клиент.Служба должна предоставить следующие результаты.  
  
```  
Testing Udp From Config.  
Service is started from config...  
Press <ENTER> to terminate the service and exit...  
```  
  
 Повторное выполнение клиента дает такие же результаты.  
  
 Для восстановления кода клиента и конфигурации с помощью Svcutil.exe запустите приложение службы и выполните следующий файл Svcutil.exe из корневого каталога образца.  
  
```  
svcutil http://localhost:8000/udpsample/ /reference:UdpTranport\bin\UdpTransport.dll /svcutilConfig:svcutil.exe.config  
```  
  
 Обратите внимание, что Svcutil.exe не создает конфигурацию расширения привязки для `SampleProfileUdpBinding`, поэтому ее нужно добавить вручную.  
  
```  
<configuration>  
    <system.serviceModel>      
        …  
        <extensions>  
            <!-- This was added manually because svcutil.exe does not add this extension to the file -->  
            <bindingExtensions>  
                <add name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport" />  
            </bindingExtensions>  
        </extensions>  
    </system.serviceModel>  
</configuration>  
```  
  
#### Настройка, построение и выполнение образца  
  
1.  Для построения решения следуйте инструкциям раздела [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2.  Чтобы выполнить образец на одном или нескольких компьютерах, выполните инструкции в разделе [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
3.  См. раздел «Тестовые служба и клиент UDP» выше.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Extensibility\Transport\Udp`  
  
## См. также