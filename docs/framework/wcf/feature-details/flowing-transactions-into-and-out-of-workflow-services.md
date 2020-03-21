---
title: Направление транзакций в службы рабочего процесса и из них
ms.date: 03/30/2017
ms.assetid: 03ced70e-b540-4dd9-86c8-87f7bd61f609
ms.openlocfilehash: fe03047dd931d25ec94bbc5e00c479d1b42397bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185279"
---
# <a name="flowing-transactions-into-and-out-of-workflow-services"></a>Направление транзакций в службы рабочего процесса и из них
Службы и клиенты рабочих процессов могут использоваться в транзакциях.  Чтобы сделать операцию службы частью внешней транзакции, поместите действие <xref:System.ServiceModel.Activities.Receive> в действие <xref:System.ServiceModel.Activities.TransactedReceiveScope>. Все вызовы, выполненные действием <xref:System.ServiceModel.Activities.Send> или <xref:System.ServiceModel.Activities.SendReply> в области <xref:System.ServiceModel.Activities.TransactedReceiveScope>, также будут выполнены во внешней транзакции. Клиентское приложение рабочего процесса может создавать внешнюю транзакцию с помощью действия <xref:System.Activities.Statements.TransactionScope> и вызывать операции службы с помощью внешних транзакций. В данном разделе описывается создание службы рабочего процесса и клиента рабочего процесса, которые участвуют в транзакции.  
  
> [!WARNING]
> Если экземпляр службы рабочего процесса загружен в транзакции <xref:System.Activities.Statements.Persist> и рабочий процесс содержит действие, экземпляр рабочего процесса будет блокироваться до тех пор, пока транзакция не выйдет из-под ожидания.  
  
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
  
     Это собственное действие, при выполнении которого отображаются данные о внешней транзакции, и оно используется в службе и клиенте рабочих процессов, описываемых в этом разделе. Создайте решение, чтобы сделать это действие доступным в **общем** разделе **Toolbox.**  
  
### <a name="implement-the-workflow-service"></a>Реализация службы рабочего процесса  
  
1. Добавьте новую службу рабочего процесса WCF, вызванную `WorkflowService` в `Common` проект. Для этого нажмите `Common` право на проект, выберите **Добавить,** **Новый пункт ...**, Выберите **Рабочий процесс** под **установленными шаблонами** и выберите **службу рабочего процесса WCF.**  
  
     ![Добавление службы рабочего процесса](./media/flowing-transactions-into-and-out-of-workflow-services/add-workflow-service.jpg)  
  
2. Удалите заданные по умолчанию действия `ReceiveRequest` и `SendResponse`.  
  
3. Перетащите действие с именем <xref:System.Activities.Statements.WriteLine> в `Sequential Service`. Задайте значение для свойства текста `"Workflow Service starting ..."`, как показано в следующем примере.  
  
     ! Добавление действия WriteLine к деятельности последовательной службы (./media/flowing-transactions-into-and-out-of-workflow-services/add-writeline-sequential-service.jpg)  
  
4. Перетащите действие <xref:System.ServiceModel.Activities.TransactedReceiveScope> и поместите его после действия <xref:System.Activities.Statements.WriteLine>. Действие <xref:System.ServiceModel.Activities.TransactedReceiveScope> можно найти в разделе **Сообщений** **в Toolbox**. Действие <xref:System.ServiceModel.Activities.TransactedReceiveScope> состоит из двух разделов **Запрос** и **Тело**. Раздел **Запрос** содержит <xref:System.ServiceModel.Activities.Receive> действие. Раздел **Тела** содержит действия для выполнения в транзакции после получения сообщения.  
  
     ![Добавление действия TransactedReceiveScope](./media/flowing-transactions-into-and-out-of-workflow-services/transactedreceivescope-activity.jpg)  
  
5. Выберите <xref:System.ServiceModel.Activities.TransactedReceiveScope> действие и нажмите кнопку **Переменные.** Добавьте следующие переменные.  
  
     ![Добавление переменных в TransactedReceiveScope](./media/flowing-transactions-into-and-out-of-workflow-services/add-transactedreceivescope-variables.jpg)  
  
    > [!NOTE]
    > Можно удалить переменную данных, заданную по умолчанию. Также можно использовать существующую переменную обработки.  
  
