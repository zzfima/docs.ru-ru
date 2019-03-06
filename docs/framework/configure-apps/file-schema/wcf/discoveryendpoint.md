---
title: <discoveryEndpoint>
ms.date: 03/30/2017
ms.assetid: fae2f48b-a635-4e4b-859d-a1432ac37e1c
ms.openlocfilehash: d1a3371872f5587a682b8242c29b71808508ca3d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374301"
---
# <a name="discoveryendpoint"></a><span data-ttu-id="9cbee-101">\<discoveryEndpoint ></span><span class="sxs-lookup"><span data-stu-id="9cbee-101">\<discoveryEndpoint></span></span>

<span data-ttu-id="9cbee-102">Этот элемент конфигурации определяет стандартную конечную точку с фиксированным контрактом обнаружения.</span><span class="sxs-lookup"><span data-stu-id="9cbee-102">This configuration element defines a standard endpoint with a fixed discovery contract.</span></span> <span data-ttu-id="9cbee-103">При добавлении в конфигурацию службы указывает, где необходимо следить за появлением сообщений обнаружения.</span><span class="sxs-lookup"><span data-stu-id="9cbee-103">When added to the service configuration, it specifies where to listen for the discovery messages.</span></span> <span data-ttu-id="9cbee-104">При добавлении в клиентскую конфигурацию указывает, куда необходимо отправлять запросы обнаружения.</span><span class="sxs-lookup"><span data-stu-id="9cbee-104">When added to the client configuration it specifies where to send the discovery queries.</span></span>  
  
<span data-ttu-id="9cbee-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9cbee-105">\<system.serviceModel></span></span>  
<span data-ttu-id="9cbee-106">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="9cbee-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cbee-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9cbee-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9cbee-108">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="9cbee-108">Attributes and elements</span></span>

<span data-ttu-id="9cbee-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9cbee-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9cbee-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9cbee-110">Attributes</span></span>

| <span data-ttu-id="9cbee-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9cbee-111">Attribute</span></span>        | <span data-ttu-id="9cbee-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9cbee-112">Description</span></span> |  
| ---------------- | ----------- |  
| <span data-ttu-id="9cbee-113">discoveryMode</span><span class="sxs-lookup"><span data-stu-id="9cbee-113">discoveryMode</span></span>    | <span data-ttu-id="9cbee-114">Строка, указывающая режим протокола обнаружения.</span><span class="sxs-lookup"><span data-stu-id="9cbee-114">A string that specifies the mode of discovery protocol.</span></span> <span data-ttu-id="9cbee-115">Допустимые значения: «Adhoc» и «Managed».</span><span class="sxs-lookup"><span data-stu-id="9cbee-115">Valid values are "Adhoc" and "Managed".</span></span> <span data-ttu-id="9cbee-116">В управляемом режиме протокол использует прокси-сервер обнаружения, который выступает в качестве репозитория обнаруживаемых служб.</span><span class="sxs-lookup"><span data-stu-id="9cbee-116">In managed mode the protocol relies on a Discovery Proxy, which acts as a repository of Discoverable services.</span></span> <span data-ttu-id="9cbee-117">Для режима Adhoc требуется, чтобы для поиска доступных служб протокол использовал многопоточный механизм UDP.</span><span class="sxs-lookup"><span data-stu-id="9cbee-117">Adhoc mode requires the protocol to use UDP multicast mechanism to find available services.</span></span> <span data-ttu-id="9cbee-118">Дополнительные сведения о свойстве см. в разделе <xref:System.ServiceModel.Discovery.DiscoveryEndpoint.DiscoveryMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="9cbee-118">For more information on the property, see <xref:System.ServiceModel.Discovery.DiscoveryEndpoint.DiscoveryMode%2A>.</span></span> |  
| <span data-ttu-id="9cbee-119">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="9cbee-119">discoveryVersion</span></span> | <span data-ttu-id="9cbee-120">Строка, указывающая одну из двух версий протокола WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="9cbee-120">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="9cbee-121">Допустимые значения: WSDiscovery11 и WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="9cbee-121">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="9cbee-122">Это значение имеет тип <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="9cbee-122">This value is of type <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span></span> |  
| <span data-ttu-id="9cbee-123">maxResponseDelay</span><span class="sxs-lookup"><span data-stu-id="9cbee-123">maxResponseDelay</span></span> | <span data-ttu-id="9cbee-124">Значение «Timespan», указывающее максимальную задержку, в течение которой протокол Discovery будет ожидать перед отправкой определенных сообщений, например Probe Match или Resolve Match.</span><span class="sxs-lookup"><span data-stu-id="9cbee-124">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending certain messages such as Probe Match or Resolve Match.</span></span><br /><br /> <span data-ttu-id="9cbee-125">Если все сообщения ProbeMatches будут отправлены одновременно, может возникнуть перегрузка сети.</span><span class="sxs-lookup"><span data-stu-id="9cbee-125">If all ProbeMatches are sent at the same time, a network storm may result.</span></span> <span data-ttu-id="9cbee-126">Для ее предотвращения сообщения ProbeMatch отправляются с произвольной задержкой между сообщениями.</span><span class="sxs-lookup"><span data-stu-id="9cbee-126">To prevent this from occurring, ProbeMatches are sent with a random delay between each ProbeMatch.</span></span> <span data-ttu-id="9cbee-127">Произвольная задержка находится в диапазоне от 0 до значения, заданного этим атрибутом.</span><span class="sxs-lookup"><span data-stu-id="9cbee-127">The random delay is in the range of 0 to the value set by this attribute.</span></span> <span data-ttu-id="9cbee-128">Если этот атрибут имеет значение 0, сообщения ProbeMatch отправляются одно за другим без задержки.</span><span class="sxs-lookup"><span data-stu-id="9cbee-128">If this attribute is set to 0, then the ProbeMatches messages are sent in a tight loop without any delay.</span></span> <span data-ttu-id="9cbee-129">В противном случае сообщения ProbeMatch отправляются с определенной произвольной задержкой так, что общее время на отправку всех сообщений ProbeMatch не превышает значение maxResponseDelay.</span><span class="sxs-lookup"><span data-stu-id="9cbee-129">Otherwise, the ProbeMatches messages are sent with some random delay such that the total time taken to send all ProbeMatches messages does not exceed the maxResponseDelay.</span></span> <span data-ttu-id="9cbee-130">Это значение действительно только для служб и не используется клиентами.</span><span class="sxs-lookup"><span data-stu-id="9cbee-130">This value is only relevant for services, it is not used by clients.</span></span> |  
| `name`           | <span data-ttu-id="9cbee-131">Строка, указывающая имя конфигурации стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="9cbee-131">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="9cbee-132">Это имя используется в атрибуте `endpointConfiguration` конечной точки службы для связывания стандартной конечной точки с ее конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="9cbee-132">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span> |  
  
