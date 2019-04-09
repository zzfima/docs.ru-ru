---
title: <announcementEndpoint>
ms.date: 03/30/2017
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
ms.openlocfilehash: 4f3cf2748acc75b0ec83732664c5f97114f3663a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195128"
---
# <a name="announcementendpoint"></a><span data-ttu-id="034df-101">\<announcementEndpoint></span><span class="sxs-lookup"><span data-stu-id="034df-101">\<announcementEndpoint></span></span>
<span data-ttu-id="034df-102">Этот элемент конфигурации определяет стандартную конечную точку с фиксированным контрактом объявления.</span><span class="sxs-lookup"><span data-stu-id="034df-102">This configuration element defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="034df-103">Служба может также объявлять свою доступность путем отправки сообщения в режимах «в сети» и «не в сети» соответственно при открытии и закрытии службы.</span><span class="sxs-lookup"><span data-stu-id="034df-103">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="034df-104">Служба Windows Communication Foundation (WCF) указывает конечные точки объявления в [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) элемент и использует AnnouncementClient для выполнения объявлений.</span><span class="sxs-lookup"><span data-stu-id="034df-104">A Windows Communication Foundation (WCF) service specifies the announcement endpoints in the [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="034df-105">Клиент, ожидающий объявления от другой службы прослушивания фактически выступает в качестве службы WCF; Таким образом вы должны настроить конечные точки объявления для этого клиента в [ \<services >](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) раздел.</span><span class="sxs-lookup"><span data-stu-id="034df-105">A client wishing to listen for the announcement from other service is actually acting as a WCF service; thus you have to configure the announcement endpoints for that client in the [\<services>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) section.</span></span>  
  
<span data-ttu-id="034df-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="034df-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="034df-107">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="034df-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="034df-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="034df-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <announcementEndpoint>
      <standardEndpoint discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxAnnouncementDelay="Timespan"
                        name="String" />
    </announcementEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="034df-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="034df-109">Attributes and Elements</span></span>  
 <span data-ttu-id="034df-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="034df-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="034df-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="034df-111">Attributes</span></span>  
  
|<span data-ttu-id="034df-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="034df-112">Attribute</span></span>|<span data-ttu-id="034df-113">Описание</span><span class="sxs-lookup"><span data-stu-id="034df-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="034df-114">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="034df-114">discoveryVersion</span></span>|<span data-ttu-id="034df-115">Строка, указывающая одну из двух версий протокола WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="034df-115">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="034df-116">Допустимые значения: WSDiscovery11 и WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="034df-116">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="034df-117">Это значение имеет тип <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="034df-117">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="034df-118">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="034df-118">maxAnnouncementDelay</span></span>|<span data-ttu-id="034df-119">Значение «Timespan», указывающее максимальную задержку, в течение которой протокол Discovery не будет отправлять сообщение Hello.</span><span class="sxs-lookup"><span data-stu-id="034df-119">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="034df-120">Перед отправкой сообщения ожидают произвольное время в диапазоне от 0 до значения этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="034df-120">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="034df-121">Этот атрибут используется для назначения короткой произвольной задержки для предотвращения перегрузки сети, когда сеть становится недоступной, а все службы входят в сеть одновременно.</span><span class="sxs-lookup"><span data-stu-id="034df-121">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="034df-122">имя</span><span class="sxs-lookup"><span data-stu-id="034df-122">name</span></span>|<span data-ttu-id="034df-123">Строка, указывающая имя конфигурации стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="034df-123">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="034df-124">Это имя используется в атрибуте `endpointConfiguration` конечной точки службы для связывания стандартной конечной точки с ее конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="034df-124">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="034df-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="034df-125">Child Elements</span></span>  
 <span data-ttu-id="034df-126">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="034df-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="034df-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="034df-127">Parent Elements</span></span>  
  
|<span data-ttu-id="034df-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="034df-128">Element</span></span>|<span data-ttu-id="034df-129">Описание</span><span class="sxs-lookup"><span data-stu-id="034df-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="034df-130">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="034df-130">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="034df-131">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="034df-131">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="034df-132">Пример</span><span class="sxs-lookup"><span data-stu-id="034df-132">Example</span></span>  
 <span data-ttu-id="034df-133">В следующем примере показано прослушивание клиентом сообщений с объявлениями по протоколам http и peernet.</span><span class="sxs-lookup"><span data-stu-id="034df-133">The following example demonstrates a client listening for announcements messages over http and peernet.</span></span>  
  
```xml  
<services>
  <service name="ServiceAnnouncementListener">
    <endpoint name="httpAnnouncementEndpoint"
              kind="announcementEndpoint"
              binding="basicHttpBinding"
              address="announcements" />
    <endpoint name="peerNetAnnouncementEndpoint"
              kind="announcementEndpoint"
              binding="peerTcpBinding"
              address="net.p2p://discoveryMesh/multicast"
              bindingConfiguration="discoveryPeerTcpBindingConfig" />
  ...
  </service>
</services>

<standardEndpoints>
  <announcementEndpoint>
    <standardEndpoint name="httpAnnouncementEndpoint"
                      version="WSDiscoveryApril2005" />
    <standardEndpoint name="peerNetAnnouncementEndpoint"
                      version="WSDiscoveryApril2005" />
  </announcementEndpoint>
</standardEndpoints>
```  
  
## <a name="see-also"></a><span data-ttu-id="034df-134">См. также</span><span class="sxs-lookup"><span data-stu-id="034df-134">See also</span></span>

- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
