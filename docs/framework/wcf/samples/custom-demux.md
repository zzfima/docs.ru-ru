---
title: Пользовательское демультиплексирование
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc54065c-518e-4146-b24a-0fe00038bfa7
caps.latest.revision: 41
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 45184c2d884347baef4090ed496e22e77aab5423
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="custom-demux"></a><span data-ttu-id="fcfd1-102">Пользовательское демультиплексирование</span><span class="sxs-lookup"><span data-stu-id="fcfd1-102">Custom Demux</span></span>
<span data-ttu-id="fcfd1-103">В этом примере показано, как можно сопоставлять заголовки сообщений MSMQ с различными операциями служб, чтобы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] служб, использующих <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> не ограничены использованием одной операции службы, как показано в [служба очереди сообщений Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) и [Windows Communication Foundation для Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) образцов.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-103">This sample demonstrates how MSMQ message headers can be mapped to different service operations so that [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services that use <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> are not limited to using one service operation as demonstrated in the [Message Queuing to Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) and [Windows Communication Foundation to Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) samples.</span></span>  
  
 <span data-ttu-id="fcfd1-104">В данном образце служба представляет собой резидентное консольное приложение, позволяющее наблюдать службу, получающую сообщения из очереди.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-104">The service in this sample is a self-hosted console application to enable you to observe the service that receives queued messages.</span></span>  
  
 <span data-ttu-id="fcfd1-105">Контракт службы `IOrderProcessor` определяет одностороннюю службу, которую можно использовать с очередями.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-105">The service contract is `IOrderProcessor`, and defines a one-way service that is suitable for use with queues.</span></span>  

```csharp
[ServiceContract]  
[KnownType(typeof(PurchaseOrder))]  
[KnownType(typeof(String))]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true, Name = "SubmitPurchaseOrder")]  
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);  
  
    [OperationContract(IsOneWay = true, Name = "CancelPurchaseOrder")]  
    void CancelPurchaseOrder(MsmqMessage<string> ponumber);  
}  
```

 <span data-ttu-id="fcfd1-106">У сообщения MSMQ нет заголовка Action.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-106">An MSMQ message does not have an Action header.</span></span> <span data-ttu-id="fcfd1-107">Из-за этого автоматически соотнести различные сообщения MSMQ с контрактами операций невозможно.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-107">It is not possible to map different MSMQ messages to operation contracts automatically.</span></span> <span data-ttu-id="fcfd1-108">Поэтому может существовать только один контракт операции.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-108">Therefore, there can be only one operation contract.</span></span> <span data-ttu-id="fcfd1-109">Чтобы преодолеть это ограничение, служба реализует метод <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> интерфейса <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector>.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-109">To overcome this limitation, the service implements the <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> method of the <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> interface.</span></span> <span data-ttu-id="fcfd1-110">Метод <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> позволяет службе сопоставить данный заголовок сообщения определенной операции службы.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-110">The <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> method enables the service to map a given header of the message to a particular service operation.</span></span> <span data-ttu-id="fcfd1-111">В этом образце метка заголовка сообщения сопоставляется операциям службы.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-111">In this sample, the message's label header is mapped to the service operations.</span></span> <span data-ttu-id="fcfd1-112">Параметр `Name` контракта операции определяет, какую операцию службы следует выполнить для данной метки сообщения.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-112">The `Name` parameter of the operation contract determines which service operation must be dispatched for a given message label.</span></span> <span data-ttu-id="fcfd1-113">Например, если метка заголовка сообщения содержит "SubmitPurchaseOrder", вызывается операция службы "SubmitPurchaseOrder".</span><span class="sxs-lookup"><span data-stu-id="fcfd1-113">For example, if the message's label header contains "SubmitPurchaseOrder", the "SubmitPurchaseOrder" service operation is invoked.</span></span>  

```csharp
public class OperationSelector : IDispatchOperationSelector  
{  
    public string SelectOperation(ref System.ServiceModel.Channels.Message message)  
    {  
        MsmqIntegrationMessageProperty property = MsmqIntegrationMessageProperty.Get(message);  
        return property.Label;  
    }  
}  
```

 <span data-ttu-id="fcfd1-114">Служба должна реализовывать метод <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%28System.ServiceModel.Description.ContractDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%2CSystem.ServiceModel.Dispatcher.DispatchRuntime%29> интерфейса <xref:System.ServiceModel.Description.IContractBehavior>, как показано в следующем образце кода.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-114">The service must implement the <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%28System.ServiceModel.Description.ContractDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%2CSystem.ServiceModel.Dispatcher.DispatchRuntime%29> method of the <xref:System.ServiceModel.Description.IContractBehavior> interface as shown in the following sample code.</span></span> <span data-ttu-id="fcfd1-115">Это применяет пользовательский `OperationSelector` к среде выполнения инфраструктуры службы.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-115">This applies the custom `OperationSelector` to the service framework dispatch runtime.</span></span>  

