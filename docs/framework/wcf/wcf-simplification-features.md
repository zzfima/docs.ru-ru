---
title: Функции упрощения WCF
ms.date: 03/30/2017
ms.assetid: 4535a511-6064-4da0-b361-80262a891663
ms.openlocfilehash: 28a05053fda8380b55a1a9eee20119b8c4cfccfe
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452660"
---
# <a name="wcf-simplification-features"></a>Функции упрощения WCF

В этом разделе описываются новые возможности, упрощающие написание приложений WCF.

## <a name="simplified-generated-configuration-files"></a>Упрощенные сформированные файлы конфигурации

Клиентский файл конфигурации создается при добавлении ссылки на службу в Visual Studio или при использовании средства SvcUtil.exe. В предыдущих версиях WCF эти файлы конфигурации содержали значения каждого свойства привязки, даже если значение было значением по умолчанию. В WCF 4.5 сформированные файлы конфигурации содержат только те свойства привязки, которым присвоено значение не по умолчанию.

Далее приведен пример файла конфигурации, сформированного WCF 3.0.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
    <system.serviceModel>
        <bindings>
            <basicHttpBinding>
                <binding name="BasicHttpBinding_IService1" closeTimeout="00:01:00"
                    openTimeout="00:01:00" receiveTimeout="00:10:00" sendTimeout="00:01:00"
                    allowCookies="false" bypassProxyOnLocal="false"
                    hostNameComparisonMode="StrongWildcard" maxBufferSize="65536"
                    maxBufferPoolSize="524288" maxReceivedMessageSize="65536"
                    messageEncoding="Text" textEncoding="utf-8" transferMode="Buffered"
                    useDefaultWebProxy="true">
                    <readerQuotas maxDepth="32" maxStringContentLength="8192"
                        maxArrayLength="16384" maxBytesPerRead="4096"
                        maxNameTableCharCount="16384" />
                    <security mode="None">
                        <transport clientCredentialType="None" proxyCredentialType="None"
                            realm="" />
                        <message clientCredentialType="UserName" algorithmSuite="Default" />
                    </security>
                </binding>
            </basicHttpBinding>
        </bindings>
        <client>
            <endpoint address="http://localhost:36906/Service1.svc" binding="basicHttpBinding"
                bindingConfiguration="BasicHttpBinding_IService1" contract="IService1"
                name="BasicHttpBinding_IService1" />
        </client>
    </system.serviceModel>
</configuration>
```

Далее приведен пример того же файла конфигурации, сформированного WCF 4.5.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
    <system.serviceModel>
        <bindings>
            <basicHttpBinding>
                <binding name="BasicHttpBinding_IService1" />
            </basicHttpBinding>
        </bindings>
        <client>
            <endpoint address="http://localhost:36906/Service1.svc" binding="basicHttpBinding"
                bindingConfiguration="BasicHttpBinding_IService1" contract="IService1"
                name="BasicHttpBinding_IService1" />
        </client>
    </system.serviceModel>
</configuration>
```

## <a name="contract-first-development"></a>Разработка в соответствии с парадигмой «Сначала контракт»

WCF теперь поддерживает разработку в соответствии с парадигмой «Сначала контракт». Средство Svcutil. exe имеет параметр/Сервицеконтракт, который позволяет создавать контракты служб и данных из документа WSDL.

## <a name="add-service-reference-from-a-portable-subset-project"></a>Добавление ссылки на службу из проекта переносимого подмножества

Переносимые проекты подмножества позволяют программистам сборок .NET поддерживать единое дерево исходного кода и систему сборки, одновременно обеспечивая поддержку нескольких реализаций .NET (Desktop, Silverlight, Windows Phone и Xbox). Переносимые проекты подмножества ссылаются только на переносимые библиотеки .NET, которые являются сборками, которые могут использоваться в любой реализации .NET. Процесс добавления такой же, как и при добавлении ссылки на службу в рамках любого другого клиентского приложения WCF. Дополнительные сведения см. [в разделе Добавление ссылки на службу в проекте переносимого подмножества](add-service-reference-in-a-portable-subset-project.md).

