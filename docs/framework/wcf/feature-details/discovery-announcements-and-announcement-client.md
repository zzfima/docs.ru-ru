---
title: Объявления обнаружения и клиент объявления
ms.date: 03/30/2017
ms.assetid: 426c6437-f8d2-4968-b23a-18afd671aa4b
ms.openlocfilehash: c32aca5e6deab01423d61c516ee924d00bc041ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="discovery-announcements-and-announcement-client"></a><span data-ttu-id="3d96b-102">Объявления обнаружения и клиент объявления</span><span class="sxs-lookup"><span data-stu-id="3d96b-102">Discovery Announcements and Announcement Client</span></span>
<span data-ttu-id="3d96b-103">Функция обнаружения WCF позволяет компонентам объявлять свою доступность.</span><span class="sxs-lookup"><span data-stu-id="3d96b-103">The WCF discovery feature enables components to announce their availability.</span></span> <span data-ttu-id="3d96b-104">При соответствующей настройке служба отправляет объявления Hello и Bye.</span><span class="sxs-lookup"><span data-stu-id="3d96b-104">If configured to do so, a service sends Hello and Bye announcements.</span></span> <span data-ttu-id="3d96b-105">Клиенты или другие компоненты могут прослушивать данные сообщения с объявлениями и действовать необходимым образом.</span><span class="sxs-lookup"><span data-stu-id="3d96b-105">Clients or other components can listen for such announcement messages and act on them.</span></span> <span data-ttu-id="3d96b-106">Это дает клиенту альтернативный метод получения данных о службах.</span><span class="sxs-lookup"><span data-stu-id="3d96b-106">This provides an alternative method for clients to be aware of services.</span></span> <span data-ttu-id="3d96b-107">Функция объявлений может использоваться несколькими разными способами. Например, если службы часто входят в сеть и выходят из сети, то объявления могут стать альтернативой их поиску.</span><span class="sxs-lookup"><span data-stu-id="3d96b-107">Announcement functionality has several uses, for example, if the services enter and leave a network frequently, announcements may be a better alternative than searching for services.</span></span> <span data-ttu-id="3d96b-108">Такой подход дает возможность снизить нагрузку на сеть, а клиенту - получать больше сведений о наличии или отсутствии службы по мере получения объявлений.</span><span class="sxs-lookup"><span data-stu-id="3d96b-108">With this approach, the network traffic is reduced and the client can learn about the presence or departure of the service as soon as announcements are received.</span></span>  
  
## <a name="discovery-announcements"></a><span data-ttu-id="3d96b-109">Объявления обнаружения</span><span class="sxs-lookup"><span data-stu-id="3d96b-109">Discovery Announcements</span></span>  
 <span data-ttu-id="3d96b-110">Когда служба, настроенная для объявлений, подключается к сети и становится доступной для обнаружения, она отправляет сообщение Hello, которое объявляет прослушивающим клиентам о ее доступности.</span><span class="sxs-lookup"><span data-stu-id="3d96b-110">When a service configured for announcements joins a network and becomes discoverable, it sends a Hello message announcing its availability to listening clients.</span></span> <span data-ttu-id="3d96b-111">Сообщение содержит сведения, связанные с обнаружением службы, например контракт, адрес конечной точки и соответствующие области.</span><span class="sxs-lookup"><span data-stu-id="3d96b-111">The message contains discovery related information about the service, such as its contract, endpoint address and associated scopes.</span></span> <span data-ttu-id="3d96b-112">В классе <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> можно указать, куда отправляется сообщение с объявлением.</span><span class="sxs-lookup"><span data-stu-id="3d96b-112">You can specify where the announcement message is sent with the <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> class.</span></span> <span data-ttu-id="3d96b-113">Если конечной точкой объявления является <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>, то сообщения Hello и Bye одновременно передаются нескольким абонентам. Если же конечная точка объявления является одноадресной рассылкой, то сообщения передаются непосредственно указанной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="3d96b-113">If the announcement endpoint is a <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> then the Hello and Bye are multicast appropriately, or if the announcement endpoint is unicast, the messages are sent directly to the specified endpoint.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d96b-114">Объявления отправляются при открытии и закрытии узла службы.</span><span class="sxs-lookup"><span data-stu-id="3d96b-114">Announcements are sent when the service host opens and closes.</span></span> <span data-ttu-id="3d96b-115">При неправильном завершении этих вызовов сообщения могут не отправляться. Например, при возникновении ошибки службы сообщение с объявлением Bye не отправляется.</span><span class="sxs-lookup"><span data-stu-id="3d96b-115">If these calls do not finish properly the announcement message may not be sent out. For example if the service faults, then the Bye announcement message is not sent.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="3d96b-116">Функцию объявлений можно настроить на отправку объявлений в заданных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="3d96b-116">You can customize the announcement functionality, allowing you to send announcements whenever you choose.</span></span>  
  
 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]<span data-ttu-id="3d96b-117"> определяет <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> и <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> как стандартные конечные точки, позволяя службам и клиентам отправлять объявления Hello и Bye.</span><span class="sxs-lookup"><span data-stu-id="3d96b-117"> defines the <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> and <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> as standard endpoints to allow services and clients to easily send Hello and Bye announcements.</span></span>  
  
