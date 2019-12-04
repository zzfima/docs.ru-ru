---
title: Активация MSMQ
ms.date: 03/30/2017
ms.assetid: e3834149-7b8c-4a54-806b-b4296720f31d
ms.openlocfilehash: be33e3d9377c30058c7a2ee06543c11f10251ebd
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714775"
---
# <a name="msmq-activation"></a><span data-ttu-id="19355-102">Активация MSMQ</span><span class="sxs-lookup"><span data-stu-id="19355-102">MSMQ Activation</span></span>

<span data-ttu-id="19355-103">Этот образец демонстрирует размещение приложений в службе активации Windows (WAS), которые считываются из очереди сообщений.</span><span class="sxs-lookup"><span data-stu-id="19355-103">This sample demonstrates how to host applications in Windows Process Activation Service (WAS) that are read from a message queue.</span></span> <span data-ttu-id="19355-104">В этом примере используется `netMsmqBinding` и основан на примере [двусторонней связи](../../../../docs/framework/wcf/samples/two-way-communication.md) .</span><span class="sxs-lookup"><span data-stu-id="19355-104">This sample uses the `netMsmqBinding` and is based on the [Two-Way Communication](../../../../docs/framework/wcf/samples/two-way-communication.md) sample.</span></span> <span data-ttu-id="19355-105">В данном случае служба представляет собой приложение, размещенное на веб-сервере, а клиент - резидентное приложение, выводящее данные в окно консоли для наблюдения за состоянием размещенных заказов на покупку.</span><span class="sxs-lookup"><span data-stu-id="19355-105">The service in this case is a Web-hosted application and the client is self-hosted and outputs to the console to observe the status of purchase orders submitted.</span></span>

> [!NOTE]
> <span data-ttu-id="19355-106">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="19355-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="19355-107">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="19355-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="19355-108">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="19355-108">Check for the following (default) directory before continuing.</span></span>
>
> <span data-ttu-id="19355-109">\<Инсталлдриве >: \ WF_WCF_Samples</span><span class="sxs-lookup"><span data-stu-id="19355-109">\<InstallDrive>:\WF_WCF_Samples</span></span>
>
> <span data-ttu-id="19355-110">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все образцы WCF и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19355-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all WCF and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="19355-111">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="19355-111">This sample is located in the following directory.</span></span>
>
> <span data-ttu-id="19355-112">\<Инсталлдриве >: \Самплес\вкфвфкардспаце\вкф\басик\сервицес\хостинг\вашост\мсмкактиватион.</span><span class="sxs-lookup"><span data-stu-id="19355-112">\<InstallDrive>:\Samples\WCFWFCardSpace\WCF\Basic\Services\Hosting\WASHost\MsmqActivation.</span></span>

<span data-ttu-id="19355-113">Служба активации Windows (WAS), новый механизм активации процессов для [!INCLUDE[lserver](../../../../includes/lserver-md.md)], предоставляет компоненты, подобные IIS, ранее доступные только приложениям, работающим на базе протокола HTTP, для приложений, использующих протоколы, отличные от HTTP.</span><span class="sxs-lookup"><span data-stu-id="19355-113">Windows Process Activation Service (WAS), the new process activation mechanism for [!INCLUDE[lserver](../../../../includes/lserver-md.md)], provides IIS-like features that were previously only available to HTTP-based applications to applications that use non-HTTP protocols.</span></span> <span data-ttu-id="19355-114">Windows Communication Foundation (WCF) использует интерфейс адаптера прослушивателя для передачи запросов на активацию, полученных через протоколы, отличные от HTTP, которые поддерживаются WCF, такие как TCP, именованные каналы и MSMQ.</span><span class="sxs-lookup"><span data-stu-id="19355-114">Windows Communication Foundation (WCF) uses the Listener Adapter interface to communicate activation requests that are received over the non-HTTP protocols supported by WCF, such as TCP, Named Pipes, and MSMQ.</span></span> <span data-ttu-id="19355-115">Функциональность для получения запросов по протоколам, отличным от HTTP, размещена в управляемых службах Windows, выполняемых в файле SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="19355-115">The functionality for receiving requests over non-HTTP protocols is hosted by managed Windows services running in SMSvcHost.exe.</span></span>

<span data-ttu-id="19355-116">Служба адаптера прослушивателя Net.Msmq (NetMsmqActivator) активирует приложения в очереди на основании очереди сообщений.</span><span class="sxs-lookup"><span data-stu-id="19355-116">The Net.Msmq Listener Adapter service (NetMsmqActivator) activates queued applications based on messages in the queue.</span></span>

