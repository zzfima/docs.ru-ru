---
title: <udpDiscoveryEndpoint>
ms.date: 03/30/2017
ms.assetid: 1f485329-2771-43bc-88de-df8f2faa3bb7
ms.openlocfilehash: e6e567e8a657b4c1683ae4abfb14f96a0f272e4a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934579"
---
# <a name="udpdiscoveryendpoint"></a><span data-ttu-id="96a79-101">\<Удпдисковерендпоинт ></span><span class="sxs-lookup"><span data-stu-id="96a79-101">\<udpDiscoveryEndpoint></span></span>
<span data-ttu-id="96a79-102">Этот элемент конфигурации указывает стандартную конечную точку, которая стандартно используется для операций обнаружения через привязку для многоадресной рассылки UDP.</span><span class="sxs-lookup"><span data-stu-id="96a79-102">This configuration element defines a standard endpoint that is pre-configured for discovery operations over a UDP multicast binding.</span></span> <span data-ttu-id="96a79-103">Эта конечная точка имеет фиксированный контракт и поддерживает две версии протокола WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="96a79-103">This endpoint has a fixed contract and supports two WS-Discovery protocol versions.</span></span> <span data-ttu-id="96a79-104">Кроме того, она имеет фиксированную привязку UDP и значение адреса по умолчанию, как определено в спецификациях WS-Discovery (WS-Discovery от апреля 2005 или WS-Discovery версии 1.1).</span><span class="sxs-lookup"><span data-stu-id="96a79-104">In addition, it has a fixed UDP binding and a default address as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery V1.1).</span></span>  
  
 <span data-ttu-id="96a79-105">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="96a79-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="96a79-106">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="96a79-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96a79-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="96a79-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <discoveryEndpoint>
      <standardEndpoint discoveryMode="Adhoc/Managed"
                        discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxResponseDelay="Timespan"
                        multicastAddress="Uri"
                        name="String" />
    </discoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="96a79-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="96a79-108">Attributes and Elements</span></span>  
 <span data-ttu-id="96a79-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="96a79-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="96a79-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="96a79-110">Attributes</span></span>  
  
