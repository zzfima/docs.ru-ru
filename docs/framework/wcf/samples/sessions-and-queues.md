---
title: Сеансы и очереди
ms.date: 03/30/2017
ms.assetid: 47d7c5c2-1e6f-4619-8003-a0ff67dcfbd6
ms.openlocfilehash: 6ab2b46325207a06f7ab12a7420765d1d8ae90e4
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73417064"
---
# <a name="sessions-and-queues"></a><span data-ttu-id="12ede-102">Сеансы и очереди</span><span class="sxs-lookup"><span data-stu-id="12ede-102">Sessions and Queues</span></span>
<span data-ttu-id="12ede-103">В этом образце показано, как отправлять и принимать набор связанных сообщений при взаимодействии с использованием очередей с помощью транспорта очереди сообщений (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="12ede-103">This sample demonstrates how to send and receive a set of related messages in queued communication over the Message Queuing (MSMQ) transport.</span></span> <span data-ttu-id="12ede-104">В этом примере используется привязка `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="12ede-104">This sample uses the `netMsmqBinding` binding.</span></span> <span data-ttu-id="12ede-105">Служба представляет собой резидентное консольное приложение, позволяющее наблюдать за получением службой сообщений из очереди.</span><span class="sxs-lookup"><span data-stu-id="12ede-105">The service is a self-hosted console application to enable you to observe the service receiving queued messages.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="12ede-106">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="12ede-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="12ede-107">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="12ede-107">The samples may already be installed on your machine.</span></span> <span data-ttu-id="12ede-108">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="12ede-108">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="12ede-109">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="12ede-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="12ede-110">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="12ede-110">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Session`  
  
 <span data-ttu-id="12ede-111">При использовании очередей клиент взаимодействует со службой посредством очереди.</span><span class="sxs-lookup"><span data-stu-id="12ede-111">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="12ede-112">Конкретно, клиент отправляет сообщения в очередь.</span><span class="sxs-lookup"><span data-stu-id="12ede-112">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="12ede-113">Служба получает сообщения из очереди.</span><span class="sxs-lookup"><span data-stu-id="12ede-113">The service receives messages from the queue.</span></span> <span data-ttu-id="12ede-114">Поэтому клиенту и службе не обязательно выполняться одновременно, чтобы взаимодействовать посредством очереди.</span><span class="sxs-lookup"><span data-stu-id="12ede-114">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>  
  
 <span data-ttu-id="12ede-115">Иногда клиент отправляет набор сообщений, связанных между собой в группу.</span><span class="sxs-lookup"><span data-stu-id="12ede-115">Sometimes, a client sends a set of messages that are related to each other in a group.</span></span> <span data-ttu-id="12ede-116">Если сообщения должны обрабатываться совместно или в определенном порядке, с помощью очереди можно сгруппировать их вместе для обработки одним принимающим приложением.</span><span class="sxs-lookup"><span data-stu-id="12ede-116">When messages must be processed together or in a specified order, a queue can be used to group them together, for processing by a single receiving application.</span></span> <span data-ttu-id="12ede-117">Это особенно важно, если имеется несколько принимающих приложений на группе серверов и необходимо обеспечить, чтобы группа сообщений обрабатывалась одним и тем же принимающим приложением.</span><span class="sxs-lookup"><span data-stu-id="12ede-117">This is particularly important when there are several receiving applications on a group of servers and it is necessary to ensure that a group of messages is processed by the same receiving application.</span></span> <span data-ttu-id="12ede-118">В качестве механизма отправки и приема связанного набора сообщений, которые должны обрабатываться одновременно, используются сеансы с очередями.</span><span class="sxs-lookup"><span data-stu-id="12ede-118">Queued sessions are a mechanism used to send and receive a related set of messages that must get processed all at once.</span></span> <span data-ttu-id="12ede-119">Чтобы сеанс с очередями демонстрировал такое поведение, требуется транзакция.</span><span class="sxs-lookup"><span data-stu-id="12ede-119">Queued sessions require a transaction to exhibit this pattern.</span></span>  
  
 <span data-ttu-id="12ede-120">В этом образце клиент отправляет ряд сообщений в службу как часть сеанса в рамках одной транзакции.</span><span class="sxs-lookup"><span data-stu-id="12ede-120">In the sample, the client sends a number of messages to the service as part of a session within the scope of a single transaction.</span></span>  
  
 <span data-ttu-id="12ede-121">Контракт службы `IOrderTaker` определяет одностороннюю службу, которую можно использовать с очередями.</span><span class="sxs-lookup"><span data-stu-id="12ede-121">The service contract is `IOrderTaker`, which defines a one-way service that is suitable for use with queues.</span></span> <span data-ttu-id="12ede-122">Класс <xref:System.ServiceModel.SessionMode>, использованный в контракте, показанном в следующем образце кода, означает, что сообщения являются частью сеанса.</span><span class="sxs-lookup"><span data-stu-id="12ede-122">The <xref:System.ServiceModel.SessionMode> used in the contract shown in the following sample code indicates that the messages are part of the session.</span></span>  

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples", SessionMode=SessionMode.Required)]  
public interface IOrderTaker  
{  
    [OperationContract(IsOneWay = true)]  
    void OpenPurchaseOrder(string customerId);  
  
    [OperationContract(IsOneWay = true)]  
    void AddProductLineItem(string productId, int quantity);  
  
    [OperationContract(IsOneWay = true)]  
    void EndPurchaseOrder();  
}  
```

 <span data-ttu-id="12ede-123">Служба определяет операции службы таким образом, что первая операция зачисляется в транзакцию, но не завершает транзакцию автоматически.</span><span class="sxs-lookup"><span data-stu-id="12ede-123">The service defines service operations in such a way that the first operation enlists in a transaction but does not automatically complete the transaction.</span></span> <span data-ttu-id="12ede-124">Последующие операции также зачисляются в эту же транзакцию, но не производят ее автоматического завершения.</span><span class="sxs-lookup"><span data-stu-id="12ede-124">Subsequent operations also enlist in the same transaction but do not automatically complete.</span></span> <span data-ttu-id="12ede-125">Последняя операция в сеансе автоматически завершает транзакцию.</span><span class="sxs-lookup"><span data-stu-id="12ede-125">The last operation in the session automatically completes the transaction.</span></span> <span data-ttu-id="12ede-126">Таким образом, одна и та же транзакция используется для вызова нескольких операций в контракте службы.</span><span class="sxs-lookup"><span data-stu-id="12ede-126">Thus, the same transaction is used for several operation invocations in the service contract.</span></span> <span data-ttu-id="12ede-127">Если любая из операций вызывает исключение, производится откат транзакции и сеанс возвращается в очередь.</span><span class="sxs-lookup"><span data-stu-id="12ede-127">If any of the operations throw an exception, then the transaction rolls back and the session is put back into the queue.</span></span> <span data-ttu-id="12ede-128">После успешного завершения последней операции производится фиксация транзакции.</span><span class="sxs-lookup"><span data-stu-id="12ede-128">Upon successful completion of the last operation, the transaction is committed.</span></span> <span data-ttu-id="12ede-129">В службе значение `PerSession` параметра <xref:System.ServiceModel.InstanceContextMode> используется для того, чтобы все сообщения в сеансе получались одним экземпляром службы.</span><span class="sxs-lookup"><span data-stu-id="12ede-129">The service uses `PerSession` as the <xref:System.ServiceModel.InstanceContextMode> to receive all messages in a session on the same instance of the service.</span></span>  

```csharp
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
public class OrderTakerService : IOrderTaker  
{  
    PurchaseOrder po;  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                                 TransactionAutoComplete = false)]  
    public void OpenPurchaseOrder(string customerId)  
    {  
        Console.WriteLine("Creating purchase order");  
        po = new PurchaseOrder(customerId);  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                                  TransactionAutoComplete = false)]  
    public void AddProductLineItem(string productId, int quantity)  
    {  
        po.AddProductLineItem(productId, quantity);  
        Console.WriteLine("Product " + productId + " quantity " +   
                            quantity + " added to purchase order");  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                                  TransactionAutoComplete = true)]  
    public void EndPurchaseOrder()  
    {  
       Console.WriteLine("Purchase Order Completed");  
       Console.WriteLine();  
       Console.WriteLine(po.ToString());  
    }  
}  
```

 <span data-ttu-id="12ede-130">Служба является резидентной.</span><span class="sxs-lookup"><span data-stu-id="12ede-130">The service is self hosted.</span></span> <span data-ttu-id="12ede-131">При работе с транспортом MSMQ используемую очередь следует создавать заранее.</span><span class="sxs-lookup"><span data-stu-id="12ede-131">When using the MSMQ transport, the queue used must be created in advance.</span></span> <span data-ttu-id="12ede-132">Это можно сделать вручную или с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="12ede-132">This can be done manually or through code.</span></span> <span data-ttu-id="12ede-133">В данном образце служба содержит код <xref:System.Messaging> для проверки наличия очереди и ее создания, если требуется.</span><span class="sxs-lookup"><span data-stu-id="12ede-133">In this sample, the service contains <xref:System.Messaging> code to check for the existence of the queue and creates it, if necessary.</span></span> <span data-ttu-id="12ede-134">Имя очереди считывается из файла конфигурации с помощью класса <xref:System.Configuration.ConfigurationManager.AppSettings%2A>.</span><span class="sxs-lookup"><span data-stu-id="12ede-134">The queue name is read from the configuration file using the <xref:System.Configuration.ConfigurationManager.AppSettings%2A> class.</span></span>  

```csharp
// Host the service within this EXE console application.  
public static void Main()  
{  
    // Get MSMQ queue name from app settings in configuration.  
    string queueName = ConfigurationManager.AppSettings["queueName"];  
  
    // Create the transacted MSMQ queue if necessary.  
    if (!MessageQueue.Exists(queueName))  
        MessageQueue.Create(queueName, true);  
  
    // Create a ServiceHost for the OrderTakerService type.  
    using (ServiceHost serviceHost = new ServiceHost(typeof(OrderTakerService)))  
    {  
        // Open the ServiceHost to create listeners and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.WriteLine();  
        Console.ReadLine();  
  
        // Close the ServiceHost to shutdown the service.  
        serviceHost.Close();   
    }  
}  
```

 <span data-ttu-id="12ede-135">Имя очереди MSMQ задается в разделе appSettings файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="12ede-135">The MSMQ queue name is specified in an appSettings section of the configuration file.</span></span> <span data-ttu-id="12ede-136">Конечная точка для службы задается в разделе system.serviceModel файла конфигурации и определяет привязку `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="12ede-136">The endpoint for the service is defined in the system.serviceModel section of the configuration file and specifies the `netMsmqBinding` binding.</span></span>  
  