```csharp
void IContractBehavior.ApplyDispatchBehavior(ContractDescription description, ServiceEndpoint endpoint, DispatchRuntime dispatch)  
{  
    dispatch.OperationSelector = new OperationSelector();  
}  
```

 <span data-ttu-id="fcfd1-116">Перед тем как попасть к OperationSelector, сообщение должно пройти через свойство <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> диспетчера.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-116">A message must pass through the dispatcher's <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> before getting to the OperationSelector.</span></span> <span data-ttu-id="fcfd1-117">По умолчанию сообщение отклоняется, если его действие не обнаружено ни в одном контракте, реализованном службой.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-117">By default a message is rejected if its action cannot be found on any contract implemented by the service.</span></span> <span data-ttu-id="fcfd1-118">Чтобы избежать этого, реализуем поведение <xref:System.ServiceModel.Description.IEndpointBehavior> с именем `MatchAllFilterBehavior`, позволяющее любым сообщениям проходить через фильтр `ContractFilter`, применяя <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter> следующим образом.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-118">To avoid this check, we implement an <xref:System.ServiceModel.Description.IEndpointBehavior> named `MatchAllFilterBehavior`, which allows any message to pass through the `ContractFilter` by applying the <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter> as follows.</span></span>  

```csharp
public void ApplyDispatchBehavior(ServiceEndpoint serviceEndpoint, EndpointDispatcher endpointDispatcher)  
{  
    endpointDispatcher.ContractFilter = new MatchAllMessageFilter();  
}  
```
  
 <span data-ttu-id="fcfd1-119">При получении сообщения службой используются сведения, содержащиеся в метке заголовка, и выполняется соответствующая операция службы.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-119">When a message is received by the service, the appropriate service operation is dispatched using the information provided by the label header.</span></span> <span data-ttu-id="fcfd1-120">Тело сообщения десериализуется в объект `PurchaseOrder`, как показано в следующем образце кода.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-120">The body of the message is deserialized into a `PurchaseOrder` object, as shown in the following sample code.</span></span>  

```csharp
[OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
public void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg)  
{  
    PurchaseOrder po = (PurchaseOrder)msg.Body;  
    Random statusIndexer = new Random();  
    po.Status = (OrderStates)statusIndexer.Next(3);  
    Console.WriteLine("Processing {0} ", po);  
}  
```

 <span data-ttu-id="fcfd1-121">Служба является резидентной.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-121">The service is self-hosted.</span></span> <span data-ttu-id="fcfd1-122">При работе с MSMQ используемую очередь следует создавать заранее.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-122">When using the MSMQ, the queue that is used must be created in advance.</span></span> <span data-ttu-id="fcfd1-123">Это можно сделать вручную или с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-123">This can be done manually or through code.</span></span> <span data-ttu-id="fcfd1-124">В данном образце служба содержит код для проверки наличия очереди и ее создания, если очереди нет.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-124">In this sample, the service contains code to check for the existence of the queue and creates it if the queue does not exist.</span></span> <span data-ttu-id="fcfd1-125">Имя очереди считывается из файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-125">The queue name is read from the configuration file.</span></span>  

```csharp
public static void Main()  
{  
    // Get MSMQ queue name from app settings in configuration  
    string queueName = ConfigurationManager.AppSettings["orderQueueName"];  
  
    // Create the transacted MSMQ queue if necessary.  
    if (!MessageQueue.Exists(queueName))  
        MessageQueue.Create(queueName, true);  
  
    // Create a ServiceHost for the CalculatorService type.  
    using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))  
    {                 
        ServiceEndpoint endpoint = serviceHost.Description.Endpoints[0];  
        endpoint.Behaviors.Add(new MatchAllFilterBehavior());  
  
        //Open the ServiceHost to create listeners and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.ReadLine();  
  
        // Close the ServiceHost to shutdown the service.  
        serviceHost.Close();  
    }  
}  
```

 <span data-ttu-id="fcfd1-126">Имя очереди MSMQ задается в разделе appSettings файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-126">The MSMQ queue name is specified in an appSettings section of the configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fcfd1-127">В имени очереди для определения локального компьютера используется точка (.), а в пути в качестве разделителей используются символы обратной косой черты.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-127">The queue name uses a dot (.) for the local computer and backslash separators in its path.</span></span> <span data-ttu-id="fcfd1-128">В адресе конечной точки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] задается схема msmq.formatname, для обозначения локального компьютера используется имя localhost.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-128">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint address specifies a msmq.formatname scheme, and uses localhost for the local computer.</span></span> <span data-ttu-id="fcfd1-129">Схеме следует адрес очереди в правильном формате в соответствии с рекомендациям о создании адресов имен в формате MSMQ.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-129">What follows the scheme is a properly formatted queue address according to the MSMQ Format name addressing guidelines.</span></span>  
  
