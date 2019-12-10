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
# <a name="transport-custom-transactions-over-udp-sample"></a><span data-ttu-id="e6f87-102">Транспорт: пример пользовательских транзакций по протоколу UDP</span><span class="sxs-lookup"><span data-stu-id="e6f87-102">Transport: Custom Transactions over UDP Sample</span></span>
<span data-ttu-id="e6f87-103">Этот пример основан на образце [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) в средстве[расширения транспорта](../../../../docs/framework/wcf/samples/transport-extensibility.md)Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="e6f87-103">This sample is based on the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample in the Windows Communication Foundation (WCF)[Transport Extensibility](../../../../docs/framework/wcf/samples/transport-extensibility.md).</span></span> <span data-ttu-id="e6f87-104">Он расширяет пример транспорта UDP за счет поддержки пользовательского потока транзакций и иллюстрирует использование свойства <xref:System.ServiceModel.Channels.TransactionMessageProperty>.</span><span class="sxs-lookup"><span data-stu-id="e6f87-104">It extends the UDP Transport sample to support custom transaction flow and demonstrates the use of the <xref:System.ServiceModel.Channels.TransactionMessageProperty> property.</span></span>  
  
## <a name="code-changes-in-the-udp-transport-sample"></a><span data-ttu-id="e6f87-105">Изменения кода в примере транспорта UDP</span><span class="sxs-lookup"><span data-stu-id="e6f87-105">Code Changes in the UDP Transport Sample</span></span>  
 <span data-ttu-id="e6f87-106">Чтобы продемонстрировать поток транзакций, в этом примере изменен контракт службы для `ICalculatorContract`. Здесь этот контракт требует область транзакции для `CalculatorService.Add()`.</span><span class="sxs-lookup"><span data-stu-id="e6f87-106">To demonstrate transaction flow, the sample changes the service contract for `ICalculatorContract` to require a transaction scope for `CalculatorService.Add()`.</span></span> <span data-ttu-id="e6f87-107">Кроме того, в контракт операции `System.Guid` добавлен параметр `Add`.</span><span class="sxs-lookup"><span data-stu-id="e6f87-107">The sample also adds an extra `System.Guid` parameter to the contract of the `Add` operation.</span></span> <span data-ttu-id="e6f87-108">Этот параметр используется для передачи службе идентификатора транзакции клиента.</span><span class="sxs-lookup"><span data-stu-id="e6f87-108">This parameter is used to pass the identifier of the client transaction to the service.</span></span>  
  
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
  
 <span data-ttu-id="e6f87-109">В примере [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) для передачи сообщений между клиентом и службой используются пакеты UDP.</span><span class="sxs-lookup"><span data-stu-id="e6f87-109">The [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample uses UDP packets to pass messages between a client and a service.</span></span> <span data-ttu-id="e6f87-110">В [примере "Транспорт: пользовательский транспорт](../../../../docs/framework/wcf/samples/transport-custom-transactions-over-udp-sample.md) " используется тот же механизм передачи сообщений, но при передаче транзакции он вставляется в пакет UDP вместе с закодированным сообщением.</span><span class="sxs-lookup"><span data-stu-id="e6f87-110">The [Transport: Custom Transport Sample](../../../../docs/framework/wcf/samples/transport-custom-transactions-over-udp-sample.md) uses the same mechanism to transport messages, but when a transaction is flowed, it is inserted into the UDP packet along with the encoded message.</span></span>  
  
```csharp  
byte[] txmsgBuffer = TransactionMessageBuffer.WriteTransactionMessageBuffer(txPropToken, messageBuffer);  
  
int bytesSent = this.socket.SendTo(txmsgBuffer, 0, txmsgBuffer.Length, SocketFlags.None, this.remoteEndPoint);  
```  
  
 <span data-ttu-id="e6f87-111">`TransactionMessageBuffer.WriteTransactionMessageBuffer` - вспомогательный метод, содержащий новые функции для слияния маркера распространения для текущей транзакции с сущностью сообщения и его помещения в буфер.</span><span class="sxs-lookup"><span data-stu-id="e6f87-111">`TransactionMessageBuffer.WriteTransactionMessageBuffer` is a helper method that contains new functionality to merge the propagation token for the current transaction with the message entity and place it into a buffer.</span></span>  
  
 <span data-ttu-id="e6f87-112">Для настраиваемого транспорта потока транзакций клиентская реализация должна узнать, какие операции службы нуждаются в потоке транзакций и передать эти сведения в WCF.</span><span class="sxs-lookup"><span data-stu-id="e6f87-112">For custom transaction flow transport, the client implementation must know what service operations require transaction flow and to pass this information to WCF.</span></span> <span data-ttu-id="e6f87-113">Должен быть и механизм для передачи транзакции пользователя на транспортный уровень.</span><span class="sxs-lookup"><span data-stu-id="e6f87-113">There should also be a mechanism for transmitting the user transaction to the transport layer.</span></span> <span data-ttu-id="e6f87-114">В этом примере для получения этих сведений используется "инспекторы сообщений WCF".</span><span class="sxs-lookup"><span data-stu-id="e6f87-114">This sample uses "WCF message inspectors" to obtain this information.</span></span> <span data-ttu-id="e6f87-115">Инспектор сообщений клиента, реализованный здесь, называется `TransactionFlowInspector` и выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="e6f87-115">The client message inspector implemented here, which is called `TransactionFlowInspector`, performs the following tasks:</span></span>  
  
- <span data-ttu-id="e6f87-116">Определяет, следует ли создать поток транзакции для данного действия сообщения (это происходит в `IsTxFlowRequiredForThisOperation()`);</span><span class="sxs-lookup"><span data-stu-id="e6f87-116">Determines whether a transaction must be flowed for a given message action (this takes place in `IsTxFlowRequiredForThisOperation()`).</span></span>  
  
- <span data-ttu-id="e6f87-117">Присоединяет к сообщению текущую внешнюю транзакцию с помощью `TransactionFlowProperty`, если транзакцию нужно заключить в поток (это делается в `BeforeSendRequest()`).</span><span class="sxs-lookup"><span data-stu-id="e6f87-117">Attaches the current ambient transaction to the message using `TransactionFlowProperty`, if a transaction is required to be flowed (this is done in `BeforeSendRequest()`).</span></span>  
  
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
  
 <span data-ttu-id="e6f87-118">Сам `TransactionFlowInspector` передается инфраструктуре с помощью пользовательского поведения `TransactionFlowBehavior`.</span><span class="sxs-lookup"><span data-stu-id="e6f87-118">The `TransactionFlowInspector` itself is passed to the framework using a custom behavior: the `TransactionFlowBehavior`.</span></span>  
  
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
  
 <span data-ttu-id="e6f87-119">При наличии вышеуказанного механизма пользовательский код создает область `TransactionScope` перед вызовом операции службы.</span><span class="sxs-lookup"><span data-stu-id="e6f87-119">With the preceding mechanism in place, the user code creates a `TransactionScope` before calling the service operation.</span></span> <span data-ttu-id="e6f87-120">Инспектор сообщений следит, чтобы транзакция была передана транспорту, если она должна быть заключена в поток для операции службы.</span><span class="sxs-lookup"><span data-stu-id="e6f87-120">The message inspector ensures that the transaction is passed to the transport in case it is required to be flowed to the service operation.</span></span>  
  
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
  
 <span data-ttu-id="e6f87-121">После получения от клиента пакета UPD служба десериализует его, чтобы извлечь сообщение и, возможно, транзакцию.</span><span class="sxs-lookup"><span data-stu-id="e6f87-121">Upon receiving a UDP packet from the client, the service deserializes it to extract the message and possibly a transaction.</span></span>  
  
```csharp  
count = listenSocket.EndReceiveFrom(result, ref dummy);  
  
// read the transaction and message                       TransactionMessageBuffer.ReadTransactionMessageBuffer(buffer, count, out transaction, out msg);  
```  
  
 <span data-ttu-id="e6f87-122">`TransactionMessageBuffer.ReadTransactionMessageBuffer()` - это вспомогательный метод, обращающий процесс сериализации, выполняемый `TransactionMessageBuffer.WriteTransactionMessageBuffer()`.</span><span class="sxs-lookup"><span data-stu-id="e6f87-122">`TransactionMessageBuffer.ReadTransactionMessageBuffer()` is the helper method that reverses the serialization process performed by `TransactionMessageBuffer.WriteTransactionMessageBuffer()`.</span></span>  
  
 <span data-ttu-id="e6f87-123">Если транзакция получена в потоке, она присоединяется к сообщению в свойстве `TransactionMessageProperty`.</span><span class="sxs-lookup"><span data-stu-id="e6f87-123">If a transaction was flowed in, it is appended to the message in the `TransactionMessageProperty`.</span></span>  
  
```csharp  
message = MessageEncoderFactory.Encoder.ReadMessage(msg, bufferManager);  
  
if (transaction != null)  
{  
       TransactionMessageProperty.Set(transaction, message);  
}  
```  
  
 <span data-ttu-id="e6f87-124">Это обеспечивает принятие диспетчером транзакции в момент распределения и использование ее при вызове операции службы, которой адресовано сообщение.</span><span class="sxs-lookup"><span data-stu-id="e6f87-124">This ensures that the dispatcher picks up the transaction at dispatch time and uses it when calling the service operation addressed by the message.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e6f87-125">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="e6f87-125">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="e6f87-126">Чтобы выполнить сборку решения, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e6f87-126">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="e6f87-127">Текущий пример должен выполняться аналогично примеру [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) .</span><span class="sxs-lookup"><span data-stu-id="e6f87-127">The current sample should be run similarly to the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span> <span data-ttu-id="e6f87-128">Для его запуска запустите службу с UdpTestService.exe.</span><span class="sxs-lookup"><span data-stu-id="e6f87-128">To run it, start the service with UdpTestService.exe.</span></span> <span data-ttu-id="e6f87-129">Если вы используете Windows Vista, необходимо запустить службу с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="e6f87-129">If you are running Windows Vista, you must start the service with elevated privileges.</span></span> <span data-ttu-id="e6f87-130">Для этого щелкните правой кнопкой мыши файл Удптестсервице. exe в проводнике и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="e6f87-130">To do so, right-click UdpTestService.exe in File Explorer and click **Run as administrator**.</span></span>  
  
3. <span data-ttu-id="e6f87-131">Получатся следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="e6f87-131">This produces the following output.</span></span>  
  
    ```console  
    Testing Udp From Code.  
    Service is started from code...  
    Press <ENTER> to terminate the service and start service from config...  
    ```  
  
4. <span data-ttu-id="e6f87-132">В этот момент можно запустить клиент, выполнив UdpTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="e6f87-132">At this time, you can start the client by running UdpTestClient.exe.</span></span> <span data-ttu-id="e6f87-133">Результаты работы клиента таковы.</span><span class="sxs-lookup"><span data-stu-id="e6f87-133">The output produced by the client is as follows.</span></span>  
  
    ```console 
    0  
    3  
    6  
    9  
    12  
    Press <ENTER> to complete test.  
    ```  
  
5. <span data-ttu-id="e6f87-134">Вывод службы имеют следующий вид.</span><span class="sxs-lookup"><span data-stu-id="e6f87-134">The service output is as follows.</span></span>  
  
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
  
6. <span data-ttu-id="e6f87-135">Приложение службы отображает сообщение `The client transaction has flowed to the service`, если может сопоставить идентификатор, присланный клиентом в параметре `clientTransactionId` операции `CalculatorService.Add()`, идентификатору транзакции службы.</span><span class="sxs-lookup"><span data-stu-id="e6f87-135">The service application displays the message `The client transaction has flowed to the service` if it can match the transaction identifier sent by the client, in the `clientTransactionId` parameter of the `CalculatorService.Add()` operation, to the identifier of the service transaction.</span></span> <span data-ttu-id="e6f87-136">Сопоставление происходит, только если транзакция клиента доставлена службе в виде потока.</span><span class="sxs-lookup"><span data-stu-id="e6f87-136">A match is obtained only if the client transaction has flowed to the service.</span></span>  
  
7. <span data-ttu-id="e6f87-137">Для выполнения клиентского приложения относительно конечных точек, опубликованных с помощью конфигурации, нажмите в окне приложения службы клавишу ВВОД и снова запустите тестовый клиент.</span><span class="sxs-lookup"><span data-stu-id="e6f87-137">To run the client application against endpoints published using configuration, press ENTER on the service application window and then run the test client again.</span></span> <span data-ttu-id="e6f87-138">Служба должна предоставить следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="e6f87-138">You should see the following output on the service.</span></span>  
  
    ```console  
    Testing Udp From Config.  
    Service is started from config...  
    Press <ENTER> to terminate the service and exit...  
    ```  
  
8. <span data-ttu-id="e6f87-139">Выполнение клиента относительно службы теперь дает такие же результаты, как раньше.</span><span class="sxs-lookup"><span data-stu-id="e6f87-139">Running the client against the service now produces similar output as before.</span></span>  
  
9. <span data-ttu-id="e6f87-140">Для восстановления кода клиента и конфигурации с помощью Svcutil.exe запустите приложение службы и выполните следующую команду Svcutil.exe из корневого каталога образца.</span><span class="sxs-lookup"><span data-stu-id="e6f87-140">To regenerate the client code and configuration using Svcutil.exe, start the service application and then run the following Svcutil.exe command from the root directory of the sample.</span></span>  
  
    ```console  
    svcutil http://localhost:8000/udpsample/ /reference:UdpTransport\bin\UdpTransport.dll /svcutilConfig:svcutil.exe.config  
    ```  
  
10. <span data-ttu-id="e6f87-141">Обратите внимание, что Svcutil.exe не создает конфигурацию расширения привязки для `sampleProfileUdpBinding`, поэтому ее нужно добавить вручную.</span><span class="sxs-lookup"><span data-stu-id="e6f87-141">Note that Svcutil.exe does not generate the binding extension configuration for the `sampleProfileUdpBinding`; you must add it manually.</span></span>  
  
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
> <span data-ttu-id="e6f87-142">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e6f87-142">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e6f87-143">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e6f87-143">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="e6f87-144">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="e6f87-144">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e6f87-145">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="e6f87-145">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Transactions\TransactionMessagePropertyUDPTransport`  
  
## <a name="see-also"></a><span data-ttu-id="e6f87-146">См. также:</span><span class="sxs-lookup"><span data-stu-id="e6f87-146">See also</span></span>

- [<span data-ttu-id="e6f87-147">Транспорт: UDP</span><span class="sxs-lookup"><span data-stu-id="e6f87-147">Transport: UDP</span></span>](../../../../docs/framework/wcf/samples/transport-udp.md)