```xml  
<appSettings>  
  <!-- Use appSetting to configure MSMQ queue name. -->  
  <add key="queueName" value=".\private$\ServiceModelSamplesSession" />  
</appSettings>  
  
<system.serviceModel>  
  <services>  
    <service name="Microsoft.ServiceModel.Samples.OrderTakerService"  
        behaviorConfiguration="CalculatorServiceBehavior">  
      ...  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesSession"  
                binding="netMsmqBinding"  
                contract="Microsoft.ServiceModel.Samples.IOrderTaker" />  
      ...  
    </service>  
  </services>  
  ...  
<system.serviceModel>  
```  
  
 <span data-ttu-id="12ede-137">Клиент создает область транзакции.</span><span class="sxs-lookup"><span data-stu-id="12ede-137">The client creates a transaction scope.</span></span> <span data-ttu-id="12ede-138">Все сообщения в сеансе отправляются в очередь в области транзакции, поэтому она обрабатывается как единый модуль, в котором все сообщения завершаются успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="12ede-138">All messages in the session are sent to the queue within the transaction scope, causing it to be treated as an atomic unit where all messages succeed or fail.</span></span> <span data-ttu-id="12ede-139">Транзакция фиксируется путем вызова метода <xref:System.Transactions.TransactionScope.Complete%2A>.</span><span class="sxs-lookup"><span data-stu-id="12ede-139">The transaction is committed by calling <xref:System.Transactions.TransactionScope.Complete%2A>.</span></span>  

