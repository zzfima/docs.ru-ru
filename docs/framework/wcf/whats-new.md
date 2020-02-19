---
title: Новые возможности в Windows Communication Foundation 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], what's new
- Windows Communication Foundation [WCF], what's new
ms.assetid: 7e93fe73-af93-46b5-9f63-32f761ee40cf
ms.openlocfilehash: b22266efe2e775acd04c400cf9da50bffab28183
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449508"
---
# <a name="whats-new-in-windows-communication-foundation-45"></a>Новые возможности в Windows Communication Foundation 4.5

В этом разделе обсуждаются новые функции Windows Communication Foundation (WCF) версии 4,5.

## <a name="wcf-simplification-features"></a>Функции упрощения WCF

Много работы было посвящено тому, чтобы сделать разработку и поддержку приложений WCF 4.5 более легкой. Дополнительные сведения см. в разделе [функции упрощения WCF](wcf-simplification-features.md).

### <a name="task-based-async-support"></a>Поддержка асинхронного выполнения задач

По умолчанию команда добавления ссылки на службу формирует методы асинхронных операций службы, возвращающие объекты задач. Это выполняется как для синхронных, так и для асинхронных методов. Это позволяет вызывать операции службы асинхронно, используя новую модель асинхронного программирования на основе задач. При вызове сформированного прокси-метода WCF создает объект задачи, представляющий асинхронную операцию, и возвращает ее. Задача завершается после завершения операции. При реализации асинхронной операции ее можно реализовать как асинхронную операцию на основе задач. Дополнительные сведения см. в разделе [синхронные и асинхронные операции](synchronous-and-asynchronous-operations.md).

### <a name="simplified-generated-configuration-files"></a>Упрощенные сформированные файлы конфигурации

Клиентский файл конфигурации создается при добавлении ссылки на службу в Visual Studio или при использовании средства SvcUtil.exe. В предыдущих версиях WCF эти файлы конфигурации содержали значения каждого свойства привязки, даже если значение было значением по умолчанию. В WCF 4.5 сформированные файлы конфигурации содержат только те свойства привязки, которым присвоено значение не по умолчанию.

Дополнительные сведения см. в разделе [функции упрощения WCF](wcf-simplification-features.md).

### <a name="contract-first-development"></a>Разработка в соответствии с парадигмой «Сначала контракт»

WCF теперь поддерживает разработку в соответствии с парадигмой «Сначала контракт». Svcutil. exe имеет параметр/Сервицеконтракт, который позволяет создавать контракты служб и данных из документа WSDL.

### <a name="add-service-reference-from-a-portable-subset-project"></a>Добавление ссылки на службу из проекта переносимого подмножества

Проекты переносимых подмножеств позволяют программистам сборок .NET поддерживать единое дерево исходного кода и систему сборки, одновременно обеспечивая поддержку нескольких платформ .NET (настольные системы, Silverlight, Windows Phone и Xbox). Переносимые проекты подмножества ссылаются только на переносимые библиотеки .NET, которые являются сборками, которые можно использовать на любой платформе .NET. Процесс добавления такой же, как и при добавлении ссылки на службу в рамках любого другого клиентского приложения WCF. Дополнительные сведения см. [в разделе Добавление ссылки на службу в проекте переносимого подмножества](add-service-reference-in-a-portable-subset-project.md).

### <a name="aspnet-compatibility-mode-default-changed"></a>Изменились значения по умолчанию для режима совместимости с ASP.NET

WCF предоставляет режим совместимости с ASP.NET, дающий разработчикам при создании служб WCF полный доступ к функциям HTTP-конвейера ASP.NET. Чтобы использовать этот режим, необходимо присвоить атрибуту `aspNetCompatibilityEnabled` значение true в разделе [\<serviceHostingEnvironment >](../configure-apps/file-schema/wcf/servicehostingenvironment.md) файла Web. config. Кроме того, любая служба в этом appDomain должна иметь свойство `RequirementsMode` в своем <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>е, для которого задано значение <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed> или <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>. По умолчанию <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> теперь имеет значение <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>. Дополнительные сведения см. в разделе [WCF Services and ASP.NET](./feature-details/wcf-services-and-aspnet.md).

