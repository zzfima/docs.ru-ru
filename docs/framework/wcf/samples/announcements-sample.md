---
title: Образец замечаний
ms.date: 03/30/2017
ms.assetid: 954a75e4-9a97-41d6-94fc-43765d4205a9
ms.openlocfilehash: c3824fb0dc7ab4169c309d1a5154127d6bc3b78f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746999"
---
# <a name="announcements-sample"></a><span data-ttu-id="ab0f3-102">Образец замечаний</span><span class="sxs-lookup"><span data-stu-id="ab0f3-102">Announcements Sample</span></span>

<span data-ttu-id="ab0f3-103">Данный образец показывает, как использовать функциональность объявлений возможности обнаружения.</span><span class="sxs-lookup"><span data-stu-id="ab0f3-103">This sample shows how to use the Announcement functionality of the Discovery feature.</span></span> <span data-ttu-id="ab0f3-104">Объявления позволяют службам отправлять сообщения объявления, содержащие метаданные службы.</span><span class="sxs-lookup"><span data-stu-id="ab0f3-104">Announcements allow services to send out announcement messages that contain metadata about the service.</span></span> <span data-ttu-id="ab0f3-105">По умолчанию отправляется объявление о входе в сеть при запуске службы и объявление о выходе из сети при отключении службы.</span><span class="sxs-lookup"><span data-stu-id="ab0f3-105">By default a hello announcement is sent when the service starts up and a bye announcement is sent when the service shuts down.</span></span> <span data-ttu-id="ab0f3-106">Эти объявления могут быть многоадресными или отправляться от точки к точке.</span><span class="sxs-lookup"><span data-stu-id="ab0f3-106">These announcements can be multicast or they can be sent point-to-point.</span></span> <span data-ttu-id="ab0f3-107">Этот образец состоит из двух проектов: служба и клиент.</span><span class="sxs-lookup"><span data-stu-id="ab0f3-107">This sample consists of two projects service and client.</span></span>

## <a name="service"></a><span data-ttu-id="ab0f3-108">Service</span><span class="sxs-lookup"><span data-stu-id="ab0f3-108">Service</span></span>

<span data-ttu-id="ab0f3-109">Данный проект содержит саморазмещаемую службу калькулятора.</span><span class="sxs-lookup"><span data-stu-id="ab0f3-109">This project contains a self-hosted calculator service.</span></span> <span data-ttu-id="ab0f3-110">В методе `Main` создается узел службы, к которому добавляется конечная точка службы.</span><span class="sxs-lookup"><span data-stu-id="ab0f3-110">In the `Main` method, a service host is created and a service endpoint is added to it.</span></span> <span data-ttu-id="ab0f3-111">Далее создается поведение <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.</span><span class="sxs-lookup"><span data-stu-id="ab0f3-111">Next, a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> is created.</span></span> <span data-ttu-id="ab0f3-112">Чтобы включить объявления, к поведению <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> должна быть добавлена конечная точка объявлений.</span><span class="sxs-lookup"><span data-stu-id="ab0f3-112">To enable announcements, an announcement endpoint must be added to the <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.</span></span> <span data-ttu-id="ab0f3-113">В случае стандартной конечной точки в качестве конечной точки объявления добавляется многоадресная рассылка UDP.</span><span class="sxs-lookup"><span data-stu-id="ab0f3-113">In this case a standard endpoint, using UDP multicast is added as the announcement endpoint.</span></span> <span data-ttu-id="ab0f3-114">При этом объявления рассылаются через общеизвестный адрес UDP.</span><span class="sxs-lookup"><span data-stu-id="ab0f3-114">This broadcasts the announcements over a well-known UDP address.</span></span>

```csharp
Uri baseAddress = new Uri("http://localhost:8000/" + Guid.NewGuid().ToString());

// Create a ServiceHost for the CalculatorService type.
using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress))
{
     serviceHost.AddServiceEndpoint(typeof(ICalculatorService), new WSHttpBinding(), String.Empty);

     ServiceDiscoveryBehavior serviceDiscoveryBehavior = new ServiceDiscoveryBehavior();

     // Announce the availability of the service over UDP multicast
    serviceDiscoveryBehavior.AnnouncementEndpoints.Add(new UdpAnnouncementEndpoint());

    // Make the service discoverable over UDP multicast.
    serviceHost.Description.Behaviors.Add(serviceDiscoveryBehavior);
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());
    serviceHost.Open();
    // ...
}
```

## <a name="client"></a><span data-ttu-id="ab0f3-115">Клиент</span><span class="sxs-lookup"><span data-stu-id="ab0f3-115">Client</span></span>

