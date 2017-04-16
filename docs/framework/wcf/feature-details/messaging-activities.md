---
title: "Действия обмена сообщениями | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8498f215-1823-4aba-a6e1-391407f8c273
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# Действия обмена сообщениями
Действия обмена сообщениями позволяют рабочим процессам отправлять или получать сообщения WCF.Добавляя действия обмена сообщениями в рабочий процесс, можно моделировать шаблоны обмена сообщениями любого уровня сложности.  
  
## Шаблоны обмена сообщениями  
 Существует три основных шаблона обмена сообщениями.  
  
-   **Датаграмма** — при использовании шаблона обмена сообщениями «датаграмма», клиент отправляет сообщение службе, но служба не отвечает.Такой метод иногда называют «отправить и забыть».В этом случае требуется внешнее подтверждение успешной доставки.Сообщение может быть потеряно при передаче и может не достичь службы.Если клиент успешно отправил сообщение, это не гарантирует, что удаленная служба получила его.Датаграмма — это фундаментальный элемент обмена сообщениями, на основе которого можно строить собственные шаблоны обмена сообщениями.  
  
-   **Запрос\-ответ** — при использовании шаблона обмена сообщениями «запрос\-ответ» клиент отправляет сообщение службе, служба выполняет необходимые вычисления и отправляет ответ клиенту.Шаблон состоит из пар "запрос\-ответ".Примерами вызовов "запрос\-ответ" являются удаленные вызовы процедур \(RPC\) и запросы GET браузера.Этот шаблон также называют полудуплексным.  
  
-   **Дуплекс** — при использовании шаблона обмена сообщения «дуплекс» клиент и служба могут отправлять сообщения друг другу в любом порядке.Применение дуплексного шаблона похоже на разговор по телефону, когда каждое произносимое слово является сообщением.  
  
 Действия обмена сообщениями позволяют реализовать любой из этих базовых шаблонов обмена сообщениями, а также любые другие шаблоны обмена сообщениями любого уровня сложности.  
  
## Действия обмена сообщениями  
 Платформа [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] определяет следующие действия обмена сообщениями.  
  
-   <xref:System.ServiceModel.Activities.Send> — используется для отправки сообщения.  
  
-   <xref:System.ServiceModel.Activities.SendReply> — используется для отправки ответа на полученное сообщение.Это действие используется службами рабочего процесса при реализации шаблона обмена сообщениями «запрос\-ответ».  
  
-   <xref:System.ServiceModel.Activities.Receive> — используется для получения сообщения.  
  
-   <xref:System.ServiceModel.Activities.ReceiveReply> — используется для получения ответного сообщения.Это действие используется клиентами службы рабочего процесса при реализации шаблона обмена сообщениями «запрос\-ответ».  
  
## Действия обмена сообщениями и шаблоны обмена сообщениями  
 В шаблоне обмена сообщениями «датаграмма» участвуют клиент, отправляющий сообщение, и служба, получающая его.Если клиент — это рабочий процесс, то следует использовать действие <xref:System.ServiceModel.Activities.Send> для отправки сообщения.Для получения этого сообщения в рабочем процессе следует использовать действие <xref:System.ServiceModel.Activities.Receive>.Действия <xref:System.ServiceModel.Activities.Send> и <xref:System.ServiceModel.Activities.Receive> имеют свойство с именем `Content`.Это свойство содержит отправляемые или получаемые данные.При реализации шаблона обмена сообщениями «запрос\-ответ» клиент и службы используют пары действий.Клиент использует действие <xref:System.ServiceModel.Activities.Send> для отправки сообщения и действие <xref:System.ServiceModel.Activities.ReceiveReply> для получения ответа от службы.Эти два действия связаны друг с другом свойством <xref:System.ServiceModel.Activities.ReceiveReply.Request%2A>.Значение этого свойства — действие <xref:System.ServiceModel.Activities.Send>, отправившее исходное сообщение.Служба также использует пару связанных действий: <xref:System.ServiceModel.Activities.Receive> и <xref:System.ServiceModel.Activities.SendReply>.Эти два действия связаны свойством <xref:System.ServiceModel.Activities.SendReply.Request%2A>.Значение этого свойства — действие <xref:System.ServiceModel.Activities.Receive>, получившее исходное сообщение.Действия <xref:System.ServiceModel.Activities.ReceiveReply> и <xref:System.ServiceModel.Activities.SendReply>, как и действия <xref:System.ServiceModel.Activities.Send> и <xref:System.ServiceModel.Activities.Receive>, позволяют отправить экземпляр <xref:System.ServiceModel.Channels.Message> или тип контракта сообщения.  
  
 Поскольку рабочие процессы выполняются в течение долгого времени, очень важно, чтобы шаблон обмена сообщениями «дуплекс» также поддерживал долговременные диалоги.Для поддержки долговременных диалогов клиенты, инициирующие диалоги, должны предоставлять службу с возможностью ее повторного вызова позднее, когда данные станут доступны.Например, заказ на покупку подается на одобрение менеджера, но он может быть обработан спустя день, неделю или даже год; рабочий процесс, управляющий заказом на покупку должен иметь возможность продолжить работу с ним после получения одобрения.Шаблон обмена сообщениями «дуплекс» поддерживается в рабочих процессах, использующих корреляцию.Для реализации шаблона «дуплекс» следует использовать действия <xref:System.ServiceModel.Activities.Send> и <xref:System.ServiceModel.Activities.Receive>.В действии <xref:System.ServiceModel.Activities.Receive> следует инициализировать корреляцию с использованием значения специального ключа <xref:System.ServiceModel.Activities.CorrelationHandle.CallbackHandleName%2A>.В действии <xref:System.ServiceModel.Activities.Send> задайте дескриптор взаимосвязи как значение свойства <xref:System.ServiceModel.Activities.Send.CorrelatesWith%2A>.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Сохраняемый дуплекс](../../../../docs/framework/wcf/feature-details/durable-duplex-correlation.md).  
  
