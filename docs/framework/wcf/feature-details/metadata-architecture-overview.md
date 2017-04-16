---
title: "Общие сведения об архитектуре метаданных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "метаданные [модель WCF], общие сведения"
ms.assetid: 1d37645e-086d-4d68-a358-f3c5b6e8205e
caps.latest.revision: 24
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 24
---
# Общие сведения об архитектуре метаданных
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] предоставляет богатую инфраструктуру для экспорта, публикации, извлечения и импорта служб метаданных.Службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] используют метаданные для описания взаимодействия со службами конечных точек, чтобы такие средства, как Svcutil.exe, могли автоматически создавать клиентский код для обращения к службе.  
  
 Большая часть типов, составляющих инфраструктуру метаданных [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], принадлежит к пространству имен <xref:System.ServiceModel.Description>.  
  
 Платформа [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует класс <xref:System.ServiceModel.Description.ServiceEndpoint> для описания конечных точек службы.С помощью [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] можно создавать метаданные для конечных точек служб или импортировать метаданные служб, чтобы создавать экземпляры <xref:System.ServiceModel.Description.ServiceEndpoint>.  
  
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] метаданные службы представляются в форме экземпляра типа <xref:System.ServiceModel.Description.MetadataSet>, структура которого строго соответствует формату сериализации метаданных, определенному в спецификации WS\-MetadataExchange.Тип <xref:System.ServiceModel.Description.MetadataSet> объединяет фактические метаданные службы, например документы на языке WSDL, документы схемы XML или выражения WS\-Policy, в коллекцию экземпляров <xref:System.ServiceModel.Description.MetadataSection>.Каждый экземпляр <xref:System.ServiceModel.Description.MetadataSection?displayProperty=fullName> содержит собственный идентификатор и диалект метаданных.Свойство <xref:System.ServiceModel.Description.MetadataSection.Metadata%2A?displayProperty=fullName> объекта <xref:System.ServiceModel.Description.MetadataSection?displayProperty=fullName> может содержать следующие элементы.  
  
-   Необработанные метаданные.  
  
-   Экземпляр <xref:System.ServiceModel.Description.MetadataReference>.  
  
-   Экземпляр <xref:System.ServiceModel.Description.MetadataLocation>.  
  
 Экземпляры <xref:System.ServiceModel.Description.MetadataReference?displayProperty=fullName> указывают на другую конечную точку обмена метаданными \(MEX\), а экземпляры <xref:System.ServiceModel.Description.MetadataLocation?displayProperty=fullName> указывают на документ метаданных, используя URL\-адрес HTTP.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает использование WSDL для описания конечных точек службы, контрактов службы, привязок, шаблонов обмена сообщениями, сообщений и сообщений об ошибках, реализуемых службой.Используемые службой типы данных описываются в документах WSDL с помощью схемы XML.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Импорт и экспорт схемы](../../../../docs/framework/wcf/feature-details/schema-import-and-export.md).С помощью [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] можно экспортировать и импортировать расширения WSDL для поведения службы, поведений контракта и элементов привязки, расширяющих функциональные возможности службы.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Экспорт пользовательских метаданных для расширения WCF](../../../../docs/framework/wcf/extending/exporting-custom-metadata-for-a-wcf-extension.md).  
  
