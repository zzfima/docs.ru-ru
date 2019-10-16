---
title: Сбои при отправке и получении
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- handling faults [WCF], sending
ms.assetid: 7be6fb96-ce2a-450b-aebe-f932c6a4bc5d
ms.openlocfilehash: dc9dcb5d8e36984d1e5a2e5c5124e74509de7f3d
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320217"
---
# <a name="sending-and-receiving-faults"></a>Сбои при отправке и получении

Ошибки SOAP передают сведения об ошибке от службы клиенту и, в дуплексном случае, от клиента службе совместимым способом. Как правило, служба определяет пользовательское содержимое ошибки и указывает операции, которые могут возвращать такие ошибки. (Дополнительные сведения см. в разделе [Определение и указание ошибок](defining-and-specifying-faults.md).) В этом разделе обсуждается, как служба или дуплексный клиент могут отправить эти ошибки при возникновении соответствующего условия ошибки и о том, как клиент или приложение службы обрабатывает эти ошибки. Общие сведения об обработке ошибок в приложениях Windows Communication Foundation (WCF) см. в разделе [Указание и обработка ошибок в контрактах и службах](specifying-and-handling-faults-in-contracts-and-services.md).

## <a name="sending-soap-faults"></a>Отправка ошибок SOAP

Объявленные ошибки SOAP - это ошибки, в которых в операции имеется атрибут <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>, указывающий пользовательский тип ошибки SOAP. Необъявленные ошибки SOAP - это ошибки, не указанные в контракте операции.

### <a name="sending-declared-faults"></a>Отправка объявленных ошибок

Чтобы отправить объявленную ошибку SOAP, необходимо обнаружить условия ошибки, в которых возникает ошибка SOAP, и создать новое исключение <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>, в котором параметр типа является новым объектом типа, указанным в атрибуте <xref:System.ServiceModel.FaultContractAttribute> для этой операции. В следующем примере кода показано, как с помощью атрибута <xref:System.ServiceModel.FaultContractAttribute> указать, что операция `SampleMethod` может возвращать ошибку SOAP с типом по умолчанию `GreetingFault`.