```csharp
//Create a transaction scope.  
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
{  
    // Create a client with given client endpoint configuration.  
    OrderTakerClient client = new OrderTakerClient("OrderTakerEndpoint");  
    // Open a purchase order.  
    client.OpenPurchaseOrder("somecustomer.com");  
    Console.WriteLine("Purchase Order created");  
  
    // Add product line items.  
    Console.WriteLine("Adding 10 quantities of blue widget");  
    client.AddProductLineItem("Blue Widget", 10);  
  
    Console.WriteLine("Adding 23 quantities of red widget");  
    client.AddProductLineItem("Red Widget", 23);  
  
    // Close the purchase order.  
    Console.WriteLine("Closing the purchase order");  
    client.EndPurchaseOrder();  
  
    //Closing the client gracefully closes the connection and cleans up resources.  
    client.Close();                  
  
    // Complete the transaction.  
    scope.Complete();  
}  
```

> [!NOTE]
> <span data-ttu-id="12ede-140">Можно использовать только одну транзакцию для всех сообщений в сеансе, и все сообщения в сеансе должны быть отправлены до фиксации транзакции.</span><span class="sxs-lookup"><span data-stu-id="12ede-140">You can use only a single transaction for all messages in the session and all messages in the session must be sent before committing the transaction.</span></span> <span data-ttu-id="12ede-141">При закрытии клиента сеанс также закрывается.</span><span class="sxs-lookup"><span data-stu-id="12ede-141">Closing the client closes the session.</span></span> <span data-ttu-id="12ede-142">Поэтому для отправки всех сообщений в сеансе в очередь клиент должен быть закрыт до завершения транзакции.</span><span class="sxs-lookup"><span data-stu-id="12ede-142">Therefore, the client has to be closed before the transaction is completed to send all messages in the session to the queue.</span></span>  
  
 <span data-ttu-id="12ede-143">При выполнении образца действия клиента и службы отображаются в окнах консоли как службы, так и клиента.</span><span class="sxs-lookup"><span data-stu-id="12ede-143">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="12ede-144">Можно видеть, как служба получает сообщения от клиента.</span><span class="sxs-lookup"><span data-stu-id="12ede-144">You can see the service receive messages from the client.</span></span> <span data-ttu-id="12ede-145">Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент.</span><span class="sxs-lookup"><span data-stu-id="12ede-145">Press ENTER in each console window to shut down the service and client.</span></span> <span data-ttu-id="12ede-146">Обратите внимание, что поскольку используется очередь, клиенту и службе не обязательно быть запущенными и работать одновременно.</span><span class="sxs-lookup"><span data-stu-id="12ede-146">Note that because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="12ede-147">Можно запустить клиент, выключить его, а затем запустить службу, которая все равно получит сообщения клиента.</span><span class="sxs-lookup"><span data-stu-id="12ede-147">You can run the client, shut it down, and then start up the service and it still receives its messages.</span></span>  
  
 <span data-ttu-id="12ede-148">На клиенте.</span><span class="sxs-lookup"><span data-stu-id="12ede-148">On the client.</span></span>  
  
