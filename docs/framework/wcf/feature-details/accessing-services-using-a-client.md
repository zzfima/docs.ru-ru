---
title: "Обращение к службам с использованием клиента | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c8329832-bf66-4064-9034-bf39f153fc2d
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Обращение к службам с использованием клиента
Клиентские приложения должны создавать, настраивать и использовать клиент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] или объекты канала для связи со службами.  В разделе [Общие сведения о клиентах WCF](../../../../docs/framework/wcf/wcf-client-overview.md) описаны объекты и этапы создания основного клиента и объектов канала, а также их использование.  
  
 В разделе приводится подробная информация о некоторых проблемах с приложениями клиента и объектами клиента и канала, которые могут пригодиться в зависимости от вашего сценария.  
  
## Обзор  
 В разделе описаны поведение и проблемы, связанные со следующими пунктами.  
  
-   Каналы и время существования сеанса.  
  
-   Обработка исключений.  
  
-   Понимание блокирующих проблем.  
  
-   Интерактивная инициализация каналов.  
  
### Каналы и время существования сеанса  
 Приложения [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] включают две категории каналов: датаграмма и сеанс.  
  
 Канал *датаграммы* \- это канал, в котором все сообщения являются некоррелированными.  При использовании канала датаграммы на последующую операцию обычно не влияет то, что операция ввода или вывода не удалась, и тот же канал может быть использован повторно.  По этой причине в каналах датаграмм обычно не возникает сбоев.  
  
 Каналы *сеанса*, однако, являются каналами с подключением к другой конечной точке.  Сообщения в сессии всегда коррелируют с таким же сеансом с другой стороны.  Кроме того, между участниками сеанса должно быть соглашение, описывающее требования к их диалогу, которые, для того чтобы сеанс считался успешным, должны быть удовлетворены.  Если такого соглашения между участниками нет, в канале сеанса может возникнуть ошибка.  
  
 Откройте клиенты явно или неявно, вызвав первую операцию.  
  
> [!NOTE]
>  Попытка явно обнаружить каналы сеанса со сбоем обычно оказывается полезной, поскольку то, когда вы будете оповещены, зависит от реализации сеанса.  Например, поскольку <xref:System.ServiceModel.NetTcpBinding?displayProperty=fullName> \(с отключенным надежным сеансом\) покрывает сеанс связи TCP, если при ожидании передачи данных события <xref:System.ServiceModel.ICommunicationObject.Faulted?displayProperty=fullName> службы или клиента, желательно получить уведомление о сбое сети незамедлительно.  Но надежные сеансы \(установленные привязками, в которых включен <xref:System.ServiceModel.Channels.ReliableSessionBindingElement?displayProperty=fullName>\) предназначены для изолирования служб от незначительных сбоев сети.  Если сеанс может быть повторно установлен в течение допустимого периода времени, та же привязка, настроенная для надежных сеансов, может не дать сбой, пока прерывание не будет происходить в течение более продолжительного промежутка времени.  
  
 Большинство предоставляемых системой привязок \(экспонирующих каналы на уровень приложения\) использует сеансы по умолчанию, однако <xref:System.ServiceModel.BasicHttpBinding?displayProperty=fullName> этого не делает.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Использование сеансов](../../../../docs/framework/wcf/using-sessions.md).  
  
### Правильное использование сеансов  
 Сеансы являются способом, с помощью которого можно узнать, полностью ли был завершен обмен сообщением и обе ли стороны считают его успешным.  Рекомендуется, чтобы вызывающее приложение открыло канал, использовало его и закрыло канал внутри одного блока try.  Если канал сеанса открыт и однократно вызван метод <xref:System.ServiceModel.ICommunicationObject.Close%2A?displayProperty=fullName>, и данный вызов успешно возвращается, значит сеанс был успешен.  "Успешный" в данном случае означает, что все гарантии доставки, заданные привязкой, были обеспечены и другая сторона не вызвала <xref:System.ServiceModel.ICommunicationObject.Abort%2A?displayProperty=fullName> в канале перед вызовом <xref:System.ServiceModel.ICommunicationObject.Close%2A>.  
  
 В следующем разделе показан пример данного подхода к клиенту.  
  
### Обработка исключений  
 Обработка исключений в приложениях клиента является прямой.  Если канал открыт, использован и закрыт внутри одного блока try, диалог был успешен, кроме случая, если было выдано исключение.  Обычно при выдаче исключения диалог прерывается.  
  
