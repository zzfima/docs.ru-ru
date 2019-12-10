---
title: 'Транспорт: пример пользовательских транзакций по протоколу UDP'
ms.date: 03/30/2017
ms.assetid: 6cebf975-41bd-443e-9540-fd2463c3eb23
ms.openlocfilehash: 00e6d593e185cd09ea66e88f38cf1d8e71785704
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960410"
---
# <a name="transport-custom-transactions-over-udp-sample"></a>Транспорт: пример пользовательских транзакций по протоколу UDP
Этот пример основан на образце [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) в средстве[расширения транспорта](../../../../docs/framework/wcf/samples/transport-extensibility.md)Windows Communication Foundation (WCF). Он расширяет пример транспорта UDP за счет поддержки пользовательского потока транзакций и иллюстрирует использование свойства <xref:System.ServiceModel.Channels.TransactionMessageProperty>.  
  
## <a name="code-changes-in-the-udp-transport-sample"></a>Изменения кода в примере транспорта UDP  
 Чтобы продемонстрировать поток транзакций, в этом примере изменен контракт службы для `ICalculatorContract`. Здесь этот контракт требует область транзакции для `CalculatorService.Add()`. Кроме того, в контракт операции `System.Guid` добавлен параметр `Add`. Этот параметр используется для передачи службе идентификатора транзакции клиента.  
  
```csharp  
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
  
 В примере [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) для передачи сообщений между клиентом и службой используются пакеты UDP. В [примере "Транспорт: пользовательский транспорт](../../../../docs/framework/wcf/samples/transport-custom-transactions-over-udp-sample.md) " используется тот же механизм передачи сообщений, но при передаче транзакции он вставляется в пакет UDP вместе с закодированным сообщением.  
  
```csharp  
byte[] txmsgBuffer = TransactionMessageBuffer.WriteTransactionMessageBuffer(txPropToken, messageBuffer);  
  
int bytesSent = this.socket.SendTo(txmsgBuffer, 0, txmsgBuffer.Length, SocketFlags.None, this.remoteEndPoint);  
```  
  
 `TransactionMessageBuffer.WriteTransactionMessageBuffer` - вспомогательный метод, содержащий новые функции для слияния маркера распространения для текущей транзакции с сущностью сообщения и его помещения в буфер.  
  
 Для настраиваемого транспорта потока транзакций клиентская реализация должна узнать, какие операции службы нуждаются в потоке транзакций и передать эти сведения в WCF. Должен быть и механизм для передачи транзакции пользователя на транспортный уровень. В этом примере для получения этих сведений используется "инспекторы сообщений WCF". Инспектор сообщений клиента, реализованный здесь, называется `TransactionFlowInspector` и выполняет следующие задачи:  
  
- Определяет, следует ли создать поток транзакции для данного действия сообщения (это происходит в `IsTxFlowRequiredForThisOperation()`);  
  
- Присоединяет к сообщению текущую внешнюю транзакцию с помощью `TransactionFlowProperty`, если транзакцию нужно заключить в поток (это делается в `BeforeSendRequest()`).  
  
```csharp  
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
  
```csharp  
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
  
 При наличии вышеуказанного механизма пользовательский код создает область `TransactionScope` перед вызовом операции службы. Инспектор сообщений следит, чтобы транзакция была передана транспорту, если она должна быть заключена в поток для операции службы.  
  
```csharp  
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
  
```csharp  
count = listenSocket.EndReceiveFrom(result, ref dummy);  
  
// read the transaction and message                       TransactionMessageBuffer.ReadTransactionMessageBuffer(buffer, count, out transaction, out msg);  
```  
  
 `TransactionMessageBuffer.ReadTransactionMessageBuffer()` - это вспомогательный метод, обращающий процесс сериализации, выполняемый `TransactionMessageBuffer.WriteTransactionMessageBuffer()`.  
  
 Если транзакция получена в потоке, она присоединяется к сообщению в свойстве `TransactionMessageProperty`.  
  
```csharp  
message = MessageEncoderFactory.Encoder.ReadMessage(msg, bufferManager);  
  
if (transaction != null)  
{  
       TransactionMessageProperty.Set(transaction, message);  
}  
```  
  
 Это обеспечивает принятие диспетчером транзакции в момент распределения и использование ее при вызове операции службы, которой адресовано сообщение.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Чтобы выполнить сборку решения, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2. Текущий пример должен выполняться аналогично примеру [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) . Для его запуска запустите службу с UdpTestService.exe. Если вы используете Windows Vista, необходимо запустить службу с повышенными привилегиями. Для этого щелкните правой кнопкой мыши файл Удптестсервице. exe в проводнике и выберите команду **Запуск от имени администратора**.  
  
3. Получатся следующие результаты.  
  
    ```console  
    Testing Udp From Code.  
    Service is started from code...  
    Press <ENTER> to terminate the service and start service from config...  
    ```  
  
4. В этот момент можно запустить клиент, выполнив UdpTestClient.exe. Результаты работы клиента таковы.  
  
    ```console 
    0  
    3  
    6  
    9  
    12  
    Press <ENTER> to complete test.  
    ```  
  
5. Вывод службы имеют следующий вид.  
  
    ```console 
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
  
6. Приложение службы отображает сообщение `The client transaction has flowed to the service`, если может сопоставить идентификатор, присланный клиентом в параметре `clientTransactionId` операции `CalculatorService.Add()`, идентификатору транзакции службы. Сопоставление происходит, только если транзакция клиента доставлена службе в виде потока.  
  
7. Для выполнения клиентского приложения относительно конечных точек, опубликованных с помощью конфигурации, нажмите в окне приложения службы клавишу ВВОД и снова запустите тестовый клиент. Служба должна предоставить следующие результаты.  
  
    ```console  
    Testing Udp From Config.  
    Service is started from config...  
    Press <ENTER> to terminate the service and exit...  
    ```  
  
8. Выполнение клиента относительно службы теперь дает такие же результаты, как раньше.  
  
9. Для восстановления кода клиента и конфигурации с помощью Svcutil.exe запустите приложение службы и выполните следующую команду Svcutil.exe из корневого каталога образца.  
  
    ```console  
    svcutil http://localhost:8000/udpsample/ /reference:UdpTransport\bin\UdpTransport.dll /svcutilConfig:svcutil.exe.config  
    ```  
  
10. Обратите внимание, что Svcutil.exe не создает конфигурацию расширения привязки для `sampleProfileUdpBinding`, поэтому ее нужно добавить вручную.  
  
    ```xml  
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
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Transactions\TransactionMessagePropertyUDPTransport`  
  
## <a name="see-also"></a>См. также:

- [Транспорт: UDP](../../../../docs/framework/wcf/samples/transport-udp.md)