<span data-ttu-id="19355-117">Клиент отправляет службе заказы на покупку из области транзакции.</span><span class="sxs-lookup"><span data-stu-id="19355-117">The client sends purchase orders to the service from within the scope of a transaction.</span></span> <span data-ttu-id="19355-118">Служба получает заказы в транзакцию и обрабатывает их.</span><span class="sxs-lookup"><span data-stu-id="19355-118">The service receives the orders in a transaction and processes them.</span></span> <span data-ttu-id="19355-119">После этого служба возвращает клиенту состояние заказа.</span><span class="sxs-lookup"><span data-stu-id="19355-119">The service then calls back the client with the status of the order.</span></span> <span data-ttu-id="19355-120">Для двустороннего взаимодействия и клиент, и служба используют очереди для заказов на покупку и состояний заказов.</span><span class="sxs-lookup"><span data-stu-id="19355-120">To facilitate two-way communication the client and service both use queues to enqueue purchase orders and order status.</span></span>

<span data-ttu-id="19355-121">Контракт службы `IOrderProcessor` определяет односторонние операции службы, работающие с очередями.</span><span class="sxs-lookup"><span data-stu-id="19355-121">The service contract `IOrderProcessor` defines the one-way service operations that work with queuing.</span></span> <span data-ttu-id="19355-122">Операция службы использует конечную точку ответа для отправки клиенту состояний заказов.</span><span class="sxs-lookup"><span data-stu-id="19355-122">The service operation uses the reply endpoint to send order statuses to the client.</span></span> <span data-ttu-id="19355-123">Адрес конечной точки ответа - это универсальный код ресурса (URI) очереди, служащий для отправки клиенту состояний заказов.</span><span class="sxs-lookup"><span data-stu-id="19355-123">The reply endpoint's address is the URI of the queue used to send the order status back to the client.</span></span> <span data-ttu-id="19355-124">Приложение, обрабатывающее заказы, реализует этот контракт.</span><span class="sxs-lookup"><span data-stu-id="19355-124">The order processing application implements this contract.</span></span>

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true)]
    void SubmitPurchaseOrder(PurchaseOrder po,
                                           string reportOrderStatusTo);
}
```

<span data-ttu-id="19355-125">Контракт ответа для отправки состояния заказа задается клиентом.</span><span class="sxs-lookup"><span data-stu-id="19355-125">The reply contract to send order status to is specified by the client.</span></span> <span data-ttu-id="19355-126">Клиент реализует контракт состояния заказа.</span><span class="sxs-lookup"><span data-stu-id="19355-126">The client implements the order status contract.</span></span> <span data-ttu-id="19355-127">Служба использует созданного клиента этого контракта для отправки состояния заказа клиенту.</span><span class="sxs-lookup"><span data-stu-id="19355-127">The service uses the generated client of this contract to send order status back to the client.</span></span>

```csharp
[ServiceContract]
public interface IOrderStatus
{
    [OperationContract(IsOneWay = true)]
    void OrderStatus(string poNumber, string status);
}
```

<span data-ttu-id="19355-128">Операция службы обрабатывает отправленный заказ на покупку.</span><span class="sxs-lookup"><span data-stu-id="19355-128">The service operation processes the submitted purchase order.</span></span> <span data-ttu-id="19355-129">Объект <xref:System.ServiceModel.OperationBehaviorAttribute> применяется к операции службы, чтобы задать автоматическое зачисление в транзакцию, которая используется для получения сообщения из очереди, и автоматическое завершение транзакции после завершения операции службы.</span><span class="sxs-lookup"><span data-stu-id="19355-129">The <xref:System.ServiceModel.OperationBehaviorAttribute> is applied to the service operation to specify automatic enlistment in the transaction that is used to receive the message from the queue and automatic completion of the transaction on completion of the service operation.</span></span> <span data-ttu-id="19355-130">Класс `Orders` инкапсулирует функцию обработки заказа.</span><span class="sxs-lookup"><span data-stu-id="19355-130">The `Orders` class encapsulates order processing functionality.</span></span> <span data-ttu-id="19355-131">В данном случае он добавляет заказ на покупку в словарь.</span><span class="sxs-lookup"><span data-stu-id="19355-131">In this case, it adds the purchase order to a dictionary.</span></span> <span data-ttu-id="19355-132">Транзакция, в которую зачислена операция службы, доступна операциям в классе `Orders`.</span><span class="sxs-lookup"><span data-stu-id="19355-132">The transaction that the service operation enlisted in is available to the operations in the `Orders` class.</span></span>

<span data-ttu-id="19355-133">Операция службы, помимо обработки отправленного заказа на покупку, возвращает клиенту состояние заказа.</span><span class="sxs-lookup"><span data-stu-id="19355-133">The service operation, in addition to processing the submitted purchase order, replies back to the client about the status of the order.</span></span>

```csharp
public class OrderProcessorService : IOrderProcessor
{
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po, string reportOrderStatusTo)
    {
        Orders.Add(po);
        Console.WriteLine("Processing {0} ", po);
        Console.WriteLine("Sending back order status information");
        NetMsmqBinding msmqCallbackBinding = new NetMsmqBinding();
        msmqCallbackBinding.Security.Mode = NetMsmqSecurityMode.None;
        OrderStatusClient client = new OrderStatusClient(msmqCallbackBinding, new EndpointAddress(reportOrderStatusTo));
        // please note that the same transaction that is used to dequeue purchase order is used
        // to send back order status
        using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
        {
            client.OrderStatus(po.PONumber, po.Status);
            scope.Complete();
        }
    }
}
```

<span data-ttu-id="19355-134">Используемая клиентом привязка задается при помощи файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="19355-134">The client binding to use is specified using a configuration file.</span></span>

<span data-ttu-id="19355-135">Имя очереди MSMQ задается в разделе appSettings файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="19355-135">The MSMQ queue name is specified in an appSettings section of the configuration file.</span></span> <span data-ttu-id="19355-136">Конечная точка службы определяется в разделе System.serviceModel файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="19355-136">The endpoint for the service is defined in the System.serviceModel section of the configuration file.</span></span>

> [!NOTE]
> <span data-ttu-id="19355-137">Правила адресации несколько различаются для имени очереди MSMQ и адреса конечной точки.</span><span class="sxs-lookup"><span data-stu-id="19355-137">The MSMQ queue name and endpoint address use slightly different addressing conventions.</span></span> <span data-ttu-id="19355-138">В имени очереди MSMQ для определения локального компьютера используется точка (.), а в пути в качестве разделителей используются символы обратной косой черты.</span><span class="sxs-lookup"><span data-stu-id="19355-138">The MSMQ queue name uses a dot (.) for the local computer and backslash separators in its path.</span></span> <span data-ttu-id="19355-139">Адрес конечной точки WCF указывает схему "net. msmq:", использует "localhost" для локального компьютера и использует косую черту в пути.</span><span class="sxs-lookup"><span data-stu-id="19355-139">The WCF endpoint address specifies a net.msmq: scheme, uses "localhost" for the local computer, and uses forward slashes in its path.</span></span> <span data-ttu-id="19355-140">Для чтения очереди, размещенной на удаленном компьютере, «.» и «localhost» следует заменить именем удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="19355-140">To read from a queue that is hosted on the remote computer, replace the "." and "localhost" to the remote computer name.</span></span>

<span data-ttu-id="19355-141">Для размещения кода службы в WAS используется файл с именем, соответствующем имени класса и расширением SVC.</span><span class="sxs-lookup"><span data-stu-id="19355-141">A .svc file with the name of the class is used to host the service code in WAS.</span></span>

<span data-ttu-id="19355-142">Файл Service.svc содержит директиву для создания `OrderProcessorService`.</span><span class="sxs-lookup"><span data-stu-id="19355-142">The Service.svc file itself contains a directive to create the `OrderProcessorService`.</span></span>

`<%@ServiceHost language="c#" Debug="true" Service="Microsoft.ServiceModel.Samples.OrderProcessorService"%>`

<span data-ttu-id="19355-143">Файл Service.svc также содержит директиву сборки для проверки загрузки System.Transactions.dll.</span><span class="sxs-lookup"><span data-stu-id="19355-143">The Service.svc file also contains an assembly directive to ensure that System.Transactions.dll is loaded.</span></span>

`<%@Assembly name="System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"%>`

<span data-ttu-id="19355-144">Клиент создает область транзакции.</span><span class="sxs-lookup"><span data-stu-id="19355-144">The client creates a transaction scope.</span></span> <span data-ttu-id="19355-145">Связь со службой происходит в области транзакции, поэтому она обрабатывается как единый модуль, в котором либо все сообщения отправляются успешно, либо не отправляется ни одного.</span><span class="sxs-lookup"><span data-stu-id="19355-145">Communication with the service takes place within the scope of the transaction, causing it to be treated as an atomic unit where all messages succeed or fail.</span></span> <span data-ttu-id="19355-146">Транзакция фиксируется вызовом метода `Complete` для области транзакции.</span><span class="sxs-lookup"><span data-stu-id="19355-146">The transaction is committed by calling `Complete` on the transaction scope.</span></span>

```csharp
using (ServiceHost serviceHost = new ServiceHost(typeof(OrderStatusService)))
{
    // Open the ServiceHostBase to create listeners and start listening
    // for order status messages.
    serviceHost.Open();

    // Create a proxy with given client endpoint configuration
    OrderProcessorClient client = new OrderProcessorClient();

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
    using (TransactionScope scope = new
        TransactionScope(TransactionScopeOption.Required))
    {
        // Make a queued call to submit the purchase order
        client.SubmitPurchaseOrder(po,
       "net.msmq://localhost/private/ServiceModelSamplesOrder/OrderStatus");
        // Complete the transaction.
        scope.Complete();
    }

    //Closing the client gracefully closes the connection and cleans up
    //resources
    client.Close();

    Console.WriteLine();
    Console.WriteLine("Press <ENTER> to terminate client.");
    Console.ReadLine();

    // Close the ServiceHostBase to shutdown the service.
    serviceHost.Close();
    }
