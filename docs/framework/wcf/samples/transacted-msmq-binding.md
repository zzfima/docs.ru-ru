---
title: Привязка MSMQ с поддержкой транзакций
ms.date: 03/30/2017
ms.assetid: 71f5cb8d-f1df-4e1e-b8a2-98e734a75c37
ms.openlocfilehash: ebf93ba5b7497d30ff7efceea3bd7ca827d5b502
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423905"
---
# <a name="transacted-msmq-binding"></a><span data-ttu-id="cfe26-102">Привязка MSMQ с поддержкой транзакций</span><span class="sxs-lookup"><span data-stu-id="cfe26-102">Transacted MSMQ Binding</span></span>

<span data-ttu-id="cfe26-103">В этом образце показано, как осуществлять транзакционное взаимодействие с использованием очередей с помощью очереди сообщений (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="cfe26-103">This sample demonstrates how to perform transacted queued communication by using Message Queuing (MSMQ).</span></span>

> [!NOTE]
> <span data-ttu-id="cfe26-104">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="cfe26-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="cfe26-105">При использовании очередей клиент взаимодействует со службой посредством очереди.</span><span class="sxs-lookup"><span data-stu-id="cfe26-105">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="cfe26-106">Конкретно, клиент отправляет сообщения в очередь.</span><span class="sxs-lookup"><span data-stu-id="cfe26-106">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="cfe26-107">Служба получает сообщения из очереди.</span><span class="sxs-lookup"><span data-stu-id="cfe26-107">The service receives messages from the queue.</span></span> <span data-ttu-id="cfe26-108">Поэтому при взаимодействии посредством очереди клиенту и службе не обязательно работать одновременно.</span><span class="sxs-lookup"><span data-stu-id="cfe26-108">The service and client, therefore, do not have to be running at the same time to communicate using a queue.</span></span>

<span data-ttu-id="cfe26-109">При использовании транзакций для отправки и получения сообщений это фактически две отдельные транзакции.</span><span class="sxs-lookup"><span data-stu-id="cfe26-109">When transactions are used to send and receive messages, there are actually two separate transactions.</span></span> <span data-ttu-id="cfe26-110">При отправке клиентом сообщений в области транзакции эта транзакция локальна для клиента и диспетчера очереди клиента.</span><span class="sxs-lookup"><span data-stu-id="cfe26-110">When the client sends messages within the scope of a transaction, the transaction is local to the client and the client queue manager.</span></span> <span data-ttu-id="cfe26-111">При получении службой сообщений в области транзакции эта транзакция локальна для службы и диспетчера принимающей очереди.</span><span class="sxs-lookup"><span data-stu-id="cfe26-111">When the service receives messages within the scope of the transaction, the transaction is local to the service and the receiving queue manager.</span></span> <span data-ttu-id="cfe26-112">Очень важно помнить, что клиент и служба не участвуют в одной транзакции, а используют разные транзакции при выполнении операций с очередью (например, отправки и получения).</span><span class="sxs-lookup"><span data-stu-id="cfe26-112">It is very important to remember that the client and the service are not participating in the same transaction; rather, they are using different transactions when performing their operations (such as send and receive) with the queue.</span></span>

<span data-ttu-id="cfe26-113">В этом образце клиент отправляет службе пакет сообщений из области транзакции.</span><span class="sxs-lookup"><span data-stu-id="cfe26-113">In this sample, the client sends a batch of messages to the service from within the scope of a transaction.</span></span> <span data-ttu-id="cfe26-114">Сообщения, отправленные в очередь, принимаются после этого службой в области транзакции, определенной службой.</span><span class="sxs-lookup"><span data-stu-id="cfe26-114">The messages sent to the queue are then received by the service within the transaction scope defined by the service.</span></span>

<span data-ttu-id="cfe26-115">Контракт службы - `IOrderProcessor`, как показано в следующем образце кода.</span><span class="sxs-lookup"><span data-stu-id="cfe26-115">The service contract is `IOrderProcessor`, as shown in the following sample code.</span></span> <span data-ttu-id="cfe26-116">Интерфейс определяет одностороннюю службу, которую можно использовать с очередями.</span><span class="sxs-lookup"><span data-stu-id="cfe26-116">The interface defines a one-way service that is suitable for use with queues.</span></span>

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true)]
    void SubmitPurchaseOrder(PurchaseOrder po);
}
```

<span data-ttu-id="cfe26-117">Поведение службы определяет поведение операции со значением `TransactionScopeRequired`, равным `true`.</span><span class="sxs-lookup"><span data-stu-id="cfe26-117">The service behavior defines an operation behavior with `TransactionScopeRequired` set to `true`.</span></span> <span data-ttu-id="cfe26-118">Это обеспечивает использование любыми диспетчерами ресурсов, к которым обращается метод, той же области транзакции, что и для получения сообщения из очереди.</span><span class="sxs-lookup"><span data-stu-id="cfe26-118">This ensures that the same transaction scope that is used to retrieve the message from the queue is used by any resource managers accessed by the method.</span></span> <span data-ttu-id="cfe26-119">Кроме того, этим гарантируется возврат сообщения в очередь, если метод создаст исключение.</span><span class="sxs-lookup"><span data-stu-id="cfe26-119">It also guarantees that if the method throws an exception, the message is returned to the queue.</span></span> <span data-ttu-id="cfe26-120">Если не установить такое поведение операции, канал в очереди создает транзакцию для чтения сообщения из очереди и автоматически фиксирует ее перед передачей, поэтому при ошибке операции сообщение теряется.</span><span class="sxs-lookup"><span data-stu-id="cfe26-120">Without setting this operation behavior, a queued channel creates a transaction to read the message from the queue and commits it automatically before dispatch such that if the operation fails, the message is lost.</span></span> <span data-ttu-id="cfe26-121">Обычная схема для операций служб заключается в зачислении транзакции, которая используется для чтения сообщения из очереди, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="cfe26-121">The most common scenario is for service operations to enlist in the transaction that is used to read the message from the queue, as demonstrated in the following code.</span></span>

```csharp
 // This service class that implements the service contract.
 // This added code writes output to the console window.
 public class OrderProcessorService : IOrderProcessor
 {
     [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
     public void SubmitPurchaseOrder(PurchaseOrder po)
     {
         Orders.Add(po);
         Console.WriteLine("Processing {0} ", po);
     }
  …
}
```

<span data-ttu-id="cfe26-122">Служба является резидентной.</span><span class="sxs-lookup"><span data-stu-id="cfe26-122">The service is self hosted.</span></span> <span data-ttu-id="cfe26-123">При работе с транспортом MSMQ используемую очередь следует создавать заранее.</span><span class="sxs-lookup"><span data-stu-id="cfe26-123">When using the MSMQ transport, the queue used must be created in advance.</span></span> <span data-ttu-id="cfe26-124">Это можно сделать вручную или с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="cfe26-124">This can be done manually or through code.</span></span> <span data-ttu-id="cfe26-125">В данном образце служба содержит код для проверки наличия очереди и ее создания, если очереди нет.</span><span class="sxs-lookup"><span data-stu-id="cfe26-125">In this sample, the service contains code to check for the existence of the queue and create the queue if it does not exist.</span></span> <span data-ttu-id="cfe26-126">Имя очереди считывается из файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cfe26-126">The queue name is read from the configuration file.</span></span> <span data-ttu-id="cfe26-127">Базовый адрес используется [средством служебной программы метаданных ServiceModel (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания прокси-сервера для службы.</span><span class="sxs-lookup"><span data-stu-id="cfe26-127">The base address is used by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy to the service.</span></span>

```csharp
// Host the service within this EXE console application.
public static void Main()
{
    // Get the MSMQ queue name from appSettings in configuration.
    string queueName = ConfigurationManager.AppSettings["queueName"];

    // Create the transacted MSMQ queue if necessary.
    if (!MessageQueue.Exists(queueName))
        MessageQueue.Create(queueName, true);

    // Create a ServiceHost for the OrderProcessorService type.
    using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))
    {
        // Open the ServiceHost to create listeners and start listening for messages.
        serviceHost.Open();

        // The service can now be accessed.
        Console.WriteLine("The service is ready.");
        Console.WriteLine("Press <ENTER> to terminate service.");
        Console.WriteLine();
        Console.ReadLine();

        // Close the ServiceHost to shut down the service.
        serviceHost.Close();
    }
}
```

<span data-ttu-id="cfe26-128">Имя очереди MSMQ задается в разделе appSettings файла конфигурации, как показано в следующем образце конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cfe26-128">The MSMQ queue name is specified in an appSettings section of the configuration file, as shown in the following sample configuration.</span></span>

```xml
<appSettings>
    <add key="queueName" value=".\private$\ServiceModelSamplesTransacted" />
