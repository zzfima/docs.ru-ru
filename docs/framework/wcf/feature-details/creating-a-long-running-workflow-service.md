---
title: Создание службы долго выполняющегося рабочего процесса
ms.date: 03/30/2017
ms.assetid: 4c39bd04-5b8a-4562-a343-2c63c2821345
ms.openlocfilehash: 37d3accae017b6725eab5ebb3d7df6e1bc15a56a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109659"
---
# <a name="creating-a-long-running-workflow-service"></a>Создание службы долго выполняющегося рабочего процесса
В данном разделе описывается, как создать службу длительных рабочих процессов. Службы длительных рабочих процессов могут работать в течение долгого времени. В определенные моменты рабочий процесс может переходить в состояние бездействия в ожидании дополнительных данных. В этом случае рабочий процесс сохраняется в базе данных SQL и удаляется из памяти. При поступлении дополнительных данных экземпляр рабочего процесса снова загружается в память и его выполнение продолжается.  В этом сценарии реализуется очень упрощенная система обработки заказов.  Клиент отправляет первоначальное сообщение службе рабочего процесса с указанием начать заказ. Служба возвращает клиенту идентификатор заказа. С этого момента в ожидании нового сообщения от клиента служба рабочего процесса переходит в состояние бездействия и сохраняется в базе данных SQL Server.  Когда клиент отправит следующее сообщение, чтобы заказать товар, служба рабочего процесса будет снова загружена в память, после чего она завершит обработку заказа. В приведенном образце кода служба возвращает строку, указывающую на то, что товар добавлен в заказ. Этот образец кода не предполагает реализацию такого приложения в реальности, скорее это простой образец, иллюстрирующий работу служб длительных рабочих процессов. В этом разделе предполагается, что вы умеете создавать проекты Visual Studio 2012 и решения.

## <a name="prerequisites"></a>Предварительные требования
 Чтобы воспользоваться этим пошаговым руководством, необходимо установить следующее программное обеспечение:

1.  Microsoft SQL Server 2008

2.  Visual Studio 2012

3.  Майкрософт  [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]

4.  Вы уже знакомы с WCF и Visual Studio 2012 и навыки создания проектов и решений.

### <a name="to-setup-the-sql-database"></a>Настройка базы данных SQL

1.  Для сохранения экземпляров служб рабочих процессов требуется установленный Microsoft SQL Server, на котором необходимо настроить базу данных для хранения выгруженных из памяти экземпляров рабочих процессов. Запустите Microsoft SQL Management Studio, щелкнув **запустить** кнопку, выбрав **все программы**, **Microsoft SQL Server 2008**, и **Microsoft SQL Management Studio**.

2.  Нажмите кнопку **Connect** кнопку, чтобы войти в экземпляр SQL Server

3.  Щелкните правой кнопкой мыши **баз данных** в древовидном представлении и выберите **новую базу данных...** Чтобы создать новую базу данных с именем `SQLPersistenceStore`.

4.  Выполните в базе данных SQLPersistenceStore файл скрипта SqlWorkflowInstanceStoreSchema.sql, расположенный в каталоге C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en, чтобы настроить требуемые схемы базы данных.

5.  Выполните в базе данных SQLPersistenceStore файл скрипта SqlWorkflowInstanceStoreLogic.sql, расположенный в каталоге C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en, чтобы настроить требуемую логику базы данных.

### <a name="to-create-the-web-hosted-workflow-service"></a>Создание размещенной на веб-узле службы рабочего процесса

1.  Создание пустого решения Visual Studio 2012, назовите его `OrderProcessing`.

2.  Добавьте в него новый проект служебного приложения рабочего процесса WCF под названием `OrderService`.

3.  В диалоговом окне свойств проекта выберите **Web** вкладки.

    1.  В разделе **действие при запуске** выберите **определенную страницу** и укажите `Service1.xamlx`.

         ![Веб-свойства проекта службы рабочего процесса](./media/creating-a-long-running-workflow-service/start-action-specific-page-option.png "создание размещенных на веб-службы рабочего процесса - параметр определенную страницу")

    2.  В разделе **серверы** выберите **используйте локальный веб-сервере IIS**.

         ![Параметры локального веб-сервера](./media/creating-a-long-running-workflow-service/use-local-web-server.png "создание размещенных на веб-службы рабочего процесса - параметр использовать локальный веб-сервер IIS")

        > [!WARNING]
        >  В режиме администратора, чтобы установить этот параметр, необходимо запустить Visual Studio 2012.

         Эти шаги необходимы, чтобы настроить размещение проекта службы рабочего процесса в IIS.

4.  Откройте `Service1.xamlx` Если это не уже открыт и удалите существующие **ReceiveRequest** и **SendResponse** действий.