```

<span data-ttu-id="19355-147">Код клиента реализует контракт `IOrderStatus` для получения от службы состояния заказа.</span><span class="sxs-lookup"><span data-stu-id="19355-147">The client code implements the `IOrderStatus` contract to receive order status from the service.</span></span> <span data-ttu-id="19355-148">В данном случае он выводит состояние заказа.</span><span class="sxs-lookup"><span data-stu-id="19355-148">In this case, it prints out the order status.</span></span>

```csharp
[ServiceBehavior]
public class OrderStatusService : IOrderStatus
{
    [OperationBehavior(TransactionAutoComplete = true,
                        TransactionScopeRequired = true)]
    public void OrderStatus(string poNumber, string status)
    {
        Console.WriteLine("Status of order {0}:{1} ",
                                         poNumber , status);
    }
}
```

<span data-ttu-id="19355-149">Очередь состояний заказов создается в методе `Main`.</span><span class="sxs-lookup"><span data-stu-id="19355-149">The order status queue is created in the `Main` method.</span></span> <span data-ttu-id="19355-150">Конфигурация клиента включает конфигурацию службы состояния заказов, размещающую службу состояния заказов, как показано в следующем образце конфигурации.</span><span class="sxs-lookup"><span data-stu-id="19355-150">The client configuration includes the order status service configuration to host the order status service, as shown in the following sample configuration.</span></span>

```xml
<appSettings>
    <!-- use appSetting to configure MSMQ queue name -->
    <add key="targetQueueName" value=".\private$\ServiceModelSamples/service.svc" />
    <add key="responseQueueName" value=".\private$\ServiceModelSamples/OrderStatus" />
  </appSettings>