[!code-csharp[FaultContractAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#4)]
[!code-vb[FaultContractAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#4)]

Для передачи клиенту сведений об ошибке `GreetingFault` необходимо перехватить ошибку и создать новое исключение <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> типа `GreetingFault` с новым объектом `GreetingFault` в качестве аргумента; см. пример кода ниже. Если клиент является клиентским приложением WCF, он работает как управляемое исключение, где тип — <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> типа `GreetingFault`.

[!code-csharp[FaultContractAttribute#5](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#5)]
[!code-vb[FaultContractAttribute#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#5)]

### <a name="sending-undeclared-faults"></a>Отправка необъявленных ошибок

Отправка необъявленных сбоев может оказаться очень полезной для быстрой диагностики и отладки проблем в приложениях WCF, но ее полезность в том, что это средство отладки ограничено. В общем случае при отладке рекомендуется использовать свойство <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType>. Если свойству присвоено значение true, клиенты получают такие ошибки в виде исключений <xref:System.ServiceModel.FaultException%601> типа <xref:System.ServiceModel.ExceptionDetail>.

> [!IMPORTANT]
> Поскольку управляемые исключения могут предоставлять внутренние сведения о приложении, установка <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> или <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> в `true` может позволить клиентам WCF получать сведения о внутренних исключениях операций службы, включая персональные и другие конфиденциальные данные. об.
>
> Поэтому задавать для свойства <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> или <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> значение `true` рекомендуется только для временной отладки приложения службы. Кроме того, WSDL для метода, который возвращает такие необработанные управляемые исключения, не содержит контракт для исключения <xref:System.ServiceModel.FaultException%601> типа <xref:System.ServiceModel.ExceptionDetail>. Клиенты должны рассчитывать на возможность неизвестной ошибки SOAP (возвращенные клиентам WCF как объекты <xref:System.ServiceModel.FaultException?displayProperty=nameWithType>) для правильного получения отладочной информации.

Чтобы отправить необъявленную ошибку SOAP, необходимо создать объект <xref:System.ServiceModel.FaultException?displayProperty=nameWithType> (не универсального типа <xref:System.ServiceModel.FaultException%601>) и передать строку конструктору. Он предоставляется клиентским приложениям WCF в виде вызванного исключения <xref:System.ServiceModel.FaultException?displayProperty=nameWithType>, где строка доступна путем вызова метода <xref:System.ServiceModel.FaultException%601.ToString%2A?displayProperty=nameWithType>.

> [!NOTE]
> Если объявлена ошибка SOAP строкового типа, а затем она выдана службе в виде объекта <xref:System.ServiceModel.FaultException%601> с параметром типа <xref:System.String?displayProperty=nameWithType>, значение строки присваивается свойству <xref:System.ServiceModel.FaultException%601.Detail%2A?displayProperty=nameWithType> и недоступно в свойстве <xref:System.ServiceModel.FaultException%601.ToString%2A?displayProperty=nameWithType>.

## <a name="handling-faults"></a>Обработка ошибок

В клиентах WCF ошибки SOAP, происходящие при обмене данными, которые представляют интерес для клиентских приложений, вызываются как управляемые исключения. Хотя существует множество исключений, которые могут возникнуть во время выполнения любой программы, приложения, использующие клиентскую модель программирования WCF, могут рассчитывать исключения следующих двух типов в результате обмена данными.

- <xref:System.TimeoutException>

- <xref:System.ServiceModel.CommunicationException>

Объекты <xref:System.TimeoutException> выдаются по истечении заданного времени ожидания.

Объекты <xref:System.ServiceModel.CommunicationException> выдаются в случае возникновения устранимой ошибки передачи данных в службе или клиенте.

Класс <xref:System.ServiceModel.CommunicationException> имеет два важных производных типа, <xref:System.ServiceModel.FaultException> и универсальный тип <xref:System.ServiceModel.FaultException%601>.

Исключения <xref:System.ServiceModel.FaultException> выдаются, когда прослушиватель получает неожиданную или не указанную в контракте операции ошибку. Обычно это происходит во время отладки приложения, когда свойству <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> службы присвоено значение `true`.

Исключения <xref:System.ServiceModel.FaultException%601> выдаются в клиенте при получении ошибки, указанной в контракте операции, в ответ на двустороннюю операцию (т.е. метод с атрибутом <xref:System.ServiceModel.OperationContractAttribute>, у которого свойству <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> присвоено значение `false`).

> [!NOTE]
> Если для службы WCF свойство <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> или <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> установлено в значение `true`, клиент выдает это как необъявленный <xref:System.ServiceModel.FaultException%601> типа <xref:System.ServiceModel.ExceptionDetail>. Клиенты могут либо перехватить эту определенную ошибку, либо обработать ее в блоке catch для <xref:System.ServiceModel.FaultException>.

Как правило, только исключения <xref:System.ServiceModel.FaultException%601>, <xref:System.TimeoutException> и <xref:System.ServiceModel.CommunicationException> представляют интерес для клиентов и служб.

> [!NOTE]
> Конечно, возникают и другие исключения. К неожиданным исключениям относятся неустранимые ошибки, например <xref:System.OutOfMemoryException?displayProperty=nameWithType>. Как правило, приложения не должны перехватывать такие методы.

### <a name="catch-fault-exceptions-in-the-correct-order"></a>Перехват исключений ошибок в правильном порядке

Поскольку класс <xref:System.ServiceModel.FaultException%601> является производным класса <xref:System.ServiceModel.FaultException>, а класс <xref:System.ServiceModel.FaultException> является производным класса <xref:System.ServiceModel.CommunicationException>, важно перехватывать эти исключения в нужном порядке. Например, если в блоке try/catch сначала перехватывается исключение <xref:System.ServiceModel.CommunicationException>, обработка всех объявленных и необъявленных ошибок SOAP будет выполняться в этом блоке. Все последующие блоки catch, предназначенные для обработки пользовательского исключения <xref:System.ServiceModel.FaultException%601>, не вызываются никогда.

Помните, что одна операция может возвращать любое количество объявленных ошибок. Каждая ошибка имеет уникальный тип и должна обрабатываться отдельно.

### <a name="handle-exceptions-when-closing-the-channel"></a>Обработка исключений при закрытии канала

Большая часть предыдущего обсуждения связана с ошибками, отправленными в процессе обработки сообщений приложения, то есть сообщения, явно отправленные клиентом, когда клиентское приложение вызывает операции в клиентском объекте WCF.

Даже при удалении локального объекта могут быть созданы или скрыты исключения, возникающие в процессе перезапуска. Что-то подобное может произойти при использовании объектов клиента WCF. При вызове операций сообщения передаются по установленному подключению. Закрытие канала может приводить к исключениям, если не удается аккуратно закрыть подключение или если оно уже закрыто, даже при надлежащем возврате всех операций.

Как правило, каналы объекта клиента закрываются одним из следующих способов.

- При повторном запуске клиентского объекта WCF.

- При вызове метода <xref:System.ServiceModel.ClientBase%601.Close%2A?displayProperty=nameWithType> клиентским приложением.

- При вызове метода <xref:System.ServiceModel.ICommunicationObject.Close%2A?displayProperty=nameWithType> клиентским приложением.

- При вызове клиентским приложением операции, которая является завершающей операцией сеанса.

Во всех случаях при закрытии канал получает указания начать закрытие всех базовых каналов, которые могут отправлять сообщения для поддержки сложных функций на уровне приложения. Например, если контракту требуются сеансы, привязка предпринимает попытки установить сеанс путем обмена сообщениями с каналом службы до тех пор, пока сеанс не будет установлен. После закрытия канала базовый канал сеанса уведомляет службу о прерывании сеанса. Если канал уже был прерван, закрыт или иным образом стал непригодным (например, при отключении сетевого кабеля), канал клиента не может уведомить канал службы о прекращении сеанса и возможном исключении.

### <a name="abort-the-channel-if-necessary"></a>Прерывание работы канала при необходимости

Поскольку при закрытии канала также могут создаваться исключения, рекомендуется в дополнение к перехвату исключений ошибок в правильном порядке прерывать канал, использованный в вызове, в блоке catch.

Если ошибка содержит сведения об ошибке, касающиеся операции, и существует возможность использования ее другими объектами, прерывать канал не требуется (такие случаи являются редкими). Во всех остальных случаях рекомендуется прерывать канал. Пример, демонстрирующий все эти моменты, см. в разделе [ожидаемые исключения](./samples/expected-exceptions.md).

В следующем примере кода демонстрируется обработка исключений ошибок SOAP в простом клиентском приложении, в том числе объявленных и необъявленных ошибок.

> [!NOTE]
> В этом примере кода не используется конструкция `using`. Поскольку закрытие каналов может вызывать исключения, рекомендуется сначала создать клиент WCF, а затем открыть, использовать и закрыть клиент WCF в том же блоке try. Дополнительные сведения см. в статье [Общие сведения о клиенте WCF](wcf-client-overview.md) и [Использование Close и Abort для освобождения ресурсов клиента WCF](./samples/use-close-abort-release-wcf-client-resources.md).

[!code-csharp[FaultContractAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/client.cs#3)]
[!code-vb[FaultContractAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/client.vb#3)]

## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.FaultException>
- <xref:System.ServiceModel.FaultException%601>
- <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType>
- [Ожидаемые исключения](./samples/expected-exceptions.md)
- [Использование закрытия и прерывания для освобождения ресурсов клиента WCF](./samples/use-close-abort-release-wcf-client-resources.md)