### <a name="child-elements"></a><span data-ttu-id="9cbee-133">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9cbee-133">Child elements</span></span>

<span data-ttu-id="9cbee-134">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9cbee-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9cbee-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9cbee-135">Parent elements</span></span>

| <span data-ttu-id="9cbee-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="9cbee-136">Element</span></span> | <span data-ttu-id="9cbee-137">Описание:</span><span class="sxs-lookup"><span data-stu-id="9cbee-137">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="9cbee-138">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="9cbee-138">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md) | <span data-ttu-id="9cbee-139">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="9cbee-139">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span> |  
  
## <a name="example"></a><span data-ttu-id="9cbee-140">Пример</span><span class="sxs-lookup"><span data-stu-id="9cbee-140">Example</span></span>

<span data-ttu-id="9cbee-141">В следующем примере показано прослушивание службой сообщений об обнаружении по многоадресному протоколу транспорта peer net.</span><span class="sxs-lookup"><span data-stu-id="9cbee-141">The following example demonstrates a service listening on the discovery messages over a peer net multicast transport.</span></span> <span data-ttu-id="9cbee-142">В этом примере явно указана версия WS-Discovery April 2005.</span><span class="sxs-lookup"><span data-stu-id="9cbee-142">The example explicitly specifies WS-Discovery April 2005 version.</span></span>  
  
<span data-ttu-id="9cbee-143">Конфигурация стандартной конечной точки определена для каждой службы и не может совместно использоваться между службами.</span><span class="sxs-lookup"><span data-stu-id="9cbee-143">The standard endpoint configuration is defined per service and cannot be shared across the service.</span></span> <span data-ttu-id="9cbee-144">Если нужно использовать такую же конечную точку обнаружения для другой службы, следует добавить такую же конфигурацию в раздел этой службы.</span><span class="sxs-lookup"><span data-stu-id="9cbee-144">If another service would like to have the same discovery endpoint, the same configuration needs to be added to that service’s section.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9cbee-145">См. также</span><span class="sxs-lookup"><span data-stu-id="9cbee-145">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>
