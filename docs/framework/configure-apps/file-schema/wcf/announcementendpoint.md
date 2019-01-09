---
title: '&lt;AnnouncementEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
ms.openlocfilehash: fe278da539af59a32edf5a626461dbec0ba3887d
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151648"
---
# <a name="ltannouncementendpointgt"></a><span data-ttu-id="12f23-102">&lt;AnnouncementEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="12f23-102">&lt;announcementEndpoint&gt;</span></span>
<span data-ttu-id="12f23-103">Этот элемент конфигурации определяет стандартную конечную точку с фиксированным контрактом объявления.</span><span class="sxs-lookup"><span data-stu-id="12f23-103">This configuration element defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="12f23-104">Служба может также объявлять свою доступность путем отправки сообщения в режимах «в сети» и «не в сети» соответственно при открытии и закрытии службы.</span><span class="sxs-lookup"><span data-stu-id="12f23-104">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="12f23-105">Служба Windows Communication Foundation (WCF) указывает конечные точки объявления в [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) элемент и использует AnnouncementClient для выполнения объявлений.</span><span class="sxs-lookup"><span data-stu-id="12f23-105">A Windows Communication Foundation (WCF) service specifies the announcement endpoints in the [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="12f23-106">Клиент, ожидающий объявления от другой службы прослушивания фактически выступает в качестве службы WCF; Таким образом вы должны настроить конечные точки объявления для этого клиента в [ \<services >](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) раздел.</span><span class="sxs-lookup"><span data-stu-id="12f23-106">A client wishing to listen for the announcement from other service is actually acting as a WCF service; thus you have to configure the announcement endpoints for that client in the [\<services>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) section.</span></span>  
  
<span data-ttu-id="12f23-107">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="12f23-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="12f23-108">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="12f23-108">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12f23-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="12f23-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="12f23-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="12f23-110">Attributes and Elements</span></span>  
 <span data-ttu-id="12f23-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="12f23-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="12f23-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="12f23-112">Attributes</span></span>  
  
|<span data-ttu-id="12f23-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="12f23-113">Attribute</span></span>|<span data-ttu-id="12f23-114">Описание</span><span class="sxs-lookup"><span data-stu-id="12f23-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="12f23-115">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="12f23-115">discoveryVersion</span></span>|<span data-ttu-id="12f23-116">Строка, указывающая одну из двух версий протокола WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="12f23-116">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="12f23-117">Допустимые значения: WSDiscovery11 и WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="12f23-117">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="12f23-118">Это значение имеет тип <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="12f23-118">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="12f23-119">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="12f23-119">maxAnnouncementDelay</span></span>|<span data-ttu-id="12f23-120">Значение «Timespan», указывающее максимальную задержку, в течение которой протокол Discovery не будет отправлять сообщение Hello.</span><span class="sxs-lookup"><span data-stu-id="12f23-120">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="12f23-121">Перед отправкой сообщения ожидают произвольное время в диапазоне от 0 до значения этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="12f23-121">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="12f23-122">Этот атрибут используется для назначения короткой произвольной задержки для предотвращения перегрузки сети, когда сеть становится недоступной, а все службы входят в сеть одновременно.</span><span class="sxs-lookup"><span data-stu-id="12f23-122">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="12f23-123">имя</span><span class="sxs-lookup"><span data-stu-id="12f23-123">name</span></span>|<span data-ttu-id="12f23-124">Строка, указывающая имя конфигурации стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="12f23-124">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="12f23-125">Это имя используется в атрибуте `endpointConfiguration` конечной точки службы для связывания стандартной конечной точки с ее конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="12f23-125">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="12f23-126">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="12f23-126">Child Elements</span></span>  
 <span data-ttu-id="12f23-127">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="12f23-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="12f23-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="12f23-128">Parent Elements</span></span>  
  
|<span data-ttu-id="12f23-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="12f23-129">Element</span></span>|<span data-ttu-id="12f23-130">Описание:</span><span class="sxs-lookup"><span data-stu-id="12f23-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12f23-131">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="12f23-131">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="12f23-132">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="12f23-132">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="12f23-133">Пример</span><span class="sxs-lookup"><span data-stu-id="12f23-133">Example</span></span>  
 <span data-ttu-id="12f23-134">В следующем примере показано прослушивание клиентом сообщений с объявлениями по протоколам http и peernet.</span><span class="sxs-lookup"><span data-stu-id="12f23-134">The following example demonstrates a client listening for announcements messages over http and peernet.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="12f23-135">См. также</span><span class="sxs-lookup"><span data-stu-id="12f23-135">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
