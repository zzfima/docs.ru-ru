---
title: Очереди недоставленных сообщений
ms.date: 03/30/2017
ms.assetid: ff664f33-ad02-422c-9041-bab6d993f9cc
ms.openlocfilehash: 70007289e457588e94128a573ced4b28e238acf4
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74710876"
---
# <a name="dead-letter-queues"></a>Очереди недоставленных сообщений
В этом образце показано, как обрабатывать недоставленные сообщения. Он основан на образце [транзакционной привязки MSMQ](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) . В этом примере используется привязка `netMsmqBinding`. Служба представляет собой резидентное консольное приложение, позволяющее наблюдать за получением службой сообщений из очереди.

> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.

> [!NOTE]
> В этом образце для всех приложений показана очередь недоставленных сообщений, доступная только в [!INCLUDE[wv](../../../../includes/wv-md.md)]. Этот образец можно изменить для использования общесистемных очередей MSMQ 3.0 по умолчанию в [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] и [!INCLUDE[wxp](../../../../includes/wxp-md.md)].

 При использовании очередей клиент взаимодействует со службой посредством очереди. Конкретно, клиент отправляет сообщения в очередь. Служба получает сообщения из очереди. Поэтому клиенту и службе не обязательно выполняться одновременно, чтобы взаимодействовать посредством очереди.

 Связь с использованием очереди может приводить к определенным задержкам, поэтому следует назначать для сообщений срок жизни, чтобы сообщения не доставлялись приложению позже положенного времени. В некоторых случаях приложению нужно знать, что приложение не доставлено. В таких ситуациях, если истек срок жизни сообщения или его не удалось доставить, сообщение помещается в очередь недоставленных сообщений. Отправляющее приложение может после этого выполнить чтение сообщений из очереди недоставленных сообщений и предпринять корректирующие действия (к ним относятся ситуации от бездействия приложения до исправления причины ошибки доставки и повторной отправки сообщения).

 Очередь недоставленных сообщений в привязке `NetMsmqBinding` выражается в следующих свойствах.

- Свойство <xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A> выражает тип очереди недоставленных сообщений, который необходим клиенту. Значения перечисления указаны ниже:

- `None`: клиенту не требуется очередь недоставленных сообщений;

- `System`: для хранения сообщений, которые не удалось доставить, служит системная очередь недоставленных сообщений. Системная очередь недоставленных сообщений общая для всех приложений, работающих на компьютере.

- `Custom`: для хранения сообщений, которые не удалось доставить, служит пользовательская очередь недоставленных сообщений, определяемая с помощью свойства <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A>. Эта возможность доступна только в [!INCLUDE[wv](../../../../includes/wv-md.md)]. Используется, если приложению нужна собственная очередь недоставленных сообщений, независимая от других приложений, работающих на данном компьютере.

- Свойство <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A> выражает конкретную очередь, которая используется как очередь недоставленных сообщений. Это свойство доступно только в [!INCLUDE[wv](../../../../includes/wv-md.md)].

 В этом образце клиент отправляет службе пакет сообщений из области транзакции и задает неоправданно низкое значение срока жизни этих сообщений (около 2 секунд). Клиент также задает пользовательскую очередь недоставленных сообщений, в которую помещаются сообщения с истекшим сроком жизни.

 Клиентское приложение может после этого выполнить чтение сообщений из очереди недоставленных сообщений и попытаться повторно отправить сообщение или исправить ошибку, из-за которой сообщение оказалось в очереди недоставленных сообщений, и отправить его. В этом образце клиент отображает сообщение об ошибке.

 Контракт службы - `IOrderProcessor`, как показано в следующем образце кода.

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true)]
    void SubmitPurchaseOrder(PurchaseOrder po);
}
```

 Код службы в примере — это [Привязка транзакционной MSMQ](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).

 Связь с службой осуществляется в области транзакции. Служба выполняет чтение сообщений из очереди, выполняет операцию и отображает результаты операции. Также приложение создает очередь недоставленных сообщений.

```csharp
//The service contract is defined in generatedClient.cs, generated from the service by the svcutil tool.