6. Перетащите <xref:System.ServiceModel.Activities.Receive> и отбросьте <xref:System.ServiceModel.Activities.TransactedReceiveScope> действие в разделе **Запрос** деятельности. Задайте следующие свойства.  
  
    |Свойство|Значение|  
    |--------------|-----------|  
    |CanCreateInstance|True (установите флажок)|  
    |OperationName|StartSample|  
    |ServiceContractName|ITransactionSample|  
  
     Рабочий процесс должен выглядеть так:  
  
     ![Добавление действия Receive](./media/flowing-transactions-into-and-out-of-workflow-services/add-receive-activity.jpg)  
  
7. Нажмите ссылку **Define...** в действии <xref:System.ServiceModel.Activities.Receive> и сделайте следующие настройки:  
  
     ![Настройка настроек сообщения для действия Receive](./media/flowing-transactions-into-and-out-of-workflow-services/receive-message-settings.jpg)  
  
8. Перетащите действие <xref:System.Activities.Statements.Sequence> в разделе «Текст» <xref:System.ServiceModel.Activities.TransactedReceiveScope>. В действии <xref:System.Activities.Statements.Sequence> перетащите два действия <xref:System.Activities.Statements.WriteLine> и настройте свойства <xref:System.Activities.Statements.WriteLine.Text%2A>, как показано в следующей таблице.  
  
    |Действие|Значение|  
    |--------------|-----------|  
    |Первое действие WriteLine|"Обслуживание: Получить завершена"|  
    |Второе действие WriteLine|"Service: Received = " + requestMessage|  
  
     После этого рабочий процесс должен выглядеть так:  
  
     ![Последовательность после добавления действий WriteLine](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-writelines.jpg)  
  
9. Перетащите `PrintTransactionInfo` и сбросьте активность после второго <xref:System.Activities.Statements.WriteLine> действия в **организме** в деятельности. <xref:System.ServiceModel.Activities.TransactedReceiveScope>  
  
     ![Последовательность после добавления PrintTransactionInfo](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-printtransactioninfo.jpg )  
  
10. Перетащите действие <xref:System.Activities.Statements.Assign>, поместите его после действия `PrintTransactionInfo` и задайте свойства в соответствии со следующей таблицей.  
  
    |Свойство|Значение|  
    |--------------|-----------|  
    |Чтобы|replyMessage|  
    |Значение|"Service: Sending reply."|  
  
11. Перетащите действие <xref:System.Activities.Statements.WriteLine>, поместите его после действия <xref:System.Activities.Statements.Assign> и задайте для свойства <xref:System.Activities.Statements.WriteLine.Text%2A> значение "Service: Begin reply".  
  
     После этого рабочий процесс должен выглядеть так:  
  
     ![После добавления Assign и WriteLine](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-sbr-writeline.jpg)  
  
12. Нажмите <xref:System.ServiceModel.Activities.Receive> правой кнопкой мыши и выберите <xref:System.Activities.Statements.WriteLine> **Создать SendReply** и вставить его после последнего действия. Нажмите ссылку **Define...** в действии `SendReplyToReceive` и сделайте следующие настройки.  
  
     ![Параметры ответного сообщения](./media/flowing-transactions-into-and-out-of-workflow-services/reply-message-settings.jpg)  
  
13. Перетащите <xref:System.Activities.Statements.WriteLine> и `SendReplyToReceive` отбросьте действие <xref:System.Activities.Statements.WriteLine.Text%2A> после действия и установите его свойство "Служба: Ответ отправлено".  
  
14. Перетащите действие <xref:System.Activities.Statements.WriteLine> в нижнюю область рабочего процесса и задайте для свойства <xref:System.Activities.Statements.WriteLine.Text%2A> значение "Service: Workflow ends, press ENTER to exit".  
  
     Завершенный рабочий процесс службы должен выглядеть следующим образом:  
  
     ![Полный рабочий процесс службы](./media/flowing-transactions-into-and-out-of-workflow-services/service-complete-workflow.jpg)  
  
### <a name="implement-the-workflow-client"></a>Реализуйте клиент рабочего процесса  
  
1. Добавьте новое приложение WCF Workflow с именем `WorkflowClient` к проекту `Common`. Для этого нажмите `Common` право на проект, выберите **Добавить,** **Новый пункт ...**, Выберите **Рабочий процесс** под **установленными шаблонами** и выберите **активность.**  
  
     ![Добавление проекта действия](./media/flowing-transactions-into-and-out-of-workflow-services/add-activity-project.jpg)  
  
2. Перетащите действие <xref:System.Activities.Statements.Sequence> в область конструктора.  
  
