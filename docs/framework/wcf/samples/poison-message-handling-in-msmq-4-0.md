---
title: Обработка подозрительных сообщений в MSMQ 4.0
ms.date: 03/30/2017
ms.assetid: ec8d59e3-9937-4391-bb8c-fdaaf2cbb73e
ms.openlocfilehash: 4b662094923c85e825edcc9025a73f1a1b42cb9b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144244"
---
# <a name="poison-message-handling-in-msmq-40"></a><span data-ttu-id="adf21-102">Обработка подозрительных сообщений в MSMQ 4.0</span><span class="sxs-lookup"><span data-stu-id="adf21-102">Poison Message Handling in MSMQ 4.0</span></span>
<span data-ttu-id="adf21-103">В этом образце демонстрируется обработка подозрительных сообщений в службе.</span><span class="sxs-lookup"><span data-stu-id="adf21-103">This sample demonstrates how to perform poison message handling in a service.</span></span> <span data-ttu-id="adf21-104">Этот образец основан на [транс-образной пробы Связывания МСМЗ.](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)</span><span class="sxs-lookup"><span data-stu-id="adf21-104">This sample is based on the [Transacted MSMQ Binding](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) sample.</span></span> <span data-ttu-id="adf21-105">В этом образце используется привязка `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="adf21-105">This sample uses the `netMsmqBinding`.</span></span> <span data-ttu-id="adf21-106">Служба представляет собой резидентное консольное приложение, позволяющее наблюдать за получением службой сообщений из очереди.</span><span class="sxs-lookup"><span data-stu-id="adf21-106">The service is a self-hosted console application to enable you to observe the service receiving queued messages.</span></span>

 <span data-ttu-id="adf21-107">При использовании очередей клиент взаимодействует со службой посредством очереди.</span><span class="sxs-lookup"><span data-stu-id="adf21-107">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="adf21-108">Конкретно, клиент отправляет сообщения в очередь.</span><span class="sxs-lookup"><span data-stu-id="adf21-108">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="adf21-109">Служба получает сообщения из очереди.</span><span class="sxs-lookup"><span data-stu-id="adf21-109">The service receives messages from the queue.</span></span> <span data-ttu-id="adf21-110">Поэтому клиенту и службе не обязательно выполняться одновременно, чтобы взаимодействовать посредством очереди.</span><span class="sxs-lookup"><span data-stu-id="adf21-110">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>

 <span data-ttu-id="adf21-111">Подозрительное сообщение - это сообщение, которое повторно считывается из очереди, если служба, читающая сообщение, не может его обработать и завершает транзакцию, в рамках которой считывается сообщение.</span><span class="sxs-lookup"><span data-stu-id="adf21-111">A poison message is a message that is repeatedly read from a queue when the service reading the message cannot process the message and therefore terminates the transaction under which the message is read.</span></span> <span data-ttu-id="adf21-112">В таких случаях предпринимается еще одна попытка считывания сообщения.</span><span class="sxs-lookup"><span data-stu-id="adf21-112">In such cases, the message is retried again.</span></span> <span data-ttu-id="adf21-113">Теоретически этот процесс может продолжаться бесконечно, если существует проблема с сообщением.</span><span class="sxs-lookup"><span data-stu-id="adf21-113">This can theoretically go on forever if there is a problem with the message.</span></span> <span data-ttu-id="adf21-114">Это может произойти только при использовании транзакций для чтения из очереди и вывоза службы.</span><span class="sxs-lookup"><span data-stu-id="adf21-114">This can only occur when you use transactions to read from the queue and invoke the service operation.</span></span>

 <span data-ttu-id="adf21-115">Возможность поддержки обнаружения подозрительных сообщений (от ограниченного до полного) привязкой NetMsmqBinding зависит от версии MSMQ.</span><span class="sxs-lookup"><span data-stu-id="adf21-115">Based on the version of MSMQ, the NetMsmqBinding supports limited detection to full detection of poison messages.</span></span> <span data-ttu-id="adf21-116">После того как сообщение было распознано как подозрительное, оно может обрабатываться несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="adf21-116">After the message has been detected as poisoned, then it can be handled in several ways.</span></span> <span data-ttu-id="adf21-117">Поддержка обработки подозрительных сообщений (от ограниченной до полной) привязкой NetMsmqBinding зависит от версии MSMQ.</span><span class="sxs-lookup"><span data-stu-id="adf21-117">Again, based on the version of MSMQ, the NetMsmqBinding supports limited handling to full handling of poison messages.</span></span>

 <span data-ttu-id="adf21-118">Этот пример иллюстрирует ограниченные ядовитые средства, предоставляемые на Windows Server 2003 и windows XP платформы и полного яда средств, предоставляемых на Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="adf21-118">This sample illustrates the limited poison facilities provided on Windows Server 2003 and Windows XP platform and the full poison facilities provided on Windows Vista.</span></span> <span data-ttu-id="adf21-119">В обоих образцах цель состоит в том, чтобы переместить сообщение яда из очереди в другую очередь.</span><span class="sxs-lookup"><span data-stu-id="adf21-119">In both samples, the objective is to move the poison message out of the queue to another queue.</span></span> <span data-ttu-id="adf21-120">Затем эта очередь может обслуживаться службой ядовитого сообщения.</span><span class="sxs-lookup"><span data-stu-id="adf21-120">That queue can then be serviced by a poison message service.</span></span>

## <a name="msmq-v40-poison-handling-sample"></a><span data-ttu-id="adf21-121">Образец обработки подозрительных сообщений в MSMQ v4.0.</span><span class="sxs-lookup"><span data-stu-id="adf21-121">MSMQ v4.0 Poison Handling Sample</span></span>
 <span data-ttu-id="adf21-122">В Windows Vista, МСМЗ обеспечивает яд подочереди объекта, которые могут быть использованы для хранения ядовитых сообщений.</span><span class="sxs-lookup"><span data-stu-id="adf21-122">In Windows Vista, MSMQ provides a poison subqueue facility that can be used to store poison messages.</span></span> <span data-ttu-id="adf21-123">Этот пример демонстрирует наилучшую практику работы с ядовитыми сообщениями с помощью Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="adf21-123">This sample demonstrates the best practice of dealing with poison messages using Windows Vista.</span></span>

 <span data-ttu-id="adf21-124">Обнаружение яда в Windows Vista является сложным.</span><span class="sxs-lookup"><span data-stu-id="adf21-124">The poison message detection in Windows Vista is sophisticated.</span></span> <span data-ttu-id="adf21-125">Обнаружению таких сообщений способствуют три свойства.</span><span class="sxs-lookup"><span data-stu-id="adf21-125">There are 3 properties that help with detection.</span></span> <span data-ttu-id="adf21-126">Свойство <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> обозначает, сколько раз заданное сообщение перечитывается из очереди и передается приложению для обработки.</span><span class="sxs-lookup"><span data-stu-id="adf21-126">The <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> is number of times a given message is re-read from the queue and dispatched to the application for processing.</span></span> <span data-ttu-id="adf21-127">Сообщение повторно считывается из очереди, если оно повторно помещено в очередь, потому что его не удается передать приложению, или приложение выполняет откат транзакции в операции службы.</span><span class="sxs-lookup"><span data-stu-id="adf21-127">A message is re-read from the queue when it is put back into the queue because the message cannot be dispatched to the application or the application rolls back the transaction in the service operation.</span></span> <span data-ttu-id="adf21-128">Свойство <xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A> указывает, сколько раз сообщение перемещается в очередь повторных попыток.</span><span class="sxs-lookup"><span data-stu-id="adf21-128"><xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A> is the number of times the message is moved to the retry queue.</span></span> <span data-ttu-id="adf21-129">При достижении <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> сообщение перемещается в очередь повторных попыток.</span><span class="sxs-lookup"><span data-stu-id="adf21-129">When <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> is reached, the message is moved to the retry queue.</span></span> <span data-ttu-id="adf21-130">Свойство <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A> - это промежуток времени, по истечении которого сообщение перемещается из очереди повторных попыток в основную очередь.</span><span class="sxs-lookup"><span data-stu-id="adf21-130">The property <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A> is the time delay after which the message is moved from the retry queue back to the main queue.</span></span> <span data-ttu-id="adf21-131">Счетчик <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> обнуляется.</span><span class="sxs-lookup"><span data-stu-id="adf21-131">The <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> is reset to 0.</span></span> <span data-ttu-id="adf21-132">Делается еще одна попытка прочесть сообщение.</span><span class="sxs-lookup"><span data-stu-id="adf21-132">The message is tried again.</span></span> <span data-ttu-id="adf21-133">Если все попытки прочтения сообщения оказываются неудачными, сообщение помечается как подозрительное.</span><span class="sxs-lookup"><span data-stu-id="adf21-133">If all attempts to read the message have failed, then the message is marked as poisoned.</span></span>

 <span data-ttu-id="adf21-134">После этого сообщение обрабатывается в соответствии с параметрами, заданными в перечислении <xref:System.ServiceModel.MsmqBindingBase.ReceiveErrorHandling%2A>.</span><span class="sxs-lookup"><span data-stu-id="adf21-134">Once the message is marked as poisoned, the message is dealt with according to the settings in the <xref:System.ServiceModel.MsmqBindingBase.ReceiveErrorHandling%2A> enumeration.</span></span> <span data-ttu-id="adf21-135">Ниже еще раз перечислены возможные значения.</span><span class="sxs-lookup"><span data-stu-id="adf21-135">To reiterate the possible values:</span></span>

- <span data-ttu-id="adf21-136">Fault (по умолчанию): происходит сбой прослушивателя и узла службы.</span><span class="sxs-lookup"><span data-stu-id="adf21-136">Fault (default): To fault the listener and also the service host.</span></span>

- <span data-ttu-id="adf21-137">Drop: сообщение отбрасывается.</span><span class="sxs-lookup"><span data-stu-id="adf21-137">Drop: To drop the message.</span></span>

- <span data-ttu-id="adf21-138">Перемещение: Для перемещения сообщения в подкейке сообщения яда.</span><span class="sxs-lookup"><span data-stu-id="adf21-138">Move: To move the message to the poison message subqueue.</span></span> <span data-ttu-id="adf21-139">Это значение доступно только на Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="adf21-139">This value is available only on Windows Vista.</span></span>

- <span data-ttu-id="adf21-140">Reject: сообщение отклоняется и возвращается в очередь недоставленных сообщений отправителя.</span><span class="sxs-lookup"><span data-stu-id="adf21-140">Reject: To reject the message, sending the message back to the sender's dead-letter queue.</span></span> <span data-ttu-id="adf21-141">Это значение доступно только на Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="adf21-141">This value is available only on Windows Vista.</span></span>

 <span data-ttu-id="adf21-142">В этом образце демонстрируется использование команды `Move` для перемещения опасного сообщения о сбое.</span><span class="sxs-lookup"><span data-stu-id="adf21-142">The sample demonstrates using the `Move` disposition for the poison message.</span></span> <span data-ttu-id="adf21-143">`Move`вызывает сообщение, чтобы перейти к яд subqueue.</span><span class="sxs-lookup"><span data-stu-id="adf21-143">`Move` causes the message to move to the poison subqueue.</span></span>

 <span data-ttu-id="adf21-144">Контракт службы `IOrderProcessor` определяет одностороннюю службу, которую можно использовать с очередями.</span><span class="sxs-lookup"><span data-stu-id="adf21-144">The service contract is `IOrderProcessor`, which defines a one-way service that is suitable for use with queues.</span></span>

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true)]
    void SubmitPurchaseOrder(PurchaseOrder po);
}
```

 <span data-ttu-id="adf21-145">Операция службы отображает сообщение о том, что она обрабатывает заказ.</span><span class="sxs-lookup"><span data-stu-id="adf21-145">The service operation displays a message stating it is processing the order.</span></span> <span data-ttu-id="adf21-146">Чтобы продемонстрировать функциональность сообщения `SubmitPurchaseOrder` яда, операция службы бросает исключение для отката транзакции при случайном вызове службы.</span><span class="sxs-lookup"><span data-stu-id="adf21-146">To demonstrate the poison message functionality, the `SubmitPurchaseOrder` service operation throws an exception to roll back the transaction on a random invocation of the service.</span></span> <span data-ttu-id="adf21-147">В результате сообщение помещается обратно в очередь.</span><span class="sxs-lookup"><span data-stu-id="adf21-147">This causes the message to be put back in the queue.</span></span> <span data-ttu-id="adf21-148">В конечном счете это сообщение помечается как подозрительное.</span><span class="sxs-lookup"><span data-stu-id="adf21-148">Eventually the message is marked as poison.</span></span> <span data-ttu-id="adf21-149">Конфигурация настроена для перемещения сообщения о яда в подqueue яда.</span><span class="sxs-lookup"><span data-stu-id="adf21-149">The configuration is set to move the poison message to the poison subqueue.</span></span>

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

 <span data-ttu-id="adf21-150">Конфигурация службы включает следующие свойства подозрительных сообщений: `receiveRetryCount`, `maxRetryCycles`, `retryCycleDelay` и `receiveErrorHandling`, как показано в следующем файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="adf21-150">The service configuration includes the following poison message properties: `receiveRetryCount`, `maxRetryCycles`, `retryCycleDelay`, and `receiveErrorHandling` as shown in the following configuration file.</span></span>

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

