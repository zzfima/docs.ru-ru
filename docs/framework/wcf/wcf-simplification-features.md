---
title: "Функции упрощения WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4535a511-6064-4da0-b361-80262a891663
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Функции упрощения WCF
В этом разделе описываются новые функции, упрощающие написание приложений WCF.  
  
## Упрощенные сформированные файлы конфигурации  
 Клиентский файл конфигурации создается при добавлении ссылки на службу в Visual Studio или при использовании средства SvcUtil.exe.В предыдущих версиях WCF эти файлы конфигурации содержали значения каждого свойства привязки, даже если значение было значением по умолчанию.В WCF 4.5 сформированные файлы конфигурации содержат только те свойства привязки, которым присвоено значение не по умолчанию.  
  
 Далее приведен пример файла конфигурации, сформированного WCF 3.0.  
  
```  
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
  
```  
  
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
  
## Разработка в соответствии с парадигмой «Сначала контракт»  
 WCF теперь поддерживает разработку в соответствии с парадигмой «Сначала контракт».Средство svcutl.exe имеет переключатель \/serviceContract, который позволяет создавать контракты служб и данных на основе WSDL\-документа.  
  
## Добавление ссылки на службу из проекта переносимого подмножества  
 Проекты переносимого подмножества позволяют программистам, создающим сборки .NET, поддерживать одно дерево исходного кода и создавать сборки, одновременно поддерживая несколько платформ .NET \(настольные приложения, Silverlight, Windows Phone и XBOX\).Проекты переносимого подмножества обращаются только к переносимым сборкам .NET Framework, которые могут использоваться на любой платформе .NET.Процесс добавления такой же, как и при добавлении ссылки на службу в рамках любого другого клиентского приложения WCF.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Добавление ссылки на службу в проект переносного вложенного набора](../../../docs/framework/wcf/add-service-reference-in-a-portable-subset-project.md).  
  
## Изменились значения по умолчанию для режима совместимости с ASP.NET  
 WCF предоставляет режим совместимости с ASP.NET, дающий разработчикам при создании служб WCF полный доступ к функциям HTTP\-конвейера ASP.NET.Для использования этого режима необходимо установить атрибут `aspNetCompatibilityEnabled` в значение true в разделе [\<serviceHostingEnvironment\>](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) файла web.config.Кроме того, у любой службы в данном домене приложения свойство `RequirementsMode` в ее атрибуте <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> должно быть задано как значение <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode> или <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode>.По умолчанию <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> имеет значение <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode>, и стандартный набор шаблонов для приложения WCF службы задает атрибуту `aspNetCompatibilityEnabled` значение `true`.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Новые возможности в Windows Communication Foundation 4.5](../../../docs/framework/wcf/whats-new.md) и [Службы WCF и ASP.NET](../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).  
  
## Улучшения в потоковой передаче данных  
  
-   В WCF была добавлена новая поддержка асинхронной потоковой передачи данных.Чтобы включить поддержку асинхронной потоковой передачи данных, добавьте поведение конечной точки <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior> в основное приложение службы и установите свойству <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior.AsynchronousSendEnabled%2A> значение `true`.Это может улучшить масштабируемость, когда служба отправляет потоковые сообщения нескольким клиентам, которые медленно считывают сообщения.WCF больше не блокирует один поток для каждого клиента и освобождает поток для обслуживания другого клиента.  
  
