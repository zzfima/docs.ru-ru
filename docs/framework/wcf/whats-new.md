---
title: "Новые возможности в Windows Communication Foundation 4.5 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF [WCF], новые возможности"
  - "Windows Communication Foundation [WCF], новые возможности"
ms.assetid: 7e93fe73-af93-46b5-9f63-32f761ee40cf
caps.latest.revision: 35
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 35
---
# Новые возможности в Windows Communication Foundation 4.5
В этом разделе рассматриваются новые возможности [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].  
  
## Функции упрощения WCF  
 Много работы было посвящено тому, чтобы сделать разработку и поддержку приложений WCF 4.5 более легкой.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Функции упрощения WCF](../../../docs/framework/wcf/wcf-simplification-features.md).  
  
### Поддержка асинхронного выполнения задач  
 По умолчанию команда добавления ссылки на службу формирует методы асинхронных операций службы, возвращающие объекты задач.Это выполняется как для синхронных, так и для асинхронных методов.Это позволяет вызывать операции службы асинхронно, используя новую модель асинхронного программирования на основе задач.При вызове сформированного прокси\-метода WCF создает объект задачи, представляющий асинхронную операцию, и возвращает ее.Задача завершается при завершении операции. При реализации асинхронной операции ее можно реализовать как асинхронную операцию на основе задачи.Дополнительные сведения см. в разделе [Синхронные и асинхронные операции](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).  
  
### Упрощенные сформированные файлы конфигурации  
 Клиентский файл конфигурации создается при добавлении ссылки на службу в Visual Studio или при использовании средства SvcUtil.exe.В предыдущих версиях WCF эти файлы конфигурации содержали значения каждого свойства привязки, даже если значение было значением по умолчанию.В WCF 4.5 сформированные файлы конфигурации содержат только те свойства привязки, которым присвоено значение не по умолчанию.  
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Функции упрощения WCF](../../../docs/framework/wcf/wcf-simplification-features.md)  
  
### Разработка в соответствии с парадигмой «Сначала контракт»  
 WCF теперь поддерживает разработку в соответствии с парадигмой «Сначала контракт».Средство svcutl.exe имеет переключатель \/serviceContract, который позволяет создавать контракты службы и данных на основе WSDL\-документа.  
  
### Добавление ссылки на службу из проекта переносимого подмножества  
 Проекты переносимого подмножества позволяют программистам, создающим сборки .NET, поддерживать одно дерево исходного кода и создавать сборки, одновременно поддерживая несколько платформ .NET \(настольные приложения, Silverlight, Windows Phone и XBOX\).Проекты переносимого подмножества обращаются только к переносимым сборкам .NET Framework, которые могут использоваться на любой платформе .NET.Процесс добавления такой же, как и при добавлении ссылки на службу в рамках любого другого клиентского приложения WCF.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Добавление ссылки на службу в проект переносного вложенного набора](../../../docs/framework/wcf/add-service-reference-in-a-portable-subset-project.md).  
  
### Изменились значения по умолчанию для режима совместимости с ASP.NET  
 WCF предоставляет режим совместимости с ASP.NET, дающий разработчикам при создании служб WCF полный доступ к функциям HTTP\-конвейера ASP.NET.Для использования этого режима необходимо установить атрибут `aspNetCompatibilityEnabled` в значение true в разделе [\<serviceHostingEnvironment\>](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) файла web.config.Кроме того, у любой службы в данном домене приложения свойство `RequirementsMode` в ее атрибуте <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> должно быть задано как значение <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode> или <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode>.По умолчанию атрибут <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> имеет значение <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode>.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][What's New in Windows Communication Foundation](../../../docs/framework/wcf/whats-new.md) и [Службы WCF и ASP.NET](../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).  
  
### Новые значения по умолчанию для свойств транспорта  
 Для упрощения настройки были изменены несколько значений по умолчанию для свойств транспорта.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Функции упрощения WCF](../../../docs/framework/wcf/wcf-simplification-features.md).  
  