```console  
Purchase Order created  
Adding 10 quantities of blue widget  
Adding 23 quantities of red widget  
Closing the purchase order  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="12ede-149">В службе.</span><span class="sxs-lookup"><span data-stu-id="12ede-149">On the service.</span></span>  
  
```console  
The service is ready.  
Press <ENTER> to terminate service.  
  
Creating purchase order  
Product Blue Widget quantity 10 added to purchase order  
Product Red Widget quantity 23 added to purchase order  
Purchase Order Completed  
  
Purchase Order: 7c86fef0-2306-4c51-80e6-bcabcc1a6e5e  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 10 of Blue Widget @unit price: $2985  
                Order LineItem: 23 of Red Widget @unit price: $156  
        Total cost of this order: $33438  
        Order status: Pending  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="12ede-150">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="12ede-150">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="12ede-151">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="12ede-151">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="12ede-152">Чтобы создать выпуск C#решения C++, или Visual Basic .NET, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="12ede-152">To build the C#, C++, or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="12ede-153">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="12ede-153">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
 <span data-ttu-id="12ede-154">По умолчанию с привязкой <xref:System.ServiceModel.NetMsmqBinding> безопасность транспорта включена.</span><span class="sxs-lookup"><span data-stu-id="12ede-154">By default with the <xref:System.ServiceModel.NetMsmqBinding>, transport security is enabled.</span></span> <span data-ttu-id="12ede-155">Есть два соответствующих свойства: имя безопасности транспорта MSMQ, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> и <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.` по умолчанию, для режима проверки подлинности устанавливается значение `Windows`, а для уровня защиты — значение `Sign`.</span><span class="sxs-lookup"><span data-stu-id="12ede-155">There are two relevant properties for MSMQ transport security namely, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> and <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.` By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="12ede-156">Чтобы служба MSMQ обеспечивала возможности проверки подлинности и подписывания, она должна входить в домен, а также должна быть установлена возможность интеграции MSMQ со службой каталогов Active Directory.</span><span class="sxs-lookup"><span data-stu-id="12ede-156">For MSMQ to provide the authentication and signing feature, it must be part of a domain and the active directory integration option for MSMQ must be installed.</span></span> <span data-ttu-id="12ede-157">Если запустить данный образец на компьютере, который не удовлетворяет этому условию, возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="12ede-157">If you run this sample on a computer that does not satisfy these criteria you receive an error.</span></span>  
  
### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a><span data-ttu-id="12ede-158">Запуск образца на компьютере, входящем в рабочую группу, или без интеграции с Active Directory</span><span class="sxs-lookup"><span data-stu-id="12ede-158">To run the sample on a computer joined to a workgroup or without active directory integration</span></span>  
  
1. <span data-ttu-id="12ede-159">Если компьютер не входит в домен или не установлена интеграция с Active Directory, отключите безопасность транспорта, задав для режима проверки подлинности и уровня защиты значение `None`, как показано в следующем образце конфигурации.</span><span class="sxs-lookup"><span data-stu-id="12ede-159">If your computer is not part of a domain or does not have active directory integration installed, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration.</span></span>  
  
    ```xml  
    <system.serviceModel>  
      <services>  
        <service name="Microsoft.ServiceModel.Samples.OrderTakerService"  
                 behaviorConfiguration="OrderTakerServiceBehavior">  
          <host>  
            <baseAddresses>  
              <add baseAddress=  
             "http://localhost:8000/ServiceModelSamples/service"/>  
            </baseAddresses>  
          </host>  
          <!-- Define NetMsmqEndpoint -->  
          <endpoint  
              address=  
            "net.msmq://localhost/private/ServiceModelSamplesSession"  
              binding="netMsmqBinding"  
              bindingConfiguration="Binding1"  
           contract="Microsoft.ServiceModel.Samples.IOrderTaker" />  
          <!-- The mex endpoint is exposed at-->      
          <!--http://localhost:8000/ServiceModelSamples/service/mex. -->  
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
            <behavior name="OrderTakerServiceBehavior">  
              <serviceMetadata httpGetEnabled="True"/>  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
  
      </system.serviceModel>  
    ```  
  
2. <span data-ttu-id="12ede-160">Перед выполнением примера убедитесь, что изменена конфигурация как сервера, так и клиента.</span><span class="sxs-lookup"><span data-stu-id="12ede-160">Ensure that you change the configuration on both the server and the client before you run the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="12ede-161">Установка для режима безопасности значения `None` равносильна установке для <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> и безопасности `Message` значения `None`.</span><span class="sxs-lookup"><span data-stu-id="12ede-161">Setting security mode to `None` is equivalent to setting <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>, and `Message` security to `None`.</span></span>  