### <a name="new-transport-default-values"></a>Новые значения по умолчанию для свойств транспорта

Для упрощения настройки были изменены несколько значений по умолчанию для свойств транспорта. Дополнительные сведения см. в разделе [функции упрощения WCF](wcf-simplification-features.md).

### <a name="xmldictionaryreaderquotas"></a>XmlDictionaryReaderQuotas

<xref:System.Xml.XmlDictionaryReaderQuotas> содержит настраиваемые значения квот для средств чтения словаря XML, которые ограничивают объем памяти, используемый кодировщиком при создании сообщения. Хотя эти квоты и можно изменить, значения по умолчанию были изменены для уменьшения вероятности явной настройки разработчиками этих данных. Дополнительные сведения см. в разделе [функции упрощения WCF](wcf-simplification-features.md).

### <a name="wcf-configuration-validation"></a>Проверка конфигурации WCF

В ходе выполнения процесса сборки в Visual Studio теперь выполняется проверка файлов конфигурации WCF на наличие атрибутов, заданных в проекте. Если проверка завершается с ошибкой, то в Visual Studio отображается список ошибок и предупреждений.

### <a name="xml-editor-tooltips"></a>Подсказки в редакторе XML

В XML-редакторе Visual Studio отображаются подсказки для каждого элемента конфигурации (и его свойств), входящего в файл конфигурации службы. Это облегчает работу разработчиков по конфигурации WCF-служб.

## <a name="streaming-improvements"></a>Улучшения в потоковой передаче данных

Добавлена поддержка истинной асинхронной потоковой передачи, когда отправляющая сторона не блокирует потоки в случае, если принимающая сторона не считывает или считывает медленно, таким образом увеличивая масштабируемость решений. Снято ограничение буферизации сообщений, когда клиент отправляет потоковое сообщение службе WCF, размещенной на веб-сервере служб IIS. Дополнительные сведения см. в разделе [функции упрощения WCF](wcf-simplification-features.md).

## <a name="simplifying-exposing-an-endpoint-over-https-with-iis"></a>Упрощено предоставление доступа к конечной точке по протоколу HTTPS в службах IIS

Было добавлено сопоставление протокола HTTPS для упрощения предоставления доступа к конечной точке по протоколу HTTPS. Чтобы включить конечную точку HTTPS, убедитесь, что веб-сайт имеет привязку HTTPS и настроенный SSL-сертификат, а затем просто включите HTTPS для виртуального каталога, в котором размещается служба. Если для службы включены метаданные, то доступ к ней будет также предоставлен по протоколу HTTPS.

## <a name="generating-a-single-wsdl-document"></a>Создание одного документа WSDL

Некоторые стеки обработки WSDL от сторонних производителей не могут обрабатывать документы WSDL, которые имеют зависимости от других документов посредством xsd:import. WCF теперь позволяет указывать, что все данные WSDL должны быть возвращены в одном документе. Чтобы запросить один документ WSDL, добавьте "? Синглевсдл" в универсальный код ресурса (URI) при запросе метаданных из службы.

## <a name="websocket-support"></a>Поддержка WebSocket

WebSockets - это технология, которая обеспечивает истинный двусторонний обмен сообщениями по портам 80 и 443, имеющий характеристики производительности, схожие с протоколом TCP. Были добавлены две привязки для поддержки обмена данными через транспорт WebSocket. <xref:System.ServiceModel.NetHttpBinding> и <xref:System.ServiceModel.NetHttpsBinding>. Дополнительные сведения см. в разделе [привязки, предоставляемые системой](system-provided-bindings.md).

## <a name="new-transport-default-values"></a>Новые значения по умолчанию для свойств транспорта

В следующей таблице описываются измененные настройки и разделы, в которых можно найти дополнительные сведения.

