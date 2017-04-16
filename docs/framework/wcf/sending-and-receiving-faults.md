---
title: "Сбои при отправке и получении | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "обработка ошибок [WCF], отправка"
ms.assetid: 7be6fb96-ce2a-450b-aebe-f932c6a4bc5d
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Сбои при отправке и получении
Ошибки SOAP передают сведения об ошибке от службы клиенту и, в дуплексном случае, от клиента службе совместимым способом.Как правило, служба определяет пользовательское содержимое ошибки и указывает операции, которые могут возвращать такие ошибки.\(Дополнительные сведения см. в разделе [Определение и задание сбоев](../../../docs/framework/wcf/defining-and-specifying-faults.md).\) В этом разделе описывается, как служба или дуплексный клиент могут отправлять такие ошибки в случае возникновения соответствующих условий и как клиентское приложение или приложение службы обрабатывает эти ошибки.Общие сведения об обработке ошибок в приложениях [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] см. в разделе [Задание и обработка сбоев в контрактах и службах](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).  
  
## Отправка ошибок SOAP  
 Объявленные ошибки SOAP — это ошибки, в которых в операции имеется атрибут <xref:System.ServiceModel.FaultContractAttribute?displayProperty=fullName>, указывающий пользовательский тип ошибки SOAP.Необъявленные ошибки SOAP — это ошибки, не указанные в контракте операции.  
  
