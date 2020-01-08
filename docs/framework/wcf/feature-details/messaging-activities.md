---
title: Действия обмена сообщениями
ms.date: 03/30/2017
ms.assetid: 8498f215-1823-4aba-a6e1-391407f8c273
ms.openlocfilehash: 1e65a3ead9df4103fb270911e3bbb2cc03fcfcba
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347576"
---
# <a name="messaging-activities"></a>Действия обмена сообщениями

Действия обмена сообщениями позволяют рабочим процессам отправлять или получать сообщения WCF. Добавляя действия обмена сообщениями в рабочий процесс, можно моделировать шаблоны обмена сообщениями любого уровня сложности.

## <a name="message-exchange-patterns"></a>Шаблоны обмена сообщениями

Существует три основных шаблона обмена сообщениями.

- **Датаграмма** . при использовании датаграммы MEP клиент отправляет службе сообщение, но служба не отвечает. Такой метод иногда называют «отправить и забыть». В этом случае требуется внешнее подтверждение успешной доставки. Сообщение может быть потеряно при передаче и может не достичь службы. Если клиент успешно отправил сообщение, это не гарантирует, что удаленная служба получила его. Датаграмма - это фундаментальный элемент обмена сообщениями, на основе которого можно строить собственные шаблоны обмена сообщениями.

- **Запрос-ответ** . при использовании запроса-Response MEP клиент отправляет сообщение в службу, служба выполняет необходимую обработку, а затем отправляет ответ обратно клиенту. Шаблон состоит из пар «запрос-ответ». Примерами вызовов "запрос-ответ" являются удаленные вызовы процедур (RPC) и запросы GET браузера. Этот шаблон также называют полудуплексным.

- **Дуплекс** — при использовании дуплексного MEP клиент и служба могут передавать сообщения друг другу в любом порядке. Применение дуплексного шаблона похоже на разговор по телефону, когда каждое произносимое слово является сообщением.

Действия обмена сообщениями позволяют реализовать любой из этих базовых шаблонов обмена сообщениями, а также любые другие шаблоны обмена сообщениями любого уровня сложности.

## <a name="messaging-activities"></a>Действия обмена сообщениями

Платформа [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] определяет следующие действия обмена сообщениями.

- <xref:System.ServiceModel.Activities.Send> — следует использовать <xref:System.ServiceModel.Activities.Send> для отправки сообщения.

- <xref:System.ServiceModel.Activities.SendReply> — следует использовать действие <xref:System.ServiceModel.Activities.SendReply>для отправки ответа на полученное сообщение. Это действие используется службами рабочего процесса при реализации шаблона обмена сообщениями «запрос-ответ».

- <xref:System.ServiceModel.Activities.Receive> — следует использовать действие <xref:System.ServiceModel.Activities.Receive> для получения сообщения.

- <xref:System.ServiceModel.Activities.ReceiveReply> — следует использовать действие <xref:System.ServiceModel.Activities.ReceiveReply> для получения ответного сообщения. Это действие используется клиентами службы рабочего процесса при реализации шаблона обмена сообщениями «запрос-ответ».

## <a name="messaging-activities-and-message-exchange-patterns"></a>Действия обмена сообщениями и шаблоны обмена сообщениями

В шаблоне обмена сообщениями «датаграмма» участвуют клиент, отправляющий сообщение, и служба, получающая его. Если клиент - это рабочий процесс, то следует использовать действие <xref:System.ServiceModel.Activities.Send> для отправки сообщения. Для получения этого сообщения в рабочем процессе следует использовать действие <xref:System.ServiceModel.Activities.Receive>. Действия <xref:System.ServiceModel.Activities.Send> и <xref:System.ServiceModel.Activities.Receive> имеют свойство с именем `Content`. Это свойство содержит отправляемые или получаемые данные. При реализации шаблона обмена сообщениями «запрос-ответ» клиент и службы используют пары действий. Клиент использует действие <xref:System.ServiceModel.Activities.Send> для отправки сообщения и действие <xref:System.ServiceModel.Activities.ReceiveReply> для получения ответа от службы. Эти два действия связаны друг с другом свойством <xref:System.ServiceModel.Activities.ReceiveReply.Request%2A>. Значение этого свойства - действие <xref:System.ServiceModel.Activities.Send>, отправившее исходное сообщение. Служба также использует пару связанных действий: <xref:System.ServiceModel.Activities.Receive> и <xref:System.ServiceModel.Activities.SendReply>. Эти два действия связаны свойством <xref:System.ServiceModel.Activities.SendReply.Request%2A>. Значение этого свойства - действие <xref:System.ServiceModel.Activities.Receive>, получившее исходное сообщение. Действия <xref:System.ServiceModel.Activities.ReceiveReply> и <xref:System.ServiceModel.Activities.SendReply>, как и действия <xref:System.ServiceModel.Activities.Send> и <xref:System.ServiceModel.Activities.Receive>, позволяют отправить экземпляр <xref:System.ServiceModel.Channels.Message> или тип контракта сообщения.

