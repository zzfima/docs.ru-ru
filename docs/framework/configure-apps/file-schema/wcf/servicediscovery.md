---
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: 564410fdc4085cc3ed14c394006551cddb028910
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373755"
---
# <a name="servicediscovery"></a><span data-ttu-id="1ab9c-101">\<serviceDiscovery ></span><span class="sxs-lookup"><span data-stu-id="1ab9c-101">\<serviceDiscovery></span></span>
<span data-ttu-id="1ab9c-102">Указывает возможность обнаружения конечных точек службы.</span><span class="sxs-lookup"><span data-stu-id="1ab9c-102">Specifies the discoverability of service endpoints.</span></span>  
  
 <span data-ttu-id="1ab9c-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1ab9c-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="1ab9c-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="1ab9c-104">\<behaviors></span></span>  
<span data-ttu-id="1ab9c-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1ab9c-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="1ab9c-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="1ab9c-106">\<behavior></span></span>  
<span data-ttu-id="1ab9c-107">\<serviceDiscovery ></span><span class="sxs-lookup"><span data-stu-id="1ab9c-107">\<serviceDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ab9c-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1ab9c-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ab9c-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1ab9c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1ab9c-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1ab9c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ab9c-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1ab9c-111">Attributes</span></span>  
 <span data-ttu-id="1ab9c-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1ab9c-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1ab9c-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1ab9c-113">Child Elements</span></span>  
  
|<span data-ttu-id="1ab9c-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="1ab9c-114">Element</span></span>|<span data-ttu-id="1ab9c-115">Описание:</span><span class="sxs-lookup"><span data-stu-id="1ab9c-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ab9c-116">\<announcementEndpoint ></span><span class="sxs-lookup"><span data-stu-id="1ab9c-116">\<announcementEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)|<span data-ttu-id="1ab9c-117">Коллекция конечных точек объявления.</span><span class="sxs-lookup"><span data-stu-id="1ab9c-117">A collection of announcement endpoints.</span></span> <span data-ttu-id="1ab9c-118">Используйте этот раздел, чтобы задать конечные точки, которые будут использоваться для отправки сообщений с объявлениями.</span><span class="sxs-lookup"><span data-stu-id="1ab9c-118">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[<span data-ttu-id="1ab9c-119">\<discoveryEndpoint ></span><span class="sxs-lookup"><span data-stu-id="1ab9c-119">\<discoveryEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)|<span data-ttu-id="1ab9c-120">Коллекция конечных точек обнаружения.</span><span class="sxs-lookup"><span data-stu-id="1ab9c-120">A collection of discovery endpoints.</span></span> <span data-ttu-id="1ab9c-121">Используйте этот раздел, чтобы задать конечные точки, которые будут прослушиваться на предмет сообщений об обнаружении.</span><span class="sxs-lookup"><span data-stu-id="1ab9c-121">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1ab9c-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1ab9c-122">Parent Elements</span></span>  
  
|<span data-ttu-id="1ab9c-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="1ab9c-123">Element</span></span>|<span data-ttu-id="1ab9c-124">Описание:</span><span class="sxs-lookup"><span data-stu-id="1ab9c-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ab9c-125">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="1ab9c-125">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="1ab9c-126">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="1ab9c-126">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ab9c-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="1ab9c-127">Remarks</span></span>  
 <span data-ttu-id="1ab9c-128">При добавлении к конфигурации поведения службы этот элемент конфигурации делает все конечные точки этой службы обнаруживаемыми.</span><span class="sxs-lookup"><span data-stu-id="1ab9c-128">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="1ab9c-129">Можно продолжить настройку функции обнаружения этих конечных точек с помощью [ \<discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) или [ \<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="1ab9c-129">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) or [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) child elements.</span></span> <span data-ttu-id="1ab9c-130">Используйте [ \<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) раздел для настройки объявлений, указав конфигурацию конечной точки, которая будет использована для отправки объявлений службы (online/Hello и offline/Bye).</span><span class="sxs-lookup"><span data-stu-id="1ab9c-130">Use the [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="1ab9c-131">Используйте [ \<discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) раздел, чтобы вручную указать конечную точку, которая для прослушивания сообщений обнаружения.</span><span class="sxs-lookup"><span data-stu-id="1ab9c-131">Use the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ab9c-132">Пример</span><span class="sxs-lookup"><span data-stu-id="1ab9c-132">Example</span></span>  
 <span data-ttu-id="1ab9c-133">В следующем примере конфигурации указано, что объект CalculatorService является обнаруживаемым. Дополнительно также указана конечная точка, используемая для объявления.</span><span class="sxs-lookup"><span data-stu-id="1ab9c-133">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1ab9c-134">См. также</span><span class="sxs-lookup"><span data-stu-id="1ab9c-134">See also</span></span>
- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