3. В действии <xref:System.Activities.Statements.Sequence> перетащите действие <xref:System.Activities.Statements.WriteLine> и задайте для его свойства <xref:System.Activities.Statements.WriteLine.Text%2A> значение `"Client: Workflow starting"`. После этого рабочий процесс должен выглядеть так:  
  
     ![Добавление действия WriteLine](./media/flowing-transactions-into-and-out-of-workflow-services/add-writeline-activity.jpg)  
  
4. Перетащите действие <xref:System.Activities.Statements.TransactionScope> и поместите его после действия <xref:System.Activities.Statements.WriteLine>.  Выберите действие <xref:System.Activities.Statements.TransactionScope>, нажмите кнопку «Переменные» и добавьте следующие переменные.  
  
     ![Добавление переменных в TransactionScope](./media/flowing-transactions-into-and-out-of-workflow-services/transactionscope-variables.jpg)  
  
5. Перетащите действие <xref:System.Activities.Statements.Sequence> в текст действия <xref:System.Activities.Statements.TransactionScope>.  
  
6. Перетащите действие `PrintTransactionInfo` в <xref:System.Activities.Statements.Sequence>.  
  
7. Перетащите <xref:System.Activities.Statements.WriteLine> и `PrintTransactionInfo` отбросьте <xref:System.Activities.Statements.WriteLine.Text%2A> действие после действия и установите его свойство на "Клиент: Начало отправки". После этого рабочий процесс должен выглядеть так:  
  
     ![Добавление клиента: Начало действий по отправке](./media/flowing-transactions-into-and-out-of-workflow-services/client-add-cbs-writeline.jpg)  
  
8. Перетащите действие <xref:System.ServiceModel.Activities.Send>, поместите его после действия <xref:System.Activities.Statements.Assign> и задайте следующие свойства:  
  
    |Свойство|Значение|  
    |--------------|-----------|  
    |EndpointConfigurationName|workflowServiceEndpoint|  
    |OperationName|StartSample|  
    |ServiceContractName|ITransactionSample|  
  
     После этого рабочий процесс должен выглядеть так:  
  
     ![Задание свойств действия Send](./media/flowing-transactions-into-and-out-of-workflow-services/client-send-activity-settings.jpg)  
  
9. Нажмите на ссылку **Define...** и сделайте следующие настройки:  
  
     ![Параметры сообщения действия Send](./media/flowing-transactions-into-and-out-of-workflow-services/send-message-settings.jpg)  
  
10. Право нажмите <xref:System.ServiceModel.Activities.Send> на действие и выберите Создать **ReceiveReply**. Действие <xref:System.ServiceModel.Activities.ReceiveReply> будет автоматически помещено после действия <xref:System.ServiceModel.Activities.Send>.  
  
11. Щелкните ссылку «Определить...» в действии ReceiveReplyForSend и задайте следующие параметры:  
  
     ![Задание параметров сообщения ReceiveForSend](./media/flowing-transactions-into-and-out-of-workflow-services/client-reply-message-settings.jpg)  
  
12. Перетащите действие <xref:System.Activities.Statements.WriteLine>, поместите его между действиями <xref:System.ServiceModel.Activities.Send> и <xref:System.ServiceModel.Activities.ReceiveReply>, а также задайте для свойства <xref:System.Activities.Statements.WriteLine.Text%2A> значение "Client: Send complete".  
  
13. Перетащите действие <xref:System.Activities.Statements.WriteLine>, поместите его после действия <xref:System.ServiceModel.Activities.ReceiveReply> и задайте для свойства <xref:System.Activities.Statements.WriteLine.Text%2A> значение "Client side: Reply received = " + replyMessage.  
  
14. Перетащите действие `PrintTransactionInfo` и поместите его после действия <xref:System.Activities.Statements.WriteLine>.  
  
15. Перетащите действие <xref:System.Activities.Statements.WriteLine> в конец рабочего процесса и задайте для свойства <xref:System.Activities.Statements.WriteLine.Text%2A> значение "Client workflow ends". Завершенный рабочий процесс клиента должен выглядеть следующим образом на приведенной ниже схеме.  
  
     ![Завершенный рабочий процесс клиента](./media/flowing-transactions-into-and-out-of-workflow-services/client-complete-workflow.jpg)  
  
16. Создайте решение.  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Службы рабочего процесса](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Общие сведения о транзакциях Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/transactions-overview.md)