## <a name="processing-messages-from-the-poison-message-queue"></a><span data-ttu-id="adf21-151">Обработка сообщений из очереди подозрительных сообщений</span><span class="sxs-lookup"><span data-stu-id="adf21-151">Processing messages from the poison message queue</span></span>
 <span data-ttu-id="adf21-152">Служба подозрительных сообщений считывает сообщения из конечной очереди подозрительных сообщений и обрабатывает их.</span><span class="sxs-lookup"><span data-stu-id="adf21-152">The poison message service reads messages from the final poison message queue and processes them.</span></span>

 <span data-ttu-id="adf21-153">Сообщения в очереди подозрительных сообщений - это сообщения, адресованные обрабатывающей сообщение службе, которая может отличаться от конечной точки службы подозрительных сообщений.</span><span class="sxs-lookup"><span data-stu-id="adf21-153">Messages in the poison message queue are messages that are addressed to the service that is processing the message, which could be different from the poison message service endpoint.</span></span> <span data-ttu-id="adf21-154">Поэтому, когда служба ядовых сообщений читает сообщения из очереди, слой канала WCF находит несоответствие в конечных точках и не отправляет сообщение.</span><span class="sxs-lookup"><span data-stu-id="adf21-154">Therefore, when the poison message service reads messages from the queue, the WCF channel layer finds the mismatch in endpoints and does not dispatch the message.</span></span> <span data-ttu-id="adf21-155">В этом случае сообщение адресуется службе, обрабатывающей заказы, но получает его служба подозрительных сообщений.</span><span class="sxs-lookup"><span data-stu-id="adf21-155">In this case, the message is addressed to the order processing service but is being received by the poison message service.</span></span> <span data-ttu-id="adf21-156">Чтобы продолжать получать сообщение, даже если оно адресовано другой конечной точке, необходимо добавить поведение `ServiceBehavior` для фильтрации адресов, в котором критерием соответствия будет соответствие любой конечной точке службы, которой адресовано сообщение.</span><span class="sxs-lookup"><span data-stu-id="adf21-156">To continue to receive the message even if the message is addressed to a different endpoint, we must add a `ServiceBehavior` to filter addresses where the match criterion is to match any service endpoint the message is addressed to.</span></span> <span data-ttu-id="adf21-157">Это необходимо для успешной обработки сообщений, считываемых из очереди подозрительных сообщений.</span><span class="sxs-lookup"><span data-stu-id="adf21-157">This is required to successfully process messages that you read from the poison message queue.</span></span>

 <span data-ttu-id="adf21-158">Реализация самой службы подозрительных сообщений очень похожа на реализацию службы.</span><span class="sxs-lookup"><span data-stu-id="adf21-158">The poison message service implementation itself is very similar to the service implementation.</span></span> <span data-ttu-id="adf21-159">Она реализует контракт и обрабатывает заказы.</span><span class="sxs-lookup"><span data-stu-id="adf21-159">It implements the contract and processes the orders.</span></span> <span data-ttu-id="adf21-160">Ниже приведен пример кода.</span><span class="sxs-lookup"><span data-stu-id="adf21-160">The code example is as follows.</span></span>

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

 <span data-ttu-id="adf21-161">В отличие от службы обработки заказов, которая считывает сообщения из очереди заказов, служба яда считывает сообщения из подочереди яда.</span><span class="sxs-lookup"><span data-stu-id="adf21-161">Unlike the order processing service that reads messages from the order queue, the poison message service reads messages from the poison subqueue.</span></span> <span data-ttu-id="adf21-162">Очередь яда представляет собой подкидочку основной очереди, называется «яд» и автоматически генерируется МСМЗ.</span><span class="sxs-lookup"><span data-stu-id="adf21-162">The poison queue is a subqueue of the main queue, is named "poison" and is automatically generated by MSMQ.</span></span> <span data-ttu-id="adf21-163">Чтобы получить к нему доступ, укажите имя основной очереди, за которым следует ";" и имя подочереди, в данном случае -"яд", как показано в следующей конфигурации образца.</span><span class="sxs-lookup"><span data-stu-id="adf21-163">To access it, provide the main queue name followed by a ";" and the subqueue name, in this case -"poison", as shown in the following sample configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="adf21-164">В образце для MSMQ v3.0 очередь подозрительных сообщений является не вложенной очередью, а очередью, в которую было перемещено сообщение.</span><span class="sxs-lookup"><span data-stu-id="adf21-164">In the sample for MSMQ v3.0, the poison queue name is not a sub-queue, rather the queue that we moved the message to.</span></span>

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

 <span data-ttu-id="adf21-165">При выполнении образца действия клиента, службы и службы подозрительных сообщений отображаются в окнах консоли.</span><span class="sxs-lookup"><span data-stu-id="adf21-165">When you run the sample, the client, service, and poison message service activities are displayed in console windows.</span></span> <span data-ttu-id="adf21-166">Можно видеть, как служба получает сообщения от клиента.</span><span class="sxs-lookup"><span data-stu-id="adf21-166">You can see the service receive messages from the client.</span></span> <span data-ttu-id="adf21-167">Нажмите клавишу ВВОД в каждом окне консоли, чтобы завершить работу служб.</span><span class="sxs-lookup"><span data-stu-id="adf21-167">Press ENTER in each console window to shut down the services.</span></span>

 <span data-ttu-id="adf21-168">Служба начинает работать, обрабатывать заказы и в произвольном порядке завершать обработку.</span><span class="sxs-lookup"><span data-stu-id="adf21-168">The service starts running, processing orders and at random starts to terminate processing.</span></span> <span data-ttu-id="adf21-169">Если появляется сообщение о том, что заказ обработан, можно снова запустить клиент для отправки другого сообщения, пока не будет видно, что служба действительно завершила обработку сообщения.</span><span class="sxs-lookup"><span data-stu-id="adf21-169">If the message indicates it has processed the order, you can run the client again to send another message until you see the service has actually terminated a message.</span></span> <span data-ttu-id="adf21-170">В зависимости от заданных параметров подозрительных сообщений перед помещением сообщения в конечную очередь подозрительных сообщений предпринимается одна попытка его обработки.</span><span class="sxs-lookup"><span data-stu-id="adf21-170">Based on the configured poison settings, the message is tried once for processing before moving it to the final poison queue.</span></span>

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

 <span data-ttu-id="adf21-171">Запустите службу подозрительных сообщений, чтобы считать подозрительное сообщение из очереди подозрительных сообщений.</span><span class="sxs-lookup"><span data-stu-id="adf21-171">Start up the poison message service to read the poisoned message from the poison queue.</span></span> <span data-ttu-id="adf21-172">В этом примере служба подозрительных сообщений считывает сообщение и обрабатывает его.</span><span class="sxs-lookup"><span data-stu-id="adf21-172">In this example, the poison message service reads the message and processes it.</span></span> <span data-ttu-id="adf21-173">Можно видеть, что заказ на покупку, обработка которого была завершена и который был помечен как подозрительный, считывается службой подозрительных сообщений.</span><span class="sxs-lookup"><span data-stu-id="adf21-173">You could see that the purchase order that was terminated and poisoned is read by the poison message service.</span></span>

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

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="adf21-174">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="adf21-174">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="adf21-175">Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)</span><span class="sxs-lookup"><span data-stu-id="adf21-175">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="adf21-176">При первом запуске служба проверит наличие очереди.</span><span class="sxs-lookup"><span data-stu-id="adf21-176">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="adf21-177">Если очередь отсутствует, служба ее создаст.</span><span class="sxs-lookup"><span data-stu-id="adf21-177">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="adf21-178">Можно сначала запустить службу, чтобы создать очередь, либо создать ее с помощью диспетчера очередей MSMQ.</span><span class="sxs-lookup"><span data-stu-id="adf21-178">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="adf21-179">Чтобы создать очередь в Windows 2008, выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="adf21-179">Follow these steps to create a queue in Windows 2008.</span></span>

    1. <span data-ttu-id="adf21-180">Открытый менеджер сервера в Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="adf21-180">Open Server Manager in Visual Studio 2012.</span></span>

    2. <span data-ttu-id="adf21-181">Расширьте вкладку **«Функции».**</span><span class="sxs-lookup"><span data-stu-id="adf21-181">Expand the **Features** tab.</span></span>

    3. <span data-ttu-id="adf21-182">Справа щелкните **Очереди частных сообщений**и выберите **Новый,** **Частный Конвей**.</span><span class="sxs-lookup"><span data-stu-id="adf21-182">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>

    4. <span data-ttu-id="adf21-183">Проверьте **транзакционную** коробку.</span><span class="sxs-lookup"><span data-stu-id="adf21-183">Check the **Transactional** box.</span></span>

    5. <span data-ttu-id="adf21-184">Введите `ServiceModelSamplesTransacted` как имя новой очереди.</span><span class="sxs-lookup"><span data-stu-id="adf21-184">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>