```xml  
<appSettings>  
    <!-- Use appSetting to configure the MSMQ queue name. -->  
    <add key="queueName" value=".\private$\Orders" />  
</appSettings>  
```  
  
> [!NOTE]
>  <span data-ttu-id="fcfd1-130">В этом примере требуется установка [очереди сообщений](http://go.microsoft.com/fwlink/?LinkId=95143).</span><span class="sxs-lookup"><span data-stu-id="fcfd1-130">This sample requires the installation of [Message Queuing](http://go.microsoft.com/fwlink/?LinkId=95143).</span></span>  
  
 <span data-ttu-id="fcfd1-131">Запустите службу и выполните клиент.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-131">Start the service and run the client.</span></span>  
  
 <span data-ttu-id="fcfd1-132">Клиент получает следующий результат.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-132">The following output is seen on the client.</span></span>  
  
```  
Placed the order:Purchase Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
Canceled the Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="fcfd1-133">Служба должна предоставить следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-133">The following output must be seen on the service.</span></span>  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
Processing Purchase Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Shipped  
Purchase Order 28fc457a-1a56-4fe0-9dde-156965c21ed6 is canceled  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="fcfd1-134">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="fcfd1-134">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="fcfd1-135">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="fcfd1-135">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="fcfd1-136">При первом запуске служба проверит наличие очереди.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-136">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="fcfd1-137">Если очередь отсутствует, служба ее создаст.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-137">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="fcfd1-138">Можно сначала запустить службу, чтобы создать очередь, либо создать ее с помощью диспетчера очередей MSMQ.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-138">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="fcfd1-139">Чтобы создать очередь в Windows 2008, выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-139">Follow these steps to create a queue in Windows 2008.</span></span>  
  
    1.  <span data-ttu-id="fcfd1-140">Откройте диспетчер сервера в [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fcfd1-140">Open Server Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
    2.  <span data-ttu-id="fcfd1-141">Разверните **функции** вкладки.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-141">Expand the **Features** tab.</span></span>  
  
    3.  <span data-ttu-id="fcfd1-142">Щелкните правой кнопкой мыши **очереди личных сообщений**и выберите **New**, **частную очередь**.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-142">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>  
  
    4.  <span data-ttu-id="fcfd1-143">Проверьте **транзакций** поле.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-143">Check the **Transactional** box.</span></span>  
  
    5.  <span data-ttu-id="fcfd1-144">Введите `ServiceModelSamplesTransacted` качестве имени новой очереди.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-144">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>  
  
3.  <span data-ttu-id="fcfd1-145">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="fcfd1-145">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="fcfd1-146">Для запуска образца в конфигурации с одним или несколькими компьютерами следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="fcfd1-146">To run the sample in a single- or cross- computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="fcfd1-147">Запуск образца на нескольких компьютерах</span><span class="sxs-lookup"><span data-stu-id="fcfd1-147">To run the sample across computers</span></span>  
  
1.  <span data-ttu-id="fcfd1-148">Скопируйте на компьютер службы файлы служебной программы из папки \service\bin\ в папку языка.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-148">Copy the service program files from the \service\bin\ folder, under the language-specific folder, to the service computer.</span></span>  
  
2.  <span data-ttu-id="fcfd1-149">Скопируйте на клиентские компьютеры файлы из папки \client\bin\ в папку языка.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-149">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
3.  <span data-ttu-id="fcfd1-150">В файле Client.exe.config измените orderQueueName, указав имя компьютера службы вместо «.».</span><span class="sxs-lookup"><span data-stu-id="fcfd1-150">In the Client.exe.config file, change the orderQueueName to specify the service computer name instead of ".".</span></span>  
  
4.  <span data-ttu-id="fcfd1-151">На компьютере службы запустите из командной строки программу Service.exe.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-151">On the service computer, launch Service.exe from a command prompt.</span></span>  
  
5.  <span data-ttu-id="fcfd1-152">На клиентском компьютере из командной строки запустите программу Client.exe.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-152">On the client computer, launch Client.exe from a command prompt.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fcfd1-153">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-153">The samples may already be installed on your computer.</span></span> <span data-ttu-id="fcfd1-154">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="fcfd1-154">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="fcfd1-155">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) Чтобы загрузить все [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-155">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fcfd1-156">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-156">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\CustomDemux`  
  
## <a name="see-also"></a><span data-ttu-id="fcfd1-157">См. также</span><span class="sxs-lookup"><span data-stu-id="fcfd1-157">See Also</span></span>  
 [<span data-ttu-id="fcfd1-158">Очереди в WCF</span><span class="sxs-lookup"><span data-stu-id="fcfd1-158">Queuing in WCF</span></span>](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [<span data-ttu-id="fcfd1-159">Очереди сообщений</span><span class="sxs-lookup"><span data-stu-id="fcfd1-159">Message Queuing</span></span>](http://go.microsoft.com/fwlink/?LinkId=95143)
