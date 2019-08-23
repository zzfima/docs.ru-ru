---
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: a99edd3a62a40c2efbc63a166b8c0b0d124e8a72
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936278"
---
# <a name="servicediscovery"></a><span data-ttu-id="1d8c1-101">\<Сервицедисковери ></span><span class="sxs-lookup"><span data-stu-id="1d8c1-101">\<serviceDiscovery></span></span>
<span data-ttu-id="1d8c1-102">Указывает возможность обнаружения конечных точек службы.</span><span class="sxs-lookup"><span data-stu-id="1d8c1-102">Specifies the discoverability of service endpoints.</span></span>  
  
 <span data-ttu-id="1d8c1-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1d8c1-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="1d8c1-104">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="1d8c1-104">\<behaviors></span></span>  
<span data-ttu-id="1d8c1-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1d8c1-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="1d8c1-106">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="1d8c1-106">\<behavior></span></span>  
<span data-ttu-id="1d8c1-107">\<Сервицедисковери ></span><span class="sxs-lookup"><span data-stu-id="1d8c1-107">\<serviceDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d8c1-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1d8c1-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint name="String"
                    kind="Type" />
        </announcementEndpoints>
        <discoveryEndpoints>
          <endpoint name="String"
                    kind="Type" />
        </discoveryEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1d8c1-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1d8c1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1d8c1-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1d8c1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1d8c1-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1d8c1-111">Attributes</span></span>  
 <span data-ttu-id="1d8c1-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="1d8c1-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1d8c1-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1d8c1-113">Child Elements</span></span>  
  
|<span data-ttu-id="1d8c1-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="1d8c1-114">Element</span></span>|<span data-ttu-id="1d8c1-115">Описание</span><span class="sxs-lookup"><span data-stu-id="1d8c1-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1d8c1-116">\<Аннаунцементендпоинт ></span><span class="sxs-lookup"><span data-stu-id="1d8c1-116">\<announcementEndpoint></span></span>](announcementendpoint.md)|<span data-ttu-id="1d8c1-117">Коллекция конечных точек объявления.</span><span class="sxs-lookup"><span data-stu-id="1d8c1-117">A collection of announcement endpoints.</span></span> <span data-ttu-id="1d8c1-118">Используйте этот раздел, чтобы задать конечные точки, которые будут использоваться для отправки сообщений с объявлениями.</span><span class="sxs-lookup"><span data-stu-id="1d8c1-118">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[<span data-ttu-id="1d8c1-119">\<Дисковерендпоинт ></span><span class="sxs-lookup"><span data-stu-id="1d8c1-119">\<discoveryEndpoint></span></span>](discoveryendpoint.md)|<span data-ttu-id="1d8c1-120">Коллекция конечных точек обнаружения.</span><span class="sxs-lookup"><span data-stu-id="1d8c1-120">A collection of discovery endpoints.</span></span> <span data-ttu-id="1d8c1-121">Используйте этот раздел, чтобы задать конечные точки, которые будут прослушиваться на предмет сообщений об обнаружении.</span><span class="sxs-lookup"><span data-stu-id="1d8c1-121">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1d8c1-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1d8c1-122">Parent Elements</span></span>  
  
|<span data-ttu-id="1d8c1-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="1d8c1-123">Element</span></span>|<span data-ttu-id="1d8c1-124">Описание</span><span class="sxs-lookup"><span data-stu-id="1d8c1-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1d8c1-125">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="1d8c1-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="1d8c1-126">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="1d8c1-126">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d8c1-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="1d8c1-127">Remarks</span></span>  
 <span data-ttu-id="1d8c1-128">При добавлении к конфигурации поведения службы этот элемент конфигурации делает все конечные точки этой службы обнаруживаемыми.</span><span class="sxs-lookup"><span data-stu-id="1d8c1-128">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="1d8c1-129">Вы можете дополнительно настроить функции обнаружения таких конечных точек, используя [ \<](discoveryendpoint.md) дочерние элементы дисковерендпоинт > или [ \<аннаунцементендпоинт >](announcementendpoint.md) .</span><span class="sxs-lookup"><span data-stu-id="1d8c1-129">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](discoveryendpoint.md) or [\<announcementEndpoint>](announcementendpoint.md) child elements.</span></span> <span data-ttu-id="1d8c1-130">Используйте раздел [> аннаунцементендпоинт,чтобынастроитьобъявления,указавконфигурациюконечнойточки,котораябудетиспользоватьсядляотправкиобъявленийслужбы(всети,Helloиoffline/Bye).\<](announcementendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="1d8c1-130">Use the [\<announcementEndpoint>](announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="1d8c1-131">Используйте раздел [> дисковерендпоинт,чтобывручнуюуказатьконечнуюточкудляпрослушиваниясообщенийобнаружения.\<](discoveryendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="1d8c1-131">Use the [\<discoveryEndpoint>](discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d8c1-132">Пример</span><span class="sxs-lookup"><span data-stu-id="1d8c1-132">Example</span></span>  
 <span data-ttu-id="1d8c1-133">В следующем примере конфигурации указано, что объект CalculatorService является обнаруживаемым. Дополнительно также указана конечная точка, используемая для объявления.</span><span class="sxs-lookup"><span data-stu-id="1d8c1-133">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    ...
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint name="udpEndpoint"
                    kind="udpAnnouncementEndpoint" />
        </announcementEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="1d8c1-134">См. также</span><span class="sxs-lookup"><span data-stu-id="1d8c1-134">See also</span></span>

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