</appSettings>
```

> [!NOTE]
> <span data-ttu-id="cfe26-129">В имени очереди для определения локального компьютера используется точка (.), а при создании очереди с помощью <xref:System.Messaging> в пути в качестве разделителей используются символы обратной косой черты.</span><span class="sxs-lookup"><span data-stu-id="cfe26-129">The queue name uses a dot (.) for the local computer and backslash separators in its path when creating the queue using <xref:System.Messaging>.</span></span> <span data-ttu-id="cfe26-130">Конечная точка Windows Communication Foundation (WCF) использует адрес очереди в схеме NET. MSMQ, использует "localhost" для обозначения локального компьютера и использует косую черту в пути.</span><span class="sxs-lookup"><span data-stu-id="cfe26-130">The Windows Communication Foundation (WCF) endpoint uses the queue address with net.msmq scheme, uses "localhost" to denote the local computer, and uses forward slashes in its path.</span></span>

<span data-ttu-id="cfe26-131">Клиент создает область транзакции.</span><span class="sxs-lookup"><span data-stu-id="cfe26-131">The client creates a transaction scope.</span></span> <span data-ttu-id="cfe26-132">Связь с очередью происходит в области транзакции, поэтому она обрабатывается как единый модуль, в котором либо все сообщения отправляются в очередь, либо в очередь не отправляется ни одного сообщения.</span><span class="sxs-lookup"><span data-stu-id="cfe26-132">Communication with the queue takes place within the scope of the transaction, causing it to be treated as an atomic unit where all messages are sent to the queue or none of the messages are sent to the queue.</span></span> <span data-ttu-id="cfe26-133">Транзакция фиксируется вызовом метода <xref:System.Transactions.TransactionScope.Complete%2A> для области транзакции.</span><span class="sxs-lookup"><span data-stu-id="cfe26-133">The transaction is committed by calling <xref:System.Transactions.TransactionScope.Complete%2A> on the transaction scope.</span></span>

```csharp
// Create a client.
OrderProcessorClient client = new OrderProcessorClient();