|Свойство|С|Новое значение по умолчанию|Дополнительные сведения см. в разделе|
|--------------|--------|-----------------|------------------------------|
|channelInitializationTimeout|<xref:System.ServiceModel.NetTcpBinding>|30 секунд|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.ChannelInitializationTimeout%2A>|
|listenBacklog|<xref:System.ServiceModel.NetTcpBinding>|12 * количество процессоров|<xref:System.ServiceModel.NetTcpBinding.ListenBacklog%2A>|
|maxPendingAccepts|ConnectionOrientedTransportBindingElement<br /><br /> SMSvcHost.exe|2 * количество процессоров для транспорта<br /><br /> 4 \* число процессоров для SMSvcHost. exe|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingAccepts%2A> [настройке службы совместного использования портов net. TCP](./feature-details/configuring-the-net-tcp-port-sharing-service.md)|
|maxPendingConnections|ConnectionOrientedTransportBindingElement|12 * количество процессоров|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingConnections%2A>|
|receiveTimeout|SMSvcHost.exe|30 секунд|[Настройка службы совместного использования портов Net.TCP](./feature-details/configuring-the-net-tcp-port-sharing-service.md)|

## <a name="xml-editor-tooltips"></a>Подсказки в редакторе XML

В XML-редакторе Visual Studio отображаются подсказки для каждого элемента конфигурации (и его свойств), входящего в файл конфигурации службы. Это облегчает работу разработчиков по конфигурации WCF-служб.

## <a name="configuring-wcf-services-in-code"></a>Настройка служб WCF в коде

Windows Communication Foundation (WCF) позволяет разработчикам настраивать службы с помощью файлов конфигурации или кода. Файлы конфигурации используются, если необходимо настроить службу после ее развертывания. При использовании файлов конфигурации ИТ-работнику требуется только обновить файл конфигурации без необходимости выполнять повторную компиляцию. Файлы конфигурации, однако, могут быть сложными и требовать больших усилий при обслуживании. Отсутствует поддержка отладки файлов конфигурации, и ссылки на элементы конфигурации осуществляются по именам, что усложняет работу и способствует совершению ошибок при создании файлов конфигурации. WCF также позволяет настраивать службы в коде. В более ранних версиях WCF (4,0 и более ранних версий) Настройка служб в коде была непростой в собственных сценариях, класс <xref:System.ServiceModel.ServiceHost> позволял вам настроить конечные точки и поведения до вызова ServiceHost. Open. Однако в сценариях с размещением в Интернете нет прямого доступа к классу <xref:System.ServiceModel.ServiceHost>. Чтобы настроить службу, размещенную в сети, приходилось создавать класс `System.ServiceModel.ServiceHostFactory`, который создавал <xref:System.ServiceModel.Activation.ServiceHostFactory> и выполнял необходимые настройки. Начиная с .NET 4,5, WCF предоставляет более простой способ настройки автономных и размещенных в Интернете служб в коде. Дополнительные сведения см. [в разделе Настройка служб WCF в коде](configuring-wcf-services-in-code.md).

## <a name="channelfactory-caching"></a>Кэширование ChannelFactory

Клиентские приложения WCF используют класс <xref:System.ServiceModel.ChannelFactory%601> для создания коммуникационного канала со службой WCF. Создание экземпляров класса <xref:System.ServiceModel.ChannelFactory%601> оказывает определенное влияние на производительность, поскольку выполняются следующие операции:

1. Построение дерева <xref:System.ServiceModel.Description.ContractDescription>

2. Отображение всех необходимых типов CLR

3. Построение стека каналов

4. Освобождение ресурсов

Чтобы уменьшить дополнительные расходы ресурсов, WCF может кэшировать фабрики каналов при использовании прокси клиента WCF. Дополнительные сведения см. в статье [фабрика каналов и кэширование](./feature-details/channel-factory-and-caching.md).

## <a name="compression-and-the-binary-encoder"></a>Сжатие и двоичный кодировщик

Начиная с версии WCF 4.5, в двоичном кодировщике появилась поддержка сжатия. Тип сжатия задается с помощью свойства <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement.CompressionFormat%2A>. Свойство <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement.CompressionFormat%2A> должно быть задано и в клиенте и в службе. Сжатие будет работать для протоколов HTTP, HTTPS и TCP. Если клиент указывает использование сжатия, но служба его не поддерживает, возникает исключение протокола, указывающее на несоответствие. Дополнительные сведения см. [в разделе Выбор кодировщика сообщений](./feature-details/choosing-a-message-encoder.md).

## <a name="udp"></a>UDP