> [!NOTE]
>  Использование оператора `using` \(`Using` в [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]\) не рекомендуется.  Это связано с тем, что конец оператора `using` может привести к исключениям, которые могут маскировать другие исключения, о которых вам, возможно, нужно знать.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Предотвращение проблем при использовании операторов](../../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md).  
  
 В приведенном ниже примере кода демонстрируется рекомендуемый шаблон клиента с помощью блока try\/catch, а не с помощью оператора `using`.  
  
 [!code-csharp[FaultContractAttribute#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/client.cs#3)]
 [!code-vb[FaultContractAttribute#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/client.vb#3)]  
  
> [!NOTE]
>  Проверка значения свойства <xref:System.ServiceModel.ICommunicationObject.State%2A?displayProperty=fullName> является состоянием гонки и не рекомендуется для определения ситуации, когда канал можно использовать повторно или когда его нужно закрыть.  
  
 Каналы датаграммы не дают сбой, даже если исключения происходят при их закрытии.  Кроме того, недуплексные клиенты, которые не смогли пройти проверку с помощью защищенного диалога, как правило, создают исключение <xref:System.ServiceModel.Security.MessageSecurityException?displayProperty=fullName>.  Однако если дуплексному клиенту, использующему защищенный диалог, не удается пройти проверку, клиент получает вместо этого исключение <xref:System.TimeoutException?displayProperty=fullName>.  
  
 Дополнительные сведения о работе с информацией об ошибке на уровне приложения см. в разделе [Задание и обработка сбоев в контрактах и службах](../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).  В разделе [Ожидаемые исключения](../../../../docs/framework/wcf/samples/expected-exceptions.md) описаны ожидаемые исключения и показано, как обрабатывать их.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] обработке ошибок при разработке каналов см. в разделе [Обработка исключений и сбоев](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md).  
  
### Блокировка и производительность клиента  
 Когда приложение синхронно вызывает операцию типа запрос\-ответ, клиент блокируется до тех пор, пока не будет получено возвращаемое значение или создано исключение \(такое как <xref:System.TimeoutException?displayProperty=fullName>\).  Такое поведение аналогично локальному поведению.  Когда приложение синхронно вызывает операцию объекта клиента или канала [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], клиент ничего не возвращает до тех пор, пока уровень канала сможет записать данные в сеть или до тех пор, пока не будет создано исключение.  И до тех пор, пока шаблон одностороннего обмена сообщениями \(заданный маркировкой операции с помощью <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A?displayProperty=fullName>, которому присвоено значение `true`\) повышает реакцию некоторых клиентов, односторонние операции также блокируются, в зависимости от привязки и того, какие сообщения уже были отправлены.  Односторонние операции относятся только к обмену сообщениями, не больше и не меньше.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Односторонние службы](../../../../docs/framework/wcf/feature-details/one-way-services.md).  
  
 Большие порции данных могут замедлить обработку клиента, независимо от шаблона обмена сообщениями.  Чтобы понять, как работать с данными проблемами, см. [Большие наборы данных и потоковая передача](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md).  
  
 Если ваше приложение должно выполнять больше работы при завершении операции, необходимо создать пару асинхронных методов интерфейса контракта службы, которую реализует клиент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  Самым простым способом сделать это является использование параметра `/async` в [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  Пример см. в разделе [Как асинхронно вызывать операции службы](../../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] увеличении производительности клиента см. [Клиентские приложения среднего уровня](../../../../docs/framework/wcf/feature-details/middle-tier-client-applications.md).  
  
### Включение динамического выбора учетных данных пользователем  
 Интерфейс <xref:System.ServiceModel.Dispatcher.IInteractiveChannelInitializer> позволяет приложениям отображать интерфейс пользователя, что позволяет пользователю выбирать учетные данные пользователя с которыми канал создается до того, как запустятся таймеры периода времени.  
  
 Разработчики приложений могут использовать вставленный <xref:System.ServiceModel.Dispatcher.IInteractiveChannelInitializer> двумя способами.  Приложение клиента может вызвать либо метод <xref:System.ServiceModel.ClientBase%601.DisplayInitializationUI%2A?displayProperty=fullName>, либо метод <xref:System.ServiceModel.IClientChannel.DisplayInitializationUI%2A?displayProperty=fullName> \(или асинхронную версию\) до открытия канала \(*явный* подход\), либо просто вызвать первую операцию \(*неявный* подход\).  
  
 Если использовать неявный подход, то приложение должно вызвать первую операцию в расширении <xref:System.ServiceModel.ClientBase%601> или <xref:System.ServiceModel.IClientChannel>.  Если приложение вызовет что\-либо другое вместо первой операции, будет создано исключение.  
  
 Если использовать явный подход, то приложение должно выполнить следующие шаги по порядку:  
  
1.  Вызывать либо <xref:System.ServiceModel.ClientBase%601.DisplayInitializationUI%2A?displayProperty=fullName>, либо <xref:System.ServiceModel.IClientChannel.DisplayInitializationUI%2A?displayProperty=fullName> \(или асинхронную версию\).  
  
2.  После возвращения инициализаторов вызвать либо метод <xref:System.ServiceModel.ICommunicationObject.Open%2A> в объекте <xref:System.ServiceModel.IClientChannel>, либо в объекте <xref:System.ServiceModel.IClientChannel>, возвращенном из свойства <xref:System.ServiceModel.ClientBase%601.InnerChannel%2A?displayProperty=fullName>.  
  
3.  Вызовите операции.  
  
 Рекомендуется, чтобы приложения для промышленного применения управляли процессом пользовательского интерфейса в соответствии с явным подходом.  
  
 Приложения, использующие неявный подход, вызывают инициализаторы интерфейса пользователя, но если пользователь приложения не сможет ответить в отведенный период времени привязки для отправки, то при возвращении пользовательского интерфейса создается исключение.  
  
## См. также  
 [Дуплексные службы](../../../../docs/framework/wcf/feature-details/duplex-services.md)   
 [Практическое руководство. Доступ к службам с односторонним контрактом и контрактом типа «запрос\-ответ»](../../../../docs/framework/wcf/feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md)   
 [Практическое руководство. Доступ к службам с дуплексным контрактом](../../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)   
 [Как обращаться к службе WSE 3.0](../../../../docs/framework/wcf/feature-details/how-to-access-a-wse-3-0-service-with-a-wcf-client.md)   
 [Практическое руководство. Использование ChannelFactory](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)   
 [Как асинхронно вызывать операции службы](../../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md)   
 [Клиентские приложения среднего уровня](../../../../docs/framework/wcf/feature-details/middle-tier-client-applications.md)