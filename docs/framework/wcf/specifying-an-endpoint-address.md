---
title: "Задание адреса конечной точки | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "адресация конечные точки [WCF]"
ms.assetid: ac24f5ad-9558-4298-b168-c473c68e819b
caps.latest.revision: 41
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 41
---
# Задание адреса конечной точки
Вся связь со службой [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] осуществляется через ее конечные точки. Каждый <xref:System.ServiceModel.Description.ServiceEndpoint> содержит <xref:System.ServiceModel.Description.ServiceEndpoint.Address%2A>, <xref:System.ServiceModel.Description.ServiceEndpoint.Binding%2A>и <xref:System.ServiceModel.Description.ServiceEndpoint.Contract%2A>. В контракте задается, какие операции доступны. Привязка определяет, как осуществлять взаимодействие со службой, а адрес показывает, где можно найти службу. Каждая конечная точка должна иметь уникальный адрес. Адрес конечной точки представляется <xref:System.ServiceModel.EndpointAddress> класс, который содержит универсальный идентификатор ресурса (URI), который представляет адрес службы, <xref:System.ServiceModel.EndpointAddress.Identity%2A>, представляет идентификатор безопасности службы и коллекцию необязательных <xref:System.ServiceModel.EndpointAddress.Headers%2A>. Необязательные заголовки содержат более подробную информацию для идентификации конечной точки и взаимодействия с ней. Например, в заголовках может содержаться информация о том, как следует обрабатывать входящее сообщение, куда конечная точка должна отправить ответное сообщение или какой экземпляр службы необходимо использовать для обработки входящего сообщения от конкретного пользователя, если доступно несколько экземпляров.  
  
## <a name="definition-of-an-endpoint-address"></a>Определение адреса конечной точки  
 В [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], <xref:System.ServiceModel.EndpointAddress> моделирует ссылку на конечную точку (EPR) согласно определению в стандарте WS-Addressing.  
  
 Универсальный код ресурса (URI) адреса для большинства видов транспорта состоит из четырех частей. Например, код "http://www.fabrikam.com:322/mathservice.svc/secureEndpoint" состоит из следующих четырех частей.  
  
-   Схема: http:  
  
-   Компьютер: www.fabrikam.com  
  
-   (Необязательно) Порт: 322  
  
-   Путь: /mathservice.svc/secureEndpoint  
  
 Одной из особенностей модели EPR является то, что каждая ссылка на конечную точку может содержать некоторые ссылочные параметры, которые добавляют дополнительные идентификационные сведения. В [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], эти ссылочные параметры моделируются как экземпляры <xref:System.ServiceModel.Channels.AddressHeader> класса.  
  
 Адрес конечной точки службы можно задать императивно с помощью кода или декларативно с помощью конфигурации. Как правило, определять конечные точки в коде непрактично, поскольку привязки и адреса для развернутой службы чаще всего отличаются от привязок и адресов, используемых в процессе разработки службы. Обычно более целесообразно задать конечные точки службы в конфигурации, а не в коде. Если не указывать привязку и адрес в коде, их можно изменять без повторной компиляции и повторного развертывания приложения. Если конечные точки не заданы в коде или в конфигурации, то среда выполнения добавляет одну конечную точку по умолчанию для каждого базового адреса в каждом контракте службы, реализованном в службе.  
  
 В [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] существует два способа задания адресов конечных точек для службы. Можно указать абсолютный адрес для каждой конечной точки, связанный со службой, или можно предоставить базовый адрес для <xref:System.ServiceModel.ServiceHost> службы, а затем укажите адрес для каждой конечной точки, связанный с этой службой, которая определяется относительно этого базового адреса. Любой из этих методов можно использовать для задания адресов конечных точек для службы как в конфигурации, так и в коде. Если не указывать относительный адрес, служба использует базовый адрес. Можно указать несколько базовых адресов для службы, однако для каждого транспорта каждая служба может иметь только один базовый адрес. Если имеется несколько конечных точек, настроенных по разным привязкам, каждая из них должна иметь уникальный адрес. Конечные точки, использующие одну привязку, но разные контракты, могут иметь один и тот же адрес.  
  
 При размещении в IIS, которые не управляются <xref:System.ServiceModel.ServiceHost> экземпляр самостоятельно. При размещении в службах IIS базовый адрес - это всегда адрес службы, указанный в файле SVC. Следовательно, для конечных точек служб, размещенных в IIS, следует использовать относительные адреса. Указание полного адреса конечной точки может привести к ошибкам при развертывании службы. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Развертывание службы WCF, размещенной в IIS](../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md).  
  