### Отправка объявленных ошибок  
 Чтобы отправить объявленную ошибку SOAP, необходимо обнаружить условия ошибки, в которых возникает ошибка SOAP, и создать новое исключение <xref:System.ServiceModel.FaultException%601?displayProperty=fullName>, в котором параметр типа является новым объектом типа, указанным в атрибуте <xref:System.ServiceModel.FaultContractAttribute> для этой операции.В следующем примере кода показано, как с помощью атрибута <xref:System.ServiceModel.FaultContractAttribute> указать, что операция `SampleMethod` может возвращать ошибку SOAP с типом по умолчанию `GreetingFault`.  
  
 [!code-csharp[FaultContractAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#4)]
 [!code-vb[FaultContractAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#4)]  
  
 Для передачи клиенту сведений об ошибке `GreetingFault` необходимо перехватить ошибку и создать новое исключение <xref:System.ServiceModel.FaultException%601?displayProperty=fullName> типа `GreetingFault` с новым объектом `GreetingFault` в качестве аргумента; см. пример кода ниже.Если клиент является клиентским приложением [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], исключение обрабатывается как управляемое исключение, принадлежащее типу <xref:System.ServiceModel.FaultException%601?displayProperty=fullName> типа `GreetingFault`.  
  
 [!code-csharp[FaultContractAttribute#5](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#5)]
 [!code-vb[FaultContractAttribute#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#5)]  
  
### Отправка необъявленных ошибок  
 Отправка необъявленных ошибок может оказаться очень полезной для быстрой диагностики и отладки ошибок в приложениях [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], однако ее возможности в качестве средства отладки ограничены.В общем случае при отладке рекомендуется использовать свойство <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=fullName>.Если свойству присвоено значение true, клиенты получают такие ошибки в виде исключений <xref:System.ServiceModel.FaultException%601> типа <xref:System.ServiceModel.ExceptionDetail>.  
  
> [!IMPORTANT]
>  Управляемые исключения могут предоставлять внутренние сведения о приложении, поэтому присвоение свойству <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=fullName> или <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=fullName> значения `true` позволяет клиентам [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] получать информацию о внутренних исключениях операции службы.  
>   
>  Поэтому задавать для свойства <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=fullName> или <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=fullName> значение `true` рекомендуется только для временной отладки приложения службы.Кроме того, WSDL для метода, который возвращает такие необработанные управляемые исключения, не содержит контракт для исключения <xref:System.ServiceModel.FaultException%601> типа <xref:System.ServiceModel.ExceptionDetail>.В клиентах должна быть предусмотрена возможность получения неизвестной ошибки SOAP \(возвращаемой клиентам [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] в виде объектов <xref:System.ServiceModel.FaultException?displayProperty=fullName>\) для надлежащего получения отладочной информации.  
  
 Чтобы отправить необъявленную ошибку SOAP, необходимо создать объект <xref:System.ServiceModel.FaultException?displayProperty=fullName> \(не универсального типа <xref:System.ServiceModel.FaultException%601>\) и передать строку конструктору.Она предоставляется клиентскому приложению [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] в виде исключения <xref:System.ServiceModel.FaultException?displayProperty=fullName>. Доступ к строке в этом исключении можно получить с помощью метода <xref:System.ServiceModel.FaultException%601.ToString%2A?displayProperty=fullName>.  
  
> [!NOTE]
>  Если объявлена ошибка SOAP строкового типа, а затем она выдана службе в виде объекта <xref:System.ServiceModel.FaultException%601> с параметром типа <xref:System.String?displayProperty=fullName>, значение строки присваивается свойству <xref:System.ServiceModel.FaultException%601.Detail%2A?displayProperty=fullName> и недоступно в свойстве <xref:System.ServiceModel.FaultException%601.ToString%2A?displayProperty=fullName>.  
  
## Обработка ошибок  
 В клиентах [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] ошибки SOAP, возникающие при передаче данных и относящиеся к клиентским приложениям, выдаются в виде управляемых исключений.Во время выполнения любой программы возникает множество исключений, однако можно ожидать, что в результате передачи данных приложения, использующие модель программирования клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], будут обрабатывать исключения двух следующих типов.  
  
-   <xref:System.TimeoutException>  
  
-   <xref:System.ServiceModel.CommunicationException>  
  
 Объекты <xref:System.TimeoutException> выдаются по истечении заданного времени ожидания.  
  
 Объекты <xref:System.ServiceModel.CommunicationException> выдаются в случае возникновения устранимой ошибки передачи данных в службе или клиенте.  
  
 Класс <xref:System.ServiceModel.CommunicationException> имеет два важных производных типа, <xref:System.ServiceModel.FaultException> и универсальный тип <xref:System.ServiceModel.FaultException%601>.  
  
 Исключения <xref:System.ServiceModel.FaultException> выдаются, когда прослушиватель получает неожиданную или не указанную в контракте операции ошибку. Обычно это происходит во время отладки приложения, когда свойству <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=fullName> службы присвоено значение `true`.  
  
 Исключения <xref:System.ServiceModel.FaultException%601> выдаются в клиенте при получении ошибки, указанной в контракте операции, в ответ на двустороннюю операцию \(т.е. метод с атрибутом <xref:System.ServiceModel.OperationContractAttribute>, у которого свойству <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> присвоено значение `false`\).  
  
> [!NOTE]
>  Когда служба [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] имеет свойство <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=fullName> или <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=fullName> со значением `true`, клиент получает необъявленное исключение <xref:System.ServiceModel.FaultException%601>, принадлежащее типу <xref:System.ServiceModel.ExceptionDetail>.Клиенты могут либо перехватить эту определенную ошибку, либо обработать ее в блоке catch для <xref:System.ServiceModel.FaultException>.  
  
 Как правило, только исключения <xref:System.ServiceModel.FaultException%601>, <xref:System.TimeoutException> и <xref:System.ServiceModel.CommunicationException> представляют интерес для клиентов и служб.  
  
> [!NOTE]
>  Конечно, возникают и другие исключения.К неожиданным исключениям относятся неустранимые ошибки, например <xref:System.OutOfMemoryException?displayProperty=fullName>. Как правило, приложения не должны перехватывать такие методы.  
  
### Перехват исключений ошибок в правильном порядке  
 Поскольку класс <xref:System.ServiceModel.FaultException%601> является производным класса <xref:System.ServiceModel.FaultException>, а класс <xref:System.ServiceModel.FaultException> является производным класса <xref:System.ServiceModel.CommunicationException>, важно перехватывать эти исключения в нужном порядке.Например, если в блоке try\/catch сначала перехватывается исключение <xref:System.ServiceModel.CommunicationException>, обработка всех объявленных и необъявленных ошибок SOAP будет выполняться в этом блоке. Все последующие блоки catch, предназначенные для обработки пользовательского исключения <xref:System.ServiceModel.FaultException%601>, не вызываются никогда.  
  
 Помните, что одна операция может возвращать любое количество объявленных ошибок.Каждая ошибка имеет уникальный тип и должна обрабатываться отдельно.  
  
### Обработка исключений при закрытии канала  
 Большая часть вышесказанного касалась ошибок, отправляемых в процессе обработки сообщений приложения, т.е. сообщений, явно отправляемых клиентом, когда клиентское приложение вызывает операции с объектом клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
 Даже при удалении локального объекта могут быть созданы или скрыты исключения, возникающие в процессе перезапуска.Аналогичная ситуация может иногда возникать при работе с объектами клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].При вызове операций сообщения передаются по установленному подключению.Закрытие канала может приводить к исключениям, если не удается аккуратно закрыть подключение или если оно уже закрыто, даже при надлежащем возврате всех операций.  
  
 Как правило, каналы объекта клиента закрываются одним из следующих способов.  
  
-   При перезапуске объекта клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
-   При вызове метода <xref:System.ServiceModel.ClientBase%601.Close%2A?displayProperty=fullName> клиентским приложением.  
  
-   При вызове метода <xref:System.ServiceModel.ICommunicationObject.Close%2A?displayProperty=fullName> клиентским приложением.  
  
-   При вызове клиентским приложением операции, которая является завершающей операцией сеанса.  
  
 Во всех случаях при закрытии канал получает указания начать закрытие всех базовых каналов, которые могут отправлять сообщения для поддержки сложных функций на уровне приложения.Например, если контракту требуются сеансы, привязка предпринимает попытки установить сеанс путем обмена сообщениями с каналом службы до тех пор, пока сеанс не будет установлен.После закрытия канала базовый канал сеанса уведомляет службу о прерывании сеанса.Если канал уже был прерван, закрыт или иным образом стал непригодным \(например, при отключении сетевого кабеля\), канал клиента не может уведомить канал службы о прекращении сеанса и возможном исключении.  
  
### Прерывание работы канала при необходимости  
 Поскольку при закрытии канала также могут создаваться исключения, рекомендуется в дополнение к перехвату исключений ошибок в правильном порядке прерывать канал, использованный в вызове, в блоке catch.  
  
 Если ошибка содержит сведения об ошибке, касающиеся операции, и существует возможность использования ее другими объектами, прерывать канал не требуется \(такие случаи являются редкими\).Во всех остальных случаях рекомендуется прерывать канал.Пример, демонстрирующий все эти моменты, см. в разделе [Ожидаемые исключения](../../../docs/framework/wcf/samples/expected-exceptions.md).  
  
 В следующем примере кода демонстрируется обработка исключений ошибок SOAP в простом клиентском приложении, в том числе объявленных и необъявленных ошибок.  
  
> [!NOTE]
>  В этом примере кода не используется конструкция `using`.При закрытии каналов могут создаваться исключения, поэтому рекомендуется в приложениях сначала создать клиент [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], а затем открыть, использовать и закрыть клиент [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] в одном блоке try.Дополнительные сведения см. в разделах [Общие сведения о клиентах WCF](../../../docs/framework/wcf/wcf-client-overview.md) и [Предотвращение проблем при использовании операторов](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md).  
  
 [!code-csharp[FaultContractAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/client.cs#3)]
 [!code-vb[FaultContractAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/client.vb#3)]  
  
## См. также  
 <xref:System.ServiceModel.FaultException>   
 <xref:System.ServiceModel.FaultException%601>   
 <xref:System.ServiceModel.CommunicationException?displayProperty=fullName>   
 [Ожидаемые исключения](../../../docs/framework/wcf/samples/expected-exceptions.md)   
 [Предотвращение проблем при использовании операторов](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)