// Create the purchase order.
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

// Create a transaction scope.
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
{
    // Make a queued call to submit the purchase order.
    client.SubmitPurchaseOrder(po);
    // Complete the transaction.
    scope.Complete();
}

// Closing the client gracefully closes the connection and cleans up resources.
client.Close();

Console.WriteLine();
Console.WriteLine("Press <ENTER> to terminate client.");
Console.ReadLine();
```

<span data-ttu-id="cfe26-134">Чтобы убедиться, что транзакции работают, измените клиент, преобразовав область транзакции в комментарий, как показано в следующем фрагменте кода, снова выполните построение решения и запустите клиент.</span><span class="sxs-lookup"><span data-stu-id="cfe26-134">To verify that transactions are working, modify the client by commenting the transaction scope as shown in the following sample code, rebuild the solution, and run the client.</span></span>

```csharp
//scope.Complete();
```

<span data-ttu-id="cfe26-135">Так как транзакция не завершена, сообщения не отправляются в очередь.</span><span class="sxs-lookup"><span data-stu-id="cfe26-135">Because the transaction is not completed, the messages are not sent to the queue.</span></span>

<span data-ttu-id="cfe26-136">При выполнении образца действия клиента и службы отображаются в окнах консоли как службы, так и клиента.</span><span class="sxs-lookup"><span data-stu-id="cfe26-136">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="cfe26-137">Можно видеть, как служба получает сообщения от клиента.</span><span class="sxs-lookup"><span data-stu-id="cfe26-137">You can see the service receive messages from the client.</span></span> <span data-ttu-id="cfe26-138">Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент.</span><span class="sxs-lookup"><span data-stu-id="cfe26-138">Press ENTER in each console window to shut down the service and client.</span></span> <span data-ttu-id="cfe26-139">Обратите внимание, что поскольку используется очередь, клиенту и службе не обязательно быть запущенными и работать одновременно.</span><span class="sxs-lookup"><span data-stu-id="cfe26-139">Note that because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="cfe26-140">Можно запустить клиент, выключить его, а затем запустить службу и все равно получить сообщения клиента.</span><span class="sxs-lookup"><span data-stu-id="cfe26-140">You can run the client, shut it down, and then start up the service and it still receives the messages.</span></span>

```console
The service is ready.
Press <ENTER> to terminate service.

Processing Purchase Order: 7b31ce51-ae7c-4def-9b8b-617e4288eafd
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="cfe26-141">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="cfe26-141">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="cfe26-142">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="cfe26-142">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="cfe26-143">При первом запуске служба проверит наличие очереди.</span><span class="sxs-lookup"><span data-stu-id="cfe26-143">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="cfe26-144">Если очередь отсутствует, служба ее создаст.</span><span class="sxs-lookup"><span data-stu-id="cfe26-144">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="cfe26-145">Можно сначала запустить службу, чтобы создать очередь, либо создать ее с помощью диспетчера очередей MSMQ.</span><span class="sxs-lookup"><span data-stu-id="cfe26-145">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="cfe26-146">Чтобы создать очередь в Windows 2008, выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="cfe26-146">Follow these steps to create a queue in Windows 2008.</span></span>

    1. <span data-ttu-id="cfe26-147">Откройте диспетчер сервера в Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="cfe26-147">Open Server Manager in Visual Studio 2012.</span></span>

    2. <span data-ttu-id="cfe26-148">Разверните вкладку **функции** .</span><span class="sxs-lookup"><span data-stu-id="cfe26-148">Expand the **Features** tab.</span></span>

    3. <span data-ttu-id="cfe26-149">Щелкните правой кнопкой мыши **частные очереди сообщений**и выберите **создать**, **Частная очередь**.</span><span class="sxs-lookup"><span data-stu-id="cfe26-149">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>

    4. <span data-ttu-id="cfe26-150">Установите флажок **транзакционная** .</span><span class="sxs-lookup"><span data-stu-id="cfe26-150">Check the **Transactional** box.</span></span>

    5. <span data-ttu-id="cfe26-151">Введите `ServiceModelSamplesTransacted` в качестве имени новой очереди.</span><span class="sxs-lookup"><span data-stu-id="cfe26-151">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>

