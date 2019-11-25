---
title: Указание поведения службы во время выполнения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5c5450ea-6af1-4b75-a267-613d0ac54707
ms.openlocfilehash: ffa2f906ac2ff4630de83938ce365c1b9d5d4d64
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976637"
---
# <a name="specifying-service-run-time-behavior"></a>Указание поведения службы во время выполнения
После создания ([Designing Service Contracts](designing-service-contracts.md)) и реализации ([Implementing Service Contracts](implementing-service-contracts.md)) контракта службы можно переходить к настройке рабочего поведения для среды выполнения службы. В этом разделе рассматриваются предоставляемые системой поведения служб и операций, а также указывается, где можно найти дополнительные сведения по созданию новых поведений. Хотя некоторые поведения применяются как атрибуты, многие поведения применяются с помощью файла конфигурации приложения или программно. Дополнительные сведения о настройке приложения службы см. в разделе [Настройка служб](configuring-services.md).  
  
## <a name="overview"></a>Обзор  
 Контракт определяет входные данные, выходные данные, типы данных и возможности службы этого типа. При реализации контракта службы создается класс, которой, при настройке с привязкой к адресу, выполняет реализуемый им контракт. Сведения о контракте, привязке и адресе известны клиенту; без этих сведений клиент не может пользоваться службой.  
  
 Однако конкретные сведения об операциях, такие как сведения о потоках или управлении экземплярами, не видны клиентам. После реализации контракта службы можно настроить большое количество характеристик операций с помощью *поведений*. Поведение — это объекты, изменяющие среду выполнения Windows Communication Foundation (WCF) путем установки свойства среды выполнения или путем вставки в среду выполнения типа настройки. Дополнительные сведения об изменении среды выполнения путем создания определяемых пользователем поведений см. [в разделе Расширение ServiceHost и уровня модели службы](./extending/extending-servicehost-and-the-service-model-layer.md).  
  
 Атрибуты <xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType> и <xref:System.ServiceModel.OperationBehaviorAttribute?displayProperty=nameWithType> являются наиболее широко используемыми поведениями, раскрывающими наиболее часто запрашиваемые функции операции. Так как они являются атрибутами, они применяются к реализации службы или операции. Другие поведения, такие как <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> и <xref:System.ServiceModel.Description.ServiceDebugBehavior?displayProperty=nameWithType>, обычно применяются с помощью файла конфигурации приложения, хотя их можно использовать и программно.  
  
 В этом разделе приводятся общие сведения об атрибутах <xref:System.ServiceModel.ServiceBehaviorAttribute> и <xref:System.ServiceModel.OperationBehaviorAttribute>, описываются различные области, в которых могут работать поведения, и приводится краткое описание многих предоставляемых системой поведений в различных областях, которые могут представлять интерес для WCF. разработки.  
  
## <a name="servicebehaviorattribute-and-operationbehaviorattribute"></a>Атрибуты ServiceBehaviorAttribute и OperationBehaviorAttribute  
 Наиболее важными поведениями являются атрибуты <xref:System.ServiceModel.ServiceBehaviorAttribute> и <xref:System.ServiceModel.OperationBehaviorAttribute> , которые можно использовать для управления указанными ниже характеристиками.  
  
- Время существования экземпляра  
  
- Поддержка параллелизма и синхронизации  
  
- Поведение конфигурации  
  
- Поведение транзакции  
  
- Поведение сериализации  
  
- Преобразование метаданных  
  
- Время существования сеанса  
  
- Фильтрация адресов и обработка заголовков  
  
- Олицетворение  
  
