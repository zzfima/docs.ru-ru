---
title: Расширение клиентов
ms.date: 03/30/2017
helpviewer_keywords:
- proxy extensions [WCF]
ms.assetid: 1328c61c-06e5-455f-9ebd-ceefb59d3867
ms.openlocfilehash: 7eea247602d24c545e0de5fa9df50e83aae8ed7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="extending-clients"></a>Расширение клиентов
В вызывающем приложении уровень модели службы отвечает за преобразование вызовов методов в коде приложения в исходящие сообщения, передачу их по соответствующим каналам, преобразование результатов обратно в возвращаемые значения и выходные параметры в коде приложения, а также за возврат результатов вызывающем объекту. Расширения модели службы изменяют или реализуют поведение и возможности выполнения или взаимодействия, в том числе возможности клиента или диспетчера, пользовательские поведения, перехват сообщений и параметров, а также другие возможности расширяемости.  
  
 В этом разделе описывается использование <xref:System.ServiceModel.Dispatcher.ClientRuntime> и <xref:System.ServiceModel.Dispatcher.ClientOperation> классы в клиентском приложении Windows Communication Foundation (WCF) для изменения поведения выполнения по умолчанию [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] клиента или чтобы перехватывать или изменять сообщения, параметры или возвращаемые значения до или после их отправки и получения через канал. Дополнительные сведения о расширении среды выполнения службы см. в разделе [расширение диспетчеров](../../../../docs/framework/wcf/extending/extending-dispatchers.md). Дополнительные сведения о моделях поведения, изменять и вставлять объекты настройки в среду выполнения клиента см. в разделе [настройку и расширение среды выполнения с помощью поведений](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="clients"></a>Клиенты  
 На стороне клиента объект или канал клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] преобразует вызовы метода в исходящие сообщения, а входящие сообщения - в результат выполнения операций, возвращаемый вызывающему приложению. (Дополнительные сведения о типах клиента см. в разделе [Клиентская архитектура технологии WCF](../../../../docs/framework/wcf/feature-details/client-architecture.md).)  
  
 У типов клиентов [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] имеются типы среды выполнения, которые обрабатывают данные функции уровня конечных точек и операций. Когда приложение вызывает операцию, <xref:System.ServiceModel.Dispatcher.ClientOperation> преобразует исходящие объекты в сообщение, обрабатывает перехватчики, проверяет, что исходящий вызов соответствует целевому контракту, и передает исходящее сообщение объекту <xref:System.ServiceModel.Dispatcher.ClientRuntime>, который отвечает за создание исходящих каналов (и входящих в случае дуплексной связи) и управление ими, дополнительную обработку исходящих сообщений (например, изменение заголовка), обработку перехватчиков сообщений в обоих направлениях и перенаправление входящих дуплексных вызовов соответствующему объекту <xref:System.ServiceModel.Dispatcher.DispatchRuntime> на стороне клиента. Объекты <xref:System.ServiceModel.Dispatcher.ClientOperation> и <xref:System.ServiceModel.Dispatcher.ClientRuntime> выполняют аналогичные функции, когда сообщения (в том числе ошибки) возвращаются клиенту.  
  
 Эти два класса среды выполнения являются основным расширением, позволяющим настроить обработку объектов и каналов клиентов [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Класс <xref:System.ServiceModel.Dispatcher.ClientRuntime> позволяет пользователям перехватывать и расширять выполнение клиента на уровне всех сообщений в контракте. Класс <xref:System.ServiceModel.Dispatcher.ClientOperation> позволяет пользователям перехватывать и расширять выполнение клиента для всех сообщений в заданной операции.  
  
 Изменение свойств и вставка дополнительных функций реализуются с помощью расширений функциональности контрактов, конечных точек и операций. Дополнительные сведения о том, как использовать эти типы поведения для выполнения настройки среды выполнения клиента см. в разделе [настройку и расширение среды выполнения с помощью поведений](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="scenarios"></a>Сценарии  
 Существует несколько причин для расширения клиентской системы, в том числе следующие.  
  
-   Пользовательская проверка сообщений У пользователя может возникнуть потребность проверить, что сообщение удовлетворяет конкретной схеме. Этого можно добиться, реализовав интерфейс <xref:System.ServiceModel.Dispatcher.IClientMessageInspector> и присвоив реализацию свойству <xref:System.ServiceModel.Dispatcher.DispatchRuntime.MessageInspectors%2A>. Примеры см. в разделе [как: проверки или изменения сообщений на клиенте](../../../../docs/framework/wcf/extending/how-to-inspect-or-modify-messages-on-the-client.md) и [как: проверки или изменения сообщений на клиенте](../../../../docs/framework/wcf/extending/how-to-inspect-or-modify-messages-on-the-client.md).  
  
-   Ведение пользовательского журнала сообщений У пользователя может возникнуть потребность проверять и регистрировать некоторый набор сообщений приложения, которые проходят через конечную точку. Для этого также можно использовать интерфейсы перехватчиков сообщений.  
  
-   Пользовательские преобразования сообщений Вместо изменения кода приложений пользователю может потребоваться применить некоторые преобразования к сообщению в среде выполнения (например, для работы с версиями). Для этого также можно использовать интерфейсы перехватчиков сообщений.  
  
-   Пользовательская модель данных Может возникнуть необходимость использовать модель данных и сериализации, отличную от модели, которая по умолчанию поддерживается в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] (а именно объекты <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>, <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> и <xref:System.ServiceModel.Channels.Message?displayProperty=nameWithType>). Этого можно добиться, реализовав интерфейсы модулей форматирования сообщений. Дополнительные сведения см. в описании интерфейса <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter?displayProperty=nameWithType> и свойства <xref:System.ServiceModel.Dispatcher.ClientOperation.Formatter%2A?displayProperty=nameWithType>.  
  
-   Пользовательская проверка параметров Может возникнуть необходимость принудительной проверки введенных параметров (в отличие от XML). Для этого также можно использовать интерфейсы инспекторов параметров. Пример см. в разделе [как: проверять или изменять параметры](../../../../docs/framework/wcf/extending/how-to-inspect-or-modify-parameters.md) или [клиентской проверки](../../../../docs/framework/wcf/samples/client-validation.md).  
  
### <a name="using-the-clientruntime-class"></a>Использование класса ClientRuntime  
 Класс <xref:System.ServiceModel.Dispatcher.ClientRuntime> является точкой расширения, в которую можно добавить объекты расширения, перехватывающие сообщения и расширяющие функциональность клиента. Объекты перехвата могут обрабатывать все сообщения в определенном контракте, обрабатывать только сообщения для определенных операций, выполнять инициализацию пользовательского канала, а также реализовывать другие варианты функциональности пользовательского клиентского приложения.  
  
-   Свойство <xref:System.ServiceModel.Dispatcher.ClientRuntime.CallbackDispatchRuntime%2A> возвращает объект времени выполнения диспетчеризации для клиентов обратного вызова, инициируемого службой.  
  
-   Свойство <xref:System.ServiceModel.Dispatcher.ClientRuntime.OperationSelector%2A> принимает объект выбора пользовательской операции.  
  
-   Свойство <xref:System.ServiceModel.Dispatcher.ClientRuntime.ChannelInitializers%2A> позволяет добавлять инициализатор канала, который может проверять или изменять клиентский канал.  
  
-   Свойство <xref:System.ServiceModel.Dispatcher.ClientRuntime.Operations%2A> возвращает коллекцию объектов <xref:System.ServiceModel.Dispatcher.ClientOperation>, в которую можно добавить пользовательские перехватчики сообщений, предоставляющие функциональность в соответствии с сообщениями данной операции.  
  
-   Свойство <xref:System.ServiceModel.Dispatcher.ClientRuntime.ManualAddressing%2A> позволяет приложению отключать некоторые заголовки автоматической адресации для управления адресацией напрямую.  
  
-   Свойство <xref:System.ServiceModel.Dispatcher.ClientRuntime.Via%2A> задает значение назначения сообщения на уровне транспорта для поддержки посредников и других сценариев.  
  
-   Свойство <xref:System.ServiceModel.Dispatcher.ClientRuntime.MessageInspectors%2A> возвращает коллекцию объектов <xref:System.ServiceModel.Dispatcher.IClientMessageInspector>, в которую можно добавить пользовательские перехватчики сообщений для всех сообщений, проходящих через клиент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Кроме того, существует несколько других свойств, которые извлекают данные о контракте:  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.ContractName%2A>  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.ContractNamespace%2A>  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.ContractClientType%2A>  
  
 Если клиент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] является дуплексным клиентом [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], то следующие свойства также извлекают сведения о клиенте [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] обратного вызова:  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.CallbackClientType%2A>  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.CallbackDispatchRuntime%2A>  
  
 Чтобы расширить выполнение клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] на весь клиент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], изучите свойства, предоставляемые классом <xref:System.ServiceModel.Dispatcher.ClientRuntime>, чтобы понять, каким образом проще реализовать нужную функциональность - путем изменения свойства или путем реализации интерфейса и его добавления в свойство. После выбора расширения для построения вставьте это расширение в соответствующее свойство <xref:System.ServiceModel.Dispatcher.ClientRuntime>, реализовав расширение функциональности клиента, которое при вызове обеспечивает доступ к классу <xref:System.ServiceModel.Dispatcher.ClientRuntime>.  
  
 Объекты пользовательских расширений можно вставлять в коллекцию с помощью расширения функциональности оператора (объекта, реализующего интерфейс <xref:System.ServiceModel.Description.IOperationBehavior>), контракта (объекта, реализующего интерфейс <xref:System.ServiceModel.Description.IContractBehavior>) или конечной точки (объекта, реализующего интерфейс <xref:System.ServiceModel.Description.IEndpointBehavior>). Устанавливаемый объект расширения функциональности добавляется в соответствующую коллекцию либо программным образам, либо декларативно (путем реализации пользовательского атрибута), либо путем реализации пользовательского объекта <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>, чтобы сделать возможной вставку расширения функциональности при помощи файла конфигурации приложения. Дополнительные сведения см. в разделе [настройку и расширение среды выполнения с помощью поведений](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  
  
 Примеры, демонстрирующие перехвата через [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] клиента, в разделе [как: проверки или изменения сообщений на клиенте](../../../../docs/framework/wcf/extending/how-to-inspect-or-modify-messages-on-the-client.md).  
  
### <a name="using-the-clientoperation-class"></a>Использование класса ClientOperation  
 Класс <xref:System.ServiceModel.Dispatcher.ClientOperation> - это расположение для изменений клиента, вносимых во время выполнения, и точка вставки для пользовательских расширений, применяемых только к одной операции службы. (Чтобы изменить поведение клиента во время выполнения для всех сообщений в контракте, используйте класс <xref:System.ServiceModel.Dispatcher.ClientRuntime>.)  
  
 Используйте свойство <xref:System.ServiceModel.Dispatcher.ClientRuntime.Operations%2A>, чтобы найти объект <xref:System.ServiceModel.Dispatcher.ClientOperation>, который представляет определенную операцию службы. Следующие свойства позволяют вставить пользовательские объекты в систему клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
-   Используйте свойство <xref:System.ServiceModel.Dispatcher.ClientOperation.Formatter%2A> для вставки пользовательской реализации <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> для операции или изменения текущего модуля форматирования.  
  
-   Используйте свойство <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A> для вставки пользовательской реализации <xref:System.ServiceModel.Dispatcher.IParameterInspector> или для изменения текущей реализации.  
  
 Следующие свойства позволяют изменить систему при взаимодействии с модулем форматирования и пользовательскими инспекторами параметров.  
  
-   Используйте свойство <xref:System.ServiceModel.Dispatcher.ClientOperation.SerializeRequest%2A>, чтобы управлять сериализацией исходящего сообщения.  
  
-   Используйте свойство <xref:System.ServiceModel.Dispatcher.ClientOperation.DeserializeReply%2A>, чтобы управлять десериализацией входящего сообщения.  
  
-   Используйте свойство <xref:System.ServiceModel.Dispatcher.ClientOperation.Action%2A>, чтобы управлять действием WS-Addressing сообщения запроса.  
  
-   Используйте свойства <xref:System.ServiceModel.Dispatcher.ClientOperation.BeginMethod%2A> и <xref:System.ServiceModel.Dispatcher.ClientOperation.EndMethod%2A> для указания методов клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], которые связаны с асинхронной операцией.  
  
