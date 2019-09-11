---
title: <discoveryEndpoint>
ms.date: 03/30/2017
ms.assetid: fae2f48b-a635-4e4b-859d-a1432ac37e1c
ms.openlocfilehash: 32b14f8fb3235040a51455f2099a403c8312c699
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855393"
---
# <a name="discoveryendpoint"></a><span data-ttu-id="3415d-101">\<Дисковерендпоинт ></span><span class="sxs-lookup"><span data-stu-id="3415d-101">\<discoveryEndpoint></span></span>

<span data-ttu-id="3415d-102">Этот элемент конфигурации определяет стандартную конечную точку с фиксированным контрактом обнаружения.</span><span class="sxs-lookup"><span data-stu-id="3415d-102">This configuration element defines a standard endpoint with a fixed discovery contract.</span></span> <span data-ttu-id="3415d-103">При добавлении в конфигурацию службы указывает, где необходимо следить за появлением сообщений обнаружения.</span><span class="sxs-lookup"><span data-stu-id="3415d-103">When added to the service configuration, it specifies where to listen for the discovery messages.</span></span> <span data-ttu-id="3415d-104">При добавлении в клиентскую конфигурацию указывает, куда необходимо отправлять запросы обнаружения.</span><span class="sxs-lookup"><span data-stu-id="3415d-104">When added to the client configuration it specifies where to send the discovery queries.</span></span>  
  
<span data-ttu-id="3415d-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3415d-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3415d-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3415d-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3415d-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Стандардендпоинтс >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="3415d-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="3415d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Дисковерендпоинт >**</span><span class="sxs-lookup"><span data-stu-id="3415d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3415d-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3415d-109">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <discoveryEndpoint>
      <standardEndpoint discoveryMode="Adhoc/Managed"
                        discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxResponseDelay="Timespan"
                        name="String" />
    </discoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3415d-110">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="3415d-110">Attributes and elements</span></span>

<span data-ttu-id="3415d-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3415d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3415d-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3415d-112">Attributes</span></span>

| <span data-ttu-id="3415d-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3415d-113">Attribute</span></span>        | <span data-ttu-id="3415d-114">Описание</span><span class="sxs-lookup"><span data-stu-id="3415d-114">Description</span></span> |  
| ---------------- | ----------- |  
| <span data-ttu-id="3415d-115">discoveryMode</span><span class="sxs-lookup"><span data-stu-id="3415d-115">discoveryMode</span></span>    | <span data-ttu-id="3415d-116">Строка, указывающая режим протокола обнаружения.</span><span class="sxs-lookup"><span data-stu-id="3415d-116">A string that specifies the mode of discovery protocol.</span></span> <span data-ttu-id="3415d-117">Допустимые значения: "нерегламентированный" и "управляемый".</span><span class="sxs-lookup"><span data-stu-id="3415d-117">Valid values are "Adhoc" and "Managed".</span></span> <span data-ttu-id="3415d-118">В управляемом режиме протокол использует прокси-сервер обнаружения, который выступает в качестве репозитория обнаруживаемых служб.</span><span class="sxs-lookup"><span data-stu-id="3415d-118">In managed mode the protocol relies on a Discovery Proxy, which acts as a repository of Discoverable services.</span></span> <span data-ttu-id="3415d-119">Для режима Adhoc требуется, чтобы для поиска доступных служб протокол использовал многопоточный механизм UDP.</span><span class="sxs-lookup"><span data-stu-id="3415d-119">Adhoc mode requires the protocol to use UDP multicast mechanism to find available services.</span></span> <span data-ttu-id="3415d-120">Дополнительные сведения о свойстве см. в <xref:System.ServiceModel.Discovery.DiscoveryEndpoint.DiscoveryMode%2A>разделе.</span><span class="sxs-lookup"><span data-stu-id="3415d-120">For more information on the property, see <xref:System.ServiceModel.Discovery.DiscoveryEndpoint.DiscoveryMode%2A>.</span></span> |  
| <span data-ttu-id="3415d-121">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="3415d-121">discoveryVersion</span></span> | <span data-ttu-id="3415d-122">Строка, указывающая одну из двух версий протокола WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="3415d-122">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="3415d-123">Допустимые значения: WSDiscovery11 и WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="3415d-123">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="3415d-124">Это значение имеет тип <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="3415d-124">This value is of type <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span></span> |  
| <span data-ttu-id="3415d-125">maxResponseDelay</span><span class="sxs-lookup"><span data-stu-id="3415d-125">maxResponseDelay</span></span> | <span data-ttu-id="3415d-126">Значение «Timespan», указывающее максимальную задержку, в течение которой протокол Discovery будет ожидать перед отправкой определенных сообщений, например Probe Match или Resolve Match.</span><span class="sxs-lookup"><span data-stu-id="3415d-126">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending certain messages such as Probe Match or Resolve Match.</span></span><br /><br /> <span data-ttu-id="3415d-127">Если все сообщения ProbeMatches будут отправлены одновременно, может возникнуть перегрузка сети.</span><span class="sxs-lookup"><span data-stu-id="3415d-127">If all ProbeMatches are sent at the same time, a network storm may result.</span></span> <span data-ttu-id="3415d-128">Для ее предотвращения сообщения ProbeMatch отправляются с произвольной задержкой между сообщениями.</span><span class="sxs-lookup"><span data-stu-id="3415d-128">To prevent this from occurring, ProbeMatches are sent with a random delay between each ProbeMatch.</span></span> <span data-ttu-id="3415d-129">Произвольная задержка находится в диапазоне от 0 до значения, заданного этим атрибутом.</span><span class="sxs-lookup"><span data-stu-id="3415d-129">The random delay is in the range of 0 to the value set by this attribute.</span></span> <span data-ttu-id="3415d-130">Если этот атрибут имеет значение 0, сообщения ProbeMatch отправляются одно за другим без задержки.</span><span class="sxs-lookup"><span data-stu-id="3415d-130">If this attribute is set to 0, then the ProbeMatches messages are sent in a tight loop without any delay.</span></span> <span data-ttu-id="3415d-131">В противном случае сообщения ProbeMatch отправляются с определенной произвольной задержкой так, что общее время на отправку всех сообщений ProbeMatch не превышает значение maxResponseDelay.</span><span class="sxs-lookup"><span data-stu-id="3415d-131">Otherwise, the ProbeMatches messages are sent with some random delay such that the total time taken to send all ProbeMatches messages does not exceed the maxResponseDelay.</span></span> <span data-ttu-id="3415d-132">Это значение действительно только для служб и не используется клиентами.</span><span class="sxs-lookup"><span data-stu-id="3415d-132">This value is only relevant for services, it is not used by clients.</span></span> |  
| `name`           | <span data-ttu-id="3415d-133">Строка, указывающая имя конфигурации стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="3415d-133">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="3415d-134">Это имя используется в атрибуте `endpointConfiguration` конечной точки службы для связывания стандартной конечной точки с ее конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="3415d-134">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span> |  
  