//Client implementation code.
class Client
{
    static void Main()
    {
        // Get MSMQ queue name from app settings in configuration
        string deadLetterQueueName = ConfigurationManager.AppSettings["deadLetterQueueName"];

        // Create the transacted MSMQ queue for storing dead message if necessary.
        if (!MessageQueue.Exists(deadLetterQueueName))
            MessageQueue.Create(deadLetterQueueName, true);

        // Create a proxy with given client endpoint configuration
        OrderProcessorClient client = new OrderProcessorClient("OrderProcessorEndpoint");

        // Create the purchase order
        PurchaseOrder po = new PurchaseOrder();
        po.CustomerId = "somecustomer.com";
        po.PONumber = Guid.NewGuid().ToString();

        PurchaseOrderLineItem lineItem1 = new PurchaseOrderLineItem();
        lineItem1.ProductId = "Blue Widget";
        lineItem1.Quantity = 54;
        lineItem1.UnitCost = 29.99F;

        PurchaseOrderLineItem lineItem2 = new PurchaseOrderLineItem();
        lineItem2.ProductId = "Red Widget";
        lineItem2.Quantity = 890;
        lineItem2.UnitCost = 45.89F;

        po.orderLineItems = new PurchaseOrderLineItem[2];
        po.orderLineItems[0] = lineItem1;
        po.orderLineItems[1] = lineItem2;

        //Create a transaction scope.
        using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
        {
            // Make a queued call to submit the purchase order
            client.SubmitPurchaseOrder(po);
            // Complete the transaction.
            scope.Complete();
        }

        client.Close();

        Console.WriteLine();
        Console.WriteLine("Press <ENTER> to terminate client.");
        Console.ReadLine();
    }
}
```

 В конфигурации клиента задается короткий срок, в течение которого сообщение должно достичь службы. Если за указанное время сообщение передать не удается, его срок жизни истекает и оно помещается в очередь недоставленных сообщений.

> [!NOTE]
> Клиент может доставить сообщение в очередь службы за указанное время. Чтобы увидеть работу службы недоставленных сообщений, следует сначала запустить клиент, а только затем - службу. Срок жизни сообщения истекает, и оно передается службе недоставленных сообщений.

 Приложение должно определить очередь, которая используется в качестве очереди недоставленных сообщений. Если очередь не задана, для недоставленных сообщений используется системная очередь недоставленных сообщений по умолчанию. В этом примере клиентское приложение задает собственную очередь недоставленных сообщений.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <appSettings>
    <!-- use appSetting to configure MSMQ Dead Letter queue name -->
    <add key="deadLetterQueueName" value=".\private$\ServiceModelSamplesOrdersAppDLQ"/>
  </appSettings>

  <system.serviceModel>
    <client>
      <!-- Define NetMsmqEndpoint -->
      <endpoint name="OrderProcessorEndpoint"
                address="net.msmq://localhost/private/ServiceModelSamplesDeadLetter"
                binding="netMsmqBinding"
                bindingConfiguration="PerAppDLQBinding"
                contract="IOrderProcessor" />
    </client>

    <bindings>
      <netMsmqBinding>
        <binding name="PerAppDLQBinding"
                 deadLetterQueue="Custom"
                 customDeadLetterQueue="net.msmq://localhost/private/ServiceModelSamplesOrdersAppDLQ"
                 timeToLive="00:00:02"/>
      </netMsmqBinding>
    </bindings>
  </system.serviceModel>

</configuration>
```

 Служба недоставленных сообщений выполняет чтение сообщений из очереди недоставленных сообщений. Служба недоставленных сообщений реализует контракт `IOrderProcessor`. Эта реализация не связана с обработкой команд. Служба недоставленных сообщений - это клиентская служба, она не имеет возможности обрабатывать команды.

> [!NOTE]
> Очередь недоставленных сообщений - это клиентская очередь, локальная для диспетчера очереди клиента.

 Реализация службы недоставленных сообщений ищет причину, по которой сообщение не было доставлено, и принимает меры по исправлению ошибки. Причина ошибки доставки сообщения содержится в двух перечислениях: <xref:System.ServiceModel.Channels.MsmqMessageProperty.DeliveryFailure%2A> и <xref:System.ServiceModel.Channels.MsmqMessageProperty.DeliveryStatus%2A>. Объект <xref:System.ServiceModel.Channels.MsmqMessageProperty> можно извлечь из объекта <xref:System.ServiceModel.OperationContext>, как показано в следующем образце кода.

