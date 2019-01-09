---
title: '&lt;DiscoveryEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: fae2f48b-a635-4e4b-859d-a1432ac37e1c
ms.openlocfilehash: ab00a80904cdcd2844a44c154edb2e424633427b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145384"
---
# <a name="ltdiscoveryendpointgt"></a><span data-ttu-id="cd9a5-102">&lt;DiscoveryEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="cd9a5-102">&lt;discoveryEndpoint&gt;</span></span>

<span data-ttu-id="cd9a5-103">Этот элемент конфигурации определяет стандартную конечную точку с фиксированным контрактом обнаружения.</span><span class="sxs-lookup"><span data-stu-id="cd9a5-103">This configuration element defines a standard endpoint with a fixed discovery contract.</span></span> <span data-ttu-id="cd9a5-104">При добавлении в конфигурацию службы указывает, где необходимо следить за появлением сообщений обнаружения.</span><span class="sxs-lookup"><span data-stu-id="cd9a5-104">When added to the service configuration, it specifies where to listen for the discovery messages.</span></span> <span data-ttu-id="cd9a5-105">При добавлении в клиентскую конфигурацию указывает, куда необходимо отправлять запросы обнаружения.</span><span class="sxs-lookup"><span data-stu-id="cd9a5-105">When added to the client configuration it specifies where to send the discovery queries.</span></span>  
  
<span data-ttu-id="cd9a5-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="cd9a5-106">\<system.serviceModel></span></span>  
<span data-ttu-id="cd9a5-107">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="cd9a5-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd9a5-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cd9a5-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd9a5-109">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="cd9a5-109">Attributes and elements</span></span>

<span data-ttu-id="cd9a5-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cd9a5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd9a5-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cd9a5-111">Attributes</span></span>

| <span data-ttu-id="cd9a5-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="cd9a5-112">Attribute</span></span>        | <span data-ttu-id="cd9a5-113">Описание</span><span class="sxs-lookup"><span data-stu-id="cd9a5-113">Description</span></span> |  
| ---------------- | ----------- |  
| <span data-ttu-id="cd9a5-114">discoveryMode</span><span class="sxs-lookup"><span data-stu-id="cd9a5-114">discoveryMode</span></span>    | <span data-ttu-id="cd9a5-115">Строка, указывающая режим протокола обнаружения.</span><span class="sxs-lookup"><span data-stu-id="cd9a5-115">A string that specifies the mode of discovery protocol.</span></span> <span data-ttu-id="cd9a5-116">Допустимые значения: «Adhoc» и «Managed».</span><span class="sxs-lookup"><span data-stu-id="cd9a5-116">Valid values are "Adhoc" and "Managed".</span></span> <span data-ttu-id="cd9a5-117">В управляемом режиме протокол использует прокси-сервер обнаружения, который выступает в качестве репозитория обнаруживаемых служб.</span><span class="sxs-lookup"><span data-stu-id="cd9a5-117">In managed mode the protocol relies on a Discovery Proxy, which acts as a repository of Discoverable services.</span></span> <span data-ttu-id="cd9a5-118">Для режима Adhoc требуется, чтобы для поиска доступных служб протокол использовал многопоточный механизм UDP.</span><span class="sxs-lookup"><span data-stu-id="cd9a5-118">Adhoc mode requires the protocol to use UDP multicast mechanism to find available services.</span></span> <span data-ttu-id="cd9a5-119">Дополнительные сведения о свойстве см. в разделе <xref:System.ServiceModel.Discovery.DiscoveryEndpoint.DiscoveryMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="cd9a5-119">For more information on the property, see <xref:System.ServiceModel.Discovery.DiscoveryEndpoint.DiscoveryMode%2A>.</span></span> |  
| <span data-ttu-id="cd9a5-120">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="cd9a5-120">discoveryVersion</span></span> | <span data-ttu-id="cd9a5-121">Строка, указывающая одну из двух версий протокола WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="cd9a5-121">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="cd9a5-122">Допустимые значения: WSDiscovery11 и WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="cd9a5-122">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="cd9a5-123">Это значение имеет тип <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="cd9a5-123">This value is of type <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span></span> |  
| <span data-ttu-id="cd9a5-124">maxResponseDelay</span><span class="sxs-lookup"><span data-stu-id="cd9a5-124">maxResponseDelay</span></span> | <span data-ttu-id="cd9a5-125">Значение «Timespan», указывающее максимальную задержку, в течение которой протокол Discovery будет ожидать перед отправкой определенных сообщений, например Probe Match или Resolve Match.</span><span class="sxs-lookup"><span data-stu-id="cd9a5-125">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending certain messages such as Probe Match or Resolve Match.</span></span><br /><br /> <span data-ttu-id="cd9a5-126">Если все сообщения ProbeMatches будут отправлены одновременно, может возникнуть перегрузка сети.</span><span class="sxs-lookup"><span data-stu-id="cd9a5-126">If all ProbeMatches are sent at the same time, a network storm may result.</span></span> <span data-ttu-id="cd9a5-127">Для ее предотвращения сообщения ProbeMatch отправляются с произвольной задержкой между сообщениями.</span><span class="sxs-lookup"><span data-stu-id="cd9a5-127">To prevent this from occurring, ProbeMatches are sent with a random delay between each ProbeMatch.</span></span> <span data-ttu-id="cd9a5-128">Произвольная задержка находится в диапазоне от 0 до значения, заданного этим атрибутом.</span><span class="sxs-lookup"><span data-stu-id="cd9a5-128">The random delay is in the range of 0 to the value set by this attribute.</span></span> <span data-ttu-id="cd9a5-129">Если этот атрибут имеет значение 0, сообщения ProbeMatch отправляются одно за другим без задержки.</span><span class="sxs-lookup"><span data-stu-id="cd9a5-129">If this attribute is set to 0, then the ProbeMatches messages are sent in a tight loop without any delay.</span></span> <span data-ttu-id="cd9a5-130">В противном случае сообщения ProbeMatch отправляются с определенной произвольной задержкой так, что общее время на отправку всех сообщений ProbeMatch не превышает значение maxResponseDelay.</span><span class="sxs-lookup"><span data-stu-id="cd9a5-130">Otherwise, the ProbeMatches messages are sent with some random delay such that the total time taken to send all ProbeMatches messages does not exceed the maxResponseDelay.</span></span> <span data-ttu-id="cd9a5-131">Это значение действительно только для служб и не используется клиентами.</span><span class="sxs-lookup"><span data-stu-id="cd9a5-131">This value is only relevant for services, it is not used by clients.</span></span> |  
| `name`           | <span data-ttu-id="cd9a5-132">Строка, указывающая имя конфигурации стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="cd9a5-132">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="cd9a5-133">Это имя используется в атрибуте `endpointConfiguration` конечной точки службы для связывания стандартной конечной точки с ее конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="cd9a5-133">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span> |  
  