Добавлена поддержка для транспорта UDP, который позволяет разработчикам писать службы, использующие "пожар и забыть" сообщения. Клиент отправляет сообщение службе, но не ожидает от нее ответа.

## <a name="multiple-authentication-support"></a>Поддержка нескольких видов проверок подлинности

Была добавлена поддержка нескольких режимов проверок подлинности, поддерживаемых службами IIS, в одной конечной точке WCF при использовании транспорта HTTP и безопасности транспорта. Служба IIS позволяет включить несколько режимов проверки подлинности в виртуальном каталоге. Эта возможность позволяет одной конечной точке WCF поддерживать несколько режимов проверки подлинности, разрешенных для виртуального каталога, в котором размещена служба WCF.

## <a name="idn-support"></a>Поддержка IDN

Добавлена поддержка служб WCF с интернационализированными именами домена (IDN). Дополнительные сведения см. в разделе [WCF и международные доменные имена](./feature-details/wcf-and-internationalized-domain-names.md).

## <a name="httpclient"></a>HttpClient

Был добавлен новый класс <xref:System.Net.Http.HttpClient>, существенного облегчающий работу с HTTP-запросами. Дополнительные сведения см. в разделе [Создание приложений в социальных сетях и подключение к службам HTTP](https://channel9.msdn.com/Events/BUILD/BUILD2011/PLAT-581T) и [Пример HTTP-клиента](https://code.msdn.microsoft.com/windowsapps/HttpClient-sample-55700664).

## <a name="configuration-intellisense"></a>Технология Intellisense в файлах конфигурации

Значения атрибутов в файлах конфигурации для настраиваемых атрибутов, определенных в проекте, теперь поддерживают технологию intellisense для ускорения работы.

## <a name="configuration-tooltips"></a>Всплывающие подсказки в файлах конфигурации

Элементы и атрибуты WCF теперь имеют подсказки в редакторе XML, что упрощает и точно определяет назначение элемента или атрибута.

## <a name="paste-data-as-classes"></a>Вставка данных в виде классов

В проекте WCF типы данных, определенные в XML (например, предоставленные как служба), могут быть вставлены непосредственно в кодовую страницу. XML-тип будет вставлен как тип CLR. Дополнительные сведения см. [в разделе Создание классов типов данных из XML](generating-data-type-classes-from-xml.md) .

## <a name="webservicehost-and-default-endpoints"></a>WebServiceHost и конечные точки по умолчанию.

В Visual Studio 2010 WebServiceHost автоматически создавал конечную точку по умолчанию независимо от того, была она явно указана или нет. В Visual Studio 2012 и более поздних версиях класс ServiceHost создает конечную точку по умолчанию только в том случае, если конечные точки явно не добавлены. Если клиент ожидает конечную точку по умолчанию, можно явно добавить конечную точку и указать клиенту на нее. Кроме того, можно вернуть прежнее поведение WCF, добавив следующий параметр в файл конфигурации приложения.

```xml
<appSettings>
    <add key="wcf:webservicehost:enableautomaticendpointscompatability" value="true"/>
  </appSettings>
```

## <a name="ihttpcookiecontainermanager"></a>IHttpCookieContainerManager

Этот интерфейс, предоставляемый <xref:System.ServiceModel.Channels.IChannelFactory%601>, существенно упрощает работу с куки-файлами на стороне клиента. Когда свойство AllowCookies имеет значение true для привязки, доступ к куки-файлам можно получить следующим образом:

```csharp
IHttpCookieContainerManager cookieManager = factory.GetProperty<IHttpCookieContainerManager>();
System.Net.CookieContainer container = cookieManager.CookieContainer;
```

Затем можно получать или устанавливать куки-файлы из <xref:System.Net.CookieContainer>. Когда свойство AllowCookies имеет значение false, куки-файл можно получить вручную с помощью <xref:System.ServiceModel.OperationContext> и отправить его запросом с помощью другого <xref:System.ServiceModel.OperationContext> или средства проверки сообщений. Интерфейс IHttpCookieContainerManager позволяет выполнить проверку подлинности пользователя для службы и использовать куки-файл, возвращенный службой, для проверки подлинности в других службах.