```csharp
public void SubmitPurchaseOrder(PurchaseOrder po)
{
    Console.WriteLine("Submitting purchase order did not succeed ", po);
    MsmqMessageProperty mqProp =
                  OperationContext.Current.IncomingMessageProperties[
                  MsmqMessageProperty.Name] as MsmqMessageProperty;
    Console.WriteLine("Message Delivery Status: {0} ",
                                                mqProp.DeliveryStatus);
    Console.WriteLine("Message Delivery Failure: {0}",
                                               mqProp.DeliveryFailure);
    Console.WriteLine();
    …
}
```

 Сообщения в очереди недоставленных сообщений - это сообщения, адресованные службе, обрабатывающей сообщение. Таким образом, когда Служба недоставленных сообщений считывает сообщения из очереди, уровень канала Windows Communication Foundation (WCF) находит несоответствие в конечных точках и не отправляет сообщение. В этом случае сообщение адресуется службе, обрабатывающей заказы, но доставляется оно службе недоставленных сообщений. Для получения сообщений, адресованных другой конечной точке, в `ServiceBehavior` задается фильтр адресов, соответствующий любому адресу. Это необходимо для успешной обработки сообщений, считываемых из очереди недоставленных сообщений.

 В этом примере служба недоставленных сообщений повторно отправляет сообщение, если причина сбоя заключается в том, что время ожидания сообщения истекло. По всем остальным причинам отображается ошибка доставки, как показано в следующем образце кода:

```csharp
// Service class that implements the service contract.
// Added code to write output to the console window.
[ServiceBehavior(InstanceContextMode=InstanceContextMode.Single, ConcurrencyMode=ConcurrencyMode.Single, AddressFilterMode=AddressFilterMode.Any)]
public class PurchaseOrderDLQService : IOrderProcessor
{
    OrderProcessorClient orderProcessorService;
    public PurchaseOrderDLQService()
    {
        orderProcessorService = new OrderProcessorClient("OrderProcessorEndpoint");
    }

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po)
    {
        Console.WriteLine("Submitting purchase order did not succeed ", po);
        MsmqMessageProperty mqProp = OperationContext.Current.IncomingMessageProperties[MsmqMessageProperty.Name] as MsmqMessageProperty;

        Console.WriteLine("Message Delivery Status: {0} ", mqProp.DeliveryStatus);
        Console.WriteLine("Message Delivery Failure: {0}", mqProp.DeliveryFailure);
        Console.WriteLine();

        // resend the message if timed out
        if (mqProp.DeliveryFailure == DeliveryFailure.ReachQueueTimeout ||
            mqProp.DeliveryFailure == DeliveryFailure.ReceiveTimeout)
        {
            // re-send
            Console.WriteLine("Purchase order Time To Live expired");
            Console.WriteLine("Trying to resend the message");

            // reuse the same transaction used to read the message from dlq to enqueue the message to app. queue
            orderProcessorService.SubmitPurchaseOrder(po);
            Console.WriteLine("Purchase order resent");
        }
    }

    // Host the service within this EXE console application.
    public static void Main()
    {
        // Create a ServiceHost for the PurchaseOrderDLQService type.
        using (ServiceHost serviceHost = new ServiceHost(typeof(PurchaseOrderDLQService)))
        {
            // Open the ServiceHostBase to create listeners and start listening for messages.
            serviceHost.Open();

            // The service can now be accessed.
            Console.WriteLine("The dead letter service is ready.");
            Console.WriteLine("Press <ENTER> to terminate service.");
            Console.WriteLine();
            Console.ReadLine();
        }
    }
}
```

 В следующем образце показана конфигурация для недоставленного сообщения:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <services>
      <service
          name="Microsoft.ServiceModel.Samples.PurchaseOrderDLQService">
        <!-- Define NetMsmqEndpoint in this case, DLQ end point to read messages-->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesOrdersAppDLQ"
                  binding="netMsmqBinding"
                  bindingConfiguration="DefaultBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
      </service>
    </services>

    <client>
      <!-- Define NetMsmqEndpoint -->
      <endpoint name="OrderProcessorEndpoint"
                 address="net.msmq://localhost/private/ServiceModelSamplesDeadLetter"
                 binding="netMsmqBinding"
                 bindingConfiguration="SystemDLQBinding"
                 contract="IOrderProcessor" />
    </client>

    <bindings>
      <netMsmqBinding>
        <binding name="DefaultBinding" />
        <binding name="SystemDLQBinding"
                 deadLetterQueue="System"/>
      </netMsmqBinding>
    </bindings>
  </system.serviceModel>