### XmlDictionaryReaderQuotas  
 <xref:System.Xml.XmlDictionaryReaderQuotas> содержит настраиваемые значения квот для средств чтения словаря XML, которые ограничивают объем памяти, используемый кодировщиком при создании сообщения.Хотя эти квоты и можно изменить, значения по умолчанию были изменены для уменьшения вероятности явной настройки разработчиками этих данных.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Функции упрощения WCF](../../../docs/framework/wcf/wcf-simplification-features.md).  
  
### Проверка конфигурации WCF  
 В ходе выполнения процесса сборки в Visual Studio теперь выполняется проверка файлов конфигурации WCF на наличие атрибутов, заданных в проекте.Если проверка завершается с ошибкой, то в Visual Studio отображается список ошибок и предупреждений.  
  
### Подсказки в редакторе XML  
 В XML\-редакторе Visual Studio отображаются подсказки для каждого элемента конфигурации \(и его свойств\), входящего в файл конфигурации службы. Это облегчает работу разработчиков по конфигурации WCF\-служб.  
  
## Улучшения в потоковой передаче данных  
 Добавлена поддержка истинной асинхронной потоковой передачи, когда отправляющая сторона не блокирует потоки в случае, если принимающая сторона не считывает или считывает медленно, таким образом увеличивая масштабируемость решений.Снято ограничение буферизации сообщений, когда клиент отправляет потоковое сообщение службе WCF, размещенной на веб\-сервере служб IIS.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Функции упрощения WCF](../../../docs/framework/wcf/wcf-simplification-features.md).  
  
## Упрощено предоставление доступа к конечной точке по протоколу HTTPS в службах IIS  
 Было добавлено сопоставление протокола HTTPS для упрощения предоставления доступа к конечной точке по протоколу HTTPS.Чтобы включить конечную точку HTTPS, убедитесь, что веб\-сайт имеет привязку HTTPS и настроенный SSL\-сертификат, а затем просто включите HTTPS для виртуального каталога, в котором размещается служба.Если для службы включены метаданные, то доступ к ней будет также предоставлен по протоколу HTTPS.  
  
## Создание одного документа WSDL  
 Некоторые стеки обработки WSDL от сторонних производителей не могут обрабатывать документы WSDL, которые имеют зависимости от других документов посредством xsd:import.WCF теперь позволяет указывать, что все данные WSDL должны быть возвращены в одном документе.Чтобы запросить один документ WSDL, добавьте «?singleWSDL» к универсальному коду ресурса \(URI\) при запросе метаданных от службы.  
  
## Поддержка WebSocket  
 WebSockets — это технология, которая обеспечивает истинный двусторонний обмен сообщениями по портам 80 и 443, имеющий характеристики производительности, схожие с протоколом TCP.Были добавлены две привязки для поддержки обмена данными через транспорт WebSocket.<xref:System.ServiceModel.NetHttpBinding> и <xref:System.ServiceModel.NetHttpsBinding>.Дополнительные сведения см. в разделе [Привязки, предоставляемые системой](../../../docs/framework/wcf/system-provided-bindings.md).  
  
## Новые значения по умолчанию для свойств транспорта  
 В следующей таблице описываются измененные настройки и разделы, в которых можно найти дополнительные сведения.  
  
