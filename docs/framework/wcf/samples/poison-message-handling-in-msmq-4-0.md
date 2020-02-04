---
title: Обработка подозрительных сообщений в MSMQ 4.0
ms.date: 03/30/2017
ms.assetid: ec8d59e3-9937-4391-bb8c-fdaaf2cbb73e
ms.openlocfilehash: cc4da0deea0de2cd8b3bb8e8f2ba9b8a17e3cc60
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2020
ms.locfileid: "76919401"
---
# <a name="poison-message-handling-in-msmq-40"></a>Обработка подозрительных сообщений в MSMQ 4.0
В этом образце демонстрируется обработка подозрительных сообщений в службе. Этот пример основан на образце [транзакционной привязки MSMQ](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) . В этом образце используется привязка `netMsmqBinding`. Служба представляет собой резидентное консольное приложение, позволяющее наблюдать за получением службой сообщений из очереди.

 При использовании очередей клиент взаимодействует со службой посредством очереди. Конкретно, клиент отправляет сообщения в очередь. Служба получает сообщения из очереди. Поэтому клиенту и службе не обязательно выполняться одновременно, чтобы взаимодействовать посредством очереди.

 Подозрительное сообщение - это сообщение, которое повторно считывается из очереди, если служба, читающая сообщение, не может его обработать и завершает транзакцию, в рамках которой считывается сообщение. В таких случаях предпринимается еще одна попытка считывания сообщения. Теоретически этот процесс может продолжаться бесконечно, если существует проблема с сообщением. Обратите внимание, что это происходит только при использовании транзакций для чтения сообщений из очереди и вызове операции службы.

 Возможность поддержки обнаружения подозрительных сообщений (от ограниченного до полного) привязкой NetMsmqBinding зависит от версии MSMQ. После того как сообщение было распознано как подозрительное, оно может обрабатываться несколькими способами. Поддержка обработки подозрительных сообщений (от ограниченной до полной) привязкой NetMsmqBinding зависит от версии MSMQ.

 В этом примере показаны ограниченные опасные средства, предоставляемые на платформе Windows Server 2003 и Windows XP, а также полностью опасные средства, предоставляемые в Windows Vista. В обоих образцах целью является перемещение подозрительного сообщения из одной очереди в другую, которая затем может быть обслужена службой подозрительных сообщений.

## <a name="msmq-v40-poison-handling-sample"></a>Образец обработки подозрительных сообщений в MSMQ v4.0.
 В Windows Vista служба MSMQ предоставляет возможность использования вложенных очередей, которые можно использовать для хранения подозрительных сообщений. В этом примере демонстрируется Лучшая практика работы с подозрительными сообщениями с помощью Windows Vista.

 Обнаружение подозрительных сообщений в Windows Vista является довольно сложным. Обнаружению таких сообщений способствуют три свойства. Свойство <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> обозначает, сколько раз заданное сообщение перечитывается из очереди и передается приложению для обработки. Сообщение повторно считывается из очереди, если оно повторно помещено в очередь, потому что его не удается передать приложению, или приложение выполняет откат транзакции в операции службы. Свойство <xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A> указывает, сколько раз сообщение перемещается в очередь повторных попыток. При достижении <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> сообщение перемещается в очередь повторных попыток. Свойство <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A> - это промежуток времени, по истечении которого сообщение перемещается из очереди повторных попыток в основную очередь. Счетчик <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> обнуляется. Делается еще одна попытка прочесть сообщение. Если все попытки прочтения сообщения оказываются неудачными, сообщение помечается как подозрительное.

 После этого сообщение обрабатывается в соответствии с параметрами, заданными в перечислении <xref:System.ServiceModel.MsmqBindingBase.ReceiveErrorHandling%2A>. Ниже еще раз перечислены возможные значения.

- Fault (по умолчанию): происходит сбой прослушивателя и узла службы.

- Drop: сообщение отбрасывается.