## <a name="aspnet-compatibility-mode-default-changed"></a>Изменились значения по умолчанию для режима совместимости с ASP.NET

WCF предоставляет режим совместимости с ASP.NET, дающий разработчикам при создании служб WCF полный доступ к функциям HTTP-конвейера ASP.NET. Чтобы использовать этот режим, необходимо присвоить атрибуту `aspNetCompatibilityEnabled` значение true в разделе [\<serviceHostingEnvironment >](../configure-apps/file-schema/wcf/servicehostingenvironment.md) файла Web. config. Кроме того, любая служба в этом appDomain должна иметь свойство `RequirementsMode` в своем <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>е, для которого задано значение <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed> или <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>. По умолчанию <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> теперь имеет значение <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>, а шаблон приложения службы WCF по умолчанию задает для атрибута `aspNetCompatibilityEnabled` значение `true`. Дополнительные сведения см. [в статье новые возможности Windows Communication Foundation 4,5](whats-new.md) и [служб WCF и ASP.NET](./feature-details/wcf-services-and-aspnet.md).

## <a name="streaming-improvements"></a>Улучшения в потоковой передаче данных

- В WCF была добавлена новая поддержка асинхронной потоковой передачи данных. Чтобы включить поддержку асинхронной потоковой передачи данных, добавьте поведение конечной точки <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior> в основное приложение службы и установите свойству <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior.AsynchronousSendEnabled%2A> значение `true`. Это может улучшить масштабируемость, когда служба отправляет потоковые сообщения нескольким клиентам, которые медленно считывают сообщения. WCF больше не блокирует один поток для каждого клиента и освобождает поток для обслуживания другого клиента.