<system.serviceModel>

    <services>
      <service
         name="Microsoft.ServiceModel.Samples.OrderStatusService">
        <!-- Define NetMsmqEndpoint -->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamples/OrderStatus"
                  binding="netMsmqBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderStatus" />
      </service>
    </services>

    <client>
      <!-- Define NetMsmqEndpoint -->
      <endpoint name="OrderProcessorEndpoint"
                address="net.msmq://localhost/private/ServiceModelSamples/service.svc"
                binding="netMsmqBinding"
                contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
    </client>

  </system.serviceModel>
```

<span data-ttu-id="19355-151">При выполнении образца действия клиента и службы отображаются в окнах консоли как сервера, так и клиента.</span><span class="sxs-lookup"><span data-stu-id="19355-151">When you run the sample, the client and service activities are displayed in both the server and client console windows.</span></span> <span data-ttu-id="19355-152">Можно видеть, как сервер получает сообщения от клиента.</span><span class="sxs-lookup"><span data-stu-id="19355-152">You can see the server receive messages from the client.</span></span> <span data-ttu-id="19355-153">Нажмите клавишу ВВОД в каждом окне консоли, чтобы завершить работу сервера и клиента.</span><span class="sxs-lookup"><span data-stu-id="19355-153">Press ENTER in each console window to shut down the server and client.</span></span>

<span data-ttu-id="19355-154">Клиент отображает сведения о состоянии заказа, отправленные сервером.</span><span class="sxs-lookup"><span data-stu-id="19355-154">The client displays the order status information sent by the server:</span></span>

```console
Press <ENTER> to terminate client.
Status of order 70cf9d63-3dfa-4e69-81c2-23aa4478ebed :Pending
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="19355-155">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="19355-155">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="19355-156">Убедитесь, что установлен IIS 7,0, так как он необходим для активации WAS.</span><span class="sxs-lookup"><span data-stu-id="19355-156">Ensure that IIS 7.0 is installed, as it is required for WAS activation.</span></span>

