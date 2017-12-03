---
title: "Направление транзакций в службы рабочего процесса и из них"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03ced70e-b540-4dd9-86c8-87f7bd61f609
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d097068720bb937911316fdb29a83ba0e8e67713
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="flowing-transactions-into-and-out-of-workflow-services"></a>Направление транзакций в службы рабочего процесса и из них
Службы и клиенты рабочих процессов могут использоваться в транзакциях.  Чтобы сделать операцию службы частью внешней транзакции, поместите действие <xref:System.ServiceModel.Activities.Receive> в действие <xref:System.ServiceModel.Activities.TransactedReceiveScope>. Все вызовы, выполненные действием <xref:System.ServiceModel.Activities.Send> или <xref:System.ServiceModel.Activities.SendReply> в области <xref:System.ServiceModel.Activities.TransactedReceiveScope>, также будут выполнены во внешней транзакции. Клиентское приложение рабочего процесса может создавать внешнюю транзакцию с помощью действия <xref:System.Activities.Statements.TransactionScope> и вызывать операции службы с помощью внешних транзакций. В данном разделе описывается создание службы рабочего процесса и клиента рабочего процесса, которые участвуют в транзакции.  
  
> [!WARNING]
>  Если экземпляр службы рабочего процесса загружается в транзакцию и рабочий процесс содержит действие <xref:System.Activities.Statements.Persist>, экземпляр рабочего процесса «зависнет» до истечения срока ожидания транзакции.  
  
> [!IMPORTANT]
>  При использовании области <xref:System.ServiceModel.Activities.TransactedReceiveScope> рекомендуется размещать все операции получения в рабочем процессе в действиях, связанных с областью <xref:System.ServiceModel.Activities.TransactedReceiveScope>.  
  
> [!IMPORTANT]
>  Если используется область <xref:System.ServiceModel.Activities.TransactedReceiveScope>, а сообщения поступают в неверном порядке, рабочий процесс будет прерван при попытке доставки первого сообщения, пришедшего в неправильном порядке. Убедитесь, что рабочий процесс всегда находится в согласованном состоянии при освобождении рабочего процесса. Это позволит перезапустить рабочий процесс с прежней сохраненной точки в случае, если он был прерван.  
  
### <a name="create-a-shared-library"></a>Создание общей библиотеки  
  
1.  Создайте новое пустое решение Visual Studio.  
  
2.  Добавьте новый проект библиотеки классов с именем `Common`. Добавьте ссылки на следующие сборки:  
  
    -   System.Activities.dll  
  
    -   System.ServiceModel.dll  
  
    -   System.ServiceModel.Activities.dll  
  
    -   System.Transactions.dll  
  