> [!NOTE]
>  Реализация шаблона «дуплекс» в рабочем процессе с использованием корреляции обратного вызова \(«устойчивый дуплекс»\) предназначена для работы с долговременными диалогами.Это не то же самое, что «дуплекс» WCF с контрактами обратного вызова, в которых диалоги являются кратковременными \(на время существования канала\).  
  
## Форматирование сообщений и действия обмена сообщениями  
 Действия <xref:System.ServiceModel.Activities.Receive> и <xref:System.ServiceModel.Activities.ReceiveReply> имеют свойство с именем `Content`.Это свойство имеет тип <xref:System.ServiceModel.Activities.ReceiveContent> и представляет данные, получаемые действием <xref:System.ServiceModel.Activities.Receive> или <xref:System.ServiceModel.Activities.ReceiveReply>.В платформе .NET Framework определены два связанных класса с именами <xref:System.ServiceModel.Activities.RecieveMessageContent> и <xref:System.ServiceModel.Activities.ReceiveParametersContent>, которые являются производными от <xref:System.ServiceModel.Activities.ReceiveContent>.Задайте для свойства `Content` действия <xref:System.ServiceModel.Activities.Receive> или <xref:System.ServiceModel.Activities.ReceiveReply> значение экземпляра одного из этих типов для получения данных в службе рабочего процесса.Используемые типы зависят от типа данных, получаемых действием.Если действие получает объект `Message` или тип контракта сообщения, следует использовать <xref:System.ServiceModel.Activities.ReceiveMessageContent>.Если действие получает контракт набора данных или типы XML, которые могут быть сериализованы, используйте <xref:System.ServiceModel.Activities.ReceiveParametersContent>.<xref:System.ServiceModel.Activities.ReceiveParametersContent> позволяет отправлять несколько параметров, <xref:System.ServiceModel.Activities.ReceiveMessageContent> позволяет отправлять только один объект — сообщение \(или тип контракта сообщения\).  
  
> [!NOTE]
>  <xref:System.ServiceModel.Activities.ReceiveMessageContent> также можно использовать с одним контрактом данных или типом XML, который может быть сериализован.Разница между использованием класса <xref:System.ServiceModel.Activities.ReceiveParametersContent> с одним параметром и передачей объекта напрямую классу <xref:System.ServiceModel.Activities.RecieveMessageContent> заключается в формате сообщений.Содержимое параметра упаковывается в элемент XML, соответствующий имени операции, а сериализуемый объект упаковывается в элемент XML с использованием имени параметра \(например, `<Echo><msg>Hello, World</msg></Echo>`\).Содержимое сообщения не упаковывается в имя операции.Вместо этого сериализуемый объект размещается в элементе XML с использованием полного имени типа XML \(например, `<string>Hello, World</string>`\).  
  
 Действия <xref:System.ServiceModel.Activities.Send> и <xref:System.ServiceModel.Activities.SendReply> также имеют свойство с именем `Content`.Это свойство имеет тип <xref:System.ServiceModel.Activities.SendContent> и представляет данные, отправляемые действием <xref:System.ServiceModel.Activities.Send> или <xref:System.ServiceModel.Activities.SendReply>.В платформе .NET Framework определены два связанных типа с именами <xref:System.ServiceModel.Activities.SendMessageContent> и <xref:System.ServiceModel.Activities.SendParametersContent>, которые являются производными от <xref:System.ServiceModel.Activities.SendContent>.Задайте для свойства `Content` действия <xref:System.ServiceModel.Activities.Send> или <xref:System.ServiceModel.Activities.SendReply> значение экземпляра одного из этих типов для отправки данных из службы рабочего процесса.Используемые типы зависят от типа данных, отправляемых действием.Если действие отправляет объект `Message` или тип контракта сообщения, следует использовать <xref:System.ServiceModel.Activities.SendMessageContent>.Если действие отправляет тип контракта, используйте <xref:System.ServiceModel.Activities.SendParametersContent>.<xref:System.ServiceModel.Activities.SendParametersContent> позволяет отправлять несколько параметров, тогда как <xref:System.ServiceModel.Activities.SendMessageContent> позволяет отправлять только один объект — сообщение \(или тип контракта сообщения\).  
  
 При императивном программировании действий обмена сообщениями следует использовать универсальные аргументы <xref:System.ServiceModel.Activities.InArgument%601> и <xref:System.ServiceModel.Activities.OutArgument%601> для упаковки объектов, назначенных для сообщения или свойств параметров для действий <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, <xref:System.ServiceModel.Activities.Receive> и <xref:System.ServiceModel.Activities.ReceiveReply>.Используйте <xref:System.ServiceModel.Activities.InArgument%601> для действий <xref:System.ServiceModel.Activities.Send> и <xref:System.ServiceModel.Activities.SendReply> — для действий <xref:System.ServiceModel.Activities.OutArgument%601><xref:System.ServiceModel.Activities.Receive>, и <xref:System.ServiceModel.Activities.ReceiveReply>.Аргументы `In` используются с действиями по отправлению сообщений, поскольку в действия передаются данные.Аргументы `Out` используются с действиями по получению сообщений, поскольку данные принимаются от действий, как показано в следующем примере.  
  