2. <span data-ttu-id="19355-157">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="19355-157">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span> <span data-ttu-id="19355-158">Кроме того, необходимо установить компоненты активации WCF, отличные от HTTP:</span><span class="sxs-lookup"><span data-stu-id="19355-158">In addition, you must install the WCF non-HTTP activation components:</span></span>

    1. <span data-ttu-id="19355-159">В меню **Пуск** выберите **Панель управления**.</span><span class="sxs-lookup"><span data-stu-id="19355-159">From the **Start** menu, choose **Control Panel**.</span></span>

    2. <span data-ttu-id="19355-160">Выберите **программы и компоненты**.</span><span class="sxs-lookup"><span data-stu-id="19355-160">Select **Programs and Features**.</span></span>

    3. <span data-ttu-id="19355-161">Щелкните **Включение или отключение компонентов Windows**.</span><span class="sxs-lookup"><span data-stu-id="19355-161">Click **Turn Windows Features on or off**.</span></span>

    4. <span data-ttu-id="19355-162">В разделе **Сводка компонентов**щелкните **Добавить компоненты**.</span><span class="sxs-lookup"><span data-stu-id="19355-162">Under **Features Summary**, click **Add Features**.</span></span>

    5. <span data-ttu-id="19355-163">Разверните узел **Microsoft .NET Framework 3,0** и установите флажок **Windows Communication Foundation активации, отличной от HTTP** .</span><span class="sxs-lookup"><span data-stu-id="19355-163">Expand the **Microsoft .NET Framework 3.0** node and check the **Windows Communication Foundation Non-HTTP Activation** feature.</span></span>

3. <span data-ttu-id="19355-164">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="19355-164">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

4. <span data-ttu-id="19355-165">Запустите клиента, выполнив файл client.exe в окне командной строки.</span><span class="sxs-lookup"><span data-stu-id="19355-165">Run the client by executing client.exe from a command window.</span></span> <span data-ttu-id="19355-166">Этим создается очередь и в нее отсылается сообщение.</span><span class="sxs-lookup"><span data-stu-id="19355-166">This creates the queue and sends a message to it.</span></span> <span data-ttu-id="19355-167">Оставьте клиента запущенным, чтобы увидеть результат считывания сообщения службой.</span><span class="sxs-lookup"><span data-stu-id="19355-167">Leave the client running to see the result of the service reading the message</span></span>

5. <span data-ttu-id="19355-168">Служба активации MSMQ по умолчанию работает как сетевая служба.</span><span class="sxs-lookup"><span data-stu-id="19355-168">The MSMQ activation service runs as Network Service by default.</span></span> <span data-ttu-id="19355-169">Поэтому очередь, используемая для активации приложения, должна иметь разрешения на получение и просмотр сетевой службой.</span><span class="sxs-lookup"><span data-stu-id="19355-169">Therefore, the queue that is used to activate the application must have receive and peek permissions for Network Service.</span></span> <span data-ttu-id="19355-170">Это можно сделать при помощи консоли управления (MMC) очередью сообщений:</span><span class="sxs-lookup"><span data-stu-id="19355-170">This can be added by using the Message Queuing MMC:</span></span>

    1. <span data-ttu-id="19355-171">В меню **Пуск** выберите пункт **выполнить**, введите `Compmgmt.msc` и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="19355-171">From the **Start** menu, click **Run**, then type `Compmgmt.msc` and press ENTER.</span></span>

    2. <span data-ttu-id="19355-172">В разделе **службы и приложения**разверните узел **очередь сообщений**.</span><span class="sxs-lookup"><span data-stu-id="19355-172">Under **Services and Applications**, expand **Message Queuing**.</span></span>

    3. <span data-ttu-id="19355-173">Щелкните **частные очереди**.</span><span class="sxs-lookup"><span data-stu-id="19355-173">Click **Private Queues**.</span></span>

    4. <span data-ttu-id="19355-174">Щелкните правой кнопкой мыши очередь (servicemodelsamples/Service. svc) и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="19355-174">Right-click the queue (servicemodelsamples/Service.svc) and choose **Properties**.</span></span>

    5. <span data-ttu-id="19355-175">На вкладке **Безопасность** щелкните **Добавить** и предоставьте разрешения Просмотр и получение для сетевой службы.</span><span class="sxs-lookup"><span data-stu-id="19355-175">On the **Security** tab, click **Add** and give peek and receive permissions to Network Service.</span></span>