## Экспорт метаданных службы  
 В среде [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]*экспорт метаданных* представляет собой процесс описания конечных точек службы и проецирования их в параллельное, стандартизованное представление, позволяющее клиентам понять, как использовать службу.Для экспорта метаданных из экземпляров <xref:System.ServiceModel.Description.ServiceEndpoint> используется реализация абстрактного класса <xref:System.ServiceModel.Description.MetadataExporter>.Реализация <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=fullName> создает метаданные, которые инкапсулируются в экземпляр <xref:System.ServiceModel.Description.MetadataSet>.  
  
 Класс <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=fullName> предоставляет платформу для создания выражений политики, которые описывают возможности и требования привязки конечной точки, а также связанные с ней операции, сообщения и ошибки.Эти выражения политики попадают в экземпляр <xref:System.ServiceModel.Description.PolicyConversionContext>.Реализация <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=fullName> может затем прикрепить эти выражения политики к создаваемым ею метаданным.  
  
 <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=fullName> делает вызовы в каждый элемент <xref:System.ServiceModel.Channels.BindingElement?displayProperty=fullName>, который реализует интерфейс <xref:System.ServiceModel.Description.IPolicyExportExtension> в привязке для <xref:System.ServiceModel.Description.ServiceEndpoint>, при создании объекта <xref:System.ServiceModel.Description.PolicyConversionContext> для используемой реализации <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=fullName>.Можно экспортировать утверждения новой политики, реализовав интерфейс <xref:System.ServiceModel.Description.IPolicyExportExtension> в пользовательских реализациях типа <xref:System.ServiceModel.Channels.BindingElement>.  
  
 Тип <xref:System.ServiceModel.Description.WsdlExporter> является реализацией абстрактного класса <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=fullName>, входящего в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].Тип <xref:System.ServiceModel.Description.WsdlExporter> создает метаданные WSDL с прикрепленными выражениями политики.  
  
 Чтобы экспортировать пользовательские метаданные языка WSDL или расширения языка WSDL для поведений конечной точки, поведений контракта или элементов привязки конечной точки службы, можно реализовать интерфейс <xref:System.ServiceModel.Description.IWsdlExportExtension>.При создании документа WSDL объект <xref:System.ServiceModel.Description.WsdlExporter> ищет в экземпляре <xref:System.ServiceModel.Description.ServiceEndpoint> элементы привязки, поведения операций, поведения контрактов и поведения конечных точек, которые реализуют интерфейс <xref:System.ServiceModel.Description.IWsdlExportExtension>.  
  
## Публикация метаданных службы  
 Службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] публикуют метаданные путем публикации одной или нескольких конечных точек метаданных.Публикация метаданных службы делает метаданные службы доступными через стандартизованные протоколы, например MEX и запросы HTTP\/GET.Конечные точки метаданных похожи на другие конечные точки служб в том смысле, что у них есть адрес, привязка и контракт.Конечные точки метаданных можно добавлять к узлу службы с помощью файла конфигурации или кода.  
  
 Для публикации конечных точек метаданных для службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] сначала необходимо добавить в службу экземпляр поведения службы <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.Добавление в службу экземпляра <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=fullName> расширяет службу, позволяя ей публиковать метаданные через одну или несколько конечных точек метаданных.После добавления поведения службы <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=fullName> можно публиковать конечные точки метаданных, поддерживающие протокол MEX, или конечные точки метаданных, отвечающие на запросы HTTP\/GET.  
  
 Чтобы добавить конечные точки метаданных, использующие протокол MEX, следует добавить в узел службы конечные точки службы, которые используют контракт службы с именем IMetadataExchange. В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] определен интерфейс <xref:System.ServiceModel.Description.IMetadataExchange>, имеющий это имя контракта службы.Конечные точки WS\-Metadata Exchange \(или конечные точки MEX\) могут использовать одну из четырех привязок по умолчанию, предоставляемых статическими методами производства в классе <xref:System.ServiceModel.Description.MetadataExchangeBindings> для сопоставления с привязками по умолчанию, используемыми средствами [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], например Svcutil.exe.Настраивать конечные точки метаданных MEX также можно с помощью пользовательской привязки.  
  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> использует <xref:System.ServiceModel.Description.WsdlExporter?displayProperty=fullName> для экспорта метаданных для всех конечных точек службы.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] об экспорте метаданных из службы см. в разделе [Экспорт и импорт метаданных](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md).  
  
 Класс <xref:System.ServiceModel.Description.ServiceMetadataBehavior> расширяет узел службы, добавляя экземпляр <xref:System.ServiceModel.Description.ServiceMetadataExtension> в качестве расширения узла службы.Расширение <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=fullName> обеспечивает реализацию протоколов публикации метаданных.Расширение <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=fullName> также можно использовать для получения метаданных службы во время выполнения, обратившись к свойству <xref:System.ServiceModel.Description.ServiceMetadataExtension.Metadata%2A>.  
  
