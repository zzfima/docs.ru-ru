---
title: Клиентская архитектура
ms.date: 03/30/2017
ms.assetid: 02624403-0d77-41cb-9a86-ab55e98c7966
ms.openlocfilehash: 4ced24f370e2ab54528c6adb2b3617d3d849e745
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781528"
---
# <a name="client-architecture"></a>Клиентская архитектура
Приложения используют объекты клиента Windows Communication Foundation (WCF) для вызова операций службы. В этом разделе рассматриваются объектов клиента WCF, каналы клиента WCF и их связи с базовой архитектурой каналов. Общий обзор объектов клиента WCF, см. в разделе [WCF Client Overview](../../../../docs/framework/wcf/wcf-client-overview.md). Дополнительные сведения о уровень канала, см. в разделе [расширение уровня каналов](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md).  
  
## <a name="overview"></a>Обзор  
 Время выполнения модели службы создает клиентов WCF, которые состоят из следующих:  
  
- Автоматически созданная реализация клиента контракта службы, направляющая вызовы из кода приложения в исходящие сообщения, а также направляющая ответные сообщения в параметры вывода и возвращаемые значения, которые приложение может получать.  
  
- Реализация интерфейса управления (<xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>), который объединяет различные интерфейсы и обеспечивает доступ к функциям управления, наиболее важной из которых является способность закрыть сеанс клиента и удалить канал.  
  
