---
title: Указание поведения службы во время выполнения
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 5c5450ea-6af1-4b75-a267-613d0ac54707
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9733bb29701e4d1b46cc08c14b91e0357c935b42
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="specifying-service-run-time-behavior"></a>Указание поведения службы во время выполнения
После создания ([Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md)) и реализации ([Implementing Service Contracts](../../../docs/framework/wcf/implementing-service-contracts.md)) контракта службы можно переходить к настройке рабочего поведения для среды выполнения службы. В этом разделе рассматриваются предоставляемые системой поведения служб и операций, а также указывается, где можно найти дополнительные сведения по созданию новых поведений. Хотя некоторые поведения применяются как атрибуты, многие поведения применяются с помощью файла конфигурации приложения или программно. Дополнительные сведения о настройке приложения-службы см. в разделе [Настройка службы](../../../docs/framework/wcf/configuring-services.md).  
  
## <a name="overview"></a>Обзор  
 Контракт определяет входные данные, выходные данные, типы данных и возможности службы этого типа. При реализации контракта службы создается класс, которой, при настройке с привязкой к адресу, выполняет реализуемый им контракт. Сведения о контракте, привязке и адресе известны клиенту; без этих сведений клиент не может пользоваться службой.  
  
 Однако конкретные сведения об операциях, такие как сведения о потоках или управлении экземплярами, не видны клиентам. После реализации контракта службы можно настроить большое количество характеристик операций с помощью *поведений*. Поведения — это объекты, изменения среды выполнения Windows Communication Foundation (WCF), задав свойства среды выполнения или путем добавления пользовательского типа во время выполнения. Дополнительные сведения об изменении среды выполнения при создании определенных пользователем поведений см. в разделе [расширение ServiceHost и уровень модели службы](../../../docs/framework/wcf/extending/extending-servicehost-and-the-service-model-layer.md).  
  
 Атрибуты <xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType> и <xref:System.ServiceModel.OperationBehaviorAttribute?displayProperty=nameWithType> являются наиболее широко используемыми поведениями, раскрывающими наиболее часто запрашиваемые функции операции. Так как они являются атрибутами, они применяются к реализации службы или операции. Другие поведения, такие как <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> и <xref:System.ServiceModel.Description.ServiceDebugBehavior?displayProperty=nameWithType>, обычно применяются с помощью файла конфигурации приложения, хотя их можно использовать и программно.  
  
 В этом разделе приводятся общие сведения об атрибутах <xref:System.ServiceModel.ServiceBehaviorAttribute> и <xref:System.ServiceModel.OperationBehaviorAttribute> , описываются различные области, в которых могут работать поведения, и приводится краткое описание многих предоставляемых системой поведений в различных областях, которые могут представлять интерес для разработчиков [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] .  
  
## <a name="servicebehaviorattribute-and-operationbehaviorattribute"></a>Атрибуты ServiceBehaviorAttribute и OperationBehaviorAttribute  
 Наиболее важными поведениями являются атрибуты <xref:System.ServiceModel.ServiceBehaviorAttribute> и <xref:System.ServiceModel.OperationBehaviorAttribute> , которые можно использовать для управления указанными ниже характеристиками.  
  
-   Время существования экземпляра  
  
-   Поддержка параллелизма и синхронизации  
  
-   Поведение конфигурации  
  
-   Поведение транзакции  
  
-   Поведение сериализации  
  
-   Преобразование метаданных  
  
-   Время существования сеанса  
  
-   Фильтрация адресов и обработка заголовков  
  
-   Олицетворение  
  