3. <span data-ttu-id="cfe26-152">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="cfe26-152">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

4. <span data-ttu-id="cfe26-153">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="cfe26-153">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

<span data-ttu-id="cfe26-154">По умолчанию с привязкой <xref:System.ServiceModel.NetMsmqBinding> безопасность транспорта включена.</span><span class="sxs-lookup"><span data-stu-id="cfe26-154">By default with the <xref:System.ServiceModel.NetMsmqBinding>, transport security is enabled.</span></span> <span data-ttu-id="cfe26-155">Имеется два соответствующих свойства для обеспечения безопасности транспорта MSMQ: <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> и <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>.</span><span class="sxs-lookup"><span data-stu-id="cfe26-155">There are two relevant properties for MSMQ transport security, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> and <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>.</span></span> <span data-ttu-id="cfe26-156">По умолчанию задан режим проверки подлинности `Windows` и уровень защиты `Sign`.</span><span class="sxs-lookup"><span data-stu-id="cfe26-156">By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="cfe26-157">Чтобы служба MSMQ обеспечивала возможности проверки подлинности и подписывания, она должна входить в домен, а также должна быть установлена возможность интеграции MSMQ со службой каталогов Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cfe26-157">For MSMQ to provide the authentication and signing feature, it must be part of a domain and the Active Directory integration option for MSMQ must be installed.</span></span> <span data-ttu-id="cfe26-158">Если запустить этот образец на компьютере, который не удовлетворяет этому условию, возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="cfe26-158">If you run this sample on a computer that does not satisfy these criteria, you receive an error.</span></span>

### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a><span data-ttu-id="cfe26-159">Выполнение образца на компьютере, входящем в рабочую группу, или без интеграции с Active Directory</span><span class="sxs-lookup"><span data-stu-id="cfe26-159">To run the sample on a computer joined to a workgroup or without Active Directory integration</span></span>

1. <span data-ttu-id="cfe26-160">Если компьютер не входит в домен или не установлена интеграция с Active Directory, отключите безопасность транспорта, задав для режима проверки подлинности и уровня защиты значение `None`, как показано в следующем образце кода конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cfe26-160">If your computer is not part of a domain or does not have Active Directory integration installed, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration code.</span></span>

    ```xml
    <system.serviceModel>
      <services>
        <service name="Microsoft.ServiceModel.Samples.OrderProcessorService"
                 behaviorConfiguration="OrderProcessorServiceBehavior">
          <host>
            <baseAddresses>
              <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>
            </baseAddresses>
          </host>
          <!-- Define NetMsmqEndpoint. -->
          <endpoint
              address="net.msmq://localhost/private/ServiceModelSamplesTransacted"
              binding="netMsmqBinding"
              bindingConfiguration="Binding1"
           contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
          <!-- The mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex. -->
          <endpoint address="mex"
                    binding="mexHttpBinding"
                    contract="IMetadataExchange" />
        </service>
      </services>

      <bindings>
        <netMsmqBinding>
          <binding name="Binding1">
            <security mode="None" />
          </binding>
        </netMsmqBinding>
      </bindings>

        <behaviors>
          <serviceBehaviors>
            <behavior name="OrderProcessorServiceBehavior">
              <serviceMetadata httpGetEnabled="True"/>
            </behavior>
          </serviceBehaviors>
        </behaviors>

      </system.serviceModel>
    ```

2. <span data-ttu-id="cfe26-161">Перед выполнением примера убедитесь, что изменена конфигурация как сервера, так и клиента.</span><span class="sxs-lookup"><span data-stu-id="cfe26-161">Ensure that you change the configuration on both the server and the client before you run the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cfe26-162">Задание для `security mode` значения `None` эквивалентно заданию для параметров безопасности <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> и `Message` значения `None`.</span><span class="sxs-lookup"><span data-stu-id="cfe26-162">Setting `security mode` to `None` is equivalent to setting <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>, and `Message` security to `None`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cfe26-163">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="cfe26-163">The samples may already be installed on your computer.</span></span> <span data-ttu-id="cfe26-164">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="cfe26-164">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="cfe26-165">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="cfe26-165">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cfe26-166">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="cfe26-166">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Transacted`