- Клиентский канал, созданный на основе параметров конфигурации, определенных использованной привязкой.  
  
 Приложения могут создавать таких клиентов по требованию, либо с помощью <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType> или путем создания экземпляра <xref:System.ServiceModel.ClientBase%601> производного класса, так как оно генерируется [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Эти созданные клиентские классы осуществляют инкапсуляцию и делегирование в реализацию клиентского канала, которая динамически создается фабрикой <xref:System.ServiceModel.ChannelFactory>. Следовательно, наибольший интерес для данного обсуждения представляют клиентские каналы и создающая их фабрика каналов.  
  
## <a name="client-objects-and-client-channels"></a>Клиентские объекты и клиентские каналы  
 Является базовым интерфейсом клиентов WCF <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> интерфейс, который предоставляет основные функциональные возможности клиента, а также базовые функции коммуникационных объектов <xref:System.ServiceModel.ICommunicationObject?displayProperty=nameWithType>, контекстные функции канала <xref:System.ServiceModel.IContextChannel?displayProperty=nameWithType>и расширяемое поведение объекта <xref:System.ServiceModel.IExtensibleObject%601?displayProperty=nameWithType>.  
  
 Интерфейс <xref:System.ServiceModel.IClientChannel>, однако, не определяет сам контракт службы. Они объявляются интерфейсом контракта службы (обычно создается из метаданных службы с помощью такого средства, как [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)). Типы клиентов WCF расширяют как <xref:System.ServiceModel.IClientChannel> и целевой интерфейс контракта службы, чтобы приложения могли вызывать операции непосредственно, а также иметь доступ к функциям среды выполнения на стороне клиента. Создание клиента WCF предоставляет WCF<xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType> объектов с сведения, необходимые для создания среды выполнения, которые могут подключаться и взаимодействовать с конечной точкой настроенной службы.  
  
 Как упоминалось ранее, необходимо настроить два типа клиентов WCF, чтобы вы могли использовать их. Наиболее простыми типами клиента WCF являются объектами, которые являются производными от <xref:System.ServiceModel.ClientBase%601> (или <xref:System.ServiceModel.DuplexClientBase%601> Если контракт службы является дуплексный контракт). Эти типы можно создать с помощью программно настроенного конструктора или с использованием файла конфигурации и затем вызывать непосредственно для запуска операций службы. Для получения общих сведений о <xref:System.ServiceModel.ClientBase%601> объектов, см. в разделе [WCF Client Overview](../../../../docs/framework/wcf/wcf-client-overview.md).  
  
 Второй тип создается во время выполнения в результате вызова метода <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A>. Приложения, которым требуется жесткий контроль особенностей взаимодействия обычно использовать этот тип клиента, называемый *объекте канала клиента*, так как она допускает более непосредственное взаимодействие от базовой среды выполнения клиента и канала система.  
  
## <a name="channel-factories"></a>Фабрики каналов  
 За создание базовой среды выполнения, которая поддерживает вызовы клиентов, отвечает класс <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>. Объектов клиента WCF и клиент WCF канала использование объектов <xref:System.ServiceModel.ChannelFactory%601> объект для создания экземпляров; <xref:System.ServiceModel.ClientBase%601> клиентский объект, унаследованный инкапсулирует обработку фабрики каналов, но в ряде сценариев полностью подходит для использования Фабрика каналов, напрямую. Распространенный сценарий для этого - необходимость многократного создания новых клиентских каналов из существующей фабрики. Если вы используете объект клиента, можно получить фабрику выделенного канала из объекта клиента WCF, вызвав <xref:System.ServiceModel.ClientBase%601.ChannelFactory%2A?displayProperty=nameWithType> свойство.  
  
 В отношении фабрик каналов необходимо иметь в виду, что они создают новые экземпляры клиентских каналов для предоставленной им конфигурации до вызова метода <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType>. При вызове метода <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A> (или <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType>, <xref:System.ServiceModel.ClientBase%601.CreateChannel%2A?displayProperty=nameWithType>, либо любая операция для объекта клиента WCF), нельзя изменить фабрику каналов и надеяться на получение каналов к различным экземплярам службы, даже если простого изменения целевого адреса конечной точки. Если требуется создать клиентский объект или клиентский канал с другой конфигурацией, сначала необходимо создать новую фабрику каналов.  
  
 Дополнительные сведения о различных проблем, с помощью объектов клиента WCF и клиентских каналов WCF, см. в разделе [доступ к службам, с помощью клиента WCF](../../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md).  
  
 В следующих двух разделах Создание и использование объектов клиентских каналов WCF.  
  
#### <a name="creating-a-new-wcf-client-channel-object"></a>Создание нового объекта клиентского канала WCF  
 Чтобы продемонстрировать использование клиентского канала, предположим, что создан следующий контракт службы.  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 Для подключения к службе `ISampleService` используйте созданный интерфейс контракта непосредственно с фабрикой каналов (<xref:System.ServiceModel.ChannelFactory%601>). При создании и настройке фабрики каналов для конкретного контракта можно вызвать метод <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A> для возврата объектов клиентских каналов, которые можно использовать для взаимодействия со службой `ISampleService`.  
  
 При использовании класса <xref:System.ServiceModel.ChannelFactory%601> с интерфейсом контракта службы следует перейти к интерфейсу <xref:System.ServiceModel.IClientChannel> , чтобы явно открыть, закрыть канал или прервать его работу. Для упрощения работы средство Svcutil.exe создает также вспомогательный интерфейс, реализующий и интерфейс контракта службы, и интерфейс <xref:System.ServiceModel.IClientChannel> , чтобы можно было взаимодействовать с инфраструктурой клиентских каналов без переходов. В следующем коде показано определение вспомогательного клиентского канала, который реализует указанный выше контракт службы.  
  
 [!code-csharp[C_GeneratedCodeFiles#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#13)]  
  
#### <a name="creating-a-new-wcf-client-channel-object"></a>Создание нового объекта клиентского канала WCF  
 Чтобы воспользоваться клиентским каналом для подключения к службе `ISampleService`, используйте созданный интерфейс контракта (или вспомогательный вариант) непосредственно с фабрикой каналов, передав тип интерфейса контракта в качестве параметра типа. После создания и настройки фабрики каналов для конкретного контракта можно вызвать метод <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType> для возврата объектов клиентских каналов, которые можно использовать для взаимодействия со службой `ISampleService`.  
  
 Созданные объекты клиентских каналов реализуют интерфейс <xref:System.ServiceModel.IClientChannel> и интерфейс контракта. Следовательно, их можно использовать непосредственно для вызова операций, взаимодействующих со службой, поддерживающей этот контракт.  
  
 Различие между применением клиентских объектов и объектов клиентских каналов состоит только в управлении и удобстве использования для разработчиков. Многие разработчики, которым удобно работать с классами и объектами предпочтут использовать клиентский объект WCF вместо клиентского канала WCF.  
  
 Пример см. в статье [Практическое руководство. Использование ChannelFactory](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md).
