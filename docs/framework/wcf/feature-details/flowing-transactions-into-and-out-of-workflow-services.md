---
title: Направление транзакций в службы рабочего процесса и из них
ms.date: 03/30/2017
ms.assetid: 03ced70e-b540-4dd9-86c8-87f7bd61f609
ms.openlocfilehash: ea14bc651258684fd31940aa6b88f9731348dcd1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978271"
---
# <a name="flowing-transactions-into-and-out-of-workflow-services"></a>Направление транзакций в службы рабочего процесса и из них
Службы и клиенты рабочих процессов могут использоваться в транзакциях.  Чтобы сделать операцию службы частью внешней транзакции, поместите действие <xref:System.ServiceModel.Activities.Receive> в действие <xref:System.ServiceModel.Activities.TransactedReceiveScope>. Все вызовы, выполненные действием <xref:System.ServiceModel.Activities.Send> или <xref:System.ServiceModel.Activities.SendReply> в области <xref:System.ServiceModel.Activities.TransactedReceiveScope>, также будут выполнены во внешней транзакции. Клиентское приложение рабочего процесса может создавать внешнюю транзакцию с помощью действия <xref:System.Activities.Statements.TransactionScope> и вызывать операции службы с помощью внешних транзакций. В данном разделе описывается создание службы рабочего процесса и клиента рабочего процесса, которые участвуют в транзакции.  
  
> [!WARNING]
> Если экземпляр службы рабочего процесса загружен в рамках транзакции, а рабочий процесс содержит <xref:System.Activities.Statements.Persist> действие, экземпляр рабочего процесса будет заблокирован до истечения времени ожидания транзакции.  
  
> [!IMPORTANT]
> При использовании области <xref:System.ServiceModel.Activities.TransactedReceiveScope> рекомендуется размещать все операции получения в рабочем процессе в действиях, связанных с областью <xref:System.ServiceModel.Activities.TransactedReceiveScope>.  
  
> [!IMPORTANT]
> Если используется область <xref:System.ServiceModel.Activities.TransactedReceiveScope>, а сообщения поступают в неверном порядке, рабочий процесс будет прерван при попытке доставки первого сообщения, пришедшего в неправильном порядке. Убедитесь, что рабочий процесс всегда находится в согласованном состоянии при освобождении рабочего процесса. Это позволит перезапустить рабочий процесс с прежней сохраненной точки в случае, если он был прерван.  
  
### <a name="create-a-shared-library"></a>Создание общей библиотеки  
  
1. Создайте новое пустое решение Visual Studio.  
  
2. Добавьте новый проект библиотеки классов с именем `Common`. Добавьте ссылки на следующие сборки:  
  
    - System.Activities.dll  
  
    - System.ServiceModel.dll  
  
    - System.ServiceModel.Activities.dll  
  
    - System.Transactions.dll  
  
3. Добавьте новый класс с именем `PrintTransactionInfo` к проекту `Common`. Класс является производным от <xref:System.Activities.NativeActivity> и перегружает метод <xref:System.Activities.NativeActivity.Execute%2A>.  
  
    ```csharp
    using System;  
    using System;  
    using System.Activities;  
    using System.Transactions;  
  
    namespace Common  
    {  
        public class PrintTransactionInfo : NativeActivity  
        {  
            protected override void Execute(NativeActivityContext context)  
            {  
                RuntimeTransactionHandle rth = context.Properties.Find(typeof(RuntimeTransactionHandle).FullName) as RuntimeTransactionHandle;  
  
                if (rth == null)  
                {  
                    Console.WriteLine("There is no ambient RuntimeTransactionHandle");  
                }  
  
                Transaction t = rth.GetCurrentTransaction(context);  
  
                if (t == null)  
                {  
                    Console.WriteLine("There is no ambient transaction");  
                }  
                else  
                {  
                    Console.WriteLine("Transaction: {0} is {1}", t.TransactionInformation.DistributedIdentifier, t.TransactionInformation.Status);  
                }  
            }  
        }  
  
    }  
    ```  
  
     Это собственное действие, при выполнении которого отображаются данные о внешней транзакции, и оно используется в службе и клиенте рабочих процессов, описываемых в этом разделе. Выполните сборку решения, чтобы сделать это действие доступным в разделе " **Общие** " области **элементов**.  
  
### <a name="implement-the-workflow-service"></a>Реализация службы рабочего процесса  
  
1. Добавьте новую службу рабочего процесса WCF, которая называется `WorkflowService`, в проект `Common`. Для этого щелкните проект `Common` правой кнопкой мыши, выберите **Добавить**, **новый элемент...** , выберите **Рабочий процесс** в разделе **Установленные шаблоны** и выберите **Служба рабочего процесса WCF**.  
  
     ![Добавление службы рабочего процесса](./media/flowing-transactions-into-and-out-of-workflow-services/add-workflow-service.jpg)  
  