### <a name="announcements-on-the-service"></a><span data-ttu-id="3d96b-118">Объявления в службе</span><span class="sxs-lookup"><span data-stu-id="3d96b-118">Announcements on the Service</span></span>  
 <span data-ttu-id="3d96b-119">Чтобы настроить отправку объявлений службой, добавьте <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> с конечной точкой объявления.</span><span class="sxs-lookup"><span data-stu-id="3d96b-119">To configure the service to send announcements, add a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> with an announcement endpoint.</span></span> <span data-ttu-id="3d96b-120">В следующем примере показано, как программным способом добавить это поведение в узел службы.</span><span class="sxs-lookup"><span data-stu-id="3d96b-120">The following example shows how to programmatically add this behavior to the service host.</span></span> <span data-ttu-id="3d96b-121">В этом примере используется `UdpAnnouncementEndpoint`, которая подразумевает, что сообщения являются многоадресной рассылкой в расположения, указываемые конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="3d96b-121">This example uses the `UdpAnnouncementEndpoint`, which implies that the announcements are multicast to a location specified by that standard endpoint.</span></span>  
  
```  
ServiceDiscoveryBehavior serviceDiscoveryBehavior = new ServiceDiscoveryBehavior();
serviceDiscoveryBehavior.AnnouncementEndpoints.Add(new UdpAnnouncementEndpoint());
serviceHost.Description.Behaviors.Add(serviceDiscoveryBehavior);
```  
  
 <span data-ttu-id="3d96b-122">Это поведение можно также настроить в файле конфигурации, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="3d96b-122">The behavior can be configured in the configuration file as well, as shown in the following example.</span></span>  
  
```xml  
<services>
  <service behaviorConfiguration="CalculatorBehavior" name="Microsoft.Samples.Discovery.CalculatorService">
    <!--Add Discovery Endpoint-->
    <endpoint name="udpDiscoveryEpt" kind="udpDiscoveryEndpoint" />
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorBehavior">
      <!--Add Discovery behavior-->
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint kind="udpAnnouncementEndpoint" />
        </announcementEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
 <span data-ttu-id="3d96b-123">В предыдущих примерах служба настраивается для автоматической отправки сообщений с объявлениями.</span><span class="sxs-lookup"><span data-stu-id="3d96b-123">The preceding examples configure a service to automatically send announcement messages.</span></span> <span data-ttu-id="3d96b-124">Можно также отправлять сообщения с объявлениями явным образом с помощью класса <xref:System.ServiceModel.Discovery.AnnouncementClient>.</span><span class="sxs-lookup"><span data-stu-id="3d96b-124">You can also send announcement messages explicitly by using the <xref:System.ServiceModel.Discovery.AnnouncementClient> class.</span></span>  
  
### <a name="announcements-on-the-client"></a><span data-ttu-id="3d96b-125">Объявления на клиенте</span><span class="sxs-lookup"><span data-stu-id="3d96b-125">Announcements on the Client</span></span>  
 <span data-ttu-id="3d96b-126">В клиентском приложение должна быть размещена служба объявлений, которая занимается обработкой сообщений Hello и Bye и подписана на события <xref:System.ServiceModel.Discovery.AnnouncementService.OnlineAnnouncementReceived> и <xref:System.ServiceModel.Discovery.AnnouncementService.OfflineAnnouncementReceived>.</span><span class="sxs-lookup"><span data-stu-id="3d96b-126">A client application must host an announcement service to respond to the Hello and Bye messages and subscribe to the <xref:System.ServiceModel.Discovery.AnnouncementService.OnlineAnnouncementReceived> and <xref:System.ServiceModel.Discovery.AnnouncementService.OfflineAnnouncementReceived> events.</span></span> <span data-ttu-id="3d96b-127">Следующий пример показывает, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="3d96b-127">The following example shows how to do this.</span></span>  
  
```  
// Create an AnnouncementService instance
AnnouncementService announcementService = new AnnouncementService();
  
// Subscribe the announcement events
announcementService.OnlineAnnouncementReceived += OnOnlineEvent;
announcementService.OfflineAnnouncementReceived += OnOfflineEvent;
  
// Create ServiceHost for the AnnouncementService
using (ServiceHost announcementServiceHost = new ServiceHost(announcementService))
{  
    // Listen for the announcements sent over UDP multicast
    announcementServiceHost.AddServiceEndpoint(new UdpAnnouncementEndpoint());
    announcementServiceHost.Open();
  
    Console.WriteLine("Press <ENTER> to terminate.");
    Console.ReadLine();
}  
```  
  
 <span data-ttu-id="3d96b-128">При входящей обработке сообщения Hello или Bye метаданные обнаружения конечной точки доступны через <xref:System.ServiceModel.Discovery.AnnouncementEventArgs>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="3d96b-128">When a Hello or Bye message is received, you can access the endpoint discovery metadata through <xref:System.ServiceModel.Discovery.AnnouncementEventArgs> as shown in the following example.</span></span>  
  
```  
static void OnOnlineEvent(object sender, AnnouncementEventArgs e)
{
    Console.WriteLine("Received an online announcement from {0}", 
e.EndpointDiscoveryMetadata.Address);
}

static void OnOfflineEvent(object sender, AnnouncementEventArgs e)
{
    Console.WriteLine("Received an offline announcement from {0}", 
e.EndpointDiscoveryMetadata.Address);
}
```