### <a name="child-elements"></a><span data-ttu-id="cd9a5-134">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cd9a5-134">Child elements</span></span>

<span data-ttu-id="cd9a5-135">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="cd9a5-135">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cd9a5-136">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cd9a5-136">Parent elements</span></span>

| <span data-ttu-id="cd9a5-137">Элемент</span><span class="sxs-lookup"><span data-stu-id="cd9a5-137">Element</span></span> | <span data-ttu-id="cd9a5-138">Описание:</span><span class="sxs-lookup"><span data-stu-id="cd9a5-138">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="cd9a5-139">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="cd9a5-139">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md) | <span data-ttu-id="cd9a5-140">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="cd9a5-140">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span> |  
  
## <a name="example"></a><span data-ttu-id="cd9a5-141">Пример</span><span class="sxs-lookup"><span data-stu-id="cd9a5-141">Example</span></span>

<span data-ttu-id="cd9a5-142">В следующем примере показано прослушивание службой сообщений об обнаружении по многоадресному протоколу транспорта peer net.</span><span class="sxs-lookup"><span data-stu-id="cd9a5-142">The following example demonstrates a service listening on the discovery messages over a peer net multicast transport.</span></span> <span data-ttu-id="cd9a5-143">В этом примере явно указана версия WS-Discovery April 2005.</span><span class="sxs-lookup"><span data-stu-id="cd9a5-143">The example explicitly specifies WS-Discovery April 2005 version.</span></span>  
  
<span data-ttu-id="cd9a5-144">Конфигурация стандартной конечной точки определена для каждой службы и не может совместно использоваться между службами.</span><span class="sxs-lookup"><span data-stu-id="cd9a5-144">The standard endpoint configuration is defined per service and cannot be shared across the service.</span></span> <span data-ttu-id="cd9a5-145">Если нужно использовать такую же конечную точку обнаружения для другой службы, следует добавить такую же конфигурацию в раздел этой службы.</span><span class="sxs-lookup"><span data-stu-id="cd9a5-145">If another service would like to have the same discovery endpoint, the same configuration needs to be added to that service’s section.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cd9a5-146">См. также</span><span class="sxs-lookup"><span data-stu-id="cd9a5-146">See also</span></span>

<xref:System.ServiceModel.Discovery.DiscoveryEndpoint>