Поскольку рабочие процессы выполняются в течении долгого времени, очень важно, чтобы шаблон обмена сообщениями «дуплекс» также поддерживал долговременные диалоги. Для поддержки долговременных диалогов клиенты, инициирующие диалоги, должны предоставлять службу с возможностью ее повторного вызова позднее, когда данные станут доступны. Например, заказ на покупку подается на одобрение менеджера, но он может быть обработан спустя день, неделю или даже год; рабочий процесс, управляющий заказом на покупку должен иметь возможность продолжить работу с ним после получения одобрения. Шаблон обмена сообщениями «дуплекс» поддерживается в рабочих процессах, использующих корреляцию. Для реализации шаблона «дуплекс» следует использовать действия <xref:System.ServiceModel.Activities.Send> и <xref:System.ServiceModel.Activities.Receive>. В действии <xref:System.ServiceModel.Activities.Receive> инициализируйте корреляцию с помощью <xref:System.ServiceModel.Activities.CorrelationHandle>. В действии <xref:System.ServiceModel.Activities.Send> задайте дескриптор взаимосвязи как значение свойства <xref:System.ServiceModel.Activities.Send.CorrelatesWith%2A>. Дополнительные сведения см. в разделе [устойчивый дуплекс](durable-duplex-correlation.md).

> [!NOTE]
> Реализация дуплексного метода с использованием корреляции обратного вызова ("устойчивая дуплексная") предназначена для длительных диалогов. Это не то же самое, что «дуплекс» WCF с контрактами обратного вызова, в которых диалоги являются кратковременными (на время существования канала).

## <a name="message-formatting-and-messaging-activities"></a>Форматирование сообщений и действия по обмену сообщениями

Действия <xref:System.ServiceModel.Activities.Receive> и <xref:System.ServiceModel.Activities.ReceiveReply> имеют свойство с именем `Content`. Это свойство имеет тип <xref:System.ServiceModel.Activities.ReceiveContent> и представляет данные, получаемые действием <xref:System.ServiceModel.Activities.Receive> или <xref:System.ServiceModel.Activities.ReceiveReply>. В платформе .NET Framework определены два связанных класса с именами <xref:System.ServiceModel.Activities.ReceiveMessageContent> и <xref:System.ServiceModel.Activities.ReceiveParametersContent>, которые являются производными от <xref:System.ServiceModel.Activities.ReceiveContent>. Задайте для свойства <xref:System.ServiceModel.Activities.Receive> действия <xref:System.ServiceModel.Activities.ReceiveReply> или `Content` значение экземпляра одного из этих типов для получения данных в службе рабочего процесса. Используемые типы зависят от типа данных, получаемых действием. Если действие получает объект `Message` или тип контракта сообщения, следует использовать <xref:System.ServiceModel.Activities.ReceiveMessageContent>. Если действие получает контракт набора данных или типы XML, которые могут быть сериализованы, используйте <xref:System.ServiceModel.Activities.ReceiveParametersContent>. <xref:System.ServiceModel.Activities.ReceiveParametersContent> позволяет отправлять несколько параметров, <xref:System.ServiceModel.Activities.ReceiveMessageContent> позволяет отправлять только один объект - сообщение (или тип контракта сообщения).