<span data-ttu-id="ab0f3-116">Обратите внимание, что в данном проекте клиент содержит службу <xref:System.ServiceModel.Discovery.AnnouncementService>.</span><span class="sxs-lookup"><span data-stu-id="ab0f3-116">In this project, note that the client hosts an <xref:System.ServiceModel.Discovery.AnnouncementService>.</span></span> <span data-ttu-id="ab0f3-117">Кроме того, для событий зарегистрировано два делегата.</span><span class="sxs-lookup"><span data-stu-id="ab0f3-117">Furthermore, two delegates are registered with events.</span></span> <span data-ttu-id="ab0f3-118">Эти события определяют, что делает клиент при получении объявлений о входе и выходе из сети.</span><span class="sxs-lookup"><span data-stu-id="ab0f3-118">These events dictate what the client does when online and offline announcements are received.</span></span>

```csharp
// Create an AnnouncementService instance
AnnouncementService announcementService = new AnnouncementService();

// Subscribe the announcement events
announcementService.OnlineAnnouncementReceived += OnOnlineEvent;
announcementService.OfflineAnnouncementReceived += OnOfflineEvent;
```

<span data-ttu-id="ab0f3-119">Методы `OnOnlineEvent` и `OnOfflineEvent` обслуживают соответственно сообщения объявлений о входе и выходе из сети.</span><span class="sxs-lookup"><span data-stu-id="ab0f3-119">The `OnOnlineEvent` and `OnOfflineEvent` methods handle the hello and bye announcement messages respectively.</span></span>

```csharp
static void OnOnlineEvent(object sender, AnnouncementEventArgs e)
{
    Console.WriteLine();
    Console.WriteLine("Received an online announcement from {0}:", e.AnnouncementMessage.EndpointDiscoveryMetadata.Address);
PrintEndpointDiscoveryMetadata(e.AnnouncementMessage.EndpointDiscoveryMetadata);
}

static void OnOfflineEvent(object sender, AnnouncementEventArgs e)
{
    Console.WriteLine();
    Console.WriteLine("Received an offline announcement from {0}:", e.AnnouncementMessage.EndpointDiscoveryMetadata.Address);
            PrintEndpointDiscoveryMetadata(e.AnnouncementMessage.EndpointDiscoveryMetadata);
}
```

#### <a name="to-use-this-sample"></a><span data-ttu-id="ab0f3-120">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="ab0f3-120">To use this sample</span></span>

1. <span data-ttu-id="ab0f3-121">В этом образце используются конечные точки HTTP, и для работы этого образца необходимо добавить соответствующие списки управления доступом по URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="ab0f3-121">This sample uses HTTP endpoints and to run this sample, proper URL ACLs must be added.</span></span> <span data-ttu-id="ab0f3-122">Дополнительные сведения см. в разделе [Настройка HTTP и HTTPS](../feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="ab0f3-122">For more information, see [Configuring HTTP and HTTPS](../feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="ab0f3-123">Нужные списки управления доступом будут добавлены после выполнения следующей команды с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="ab0f3-123">Executing the following command at an elevated privilege should add the appropriate ACLs.</span></span> <span data-ttu-id="ab0f3-124">Если команда не работает, следует указать домен и имя пользователя в следующих аргументах.</span><span class="sxs-lookup"><span data-stu-id="ab0f3-124">You may want to substitute your Domain and Username for the following arguments if the command does not work as is.</span></span> `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`

2. <span data-ttu-id="ab0f3-125">Выполните сборку решения.</span><span class="sxs-lookup"><span data-stu-id="ab0f3-125">Build the solution.</span></span>

3. <span data-ttu-id="ab0f3-126">Запустите приложение client.exe.</span><span class="sxs-lookup"><span data-stu-id="ab0f3-126">Run the client.exe application.</span></span>

4. <span data-ttu-id="ab0f3-127">Запустите приложение service.exe.</span><span class="sxs-lookup"><span data-stu-id="ab0f3-127">Run the service.exe application.</span></span> <span data-ttu-id="ab0f3-128">Обратите внимание, что клиент получает объявление о входе в сеть.</span><span class="sxs-lookup"><span data-stu-id="ab0f3-128">Note the client receives an online announcement.</span></span>

5. <span data-ttu-id="ab0f3-129">Закройте приложение service.exe.</span><span class="sxs-lookup"><span data-stu-id="ab0f3-129">Close the service.exe application.</span></span> <span data-ttu-id="ab0f3-130">Обратите внимание, что клиент получает объявление о выходе из сети.</span><span class="sxs-lookup"><span data-stu-id="ab0f3-130">Note the client receives an offline announcement.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ab0f3-131">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="ab0f3-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ab0f3-132">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="ab0f3-132">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="ab0f3-133">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="ab0f3-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ab0f3-134">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="ab0f3-134">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\Announcements`