### <a name="child-elements"></a><span data-ttu-id="3415d-135">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3415d-135">Child elements</span></span>

<span data-ttu-id="3415d-136">Нет.</span><span class="sxs-lookup"><span data-stu-id="3415d-136">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3415d-137">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3415d-137">Parent elements</span></span>

| <span data-ttu-id="3415d-138">Элемент</span><span class="sxs-lookup"><span data-stu-id="3415d-138">Element</span></span> | <span data-ttu-id="3415d-139">Описание</span><span class="sxs-lookup"><span data-stu-id="3415d-139">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="3415d-140">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="3415d-140">\<standardEndpoints></span></span>](standardendpoints.md) | <span data-ttu-id="3415d-141">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="3415d-141">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span> |  
  
## <a name="example"></a><span data-ttu-id="3415d-142">Пример</span><span class="sxs-lookup"><span data-stu-id="3415d-142">Example</span></span>

<span data-ttu-id="3415d-143">В следующем примере показано прослушивание службой сообщений об обнаружении по многоадресному протоколу транспорта peer net.</span><span class="sxs-lookup"><span data-stu-id="3415d-143">The following example demonstrates a service listening on the discovery messages over a peer net multicast transport.</span></span> <span data-ttu-id="3415d-144">В этом примере явно указана версия WS-Discovery April 2005.</span><span class="sxs-lookup"><span data-stu-id="3415d-144">The example explicitly specifies WS-Discovery April 2005 version.</span></span>  
  
<span data-ttu-id="3415d-145">Конфигурация стандартной конечной точки определена для каждой службы и не может совместно использоваться между службами.</span><span class="sxs-lookup"><span data-stu-id="3415d-145">The standard endpoint configuration is defined per service and cannot be shared across the service.</span></span> <span data-ttu-id="3415d-146">Если нужно использовать такую же конечную точку обнаружения для другой службы, следует добавить такую же конфигурацию в раздел этой службы.</span><span class="sxs-lookup"><span data-stu-id="3415d-146">If another service would like to have the same discovery endpoint, the same configuration needs to be added to that service’s section.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService" />
    <endpoint name="peerNetDiscovery"
              binding="peerTcpBinding"
              address="net.p2p://discoveryMesh/multicast"
              kind="discoveryEndpoint"
              endpointConfiguration="peerTcpDiscoveryEndpointConfiguration"
              bindingConfiguration="discoveryPeerTcpBindingConfig" />
  </service>
</services>
<standardEndpoints>
  <discoveryEndpoint>
    <standardEndpoint name="peerTcpDiscoveryEndpointConfiguration"
                      version="WSDiscoveryApril2005" />
  </discoveryEndpoint>
</standardEndpoints>
```  
  
## <a name="see-also"></a><span data-ttu-id="3415d-147">См. также</span><span class="sxs-lookup"><span data-stu-id="3415d-147">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>