|Свойство|On|Новое значение по умолчанию|Дополнительные сведения см. в разделах|  
|--------------|--------|---------------------------------|--------------------------------------------|  
|channelInitializationTimeout|<xref:System.ServiceModel.NetTcpBinding>|30 секунд|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.ChannelInitializationTimeout%2A>|  
|listenBacklog|<xref:System.ServiceModel.NetTcpBinding>|12 \* количество процессоров|<xref:System.ServiceModel.NetTcpBinding.ListenBacklog%2A>|  
|maxPendingAccepts|ConnectionOrientedTransportBindingElement<br /><br /> SMSvcHost.exe|2 \* количество процессоров для транспорта<br /><br /> 4 \* количество процессоров для SMSvcHost.exe|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingAccepts%2A> [Configuring the Net.TCP Port Sharing Service](http://msdn.microsoft.com/ru-ru/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)|  
|maxPendingConnections|ConnectionOrientedTransportBindingElement|12 \* количество процессоров|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingConnections%2A>|  
|receiveTimeout|SMSvcHost.exe|30 секунд|[Configuring the Net.TCP Port Sharing Service](http://msdn.microsoft.com/ru-ru/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)|  
  
## Подсказки в редакторе XML  
 В XML\-редакторе Visual Studio отображаются подсказки для каждого элемента конфигурации \(и его свойств\), входящего в файл конфигурации службы. Это облегчает работу разработчиков по конфигурации WCF\-служб.  
  
## Настройка служб WCF в коде  
 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] позволяет разработчикам настраивать службы с помощью файлов конфигурации или кода.Файлы конфигурации используются, если необходимо настроить службу после ее развертывания.При использовании файлов конфигурации ИТ\-работнику требуется только обновить файл конфигурации без необходимости выполнять повторную компиляцию.Файлы конфигурации, однако, могут быть сложными и требовать больших усилий при обслуживании.Отсутствует поддержка отладки файлов конфигурации, и ссылки на элементы конфигурации осуществляются по именам, что усложняет работу и способствует совершению ошибок при создании файлов конфигурации.[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] также позволяет настраивать службы в коде.В предыдущих версиях [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] \(4.0 и ранее\) настройка служб легко выполнялась в коде в случае сценариев резидентных служб, класс <xref:System.ServiceModel.ServiceHost> позволял настроить конечные точки и поведение до вызова метода ServiceHost.Open.Однако в сценариях с размещением в Интернете нет прямого доступа к классу <xref:System.ServiceModel.ServiceHost>.Чтобы настроить службу, размещенную в сети, приходилось создавать класс <xref:System.ServiceModel.ServiceHostFactory>, который создавал <xref:System.ServiceModel.ServiceHost> и выполнял необходимые настройки.Начиная с версии .NET 4.5, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] предоставляет более простой способ настройки как для резидентных служб, так и для служб, размещаемых в сети.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Настройка служб WCF в коде](../../../docs/framework/wcf/configuring-wcf-services-in-code.md).  
  
## Кэширование ChannelFactory  
 Клиентские приложения WCF используют класс <xref:System.ServiceModel.ChannelFactory%601> для создания коммуникационного канала со службой WCF.Создание экземпляров класса <xref:System.ServiceModel.ChannelFactory%601> оказывает определенное влияние на производительность, поскольку выполняются следующие операции:  
  
1.  Построение дерева <xref:System.ServiceModel.Description.ContractDescription>  
  
2.  Отображение всех необходимых типов CLR  
  
3.  Построение стека каналов  
  
4.  Освобождение ресурсов  
  
 Чтобы уменьшить дополнительные расходы ресурсов, WCF может кэшировать фабрики каналов при использовании прокси клиента WCF.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Производство каналов и кэширование](../../../docs/framework/wcf/feature-details/channel-factory-and-caching.md).  
  