- Для использования этих атрибутов пометьте реализацию службы или операции атрибутом, подходящим для определенной области и набора свойств. Например, в следующем примере кода показана реализация операции, в которой с помощью свойства <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A?displayProperty=nameWithType> задается требование, чтобы вызывающая сторона этой операции поддерживала олицетворение.  
  
 [!code-csharp[OperationBehaviorAttribute_Impersonation#1](../../../samples/snippets/csharp/VS_Snippets_CFX/operationbehaviorattribute_impersonation/cs/services.cs#1)]
 [!code-vb[OperationBehaviorAttribute_Impersonation#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/operationbehaviorattribute_impersonation/vb/services.vb#1)]  
  
 Многие свойства требуют дополнительной поддержки со стороны привязки. Например, операция, которой требуется транзакция от клиента, должна быть настроена для использования привязки, поддерживающей поток транзакций.  
  
### <a name="well-known-singleton-services"></a>Широко известные одноэлементные службы  
 Атрибуты <xref:System.ServiceModel.ServiceBehaviorAttribute> и <xref:System.ServiceModel.OperationBehaviorAttribute> можно использовать для управления определенными временами существования, как <xref:System.ServiceModel.InstanceContext> , так и объектов службы, реализующих операции.  
  
 Например, свойство <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> управляет частотой высвобождения <xref:System.ServiceModel.InstanceContext> , а свойства <xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A?displayProperty=nameWithType> и <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A?displayProperty=nameWithType> управляют моментом высвобождения объекта службы.  
  
 Однако можно также самому создать объект службы, а затем создать основное приложение службы, используя этот объект. Для этого необходимо задать для свойства <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> значение <xref:System.ServiceModel.InstanceContextMode.Single> - в противном случае при открытии основного приложения службы возникает исключение.  
  
 Для создания такой службы используйте конструктор <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Object%2CSystem.Uri%5B%5D%29?displayProperty=nameWithType> . Он обеспечивает альтернативу реализации пользовательского <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer?displayProperty=nameWithType> , если требуется предоставить определенный экземпляр объекта для использования одноэлементной службой. Эту перегрузку можно использовать, если тип реализации службы сложно создать (например, если он не реализует открытый конструктор без параметров).
  
 Обратите внимание, что при указании объекта для этого конструктора некоторые функции, связанные с поведением создания экземпляров Windows Communication Foundation (WCF), работают по-разному. Например, вызов <xref:System.ServiceModel.InstanceContext.ReleaseServiceInstance%2A?displayProperty=nameWithType> не выполняет никаких действий, если предоставлен экземпляр хорошо известного объекта. Аналогичным образом игнорируются все другие механизмы освобождения экземпляров. Класс <xref:System.ServiceModel.ServiceHost> всегда ведет себя таким образом, как если бы для свойства <xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A?displayProperty=nameWithType> было задано значение <xref:System.ServiceModel.ReleaseInstanceMode.None?displayProperty=nameWithType> для всех операций.  
  
## <a name="other-service-endpoint-contract-and-operation-behaviors"></a>Другие поведения службы, конечной точки, контракта и операции  
 Поведения службы, такие как атрибут <xref:System.ServiceModel.ServiceBehaviorAttribute> , действуют во всей службе. Например, если для свойства <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A?displayProperty=nameWithType> задано значение <xref:System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType> , необходимо самостоятельно обрабатывать вопросы синхронизации потоков внутри каждой операции службы. Поведения конечной точки действуют на уровне конечной точки; многие из предоставляемых системой поведений конечных точек предназначены для функциональных возможностей клиентов. Поведения контракта действуют на уровне контракта, а поведения операции изменяют доставку операции.  
  
 Многие из этих поведений реализованы атрибутами, и их можно использовать так же, как и атрибуты <xref:System.ServiceModel.ServiceBehaviorAttribute> и <xref:System.ServiceModel.OperationBehaviorAttribute> - применяя их к определенной реализации класса службы или операции. Другие поведения, такие как объекты <xref:System.ServiceModel.Description.ServiceMetadataBehavior> и <xref:System.ServiceModel.Description.ServiceDebugBehavior> , обычно применяются с помощью файла конфигурации приложения, хотя их можно также использовать программно.  
  
 Например, публикация метаданных настраивается с помощью объекта <xref:System.ServiceModel.Description.ServiceMetadataBehavior> . В следующем файле конфигурации приложения показано наиболее часто встречающееся применение.  
  
 [!code-xml[ServiceMetadataBehavior#1](../../../samples/snippets/csharp/VS_Snippets_CFX/servicemetadatabehavior/cs/hostapplication.exe.config#1)]  
  
 В следующих разделах рассматриваются многие из наиболее полезных предоставляемых системой поведений, которые можно использовать для изменения доставки среды выполнения службы или клиента. Порядок использования каждого из них см. в разделе, указанном в ссылке.  
  
### <a name="service-behaviors"></a>Поведения служб  
 Следующие поведения работают на уровне служб.  
  
- <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> Применяется к службе WCF, чтобы указать, может ли эта служба запускаться в режиме совместимости ASP.NET.  
  
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> Управляет тем, как служба авторизует запросы клиентов.  
  
- <xref:System.ServiceModel.Description.ServiceCredentials> Настраивает учетные данные службы. Этот класс используется для указания учетных данных для службы, таких как сертификат X.509.  
  
- <xref:System.ServiceModel.Description.ServiceDebugBehavior> Включает функции отладки и справочной информации для службы WCF.  
  
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior> Контролирует публикацию метаданных службы и связанной с ними информации.  
  
- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> Задает расширения функциональности аудита для событий безопасности.  
  
- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> Настраивает параметры производительности времени выполнения, которые позволяют настроить производительность службы.  
  
### <a name="endpoint-behaviors"></a>Поведения конечных точек  
 Следующие поведения работают на уровне конечных точек. Многие из этих поведений используются в клиентских приложениях.  
  
- <xref:System.ServiceModel.CallbackBehaviorAttribute> Настраивает реализацию службы обратного вызова в дуплексном клиентском приложении.  
  
- <xref:System.ServiceModel.Description.CallbackDebugBehavior> Включает отладку службы для объекта обратного вызова WCF.  
  
- <xref:System.ServiceModel.Description.ClientCredentials> Позволяет пользователю настроить учетные данные клиента и службы, а также параметры проверки подлинности учетных данных службы для использования в клиенте.  
  
- <xref:System.ServiceModel.Description.ClientViaBehavior> Используется клиентами, чтобы указать универсальный код ресурса (URI), для которого необходимо создать канал транспорта.  
  
- <xref:System.ServiceModel.Description.MustUnderstandBehavior> Указывает WCF отключить обработку `MustUnderstand`.  
  
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior> Указывает, что в среде выполнения для каналов должен использоваться синхронный процесс получения.  
  
- <xref:System.ServiceModel.Description.TransactedBatchingBehavior> Оптимизирует операции получения для транспорта, поддерживающего транзакционные получения.  
  
### <a name="contract-behaviors"></a>Поведения контрактов  
 <xref:System.ServiceModel.DeliveryRequirementsAttribute> Задает требования к функциям, которые должны поддерживаться привязками для реализации службы или клиента.  
  
### <a name="operation-behaviors"></a>Поведения операций  
 Указанные ниже поведения операций задают элементы управления сериализацией и транзакциями для операций.  
  
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> Представляет поведение времени выполнения <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.  
  
- <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> Контролирует поведение времени выполнения для `XmlSerializer` и связывает его с операцией.  
  
- <xref:System.ServiceModel.TransactionFlowAttribute> Задает уровень, на котором операция службы принимает заголовок транзакции.  
  
## <a name="see-also"></a>См. также

- [Настройка служб](configuring-services.md)
- [Практическое руководство. Управление созданием экземпляров служб](./feature-details/how-to-control-service-instancing.md)