-   Для использования этих атрибутов пометьте реализацию службы или операции атрибутом, подходящим для определенной области и набора свойств. Например, в следующем примере кода показана реализация операции, в которой с помощью свойства <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A?displayProperty=nameWithType> задается требование, чтобы вызывающая сторона этой операции поддерживала олицетворение.  
  
 [!code-csharp[OperationBehaviorAttribute_Impersonation#1](../../../samples/snippets/csharp/VS_Snippets_CFX/operationbehaviorattribute_impersonation/cs/services.cs#1)]
 [!code-vb[OperationBehaviorAttribute_Impersonation#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/operationbehaviorattribute_impersonation/vb/services.vb#1)]  
  
 Многие свойства требуют дополнительной поддержки со стороны привязки. Например, операция, которой требуется транзакция от клиента, должна быть настроена для использования привязки, поддерживающей поток транзакций.  
  
### <a name="well-known-singleton-services"></a>Широко известные одноэлементные службы  
 Атрибуты <xref:System.ServiceModel.ServiceBehaviorAttribute> и <xref:System.ServiceModel.OperationBehaviorAttribute> можно использовать для управления определенными временами существования, как <xref:System.ServiceModel.InstanceContext> , так и объектов службы, реализующих операции.  
  
 Например, свойство <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> управляет частотой высвобождения <xref:System.ServiceModel.InstanceContext>, а свойства <xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A?displayProperty=nameWithType> и <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A?displayProperty=nameWithType> управляют моментом высвобождения объекта службы.  
  
 Однако можно также самому создать объект службы, а затем создать основное приложение службы, используя этот объект. Для этого необходимо задать для свойства <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> значение <xref:System.ServiceModel.InstanceContextMode.Single> - в противном случае при открытии основного приложения службы возникает исключение.  
  
 Для создания такой службы используйте конструктор <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Object%2CSystem.Uri%5B%5D%29?displayProperty=nameWithType>. Он обеспечивает альтернативу реализации пользовательского <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer?displayProperty=nameWithType>, если требуется предоставить определенный экземпляр объекта для использования одноэлементной службой. Этот перегружаемый метод можно использовать, когда тип реализации службы не позволяет легко использовать конструктор (например, если он не реализует открытый конструктор по умолчанию, не имеющий параметров).  
  
 Обратите внимание, что при этом конструктору передается объект, некоторые функции, относящиеся к Windows Communication Foundation (WCF) поведения создания экземпляров работают по-разному. Например, вызов <xref:System.ServiceModel.InstanceContext.ReleaseServiceInstance%2A?displayProperty=nameWithType> не выполняет никаких действий, если предоставлен экземпляр хорошо известного объекта. Аналогичным образом игнорируются все другие механизмы освобождения экземпляров. Класс <xref:System.ServiceModel.ServiceHost> всегда ведет себя таким образом, как если бы для свойства <xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A?displayProperty=nameWithType> было задано значение <xref:System.ServiceModel.ReleaseInstanceMode.None?displayProperty=nameWithType> для всех операций.  
  
## <a name="other-service-endpoint-contract-and-operation-behaviors"></a>Другие поведения службы, конечной точки, контракта и операции  
 Поведения службы, такие как атрибут <xref:System.ServiceModel.ServiceBehaviorAttribute> , действуют во всей службе. Например, если для свойства <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A?displayProperty=nameWithType> задано значение <xref:System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType>, необходимо самостоятельно обрабатывать вопросы синхронизации потоков внутри каждой операции службы. Поведения конечной точки действуют на уровне конечной точки; многие из предоставляемых системой поведений конечных точек предназначены для функциональных возможностей клиентов. Поведения контракта действуют на уровне контракта, а поведения операции изменяют доставку операции.  
  
 Многие из этих поведений реализованы атрибутами, и их можно использовать так же, как и атрибуты <xref:System.ServiceModel.ServiceBehaviorAttribute> и <xref:System.ServiceModel.OperationBehaviorAttribute> - применяя их к определенной реализации класса службы или операции. Другие поведения, такие как объекты <xref:System.ServiceModel.Description.ServiceMetadataBehavior> и <xref:System.ServiceModel.Description.ServiceDebugBehavior> , обычно применяются с помощью файла конфигурации приложения, хотя их можно также использовать программно.  
  
 Например, публикация метаданных настраивается с помощью объекта <xref:System.ServiceModel.Description.ServiceMetadataBehavior> . В следующем файле конфигурации приложения показано наиболее часто встречающееся применение.  
  
 [!code-csharp[ServiceMetadataBehavior#1](../../../samples/snippets/csharp/VS_Snippets_CFX/servicemetadatabehavior/cs/hostapplication.cs#1)]  
  
 В следующих разделах рассматриваются многие из наиболее полезных предоставляемых системой поведений, которые можно использовать для изменения доставки среды выполнения службы или клиента. Порядок использования каждого из них см. в разделе, указанном в ссылке.  
  
### <a name="service-behaviors"></a>Поведения служб  
 Следующие поведения работают на уровне служб.  
  
-   <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>. Применяется к службе [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] , чтобы указать, можно ли запустить эту службу в режиме совместимости [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] .  
  
-   <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>. Управляет тем, как служба авторизует запросы клиентов.  
  
-   <xref:System.ServiceModel.Description.ServiceCredentials>. Настраивает учетные данные службы. Этот класс используется для указания учетных данных для службы, таких как сертификат X.509.  
  
-   <xref:System.ServiceModel.Description.ServiceDebugBehavior>. Включает функции отладки и справки для службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] .  
  
-   <xref:System.ServiceModel.Description.ServiceMetadataBehavior>. Контролирует публикацию метаданных службы и связанной с ними информации.  
  
-   <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>. Задает расширения функциональности аудита для событий безопасности.  
  
-   <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>. Настраивает параметры производительности времени выполнения, которые позволяют настроить производительность службы.  
  
### <a name="endpoint-behaviors"></a>Поведения конечных точек  
 Следующие поведения работают на уровне конечных точек. Многие из этих поведений используются в клиентских приложениях.  
  
-   <xref:System.ServiceModel.CallbackBehaviorAttribute>. Настраивает реализацию службы обратного вызова в дуплексном клиентском приложении.  
  
-   <xref:System.ServiceModel.Description.CallbackDebugBehavior>. Включает отладку службы для объекта обратного вызова [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] .  
  
-   <xref:System.ServiceModel.Description.ClientCredentials>. Позволяет пользователю настроить учетные данные клиента и службы, а также параметры проверки подлинности учетных данных службы для использования в клиенте.  
  
-   <xref:System.ServiceModel.Description.ClientViaBehavior>. Используется клиентами, чтобы указать универсальный код ресурса (URI), для которого необходимо создать канал транспорта.  
  
-   <xref:System.ServiceModel.Description.MustUnderstandBehavior>. Указывает [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] отключить обработку `MustUnderstand` .  
  
-   <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>. Указывает, что в среде выполнения для каналов должен использоваться синхронный процесс получения.  
  
-   <xref:System.ServiceModel.Description.TransactedBatchingBehavior>. Оптимизирует операции получения для транспорта, поддерживающего транзакционные получения.  
  
### <a name="contract-behaviors"></a>Поведения контрактов  
 <xref:System.ServiceModel.DeliveryRequirementsAttribute>. Задает требования к функциям, которые должны поддерживаться привязками для реализации службы или клиента.  
  
### <a name="operation-behaviors"></a>Поведения операций  
 Указанные ниже поведения операций задают элементы управления сериализацией и транзакциями для операций.  
  
-   <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>. Представляет поведение времени выполнения <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.  
  
-   <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior>. Контролирует поведение времени выполнения для `XmlSerializer` и связывает его с операцией.  
  
-   <xref:System.ServiceModel.TransactionFlowAttribute>. Задает уровень, на котором операция службы принимает заголовок транзакции.  
  
## <a name="see-also"></a>См. также  
 [Настройка служб](../../../docs/framework/wcf/configuring-services.md)  
 [Практическое руководство. Управление созданием экземпляров служб](../../../docs/framework/wcf/feature-details/how-to-control-service-instancing.md)
