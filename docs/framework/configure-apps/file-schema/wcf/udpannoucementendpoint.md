---
title: '&lt;udpAnnoucementEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b3fa9c5-f372-4df9-a9d6-1e426063b721
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 85fcd6b81cca9f9b7a71ebdda96ef75e1dc1405a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltudpannoucementendpointgt"></a><span data-ttu-id="3eab9-102">&lt;udpAnnoucementEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="3eab9-102">&lt;udpAnnoucementEndpoint&gt;</span></span>
<span data-ttu-id="3eab9-103">Этот элемент конфигурации определяет стандартную конечную точку, используемую службами для отправки сообщений с объявлениями по привязке UDP.</span><span class="sxs-lookup"><span data-stu-id="3eab9-103">This configuration element defines a standard endpoint that is used by services to send announcement messages over a UDP binding.</span></span> <span data-ttu-id="3eab9-104">Имеет фиксированный контракт и поддерживает две версии обнаружения.</span><span class="sxs-lookup"><span data-stu-id="3eab9-104">It has a fixed contract and supports two discovery versions.</span></span> <span data-ttu-id="3eab9-105">Кроме того, она имеет фиксированную привязку UDP и значение адреса по умолчанию, как определено в спецификациях WS-Discovery (WS-Discovery от апреля 2005 или WS-Discovery версии 1.1).</span><span class="sxs-lookup"><span data-stu-id="3eab9-105">In addition it has a fixed UDP binding and a default address value as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery version 1.1).</span></span> <span data-ttu-id="3eab9-106">Можно задать многопоточный адрес, который будет использовать для отправки и получения сообщений объявлений.</span><span class="sxs-lookup"><span data-stu-id="3eab9-106">You can specify the multicast address to use for sending and receiving the announcement messages.</span></span>  
  
<span data-ttu-id="3eab9-107">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3eab9-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="3eab9-108">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="3eab9-108">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eab9-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3eab9-109">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <announcementEndpoint>
      <standardEndpoint discoveryVersion="WSDiscovery11/WSDiscoveryApril2005" 
                        maxAnnouncementDelay="Timespan"
                        multicastAddress="Uri"
                        name="String" />
    </announcementEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3eab9-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3eab9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3eab9-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3eab9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3eab9-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3eab9-112">Attributes</span></span>  
  
|<span data-ttu-id="3eab9-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3eab9-113">Attribute</span></span>|<span data-ttu-id="3eab9-114">Описание</span><span class="sxs-lookup"><span data-stu-id="3eab9-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3eab9-115">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="3eab9-115">discoveryVersion</span></span>|<span data-ttu-id="3eab9-116">Строка, указывающая одну из двух версий протокола WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="3eab9-116">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="3eab9-117">Допустимые значения: WSDiscovery11 и WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="3eab9-117">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="3eab9-118">Это значение имеет тип <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="3eab9-118">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="3eab9-119">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="3eab9-119">maxAnnouncementDelay</span></span>|<span data-ttu-id="3eab9-120">Значение «Timespan», указывающее максимальную задержку, в течение которой протокол Discovery не будет отправлять сообщение Hello.</span><span class="sxs-lookup"><span data-stu-id="3eab9-120">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="3eab9-121">Перед отправкой сообщения ожидают произвольное время в диапазоне от 0 до значения этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="3eab9-121">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="3eab9-122">Этот атрибут используется для назначения короткой произвольной задержки для предотвращения перегрузки сети, когда сеть становится недоступной, а все службы входят в сеть одновременно.</span><span class="sxs-lookup"><span data-stu-id="3eab9-122">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="3eab9-123">multicastAddress</span><span class="sxs-lookup"><span data-stu-id="3eab9-123">multicastAddress</span></span>|<span data-ttu-id="3eab9-124">URI, в котором указывается адрес многоадресной рассылки, используемый для отправки и получения сообщений об обнаружении.</span><span class="sxs-lookup"><span data-stu-id="3eab9-124">A URI that specifies a multicast address to use for sending and receiving the discovery messages.</span></span> <span data-ttu-id="3eab9-125">Значением по умолчанию является многопоточный адрес, который соответствует спецификации протокола.</span><span class="sxs-lookup"><span data-stu-id="3eab9-125">The default value is the multicast address as conformant to the protocol specification.</span></span>|  
|<span data-ttu-id="3eab9-126">имя</span><span class="sxs-lookup"><span data-stu-id="3eab9-126">name</span></span>|<span data-ttu-id="3eab9-127">Строка, указывающая имя конфигурации стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="3eab9-127">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="3eab9-128">Это имя используется в атрибуте `endpointConfiguration` конечной точки службы для связывания стандартной конечной точки с ее конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="3eab9-128">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3eab9-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3eab9-129">Child Elements</span></span>  
  
|<span data-ttu-id="3eab9-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="3eab9-130">Element</span></span>|<span data-ttu-id="3eab9-131">Описание</span><span class="sxs-lookup"><span data-stu-id="3eab9-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3eab9-132">\<udpTransportSettings ></span><span class="sxs-lookup"><span data-stu-id="3eab9-132">\<udpTransportSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/udptransportsettings.md)|<span data-ttu-id="3eab9-133">Коллекция параметров, которые позволят настроить транспорт UDP для конечной точки UDP.</span><span class="sxs-lookup"><span data-stu-id="3eab9-133">A collection of settings that allow you to configure UDP transport for the UDP endpoint.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3eab9-134">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3eab9-134">Parent Elements</span></span>  
  
|<span data-ttu-id="3eab9-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="3eab9-135">Element</span></span>|<span data-ttu-id="3eab9-136">Описание</span><span class="sxs-lookup"><span data-stu-id="3eab9-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3eab9-137">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="3eab9-137">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="3eab9-138">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="3eab9-138">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3eab9-139">Пример</span><span class="sxs-lookup"><span data-stu-id="3eab9-139">Example</span></span>  
 <span data-ttu-id="3eab9-140">В следующем примере показано прослушивание клиентом сообщений с объявлением по многоадресному протоколу UDP с адресом многоадресной рассылки по умолчанию, а также с указанным адресом многоадресной рассылки UDP.</span><span class="sxs-lookup"><span data-stu-id="3eab9-140">The following example demonstrates a client listening for announcement over a UDP multicast transport with default multicast address, and UDP multicast transport with specified multicast address.</span></span>  
  
```xml  
<services>  
  <service name="ServiceAnnouncementListener">  
      <endpoint name="udpAnnouncementEndpointStandard"  
                kind="udpAnnouncementEndpoint"  
                bindingConfiguration="..." />  
      <endpoint name="udpAnnouncementEndpoint2"  
                kind="udpAnnouncementEndpoint"  
                endpointConfiguration="AnnouncementConfiguration3702"  
                bindingConfiguration="..." />  
...  
  </service>  
</services>  
<standardEndpoints>  
  <udpAnnouncementEndpoint>  
     <standardEndpoint name="AnnouncementConfiguration2"   
          version="WSDiscoveryApril2005"   
          multicastAddress="soap.udp://239.255.255.250:3703"/>          
  </udpAnnouncementEndpoint>  
</standardEndpoints>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3eab9-141">См. также</span><span class="sxs-lookup"><span data-stu-id="3eab9-141">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>