- Move: сообщение перемещается во вложенную очередь подозрительных сообщений. Это значение доступно только в Windows Vista.

- Reject: сообщение отклоняется и возвращается в очередь недоставленных сообщений отправителя. Это значение доступно только в Windows Vista.

 В этом образце демонстрируется использование команды `Move` для перемещения опасного сообщения о сбое. Команда `Move` перемещает сообщение во вложенную очередь подозрительных сообщений.

 Контракт службы `IOrderProcessor` определяет одностороннюю службу, которую можно использовать с очередями.

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true)]
    void SubmitPurchaseOrder(PurchaseOrder po);
}
```

 Операция службы отображает сообщение о том, что она обрабатывает заказ. Чтобы продемонстрировать возможность обработки подозрительных сообщений, операция службы `SubmitPurchaseOrder` создает исключение для отката транзакции в случайно выбранном вызове службы. В результате сообщение помещается обратно в очередь. В конечном счете это сообщение помечается как подозрительное. Конфигурация настроена для перемещения подозрительного сообщения во вложенную очередь подозрительных сообщений.

```csharp
// Service class that implements the service contract.
// Added code to write output to the console window.
public class OrderProcessorService : IOrderProcessor
{
    static Random r = new Random(137);

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po)
    {

        int randomNumber = r.Next(10);

        if (randomNumber % 2 == 0)
        {
            Orders.Add(po);
            Console.WriteLine("Processing {0} ", po);
        }
        else
        {
            Console.WriteLine("Aborting transaction, cannot process purchase order: " + po.PONumber);
            Console.WriteLine();
            throw new Exception("Cannot process purchase order: " + po.PONumber);
        }
    }

    public static void OnServiceFaulted(object sender, EventArgs e)
    {
        Console.WriteLine("Service Faulted");
    }

    // Host the service within this EXE console application.
    public static void Main()
    {
        // Get MSMQ queue name from app settings in configuration.
        string queueName = ConfigurationManager.AppSettings["queueName"];

        // Create the transacted MSMQ queue if necessary.
        if (!System.Messaging.MessageQueue.Exists(queueName))
            System.Messaging.MessageQueue.Create(queueName, true);

        // Get the base address that is used to listen for WS-MetaDataExchange requests.
        // This is useful to generate a proxy for the client.
        string baseAddress = ConfigurationManager.AppSettings["baseAddress"];

        // Create a ServiceHost for the OrderProcessorService type.
        ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService), new Uri(baseAddress));

        // Hook on to the service host faulted events.
        serviceHost.Faulted += new EventHandler(OnServiceFaulted);

        // Open the ServiceHostBase to create listeners and start listening for messages.
        serviceHost.Open();

        // The service can now be accessed.
        Console.WriteLine("The service is ready.");
        Console.WriteLine("Press <ENTER> to terminate service.");
        Console.WriteLine();
        Console.ReadLine();

        if(serviceHost.State != CommunicationState.Faulted) {
            serviceHost.Close();
        }

    }
}
```

 Конфигурация службы включает следующие свойства подозрительных сообщений: `receiveRetryCount`, `maxRetryCycles`, `retryCycleDelay` и `receiveErrorHandling`, как показано в следующем файле конфигурации.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <appSettings>
    <!-- Use appSetting to configure MSMQ queue name. -->
    <add key="queueName" value=".\private$\ServiceModelSamplesPoison" />
    <add key="baseAddress" value="http://localhost:8000/orderProcessor/poisonSample"/>
  </appSettings>
  <system.serviceModel>
    <services>
      <service
              name="Microsoft.ServiceModel.Samples.OrderProcessorService">
        <!-- Define NetMsmqEndpoint -->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesPoison"
                  binding="netMsmqBinding"
                  bindingConfiguration="PoisonBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
      </service>
    </services>

    <bindings>
      <netMsmqBinding>
        <binding name="PoisonBinding"
                 receiveRetryCount="0"
                 maxRetryCycles="1"
                 retryCycleDelay="00:00:05"
                 receiveErrorHandling="Move">
        </binding>
      </netMsmqBinding>
    </bindings>
  </system.serviceModel>
</configuration>
```

