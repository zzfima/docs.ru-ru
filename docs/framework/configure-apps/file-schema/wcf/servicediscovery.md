---
title: '&lt;serviceDiscovery&gt;'
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: 73943f5f962a6963809e2c65ce8593f6181559f7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587337"
---
# <a name="ltservicediscoverygt"></a><span data-ttu-id="e6cc3-102">&lt;serviceDiscovery&gt;</span><span class="sxs-lookup"><span data-stu-id="e6cc3-102">&lt;serviceDiscovery&gt;</span></span>
<span data-ttu-id="e6cc3-103">Указывает возможность обнаружения конечных точек службы.</span><span class="sxs-lookup"><span data-stu-id="e6cc3-103">Specifies the discoverability of service endpoints.</span></span>  
  
 <span data-ttu-id="e6cc3-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e6cc3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e6cc3-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="e6cc3-105">\<behaviors></span></span>  
<span data-ttu-id="e6cc3-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e6cc3-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="e6cc3-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="e6cc3-107">\<behavior></span></span>  
<span data-ttu-id="e6cc3-108">\<serviceDiscovery ></span><span class="sxs-lookup"><span data-stu-id="e6cc3-108">\<serviceDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6cc3-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e6cc3-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e6cc3-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e6cc3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e6cc3-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e6cc3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6cc3-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e6cc3-112">Attributes</span></span>  
 <span data-ttu-id="e6cc3-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e6cc3-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e6cc3-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e6cc3-114">Child Elements</span></span>  
  
|<span data-ttu-id="e6cc3-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="e6cc3-115">Element</span></span>|<span data-ttu-id="e6cc3-116">Описание:</span><span class="sxs-lookup"><span data-stu-id="e6cc3-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e6cc3-117">\<announcementEndpoint ></span><span class="sxs-lookup"><span data-stu-id="e6cc3-117">\<announcementEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)|<span data-ttu-id="e6cc3-118">Коллекция конечных точек объявления.</span><span class="sxs-lookup"><span data-stu-id="e6cc3-118">A collection of announcement endpoints.</span></span> <span data-ttu-id="e6cc3-119">Используйте этот раздел, чтобы задать конечные точки, которые будут использоваться для отправки сообщений с объявлениями.</span><span class="sxs-lookup"><span data-stu-id="e6cc3-119">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[<span data-ttu-id="e6cc3-120">\<discoveryEndpoint ></span><span class="sxs-lookup"><span data-stu-id="e6cc3-120">\<discoveryEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)|<span data-ttu-id="e6cc3-121">Коллекция конечных точек обнаружения.</span><span class="sxs-lookup"><span data-stu-id="e6cc3-121">A collection of discovery endpoints.</span></span> <span data-ttu-id="e6cc3-122">Используйте этот раздел, чтобы задать конечные точки, которые будут прослушиваться на предмет сообщений об обнаружении.</span><span class="sxs-lookup"><span data-stu-id="e6cc3-122">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e6cc3-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e6cc3-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e6cc3-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="e6cc3-124">Element</span></span>|<span data-ttu-id="e6cc3-125">Описание:</span><span class="sxs-lookup"><span data-stu-id="e6cc3-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e6cc3-126">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="e6cc3-126">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="e6cc3-127">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="e6cc3-127">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6cc3-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="e6cc3-128">Remarks</span></span>  
 <span data-ttu-id="e6cc3-129">При добавлении к конфигурации поведения службы этот элемент конфигурации делает все конечные точки этой службы обнаруживаемыми.</span><span class="sxs-lookup"><span data-stu-id="e6cc3-129">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="e6cc3-130">Можно продолжить настройку функции обнаружения этих конечных точек с помощью [ \<discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) или [ \<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="e6cc3-130">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) or [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) child elements.</span></span> <span data-ttu-id="e6cc3-131">Используйте [ \<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) раздел для настройки объявлений, указав конфигурацию конечной точки, которая будет использована для отправки объявлений службы (online/Hello и offline/Bye).</span><span class="sxs-lookup"><span data-stu-id="e6cc3-131">Use the [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="e6cc3-132">Используйте [ \<discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) раздел, чтобы вручную указать конечную точку, которая для прослушивания сообщений обнаружения.</span><span class="sxs-lookup"><span data-stu-id="e6cc3-132">Use the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6cc3-133">Пример</span><span class="sxs-lookup"><span data-stu-id="e6cc3-133">Example</span></span>  
 <span data-ttu-id="e6cc3-134">В следующем примере конфигурации указано, что объект CalculatorService является обнаруживаемым. Дополнительно также указана конечная точка, используемая для объявления.</span><span class="sxs-lookup"><span data-stu-id="e6cc3-134">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e6cc3-135">См. также</span><span class="sxs-lookup"><span data-stu-id="e6cc3-135">See also</span></span>
- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