6. <span data-ttu-id="19355-176">Настройка службы активации Windows (WAS) для поддержки активации MSMQ.</span><span class="sxs-lookup"><span data-stu-id="19355-176">Configure the Windows Process Activation Service (WAS) to support MSMQ activation.</span></span>

    <span data-ttu-id="19355-177">Для удобства следующие действия выполняются в пакетном файле AddMsmqSiteBinding.cmd, расположенном в каталоге образца.</span><span class="sxs-lookup"><span data-stu-id="19355-177">As a convenience, the following steps are implemented in a batch file called AddMsmqSiteBinding.cmd located in the sample directory.</span></span>

    1. <span data-ttu-id="19355-178">Для поддержки активации net.msmq сначала необходимо привязать веб-узел по умолчанию к протоколу net.msmq.</span><span class="sxs-lookup"><span data-stu-id="19355-178">To support net.msmq activation, the default Web site must first be bound to the net.msmq protocol.</span></span> <span data-ttu-id="19355-179">Сделать это позволяет файл Appcmd.exe, который устанавливается с помощью набора инструментов управления IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="19355-179">This can be done using appcmd.exe, which is installed with the IIS 7.0 management toolset.</span></span> <span data-ttu-id="19355-180">В командной строке с повышенными привилегиями (с правами администратора) выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="19355-180">From an elevated (administrator) command prompt, run the following command.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
        -+bindings.[protocol='net.msmq',bindingInformation='localhost']
        ```

        > [!NOTE]
        > <span data-ttu-id="19355-181">Эта команда представляет собой одну строку текста.</span><span class="sxs-lookup"><span data-stu-id="19355-181">This command is a single line of text.</span></span>

        <span data-ttu-id="19355-182">Эта команда добавляет для веб-узел по умолчанию привязку net.msmq.</span><span class="sxs-lookup"><span data-stu-id="19355-182">This command adds a net.msmq site binding to the default Web site.</span></span>

    2. <span data-ttu-id="19355-183">Хотя все приложения на узле имеют общую привязку net.msmq, включать поддержку net.msmq можно для каждого приложения отдельно.</span><span class="sxs-lookup"><span data-stu-id="19355-183">Although all applications within a site share a common net.msmq binding, each application can enable net.msmq support individually.</span></span> <span data-ttu-id="19355-184">Чтобы включить net.msmq для приложения /servicemodelsamples, выполните следующую команду из командной строки с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="19355-184">To enable net.msmq for the /servicemodelsamples application, run the following command from an elevated command prompt.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http,net.msmq
        ```

        > [!NOTE]
        > <span data-ttu-id="19355-185">Эта команда представляет собой одну строку текста.</span><span class="sxs-lookup"><span data-stu-id="19355-185">This command is a single line of text.</span></span>

        <span data-ttu-id="19355-186">Эта команда позволяет получить доступ к приложению/сервицемоделсамплес с помощью `http://localhost/servicemodelsamples` и `net.msmq://localhost/servicemodelsamples`.</span><span class="sxs-lookup"><span data-stu-id="19355-186">This command enables the /servicemodelsamples application to be accessed using `http://localhost/servicemodelsamples` and `net.msmq://localhost/servicemodelsamples`.</span></span>

7. <span data-ttu-id="19355-187">Убедитесь, что включена служба активации MSMQ, если это не было сделано ранее.</span><span class="sxs-lookup"><span data-stu-id="19355-187">If you have not done so previously, ensure that the MSMQ activation service is enabled.</span></span> <span data-ttu-id="19355-188">В меню **Пуск** выберите пункт **выполнить**и введите `Services.msc`.</span><span class="sxs-lookup"><span data-stu-id="19355-188">From the **Start** menu, click **Run**, and type `Services.msc`.</span></span> <span data-ttu-id="19355-189">Выполните поиск в списке служб для **адаптера прослушивателя NET. MSMQ**.</span><span class="sxs-lookup"><span data-stu-id="19355-189">Search the list of services for the **Net.Msmq Listener Adapter**.</span></span> <span data-ttu-id="19355-190">Щелкните правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="19355-190">Right-click and select **Properties**.</span></span> <span data-ttu-id="19355-191">Задайте для параметра **Тип запуска** значение **автоматически**, нажмите кнопку **Применить** и нажмите кнопку **запустить** .</span><span class="sxs-lookup"><span data-stu-id="19355-191">Set the **Startup Type** to **Automatic**, click **Apply** and click the **Start** button.</span></span> <span data-ttu-id="19355-192">Этот шаг необходимо проделать всего один раз перед первым использованием службы адаптера прослушивателя Net.Msmq.</span><span class="sxs-lookup"><span data-stu-id="19355-192">This step must only be done once prior to the first usage of the Net.Msmq Listener Adapter service.</span></span>