```  
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
  
 При реализации службы рабочего процесса, определяющей операцию «запрос\-ответ», возвращающую пустое значение, необходимо создать экземпляр действия <xref:System.ServiceModel.Activities.SendReply> и задать для свойства <xref:System.ServiceModel.Activities.SendReply.Content%2A> значение пустого экземпляра одного из типов содержимого \(<xref:System.ServiceModel.Activities.SendMesageContent> или <xref:System.ServiceModel.Activities.SendParametersContent>\), как это показано в следующем примере.  
  
```  
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
  
## Добавление ссылки на службу  
 При вызове службы рабочего процесса в приложении рабочего процесса среда [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] создает пользовательские действия обмена сообщениями, которые инкапсулируют обычные действия <xref:System.ServiceModel.Activities.Send> и <xref:System.ServiceModel.Activities.ReceiveReply>, используемые в шаблоне обмена сообщениями «запрос\-ответ».Для использовании этой функции щелкните правой кнопкой мыши клиентский проект в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] и выберите **Добавить ссылку на службу**.Введите базовый адрес службы в поле адреса и щелкните «Перейти».Доступные службы отображаются в поле **Службы:**.Разверните узел службы для отображения поддерживаемых контрактов.Выберите контракт, который следует вызвать, и в поле **Операции** будет отображен список доступных операций.Затем можно указать пространство имен для создаваемого действия и нажать кнопку **ОК**.Появится диалоговое окно с сообщением, что операция была завершена успешно, а созданные пользовательские действия появятся в области элементов после повторного построения проекта.Для каждой операции, определенной в контракте службы, существует одно действие.После повторного построения проекта пользователь сможет перетаскивать пользовательские действия в рабочий процесс и задавать любые необходимые свойства в окне свойств.  
  
## Шаблоны действий обмена сообщениями  
 Для упрощения настройки шаблона обмена «запрос\-ответ» MEP на клиенте и сервере [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] предоставляет два шаблона обмена сообщениями.<xref:System.ServiceModel.Activities.Design.ReceiveAndSendReply> используется в службе, и <xref:System.ServiceModel.Activities.Design.SendAndReceiveReply> используется на клиенте.В обоих случаях шаблоны добавят соответствующие действия обмена сообщениями в рабочий процесс.Для службы шаблон <xref:System.ServiceModel.Activities.Design.ReceiveAndSendReply> добавит действие <xref:System.ServiceModel.Activities.Receive>, за которым следует действие <xref:System.ServiceModel.Activities.SendReply>.Свойство <xref:System.ServiceModel.Activities.SendReply.Request> автоматически задается для действия <xref:System.ServiceModel.Activities.Receive>.Для клиента шаблон <xref:System.ServiceModel.Activities.Design.SendAndReceiveReply> добавит действие <xref:System.ServiceModel.Activities.Send>, за которым следует действие <xref:System.ServiceModel.Activities.ReceiveReply>.Свойство <xref:System.ServiceModel.Activities.ReceiveReply.Request%2A> автоматически задается для действия <xref:System.ServiceModel.Activities.Send>.Чтобы использовать эти шаблоны, перетащите соответствующий шаблон в рабочий процесс.  
  
## Действия обмена сообщениями и транзакции  
 При вызове службы рабочего процесса может быть полезно выделить для операции службы транзакцию.Чтобы сделать это, поместите действие <xref:System.ServiceModel.Activities.Receive> в действие <xref:System.ServiceModel.Activities.TransactedReceiveScope>.Действие <xref:System.ServiceModel.Activities.TransactedReceiveScope> содержит действие `Receive` и текст.Транзакция, выделяемая службе, остается внешней в течение выполнения текста <xref:System.ServiceModel.Activities.TransactedReceiveScope>.Транзакция завершает работу, когда завершается выполнение основной части.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] о рабочих процессах и транзакциях см. в разделе [Транзакции рабочих процессов](../../../../docs/framework/windows-workflow-foundation//workflow-transactions.md).  
  
## См. также  
 [Отправка и получение ошибок в службах рабочих процессов](http://go.microsoft.com/fwlink/?LinkId=189151)   
 [Создание службы долго выполняющегося рабочего процесса](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md)