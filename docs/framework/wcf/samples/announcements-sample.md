---
title: "Образец замечаний"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 954a75e4-9a97-41d6-94fc-43765d4205a9
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 045807df433d519b00969812afb0ae2feac94b75
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="announcements-sample"></a><span data-ttu-id="01981-102">Образец замечаний</span><span class="sxs-lookup"><span data-stu-id="01981-102">Announcements Sample</span></span>
<span data-ttu-id="01981-103">Данный образец показывает, как использовать функциональность объявлений возможности обнаружения.</span><span class="sxs-lookup"><span data-stu-id="01981-103">This sample shows how to use the Announcement functionality of the Discovery feature.</span></span> <span data-ttu-id="01981-104">Объявления позволяют службам отправлять сообщения объявления, содержащие метаданные службы.</span><span class="sxs-lookup"><span data-stu-id="01981-104">Announcements allow services to send out announcement messages that contain metadata about the service.</span></span> <span data-ttu-id="01981-105">По умолчанию отправляется объявление о входе в сеть при запуске службы и объявление о выходе из сети при отключении службы.</span><span class="sxs-lookup"><span data-stu-id="01981-105">By default a hello announcement is sent when the service starts up and a bye announcement is sent when the service shuts down.</span></span> <span data-ttu-id="01981-106">Эти объявления могут быть многоадресными или отправляться от точки к точке.</span><span class="sxs-lookup"><span data-stu-id="01981-106">These announcements can be multicast or they can be sent point-to-point.</span></span> <span data-ttu-id="01981-107">Этот образец состоит из двух проектов: служба и клиент.</span><span class="sxs-lookup"><span data-stu-id="01981-107">This sample consists of two projects service and client.</span></span>  
  
## <a name="service"></a><span data-ttu-id="01981-108">Служба</span><span class="sxs-lookup"><span data-stu-id="01981-108">Service</span></span>  
 <span data-ttu-id="01981-109">Данный проект содержит саморазмещаемую службу калькулятора.</span><span class="sxs-lookup"><span data-stu-id="01981-109">This project contains a self-hosted calculator service.</span></span> <span data-ttu-id="01981-110">В методе `Main` создается узел службы, к которому добавляется конечная точка службы.</span><span class="sxs-lookup"><span data-stu-id="01981-110">In the `Main` method, a service host is created and a service endpoint is added to it.</span></span> <span data-ttu-id="01981-111">Далее создается поведение <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.</span><span class="sxs-lookup"><span data-stu-id="01981-111">Next, a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> is created.</span></span> <span data-ttu-id="01981-112">Чтобы включить объявления, к поведению <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> должна быть добавлена конечная точка объявлений.</span><span class="sxs-lookup"><span data-stu-id="01981-112">To enable announcements, an announcement endpoint must be added to the <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.</span></span> <span data-ttu-id="01981-113">В случае стандартной конечной точки в качестве конечной точки объявления добавляется многоадресная рассылка UDP.</span><span class="sxs-lookup"><span data-stu-id="01981-113">In this case a standard endpoint, using UDP multicast is added as the announcement endpoint.</span></span> <span data-ttu-id="01981-114">При этом объявления рассылаются через общеизвестный адрес UDP.</span><span class="sxs-lookup"><span data-stu-id="01981-114">This broadcasts the announcements over a well-known UDP address.</span></span>  
  
```  
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
  
## <a name="client"></a><span data-ttu-id="01981-115">Клиент</span><span class="sxs-lookup"><span data-stu-id="01981-115">Client</span></span>  
 <span data-ttu-id="01981-116">Обратите внимание, что в данном проекте клиент содержит службу <xref:System.ServiceModel.Discovery.AnnouncementService>.</span><span class="sxs-lookup"><span data-stu-id="01981-116">In this project, note that the client hosts an <xref:System.ServiceModel.Discovery.AnnouncementService>.</span></span> <span data-ttu-id="01981-117">Кроме того, для событий зарегистрировано два делегата.</span><span class="sxs-lookup"><span data-stu-id="01981-117">Furthermore, two delegates are registered with events.</span></span> <span data-ttu-id="01981-118">Эти события определяют, что делает клиент при получении объявлений о входе и выходе из сети.</span><span class="sxs-lookup"><span data-stu-id="01981-118">These events dictate what the client does when online and offline announcements are received.</span></span>  
  
```  
// Create an AnnouncementService instance  
AnnouncementService announcementService = new AnnouncementService();  
  
// Subscribe the announcement events  
announcementService.OnlineAnnouncementReceived += OnOnlineEvent;  
announcementService.OfflineAnnouncementReceived += OnOfflineEvent;  
```  
  
 <span data-ttu-id="01981-119">Методы `OnOnlineEvent` и `OnOfflineEvent` обслуживают соответственно сообщения объявлений о входе и выходе из сети.</span><span class="sxs-lookup"><span data-stu-id="01981-119">The `OnOnlineEvent` and `OnOfflineEvent` methods handle the hello and bye announcement messages respectively.</span></span>  
  
```  
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
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="01981-120">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="01981-120">To use this sample</span></span>  
  
1.  <span data-ttu-id="01981-121">В этом образце используются конечные точки HTTP, и для запуска этого примера, соответствующие URL ACL, необходимо добавить см. в разделе [Настройка протоколов HTTP и HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) подробные сведения.</span><span class="sxs-lookup"><span data-stu-id="01981-121">This sample uses HTTP endpoints and to run this sample, proper URL ACLs must be added see [Configuring HTTP and HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) for details.</span></span> <span data-ttu-id="01981-122">Нужные списки управления доступом будут добавлены после выполнения следующей команды с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="01981-122">Executing the following command at an elevated privilege should add the appropriate ACLs.</span></span> <span data-ttu-id="01981-123">Если команда не работает, следует указать домен и имя пользователя в следующих аргументах.</span><span class="sxs-lookup"><span data-stu-id="01981-123">You may want to substitute your Domain and Username for the following arguments if the command does not work as is.</span></span> `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
2.  <span data-ttu-id="01981-124">Постройте решение.</span><span class="sxs-lookup"><span data-stu-id="01981-124">Build the solution.</span></span>  
  
3.  <span data-ttu-id="01981-125">Запустите приложение client.exe.</span><span class="sxs-lookup"><span data-stu-id="01981-125">Run the client.exe application.</span></span>  
  
4.  <span data-ttu-id="01981-126">Запустите приложение service.exe.</span><span class="sxs-lookup"><span data-stu-id="01981-126">Run the service.exe application.</span></span> <span data-ttu-id="01981-127">Обратите внимание, что клиент получает объявление о входе в сеть.</span><span class="sxs-lookup"><span data-stu-id="01981-127">Note the client receives an online announcement.</span></span>  
  
5.  <span data-ttu-id="01981-128">Закройте приложение service.exe.</span><span class="sxs-lookup"><span data-stu-id="01981-128">Close the service.exe application.</span></span> <span data-ttu-id="01981-129">Обратите внимание, что клиент получает объявление о выходе из сети.</span><span class="sxs-lookup"><span data-stu-id="01981-129">Note the client receives an offline announcement.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="01981-130">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="01981-130">The samples may already be installed on your machine.</span></span> <span data-ttu-id="01981-131">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="01981-131">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="01981-132">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="01981-132">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="01981-133">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="01981-133">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\Announcements`  
  
## <a name="see-also"></a><span data-ttu-id="01981-134">См. также</span><span class="sxs-lookup"><span data-stu-id="01981-134">See Also</span></span>