-   Убраны ограничения для буферизации сообщений, возникающие, когда служба размещается в IIS.В предыдущих версиях WCF при получении сообщения для размещенной в IIS службы, использующей потоковую передачу, ASP.NET перед отправкой сообщения в WCF поместило бы его в буфер целиком.Это привело бы к использованию большого объема памяти.Эта буферизация была ликвидирована в .NET 4.5, и теперь WCF\-службы, размещаемые в IIS, могут начинать обработку входящего потока до получения всего сообщения, поэтому реализуется истинная потоковая передача данных.Это позволяет WCF\-службам моментально реагировать на сообщения, улучшая производительность.Кроме того, теперь вам больше не требуется указывать значение для `maxRequestLength`, ограничивающего размер входящих запросов в ASP.NET.Если данное свойство установлено, то оно не учитывается.[!INCLUDE[crabout](../../../includes/crabout-md.md)]`maxRequestLength` см. в разделе [\<httpRuntime\> — элемент конфигурации](http://go.microsoft.com/fwlink/?LinkId=223344).По\-прежнему требуется выполнять настройку параметра maxAllowedContentLength, [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Ограничение запросов IIS](http://go.microsoft.com/fwlink/?LinkId=225908).  
  
## Новые значения по умолчанию для свойств транспорта  
 В следующей таблице описываются измененные настройки и разделы, в которых можно найти дополнительные сведения.  
  
|Свойство|On|Новое значение по умолчанию|Дополнительные сведения|  
|--------------|--------|---------------------------------|-----------------------------|  
|channelInitializationTimeout|<xref:System.ServiceModel.NetTcpBinding>|30 секунд|Это свойство задает время, в течение которого подключение TCP может выполнить свою проверку подлинности с помощью протокола кадрирования .Net.Клиенту необходимо отправить некоторые исходные данные, прежде чем сервер получит достаточно сведений для аутентификации.Это время ожидания специально сделано меньше значения параметра ReceiveTimeout \(10 мин\) для того, чтобы непроверенные вредоносные клиенты не сохраняли соединение с сервером в течение долгого времени.Значение по умолчанию — 30 секунды.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.ChannelInitializationTimeout%2A>|  
|listenBacklog|<xref:System.ServiceModel.NetTcpBinding>|16 \* количество процессоров|Это свойство уровня сокетов, которое описывает количество допустимых, ожидающих подтверждения запросов в очереди.Если очередь по невыполненной работе по ожиданию передачи данных заполнится полностью, новые запросы будут отклоняться.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<xref:System.ServiceModel.NetTcpBinding.ListenBacklog%2A>|  
|maxPendingAccepts|ConnectionOrientedTransportBindingElement<br /><br /> SMSvcHost.exe|2 \* количество процессоров для транспорта<br /><br /> 4 \* количество процессоров для SMSvcHost.exe|Это свойство ограничивает число каналов, которое может прослушиваться в режиме ожидания на сервере.Когда параметру MaxPendingAccepts задано слишком маленькое значение, возникает небольшой промежуток времени, в течение которого ожидающие каналы начнут обслуживать подключения, но новые каналы прослушиваться не будут.Соединение может произойти именно в этот интервал, и оно не будет установлено, потому что на сервере нет ожидающих каналов.Это свойство может быть сконфигурировано путем задания свойству <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingConnections%2A> большего значения.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)].<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingAccepts%2A> и [Configuring the Net.TCP Port Sharing Service](http://msdn.microsoft.com/ru-ru/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)|  
|maxPendingConnections|ConnectionOrientedTransportBindingElement|12 \* количество процессоров|Это свойство определяет количество соединений, которое может быть принято транспортом, но которое не было принято диспетчером ServiceModel.Для настройки этого значения используйте свойство `MaxConnections` привязки или свойство `maxOutboundConnectionsPerEndpoint` элемента привязки.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingConnections%2A>|  
|receiveTimeout|SMSvcHost.exe|30 секунд|Это свойство определяет время ожидания для чтения данных кадрирования TCP и проведения распределения подключений из базовых подключений.Это выполняется, чтобы ограничить время, которое служба SMSvcHost.exe тратит на считывание начальных данных из входящего соединения.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Configuring the Net.TCP Port Sharing Service](http://msdn.microsoft.com/ru-ru/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0).|  
  
> [!NOTE]
>  Эти новые значения по умолчанию используются только при развертывании службы WCF на компьютере с платформой .NET Framework 4.5.При развертывании той же службы на компьютере с платформой .NET Framework 4.0 используются значения по умолчанию платформы .NET 4.0.В таких случаях рекомендуется настроить эти параметры явно.  
  
## XmlDictionaryReaderQuotas  
 <xref:System.Xml.XmlDictionaryReaderQuotas> содержит настраиваемые значения квот для средств чтения словаря XML, которые ограничивают объем памяти, используемый кодировщиком при создании сообщения.Хотя эти квоты и можно изменить, значения по умолчанию были изменены так, чтобы разработчикам редко приходилось их менять.Квота `MaxReceivedMessageSize` не была изменена, и с ее помощью можно по\-прежнему ограничить потребление памяти, избегнув таким образом работы со сложными <xref:System.Xml.XmlDictionaryReaderQuotas>.В следующей таблице приведены квоты, их новые значения по умолчанию и краткое описание, для чего используется каждая квота.  
  
|Имя квоты|Значение по умолчанию|Описание|  
|---------------|---------------------------|--------------|  
|<xref:System.Xml.XmlDictionaryReaderQuotas.MaxArrayLength%2A>|Int32.MaxValue|Возвращает и задает максимально допустимую длину массива.Эта квота ограничивает максимальный размер массива примитивов, возвращаемых средством чтения XML, включая байтовые массивы.Эта квота ограничивает потребление памяти не в самом средстве чтения XML, а в компоненте, использующем средство чтения.Например, когда <xref:System.Runtime.Serialization.DataContractSerializer> использует средство чтения, защищенное <xref:System.Xml.XmlDictionaryReaderQuotas.MaxArrayLength%2A>, оно не десериализует байтовые массивы, чей размер превышает указанное в этой квоте значение.|  
|<xref:System.Xml.XmlDictionaryReaderQuotas.MaxBytesPerRead%2A>|Int32.MaxValue|Возвращает и задает максимально допустимое число байтов, возвращаемых для каждой операции чтения.Эта квота ограничивает число байтов, которые считываются за одну операцию считывания при чтении открывающего тега элемента и его атрибутов.\(В случае непотоковой передачи данных само имя элемента не входит в квоту.\)Наличие слишком большого числа атрибутов XML может привести к неоправданно большому времени обработки, поскольку требуется проверка уникальности имен атрибутов.<xref:System.Xml.XmlDictionaryReaderQuotas.MaxBytesPerRead%2A> устраняет эту возможную проблему.|  
|<xref:System.Xml.XmlDictionaryReaderQuotas.MaxDepth%2A>|Глубина в 128 узлов|Эта квота ограничивает максимальную глубину вложенности XML\-элементов.<xref:System.Xml.XmlDictionaryReaderQuotas.MaxDepth%2A> взаимодействует с <xref:System.Xml.XmlDictionaryReaderQuotas.MaxBytesPerRead%2A>: средство чтения всегда сохраняет в памяти данные по текущему элементу и всем его предкам, поэтому максимальный потребляемый средством чтения объем памяти пропорционален произведению этих двух параметров.При десериализации графа объекта с глубоким вложением десериализатор принудительно получает доступ ко всему стеку, и выдается неисправимое исключение <xref:System.StackOverflowException>.Между вложением XML и вложением объекта существует прямая связь как для <xref:System.Runtime.Serialization.DataContractSerializer>, так и для <xref:System.Runtime.Serialization.XmlSerializer>.<xref:System.Xml.XmlDictionaryReaderQuotas.MaxDepth%2A> используется для устранения этой проблемы.|  
|<xref:System.Xml.XmlDictionaryReaderQuotas.MaxNameTableCharCount%2A>|Int32.MaxValue|Эта квота ограничивает максимальное количество символов, разрешенных в таблице имен.В таблице имен содержатся определенные строки \(например пространства имен и префиксы\), возникающие при обработке документа XML.Поскольку эти строки буферизуются в память, эта квота используется для предотвращения чрезмерной буферизации, если ожидается потоковая передача.|  
|<xref:System.Xml.XmlDictionaryReaderQuotas.MaxStringContentLength%2A>|Int32.MaxValue|Эта квота ограничивает максимальный размер строки, возвращаемой средством чтения XML.Эта квота ограничивает потребление памяти не в самом средстве чтения XML, а в компоненте, использующем средство чтения.Например, когда <xref:System.Runtime.Serialization.DataContractSerializer> использует средство чтения, защищенное <xref:System.Xml.XmlDictionaryReaderQuotas.MaxStringContentLength%2A>, он не десериализует строки, чей размер превышает указанное в этой квоте значение.|  
  
> [!IMPORTANT]
>  Обратитесь к разделу «Безопасное использование XML» [Вопросы безопасности для данных](../../../docs/framework/wcf/feature-details/security-considerations-for-data.md), в котором приводятся дополнительные сведения об обеспечении безопасности данных.  
  
> [!NOTE]
>  Эти новые значения по умолчанию используются только при развертывании службы WCF на компьютере с платформой .NET Framework 4.5.При развертывании той же службы на компьютере с платформой .NET Framework 4.0 используются значения по умолчанию платформы .NET 4.0.В таких случаях рекомендуется настроить эти параметры явно.  
  
## Проверка конфигурации WCF  
 Будучи частью процесса сборки в Visual Studio, файлы конфигурации WCF теперь проверяются.Если проверка завершается с ошибкой, то в Visual Studio отображается список ошибок и предупреждений.  
  
## Подсказки в редакторе XML  
 В XML\-редакторе Visual Studio отображаются подсказки для каждого элемента конфигурации \(и его свойств\), входящего в файл конфигурации службы. Это облегчает работу разработчиков по конфигурации WCF\-служб.  
  
## Улучшения для BasicHttpBinding  
  
1.  Позволяет одной конечной точке WCF отвечать на разные режимы проверки подлинности.  
  
2.  Позволяет IIS контролировать настройки безопасности WCF\-службы.