</configuration>
```

 В этом образце нужно запустить три исполняемых файла, чтобы посмотреть, как работает очередь недоставленных сообщений для всех приложений: клиента, службы и службы недоставленных сообщений, которая выполняет чтение очереди недоставленных сообщений для каждого приложения и повторно отправляет сообщение службе. Это консольные приложения, отображающие вывод в окнах консоли.

> [!NOTE]
> Поскольку используется очередь, клиенту и службе не обязательно быть запущенными и работать одновременно. Можно запустить клиент, выключить его, а затем запустить службу, которая все равно получит сообщения клиента. Для создания очереди следует запустить и завершить службу.

 При запуске клиент отображает сообщение:

```console
Press <ENTER> to terminate client.
```

 Клиент попытался отправить сообщение, но короткое время жизни сообщения истекло, и оно попало в очередь недоставленных сообщений для каждого приложения.

 После этого запускается служба недоставленных сообщений, которая выполняет чтение сообщения, отображает код ошибки и повторно отправляет сообщение службе.

```console
The dead letter service is ready.
Press <ENTER> to terminate service.

Submitting purchase order did not succeed
Message Delivery Status: InDoubt
Message Delivery Failure: ReachQueueTimeout

Purchase order Time To Live expired
Trying to resend the message
Purchase order resent
```

 Служба запускается, выполняет чтение повторно отправленного сообщения и обрабатывает его.

```console
The service is ready.
Press <ENTER> to terminate service.

Processing Purchase Order: 97897eff-f926-4057-a32b-af8fb11b9bf9
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending
```

### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца

1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

2. При первом запуске служба проверит наличие очереди. Если очередь отсутствует, служба ее создаст. Можно сначала запустить службу, чтобы создать очередь, либо создать ее с помощью диспетчера очередей MSMQ. Чтобы создать очередь в Windows 2008, выполните следующие шаги.

    1. Откройте диспетчер сервера в Visual Studio 2012.

    2. Разверните вкладку **функции** .

    3. Щелкните правой кнопкой мыши **частные очереди сообщений**и выберите **создать**, **Частная очередь**.

    4. Установите флажок **транзакционная** .

    5. Введите `ServiceModelSamplesTransacted` в качестве имени новой очереди.

3. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).

4. Чтобы выполнить пример в конфигурации с одним или несколькими компьютерами соответствующим образом, замените localhost на полное имя компьютера и следуйте инструкциям в разделе [Запуск примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).

### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup"></a>Выполнение образца на компьютере, входящем в рабочую группу

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

     Обеспечьте связь конечной точки с привязкой, задав атрибут `bindingConfiguration` конечной точки.

2. Перед выполнением образца убедитесь, что изменена конфигурация службы DeadLetterService, сервера и клиента.

    > [!NOTE]
    > Установка для `security mode` значения `None` эквивалентна присвоению свойствам `MsmqAuthenticationMode`, `MsmqProtectionLevel` и безопасности `Message` значения `None`.

## <a name="comments"></a>Comments
 По умолчанию с транспортом привязки `netMsmqBinding` безопасность включена. Тип безопасности транспорта определяется двумя свойствами: `MsmqAuthenticationMode` и `MsmqProtectionLevel`. По умолчанию устанавливается режим проверки подлинности `Windows` и уровень защиты `Sign`. Чтобы служба MSMQ обеспечивала возможности проверки подлинности и подписывания, она должна входить в домен. При выполнении этого примера на компьютере, не входящем в домен, возникает следующая ошибка: "User's internal message queuing certificate does not exist" (не существует внутреннего сертификата очереди сообщений пользователя).

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\DeadLetter`  
