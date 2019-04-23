---
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: 54a9833f56927568af711a103bd3831b767711e4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59210000"
---
# <a name="servicediscovery"></a><span data-ttu-id="5ff0d-101">\<serviceDiscovery ></span><span class="sxs-lookup"><span data-stu-id="5ff0d-101">\<serviceDiscovery></span></span>
<span data-ttu-id="5ff0d-102">Указывает возможность обнаружения конечных точек службы.</span><span class="sxs-lookup"><span data-stu-id="5ff0d-102">Specifies the discoverability of service endpoints.</span></span>  
  
 <span data-ttu-id="5ff0d-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5ff0d-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="5ff0d-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="5ff0d-104">\<behaviors></span></span>  
<span data-ttu-id="5ff0d-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="5ff0d-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="5ff0d-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="5ff0d-106">\<behavior></span></span>  
<span data-ttu-id="5ff0d-107">\<serviceDiscovery ></span><span class="sxs-lookup"><span data-stu-id="5ff0d-107">\<serviceDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ff0d-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5ff0d-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ff0d-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5ff0d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5ff0d-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5ff0d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ff0d-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5ff0d-111">Attributes</span></span>  
 <span data-ttu-id="5ff0d-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5ff0d-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5ff0d-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5ff0d-113">Child Elements</span></span>  
  
|<span data-ttu-id="5ff0d-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="5ff0d-114">Element</span></span>|<span data-ttu-id="5ff0d-115">Описание</span><span class="sxs-lookup"><span data-stu-id="5ff0d-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ff0d-116">\<announcementEndpoint ></span><span class="sxs-lookup"><span data-stu-id="5ff0d-116">\<announcementEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)|<span data-ttu-id="5ff0d-117">Коллекция конечных точек объявления.</span><span class="sxs-lookup"><span data-stu-id="5ff0d-117">A collection of announcement endpoints.</span></span> <span data-ttu-id="5ff0d-118">Используйте этот раздел, чтобы задать конечные точки, которые будут использоваться для отправки сообщений с объявлениями.</span><span class="sxs-lookup"><span data-stu-id="5ff0d-118">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[<span data-ttu-id="5ff0d-119">\<discoveryEndpoint ></span><span class="sxs-lookup"><span data-stu-id="5ff0d-119">\<discoveryEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)|<span data-ttu-id="5ff0d-120">Коллекция конечных точек обнаружения.</span><span class="sxs-lookup"><span data-stu-id="5ff0d-120">A collection of discovery endpoints.</span></span> <span data-ttu-id="5ff0d-121">Используйте этот раздел, чтобы задать конечные точки, которые будут прослушиваться на предмет сообщений об обнаружении.</span><span class="sxs-lookup"><span data-stu-id="5ff0d-121">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5ff0d-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5ff0d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="5ff0d-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="5ff0d-123">Element</span></span>|<span data-ttu-id="5ff0d-124">Описание</span><span class="sxs-lookup"><span data-stu-id="5ff0d-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ff0d-125">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="5ff0d-125">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="5ff0d-126">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="5ff0d-126">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ff0d-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="5ff0d-127">Remarks</span></span>  
 <span data-ttu-id="5ff0d-128">При добавлении к конфигурации поведения службы этот элемент конфигурации делает все конечные точки этой службы обнаруживаемыми.</span><span class="sxs-lookup"><span data-stu-id="5ff0d-128">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="5ff0d-129">Можно продолжить настройку функции обнаружения этих конечных точек с помощью [ \<discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) или [ \<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="5ff0d-129">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) or [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) child elements.</span></span> <span data-ttu-id="5ff0d-130">Используйте [ \<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) раздел для настройки объявлений, указав конфигурацию конечной точки, которая будет использована для отправки объявлений службы (online/Hello и offline/Bye).</span><span class="sxs-lookup"><span data-stu-id="5ff0d-130">Use the [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="5ff0d-131">Используйте [ \<discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) раздел, чтобы вручную указать конечную точку, которая для прослушивания сообщений обнаружения.</span><span class="sxs-lookup"><span data-stu-id="5ff0d-131">Use the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ff0d-132">Пример</span><span class="sxs-lookup"><span data-stu-id="5ff0d-132">Example</span></span>  
 <span data-ttu-id="5ff0d-133">В следующем примере конфигурации указано, что объект CalculatorService является обнаруживаемым. Дополнительно также указана конечная точка, используемая для объявления.</span><span class="sxs-lookup"><span data-stu-id="5ff0d-133">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5ff0d-134">См. также</span><span class="sxs-lookup"><span data-stu-id="5ff0d-134">See also</span></span>

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