-   Используйте свойство <xref:System.ServiceModel.Dispatcher.ClientOperation.FaultContractInfos%2A>, чтобы получить коллекцию, содержащую типы, которые могут содержаться в ошибках SOAP в качестве типа сведений.  
  
-   Используйте свойства <xref:System.ServiceModel.Dispatcher.ClientOperation.IsInitiating%2A> и <xref:System.ServiceModel.Dispatcher.ClientOperation.IsTerminating%2A>, чтобы задать соответственно инициализацию или завершение сеанса при вызове операции.  
  
-   Используйте свойство <xref:System.ServiceModel.Dispatcher.ClientOperation.IsOneWay%2A>, чтобы определить, является ли операция односторонней.  
  
-   Используйте свойство <xref:System.ServiceModel.Dispatcher.ClientOperation.Parent%2A> для получения родительского объекта <xref:System.ServiceModel.Dispatcher.ClientRuntime>.  
  
-   Используйте свойство <xref:System.ServiceModel.Dispatcher.ClientOperation.Name%2A> для получения имени операции.  
  
-   Используйте свойство <xref:System.ServiceModel.Dispatcher.ClientOperation.SyncMethod%2A> для определения метода, который сопоставлен операции.  
  
 Чтобы расширить выполнение клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] только на одну операцию службы, изучите свойства, предоставляемые классом <xref:System.ServiceModel.Dispatcher.ClientOperation>, чтобы понять, каким образом проще реализовать нужную функциональность - путем изменения свойства или путем реализации интерфейса и его добавления в свойство. После выбора расширения для построения вставьте это расширение в соответствующее свойство <xref:System.ServiceModel.Dispatcher.ClientOperation>, реализовав расширение функциональности клиента, которое при вызове обеспечивает доступ к классу <xref:System.ServiceModel.Dispatcher.ClientOperation>. После этого внутри данного расширения функциональности можно изменить свойство <xref:System.ServiceModel.Dispatcher.ClientRuntime> для удовлетворения необходимых требований.  
  
 Обычно реализации расширения функциональности операции (объекта, реализующего интерфейс <xref:System.ServiceModel.Description.IOperationBehavior>) бывает достаточно, но для достижения такого же результата можно также воспользоваться расширениями функциональности конечных точек и контрактов, найдя объект <xref:System.ServiceModel.Description.OperationDescription> для конкретной операции и прикрепив к нему расширение функциональности. Дополнительные сведения см. в разделе [настройку и расширение среды выполнения с помощью поведений](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  
  
 Чтобы использовать пользовательское расширение функциональности на этапе конфигурации, установите его с использованием обработчика раздела конфигурации пользовательского расширения функциональности. Его также можно установить путем создания пользовательского атрибута.  
  
 Примеры, демонстрирующие перехват по [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] клиента, в разделе [как: проверить или изменить параметры](../../../../docs/framework/wcf/extending/how-to-inspect-or-modify-parameters.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Dispatcher.ClientRuntime>  
 <xref:System.ServiceModel.Dispatcher.ClientOperation>  
 [Практическое руководство. Проверка или изменение сообщений на клиенте](../../../../docs/framework/wcf/extending/how-to-inspect-or-modify-messages-on-the-client.md)  
 [Практическое руководство. Проверка или изменение параметров](../../../../docs/framework/wcf/extending/how-to-inspect-or-modify-parameters.md)