## <a name="defining-endpoint-addresses-in-configuration"></a>Определение адреса конечной точки в конфигурации  
 Для определения конечной точки в файле конфигурации, используйте [ <> \> ](http://msdn.microsoft.com/ru-ru/13aa23b7-2f08-4add-8dbf-a99f8127c017) элемента.  
  
 <!-- TODO: review snippet reference [!code[S_UEHelloWorld#5](../../../samples/snippets/common/VS_Snippets_CFX/s_uehelloworld/common/serviceapp2.config#5)]  -->  
  
 Когда <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> вызывается (то есть, когда ведущее приложение пытается запустить службу), система выполняет поиск [ <> \> ](../../../docs/framework/configure-apps/file-schema/wcf/service.md) элемент с атрибутом name, указывающее «UE. Samples.HelloService». Если [ <> \> ](../../../docs/framework/configure-apps/file-schema/wcf/service.md) элемент найден, система загружает указанный класс и создает конечные точки, с помощью конечных точек, содержащиеся в файле конфигурации. Благодаря такому механизму можно загружать и запускать службу с двумя строками кода, при этом не указывая привязку и адрес в коде. Преимуществом этого подхода является отсутствие необходимости в повторной компиляции или повторном развертывании приложения при внесении этих изменений.  
  
 Необязательные заголовки объявлены в [ <> \</> \> ](../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md). Ниже приведен пример элементов, используемых для задания конечных точек службы в файле конфигурации, различающем два заголовка: клиентов типа "Gold" из «http://tempuri1.org/» и клиентов типа "Standard" из «http://tempuri2.org/». Клиент, вызывающий эту службу необходимо наличие [ <> \> ](../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md) в своем файле конфигурации.  
  
 <!-- TODO: review snippet reference [!code[S_UEHelloWorld#1](../../../samples/snippets/common/VS_Snippets_CFX/s_uehelloworld/common/serviceapp.config#1)]  -->  
  
 Можно настроить заголовки для отдельных сообщений конечной точки, а не всех одновременно (как показано выше). Это делается с помощью <xref:System.ServiceModel.OperationContextScope> для создания нового контекста в клиентском приложении для добавления пользовательского заголовка в исходящее сообщение, как показано в следующем примере.  
  
 [!code-csharp[OperationContextScope#4](../../../samples/snippets/csharp/VS_Snippets_CFX/operationcontextscope/cs/client.cs#4)]
 [!code-vb[OperationContextScope#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/operationcontextscope/vb/client.vb#4)]  
  
## <a name="endpoint-address-in-metadata"></a>Адрес конечной точки в метаданных  
 Адрес конечной точки представляется на языке описания веб-служб (WSDL) в виде элемента ссылки на конечную точку EPR WS-Addressing `EndpointReference` в элементе `wsdl:port` соответствующей конечной точки. Ссылка на конечную точку (EPR) содержит адрес конечной точки и любые свойства адреса. Обратите внимание, что EPR в элементе `wsdl:port` заменяет `soap:Address`, как показано в следующем примере.  
  
  
  
## <a name="defining-endpoint-addresses-in-code"></a>Определение адреса конечной точки в коде  
 Адрес конечной точки можно создать в коде с <xref:System.ServiceModel.EndpointAddress> класса. URI, заданный для адреса конечной точки, может представлять собой полный путь или путь относительно базового адреса службы. Следующий код показывает, как создать экземпляр <xref:System.ServiceModel.EndpointAddress> класса и добавить его в <xref:System.ServiceModel.ServiceHost> экземпляр, на котором размещается служба.  
  
 В следующем примере показано, как задавать полный адрес конечной точки в коде.  
  
 [!code-csharp[S_UEHelloWorld#2](../../../samples/snippets/csharp/VS_Snippets_CFX/s_uehelloworld/cs/snippet.cs#2)]  
  
 В следующем примере показано, как добавлять относительный адрес ("MyService") в базовый адрес узла службы.  
  
 [!code-csharp[S_UEHelloWorld#3](../../../samples/snippets/csharp/VS_Snippets_CFX/s_uehelloworld/cs/snippet.cs#3)]  
  
> [!NOTE]
>  Свойства <xref:System.ServiceModel.Description.ServiceDescription> в службе приложений не должно изменяться вызова <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> метод <xref:System.ServiceModel.ServiceHostBase>. Некоторые элементы, такие как <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> свойство и `AddServiceEndpoint` методы <xref:System.ServiceModel.ServiceHostBase> и <xref:System.ServiceModel.ServiceHost>, исключение, если изменена после этой точки. Другие члены можно изменять без появления исключения, но результат при этом будет неопределенным.  
>   
>  Аналогично, на стороне клиента <xref:System.ServiceModel.Description.ServiceEndpoint> значения нельзя изменять после вызова <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> на <xref:System.ServiceModel.ChannelFactory>. <xref:System.ServiceModel.ChannelFactory.Credentials%2A> свойство вызывает исключение, если изменены после этой точки. Изменение других значений описания клиента происходит без ошибок, но результат изменения в этом случае является неопределенным.  
>   
>  Будет ли служба или клиент рекомендуется изменять описание до вызова метода <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.  
  
## <a name="using-default-endpoints"></a>Использование конечных точек по умолчанию  
 Если конечные точки не заданы в коде или в конфигурации, то среда выполнения предоставляет конечные точки по умолчанию, добавляя одну конечную точку по умолчанию для каждого базового адреса в каждом контракте службы, реализованном в службе. Базовый адрес можно указать в коде или в конфигурации и добавляются конечные точки по умолчанию, когда <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> вызывается на <xref:System.ServiceModel.ServiceHost>.  
  
 Если конечные точки предоставляются явно, по умолчанию конечные точки можно добавить путем вызова <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints%2A> на <xref:System.ServiceModel.ServiceHost> перед вызовом метода <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>. [!INCLUDE[crabout](../../../includes/crabout-md.md)]конечные точки по умолчанию, привязки и поведения, см. в разделе [упрощенной конфигурации](../../../docs/framework/wcf/simplified-configuration.md) и [упрощенной конфигурации для служб WCF](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.EndpointAddress>   
 [Службы идентификации и проверки подлинности](../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [Общие сведения о создании конечной точки](../../../docs/framework/wcf/endpoint-creation-overview.md)   
 [Размещение](../../../docs/framework/wcf/feature-details/hosting.md)