5.  Выберите **последовательная служба** действие и нажмите кнопку **переменных** ссылку и добавьте переменные, показанные на следующем рисунке. Эти переменные будут в дальнейшем использоваться в службе рабочего процесса.

    > [!NOTE]
    >  Если в раскрывающемся списке тип переменной не является CorrelationHandle, выберите **Выбор типов** из раскрывающегося списка. Введите CorrelationHandle в **имя типа** поле, выберите CorrelationHandle из списка и нажмите кнопку **ОК**.

     ![Добавьте переменные](./media/creating-a-long-running-workflow-service/add-variables-sequential-service-activity.gif "добавьте переменные в действие последовательная служба.")

6.  Перетаскивание **ReceiveAndSendReply** шаблон действия в **последовательная служба** действия. Этот набор действий будет получать сообщение от клиента и возвращать ему ответ.

    1.  Выберите **Receive** действия и задайте свойства, отмеченные на следующем рисунке.

         ![Задайте свойства действия получения](./media/creating-a-long-running-workflow-service/set-receive-activity-properties.png "задание свойств действия Receive.")

         Свойство DisplayName задает имя, отображаемое для действия «Receive» в конструкторе. Свойства ServiceContractName и OperationName задают имя контракта службы и операции, которые реализуются действием Receive. Дополнительные сведения об использовании контрактов в службах рабочих процессов см. в разделе [использование контрактов в рабочем процессе](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).

    2.  Нажмите кнопку **определить...**  ссылку в **ReceiveStartOrder** действия и задайте свойства, показанные на следующем рисунке.  Обратите внимание, что **параметры** переключатель, параметр с именем `p_customerName` привязан к `customerName` переменной. Это позволит настроить **Receive** действия для получения некоторых данных и связать эти данные с локальных переменных.

         ![Задание данных, получаемых действием Receive](./media/creating-a-long-running-workflow-service/set-properties-for-receive-content.png "задать свойства для данных, получаемых действием Receive.")

    3.  Выберите **SendReplyToReceive** действия и задайте свойство, отмеченное на следующем рисунке.

         ![Задание свойств действия SendReply](./media/creating-a-long-running-workflow-service/set-properties-for-reply-activities.png "SetReplyProperties")

    4.  Нажмите кнопку **определить...**  ссылку в **SendReplyToStartOrder** действия и задайте свойства, показанные на следующем рисунке. Обратите внимание, что **параметры** переключатель; параметр с именем `p_orderId` привязан к `orderId` переменной. Этот параметр указывает, что действие SendReplyToStartOrder возвратит вызывающему объекту значение типа String.

         ![Настройка данных для содержимого действия SendReply](./media/creating-a-long-running-workflow-service/setreplycontent-for-sendreplytostartorder-activity.png "настройку можно SetReplyToStartOrder действия.")

    5.  Перетащите действие Assign в диапазоне от **Receive** и **SendReply** действий и задайте свойства, как показано на следующем рисунке:

         ![Добавление действия assign](./media/creating-a-long-running-workflow-service/add-an-assign-activity.png "Добавление действия assign.")

         При этом будет создан новый идентификатор заказа, а его значение будет помещено в переменную orderId.

    6.  Выберите **ReplyToStartOrder** действия. В окне свойств нажмите кнопку с многоточием для **CorrelationInitializers**. Выберите **добавить инициализатор** ссылку, введите `orderIdHandle` в текстовом поле инициализатор выберите инициализатор корреляции запросов для типа Correlation и выберите p_orderId в раскрывающемся списке запросов XPATH. Эти параметры показаны на следующем рисунке. Нажмите кнопку **ОК**.  При этом будет инициализирована новая корреляция между клиентом и этим экземпляром службы рабочего процесса. При получении сообщения с этим идентификатором заказа оно будет направлено этому экземпляру службы рабочего процесса.

         ![Добавление инициализатора корреляции](./media/creating-a-long-running-workflow-service/add-correlationinitializers.png "добавить инициализатор корреляции.")

