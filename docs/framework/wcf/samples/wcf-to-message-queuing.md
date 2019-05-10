---
title: Отправка сообщений из приложения Windows Communication Foundation в приложение MSMQ
ms.date: 03/30/2017
ms.assetid: 78d0d0c9-648e-4d4a-8f0a-14d9cafeead9
ms.openlocfilehash: e0c4fa3e3f475b2d0996885d8eda91faabc9ba93
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625790"
---
# <a name="windows-communication-foundation-to-message-queuing"></a><span data-ttu-id="9c80e-102">Отправка сообщений из приложения Windows Communication Foundation в приложение MSMQ</span><span class="sxs-lookup"><span data-stu-id="9c80e-102">Windows Communication Foundation to Message Queuing</span></span>
<span data-ttu-id="9c80e-103">В этом примере показано, как приложение Windows Communication Foundation (WCF) можно отправлять сообщения приложению очереди сообщений (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="9c80e-103">This sample demonstrates how a Windows Communication Foundation (WCF) application can send a message to a Message Queuing (MSMQ) application.</span></span> <span data-ttu-id="9c80e-104">Служба представляет собой резидентное консольное приложение, позволяющее наблюдать за получением службой сообщений из очереди.</span><span class="sxs-lookup"><span data-stu-id="9c80e-104">The service is a self-hosted console application to enable you to observe the service receiving queued messages.</span></span> <span data-ttu-id="9c80e-105">Одновременная работа службы и клиента не требуется.</span><span class="sxs-lookup"><span data-stu-id="9c80e-105">The service and client do not have to be running at the same time.</span></span>

 <span data-ttu-id="9c80e-106">Служба получает сообщения от очереди и обрабатывает заказы.</span><span class="sxs-lookup"><span data-stu-id="9c80e-106">The service receives messages from the queue and processes orders.</span></span> <span data-ttu-id="9c80e-107">Служба создает транзакционную очередь и создает обработчик полученных сообщений, как показано в следующем образце кода.</span><span class="sxs-lookup"><span data-stu-id="9c80e-107">The service creates a transactional queue and sets up a message received message handler, as shown in the following sample code.</span></span>

```csharp
static void Main(string[] args)
{
    if (!MessageQueue.Exists(
              ConfigurationManager.AppSettings["queueName"]))
       MessageQueue.Create(
           ConfigurationManager.AppSettings["queueName"], true);
        //Connect to the queue
        MessageQueue Queue = new
    MessageQueue(ConfigurationManager.AppSettings["queueName"]);
    Queue.ReceiveCompleted +=
                 new ReceiveCompletedEventHandler(ProcessOrder);
    Queue.BeginReceive();
    Console.WriteLine("Order Service is running");
    Console.ReadLine();
}
```

 <span data-ttu-id="9c80e-108">При получении сообщения в очереди вызывается обработчик сообщений `ProcessOrder`.</span><span class="sxs-lookup"><span data-stu-id="9c80e-108">When a message is received in the queue, the message handler `ProcessOrder` is invoked.</span></span>

```csharp
public static void ProcessOrder(Object source,
    ReceiveCompletedEventArgs asyncResult)
{
    try
    {
        // Connect to the queue.
        MessageQueue Queue = (MessageQueue)source;
        // End the asynchronous receive operation.
        System.Messaging.Message msg =
                     Queue.EndReceive(asyncResult.AsyncResult);
        msg.Formatter = new System.Messaging.XmlMessageFormatter(
                                new Type[] { typeof(PurchaseOrder) });
        PurchaseOrder po = (PurchaseOrder) msg.Body;
        Random statusIndexer = new Random();
        po.Status = PurchaseOrder.OrderStates[statusIndexer.Next(3)];
        Console.WriteLine("Processing {0} ", po);
        Queue.BeginReceive();
    }
    catch (System.Exception ex)
    {
        Console.WriteLine(ex.Message);
    }

}
```

 <span data-ttu-id="9c80e-109">Служба извлекает `ProcessOrder` из тела сообщения MSMQ и обрабатывает заказ.</span><span class="sxs-lookup"><span data-stu-id="9c80e-109">The service extracts the `ProcessOrder` from the MSMQ message body, and processes the order.</span></span>

 <span data-ttu-id="9c80e-110">Имя очереди MSMQ задается в разделе appSettings файла конфигурации, как показано в следующем образце конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9c80e-110">The MSMQ queue name is specified in an appSettings section of the configuration file, as shown in the following sample configuration.</span></span>

```xml
<appSettings>
    <add key="orderQueueName" value=".\private$\Orders" />
</appSettings>
```

> [!NOTE]
>  <span data-ttu-id="9c80e-111">В имени очереди для определения локального компьютера используется точка (.), а в пути в качестве разделителей используются символы обратной косой черты.</span><span class="sxs-lookup"><span data-stu-id="9c80e-111">The queue name uses a dot (.) for the local computer and backslash separators in its path.</span></span>

 <span data-ttu-id="9c80e-112">Клиент создает заказ на покупку и отправляет его в пределах транзакции, как показано в следующем образце кода.</span><span class="sxs-lookup"><span data-stu-id="9c80e-112">The client creates a purchase order and submits the purchase order within the scope of a transaction, as shown in the following sample code.</span></span>

```csharp
// Create the purchase order
PurchaseOrder po = new PurchaseOrder();
// Fill in the details
...

OrderProcessorClient client = new OrderProcessorClient("OrderResponseEndpoint");

MsmqMessage<PurchaseOrder> ordermsg = new MsmqMessage<PurchaseOrder>(po);
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
{
    client.SubmitPurchaseOrder(ordermsg);
    scope.Complete();
}
Console.WriteLine("Order has been submitted:{0}", po);

//Closing the client gracefully closes the connection and cleans up resources
client.Close();
```

 <span data-ttu-id="9c80e-113">При отправке сообщения MSMQ в очередь клиент использует внутренний пользовательский порядок сообщений.</span><span class="sxs-lookup"><span data-stu-id="9c80e-113">The client uses a custom client in-order to send the MSMQ message to the queue.</span></span> <span data-ttu-id="9c80e-114">Поскольку приложение, которое получает и обрабатывает сообщение является приложением MSMQ, а не приложения WCF, является между двумя приложениями отсутствует неявный контракт службы.</span><span class="sxs-lookup"><span data-stu-id="9c80e-114">Because the application that receives and processes the message is an MSMQ application and not a WCF application, there is no implicit service contract between the two applications.</span></span> <span data-ttu-id="9c80e-115">Таким образом, в данном сценарии невозможно создать прокси-класс при помощи средства Svculti.exe.</span><span class="sxs-lookup"><span data-stu-id="9c80e-115">So, we cannot create a proxy using the Svcutil.exe tool in this scenario.</span></span>

 <span data-ttu-id="9c80e-116">Пользовательский клиент в основном одинаков для всех приложений WCF, использующих `MsmqIntegration` привязки для отправки сообщений.</span><span class="sxs-lookup"><span data-stu-id="9c80e-116">The custom client is essentially the same for all WCF applications that use the `MsmqIntegration` binding to send messages.</span></span> <span data-ttu-id="9c80e-117">В отличие от других клиентов, он не включает ряд операций службы.</span><span class="sxs-lookup"><span data-stu-id="9c80e-117">Unlike other clients, it does not include a range of service operations.</span></span> <span data-ttu-id="9c80e-118">В него входит только операция отправки сообщения.</span><span class="sxs-lookup"><span data-stu-id="9c80e-118">It is a submit message operation only.</span></span>

```csharp
[System.ServiceModel.ServiceContractAttribute(Namespace = "http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true, Action = "*")]
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);
}

public partial class OrderProcessorClient : System.ServiceModel.ClientBase<IOrderProcessor>, IOrderProcessor
{
    public OrderProcessorClient(){}

    public OrderProcessorClient(string configurationName)
        : base(configurationName)
    { }

    public OrderProcessorClient(System.ServiceModel.Channels.Binding binding, System.ServiceModel.EndpointAddress address)
        : base(binding, address)
    { }

    public void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg)
    {
        base.Channel.SubmitPurchaseOrder(msg);
    }
}
```

 <span data-ttu-id="9c80e-119">При выполнении образца действия клиента и службы отображаются в окнах консоли как службы, так и клиента.</span><span class="sxs-lookup"><span data-stu-id="9c80e-119">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="9c80e-120">Можно видеть, как служба получает сообщения от клиента.</span><span class="sxs-lookup"><span data-stu-id="9c80e-120">You can see the service receive messages from the client.</span></span> <span data-ttu-id="9c80e-121">Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент.</span><span class="sxs-lookup"><span data-stu-id="9c80e-121">Press ENTER in each console window to shut down the service and client.</span></span> <span data-ttu-id="9c80e-122">Обратите внимание, что поскольку используется очередь, клиенту и службе не обязательно быть запущенными и работать одновременно.</span><span class="sxs-lookup"><span data-stu-id="9c80e-122">Note that because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="9c80e-123">Например, можно запустить клиент, выключить его, а затем запустить службу и все равно получить сообщения клиента.</span><span class="sxs-lookup"><span data-stu-id="9c80e-123">For example, you could run the client, shut it down, and then start up the service and it would still receive its messages.</span></span>

> [!NOTE]
>  <span data-ttu-id="9c80e-124">Данный образец требует установки очереди сообщений.</span><span class="sxs-lookup"><span data-stu-id="9c80e-124">This sample requires the installation of Message Queuing.</span></span> <span data-ttu-id="9c80e-125">См. инструкции по установке в [Message Queuing](https://go.microsoft.com/fwlink/?LinkId=94968).</span><span class="sxs-lookup"><span data-stu-id="9c80e-125">See the installation instructions in [Message Queuing](https://go.microsoft.com/fwlink/?LinkId=94968).</span></span>  
  
### <a name="to-setup-build-and-run-the-sample"></a><span data-ttu-id="9c80e-126">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="9c80e-126">To setup, build, and run the sample</span></span>  
  
1. <span data-ttu-id="9c80e-127">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9c80e-127">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="9c80e-128">При первом запуске служба проверит наличие очереди.</span><span class="sxs-lookup"><span data-stu-id="9c80e-128">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="9c80e-129">Если очередь отсутствует, служба ее создаст.</span><span class="sxs-lookup"><span data-stu-id="9c80e-129">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="9c80e-130">Можно сначала запустить службу, чтобы создать очередь, либо создать ее с помощью диспетчера очередей MSMQ.</span><span class="sxs-lookup"><span data-stu-id="9c80e-130">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="9c80e-131">Чтобы создать очередь в Windows 2008, выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="9c80e-131">Follow these steps to create a queue in Windows 2008.</span></span>  
  
    1. <span data-ttu-id="9c80e-132">Откройте диспетчер серверов в Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="9c80e-132">Open Server Manager in Visual Studio 2012.</span></span>  
  
    2. <span data-ttu-id="9c80e-133">Разверните **функции** вкладки.</span><span class="sxs-lookup"><span data-stu-id="9c80e-133">Expand the **Features** tab.</span></span>  
  
    3. <span data-ttu-id="9c80e-134">Щелкните правой кнопкой мыши **очереди личных сообщений**и выберите **New**, **частную очередь**.</span><span class="sxs-lookup"><span data-stu-id="9c80e-134">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>  
  
    4. <span data-ttu-id="9c80e-135">Проверьте **транзакционная** поле.</span><span class="sxs-lookup"><span data-stu-id="9c80e-135">Check the **Transactional** box.</span></span>  
  
    5. <span data-ttu-id="9c80e-136">Введите `ServiceModelSamplesTransacted` как имя новой очереди.</span><span class="sxs-lookup"><span data-stu-id="9c80e-136">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>  
  
3. <span data-ttu-id="9c80e-137">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9c80e-137">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="9c80e-138">Чтобы запустить образец в конфигурации с одним компьютером, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9c80e-138">To run the sample in a single-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="9c80e-139">Запуск образца на нескольких компьютерах</span><span class="sxs-lookup"><span data-stu-id="9c80e-139">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="9c80e-140">Скопируйте на компьютер службы файлы служебной программы из папки \service\bin\ в папку языка.</span><span class="sxs-lookup"><span data-stu-id="9c80e-140">Copy the service program files from the \service\bin\ folder, under the language-specific folder, to the service computer.</span></span>  
  
2. <span data-ttu-id="9c80e-141">Скопируйте на клиентские компьютеры файлы из папки \client\bin\ в папку языка.</span><span class="sxs-lookup"><span data-stu-id="9c80e-141">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
3. <span data-ttu-id="9c80e-142">В файле Client.exe.config измените адрес конечной точки клиента, указав имя компьютера службы вместо «.».</span><span class="sxs-lookup"><span data-stu-id="9c80e-142">In the Client.exe.config file, change the client endpoint address to specify the service computer name instead of ".".</span></span>  
  
4. <span data-ttu-id="9c80e-143">На компьютере службы запустите из командной строки программу Service.exe.</span><span class="sxs-lookup"><span data-stu-id="9c80e-143">On the service computer, launch Service.exe from a command prompt.</span></span>  
  
5. <span data-ttu-id="9c80e-144">На клиентском компьютере из командной строки запустите программу Client.exe.</span><span class="sxs-lookup"><span data-stu-id="9c80e-144">On the client computer, launch Client.exe from a command prompt.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9c80e-145">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9c80e-145">The samples may already be installed on your computer.</span></span> <span data-ttu-id="9c80e-146">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="9c80e-146">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9c80e-147">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="9c80e-147">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9c80e-148">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="9c80e-148">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\WcfToMsmq`  
  
## <a name="see-also"></a><span data-ttu-id="9c80e-149">См. также</span><span class="sxs-lookup"><span data-stu-id="9c80e-149">See also</span></span>

- [<span data-ttu-id="9c80e-150">Практическое руководство. Обмен сообщениями с конечными точками WCF и приложений с очередями сообщений</span><span class="sxs-lookup"><span data-stu-id="9c80e-150">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)
- [<span data-ttu-id="9c80e-151">Очереди сообщений</span><span class="sxs-lookup"><span data-stu-id="9c80e-151">Message Queuing</span></span>](https://go.microsoft.com/fwlink/?LinkId=94968)