> [!NOTE]
> <xref:System.ServiceModel.Activities.ReceiveMessageContent> также можно использовать с одним контрактом данных или типом XML, который может быть сериализован. Разница между использованием класса <xref:System.ServiceModel.Activities.ReceiveParametersContent> с одним параметром и передачей объекта напрямую классу <xref:System.ServiceModel.Activities.ReceiveMessageContent> заключается в формате сообщений. Содержимое параметра упаковывается в элемент XML, соответствующий имени операции, а сериализуемый объект упаковывается в элемент XML с использованием имени параметра (например, `<Echo><msg>Hello, World</msg></Echo>`). Содержимое сообщения не упаковывается в имя операции. Вместо этого сериализуемый объект размещается в элементе XML с использованием полного имени типа XML (например, `<string>Hello, World</string>`).

Действия <xref:System.ServiceModel.Activities.Send> и <xref:System.ServiceModel.Activities.SendReply> также имеют свойство с именем `Content`. Это свойство имеет тип <xref:System.ServiceModel.Activities.SendContent> и представляет данные, отправляемые действием <xref:System.ServiceModel.Activities.Send> или <xref:System.ServiceModel.Activities.SendReply>. В платформе .NET Framework определены два связанных типа с именами <xref:System.ServiceModel.Activities.SendMessageContent> и <xref:System.ServiceModel.Activities.SendParametersContent>, которые являются производными от <xref:System.ServiceModel.Activities.SendContent>. Задайте для свойства <xref:System.ServiceModel.Activities.Send> действия <xref:System.ServiceModel.Activities.SendReply> или `Content` значение экземпляра одного из этих типов для отправки данных из службы рабочего процесса. Используемые типы зависят от типа данных, отправляемых действием. Если действие отправляет объект `Message` или тип контракта сообщения, следует использовать <xref:System.ServiceModel.Activities.SendMessageContent>. Если действие отправляет тип контракта, используйте <xref:System.ServiceModel.Activities.SendParametersContent>. <xref:System.ServiceModel.Activities.SendParametersContent> позволяет отправлять несколько параметров, <xref:System.ServiceModel.Activities.SendMessageContent> позволяет отправлять только один объект - сообщение (или тип контракта сообщения).

При императивном программировании действий обмена сообщениями следует использовать универсальные аргументы <xref:System.Activities.InArgument%601> и <xref:System.Activities.OutArgument%601> для упаковки объектов, назначенных для сообщения или свойств параметров для действий <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, <xref:System.ServiceModel.Activities.Receive> и <xref:System.ServiceModel.Activities.ReceiveReply>. Используйте <xref:System.Activities.InArgument%601> для действий <xref:System.ServiceModel.Activities.Send> и <xref:System.ServiceModel.Activities.SendReply> и <xref:System.Activities.OutArgument%601> для <xref:System.ServiceModel.Activities.Receive> и <xref:System.ServiceModel.Activities.ReceiveReply> действий. С действиями по передаче сообщений используются аргументы `In`, поскольку в действия передаются данные. С действиями по получению сообщений используются аргументы `Out`, поскольку данные принимаются от действий, как показано в следующем примере.

```csharp
Receive reserveSeat = new Receive
{
    ...
    Content = new ReceiveParametersContent
    {
        Parameters =
        {
            { "ReservationInfo", new OutArgument<ReservationRequest>(reservationInfo) }
        }
    }
};
SendReply reserveSeat = new SendReply
{
    ...
    Request = reserveSeat,
    Content = new SendParametersContent
    {
        Parameters =
        {
            { "ReservationId", new InArgument<string>(reservationId) }
        }
    },
};
```

При реализации службы рабочего процесса, определяющей операцию «запрос-ответ», возвращающую пустое значение, необходимо создать экземпляр действия <xref:System.ServiceModel.Activities.SendReply> и задать для свойства <xref:System.ServiceModel.Activities.SendReply.Content%2A> значение пустого экземпляра одного из типов содержимого (<xref:System.ServiceModel.Activities.SendMessageContent> или <xref:System.ServiceModel.Activities.SendParametersContent>), как это показано в следующем примере.

