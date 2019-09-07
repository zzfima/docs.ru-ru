---
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: 7ac067e84f2a4d2724e3d8f2d0af9b220fd15538
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399660"
---
# <a name="servicediscovery"></a><span data-ttu-id="7071c-101">\<Сервицедисковери ></span><span class="sxs-lookup"><span data-stu-id="7071c-101">\<serviceDiscovery></span></span>
<span data-ttu-id="7071c-102">Указывает возможность обнаружения конечных точек службы.</span><span class="sxs-lookup"><span data-stu-id="7071c-102">Specifies the discoverability of service endpoints.</span></span>  
  
<span data-ttu-id="7071c-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7071c-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7071c-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7071c-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7071c-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7071c-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="7071c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7071c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="7071c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7071c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="7071c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Сервицедисковери >**</span><span class="sxs-lookup"><span data-stu-id="7071c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceDiscovery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7071c-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7071c-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7071c-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7071c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7071c-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7071c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7071c-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7071c-112">Attributes</span></span>  
 <span data-ttu-id="7071c-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="7071c-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7071c-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7071c-114">Child Elements</span></span>  
  
|<span data-ttu-id="7071c-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="7071c-115">Element</span></span>|<span data-ttu-id="7071c-116">Описание</span><span class="sxs-lookup"><span data-stu-id="7071c-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7071c-117">\<Аннаунцементендпоинт ></span><span class="sxs-lookup"><span data-stu-id="7071c-117">\<announcementEndpoint></span></span>](announcementendpoint.md)|<span data-ttu-id="7071c-118">Коллекция конечных точек объявления.</span><span class="sxs-lookup"><span data-stu-id="7071c-118">A collection of announcement endpoints.</span></span> <span data-ttu-id="7071c-119">Используйте этот раздел, чтобы задать конечные точки, которые будут использоваться для отправки сообщений с объявлениями.</span><span class="sxs-lookup"><span data-stu-id="7071c-119">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[<span data-ttu-id="7071c-120">\<Дисковерендпоинт ></span><span class="sxs-lookup"><span data-stu-id="7071c-120">\<discoveryEndpoint></span></span>](discoveryendpoint.md)|<span data-ttu-id="7071c-121">Коллекция конечных точек обнаружения.</span><span class="sxs-lookup"><span data-stu-id="7071c-121">A collection of discovery endpoints.</span></span> <span data-ttu-id="7071c-122">Используйте этот раздел, чтобы задать конечные точки, которые будут прослушиваться на предмет сообщений об обнаружении.</span><span class="sxs-lookup"><span data-stu-id="7071c-122">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7071c-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7071c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="7071c-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="7071c-124">Element</span></span>|<span data-ttu-id="7071c-125">Описание</span><span class="sxs-lookup"><span data-stu-id="7071c-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7071c-126">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="7071c-126">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="7071c-127">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="7071c-127">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7071c-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="7071c-128">Remarks</span></span>  
 <span data-ttu-id="7071c-129">При добавлении к конфигурации поведения службы этот элемент конфигурации делает все конечные точки этой службы обнаруживаемыми.</span><span class="sxs-lookup"><span data-stu-id="7071c-129">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="7071c-130">Вы можете дополнительно настроить функции обнаружения таких конечных точек, используя [ \<](discoveryendpoint.md) дочерние элементы дисковерендпоинт > или [ \<аннаунцементендпоинт >](announcementendpoint.md) .</span><span class="sxs-lookup"><span data-stu-id="7071c-130">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](discoveryendpoint.md) or [\<announcementEndpoint>](announcementendpoint.md) child elements.</span></span> <span data-ttu-id="7071c-131">Используйте раздел [> аннаунцементендпоинт,чтобынастроитьобъявления,указавконфигурациюконечнойточки,котораябудетиспользоватьсядляотправкиобъявленийслужбы(всети,Helloиoffline/Bye).\<](announcementendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="7071c-131">Use the [\<announcementEndpoint>](announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="7071c-132">Используйте раздел [> дисковерендпоинт,чтобывручнуюуказатьконечнуюточкудляпрослушиваниясообщенийобнаружения.\<](discoveryendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="7071c-132">Use the [\<discoveryEndpoint>](discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7071c-133">Пример</span><span class="sxs-lookup"><span data-stu-id="7071c-133">Example</span></span>  
 <span data-ttu-id="7071c-134">В следующем примере конфигурации указано, что объект CalculatorService является обнаруживаемым. Дополнительно также указана конечная точка, используемая для объявления.</span><span class="sxs-lookup"><span data-stu-id="7071c-134">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7071c-135">См. также</span><span class="sxs-lookup"><span data-stu-id="7071c-135">See also</span></span>

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
