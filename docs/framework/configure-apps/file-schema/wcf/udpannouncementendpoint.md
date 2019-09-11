---
title: <udpAnnouncementEndpoint>
ms.date: 03/30/2017
ms.assetid: 5b3fa9c5-f372-4df9-a9d6-1e426063b721
ms.openlocfilehash: 8dabf8845126705d082d080b643688ed62883f39
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854913"
---
# <a name="udpannouncementendpoint"></a><span data-ttu-id="dac41-101">\<udpAnnouncementEndpoint ></span><span class="sxs-lookup"><span data-stu-id="dac41-101">\<udpAnnouncementEndpoint></span></span>
<span data-ttu-id="dac41-102">Этот элемент конфигурации определяет стандартную конечную точку, используемую службами для отправки сообщений с объявлениями по привязке UDP.</span><span class="sxs-lookup"><span data-stu-id="dac41-102">This configuration element defines a standard endpoint that is used by services to send announcement messages over a UDP binding.</span></span> <span data-ttu-id="dac41-103">Имеет фиксированный контракт и поддерживает две версии обнаружения.</span><span class="sxs-lookup"><span data-stu-id="dac41-103">It has a fixed contract and supports two discovery versions.</span></span> <span data-ttu-id="dac41-104">Кроме того, она имеет фиксированную привязку UDP и значение адреса по умолчанию, как определено в спецификациях WS-Discovery (WS-Discovery от апреля 2005 или WS-Discovery версии 1.1).</span><span class="sxs-lookup"><span data-stu-id="dac41-104">In addition it has a fixed UDP binding and a default address value as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery version 1.1).</span></span> <span data-ttu-id="dac41-105">Можно задать многопоточный адрес, который будет использовать для отправки и получения сообщений объявлений.</span><span class="sxs-lookup"><span data-stu-id="dac41-105">You can specify the multicast address to use for sending and receiving the announcement messages.</span></span>  
  
<span data-ttu-id="dac41-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="dac41-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="dac41-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="dac41-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="dac41-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Стандардендпоинтс >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="dac41-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="dac41-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<udpAnnouncementEndpoint >**</span><span class="sxs-lookup"><span data-stu-id="dac41-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<udpAnnouncementEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dac41-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dac41-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dac41-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dac41-111">Attributes and Elements</span></span>  
 <span data-ttu-id="dac41-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dac41-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dac41-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dac41-113">Attributes</span></span>  
  
|<span data-ttu-id="dac41-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="dac41-114">Attribute</span></span>|<span data-ttu-id="dac41-115">Описание</span><span class="sxs-lookup"><span data-stu-id="dac41-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dac41-116">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="dac41-116">discoveryVersion</span></span>|<span data-ttu-id="dac41-117">Строка, указывающая одну из двух версий протокола WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="dac41-117">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="dac41-118">Допустимые значения: WSDiscovery11 и WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="dac41-118">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="dac41-119">Это значение имеет тип <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="dac41-119">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="dac41-120">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="dac41-120">maxAnnouncementDelay</span></span>|<span data-ttu-id="dac41-121">Значение «Timespan», указывающее максимальную задержку, в течение которой протокол Discovery не будет отправлять сообщение Hello.</span><span class="sxs-lookup"><span data-stu-id="dac41-121">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="dac41-122">Перед отправкой сообщения ожидают произвольное время в диапазоне от 0 до значения этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="dac41-122">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="dac41-123">Этот атрибут используется для назначения короткой произвольной задержки для предотвращения перегрузки сети, когда сеть становится недоступной, а все службы входят в сеть одновременно.</span><span class="sxs-lookup"><span data-stu-id="dac41-123">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="dac41-124">multicastAddress</span><span class="sxs-lookup"><span data-stu-id="dac41-124">multicastAddress</span></span>|<span data-ttu-id="dac41-125">URI, в котором указывается адрес многоадресной рассылки, используемый для отправки и получения сообщений об обнаружении.</span><span class="sxs-lookup"><span data-stu-id="dac41-125">A URI that specifies a multicast address to use for sending and receiving the discovery messages.</span></span> <span data-ttu-id="dac41-126">Значением по умолчанию является многопоточный адрес, который соответствует спецификации протокола.</span><span class="sxs-lookup"><span data-stu-id="dac41-126">The default value is the multicast address as conformant to the protocol specification.</span></span>|  
|<span data-ttu-id="dac41-127">имя</span><span class="sxs-lookup"><span data-stu-id="dac41-127">name</span></span>|<span data-ttu-id="dac41-128">Строка, указывающая имя конфигурации стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="dac41-128">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="dac41-129">Это имя используется в атрибуте `endpointConfiguration` конечной точки службы для связывания стандартной конечной точки с ее конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="dac41-129">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dac41-130">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dac41-130">Child Elements</span></span>  
  
|<span data-ttu-id="dac41-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="dac41-131">Element</span></span>|<span data-ttu-id="dac41-132">Описание</span><span class="sxs-lookup"><span data-stu-id="dac41-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dac41-133">\<Удптранспортсеттингс ></span><span class="sxs-lookup"><span data-stu-id="dac41-133">\<udpTransportSettings></span></span>](udptransportsettings.md)|<span data-ttu-id="dac41-134">Коллекция параметров, которые позволят настроить транспорт UDP для конечной точки UDP.</span><span class="sxs-lookup"><span data-stu-id="dac41-134">A collection of settings that allow you to configure UDP transport for the UDP endpoint.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dac41-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dac41-135">Parent Elements</span></span>  
  
|<span data-ttu-id="dac41-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="dac41-136">Element</span></span>|<span data-ttu-id="dac41-137">Описание</span><span class="sxs-lookup"><span data-stu-id="dac41-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dac41-138">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="dac41-138">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="dac41-139">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="dac41-139">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dac41-140">Пример</span><span class="sxs-lookup"><span data-stu-id="dac41-140">Example</span></span>  
 <span data-ttu-id="dac41-141">В следующем примере показано прослушивание клиентом сообщений с объявлением по многоадресному протоколу UDP с адресом многоадресной рассылки по умолчанию, а также с указанным адресом многоадресной рассылки UDP.</span><span class="sxs-lookup"><span data-stu-id="dac41-141">The following example demonstrates a client listening for announcement over a UDP multicast transport with default multicast address, and UDP multicast transport with specified multicast address.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dac41-142">См. также</span><span class="sxs-lookup"><span data-stu-id="dac41-142">See also</span></span>

- <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>