## Сжатие и двоичный кодировщик  
 Начиная с версии WCF 4.5, в двоичном кодировщике появилась поддержка сжатия.Тип сжатия задается с помощью свойства <xref:System.ServiceModel.Channels.BinaryMessageEncodingElement.CompressionFormat%2A>.Свойство <xref:System.ServiceModel.Channels.BinaryMessageEncodingElement.CompressionFormat%2A> должно быть задано и в клиенте и в службе.Сжатие будет работать для протоколов HTTP, HTTPS и TCP.Если клиент указывает использование сжатия, но служба его не поддерживает, возникает исключение протокола, указывающее на несоответствие.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Выбор кодировщика сообщений](../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
  
## UDP  
 Добавлена поддержка для транспорта по протоколу UDP, позволяющая разработчикам создавать службы, использующие обмен сообщениями «отправить и забыть».Клиент отправляет сообщение службе, но не ожидает от нее ответа.  
  
## Поддержка нескольких видов проверок подлинности  
 Была добавлена поддержка нескольких режимов проверок подлинности, поддерживаемых службами IIS, в одной конечной точке WCF при использовании транспорта HTTP и безопасности транспорта.Служба IIS позволяет включить несколько режимов проверки подлинности в виртуальном каталоге. Эта функция позволяет одной конечной точке WCF поддерживать несколько режимов проверки подлинности, разрешенных для виртуального каталога, в котором размещена служба WCF.  
  
## Поддержка IDN  
 Добавлена поддержка служб WCF с интернационализированными именами домена \(IDN\).Дополнительные сведения см. в разделе [WCF и международные доменные имена](../../../docs/framework/wcf/feature-details/wcf-and-internationalized-domain-names.md).  
  
## HttpClient  
 Был добавлен новый класс <xref:System.Net.Http.HttpClient>, существенного облегчающий работу с HTTP\-запросами.Дополнительные сведения см. в разделе [Связь приложений с социальными сетями и подключение к HTTP\-службам](http://go.microsoft.com/fwlink/?LinkId=231886) и [Пример HTTP\-клиента](http://code.msdn.microsoft.com/windowsapps/HttpClient-sample-55700664).  
  
## Технология Intellisense в файлах конфигурации  
 Значения атрибутов в файлах конфигурации для настраиваемых атрибутов, определенных в проекте, теперь поддерживают технологию intellisense для ускорения работы.  
  
## Всплывающие подсказки в файлах конфигурации  
 Элементы и атрибуты [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] теперь имеют подсказки в редакторе XML, что позволяет более точно и быстро определять назначение элементов и атрибутов.  
  
## Вставка данных в виде классов  
 В проекте WCF типы данных, определенные в XML \(например, предоставленные как служба\), могут быть вставлены непосредственно в кодовую страницу.XML\-тип будет вставлен как тип CLR.Дополнительные сведения см. в разделе [Формирование классов типов данных из XML](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md).  
  
## WebServiceHost и конечные точки по умолчанию.  
 В Visual Studio 2010 WebServiceHost автоматически создавал конечную точку по умолчанию независимо от того, была она явно указана или нет.В Visual Studio 2012 WebServiceHost создаст конечную точку по умолчанию, только если не была явно добавлена ни одна конечная точка.Если клиент ожидает конечную точку по умолчанию, можно явным образом добавить точку и направить клиента к ней.Кроме того, можно вернуть прежнее поведение WCF, добавив следующий параметр в файл конфигурации приложения.  
  
```xml  
<appSettings>  
    <add key="wcf:webservicehost:enableautomaticendpointscompatability" value="true"/>  
  </appSettings>  
  
```  
  
## IHttpCookieContainerManager  
 Этот интерфейс, предоставляемый <xref:System.ServiceModel.Channels.HttpChannelFactory>, существенно упрощает работу с куки\-файлами на стороне клиента.Когда свойство AllowCookies имеет значение true для привязки, доступ к куки\-файлам можно получить следующим образом:  
  
```csharp  
IHttpCookieContainerManager cookieManager = factory.GetProperty<IHttpCookieContainerManager>();   
System.Net.CookieContainer container = cookieManager.CookieContainer;  
  
```  
  
 Затем можно получать или устанавливать куки\-файлы из <xref:System.Net.CookieContainer>.Когда свойство AllowCookies имеет значение false, куки\-файл можно получить вручную с помощью <xref:System.ServiceModel.OperationContext> и отправить его запросом с помощью другого <xref:System.ServiceModel.OperationContext> или средства проверки сообщений.Интерфейс IHttpCookieContainerManager позволяет выполнить проверку подлинности пользователя для службы и использовать куки\-файл, возвращенный службой, для проверки подлинности в других службах.