## <a name="processing-messages-from-the-poison-message-queue"></a>Обработка сообщений из очереди подозрительных сообщений
 Служба подозрительных сообщений считывает сообщения из конечной очереди подозрительных сообщений и обрабатывает их.

 Сообщения в очереди подозрительных сообщений - это сообщения, адресованные обрабатывающей сообщение службе, которая может отличаться от конечной точки службы подозрительных сообщений. Таким образом, когда служба подозрительных сообщений считывает сообщения из очереди, уровень канала WCF находит несоответствие в конечных точках и не отправляет сообщение. В этом случае сообщение адресуется службе, обрабатывающей заказы, но получает его служба подозрительных сообщений. Чтобы продолжать получать сообщение, даже если оно адресовано другой конечной точке, необходимо добавить поведение `ServiceBehavior` для фильтрации адресов, в котором критерием соответствия будет соответствие любой конечной точке службы, которой адресовано сообщение. Это необходимо для успешной обработки сообщений, считываемых из очереди подозрительных сообщений.

 Реализация самой службы подозрительных сообщений очень похожа на реализацию службы. Она реализует контракт и обрабатывает заказы. Ниже приведен пример кода.

```csharp
// Service class that implements the service contract.
// Added code to write output to the console window.
[ServiceBehavior(AddressFilterMode=AddressFilterMode.Any)]
public class OrderProcessorService : IOrderProcessor
{
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po)
    {
        Orders.Add(po);
        Console.WriteLine("Processing {0} ", po);
    }

    public static void OnServiceFaulted(object sender, EventArgs e)
    {
        Console.WriteLine("Service Faulted...exiting app");
        Environment.Exit(1);
    }

    // Host the service within this EXE console application.
    public static void Main()
    {

        // Create a ServiceHost for the OrderProcessorService type.
        ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService));

        // Hook on to the service host faulted events.
        serviceHost.Faulted += new EventHandler(OnServiceFaulted);

        serviceHost.Open();

        // The service can now be accessed.
        Console.WriteLine("The poison message service is ready.");
        Console.WriteLine("Press <ENTER> to terminate service.");
        Console.WriteLine();
        Console.ReadLine();

        // Close the ServiceHostBase to shutdown the service.
        if(serviceHost.State != CommunicationState.Faulted)
        {
            serviceHost.Close();
        }
    }
```

 В отличие от службы обработки заказов, которая считывает сообщения из очереди заказов, служба подозрительных сообщений считывает сообщения из вложенной очереди подозрительных сообщений. Очередь подозрительных сообщений вложена в основную очередь, называется "poison" и автоматически создается MSMQ. Для доступа к этой очереди следует указать имя основной очереди, ввести символ ";", а затем имя вложенной очереди, в данном случае - "poison", как показано в следующем образце конфигурации.

> [!NOTE]
> В образце для MSMQ v3.0 очередь подозрительных сообщений является не вложенной очередью, а очередью, в которую было перемещено сообщение.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.OrderProcessorService">
        <!-- Define NetMsmqEndpoint -->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesPoison;poison"
                  binding="netMsmqBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" >
        </endpoint>
      </service>
    </services>

  </system.serviceModel>
</configuration>
```

 При выполнении образца действия клиента, службы и службы подозрительных сообщений отображаются в окнах консоли. Можно видеть, как служба получает сообщения от клиента. Нажмите клавишу ВВОД в каждом окне консоли, чтобы завершить работу служб.

 Служба начинает работать, обрабатывать заказы и в произвольном порядке завершать обработку. Если появляется сообщение о том, что заказ обработан, можно снова запустить клиент для отправки другого сообщения, пока не будет видно, что служба действительно завершила обработку сообщения. В зависимости от заданных параметров подозрительных сообщений перед помещением сообщения в конечную очередь подозрительных сообщений предпринимается одна попытка его обработки.

```console
The service is ready.
Press <ENTER> to terminate service.