8. <span data-ttu-id="19355-193">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="19355-193">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span> <span data-ttu-id="19355-194">Кроме того, можно изменить код на клиенте, который отправляет заказ на покупку, для отражения имени компьютера и URI очереди при отправке заказа на покупку.</span><span class="sxs-lookup"><span data-stu-id="19355-194">Additionally, change the code on the client that submits the purchase order to reflect the computer name in the URI of the queue when submitting the purchase order.</span></span> <span data-ttu-id="19355-195">Используйте следующий код:</span><span class="sxs-lookup"><span data-stu-id="19355-195">Use the following code:</span></span>

    ```csharp
    client.SubmitPurchaseOrder(po, "net.msmq://localhost/private/ServiceModelSamples/OrderStatus");
    ```

9. <span data-ttu-id="19355-196">Удалите привязку узла net.msmq, добавленную ранее для данного образца.</span><span class="sxs-lookup"><span data-stu-id="19355-196">Remove the net.msmq site binding you added for this sample.</span></span>

    <span data-ttu-id="19355-197">Для удобства следующие действия выполняются в пакетном файле RemoveMsmqSiteBinding.cmd, расположенном в каталоге с образцом.</span><span class="sxs-lookup"><span data-stu-id="19355-197">As a convenience, the following steps are implemented in a batch file called RemoveMsmqSiteBinding.cmd located in the sample directory:</span></span>

    1. <span data-ttu-id="19355-198">Удалите net.msmq из списка включенных протоколов, выполнив следующую команду из командной строки с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="19355-198">Remove net.msmq from the list of enabled protocols by running the following command from an elevated command prompt.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http
        ```

        > [!NOTE]
        > <span data-ttu-id="19355-199">Эта команда представляет собой одну строку текста.</span><span class="sxs-lookup"><span data-stu-id="19355-199">This command is a single line of text.</span></span>

    2. <span data-ttu-id="19355-200">Удалите привязку узла net.msmq, выполнив следующую команду из командной строки с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="19355-200">Remove the net.msmq site binding by running the following command from an elevated command prompt.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" --bindings.[protocol='net.msmq',bindingInformation='localhost']
        ```

        > [!NOTE]
        > <span data-ttu-id="19355-201">Эта команда представляет собой одну строку текста.</span><span class="sxs-lookup"><span data-stu-id="19355-201">This command is a single line of text.</span></span>

    > [!WARNING]
    > <span data-ttu-id="19355-202">После выполнения пакетного файла DefaultAppPool вернется к использованию .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="19355-202">Running the batch file will reset the DefaultAppPool to run using .NET Framework version 2.0.</span></span>

<span data-ttu-id="19355-203">По умолчанию с транспортом привязки `netMsmqBinding` безопасность включена.</span><span class="sxs-lookup"><span data-stu-id="19355-203">By default with the `netMsmqBinding` binding transport, security is enabled.</span></span> <span data-ttu-id="19355-204">Тип безопасности транспорта определяется двумя свойствами: `MsmqAuthenticationMode` и `MsmqProtectionLevel`.</span><span class="sxs-lookup"><span data-stu-id="19355-204">Two properties, `MsmqAuthenticationMode` and `MsmqProtectionLevel`, together determine the type of transport security.</span></span> <span data-ttu-id="19355-205">По умолчанию устанавливается режим проверки подлинности `Windows` и уровень защиты `Sign`.</span><span class="sxs-lookup"><span data-stu-id="19355-205">By default the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="19355-206">Чтобы служба MSMQ обеспечивала возможности проверки подлинности и подписывания, она должна входить в домен.</span><span class="sxs-lookup"><span data-stu-id="19355-206">For MSMQ to provide the authentication and signing feature, it must be part of a domain.</span></span> <span data-ttu-id="19355-207">При выполнении этого образца на компьютере, не входящем в домен, возникает следующая ошибка: "User's internal message queuing certificate does not exist" (не существует внутреннего сертификата очереди сообщений пользователя).</span><span class="sxs-lookup"><span data-stu-id="19355-207">If you run this sample on a computer that is not part of a domain, the following error is received: "User's internal message queuing certificate does not exist".</span></span>

### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup"></a><span data-ttu-id="19355-208">Выполнение образца на компьютере, входящем в рабочую группу</span><span class="sxs-lookup"><span data-stu-id="19355-208">To run the sample on a computer joined to a workgroup</span></span>