2. Удалите заданные по умолчанию действия `ReceiveRequest` и `SendResponse`.  
  
3. Перетащите действие с именем <xref:System.Activities.Statements.WriteLine> в `Sequential Service`. Задайте значение для свойства текста `"Workflow Service starting ..."`, как показано в следующем примере.  
  
     ! [Добавление действия WriteLine к действию последовательной службы (./медиа/фловинг-трансактионс-Инто-Анд-аут-оф-воркфлов-сервицес/адд-врителине-секуентиал-сервице.ЖПГ)  
  
4. Перетащите действие <xref:System.ServiceModel.Activities.TransactedReceiveScope> и поместите его после действия <xref:System.Activities.Statements.WriteLine>. Действие <xref:System.ServiceModel.Activities.TransactedReceiveScope> можно найти в разделе « **Обмен сообщениями** » **панели элементов**. Действие <xref:System.ServiceModel.Activities.TransactedReceiveScope> состоит из двух разделов: **запрос** и **текст**. Раздел **запроса** содержит действие <xref:System.ServiceModel.Activities.Receive>. Раздел **Body** содержит действия, выполняемые в рамках транзакции после получения сообщения.  
  
     ![Добавление действия TransactedReceiveScope](./media/flowing-transactions-into-and-out-of-workflow-services/transactedreceivescope-activity.jpg)  
  
5. Выберите действие <xref:System.ServiceModel.Activities.TransactedReceiveScope> и нажмите кнопку **переменные** . Добавьте следующие переменные.  
  
     ![Добавление переменных в TransactedReceiveScope](./media/flowing-transactions-into-and-out-of-workflow-services/add-transactedreceivescope-variables.jpg)  
  
    > [!NOTE]
    > Можно удалить переменную данных, заданную по умолчанию. Также можно использовать существующую переменную обработки.  
  
6. Перетащите <xref:System.ServiceModel.Activities.Receive> действие в раздел **запроса** действия <xref:System.ServiceModel.Activities.TransactedReceiveScope>. Задайте следующие свойства:  
  
    |свойство;|значения|  
    |--------------|-----------|  
    |CanCreateInstance|True (установите флажок)|  
    |OperationName|StartSample|  
    |ServiceContractName|ITransactionSample|  
  
     Рабочий процесс должен выглядеть так:  
  
     ![Добавление действия Receive](./media/flowing-transactions-into-and-out-of-workflow-services/add-receive-activity.jpg)  
  
7. Щелкните ссылку **define...** в действии <xref:System.ServiceModel.Activities.Receive> и задайте следующие параметры.  
  
     ![Настройка параметров сообщений для действия Receive](./media/flowing-transactions-into-and-out-of-workflow-services/receive-message-settings.jpg)  
  
8. Перетащите действие <xref:System.Activities.Statements.Sequence> в разделе «Текст» <xref:System.ServiceModel.Activities.TransactedReceiveScope>. В действии <xref:System.Activities.Statements.Sequence> перетащите два действия <xref:System.Activities.Statements.WriteLine> и настройте свойства <xref:System.Activities.Statements.WriteLine.Text%2A>, как показано в следующей таблице.  
  
    |Действие|значения|  
    |--------------|-----------|  
    |Первое действие WriteLine|"Служба: получение завершено"|  
    |Второе действие WriteLine|"Service: Received = " + requestMessage|  
  
     После этого рабочий процесс должен выглядеть так:  
  
     ![Последовательность после добавления действий WriteLine](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-writelines.jpg)  
  
9. Перетащите `PrintTransactionInfo` действие после второго действия <xref:System.Activities.Statements.WriteLine> в **тексте** действия <xref:System.ServiceModel.Activities.TransactedReceiveScope>.  
  
     ![Последовательность после добавления Принттрансактионинфо](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-printtransactioninfo.jpg )  
  
10. Перетащите действие <xref:System.Activities.Statements.Assign>, поместите его после действия `PrintTransactionInfo` и задайте свойства в соответствии со следующей таблицей.  
  
    |свойство;|значения|  
    |--------------|-----------|  
    |Целевой тип|replyMessage|  
    |значения|"Service: Sending reply."|  
  
11. Перетащите действие <xref:System.Activities.Statements.WriteLine>, поместите его после действия <xref:System.Activities.Statements.Assign> и задайте для свойства <xref:System.Activities.Statements.WriteLine.Text%2A> значение "Service: Begin reply".  
  
     После этого рабочий процесс должен выглядеть так:  
  
     ![После добавления Assign и WriteLine](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-sbr-writeline.jpg)  
  
12. Щелкните действие <xref:System.ServiceModel.Activities.Receive> правой кнопкой мыши и выберите **Создать SendReply** и вставьте его после последнего действия <xref:System.Activities.Statements.WriteLine>. Щелкните ссылку **define...** в действии `SendReplyToReceive` и задайте следующие параметры.  
  
     ![Параметры ответного сообщения](./media/flowing-transactions-into-and-out-of-workflow-services/reply-message-settings.jpg)  
  
13. Перетащите <xref:System.Activities.Statements.WriteLine> действие после `SendReplyToReceive` действия и задайте для свойства <xref:System.Activities.Statements.WriteLine.Text%2A> значение "служба: отправленный ответ".  
  
14. Перетащите действие <xref:System.Activities.Statements.WriteLine> в нижнюю область рабочего процесса и задайте для свойства <xref:System.Activities.Statements.WriteLine.Text%2A> значение "Service: Workflow ends, press ENTER to exit".  
  
     Завершенный рабочий процесс службы должен выглядеть следующим образом:  
  
     ![Полный рабочий процесс службы](./media/flowing-transactions-into-and-out-of-workflow-services/service-complete-workflow.jpg)  
  
### <a name="implement-the-workflow-client"></a>Реализуйте клиент рабочего процесса  
  
1. Добавьте новое приложение WCF Workflow с именем `WorkflowClient` к проекту `Common`. Для этого щелкните проект `Common` правой кнопкой мыши, выберите **Добавить**, **новый элемент...** , выберите **Рабочий процесс** в разделе **Установленные шаблоны** и выберите **действие**.  
  
     ![Добавление проекта действия](./media/flowing-transactions-into-and-out-of-workflow-services/add-activity-project.jpg)  
  
2. Перетащите действие <xref:System.Activities.Statements.Sequence> в область конструктора.  
  
3. В действии <xref:System.Activities.Statements.Sequence> перетащите действие <xref:System.Activities.Statements.WriteLine> и задайте для его свойства <xref:System.Activities.Statements.WriteLine.Text%2A> значение `"Client: Workflow starting"`. После этого рабочий процесс должен выглядеть так:  
  
     ![Добавление действия WriteLine](./media/flowing-transactions-into-and-out-of-workflow-services/add-writeline-activity.jpg)  
  
4. Перетащите действие <xref:System.Activities.Statements.TransactionScope> и поместите его после действия <xref:System.Activities.Statements.WriteLine>.  Выберите действие <xref:System.Activities.Statements.TransactionScope>, нажмите кнопку «Переменные» и добавьте следующие переменные.  
  
     ![Добавление переменных в TransactionScope](./media/flowing-transactions-into-and-out-of-workflow-services/transactionscope-variables.jpg)  
  
5. Перетащите действие <xref:System.Activities.Statements.Sequence> в текст действия <xref:System.Activities.Statements.TransactionScope>.  
  
6. Перетащите действие `PrintTransactionInfo` в <xref:System.Activities.Statements.Sequence>.  
  
7. Перетащите <xref:System.Activities.Statements.WriteLine> действие после действия `PrintTransactionInfo` и задайте для его свойства <xref:System.Activities.Statements.WriteLine.Text%2A> значение "Клиент: Начало отправки". После этого рабочий процесс должен выглядеть так:  
  
     ![Добавление клиента: Начало отправки действий](./media/flowing-transactions-into-and-out-of-workflow-services/client-add-cbs-writeline.jpg)  
  
8. Перетащите действие <xref:System.ServiceModel.Activities.Send>, поместите его после действия <xref:System.Activities.Statements.Assign> и задайте следующие свойства:  
  
    |свойство;|значения|  
    |--------------|-----------|  
    |EndpointConfigurationName|workflowServiceEndpoint|  
    |OperationName|StartSample|  
    |ServiceContractName|ITransactionSample|  
  
     После этого рабочий процесс должен выглядеть так:  
  
     ![Задание свойств действия Send](./media/flowing-transactions-into-and-out-of-workflow-services/client-send-activity-settings.jpg)  
  
9. Щелкните ссылку **define...** и задайте следующие параметры:  
  
     ![Параметры сообщения действия Send](./media/flowing-transactions-into-and-out-of-workflow-services/send-message-settings.jpg)  
  
10. Щелкните правой кнопкой мыши действие <xref:System.ServiceModel.Activities.Send> и выберите **создать ReceiveReply**. Действие <xref:System.ServiceModel.Activities.ReceiveReply> будет автоматически помещено после действия <xref:System.ServiceModel.Activities.Send>.  
  
11. Щелкните ссылку «Определить...» в действии ReceiveReplyForSend и задайте следующие параметры:  
  
     ![Задание параметров сообщения ReceiveForSend](./media/flowing-transactions-into-and-out-of-workflow-services/client-reply-message-settings.jpg)  
  
12. Перетащите действие <xref:System.Activities.Statements.WriteLine>, поместите его между действиями <xref:System.ServiceModel.Activities.Send> и <xref:System.ServiceModel.Activities.ReceiveReply>, а также задайте для свойства <xref:System.Activities.Statements.WriteLine.Text%2A> значение "Client: Send complete".  
  
13. Перетащите действие <xref:System.Activities.Statements.WriteLine>, поместите его после действия <xref:System.ServiceModel.Activities.ReceiveReply> и задайте для свойства <xref:System.Activities.Statements.WriteLine.Text%2A> значение "Client side: Reply received = " + replyMessage.  
  
14. Перетащите действие `PrintTransactionInfo` и поместите его после действия <xref:System.Activities.Statements.WriteLine>.  
  
15. Перетащите действие <xref:System.Activities.Statements.WriteLine> в конец рабочего процесса и задайте для свойства <xref:System.Activities.Statements.WriteLine.Text%2A> значение "Client workflow ends". Завершенный рабочий процесс клиента должен выглядеть следующим образом на приведенной ниже схеме.  
  
     ![Завершенный рабочий процесс клиента](./media/flowing-transactions-into-and-out-of-workflow-services/client-complete-workflow.jpg)  
  
16. Постройте решение.  
  
### <a name="create-the-service-application"></a>Создание приложения службы  
  
1. Добавьте в решение новый проект консольного приложения с именем `Service`. Добавьте ссылки на следующие сборки:  
  
    1. System.Activities.dll  
  
    2. System.ServiceModel.dll  
  
    3. System.ServiceModel.Activities.dll  
  
2. Откройте созданный файл Program.cs и следующий код:  
  
    ```csharp
          static void Main()  
          {  
              Console.WriteLine("Building the server.");  
              using (WorkflowServiceHost host = new WorkflowServiceHost(new DeclarativeServiceWorkflow(), new Uri("net.tcp://localhost:8000/TransactedReceiveService/Declarative")))  
              {                
                  //Start the server  
                  host.Open();  
                  Console.WriteLine("Service started.");  
  
                  Console.WriteLine();  
                  Console.ReadLine();  
                  //Shutdown  
                  host.Close();  
              };         
          }  
    ```  
  
3. Добавьте к проекту следующий файл app.config.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <!-- Copyright © Microsoft Corporation.  All rights reserved. -->  
    <configuration>  
        <system.serviceModel>  
            <bindings>  
                <netTcpBinding>  
                    <binding transactionFlow="true" />  
                </netTcpBinding>  
            </bindings>  
        </system.serviceModel>  
    </configuration>  
    ```  
  
### <a name="create-the-client-application"></a>Создание клиентского приложения  
  
1. Добавьте в решение новый проект консольного приложения с именем `Client`. Добавьте ссылку на библиотеку System.Activities.dll.  
  
2. Откройте файл program.cs и добавьте следующий код:  
  
    ```csharp
    class Program  
    {  

        private static AutoResetEvent syncEvent = new AutoResetEvent(false);  
  
        static void Main(string[] args)  
        {  
            //Build client  
            Console.WriteLine("Building the client.");  
            WorkflowApplication client = new WorkflowApplication(new DeclarativeClientWorkflow());  
            client.Completed = Program.Completed;  
            client.Aborted = Program.Aborted;  
            client.OnUnhandledException = Program.OnUnhandledException;  
            //Wait for service to start  
            Console.WriteLine("Press ENTER once service is started.");  
            Console.ReadLine();  
  
            //Start the client              
            Console.WriteLine("Starting the client.");  
            client.Run();  
            syncEvent.WaitOne();  
  
            //Sample complete  
            Console.WriteLine();  
            Console.WriteLine("Client complete. Press ENTER to exit.");  
            Console.ReadLine();  
        }  
  
        private static void Completed(WorkflowApplicationCompletedEventArgs e)  
        {  
            Program.syncEvent.Set();  
        }  
  
        private static void Aborted(WorkflowApplicationAbortedEventArgs e)  
        {  
            Console.WriteLine("Client Aborted: {0}", e.Reason);  
            Program.syncEvent.Set();  
        }  
  
        private static UnhandledExceptionAction OnUnhandledException(WorkflowApplicationUnhandledExceptionEventArgs e)  
        {  
            Console.WriteLine("Client had an unhandled exception: {0}", e.UnhandledException);  
            return UnhandledExceptionAction.Cancel;  
        }  
    }  
    ```  
  
## <a name="see-also"></a>См. также

- [Службы рабочих процессов](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Общие сведения о транзакциях Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/transactions-overview.md)