Processing Purchase Order: 0f063b71-93e0-42a1-aa3b-bca6c7a89546
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending

Processing Purchase Order: 5ef9a4fa-5a30-4175-b455-2fb1396095fa
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending

Aborting transaction, cannot process purchase order: 23e0b991-fbf9-4438-a0e2-20adf93a4f89
```

 Запустите службу подозрительных сообщений, чтобы считать подозрительное сообщение из очереди подозрительных сообщений. В этом примере служба подозрительных сообщений считывает сообщение и обрабатывает его. Можно видеть, что заказ на покупку, обработка которого была завершена и который был помечен как подозрительный, считывается службой подозрительных сообщений.

```console
The service is ready.
Press <ENTER> to terminate service.

Processing Purchase Order: 23e0b991-fbf9-4438-a0e2-20adf93a4f89
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending
```

#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца

1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

2. При первом запуске служба проверит наличие очереди. Если очередь отсутствует, служба ее создаст. Можно сначала запустить службу, чтобы создать очередь, либо создать ее с помощью диспетчера очередей MSMQ. Чтобы создать очередь в Windows 2008, выполните следующие шаги.

    1. Откройте диспетчер сервера в Visual Studio 2012.

    2. Разверните вкладку **функции** .

    3. Щелкните правой кнопкой мыши **частные очереди сообщений**и выберите **создать**, **Частная очередь**.

    4. Установите флажок **транзакционная** .

    5. Введите `ServiceModelSamplesTransacted` в качестве имени новой очереди.

3. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).

4. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, измените имена очередей, чтобы они отражали фактическое имя узла вместо localhost, и следуйте инструкциям в разделе [Запуск примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).

 По умолчанию с транспортом привязки `netMsmqBinding` безопасность включена. Тип безопасности транспорта определяется двумя свойствами: `MsmqAuthenticationMode` и `MsmqProtectionLevel`. По умолчанию задан режим проверки подлинности `Windows` и уровень защиты `Sign`. Чтобы служба MSMQ обеспечивала возможности проверки подлинности и подписывания, она должна входить в домен. При выполнении этого примера на компьютере, не входящем в домен, возникает следующая ошибка: "User's internal message queuing certificate does not exist" (не существует внутреннего сертификата очереди сообщений пользователя).

#### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup"></a>Выполнение образца на компьютере, входящем в рабочую группу

1. Если компьютер не входит в домен, отключите безопасность транспорта, задав для режима проверки подлинности и уровня защиты значение `None`, как показано в следующем образце конфигурации.

    ```xml
    <bindings>
        <netMsmqBinding>
            <binding name="TransactedBinding">
                <security mode="None"/>
            </binding>
        </netMsmqBinding>
    </bindings>
    ```

     Обеспечьте связь конечной точки с привязкой, задав атрибут bindingConfiguration конечной точки.

2. Перед выполнением примера убедитесь, что изменена конфигурация PoisonMessageServer, сервера и клиента.

    > [!NOTE]
    > Задание для `security mode` значения `None` эквивалентно заданию для параметров безопасности `MsmqAuthenticationMode`, `MsmqProtectionLevel` и `Message` значения `None`.  
  
3. Чтобы обеспечить обмен метаданными, необходимо зарегистрировать URL-адрес с привязкой http. Это требует выполнения службы в командном окне с повышенными привилегиями. В противном случае возникнет исключение, например: `Unhandled Exception: System.ServiceModel.AddressAccessDeniedException: HTTP could not register URL http://+:8000/ServiceModelSamples/service/. Your process does not have access rights to this namespace (see https://go.microsoft.com/fwlink/?LinkId=70353 for details). ---> System.Net.HttpListenerException: Access is denied`.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Poison\MSMQ4`
