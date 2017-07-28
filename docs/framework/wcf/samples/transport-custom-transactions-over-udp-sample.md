---
title: "Транспорт: образец пользовательских транзакций по протоколу UDP | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6cebf975-41bd-443e-9540-fd2463c3eb23
caps.latest.revision: 21
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 21
---
# Транспорт: образец пользовательских транзакций по протоколу UDP
Этот пример основан на примере [Транспорт: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) из [Расширяемость транспорта](../../../../docs/framework/wcf/samples/transport-extensibility.md)[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Он расширяет образец транспорта определяемой пользователем процедуры за счет поддержки пользовательского потока транзакций и иллюстрирует использование свойства <xref:System.ServiceModel.Channels.TransactionMessageProperty>.  
  
## Изменения кода в образце транспорта UDP  
 Чтобы продемонстрировать поток транзакций, в этом образце изменен контракт службы для `ICalculatorContract`. Здесь этот контракт требует область транзакции для `CalculatorService.Add()`.Кроме того, в контракт операции `Add` добавлен параметр `System.Guid`.Этот параметр используется для передачи службе идентификатора транзакции клиента.  
  
```  
class CalculatorService : IDatagramContract, ICalculatorContract  
{  
    [OperationBehavior(TransactionScopeRequired=true)]  
    public int Add(int x, int y, Guid clientTransactionId)  
    {  
        if(Transaction.Current.TransactionInformation.DistributedIdentifier == clientTransactionId)  
    {  
        Console.WriteLine("The client transaction has flowed to the service");  
    }  
    else  
    {  
     Console.WriteLine("The client transaction has NOT flowed to the service");  
    }  
  
    Console.WriteLine("   adding {0} + {1}", x, y);              
    return (x + y);  
    }  
  
    [...]  
}  
```  
  
 Образец [Транспорт: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) использует пакеты UDP для обмена сообщениями между клиентом и службой.Образец [Transport: Custom Transport Sample](../../../../docs/framework/wcf/samples/transport-custom-transactions-over-udp-sample.md) использует для транспортировки сообщений тот же механизм, но при создании потока транзакции она вставляется в пакет UDP вместе с закодированным сообщением.  
  
```  
byte[] txmsgBuffer =                TransactionMessageBuffer.WriteTransactionMessageBuffer(txPropToken, messageBuffer);  
  
int bytesSent = this.socket.SendTo(txmsgBuffer, 0, txmsgBuffer.Length, SocketFlags.None, this.remoteEndPoint);  
```  
  
 `TransactionMessageBuffer.WriteTransactionMessageBuffer` — вспомогательный метод, содержащий новые функции для слияния маркера распространения для текущей транзакции с сущностью сообщения и его помещения в буфер.  
  
 Для транспорта пользовательского потока транзакций реализация клиента должна знать, какие операции службы нуждаются в потоке транзакций, и передавать эти сведения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].Должен быть и механизм для передачи транзакции пользователя на транспортный уровень.Данный образец использует для получения этих сведений "инспекторы сообщений [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]".Инспектор сообщений клиента, реализованный здесь, называется `TransactionFlowInspector` и выполняет следующие задачи:  
  
-   Определяет, следует ли создать поток транзакции для данного действия сообщения \(это происходит в `IsTxFlowRequiredForThisOperation()`\);  
  
-   Присоединяет к сообщению текущую внешнюю транзакцию с помощью `TransactionFlowProperty`, если транзакцию нужно заключить в поток \(это делается в `BeforeSendRequest()`\).  
  
```  
public class TransactionFlowInspector : IClientMessageInspector  
{  
   void IClientMessageInspector.AfterReceiveReply(ref           System.ServiceModel.Channels.Message reply, object correlationState)  
  {  
  }  
  
   public object BeforeSendRequest(ref System.ServiceModel.Channels.Message request, System.ServiceModel.IClientChannel channel)  
   {  
       // obtain the tx propagation token  
       byte[] propToken = null;             
       if (Transaction.Current != null && IsTxFlowRequiredForThisOperation(request.Headers.Action))  
       {  
           try  
           {  
               propToken = TransactionInterop.GetTransmitterPropagationToken(Transaction.Current);  
           }  
           catch (TransactionException e)  
           {  
              throw new CommunicationException("TransactionInterop.GetTransmitterPropagationToken failed.", e);  
           }  
       }  
  
      // set the propToken on the message in a TransactionFlowProperty  
       TransactionFlowProperty.Set(propToken, request);  
  
       return null;              
    }  
  }  
  
  static bool IsTxFlowRequiredForThisOperation(String action)  
 {  
       // In general, this should contain logic to identify which operations (actions)      require transaction flow.  
      [...]  
 }  
}  
  
```  
  
 Сам `TransactionFlowInspector` передается инфраструктуре с помощью пользовательского поведения `TransactionFlowBehavior`.  
  
```  
public class TransactionFlowBehavior : IEndpointBehavior  
{  
       public void AddBindingParameters(ServiceEndpoint endpoint,            System.ServiceModel.Channels.BindingParameterCollection bindingParameters)  
      {  
      }  
  
       public void ApplyClientBehavior(ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.ClientRuntime clientRuntime)  
      {  
            TransactionFlowInspector inspector = new TransactionFlowInspector();  
            clientRuntime.MessageInspectors.Add(inspector);  
      }  
  
      public void ApplyDispatchBehavior(ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.EndpointDispatcher endpointDispatcher)  
     {  
     }  
  
      public void Validate(ServiceEndpoint endpoint)  
      {  
      }  
}  
```  
  
 При наличии вышеуказанного механизма пользовательский код создает область `TransactionScope` перед вызовом операции службы.Инспектор сообщений следит, чтобы транзакция была передана транспорту, если она должна быть заключена в поток для операции службы.  
  