|<span data-ttu-id="96a79-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="96a79-111">Attribute</span></span>|<span data-ttu-id="96a79-112">Описание</span><span class="sxs-lookup"><span data-stu-id="96a79-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="96a79-113">discoveryMode</span><span class="sxs-lookup"><span data-stu-id="96a79-113">discoveryMode</span></span>|<span data-ttu-id="96a79-114">Строка, указывающая режим протокола обнаружения.</span><span class="sxs-lookup"><span data-stu-id="96a79-114">A string that specifies the mode of discovery protocol.</span></span> <span data-ttu-id="96a79-115">Допустимые значения: "нерегламентированный" и "управляемый".</span><span class="sxs-lookup"><span data-stu-id="96a79-115">Valid values are "Adhoc" and "Managed".</span></span> <span data-ttu-id="96a79-116">В управляемом режиме протокол использует прокси-сервер обнаружения, который выступает в качестве репозитория обнаруживаемых служб.</span><span class="sxs-lookup"><span data-stu-id="96a79-116">In managed mode the protocol relies on a Discovery Proxy, which acts as a repository of Discoverable services.</span></span> <span data-ttu-id="96a79-117">Для режима Adhoc требуется, чтобы для поиска доступных служб протокол использовал многопоточный механизм UDP.</span><span class="sxs-lookup"><span data-stu-id="96a79-117">Adhoc mode requires the protocol to use UDP multicast mechanism to find available services.</span></span> <span data-ttu-id="96a79-118">Это значение имеет тип <xref:System.ServiceModel.Discovery.ServiceDiscoveryMode>.</span><span class="sxs-lookup"><span data-stu-id="96a79-118">This value is of type <xref:System.ServiceModel.Discovery.ServiceDiscoveryMode>.</span></span>|  
|<span data-ttu-id="96a79-119">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="96a79-119">discoveryVersion</span></span>|<span data-ttu-id="96a79-120">Строка, указывающая одну из двух версий протокола WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="96a79-120">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="96a79-121">Допустимые значения: WSDiscovery11 и WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="96a79-121">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="96a79-122">Это значение имеет тип <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="96a79-122">This value is of type <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="96a79-123">maxResponseDelay</span><span class="sxs-lookup"><span data-stu-id="96a79-123">maxResponseDelay</span></span>|<span data-ttu-id="96a79-124">Значение «Timespan», указывающее максимальную задержку, в течение которой протокол Discovery будет ожидать перед отправкой определенных сообщений, например Probe Match или Resolve Match.</span><span class="sxs-lookup"><span data-stu-id="96a79-124">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending certain messages such as Probe Match or Resolve Match.</span></span><br /><br /> <span data-ttu-id="96a79-125">Если все сообщения ProbeMatches будут отправлены одновременно, может возникнуть перегрузка сети.</span><span class="sxs-lookup"><span data-stu-id="96a79-125">If all ProbeMatches are sent at the same time, a network storm may result.</span></span> <span data-ttu-id="96a79-126">Для ее предотвращения сообщения ProbeMatch отправляются с произвольной задержкой между сообщениями.</span><span class="sxs-lookup"><span data-stu-id="96a79-126">To prevent this from occurring, ProbeMatches are sent with a random delay between each ProbeMatch.</span></span> <span data-ttu-id="96a79-127">Произвольная задержка находится в диапазоне от 0 до значения, заданного этим атрибутом.</span><span class="sxs-lookup"><span data-stu-id="96a79-127">The random delay is in the range of 0 to the value set by this attribute.</span></span> <span data-ttu-id="96a79-128">Если этот атрибут имеет значение 0, сообщения ProbeMatch отправляются одно за другим без задержки.</span><span class="sxs-lookup"><span data-stu-id="96a79-128">If this attribute is set to 0, then the ProbeMatches messages are sent in a tight loop without any delay.</span></span> <span data-ttu-id="96a79-129">В противном случае сообщения ProbeMatch отправляются с определенной произвольной задержкой так, что общее время на отправку всех сообщений ProbeMatch не превышает значение maxResponseDelay.</span><span class="sxs-lookup"><span data-stu-id="96a79-129">Otherwise, the ProbeMatches messages are sent with some random delay such that the total time taken to send all ProbeMatches messages does not exceed the maxResponseDelay.</span></span> <span data-ttu-id="96a79-130">Это значение действительно только для служб и не используется клиентами.</span><span class="sxs-lookup"><span data-stu-id="96a79-130">This value is only relevant for services, it is not used by clients.</span></span>|  
|<span data-ttu-id="96a79-131">multicastAddress</span><span class="sxs-lookup"><span data-stu-id="96a79-131">multicastAddress</span></span>|<span data-ttu-id="96a79-132">URI, в котором указывается адрес многоадресной рассылки, используемый для отправки и получения сообщений об обнаружении.</span><span class="sxs-lookup"><span data-stu-id="96a79-132">A Uri that specifies a multicast address to use for sending and receiving the discovery messages.</span></span> <span data-ttu-id="96a79-133">Значением по умолчанию является многопоточный адрес, который соответствует спецификации протокола.</span><span class="sxs-lookup"><span data-stu-id="96a79-133">The default value is the multicast address as conformant to the protocol specification.</span></span>|  
|`name`|<span data-ttu-id="96a79-134">Строка, указывающая имя конфигурации стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="96a79-134">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="96a79-135">Это имя используется в атрибуте `endpointConfiguration` конечной точки службы для связывания стандартной конечной точки с ее конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="96a79-135">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="96a79-136">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="96a79-136">Child Elements</span></span>  
  
|<span data-ttu-id="96a79-137">Элемент</span><span class="sxs-lookup"><span data-stu-id="96a79-137">Element</span></span>|<span data-ttu-id="96a79-138">Описание</span><span class="sxs-lookup"><span data-stu-id="96a79-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="96a79-139">\<Удптранспортсеттингс ></span><span class="sxs-lookup"><span data-stu-id="96a79-139">\<udpTransportSettings></span></span>](udptransportsettings.md)|<span data-ttu-id="96a79-140">Коллекция параметров, которые позволят настроить транспорт UDP для конечной точки UDP.</span><span class="sxs-lookup"><span data-stu-id="96a79-140">A collection of settings that allow you to configure UDP transport for the UDP endpoint.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="96a79-141">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="96a79-141">Parent Elements</span></span>  
  
|<span data-ttu-id="96a79-142">Элемент</span><span class="sxs-lookup"><span data-stu-id="96a79-142">Element</span></span>|<span data-ttu-id="96a79-143">Описание</span><span class="sxs-lookup"><span data-stu-id="96a79-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="96a79-144">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="96a79-144">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="96a79-145">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="96a79-145">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="96a79-146">Пример</span><span class="sxs-lookup"><span data-stu-id="96a79-146">Example</span></span>  
 <span data-ttu-id="96a79-147">В следующем примере показано прослушивание сообщений об обнаружении через многоадресный протокол UDP.</span><span class="sxs-lookup"><span data-stu-id="96a79-147">The following example demonstrates a service listening for discovery messages over a UDP multicast transport.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService" />
    <endpoint name="DiscoveryEndpoint"
              kind="udpDiscoveryEndpoint" />
  </service>
  <standardEndpoints>
    <udpDiscoveryEndpoint>
      <standardEndpoint name="DiscoveryEndpoint"
                        version="WSDiscoveryApril2005" />
    </udpDiscoveryEndpoint>
  </standardEndpoints>
</services>
```  
  
## <a name="see-also"></a><span data-ttu-id="96a79-148">См. также</span><span class="sxs-lookup"><span data-stu-id="96a79-148">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>