```csharp
Receive rcv = new Receive()
{
ServiceContractName = "IService",
OperationName = "NullReturningContract",
Content = new ReceiveParametersContent( new Dictionary<string, OutArgument>() { { "message", new OutArgument<string>() } } )
};
SendReply sr = new SendReply()
{
Request = rcv
   Content = new SendParametersContent();
};
```

## <a name="add-service-reference"></a>Добавить ссылку на службу

При вызове службы рабочего процесса из приложения рабочего процесса Visual Studio 2012 создает настраиваемые действия обмена сообщениями, которые инкапсулируют обычные <xref:System.ServiceModel.Activities.Send> и <xref:System.ServiceModel.Activities.ReceiveReply> действия, используемые в запросе или ответе MEP. Чтобы использовать эту функцию, щелкните правой кнопкой мыши клиентский проект в Visual Studio и выберите **добавить** > **ссылку на службу**. Введите базовый адрес службы в поле адреса и щелкните «Перейти». Доступные службы отображаются в поле **Services:** . Разверните узел службы для отображения поддерживаемых контрактов. Выберите контракт, который требуется вызвать, и список доступных операций отображается в поле **операции** . Затем можно указать пространство имен для созданного действия и нажать кнопку **ОК**. Появится диалоговое окно с сообщением, что операция была завершена успешно, а созданные пользовательские действия появятся в области элементов после повторного построения проекта. Для каждой операции, определенной в контракте службы, существует одно действие. После повторного построения проекта пользователь сможет перетаскивать пользовательские действия в рабочий процесс и задавать любые необходимые свойства в окне свойств.

## <a name="messaging-activity-templates"></a>Шаблоны действий обмена сообщениями

Чтобы настроить запрос или ответ MEP на клиенте и службе проще, Visual Studio 2012 предоставляет два шаблона действий обмена сообщениями. `System.ServiceModel.Activities.Design.ReceiveAndSendReply` используется в службе, а `System.ServiceModel.Activities.Design.SendAndReceiveReply` используется на клиенте. В обоих случаях шаблоны добавят соответствующие действия обмена сообщениями в рабочий процесс. Для службы шаблон `System.ServiceModel.Activities.Design.ReceiveAndSendReply` добавит действие <xref:System.ServiceModel.Activities.Receive>, за которым следует действие <xref:System.ServiceModel.Activities.SendReply>. Свойство <xref:System.ServiceModel.Activities.SendReply.Request> автоматически задается для действия <xref:System.ServiceModel.Activities.Receive>. Для клиента шаблон `System.ServiceModel.Activities.Design.SendAndReceiveReply` добавит действие <xref:System.ServiceModel.Activities.Send>, за которым следует действие <xref:System.ServiceModel.Activities.ReceiveReply>. Свойство <xref:System.ServiceModel.Activities.ReceiveReply.Request%2A> автоматически задается для действия <xref:System.ServiceModel.Activities.Send>. Чтобы использовать эти шаблоны, перетащите соответствующий шаблон в рабочий процесс.

## <a name="messaging-activities-and-transactions"></a>Действия и транзакции обмена сообщениями

При вызове службы рабочего процесса может быть полезно выделить для операции службы транзакцию. Чтобы сделать это, поместите действие <xref:System.ServiceModel.Activities.Receive> в действие <xref:System.ServiceModel.Activities.TransactedReceiveScope>. Действие <xref:System.ServiceModel.Activities.TransactedReceiveScope> содержит действие `Receive` и текст. Транзакция, выделяемая службе, остается внешней в течение выполнения текста <xref:System.ServiceModel.Activities.TransactedReceiveScope>. Транзакция завершает работу, когда заканчивается выполнение основной части. Дополнительные сведения о рабочих процессах и транзакциях см. в разделе [транзакции рабочего процесса](../../../../docs/framework/windows-workflow-foundation/workflow-transactions.md).

## <a name="see-also"></a>См. также:

- [Как отправлять и получать ошибки в службах рабочих процессов](https://go.microsoft.com/fwlink/?LinkId=189151)
- [Создание службы долго выполняющегося рабочего процесса](creating-a-long-running-workflow-service.md)