> [!CAUTION]
>  Если добавить конечную точку MEX в файл конфигурации приложения, а затем добавить <xref:System.ServiceModel.Description.ServiceMetadataBehavior> в узел службы в коде, будет вызвано следующее исключение.  
>   
>  System.InvalidOperationException: не удалось найти имя контракта IMetadataExchange в списке контрактов, реализованных в службе Service1.Добавьте ServiceMetadataBehavior в файл конфигурации или непосредственно в ServiceHost, чтобы обеспечить поддержку этого контракта.  
>   
>  В качестве решения этой проблемы можно добавить <xref:System.ServiceModel.Description.ServiceMetadataBehavior> в файл конфигурации или добавить в код конечную точку и <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.  
>   
>  Пример добавления <xref:System.ServiceModel.Description.ServiceMetadataBehavior> в файл конфигурации приложения см. в разделе [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md).Пример добавления <xref:System.ServiceModel.Description.ServiceMetadataBehavior> в код см. в образце [Резидентное размещение](../../../../docs/framework/wcf/samples/self-host.md).  
  
> [!CAUTION]
>  Если опубликовать метаданные для службы, которая представляет доступ к двум различным контрактам службы, которые содержат операции с одинаковыми именами, вызывается исключение.Например, если служба предоставляет доступ к контракту службы с именем ICarService, который содержит операцию Get\(Car c\), и эта же служба предоставляет доступ к контракту службы с именем IBookService, который содержит операцию Get\(Book b\), то при создании метаданных службы вызывается исключение или выводится сообщение об ошибке.Чтобы устранить эту проблему, выполните одно из следующих действий.  
>   
>  -   Переименуйте одну из операций.  
> -   Задайте другое имя в свойстве <xref:System.ServiceModel.OperationContractAttribute.Name%2A>.  
> -   Установите другое пространство имен для одной из операций с помощью свойства <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.  
  
## Извлечение метаданных службы  
 Среда [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] позволяет извлекать метаданные служб с помощью стандартизованных протоколов, например WS\-MetadataExchange и HTTP.Оба эти протокола поддерживаются типом <xref:System.ServiceModel.Description.MetadataExchangeClient>.Чтобы извлечь метаданные службы с помощью типа <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName>, необходимо указать адрес и необязательную привязку.В роли привязки, используемой экземпляром <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName>, может выступать одна из привязок по умолчанию статического класса <xref:System.ServiceModel.Description.MetadataExchangeBindings>, предоставляемая пользователем привязка или привязка, загруженная из конфигурации конечной точки для контракта `IMetadataExchange`.Кроме того, тип <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName> может выполнять разрешение URL\-адресов ссылок HTTP на метаданные с помощью типа <xref:System.Net.HttpWebRequest>.  
  
 По умолчанию экземпляр <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName> связан с одним экземпляром <xref:System.ServiceModel.Channels.ChannelFactoryBase>.Можно изменить или заменить экземпляр <xref:System.ServiceModel.Channels.ChannelFactoryBase>, используемый экземпляром <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName>, переопределив виртуальный метод <xref:System.ServiceModel.Description.MetadataExchangeClient.GetChannelFactory%2A>.Аналогично можно изменить или заменить экземпляр <xref:System.Net.HttpWebRequest?displayProperty=fullName>, используемый экземпляром <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName> для создания запросов HTTP\/GET, переопределив виртуальный метод <xref:System.ServiceModel.Description.MetadataExchangeClient.GetWebRequest%2A?displayProperty=fullName>.  
  
 Вы можете извлекать метаданные службы с помощью протокола WS\-MetadataExchange и запросов HTTP\/GET, используя для этого средство Svcutil.exe и передав ему параметр **\/target:metadata** и адрес.Средство Svcutil.exe загружает метаданные, расположенные по указанному адресу, и сохраняет файлы на диске.Средство Svcutil.exe использует внутри себя экземпляр <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName> и загружает из файла конфигурации приложения конфигурацию конечной точки MEX, имя которой соответствует схеме адреса, переданного средству Svcutil.exe, если такая конечная точка существует.В противном случае средство Svcutil.exe по умолчанию использует одну из привязок, определенных в статическом типе производства <xref:System.ServiceModel.Description.MetadataExchangeBindings>.  
  