3.  Добавьте новый класс с именем `PrintTransactionInfo` к проекту `Common`. Класс является производным от <xref:System.Activities.NativeActivity> и перегружает метод <xref:System.Activities.NativeActivity.Execute%2A>.  
  
    ```  
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
  
     Это собственное действие, при выполнении которого отображаются данные о внешней транзакции, и оно используется в службе и клиенте рабочих процессов, описываемых в этом разделе. Постройте решение, чтобы обеспечить доступность в действия **Общие** раздел **элементов**.  
  
### <a name="implement-the-workflow-service"></a>Реализация службы рабочего процесса  
  
1.  Добавьте новый [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] службы рабочего процесса, именуемое `WorkflowService` для `Common` проекта. Для этого щелкните правой `Common` проекта, выберите **добавить**, **новый элемент...** Выберите **рабочего процесса** под **установленные шаблоны** и выберите **службы рабочего процесса WCF**.  
  
     ![Добавление службы рабочего процесса](../../../../docs/framework/wcf/feature-details/media/addwfservice.JPG "AddWFService")  
  
2.  Удалите заданные по умолчанию действия `ReceiveRequest` и `SendResponse`.  
  
3.  Перетащите действие с именем <xref:System.Activities.Statements.WriteLine> в `Sequential Service`. Задайте значение для свойства текста `"Workflow Service starting ..."`, как показано в следующем примере.  
  
     ![Добавление действия WriteLine](../../../../docs/framework/wcf/feature-details/media/addwriteline.JPG "AddWriteLine")  
  
4.  Перетащите действие <xref:System.ServiceModel.Activities.TransactedReceiveScope> и поместите его после действия <xref:System.Activities.Statements.WriteLine>. <xref:System.ServiceModel.Activities.TransactedReceiveScope> Действия можно найти в **обмен сообщениями** раздел **элементов**. <xref:System.ServiceModel.Activities.TransactedReceiveScope> Действие состоит из двух разделов **запроса** и **текст**. **Запроса** раздел содержит <xref:System.ServiceModel.Activities.Receive> действия. **Текст** содержит действия, которые необходимо выполнить в транзакции после получения сообщения.  
  
     ![Добавление действия TransactedReceiveScope](../../../../docs/framework/wcf/feature-details/media/trs.JPG "TRS")  
  
5.  Выберите <xref:System.ServiceModel.Activities.TransactedReceiveScope> действие и нажмите кнопку **переменных** кнопки. Добавьте следующие переменные.  
  
     ![Добавление переменных в transactedreceivescope](../../../../docs/framework/wcf/feature-details/media/trsvariables.JPG "TRSVariables")  
  
    > [!NOTE]
    >  Можно удалить переменную данных, заданную по умолчанию. Также можно использовать существующую переменную обработки.  
  
6.  Перетаскивание <xref:System.ServiceModel.Activities.Receive> действия в **запроса** раздел <xref:System.ServiceModel.Activities.TransactedReceiveScope> действия. Задайте следующие свойства:  
  
    |Свойство|Значение|  
    |--------------|-----------|  
    |CanCreateInstance|True (установите флажок)|  
    |OperationName|StartSample|  
    |ServiceContractName|ITransactionSample|  
  
     Рабочий процесс должен выглядеть так:  
  
     ![Добавление действия Receive](../../../../docs/framework/wcf/feature-details/media/serviceaddreceive.JPG "ServiceAddReceive")  
  
7.  Нажмите кнопку **определить...**  ссылку в <xref:System.ServiceModel.Activities.Receive> действия и задайте следующие параметры:  
  
     ![Задание параметров сообщения для действия receive](../../../../docs/framework/wcf/feature-details/media/receivemessagesettings.JPG "ReceiveMessageSettings")  
  
8.  Перетащите действие <xref:System.Activities.Statements.Sequence> в разделе «Текст» <xref:System.ServiceModel.Activities.TransactedReceiveScope>. В действии <xref:System.Activities.Statements.Sequence> перетащите два действия <xref:System.Activities.Statements.WriteLine> и настройте свойства <xref:System.Activities.Statements.WriteLine.Text%2A>, как показано в следующей таблице.  
  
    |Действие|Значение|  
    |--------------|-----------|  
    |Первое действие WriteLine|«Service: Receive Completed»|  
    |Второе действие WriteLine|"Service: Received = " + requestMessage|  
  
     После этого рабочий процесс должен выглядеть так:  
  
     ![Добавление действий WriteLine](../../../../docs/framework/wcf/feature-details/media/afteraddingwritelines.JPG "AfterAddingWriteLines")  
  
9. Перетаскивание `PrintTransactionInfo` действия после второго <xref:System.Activities.Statements.WriteLine> действия в **текст** в <xref:System.ServiceModel.Activities.TransactedReceiveScope> действия.  
  
     ![После добавления PrintTransactionInfo](../../../../docs/framework/wcf/feature-details/media/afteraddingprinttransactioninfo.JPG "AfterAddingPrintTransactionInfo")  
  
10. Перетащите действие <xref:System.Activities.Statements.Assign>, поместите его после действия `PrintTransactionInfo` и задайте свойства в соответствии со следующей таблицей.  
  
    |Свойство|Значение|  
    |--------------|-----------|  
    |Целевой тип|replyMessage|  
    |Значение|"Service: Sending reply."|  
  
11. Перетащите действие <xref:System.Activities.Statements.WriteLine>, поместите его после действия <xref:System.Activities.Statements.Assign> и задайте для свойства <xref:System.Activities.Statements.WriteLine.Text%2A> значение "Service: Begin reply".  
  
     После этого рабочий процесс должен выглядеть так:  
  
     ![После добавления Assign и WriteLine](../../../../docs/framework/wcf/feature-details/media/afteraddingsbrwriteline.JPG "AfterAddingSBRWriteLine")  
  
12. Щелкните правой кнопкой мыши <xref:System.ServiceModel.Activities.Receive> действие и выберите **создать SendReply** и вставьте его после последнего <xref:System.Activities.Statements.WriteLine> действия. Нажмите кнопку **определить...**  ссылку в `SendReplyToReceive` действия и задайте следующие параметры.  
  
     ![Параметры сообщения ответа](../../../../docs/framework/wcf/feature-details/media/replymessagesettings.JPG "ReplyMessageSettings")  
  
13. Перетаскивание <xref:System.Activities.Statements.WriteLine> действия после `SendReplyToReceive` и задайте имеет <xref:System.Activities.Statements.WriteLine.Text%2A> свойства» службы: Reply sent.»  
  
14. Перетащите действие <xref:System.Activities.Statements.WriteLine> в нижнюю область рабочего процесса и задайте для свойства <xref:System.Activities.Statements.WriteLine.Text%2A> значение "Service: Workflow ends, press ENTER to exit".  
  
     Завершенный рабочий процесс службы должен выглядеть следующим образом:  
  
     ![Полный рабочий процесс службы](../../../../docs/framework/wcf/feature-details/media/servicecomplete.jpg "ServiceComplete")  
  
### <a name="implement-the-workflow-client"></a>Реализуйте клиент рабочего процесса  
  
1.  Добавьте новое приложение WCF Workflow с именем `WorkflowClient` к проекту `Common`. Для этого щелкните правой `Common` проекта, выберите **добавить**, **новый элемент...** Выберите **рабочего процесса** под **установленные шаблоны** и выберите **действия**.  
  
     ![Добавление проекта действия](../../../../docs/framework/wcf/feature-details/media/addactivity.JPG "AddActivity")  
  
2.  Перетащите действие <xref:System.Activities.Statements.Sequence> в область конструктора.  
  
3.  В действии <xref:System.Activities.Statements.Sequence> перетащите действие <xref:System.Activities.Statements.WriteLine> и задайте для его свойства <xref:System.Activities.Statements.WriteLine.Text%2A> значение `"Client: Workflow starting"`. После этого рабочий процесс должен выглядеть так:  
  
     ![Добавление действия WriteLine](../../../../docs/framework/wcf/feature-details/media/clientaddwriteline.JPG "ClientAddWriteLine")  
  
4.  Перетащите действие <xref:System.Activities.Statements.TransactionScope> и поместите его после действия <xref:System.Activities.Statements.WriteLine>.  Выберите действие <xref:System.Activities.Statements.TransactionScope>, нажмите кнопку «Переменные» и добавьте следующие переменные.  
  
     ![Добавление переменных в TransactionScope](../../../../docs/framework/wcf/feature-details/media/tsvariables.JPG "TSVariables")  
  
5.  Перетащите действие <xref:System.Activities.Statements.Sequence> в текст действия <xref:System.Activities.Statements.TransactionScope>.  
  
6.  Перетащите действие `PrintTransactionInfo` в <xref:System.Activities.Statements.Sequence>.  
  
7.  Перетаскивание <xref:System.Activities.Statements.WriteLine> действия после `PrintTransactionInfo` и задайте его <xref:System.Activities.Statements.WriteLine.Text%2A> значение «Client: Beginning Send». После этого рабочий процесс должен выглядеть так:  
  
     ![Добавление действий](../../../../docs/framework/wcf/feature-details/media/clientaddcbswriteline.JPG "ClientAddCBSWriteLine")  
  
8.  Перетащите действие <xref:System.ServiceModel.Activities.Send>, поместите его после действия <xref:System.Activities.Statements.Assign> и задайте следующие свойства:  
  
    |Свойство|Значение|  
    |--------------|-----------|  
    |EndpointConfigurationName|workflowServiceEndpoint|  
    |OperationName|StartSample|  
    |ServiceContractName|ITransactionSample|  
  
     После этого рабочий процесс должен выглядеть так:  
  
     ![Задание свойств действия Send](../../../../docs/framework/wcf/feature-details/media/clientsendsettings.JPG "ClientSendSettings")  
  
9. Нажмите кнопку **определить...**  ссылку и задайте следующие параметры:  
  
     ![Параметры сообщения действия send](../../../../docs/framework/wcf/feature-details/media/sendmessagesettings.JPG "SendMessageSettings")  
  
10. Щелкните правой кнопкой мыши <xref:System.ServiceModel.Activities.Send> действие и выберите **создать ReceiveReply**. Действие <xref:System.ServiceModel.Activities.ReceiveReply> будет автоматически помещено после действия <xref:System.ServiceModel.Activities.Send>.  
  
11. Щелкните ссылку «Определить...» в действии ReceiveReplyForSend и задайте следующие параметры:  
  
     ![Задание параметров сообщения ReceiveForSend](../../../../docs/framework/wcf/feature-details/media/clientreplymessagesettings.JPG "ClientReplyMessageSettings")  
  
12. Перетащите действие <xref:System.Activities.Statements.WriteLine>, поместите его между действиями <xref:System.ServiceModel.Activities.Send> и <xref:System.ServiceModel.Activities.ReceiveReply>, а также задайте для свойства <xref:System.Activities.Statements.WriteLine.Text%2A> значение "Client: Send complete".  
  
13. Перетащите действие <xref:System.Activities.Statements.WriteLine>, поместите его после действия <xref:System.ServiceModel.Activities.ReceiveReply> и задайте для свойства <xref:System.Activities.Statements.WriteLine.Text%2A> значение "Client side: Reply received = " + replyMessage.  
  
14. Перетащите действие `PrintTransactionInfo` и поместите его после действия <xref:System.Activities.Statements.WriteLine>.  
  
15. Перетащите действие <xref:System.Activities.Statements.WriteLine> в конец рабочего процесса и задайте для свойства <xref:System.Activities.Statements.WriteLine.Text%2A> значение "Client workflow ends". Завершенный рабочий процесс клиента должен выглядеть следующим образом на приведенной ниже схеме.  
  
     ![Полный рабочий процесс клиента](../../../../docs/framework/wcf/feature-details/media/clientcompleteworkflow.jpg "ClientCompleteWorkflow")  
  
16. Постройте решение.  
  
### <a name="create-the-service-application"></a>Создание приложения службы  
  
1.  Добавьте в решение новый проект консольного приложения с именем `Service`. Добавьте ссылки на следующие сборки:  
  
    1.  System.Activities.dll  
  
    2.  System.ServiceModel.dll  
  
    3.  System.ServiceModel.Activities.dll  
  
2.  Откройте созданный файл Program.cs и следующий код:  
  
    ```  
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
  
3.  Добавьте к проекту следующий файл app.config.  
  
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
  
1.  Добавьте в решение новый проект консольного приложения с именем `Client`. Добавьте ссылку на библиотеку System.Activities.dll.  
  
2.  Откройте файл program.cs и добавьте следующий код:  
  
    ```  
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
 [Службы рабочих процессов](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [Общие сведения о транзакциях Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/transactions-overview.md)  
 [Использование TransactedReceiveScope](../../../../docs/framework/windows-workflow-foundation/samples/use-of-transactedreceivescope.md)