3. <span data-ttu-id="adf21-185">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="adf21-185">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

4. <span data-ttu-id="adf21-186">Чтобы запустить образец в одно- или кросс-компьютерной конфигурации, измените имена очередей, чтобы отразить фактическое имя хоста вместо локального и следуйте инструкциям в [Запуске образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/running-the-samples.md)</span><span class="sxs-lookup"><span data-stu-id="adf21-186">To run the sample in a single- or cross-computer configuration, change the queue names to reflect the actual hostname instead of localhost and follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

 <span data-ttu-id="adf21-187">По умолчанию с транспортом привязки `netMsmqBinding` безопасность включена.</span><span class="sxs-lookup"><span data-stu-id="adf21-187">By default with the `netMsmqBinding` binding transport, security is enabled.</span></span> <span data-ttu-id="adf21-188">Тип безопасности транспорта определяется двумя свойствами: `MsmqAuthenticationMode` и `MsmqProtectionLevel`.</span><span class="sxs-lookup"><span data-stu-id="adf21-188">Two properties, `MsmqAuthenticationMode` and `MsmqProtectionLevel`, together determine the type of transport security.</span></span> <span data-ttu-id="adf21-189">По умолчанию задан режим проверки подлинности `Windows` и уровень защиты `Sign`.</span><span class="sxs-lookup"><span data-stu-id="adf21-189">By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="adf21-190">Чтобы служба MSMQ обеспечивала возможности проверки подлинности и подписывания, она должна входить в домен.</span><span class="sxs-lookup"><span data-stu-id="adf21-190">For MSMQ to provide the authentication and signing feature, it must be part of a domain.</span></span> <span data-ttu-id="adf21-191">При выполнении этого примера на компьютере, не входящем в домен, возникает следующая ошибка: "User's internal message queuing certificate does not exist" (не существует внутреннего сертификата очереди сообщений пользователя).</span><span class="sxs-lookup"><span data-stu-id="adf21-191">If you run this sample on a computer that is not part of a domain, you receive the following error: "User's internal message queuing certificate does not exist".</span></span>

#### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup"></a><span data-ttu-id="adf21-192">Выполнение образца на компьютере, входящем в рабочую группу</span><span class="sxs-lookup"><span data-stu-id="adf21-192">To run the sample on a computer joined to a workgroup</span></span>

1. <span data-ttu-id="adf21-193">Если компьютер не входит в домен, отключите безопасность транспорта, задав для режима проверки подлинности и уровня защиты значение `None`, как показано в следующем образце конфигурации.</span><span class="sxs-lookup"><span data-stu-id="adf21-193">If your computer is not part of a domain, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration:</span></span>

    ```xml
    <bindings>
        <netMsmqBinding>
            <binding name="TransactedBinding">
                <security mode="None"/>
            </binding>
        </netMsmqBinding>
    </bindings>
    ```

     <span data-ttu-id="adf21-194">Обеспечьте связь конечной точки с привязкой, задав атрибут bindingConfiguration конечной точки.</span><span class="sxs-lookup"><span data-stu-id="adf21-194">Ensure the endpoint is associated with the binding by setting the endpoint's bindingConfiguration attribute.</span></span>

2. <span data-ttu-id="adf21-195">Убедитесь, что перед запуском образца необходимо изменить конфигурацию на сервере PoisonMessageServer, сервере и клиенте.</span><span class="sxs-lookup"><span data-stu-id="adf21-195">Ensure that you change the configuration on the PoisonMessageServer, server, and the client before you run the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="adf21-196">Задание для `security mode` значения `None` эквивалентно заданию для параметров безопасности `MsmqAuthenticationMode`, `MsmqProtectionLevel` и `Message` значения `None`.</span><span class="sxs-lookup"><span data-stu-id="adf21-196">Setting `security mode` to `None` is equivalent to setting `MsmqAuthenticationMode`, `MsmqProtectionLevel`, and `Message` security to `None`.</span></span>  
  
