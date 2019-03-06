---
title: <udpAnnouncementEndpoint>
ms.date: 03/30/2017
ms.assetid: 5b3fa9c5-f372-4df9-a9d6-1e426063b721
ms.openlocfilehash: 3ffb18fbd410922df4311180ef7af5153ba5c0f5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379811"
---
# <a name="udpannouncementendpoint"></a><span data-ttu-id="171aa-101">\<udpAnnouncementEndpoint ></span><span class="sxs-lookup"><span data-stu-id="171aa-101">\<udpAnnouncementEndpoint></span></span>
<span data-ttu-id="171aa-102">Этот элемент конфигурации определяет стандартную конечную точку, используемую службами для отправки сообщений с объявлениями по привязке UDP.</span><span class="sxs-lookup"><span data-stu-id="171aa-102">This configuration element defines a standard endpoint that is used by services to send announcement messages over a UDP binding.</span></span> <span data-ttu-id="171aa-103">Имеет фиксированный контракт и поддерживает две версии обнаружения.</span><span class="sxs-lookup"><span data-stu-id="171aa-103">It has a fixed contract and supports two discovery versions.</span></span> <span data-ttu-id="171aa-104">Кроме того, она имеет фиксированную привязку UDP и значение адреса по умолчанию, как определено в спецификациях WS-Discovery (WS-Discovery от апреля 2005 или WS-Discovery версии 1.1).</span><span class="sxs-lookup"><span data-stu-id="171aa-104">In addition it has a fixed UDP binding and a default address value as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery version 1.1).</span></span> <span data-ttu-id="171aa-105">Можно задать многопоточный адрес, который будет использовать для отправки и получения сообщений объявлений.</span><span class="sxs-lookup"><span data-stu-id="171aa-105">You can specify the multicast address to use for sending and receiving the announcement messages.</span></span>  
  
<span data-ttu-id="171aa-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="171aa-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="171aa-107">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="171aa-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="171aa-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="171aa-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="171aa-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="171aa-109">Attributes and Elements</span></span>  
 <span data-ttu-id="171aa-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="171aa-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="171aa-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="171aa-111">Attributes</span></span>  
  
|<span data-ttu-id="171aa-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="171aa-112">Attribute</span></span>|<span data-ttu-id="171aa-113">Описание</span><span class="sxs-lookup"><span data-stu-id="171aa-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="171aa-114">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="171aa-114">discoveryVersion</span></span>|<span data-ttu-id="171aa-115">Строка, указывающая одну из двух версий протокола WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="171aa-115">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="171aa-116">Допустимые значения: WSDiscovery11 и WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="171aa-116">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="171aa-117">Это значение имеет тип <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="171aa-117">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="171aa-118">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="171aa-118">maxAnnouncementDelay</span></span>|<span data-ttu-id="171aa-119">Значение «Timespan», указывающее максимальную задержку, в течение которой протокол Discovery не будет отправлять сообщение Hello.</span><span class="sxs-lookup"><span data-stu-id="171aa-119">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="171aa-120">Перед отправкой сообщения ожидают произвольное время в диапазоне от 0 до значения этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="171aa-120">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="171aa-121">Этот атрибут используется для назначения короткой произвольной задержки для предотвращения перегрузки сети, когда сеть становится недоступной, а все службы входят в сеть одновременно.</span><span class="sxs-lookup"><span data-stu-id="171aa-121">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="171aa-122">multicastAddress</span><span class="sxs-lookup"><span data-stu-id="171aa-122">multicastAddress</span></span>|<span data-ttu-id="171aa-123">URI, в котором указывается адрес многоадресной рассылки, используемый для отправки и получения сообщений об обнаружении.</span><span class="sxs-lookup"><span data-stu-id="171aa-123">A URI that specifies a multicast address to use for sending and receiving the discovery messages.</span></span> <span data-ttu-id="171aa-124">Значением по умолчанию является многопоточный адрес, который соответствует спецификации протокола.</span><span class="sxs-lookup"><span data-stu-id="171aa-124">The default value is the multicast address as conformant to the protocol specification.</span></span>|  
|<span data-ttu-id="171aa-125">имя</span><span class="sxs-lookup"><span data-stu-id="171aa-125">name</span></span>|<span data-ttu-id="171aa-126">Строка, указывающая имя конфигурации стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="171aa-126">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="171aa-127">Это имя используется в атрибуте `endpointConfiguration` конечной точки службы для связывания стандартной конечной точки с ее конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="171aa-127">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="171aa-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="171aa-128">Child Elements</span></span>  
  
|<span data-ttu-id="171aa-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="171aa-129">Element</span></span>|<span data-ttu-id="171aa-130">Описание</span><span class="sxs-lookup"><span data-stu-id="171aa-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="171aa-131">\<udpTransportSettings ></span><span class="sxs-lookup"><span data-stu-id="171aa-131">\<udpTransportSettings></span></span>](udptransportsettings.md)|<span data-ttu-id="171aa-132">Коллекция параметров, которые позволят настроить транспорт UDP для конечной точки UDP.</span><span class="sxs-lookup"><span data-stu-id="171aa-132">A collection of settings that allow you to configure UDP transport for the UDP endpoint.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="171aa-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="171aa-133">Parent Elements</span></span>  
  
|<span data-ttu-id="171aa-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="171aa-134">Element</span></span>|<span data-ttu-id="171aa-135">Описание:</span><span class="sxs-lookup"><span data-stu-id="171aa-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="171aa-136">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="171aa-136">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="171aa-137">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="171aa-137">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="171aa-138">Пример</span><span class="sxs-lookup"><span data-stu-id="171aa-138">Example</span></span>  
 <span data-ttu-id="171aa-139">В следующем примере показано прослушивание клиентом сообщений с объявлением по многоадресному протоколу UDP с адресом многоадресной рассылки по умолчанию, а также с указанным адресом многоадресной рассылки UDP.</span><span class="sxs-lookup"><span data-stu-id="171aa-139">The following example demonstrates a client listening for announcement over a UDP multicast transport with default multicast address, and UDP multicast transport with specified multicast address.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="171aa-140">См. также</span><span class="sxs-lookup"><span data-stu-id="171aa-140">See also</span></span>
- <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>
