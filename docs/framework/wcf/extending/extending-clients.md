---
title: Расширение клиентов
ms.date: 03/30/2017
helpviewer_keywords:
- proxy extensions [WCF]
ms.assetid: 1328c61c-06e5-455f-9ebd-ceefb59d3867
ms.openlocfilehash: 91277e1a4d0a1d001d62d677dbd087bec5d875f0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797159"
---
# <a name="extending-clients"></a>Расширение клиентов
В вызывающем приложении уровень модели службы отвечает за преобразование вызовов методов в коде приложения в исходящие сообщения, передачу их по соответствующим каналам, преобразование результатов обратно в возвращаемые значения и выходные параметры в коде приложения, а также за возврат результатов вызывающем объекту. Расширения модели службы изменяют или реализуют поведение и возможности выполнения или взаимодействия, в том числе возможности клиента или диспетчера, пользовательские поведения, перехват сообщений и параметров, а также другие возможности расширяемости.  
  
 В этом разделе описывается использование <xref:System.ServiceModel.Dispatcher.ClientRuntime> классов и <xref:System.ServiceModel.Dispatcher.ClientOperation> в клиентском приложении Windows Communication Foundation (WCF) для изменения поведения выполнения по умолчанию клиента WCF, а также для перехвата или изменения сообщений, параметров или возвращаемых значений. до или после отправки или получения из уровня канала. Дополнительные сведения о расширении среды выполнения службы см. в разделе [Расширение диспетчеров](extending-dispatchers.md). Дополнительные сведения о поведении, которые изменяют и вставляют объекты настройки в среду выполнения клиента, см. в разделе [Настройка и расширение среды выполнения с помощью поведений](configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="clients"></a>Клиенты  
 На клиенте клиентский объект или клиентский канал WCF преобразует вызовы методов в исходящие сообщения и входящие сообщения в результаты операций, возвращаемые вызывающему приложению. (Дополнительные сведения о типах клиентов см. в разделе [архитектура клиента WCF](../feature-details/client-architecture.md).)  
  
 Типы клиентов WCF имеют типы среды выполнения, которые обрабатывали эту конечную точку и функциональность на уровне операций. Когда приложение вызывает операцию, <xref:System.ServiceModel.Dispatcher.ClientOperation> преобразует исходящие объекты в сообщение, обрабатывает перехватчики, проверяет, что исходящий вызов соответствует целевому контракту, и передает исходящее сообщение объекту <xref:System.ServiceModel.Dispatcher.ClientRuntime>, который отвечает за создание исходящих каналов (и входящих в случае дуплексной связи) и управление ими, дополнительную обработку исходящих сообщений (например, изменение заголовка), обработку перехватчиков сообщений в обоих направлениях и перенаправление входящих дуплексных вызовов соответствующему объекту <xref:System.ServiceModel.Dispatcher.DispatchRuntime> на стороне клиента. Объекты <xref:System.ServiceModel.Dispatcher.ClientOperation> и <xref:System.ServiceModel.Dispatcher.ClientRuntime> выполняют аналогичные функции, когда сообщения (в том числе ошибки) возвращаются клиенту.  
  
 Эти два класса среды выполнения являются основным расширением для настройки обработки клиентских объектов и каналов WCF. Класс <xref:System.ServiceModel.Dispatcher.ClientRuntime> позволяет пользователям перехватывать и расширять выполнение клиента на уровне всех сообщений в контракте. Класс <xref:System.ServiceModel.Dispatcher.ClientOperation> позволяет пользователям перехватывать и расширять выполнение клиента для всех сообщений в заданной операции.  
  
 Изменение свойств и вставка дополнительных функций реализуются с помощью расширений функциональности контрактов, конечных точек и операций. Дополнительные сведения об использовании этих типов поведения для настройки среды выполнения клиента см. в разделе [Настройка и расширение среды выполнения с помощью поведений](configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="scenarios"></a>Сценарии  
 Существует несколько причин для расширения клиентской системы, в том числе следующие.  
  
- Пользовательская проверка сообщений У пользователя может возникнуть потребность проверить, что сообщение удовлетворяет конкретной схеме. Этого можно добиться, реализовав интерфейс <xref:System.ServiceModel.Dispatcher.IClientMessageInspector> и присвоив реализацию свойству <xref:System.ServiceModel.Dispatcher.DispatchRuntime.MessageInspectors%2A>. Примеры см. в разделах [Практическое руководство. Проверка или изменение сообщений на клиенте](how-to-inspect-or-modify-messages-on-the-client.md) и [выполнение следующих действий: Проверка или изменение сообщений на клиенте](how-to-inspect-or-modify-messages-on-the-client.md).  
  
- Ведение пользовательского журнала сообщений У пользователя может возникнуть потребность проверять и регистрировать некоторый набор сообщений приложения, которые проходят через конечную точку. Для этого также можно использовать интерфейсы перехватчиков сообщений.  
  
- Пользовательские преобразования сообщений Вместо изменения кода приложений пользователю может потребоваться применить некоторые преобразования к сообщению в среде выполнения (например, для работы с версиями). Для этого также можно использовать интерфейсы перехватчиков сообщений.  
  
- Пользовательская модель данных Пользователю может потребоваться использовать модель данных или сериализации, отличную от поддерживаемых по умолчанию в WCF (а именно <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>, и <xref:System.ServiceModel.Channels.Message?displayProperty=nameWithType> ). Этого можно добиться, реализовав интерфейсы модулей форматирования сообщений. Дополнительные сведения см. в описании интерфейса <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter?displayProperty=nameWithType> и свойства <xref:System.ServiceModel.Dispatcher.ClientOperation.Formatter%2A?displayProperty=nameWithType>.  
  
- Пользовательская проверка параметров Может возникнуть необходимость принудительной проверки введенных параметров (в отличие от XML). Для этого также можно использовать интерфейсы инспекторов параметров. Пример см. в статье [Практическое руководство. Проверьте или измените параметры](how-to-inspect-or-modify-parameters.md) или [проверку клиента](../samples/client-validation.md).  
  
### <a name="using-the-clientruntime-class"></a>Использование класса ClientRuntime  
 Класс <xref:System.ServiceModel.Dispatcher.ClientRuntime> является точкой расширения, в которую можно добавить объекты расширения, перехватывающие сообщения и расширяющие функциональность клиента. Объекты перехвата могут обрабатывать все сообщения в определенном контракте, обрабатывать только сообщения для определенных операций, выполнять инициализацию пользовательского канала, а также реализовывать другие варианты функциональности пользовательского клиентского приложения.  
  
- Свойство <xref:System.ServiceModel.Dispatcher.ClientRuntime.CallbackDispatchRuntime%2A> возвращает объект времени выполнения диспетчеризации для клиентов обратного вызова, инициируемого службой.  
  
- Свойство <xref:System.ServiceModel.Dispatcher.ClientRuntime.OperationSelector%2A> принимает объект выбора пользовательской операции.  
  
- Свойство <xref:System.ServiceModel.Dispatcher.ClientRuntime.ChannelInitializers%2A> позволяет добавлять инициализатор канала, который может проверять или изменять клиентский канал.  
  
- Свойство <xref:System.ServiceModel.Dispatcher.ClientRuntime.Operations%2A> возвращает коллекцию объектов <xref:System.ServiceModel.Dispatcher.ClientOperation>, в которую можно добавить пользовательские перехватчики сообщений, предоставляющие функциональность в соответствии с сообщениями данной операции.  
  
- Свойство <xref:System.ServiceModel.Dispatcher.ClientRuntime.ManualAddressing%2A> позволяет приложению отключать некоторые заголовки автоматической адресации для управления адресацией напрямую.  
  
- Свойство <xref:System.ServiceModel.Dispatcher.ClientRuntime.Via%2A> задает значение назначения сообщения на уровне транспорта для поддержки посредников и других сценариев.  
  
- <xref:System.ServiceModel.Dispatcher.ClientRuntime.MessageInspectors%2A> Свойство получает<xref:System.ServiceModel.Dispatcher.IClientMessageInspector> коллекцию объектов, к которым можно добавлять пользовательские перехватчики сообщений для всех сообщений, передаваемых через клиент WCF.  
  
 Кроме того, существует несколько других свойств, которые извлекают данные о контракте:  
  
- <xref:System.ServiceModel.Dispatcher.ClientRuntime.ContractName%2A>  
  
- <xref:System.ServiceModel.Dispatcher.ClientRuntime.ContractNamespace%2A>  
  
- <xref:System.ServiceModel.Dispatcher.ClientRuntime.ContractClientType%2A>  
  
 Если клиент WCF является дуплексным клиентом WCF, следующие свойства также извлекают сведения о клиенте обратного вызова WCF:  
  
- <xref:System.ServiceModel.Dispatcher.ClientRuntime.CallbackClientType%2A>  
  
- <xref:System.ServiceModel.Dispatcher.ClientRuntime.CallbackDispatchRuntime%2A>  
  
 Чтобы расширить выполнение клиента WCF во всем клиенте WCF, просмотрите свойства, доступные в <xref:System.ServiceModel.Dispatcher.ClientRuntime> классе, чтобы определить, нужно ли изменить свойство или реализовать интерфейс и добавить его в свойство, чтобы получить искомую функциональность. После выбора расширения для построения вставьте это расширение в соответствующее свойство <xref:System.ServiceModel.Dispatcher.ClientRuntime>, реализовав расширение функциональности клиента, которое при вызове обеспечивает доступ к классу <xref:System.ServiceModel.Dispatcher.ClientRuntime>.  
  
 Объекты пользовательских расширений можно вставлять в коллекцию с помощью расширения функциональности оператора (объекта, реализующего интерфейс <xref:System.ServiceModel.Description.IOperationBehavior>), контракта (объекта, реализующего интерфейс <xref:System.ServiceModel.Description.IContractBehavior>) или конечной точки (объекта, реализующего интерфейс <xref:System.ServiceModel.Description.IEndpointBehavior>). Устанавливаемый объект расширения функциональности добавляется в соответствующую коллекцию либо программным образам, либо декларативно (путем реализации пользовательского атрибута), либо путем реализации пользовательского объекта <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>, чтобы сделать возможной вставку расширения функциональности при помощи файла конфигурации приложения. Дополнительные сведения см. [в разделе Настройка и расширение среды выполнения с помощью поведений](configuring-and-extending-the-runtime-with-behaviors.md).  
  
 Примеры, демонстрирующие перехват в клиенте WCF, см. [в разделе как Проверка или изменение сообщений на клиенте](how-to-inspect-or-modify-messages-on-the-client.md).  
  
### <a name="using-the-clientoperation-class"></a>Использование класса ClientOperation  
 Класс <xref:System.ServiceModel.Dispatcher.ClientOperation> - это расположение для изменений клиента, вносимых во время выполнения, и точка вставки для пользовательских расширений, применяемых только к одной операции службы. (Чтобы изменить поведение клиента во время выполнения для всех сообщений в контракте, используйте класс <xref:System.ServiceModel.Dispatcher.ClientRuntime>.)  
  
 Используйте свойство <xref:System.ServiceModel.Dispatcher.ClientRuntime.Operations%2A>, чтобы найти объект <xref:System.ServiceModel.Dispatcher.ClientOperation>, который представляет определенную операцию службы. Следующие свойства позволяют вставлять пользовательские объекты в клиентскую систему WCF:  
  
- Используйте свойство <xref:System.ServiceModel.Dispatcher.ClientOperation.Formatter%2A> для вставки пользовательской реализации <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> для операции или изменения текущего модуля форматирования.  
  
- Используйте свойство <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A> для вставки пользовательской реализации <xref:System.ServiceModel.Dispatcher.IParameterInspector> или для изменения текущей реализации.  
  
 Следующие свойства позволяют изменить систему при взаимодействии с модулем форматирования и пользовательскими инспекторами параметров.  
  
- Используйте свойство <xref:System.ServiceModel.Dispatcher.ClientOperation.SerializeRequest%2A>, чтобы управлять сериализацией исходящего сообщения.  
  
- Используйте свойство <xref:System.ServiceModel.Dispatcher.ClientOperation.DeserializeReply%2A>, чтобы управлять десериализацией входящего сообщения.  
  
- Используйте свойство <xref:System.ServiceModel.Dispatcher.ClientOperation.Action%2A>, чтобы управлять действием WS-Addressing сообщения запроса.  
  
- <xref:System.ServiceModel.Dispatcher.ClientOperation.BeginMethod%2A> Используйте и <xref:System.ServiceModel.Dispatcher.ClientOperation.EndMethod%2A> , чтобы указать, какие клиентские методы WCF связаны с асинхронной операцией.  
  
- Используйте свойство <xref:System.ServiceModel.Dispatcher.ClientOperation.FaultContractInfos%2A>, чтобы получить коллекцию, содержащую типы, которые могут содержаться в ошибках SOAP в качестве типа сведений.  
  
- Используйте свойства <xref:System.ServiceModel.Dispatcher.ClientOperation.IsInitiating%2A> и <xref:System.ServiceModel.Dispatcher.ClientOperation.IsTerminating%2A>, чтобы задать соответственно инициализацию или завершение сеанса при вызове операции.  
  
- Используйте свойство <xref:System.ServiceModel.Dispatcher.ClientOperation.IsOneWay%2A>, чтобы определить, является ли операция односторонней.  
  
- Используйте свойство <xref:System.ServiceModel.Dispatcher.ClientOperation.Parent%2A> для получения родительского объекта <xref:System.ServiceModel.Dispatcher.ClientRuntime>.  
  
- Используйте свойство <xref:System.ServiceModel.Dispatcher.ClientOperation.Name%2A> для получения имени операции.  
  
- Используйте свойство <xref:System.ServiceModel.Dispatcher.ClientOperation.SyncMethod%2A> для определения метода, который сопоставлен операции.  
  
 Чтобы расширить выполнение клиента WCF только на одной операции службы, просмотрите свойства, доступные в <xref:System.ServiceModel.Dispatcher.ClientOperation> классе, чтобы определить, нужно ли изменить свойство или реализовать интерфейс и добавить его в свойство, чтобы получить искомую функциональность. После выбора расширения для построения вставьте это расширение в соответствующее свойство <xref:System.ServiceModel.Dispatcher.ClientOperation>, реализовав расширение функциональности клиента, которое при вызове обеспечивает доступ к классу <xref:System.ServiceModel.Dispatcher.ClientOperation>. После этого внутри данного расширения функциональности можно изменить свойство <xref:System.ServiceModel.Dispatcher.ClientRuntime> для удовлетворения необходимых требований.  
  
 Обычно реализации расширения функциональности операции (объекта, реализующего интерфейс <xref:System.ServiceModel.Description.IOperationBehavior>) бывает достаточно, но для достижения такого же результата можно также воспользоваться расширениями функциональности конечных точек и контрактов, найдя объект <xref:System.ServiceModel.Description.OperationDescription> для конкретной операции и прикрепив к нему расширение функциональности. Дополнительные сведения см. [в разделе Настройка и расширение среды выполнения с помощью поведений](configuring-and-extending-the-runtime-with-behaviors.md).  
  
 Чтобы использовать пользовательское расширение функциональности на этапе конфигурации, установите его с использованием обработчика раздела конфигурации пользовательского расширения функциональности. Его также можно установить путем создания пользовательского атрибута.  
  
 Примеры, демонстрирующие перехват в клиенте WCF, см. [в разделе как Проверьте или измените параметры](how-to-inspect-or-modify-parameters.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Dispatcher.ClientRuntime>
- <xref:System.ServiceModel.Dispatcher.ClientOperation>
- [Практическое руководство. Проверка или изменение сообщений на клиенте](how-to-inspect-or-modify-messages-on-the-client.md)
- [Практическое руководство. Проверка или изменение параметров](how-to-inspect-or-modify-parameters.md)