3. <span data-ttu-id="adf21-197">Чтобы обеспечить обмен метаданными, необходимо зарегистрировать URL-адрес с привязкой http.</span><span class="sxs-lookup"><span data-stu-id="adf21-197">In order for Meta Data Exchange to work, we register a URL with http binding.</span></span> <span data-ttu-id="adf21-198">Это требует выполнения службы в командном окне с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="adf21-198">This requires that the service run in an elevated command window.</span></span> <span data-ttu-id="adf21-199">В противном случае вы `Unhandled Exception: System.ServiceModel.AddressAccessDeniedException: HTTP could not register URL http://+:8000/ServiceModelSamples/service/. Your process does not have access rights to this namespace (see https://go.microsoft.com/fwlink/?LinkId=70353 for details). ---> System.Net.HttpListenerException: Access is denied`получите исключение, такое как: .</span><span class="sxs-lookup"><span data-stu-id="adf21-199">Otherwise, you get an exception such as: `Unhandled Exception: System.ServiceModel.AddressAccessDeniedException: HTTP could not register URL http://+:8000/ServiceModelSamples/service/. Your process does not have access rights to this namespace (see https://go.microsoft.com/fwlink/?LinkId=70353 for details). ---> System.Net.HttpListenerException: Access is denied`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="adf21-200">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="adf21-200">The samples may already be installed on your computer.</span></span> <span data-ttu-id="adf21-201">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="adf21-201">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="adf21-202">Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы.</span><span class="sxs-lookup"><span data-stu-id="adf21-202">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="adf21-203">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="adf21-203">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Poison\MSMQ4`