```  
CalculatorContractClient calculatorClient = new CalculatorContractClient("SampleProfileUdpBinding_ICalculatorContract");  
calculatorClient.Endpoint.Behaviors.Add(new TransactionFlowBehavior());               
  
try  
{  
       for (int i = 0; i < 5; ++i)  
      {  
              // call the 'Add' service operation under a transaction scope  
             using (TransactionScope ts = new TransactionScope())  
             {  
        [...]  
        Console.WriteLine(calculatorClient.Add(i, i * 2));  
         }  
      }               
       calculatorClient.Close();  
}  
catch (TimeoutException)  
{  
    calculatorClient.Abort();  
}  
catch (CommunicationException)  
{  
    calculatorClient.Abort();  
}  
catch (Exception)  
{  
    calculatorClient.Abort();  
    throw;  
}  
```  
  
 После получения от клиента пакета UPD служба десериализует его, чтобы извлечь сообщение и, возможно, транзакцию.  
  
```  
count = listenSocket.EndReceiveFrom(result, ref dummy);  
  
// read the transaction and message                       TransactionMessageBuffer.ReadTransactionMessageBuffer(buffer, count, out transaction, out msg);  
```  
  
 `TransactionMessageBuffer.ReadTransactionMessageBuffer()` — это вспомогательный метод, обращающий процесс сериализации, выполняемый `TransactionMessageBuffer.WriteTransactionMessageBuffer()`.  
  
 Если транзакция получена в потоке, она присоединяется к сообщению в свойстве `TransactionMessageProperty`.  
  
```  
message = MessageEncoderFactory.Encoder.ReadMessage(msg, bufferManager);  
  
if (transaction != null)  
{  
       TransactionMessageProperty.Set(transaction, message);  
}  
```  
  
 Это обеспечивает принятие диспетчером транзакции в момент распределения и использование ее при вызове операции службы, которой адресовано сообщение.  
  
#### Настройка, построение и выполнение образца  
  
1.  Чтобы выполнить построение решения, следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2.  Этот образец следует выполнять так же, как образец [Транспорт: UDP](../../../../docs/framework/wcf/samples/transport-udp.md).Для его запуска запустите службу с UdpTestService.exe.В случае использования [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)] службу необходимо запустить с более высоким уровнем привилегий.Для этого в проводнике щелкните правой кнопкой мыши UdpTestService.exe в [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] и выберите **Запуск от имени администратора**.  
  
3.  Получатся следующие результаты.  
  
    ```  
    Testing Udp From Code.  
    Service is started from code...  
    Press <ENTER> to terminate the service and start service from config...  
    ```  
  
4.  В этот момент можно запустить клиент, выполнив UdpTestClient.exe.Результаты работы клиента таковы.  
  
    ```  
    0  
    3  
    6  
    9  
    12  
    Press <ENTER> to complete test.  
    ```  
  
5.  Вывод службы имеют следующий вид.  
  
    ```  
    Hello, world!  
    Hello, world!  
    Hello, world!  
    Hello, world!  
    Hello, world!  
    The client transaction has flowed to the service  
       adding 0 + 0  
    The client transaction has flowed to the service  
       adding 1 + 2  
    The client transaction has flowed to the service  
       adding 2 + 4  
    The client transaction has flowed to the service  
       adding 3 + 6  
    The client transaction has flowed to the service  
       adding 4 + 8  
    ```  
  
6.  Приложение службы отображает сообщение `The client transaction has flowed to the service`, если может сопоставить идентификатор, присланный клиентом в параметре `clientTransactionId` операции `CalculatorService.Add()`, идентификатору транзакции службы.Сопоставление происходит, только если транзакция клиента доставлена службе в виде потока.  
  
7.  Для выполнения клиентского приложения относительно конечных точек, опубликованных с помощью конфигурации, нажмите в окне приложения службы клавишу ВВОД и снова запустите тестовый клиент.Служба должна предоставить следующие результаты.  
  
    ```  
    Testing Udp From Config.  
    Service is started from config...  
    Press <ENTER> to terminate the service and exit...  
    ```  
  
8.  Выполнение клиента относительно службы теперь дает такие же результаты, как раньше.  
  
9. Для восстановления кода клиента и конфигурации с помощью Svcutil.exe запустите приложение службы и выполните следующую команду Svcutil.exe из корневого каталога образца.  
  
    ```  
    svcutil http://localhost:8000/udpsample/ /reference:UdpTranport\bin\UdpTransport.dll /svcutilConfig:svcutil.exe.config  
    ```  
  
10. Обратите внимание, что Svcutil.exe не создает конфигурацию расширения привязки для `sampleProfileUdpBinding`, поэтому ее нужно добавить вручную.  
  
    ```  
    <configuration>  
        <system.serviceModel>      
            …  
            <extensions>  
                <!-- This was added manually because svcutil.exe does not add this extension to the file -->  
                <bindingExtensions>  
                    <add name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport" />  
                </bindingExtensions>  
            </extensions>  
        </system.serviceModel>  
    </configuration>  
    ```  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Extensibility\Transactions\TransactionMessagePropertyUDPTransport`  
  
## См. также  
 [Транспорт: UDP](../../../../docs/framework/wcf/samples/transport-udp.md)