- Убраны ограничения для буферизации сообщений, возникающие, когда служба размещается в IIS. В предыдущих версиях WCF при получении сообщения для размещенной в IIS службы, использующей потоковую передачу, ASP.NET перед отправкой сообщения в WCF поместило бы его в буфер целиком. Это привело бы к использованию большого объема памяти. Эта буферизация была ликвидирована в .NET 4.5, и теперь WCF-службы, размещаемые в IIS, могут начинать обработку входящего потока до получения всего сообщения, поэтому реализуется истинная потоковая передача данных. Это позволяет WCF-службам моментально реагировать на сообщения, улучшая производительность. Кроме того, теперь вам больше не требуется указывать значение для `maxRequestLength`, ограничивающего размер входящих запросов в ASP.NET. Если данное свойство установлено, то оно не учитывается. Дополнительные сведения о `maxRequestLength` см. в разделе [\<httpRuntime > Configuration element](https://docs.microsoft.com/previous-versions/dotnet/netframework-1.1/e1f13641(v=vs.71)). Вам по-прежнему потребуется настроить maxAllowedContentLength. Дополнительные сведения см. в разделе [ограничения запросов IIS](https://docs.microsoft.com/previous-versions/iis/settings-schema/ms689462(v=vs.90)).

## <a name="new-transport-default-values"></a>Новые значения по умолчанию для свойств транспорта

В следующей таблице описываются измененные настройки и разделы, в которых можно найти дополнительные сведения.

|Свойство|С|Новое значение по умолчанию|Дополнительные сведения|
|--------------|--------|-----------------|----------------------|
|channelInitializationTimeout|<xref:System.ServiceModel.NetTcpBinding>|30 секунд|Это свойство определяет, как долго TCP-соединение может пройти проверку подлинности с помощью протокола .NET Framing. Клиенту необходимо отправить некоторые исходные данные, прежде чем сервер получит достаточно сведений для аутентификации. Это время ожидания специально сделано меньше значения параметра ReceiveTimeout (10 мин) для того, чтобы непроверенные вредоносные клиенты не сохраняли соединение с сервером в течение долгого времени. Значение по умолчанию — 30 секунд. Дополнительные сведения о <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.ChannelInitializationTimeout%2A>|
|listenBacklog|<xref:System.ServiceModel.NetTcpBinding>|16 * число процессоров|Это свойство уровня сокетов, которое описывает количество допустимых, ожидающих подтверждения запросов в очереди. Если очередь по невыполненной работе по ожиданию передачи данных заполнится полностью, новые запросы будут отклоняться. Дополнительные сведения о <xref:System.ServiceModel.NetTcpBinding.ListenBacklog%2A>|
|maxPendingAccepts|ConnectionOrientedTransportBindingElement<br /><br /> SMSvcHost.exe|2 * количество процессоров для транспорта<br /><br /> 4 \* число процессоров для SMSvcHost. exe|Это свойство ограничивает число каналов, которое может прослушиваться в режиме ожидания на сервере. Когда параметру MaxPendingAccepts задано слишком маленькое значение, возникает небольшой промежуток времени, в течение которого ожидающие каналы начнут обслуживать подключения, но новые каналы прослушиваться не будут. Соединение может произойти именно в этот интервал, и оно не будет установлено, потому что на сервере нет ожидающих каналов. Это свойство может быть сконфигурировано путем задания свойству <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingConnections%2A> большего значения. Дополнительные сведения см. в разделе <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingAccepts%2A> и [Настройка службы совместного использования портов net. TCP](./feature-details/configuring-the-net-tcp-port-sharing-service.md)|
|maxPendingConnections|ConnectionOrientedTransportBindingElement|12 * количество процессоров|Это свойство определяет количество соединений, которое может быть принято транспортом, но которое не было принято диспетчером ServiceModel. Для настройки этого значения используйте свойство `MaxConnections` привязки или свойство `maxOutboundConnectionsPerEndpoint` элемента привязки. Дополнительные сведения о <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingConnections%2A>|
|receiveTimeout|SMSvcHost.exe|30 секунд|Это свойство определяет время ожидания для чтения данных кадрирования TCP и проведения распределения подключений из базовых подключений. Это выполняется, чтобы ограничить время, которое служба SMSvcHost.exe тратит на считывание начальных данных из входящего соединения. Дополнительные сведения см. [в разделе Настройка службы совместного использования портов net. TCP](./feature-details/configuring-the-net-tcp-port-sharing-service.md).|

> [!NOTE]
> Эти новые значения по умолчанию используются только при развертывании службы WCF на компьютере с платформой .NET Framework 4.5. При развертывании той же службы на компьютере с платформой .NET Framework 4.0 используются значения по умолчанию платформы .NET 4.0. В таких случаях рекомендуется настроить эти параметры явно.

## <a name="xmldictionaryreaderquotas"></a>XmlDictionaryReaderQuotas

<xref:System.Xml.XmlDictionaryReaderQuotas> содержит настраиваемые значения квот для средств чтения словаря XML, которые ограничивают объем памяти, используемый кодировщиком при создании сообщения. Хотя эти квоты и можно изменить, значения по умолчанию были изменены так, чтобы разработчикам редко приходилось их менять. Квота `MaxReceivedMessageSize` не была изменена, и с ее помощью можно по-прежнему ограничить потребление памяти, избегнув таким образом работы со сложными <xref:System.Xml.XmlDictionaryReaderQuotas>. В следующей таблице приведены квоты, их новые значения по умолчанию и краткое описание, для чего используется каждая квота.

|Имя квоты|Значение по умолчанию|Description|
|----------------|-------------------|-----------------|
|<xref:System.Xml.XmlDictionaryReaderQuotas.MaxArrayLength%2A>|Int32.MaxValue|Возвращает и задает максимально допустимую длину массива. Эта квота ограничивает максимальный размер массива примитивов, возвращаемых средством чтения XML, включая байтовые массивы. Эта квота ограничивает потребление памяти не в самом средстве чтения XML, а в компоненте, использующем средство чтения. Например, когда <xref:System.Runtime.Serialization.DataContractSerializer> использует средство чтения, защищенное <xref:System.Xml.XmlDictionaryReaderQuotas.MaxArrayLength%2A>, оно не десериализует байтовые массивы, чей размер превышает указанное в этой квоте значение.|
|<xref:System.Xml.XmlDictionaryReaderQuotas.MaxBytesPerRead%2A>|Int32.MaxValue|Возвращает и задает максимально допустимое число байтов, возвращаемых для каждой операции чтения. Эта квота ограничивает число байтов, которые считываются за одну операцию считывания при чтении открывающего тега элемента и его атрибутов. (В случае непотоковой передачи данных само имя элемента не входит в квоту.) Наличие слишком большого числа атрибутов XML может привести к неоправданно большому времени обработки, поскольку требуется проверка уникальности имен атрибутов. <xref:System.Xml.XmlDictionaryReaderQuotas.MaxBytesPerRead%2A> устраняет эту возможную проблему.|
|<xref:System.Xml.XmlDictionaryReaderQuotas.MaxDepth%2A>|Глубина в 128 узлов|Эта квота ограничивает максимальную глубину вложенности XML-элементов. <xref:System.Xml.XmlDictionaryReaderQuotas.MaxDepth%2A> взаимодействует с <xref:System.Xml.XmlDictionaryReaderQuotas.MaxBytesPerRead%2A>: средство чтения всегда сохраняет в памяти данные по текущему элементу и всем его предкам, поэтому максимальный потребляемый средством чтения объем памяти пропорционален произведению этих двух параметров. При десериализации графа объекта с глубоким вложением десериализатор принудительно получает доступ ко всему стеку, и выдается неисправимое исключение <xref:System.StackOverflowException>. Между вложением XML и вложением объекта существует прямая связь как для <xref:System.Runtime.Serialization.DataContractSerializer> , так и для <xref:System.Xml.Serialization.XmlSerializer>. <xref:System.Xml.XmlDictionaryReaderQuotas.MaxDepth%2A> используется для устранения этой проблемы.|
|<xref:System.Xml.XmlDictionaryReaderQuotas.MaxNameTableCharCount%2A>|Int32.MaxValue|Эта квота ограничивает максимальное количество символов, разрешенных в таблице имен. В таблице имен содержатся определенные строки (например пространства имен и префиксы), возникающие при обработке документа XML. Поскольку эти строки буферизуются в память, эта квота используется для предотвращения чрезмерной буферизации, если ожидается потоковая передача.|
|<xref:System.Xml.XmlDictionaryReaderQuotas.MaxStringContentLength%2A>|Int32.MaxValue|Эта квота ограничивает максимальный размер строки, возвращаемой средством чтения XML. Эта квота ограничивает потребление памяти не в самом средстве чтения XML, а в компоненте, использующем средство чтения. Например, когда <xref:System.Runtime.Serialization.DataContractSerializer> использует средство чтения, защищенное <xref:System.Xml.XmlDictionaryReaderQuotas.MaxStringContentLength%2A>, он не десериализует строки, чей размер превышает указанное в этой квоте значение.|

> [!IMPORTANT]
> Дополнительные сведения о защите данных см. в разделе "безопасная работа с XML" раздела [вопросы безопасности данных](./feature-details/security-considerations-for-data.md) .

> [!NOTE]
> Эти новые значения по умолчанию используются только при развертывании службы WCF на компьютере с платформой .NET Framework 4.5. При развертывании той же службы на компьютере с платформой .NET Framework 4.0 используются значения по умолчанию платформы .NET 4.0. В таких случаях рекомендуется настроить эти параметры явно.

## <a name="wcf-configuration-validation"></a>Проверка конфигурации WCF

Будучи частью процесса сборки в Visual Studio, файлы конфигурации WCF теперь проверяются. Если проверка завершается с ошибкой, то в Visual Studio отображается список ошибок и предупреждений.

## <a name="xml-editor-tooltips"></a>Подсказки в редакторе XML

В XML-редакторе Visual Studio отображаются подсказки для каждого элемента конфигурации (и его свойств), входящего в файл конфигурации службы. Это облегчает работу разработчиков по конфигурации WCF-служб.

## <a name="basichttpbinding-improvements"></a>Улучшения для BasicHttpBinding

1. Позволяет одной конечной точке WCF отвечать на разные режимы проверки подлинности.

2. Позволяет IIS контролировать настройки безопасности WCF-службы.