1. <span data-ttu-id="19355-209">Если компьютер не входит в домен, отключите безопасность транспорта, задав для режима проверки подлинности и уровня защиты значение None, как показано в следующем образце конфигурации.</span><span class="sxs-lookup"><span data-stu-id="19355-209">If your computer is not part of a domain, turn off transport security by setting the authentication mode and protection level to none as shown in the following sample configuration.</span></span>

    ```xml
    <bindings>
        <netMsmqBinding>
            <binding configurationName="TransactedBinding">
                <security mode="None"/>
            </binding>
        </netMsmqBinding>
    </bindings>
    ```

2. <span data-ttu-id="19355-210">Перед выполнением образца измените конфигурацию как сервера, так и клиента.</span><span class="sxs-lookup"><span data-stu-id="19355-210">Change the configuration on both the server and the client before you run the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="19355-211">Установка для `security mode` значения `None` эквивалентна присвоению свойствам `MsmqAuthenticationMode`, `MsmqProtectionLevel` и безопасности `Message` значения `None`.</span><span class="sxs-lookup"><span data-stu-id="19355-211">Setting `security mode` to `None` is equivalent to setting `MsmqAuthenticationMode`, `MsmqProtectionLevel` and `Message` security to `None`.</span></span>

3. <span data-ttu-id="19355-212">Для включения активации на компьютере, входящем в рабочую группу, и служба активации, и рабочий процесс должны быть запущены в определенной учетной записи пользователя (должна быть одинаковой для обоих), а очередь должна иметь ACL для определенной учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="19355-212">To enable activation in a computer joined to a workgroup, both the activation service and the worker process must be run with a specific user account (must be same for both) and the queue must have ACLs for the specific user account.</span></span>

     <span data-ttu-id="19355-213">Изменение удостоверения, с которым выполняется рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="19355-213">To change the identity that the worker process runs under:</span></span>

    1. <span data-ttu-id="19355-214">Запустите файл Inetmgr.exe.</span><span class="sxs-lookup"><span data-stu-id="19355-214">Run Inetmgr.exe.</span></span>

    2. <span data-ttu-id="19355-215">В разделе **Пулы приложений**щелкните правой кнопкой мыши элемент **AppPool** (обычно это **DefaultAppPool**) и выберите пункт **задать значения по умолчанию для пула приложений...** .</span><span class="sxs-lookup"><span data-stu-id="19355-215">Under **Application Pools**, right-click the **AppPool** (typically **DefaultAppPool**) and choose **Set Application Pool Defaults…**.</span></span>

    3. <span data-ttu-id="19355-216">Измените свойства удостоверения для использования определенной учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="19355-216">Change the Identity properties to use the specific user account.</span></span>

     <span data-ttu-id="19355-217">Изменение удостоверения, с которым выполняется служба активации.</span><span class="sxs-lookup"><span data-stu-id="19355-217">To change the identity that the Activation Service runs under:</span></span>

    1. <span data-ttu-id="19355-218">Запустите файл Services.msc.</span><span class="sxs-lookup"><span data-stu-id="19355-218">Run Services.msc.</span></span>

    2. <span data-ttu-id="19355-219">Щелкните правой кнопкой мыши **адаптер NET. мсмклистенер**и выберите пункт **свойства**.</span><span class="sxs-lookup"><span data-stu-id="19355-219">Right-click the **Net.MsmqListener Adapter**, and choose **Properties**.</span></span>

4. <span data-ttu-id="19355-220">Измените учетную запись на вкладке " **Вход в систему** ".</span><span class="sxs-lookup"><span data-stu-id="19355-220">Change the account in the **LogOn** tab.</span></span>

5. <span data-ttu-id="19355-221">В рабочей группе служба должна выполняться с маркером неограниченного доступа.</span><span class="sxs-lookup"><span data-stu-id="19355-221">In workgroup, the service must also run using an unrestricted token.</span></span> <span data-ttu-id="19355-222">Для этого запустите в командном окне следующее:</span><span class="sxs-lookup"><span data-stu-id="19355-222">To do this, run the following in a command window:</span></span>

    ```console
    sc sidtype netmsmqactivator unrestricted
    ```

## <a name="see-also"></a><span data-ttu-id="19355-223">См. также:</span><span class="sxs-lookup"><span data-stu-id="19355-223">See also</span></span>

- [<span data-ttu-id="19355-224">Примеры размещения и сохраняемости AppFabric</span><span class="sxs-lookup"><span data-stu-id="19355-224">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
