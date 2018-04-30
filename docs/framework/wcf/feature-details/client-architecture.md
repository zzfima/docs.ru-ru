---
title: Клиентская архитектура
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 02624403-0d77-41cb-9a86-ab55e98c7966
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 12db0d4f5717287439b66810e6354b12a4c68b77
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="client-architecture"></a>Клиентская архитектура
Для вызова операций службы приложения используют клиентские объекты [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. В этом разделе рассматриваются клиентские объекты [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], клиентские каналы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и их взаимосвязи с базовой архитектурой каналов. Для получения общих сведений о [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] клиентские объекты в разделе [Общие сведения о клиенте WCF](../../../../docs/framework/wcf/wcf-client-overview.md). Дополнительные сведения о уровень канала см. в разделе [расширение уровня каналов](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md).  
  
## <a name="overview"></a>Обзор  
 Во время выполнения модели службы создаются клиенты [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], в состав которых входят следующие компоненты.  
  
-   Автоматически созданная реализация клиента контракта службы, направляющая вызовы из кода приложения в исходящие сообщения, а также направляющая ответные сообщения в параметры вывода и возвращаемые значения, которые приложение может получать.  
  
-   Реализация интерфейса управления (<xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>), который объединяет различные интерфейсы и обеспечивает доступ к функциям управления, наиболее важной из которых является способность закрыть сеанс клиента и удалить канал.  
  
-   Клиентский канал, созданный на основе параметров конфигурации, определенных использованной привязкой.  
  
 Приложения могут создавать такие клиенты по требованию, либо с помощью <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType> или путем создания экземпляра <xref:System.ServiceModel.ClientBase%601> производного класса, как оно генерируется [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Эти созданные клиентские классы осуществляют инкапсуляцию и делегирование в реализацию клиентского канала, которая динамически создается фабрикой <xref:System.ServiceModel.ChannelFactory>. Следовательно, наибольший интерес для данного обсуждения представляют клиентские каналы и создающая их фабрика каналов.  
  
## <a name="client-objects-and-client-channels"></a>Клиентские объекты и клиентские каналы  
 Базовым интерфейсом клиентов [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] является интерфейс <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>, представляющий основные клиентские функции, а также базовые функции коммуникационных объектов <xref:System.ServiceModel.ICommunicationObject?displayProperty=nameWithType>, контекстные функции канала <xref:System.ServiceModel.IContextChannel?displayProperty=nameWithType> и расширяемое поведение объекта <xref:System.ServiceModel.IExtensibleObject%601?displayProperty=nameWithType>.  
  
 Интерфейс <xref:System.ServiceModel.IClientChannel>, однако, не определяет сам контракт службы. Те, для объявления интерфейса контракта службы (обычно создается на основе метаданных службы с помощью таких средств, как [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)). Типы клиентов [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] расширяют как интерфейс <xref:System.ServiceModel.IClientChannel>, так и целевой интерфейс контракта службы, чтобы приложения могли вызывать операции непосредственно, а также иметь доступ к функциям среды выполнения на стороне клиента. При создании клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] объектам [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType> предоставляются сведения, необходимые для создания среды выполнения, которая может подключиться к настроенной конечной точке службы и взаимодействовать с ней.  
  
 Как было указано ранее, необходимо настроить два типа клиентов [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], прежде чем их можно будет использовать. Самыми простыми типами клиентов [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] являются объекты, унаследованные от <xref:System.ServiceModel.ClientBase%601> (или <xref:System.ServiceModel.DuplexClientBase%601>, если контрактом службы является дуплексный контракт). Эти типы можно создать с помощью программно настроенного конструктора или с использованием файла конфигурации и затем вызывать непосредственно для запуска операций службы. Для получения общих сведений о <xref:System.ServiceModel.ClientBase%601> объектов, в разделе [Общие сведения о клиенте WCF](../../../../docs/framework/wcf/wcf-client-overview.md).  
  
 Второй тип создается во время выполнения в результате вызова метода <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A>. Приложения, которым требуется жесткий контроль особенностей взаимодействия обычно использовать этот тип клиента, вызывается *объекте канала клиента*, так как она допускает более непосредственное взаимодействие, чем базовой среды выполнения клиента и канала система.  
  
## <a name="channel-factories"></a>Фабрики каналов  
 За создание базовой среды выполнения, которая поддерживает вызовы клиентов, отвечает класс <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>. Клиентские объекты [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и объекты клиентских каналов [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] используют объект <xref:System.ServiceModel.ChannelFactory%601> для создания экземпляров; клиентский объект, унаследованный от <xref:System.ServiceModel.ClientBase%601>, инкапсулирует обработку фабрики каналов, но в ряде сценариев полностью подходит для использования фабрики каналов непосредственно. Распространенный сценарий для этого - необходимость многократного создания новых клиентских каналов из существующей фабрики. В случае использования клиентского объекта можно получить базовую фабрику каналов из клиентского объекта [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], вызвав свойство <xref:System.ServiceModel.ClientBase%601.ChannelFactory%2A?displayProperty=nameWithType>.  
  
 В отношении фабрик каналов необходимо иметь в виду, что они создают новые экземпляры клиентских каналов для предоставленной им конфигурации до вызова метода <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType>. Если вызывается <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A> (или <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType>, <xref:System.ServiceModel.ClientBase%601.CreateChannel%2A?displayProperty=nameWithType> либо любая операция для клиентского объекта [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]), невозможно изменить фабрику каналов и надеяться на получение каналов к различным экземплярам службы даже в случае простого изменения целевого адреса конечной точки. Если требуется создать клиентский объект или клиентский канал с другой конфигурацией, сначала необходимо создать новую фабрику каналов.  
  
 Дополнительные сведения о различных проблем, с помощью [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] клиентских объектов и [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] клиентские каналы, в разделе [получение служб с помощью клиента WCF](../../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md).  
  
 В следующих двух разделах описываются создание и использование объектов клиентских каналов [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
#### <a name="creating-a-new-wcf-client-channel-object"></a>Создание нового объекта клиентского канала WCF  
 Чтобы продемонстрировать использование клиентского канала, предположим, что создан следующий контракт службы.  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 Для подключения к службе `ISampleService` используйте созданный интерфейс контракта непосредственно с фабрикой каналов (<xref:System.ServiceModel.ChannelFactory%601>). При создании и настройке фабрики каналов для конкретного контракта можно вызвать метод <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A> для возврата объектов клиентских каналов, которые можно использовать для взаимодействия со службой `ISampleService`.  
  
 При использовании класса <xref:System.ServiceModel.ChannelFactory%601> с интерфейсом контракта службы следует перейти к интерфейсу <xref:System.ServiceModel.IClientChannel>, чтобы явно открыть, закрыть канал или прервать его работу. Для упрощения работы средство Svcutil.exe создает также вспомогательный интерфейс, реализующий и интерфейс контракта службы, и интерфейс <xref:System.ServiceModel.IClientChannel> , чтобы можно было взаимодействовать с инфраструктурой клиентских каналов без переходов. В следующем коде показано определение вспомогательного клиентского канала, который реализует указанный выше контракт службы.  
  
 [!code-csharp[C_GeneratedCodeFiles#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#13)]  
  
#### <a name="creating-a-new-wcf-client-channel-object"></a>Создание нового объекта клиентского канала WCF  
 Чтобы воспользоваться клиентским каналом для подключения к службе `ISampleService`, используйте созданный интерфейс контракта (или вспомогательный вариант) непосредственно с фабрикой каналов, передав тип интерфейса контракта в качестве параметра типа. После создания и настройки фабрики каналов для конкретного контракта можно вызвать метод <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType> для возврата объектов клиентских каналов, которые можно использовать для взаимодействия со службой `ISampleService`.  
  
 Созданные объекты клиентских каналов реализуют интерфейс <xref:System.ServiceModel.IClientChannel> и интерфейс контракта. Следовательно, их можно использовать непосредственно для вызова операций, взаимодействующих со службой, поддерживающей этот контракт.  
  
 Различие между применением клиентских объектов и объектов клиентских каналов состоит только в управлении и удобстве использования для разработчиков. Многие разработчики, которым удобно работать с классами и объектами, предпочтут использовать клиентский объект [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] вместо клиентского канала [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Пример см. в разделе [как: использование ChannelFactory](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md).
