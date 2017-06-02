---
title: "Создание службы долго выполняющегося рабочего процесса | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4c39bd04-5b8a-4562-a343-2c63c2821345
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Создание службы долго выполняющегося рабочего процесса
В данном разделе описывается, как создать службу длительных рабочих процессов.  Службы длительных рабочих процессов могут работать в течение долгого времени.  В определенные моменты рабочий процесс может переходить в состояние бездействия в ожидании дополнительных данных.  В этом случае рабочий процесс сохраняется в базе данных SQL и удаляется из памяти.  При поступлении дополнительных данных экземпляр рабочего процесса снова загружается в память и его выполнение продолжается.  В этом сценарии реализуется очень упрощенная система обработки заказов.  Клиент отправляет первоначальное сообщение службе рабочего процесса с указанием начать заказ.  Служба возвращает клиенту идентификатор заказа.  С этого момента в ожидании нового сообщения от клиента служба рабочего процесса переходит в состояние бездействия и сохраняется в базе данных SQL Server.  Когда клиент отправит следующее сообщение, чтобы заказать товар, служба рабочего процесса будет снова загружена в память, после чего она завершит обработку заказа.  В приведенном образце кода служба возвращает строку, указывающую на то, что товар добавлен в заказ.  Этот образец кода не предполагает реализацию такого приложения в реальности, скорее это простой образец, иллюстрирующий работу служб длительных рабочих процессов. Предполагается, что читатели этого раздела знают, как создавать проекты и решения [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
## Обязательные компоненты  
 Чтобы воспользоваться этим пошаговым руководством, необходимо установить следующее программное обеспечение:  
  
1.  Microsoft SQL Server 2008  
  
2.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]  
  
3.  Microsoft [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]  
  
4.  Требуются знания служб WCF, среды [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] и навыки создания проектов и решений.  
  
### Настройка базы данных SQL  
  
1.  Для сохранения экземпляров служб рабочих процессов требуется установленный Microsoft SQL Server, на котором необходимо настроить базу данных для хранения выгруженных из памяти экземпляров рабочих процессов.  Запустите среду Microsoft SQL Management Studio, для этого нажмите кнопку **Пуск** и последовательно выберите **Все программы**, **Microsoft SQL Server 2008** и **Microsoft SQL Management Studio**.  
  
2.  Нажмите кнопку **Подключить**, чтобы войти на экземпляр SQL Server.  
  
3.  В древовидном представлении щелкните правой кнопкой мыши **Базы данных** и выберите команду **Создать базу данных...**, чтобы создать новую базу данных с именем `SQLPersistenceStore`.  
  
4.  Выполните в базе данных SQLPersistenceStore файл скрипта SqlWorkflowInstanceStoreSchema.sql, расположенный в каталоге C:\\Windows\\Microsoft.NET\\Framework\\v4.0\\SQL\\en, чтобы настроить требуемые схемы базы данных.  
  
5.  Выполните в базе данных SQLPersistenceStore файл скрипта SqlWorkflowInstanceStoreLogic.sql, расположенный в каталоге C:\\Windows\\Microsoft.NET\\Framework\\v4.0\\SQL\\en, чтобы настроить требуемую логику базы данных.  
  
### Создание размещенной на веб\-узле службы рабочего процесса  
  
1.  Создайте в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] пустое решение и присвойте ему имя `OrderProcessing`.  
  