## Импорт метаданных службы  
 В процессе импорта метаданных в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создается абстрактное представление службы или ее компонентов на основе этих метаданных.Например, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может импортировать экземпляры <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Channels.Binding> или <xref:System.ServiceModel.Description.ContractDescription> из документа WSDL службы.Чтобы импортировать метаданные службы в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], следует использовать реализацию абстрактного класса <xref:System.ServiceModel.Description.MetadataImporter>.Типы, производные от класса <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=fullName>, реализуют поддержку для импорта форматов метаданных, которые используют преимущества логики импорта WS\-Policy в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Реализация <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=fullName> собирает выражения политики, прикрепленные к метаданным службы в объекте <xref:System.ServiceModel.Description.PolicyConversionContext>.Затем <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=fullName> обрабатывает политики как часть импорта метаданных путем вызова реализаций интерфейса <xref:System.ServiceModel.Description.IPolicyImportExtension> в свойстве <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A>.  
  
 Можно добавить поддержку для импорта новых утверждений политики в <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=fullName> путем добавления собственной реализации интерфейса <xref:System.ServiceModel.Description.IPolicyImportExtension> в коллекцию <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A> в экземпляре <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=fullName>.В качестве альтернативы можно зарегистрировать расширение импорта политики в файле конфигурации клиентского приложения.  
  
 Тип <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=fullName> является реализацией абстрактного класса <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=fullName>, входящего в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].Тип <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=fullName> импортирует метаданные языка WSDL с прикрепленными политиками, объединенными в объекте <xref:System.ServiceModel.Description.MetadataSet>.  
  
 Можно добавить поддержку для импорта расширений языка WSDL путем реализации интерфейса <xref:System.ServiceModel.Description.IWsdlImportExtension> и добавления реализации в свойство <xref:System.ServiceModel.Description.WsdlImporter.WsdlImportExtensions%2A> в экземпляре <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=fullName>.Кроме того, <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=fullName> может загружать реализации интерфейса <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=fullName>, зарегистрированного в файле конфигурации клиентского приложения.  
  
## Динамические привязки  
 Можно динамически обновлять привязку, используемую для создания канала к конечной точке службы, если привязка к конечной точке изменяется, или если необходимо создать канал к конечной точке, которая использует тот же контракт, но имеет другую привязку.С помощью статического класса <xref:System.ServiceModel.Description.MetadataResolver> можно во время выполнения извлекать и импортировать метаданные для конечных точек службы, реализующих заданный контракт.После этого импортированные объекты <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=fullName> можно использовать для создания клиента или производства каналов для выбранной конечной точки.  
  
## См. также  
 <xref:System.ServiceModel.Description>   
 [Форматы метаданных](../../../../docs/framework/wcf/feature-details/metadata-formats.md)   
 [Экспорт и импорт метаданных](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)   
 [Публикация метаданных](../../../../docs/framework/wcf/feature-details/publishing-metadata.md)   
 [Извлечение метаданных](../../../../docs/framework/wcf/feature-details/retrieving-metadata.md)   
 [Использование метаданных](../../../../docs/framework/wcf/feature-details/using-metadata.md)   
 [Вопросы безопасности при использовании метаданных](../../../../docs/framework/wcf/feature-details/security-considerations-with-metadata.md)   
 [Расширение системы метаданных](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)