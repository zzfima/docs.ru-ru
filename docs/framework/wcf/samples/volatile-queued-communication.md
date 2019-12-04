---
title: Неустойчивое взаимодействие с использованием очереди
ms.date: 03/30/2017
ms.assetid: 0d012f64-51c7-41d0-8e18-c756f658ee3d
ms.openlocfilehash: 8ed10262d319664d404e6beb630593cb93748a7d
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715279"
---
# <a name="volatile-queued-communication"></a><span data-ttu-id="c9b15-102">Неустойчивое взаимодействие с использованием очереди</span><span class="sxs-lookup"><span data-stu-id="c9b15-102">Volatile Queued Communication</span></span>

<span data-ttu-id="c9b15-103">В этом образце показано, как осуществлять неустойчивое взаимодействие с использованием очередей с помощью транспорта очереди сообщений (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="c9b15-103">This sample demonstrates how to perform volatile queued communication over the Message Queuing (MSMQ) transport.</span></span> <span data-ttu-id="c9b15-104">В этом образце используется привязка <xref:System.ServiceModel.NetMsmqBinding>.</span><span class="sxs-lookup"><span data-stu-id="c9b15-104">This sample uses <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="c9b15-105">В данном случае служба представляет собой резидентное консольное приложение, позволяющее наблюдать за тем, как служба получает сообщения из очереди.</span><span class="sxs-lookup"><span data-stu-id="c9b15-105">The service in this case is a self-hosted console application to enable you to observe the service receiving queued messages.</span></span>

> [!NOTE]
> <span data-ttu-id="c9b15-106">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="c9b15-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="c9b15-107">При использовании очередей клиент взаимодействует со службой посредством очереди.</span><span class="sxs-lookup"><span data-stu-id="c9b15-107">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="c9b15-108">Конкретно, клиент отправляет сообщения в очередь.</span><span class="sxs-lookup"><span data-stu-id="c9b15-108">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="c9b15-109">Служба получает сообщения из очереди.</span><span class="sxs-lookup"><span data-stu-id="c9b15-109">The service receives messages from the queue.</span></span> <span data-ttu-id="c9b15-110">Поэтому клиенту и службе не обязательно выполняться одновременно, чтобы взаимодействовать посредством очереди.</span><span class="sxs-lookup"><span data-stu-id="c9b15-110">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>

<span data-ttu-id="c9b15-111">При отправке сообщения без подтверждения MSMQ лишь делает все возможно для отправки сообщения в отличие от подтверждений "ровно один раз", при которых MSMQ проверяет, что сообщение было доставлено, или, если доставить его не удалось, уведомляет об этом.</span><span class="sxs-lookup"><span data-stu-id="c9b15-111">When you send a message with no assurances, MSMQ only makes a best effort to deliver the message, unlike with Exactly Once assurances where MSMQ ensures that the message gets delivered or, if it cannot be delivered, lets you know that the message cannot be delivered.</span></span>

<span data-ttu-id="c9b15-112">В некоторых сценариях неустойчивое сообщение может быть отправлено через очередь без подтверждения, если своевременность доставки важнее, чем возможная потеря сообщения.</span><span class="sxs-lookup"><span data-stu-id="c9b15-112">In certain scenarios, you may want to send a volatile message with no assurances over a queue, when timely delivery is more important than losing messages.</span></span> <span data-ttu-id="c9b15-113">Неустойчивые сообщения не сохраняются в случае сбоя диспетчера очереди.</span><span class="sxs-lookup"><span data-stu-id="c9b15-113">Volatile messages do not survive queue manager crashes.</span></span> <span data-ttu-id="c9b15-114">Поэтому при сбое диспетчера очереди нетранзакционная очередь, в которой содержатся неустойчивые сообщения, сохраняется, но сами сообщения исчезают, поскольку они не хранятся на диске.</span><span class="sxs-lookup"><span data-stu-id="c9b15-114">Therefore if the queue manager crashes, the non-transactional queue used to store volatile messages survives but the messages themselves do not because the messages are not stored on the disk.</span></span>

> [!NOTE]
> <span data-ttu-id="c9b15-115">Неустойчивые сообщения невозможно отправлять с помощью MSMQ без подтверждений в пределах области транзакции.</span><span class="sxs-lookup"><span data-stu-id="c9b15-115">You cannot send volatile messages with no assurances within the scope of a transaction using MSMQ.</span></span> <span data-ttu-id="c9b15-116">Кроме того, для отправки неустойчивых сообщений необходимо создавать нетранзакционные очереди.</span><span class="sxs-lookup"><span data-stu-id="c9b15-116">You also must create a non-transactional queue to send volatile messages.</span></span>

<span data-ttu-id="c9b15-117">В этом образце используется контракт службы `IStockTicker`, определяющий односторонние службы, которые лучше всего подходят для работы с очередями.</span><span class="sxs-lookup"><span data-stu-id="c9b15-117">The service contract in this sample is `IStockTicker` that defines one-way services that are best suited for use with queuing.</span></span>

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
public interface IStockTicker
{
    [OperationContract(IsOneWay = true)]
    void StockTick(string symbol, float price);
}
```

<span data-ttu-id="c9b15-118">Операция службы отображает биржевой символ и цену, как показано в следующем образце кода:</span><span class="sxs-lookup"><span data-stu-id="c9b15-118">The service operation displays the stock ticker symbol and price, as shown in the following sample code:</span></span>

```csharp
public class StockTickerService : IStockTicker
{
    public void StockTick(string symbol, float price)
    {
        Console.WriteLine("Stock Tick {0}:{1} ", symbol, price);
     }
     …
}
```

<span data-ttu-id="c9b15-119">Служба является резидентной.</span><span class="sxs-lookup"><span data-stu-id="c9b15-119">The service is self hosted.</span></span> <span data-ttu-id="c9b15-120">При работе с транспортом MSMQ используемую очередь следует создавать заранее.</span><span class="sxs-lookup"><span data-stu-id="c9b15-120">When using the MSMQ transport, the queue used must be created in advance.</span></span> <span data-ttu-id="c9b15-121">Это можно сделать вручную или с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="c9b15-121">This can be done manually or through code.</span></span> <span data-ttu-id="c9b15-122">В данном образце служба содержит код для проверки наличия очереди и ее создания, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="c9b15-122">In this sample, the service contains code to check for the existence of the queue and create it if required.</span></span> <span data-ttu-id="c9b15-123">Имя очереди считывается из файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c9b15-123">The queue name is read from the configuration file.</span></span> <span data-ttu-id="c9b15-124">Базовый адрес используется [средством служебной программы метаданных ServiceModel (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания учетной записи-посредника для службы.</span><span class="sxs-lookup"><span data-stu-id="c9b15-124">The base address is used by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy for the service.</span></span>

```csharp
// Host the service within this EXE console application.
public static void Main()
{
    // Get MSMQ queue name from app settings in configuration.
    string queueName = ConfigurationManager.AppSettings["queueName"];

    // Create the transacted MSMQ queue if necessary.
    if (!MessageQueue.Exists(queueName))
        MessageQueue.Create(queueName);

    // Create a ServiceHost for the StockTickerService type.
    using (ServiceHost serviceHost = new ServiceHost(typeof(StockTickerService)))
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

<span data-ttu-id="c9b15-125">Имя очереди MSMQ задается в разделе appSettings файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c9b15-125">The MSMQ queue name is specified in the appSettings section of the configuration file.</span></span> <span data-ttu-id="c9b15-126">Конечная точка для службы задается в разделе system.serviceModel файла конфигурации и определяет привязку `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="c9b15-126">The endpoint for the service is defined in the system.serviceModel section of the configuration file and specifies the `netMsmqBinding` binding.</span></span>

> [!NOTE]
> <span data-ttu-id="c9b15-127">В имени очереди для определения локального компьютера используется точка (.), а при создании очереди с помощью <xref:System.Messaging> в пути в качестве разделителей используются символы обратной косой черты.</span><span class="sxs-lookup"><span data-stu-id="c9b15-127">The queue name uses a dot (.) for the local machine and backslash separators in its path when creating a queue using <xref:System.Messaging>.</span></span> <span data-ttu-id="c9b15-128">Адрес конечной точки Windows Communication Foundation (WCF) указывает схему "net. msmq:", использует "localhost" для локального компьютера и косую черту в пути.</span><span class="sxs-lookup"><span data-stu-id="c9b15-128">The Windows Communication Foundation (WCF) endpoint address specifies a net.msmq: scheme, uses "localhost" for the local machine and forward slashes in its path.</span></span>

<span data-ttu-id="c9b15-129">Подтверждения устойчивости или неустойчивости сообщений также задаются в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c9b15-129">The assurances and durability or volatility of messages are also specified in the configuration.</span></span>

```xml
<appSettings>
  <!-- use appSetting to configure MSMQ queue name -->
  <add key="queueName" value=".\private$\ServiceModelSamplesVolatile" />
</appSettings>

<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.StockTickerService"
             behaviorConfiguration="CalculatorServiceBehavior">
    ...
      <!-- Define NetMsmqEndpoint -->
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesVolatile"
                binding="netMsmqBinding"
                bindingConfiguration="volatileBinding"
                contract="Microsoft.ServiceModel.Samples.IStockTicker" />
    ...
    </service>
  </services>

  <bindings>
    <netMsmqBinding>
      <binding name="volatileBinding"
             durable="false"
           exactlyOnce="false"/>
    </netMsmqBinding>
  </bindings>
  ...
</system.serviceModel>
```

<span data-ttu-id="c9b15-130">Поскольку в этом образце поддерживающие очередь сообщения отправляются с помощью нетранзакционной очереди, передавать через эту очередь сообщения транзакций невозможно.</span><span class="sxs-lookup"><span data-stu-id="c9b15-130">Because the sample sends queued messages by using a non-transactional queue, transacted messages cannot be sent to the queue.</span></span>

```csharp
// Create a client.
Random r = new Random(137);

StockTickerClient client = new StockTickerClient();

float price = 43.23F;
for (int i = 0; i < 10; i++)
{
    float increment = 0.01f * (r.Next(10));
    client.StockTick("zzz" + i, price + increment);
}

//Closing the client gracefully cleans up resources.
client.Close();
```

<span data-ttu-id="c9b15-131">При выполнении образца действия клиента и службы отображаются в окнах консоли как службы, так и клиента.</span><span class="sxs-lookup"><span data-stu-id="c9b15-131">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="c9b15-132">Можно видеть, как служба получает сообщения от клиента.</span><span class="sxs-lookup"><span data-stu-id="c9b15-132">You can see the service receive messages from the client.</span></span> <span data-ttu-id="c9b15-133">Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент.</span><span class="sxs-lookup"><span data-stu-id="c9b15-133">Press ENTER in each console window to shut down the service and client.</span></span> <span data-ttu-id="c9b15-134">Обратите внимание, что поскольку используется очередь, клиенту и службе не обязательно быть запущенными и работать одновременно.</span><span class="sxs-lookup"><span data-stu-id="c9b15-134">Note that because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="c9b15-135">Можно запустить клиент, выключить его, а затем запустить службу, которая все равно получит сообщения клиента.</span><span class="sxs-lookup"><span data-stu-id="c9b15-135">You can run the client, shut it down, and then start up the service and it still receives its messages.</span></span>

```console
The service is ready.
Press <ENTER> to terminate service.

Stock Tick zzz0:43.25
Stock Tick zzz1:43.23
Stock Tick zzz2:43.28
Stock Tick zzz3:43.3
Stock Tick zzz4:43.23
Stock Tick zzz5:43.25
Stock Tick zzz6:43.25
Stock Tick zzz7:43.24
Stock Tick zzz8:43.32
Stock Tick zzz9:43.3
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c9b15-136">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="c9b15-136">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="c9b15-137">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c9b15-137">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="c9b15-138">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c9b15-138">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="c9b15-139">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c9b15-139">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

<span data-ttu-id="c9b15-140">По умолчанию с привязкой <xref:System.ServiceModel.NetMsmqBinding> безопасность транспорта включена.</span><span class="sxs-lookup"><span data-stu-id="c9b15-140">By default with the <xref:System.ServiceModel.NetMsmqBinding>, transport security is enabled.</span></span> <span data-ttu-id="c9b15-141">Существует два соответствующих свойства безопасности транспорта MSMQ, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> и <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.` по умолчанию устанавливается режим проверки подлинности `Windows`, а для уровня защиты устанавливается значение `Sign`.</span><span class="sxs-lookup"><span data-stu-id="c9b15-141">There are two pertinent properties for MSMQ transport security, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> and <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.` By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="c9b15-142">Чтобы служба MSMQ обеспечивала возможности проверки подлинности и подписывания, она должна входить в домен, а также должна быть установлена возможность интеграции MSMQ со службой каталогов Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c9b15-142">For MSMQ to provide the authentication and signing feature, it must be part of a domain and the active directory integration option for MSMQ must be installed.</span></span> <span data-ttu-id="c9b15-143">Если запустить данный образец на компьютере, который не удовлетворяет этому условию, возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="c9b15-143">If you run this sample on a computer that does not satisfy these criteria you receive an error.</span></span>

### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a><span data-ttu-id="c9b15-144">Запуск образца на компьютере, входящем в рабочую группу, или без интеграции с Active Directory</span><span class="sxs-lookup"><span data-stu-id="c9b15-144">To run the sample on a computer joined to a workgroup or without active directory integration</span></span>

1. <span data-ttu-id="c9b15-145">Если компьютер не входит в домен или не установлена интеграция с Active Directory, отключите безопасность транспорта, задав для режима проверки подлинности и уровня защиты значения `None`, как показано в следующем образце кода конфигурации:</span><span class="sxs-lookup"><span data-stu-id="c9b15-145">If your computer is not part of a domain or does not have active directory integration installed, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration code:</span></span>

    ```xml
    <system.serviceModel>
        <services>
          <service name="Microsoft.ServiceModel.Samples.StockTickerService"
                   behaviorConfiguration="StockTickerServiceBehavior">
            <host>
              <baseAddresses>
                <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>
              </baseAddresses>
            </host>

            <!-- Define NetMsmqEndpoint -->
            <endpoint address="net.msmq://localhost/private/ServiceModelSamplesVolatile"
                      binding="netMsmqBinding"
                      bindingConfiguration="volatileBinding"
                      contract="Microsoft.ServiceModel.Samples.IStockTicker" />
            <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
            <endpoint address="mex"
                      binding="mexHttpBinding"
                      contract="IMetadataExchange" />

          </service>
        </services>

        <bindings>
          <netMsmqBinding>
            <binding name="volatileBinding"
                  durable="false"
                  exactlyOnce="false">
              <security mode="None" />
            </binding>
          </netMsmqBinding>
        </bindings>

        <behaviors>
          <serviceBehaviors>
            <behavior name="StockTickerServiceBehavior">
              <serviceMetadata httpGetEnabled="True"/>
            </behavior>
          </serviceBehaviors>
        </behaviors>

      </system.serviceModel>
    ```

2. <span data-ttu-id="c9b15-146">Перед выполнением примера убедитесь, что изменена конфигурация как сервера, так и клиента.</span><span class="sxs-lookup"><span data-stu-id="c9b15-146">Ensure that you change the configuration on both the server and the client before you run the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c9b15-147">Задание для `security mode` значения `None` эквивалентно заданию для параметров безопасности <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> и `Message` значения `None`.</span><span class="sxs-lookup"><span data-stu-id="c9b15-147">Setting `security mode` to `None` is equivalent to setting <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>, and `Message` security to `None`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9b15-148">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c9b15-148">The samples may already be installed on your computer.</span></span> <span data-ttu-id="c9b15-149">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="c9b15-149">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="c9b15-150">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="c9b15-150">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c9b15-151">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="c9b15-151">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Volatile`