2.  Добавьте в решение новый проект приложения службы рабочего процесса [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с именем `OrderService`.  
  
3.  В диалоговом окне свойств проекта перейдите на вкладку **Веб**.  
  
    1.  В разделе **Действие при запуске** выберите **Указанная страница** и укажите `Service1.xamlx`.  
  
         ![Веб&#45;свойства проекта службы рабочего процесса](../../../../docs/framework/wcf/feature-details/media/startaction.png "StartAction")  
  
    2.  Откройте узел **Серверы** и выберите **Использовать локальный веб\-сервер IIS**.  
  
         ![Настройки локального веб&#45;сервера](../../../../docs/framework/wcf/feature-details/media/uselocalwebserver.png "UseLocalWebServer")  
  
        > [!WARNING]
        >  Чтобы установить этот параметр, необходимо запустить среду [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] в режиме администратора.  
  
         Эти шаги необходимы, чтобы настроить размещение проекта службы рабочего процесса в IIS.  
  
4.  Если файл `Service1.xamlx` еще не открыт, то откройте его и удалите существующие действия **ReceiveRequest** и **SendResponse**.  
  
5.  Выберите действие **Последовательная служба**, щелкните ссылку **Переменные** и добавьте переменные, показанные на следующем рисунке.  Эти переменные будут в дальнейшем использоваться в службе рабочего процесса.  
  
    > [!NOTE]
    >  Если в раскрывающемся списке «Тип переменной» отсутствует тип CorrelationHandle, выберите в нем **Поиск типов**.  Введите CorrelationHandle в поле **Имя типа**, выберите CorrelationHandle из списка и нажмите кнопку **ОК**.  
  
     ![Добавление переменных](../../../../docs/framework/wcf/feature-details/media/addvariables.gif "AddVariables")  
  
6.  Перетащите шаблон действия **ReceiveAndSendReply** в действие **Последовательная служба**.  Этот набор действий будет получать сообщение от клиента и возвращать ему ответ.  
  
    1.  Выберите действие **Receive** и задайте свойства, отмеченные на следующем рисунке.  
  
         ![Задание свойств действия Receive](../../../../docs/framework/wcf/feature-details/media/setreceiveproperties.png "SetReceiveProperties")  
  
         Свойство DisplayName задает имя, отображаемое для действия «Receive» в конструкторе.  Свойства ServiceContractName и OperationName задают имя контракта службы и операции, которые реализуются действием Receive.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] использовании контрактов в службах Workflow Services см. в разделе [Использование контрактов в рабочих процессах](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).  
  
    2.  Щелкните ссылку **Определить...** в действии **ReceiveStartOrder** и задайте свойства, показанные на следующем рисунке.  Обратите внимание, что переключатель установлен в положение **Параметры**, а параметр `p_customerName` привязан к переменной `customerName`.  В результате действие **Receive** настроено на получение данных и привязку этих данных к локальным переменным.  
  
         ![Задание данных, получаемых действием Receive](../../../../docs/framework/wcf/feature-details/media/setreceivecontent.png "SetReceiveContent")  
  
    3.  Выберите действие **SendReplyToReceive** и задайте свойство, отмеченное на следующем рисунке.  
  
         ![Задание свойств действия SendReply](../../../../docs/framework/wcf/feature-details/media/setreplyproperties.png "SetReplyProperties")  
  
    4.  Щелкните ссылку **Определить...** в действии **SendReplyToStartOrder** и задайте свойства, показанные на следующем рисунке.  Обратите внимание, что переключатель установлен в положение **Параметры**, а параметр `p_orderId` привязан к переменной `orderId`.  Этот параметр указывает, что действие SendReplyToStartOrder возвратит вызывающему объекту значение типа String.  
  
         ![Настройка данных содержимого действия SendReply](../../../../docs/framework/wcf/feature-details/media/setreplycontent.png "SetReplyContent")  
  
        > [!NOTE]
    5.  Перетащите действие Assign в область между действиями **Receive** и **SendReply** и задайте свойства в соответствии со следующим рисунком.  
  
         ![Добавление действия Assign](../../../../docs/framework/wcf/feature-details/media/addassign.png "AddAssign")  
  
         При этом будет создан новый идентификатор заказа, а его значение будет помещено в переменную orderId.  
  
    6.  Выберите действие **ReplyToStartOrder**.  В окне свойств нажмите кнопку с многоточием **CorrelationInitializers**.  Выберите ссылку **Добавить инициализатор**, введите `orderIdHandle` в текстовое поле «Инициализатор», выберите инициализатор корреляции запросов для типа Correlation, а в раскрывающемся списке «Запросы XPATH» выберите p\_orderId.  Эти параметры показаны на следующем рисунке.  Нажмите кнопку **ОК**.  При этом будет инициализирована новая корреляция между клиентом и этим экземпляром службы рабочего процесса.  При получении сообщения с этим идентификатором заказа оно будет направлено этому экземпляру службы рабочего процесса.  
  
         ![Добавление инициализатора корреляции](../../../../docs/framework/wcf/feature-details/media/addcorrelationinitializers.png "AddCorrelationInitializers")  
  
7.  Перетащите еще одно действие **ReceiveAndSendReply** в конец рабочего процесса \(за пределы **последовательности**, содержащей первые действия **Receive** и **SendReply**\).  Оно получит второе сообщение от клиента и ответит на него.  
  
    1.  Выберите **последовательность**, содержащую вновь добавленные действия **Receive** и **SendReply**, и нажмите кнопку **Переменные**.  Добавьте переменную, отмеченную на следующем рисунке.  
  
         ![Добавление новых переменных](../../../../docs/framework/wcf/feature-details/media/addorderitemidvariable.png "AddOrderItemIdVariable")  
  
    2.  Выберите действие **Receive** и задайте свойства, показанные на следующем рисунке.  
  
         ![Задание свойств действия Receive](../../../../docs/framework/wcf/feature-details/media/setreceiveproperties2.png "SetReceiveProperties2")  
  
    3.  Щелкните ссылку **Определить...** в действии **ReceiveAddItem** и добавьте параметры, показанные на следующем рисунке. При этом действие «Receive» будет настроено на прием двух параметров: идентификатора заказа и идентификатора заказываемого товара.  
  
         ![Задание параметров для второго Receive](../../../../docs/framework/wcf/feature-details/media/addreceive2parameters.png "AddReceive2Parameters")  
  
    4.  Нажмите кнопку с многоточием **CorrelateOn** и введите `orderIdHandle`.  В области **Запросы XPath** нажмите стрелку раскрывающегося списка и выберите `p_orderId`.  При этом будет настроена корреляция второго действия Receive.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] использовании корреляции см. в разделе [Корреляция](../../../../docs/framework/wcf/feature-details/correlation.md).  
  
         ![Задание свойства CorrelatesOn](../../../../docs/framework/wcf/feature-details/media/correlateson.png "CorrelatesOn")  
  
    5.  Перетащите действие **If** и расположите его сразу после действия **ReceiveAddItem**.  Это действие работает аналогично инструкции IF.  
  
        1.  Свойству **Condition** задайте значение `itemId==”Zune HD” (itemId=”Zune HD” for Visual Basic)`.  
  
        2.  Перетащите одно действие **Assign** в раздел **Then**, а второе \- в раздел **Else**. Задайте свойства действий **Assign**, как показано на следующем рисунке.  
  
             ![Присвоение результата вызова службы](../../../../docs/framework/wcf/feature-details/media/resultassign.png "ResultAssign")  
  
             Если условие будет иметь значение `true`, будет выполнен раздел **Then**.  Если условие будет иметь значение `false`, будет выполнен раздел **Else**.  
  
        3.  Выберите действие **SendReplyToReceive** и задайте свойство **DisplayName**, отмеченное на следующем рисунке.  
  
             ![Задание свойств действия SendReply](../../../../docs/framework/wcf/feature-details/media/setreply2properties.png "SetReply2Properties")  
  
        4.  Щелкните ссылку **Определить...** в действии **SetReplyToAddItem** и настройте его, как показано на следующем рисунке.  При этом действие **SendReplyToAddItem** будет настроено на возврат значения в переменной `orderResult`.  
  
             ![Задание привязки данных для действия SendReply](../../../../docs/framework/wcf/feature-details/media/replytoadditemcontent.gif "ReplyToAddItemContent")  
  
8.  Откройте файл web.config и добавьте в раздел \<behavior\> следующие элементы, чтобы включить сохранение рабочего процесса.  
  
    ```xml  
    <sqlWorkflowInstanceStore connectionString="Data Source=your-machine\SQLExpress;Initial Catalog=SQLPersistenceStore;Integrated Security=True;Asynchronous Processing=True" instanceEncodingOption="None" instanceCompletionAction="DeleteAll" instanceLockedExceptionAction="BasicRetry" hostLockRenewalPeriod="00:00:30" runnableInstancesDetectionPeriod="00:00:02" />  
              <workflowIdle timeToUnload="0"/>  
  
    ```  
  
    > [!WARNING]
    >  В приведенном выше фрагменте кода необходимо заменить имя узла и экземпляра SQL Server.  
  
9. Постройте решение.  
  
### Создание клиентского приложения, вызывающего службу рабочего процесса  
  
1.  Добавьте в решение новый проект консольного приложения с именем `OrderClient`.  
  
2.  Добавьте в проект `OrderClient` ссылки на следующие сборки:  
  
    1.  System.ServiceModel.dll  
  
    2.  System.ServiceModel.Activities.dll  
  
3.  Добавьте ссылку на службу рабочего процесса и укажите `OrderService` в качестве пространства имен.  
  
4.  В метод `Main()` клиентского проекта добавьте следующий код:  
  
    ```  
    static void Main(string[] args)  
    {  
       // Send initial message to start the workflow service  
       Console.WriteLine("Sending start message");  
       StartOrderClient startProxy = new StartOrderClient();  
       string orderId = startProxy.StartOrder("Kim Abercrombie");  
  
       // The workflow service is now waiting for the second message to be sent  
       Console.WriteLine("Workflow service is idle...");  
       Console.WriteLine("Press [ENTER] to send an add item message to reactivate the workflow service...");  
       Console.ReadLine();  
  
       // Send the second message  
       Console.WriteLine("Sending add item message");  
       AddItemClient addProxy = new AddItemClient();  
       AddItem item = new AddItem();  
       item.p_itemId = "Zune HD";  
       item.p_orderId = orderId;  
  
       string orderResult = addProxy.AddItem(item);  
       Console.WriteLine("Service returned: " + orderResult);  
    }  
  
    ```  
  
5.  Выполните построение решения и запустите приложение `OrderClient`.  Клиент выведет на экран следующий текст.  
  
    ```Output  
  
                  Отправка начального сообщения  
    Служба Workflow Service простаивает…  Нажмите клавишу ВВОД, чтобы отправить сообщение о добавлении элемента для повторной активации службы Workflow Service…    
    ```  
  
6.  Чтобы проверить, что служба рабочего процесса сохранена, запустите среду SQL Server Management Studio. Для этого нажмите кнопку **Пуск** и выберите **Все программы**, **Microsoft SQL Server 2008**, **SQL Server Management Studio**.  
  
    1.  В области слева раскройте узел **Базы данных**, **SQLPersistenceStore**, **Представления**, щелкните правой кнопкой мыши **System.Activities.DurableInstancing.Instances** и выберите **Выделить 1000 верхних строк**.  В области **Результаты** должен отображаться хотя бы один экземпляр.  Если во время работы возникнет исключение, в этой области могут быть указаны и другие экземпляры, оставшиеся от прошлых запусков.  Чтобы удалить существующие строки, щелкните **System.Activities.DurableInstancing.Instances** правой кнопкой мыши и выберите **Изменить 200 верхних строк**, нажмите кнопку **Выполнить**, выделите все строки в области результатов и нажмите **Удалить**.  Чтобы проверить, что в базе данных отображается экземпляр, созданный учебным приложением, перед запуском клиента удалите все записи из представления экземпляров.  После запуска клиента выполните этот запрос \(«Выделить 1000 верхних строк»\) еще раз и удостоверьтесь, что новый экземпляр добавлен.  
  
7.  Нажмите клавишу ВВОД, чтобы отправить сообщение о добавлении товара службе рабочего процесса.  Клиент выведет на экран следующий текст.  
  
    ```Output  
  
                  Отправка сообщения о добавлении элемента  
    Возвращено службой: элемент добавлен к заказу  
    Нажмите любую клавишу для продолжения.  .  .    
    ```  
  
## См. также  
 [Службы рабочего процесса](../../../../docs/framework/wcf/feature-details/workflow-services.md)