7.  Перетащите другое **ReceiveAndSendReply** действие в конец рабочего процесса (за пределами **последовательности** содержащей первые **Receive** и  **SendReply** действий). Оно получит второе сообщение от клиента и ответит на него.

    1.  Выберите **последовательности** , содержащий только что добавленного **Receive** и **SendReply** действия и нажмите кнопку **переменных** кнопки. Добавьте переменную, отмеченную на следующем рисунке.

         ![Добавление новых переменных](./media/creating-a-long-running-workflow-service/add-the-itemid-variable.png "Добавьте переменную ItemId.")

    2.  Выберите **Receive** действия и задайте свойства, показанные на следующем рисунке:

         ![Набор свойств действия receive](./media/creating-a-long-running-workflow-service/set-receive-activities-properties.png "задание свойств действия Receive.")

    3.  Нажмите кнопку **определить...**  ссылку в **ReceiveAddItem** действия и добавьте параметры, показанные на следующем рисунке: Это позволит настроить действие receive и принимать два параметра, идентификатор заказа и идентификатора заказываемого товара.

         ![Указание параметров для второго получения](./media/creating-a-long-running-workflow-service/add-receive-two-parameters.png "настроить выбранное действие receive для получения двух параметров.")

    4.  Нажмите кнопку **CorrelateOn** кнопку с многоточием и ввести `orderIdHandle`. В разделе **запросы XPath**, щелкните стрелку раскрывающегося списка и выберите `p_orderId`. При этом будет настроена корреляция второго действия Receive. Дополнительные сведения о корреляции см. в разделе [корреляции](../../../../docs/framework/wcf/feature-details/correlation.md).

         ![Задание свойства CorrelatesOn](./media/creating-a-long-running-workflow-service/correlateson-setting.png "свойство CorrelatesOn.")

    5.  Перетаскивание **Если** действия сразу после **ReceiveAddItem** действия. Это действие работает аналогично инструкции IF.

        1.  Задайте **условие** свойства `itemId=="Zune HD" (itemId="Zune HD" for Visual Basic)`

        2.  Перетаскивание **назначить** действие в **затем** раздел, а второе-в **Else** разделе Задание свойств **назначить** действия, как показано на следующем рисунке.

             ![Задание результата вызова службы](./media/creating-a-long-running-workflow-service/assign-result-of-service-call.png "назначить результат вызова службы.")

             Если условие равно `true` **затем** будет выполнен раздел. Если условие равно `false` **Else** будет выполнен раздел.

        3.  Выберите **SendReplyToReceive** действие и набор **DisplayName** свойства, показанного на следующем рисунке.

             ![Задание свойств действия SendReply](./media/creating-a-long-running-workflow-service/send-reply-activity-property.png "задайте свойства действия SendReply.")

        4.  Нажмите кнопку **определить...**  ссылку в **SetReplyToAddItem** действия и настройте его, как показано на следующем рисунке. Это позволит настроить **SendReplyToAddItem** действие будет возвращать значение в `orderResult` переменной.

             ![Задание привязки данных для действия SendReply](./media/creating-a-long-running-workflow-service/set-property-for-sendreplytoadditem.gif "задать свойство для SendReplyToAddItem действия.")

8.  Откройте файл web.config и добавьте следующие элементы в \<поведение > раздела, чтобы включить сохранение рабочего процесса.

    ```xml
    <sqlWorkflowInstanceStore connectionString="Data Source=your-machine\SQLExpress;Initial Catalog=SQLPersistenceStore;Integrated Security=True;Asynchronous Processing=True" instanceEncodingOption="None" instanceCompletionAction="DeleteAll" instanceLockedExceptionAction="BasicRetry" hostLockRenewalPeriod="00:00:30" runnableInstancesDetectionPeriod="00:00:02" />
              <workflowIdle timeToUnload="0"/>
    ```

    > [!WARNING]
    >  В приведенном выше фрагменте кода необходимо заменить имя узла и экземпляра SQL Server.

9. Постройте решение.

### <a name="to-create-a-client-application-to-call-the-workflow-service"></a>Создание клиентского приложения, вызывающего службу рабочего процесса

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

5.  Выполните построение решения и запустите приложение `OrderClient`. Клиент выведет на экран следующий текст.

    ```Output
    Sending start messageWorkflow service is idle...Press [ENTER] to send an add item message to reactivate the workflow service...
    ```

6.  Чтобы убедиться, что службы рабочего процесса были сохранены, запустите SQL Server Management Studio, выбрав **запустить** меню, выбрав вариант **все программы**, **Microsoft SQL Server 2008**, **SQL Server Management Studio**.

    1.  В области слева разверните узел, **баз данных**, **SQLPersistenceStore**, **представления** и щелкните правой кнопкой мыши **System.Activities.DurableInstancing.Instances**  и выберите **выделить 1000 верхних строк**. В **результаты** области проверьте отображаться по крайней мере один экземпляр. Если во время работы возникнет исключение, в этой области могут быть указаны и другие экземпляры, оставшиеся от прошлых запусков. Удалить существующие строки, щелкнув правой кнопкой мыши **System.Activities.DurableInstancing.Instances** и выбрав **изменить 200 верхних строк**, нажмите клавишу **Execute** кнопки, Выделите все строки в области результатов и выбрав **удалить**.  Чтобы проверить, что в базе данных отображается экземпляр, созданный учебным приложением, перед запуском клиента удалите все записи из представления экземпляров. После запуска клиента выполните этот запрос («Выделить 1000 верхних строк») еще раз и удостоверьтесь, что новый экземпляр добавлен.

7.  Нажмите клавишу ВВОД, чтобы отправить сообщение о добавлении товара службе рабочего процесса. Клиент выведет на экран следующий текст.

    ```Output
    Sending add item messageService returned: Item added to orderPress any key to continue . . .
    ```

## <a name="see-also"></a>См. также

- [Службы рабочего процесса](../../../../docs/framework/wcf/feature-details/workflow-services.md)
