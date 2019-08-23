---
title: <announcementEndpoint>
ms.date: 03/30/2017
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
ms.openlocfilehash: aa4cd8f4d7dcfa438ede71c394f1d0b0ac6faa50
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926555"
---
# <a name="announcementendpoint"></a><span data-ttu-id="f3d4b-101">\<Аннаунцементендпоинт ></span><span class="sxs-lookup"><span data-stu-id="f3d4b-101">\<announcementEndpoint></span></span>
<span data-ttu-id="f3d4b-102">Этот элемент конфигурации определяет стандартную конечную точку с фиксированным контрактом объявления.</span><span class="sxs-lookup"><span data-stu-id="f3d4b-102">This configuration element defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="f3d4b-103">Служба может также объявлять свою доступность путем отправки сообщения в режимах «в сети» и «не в сети» соответственно при открытии и закрытии службы.</span><span class="sxs-lookup"><span data-stu-id="f3d4b-103">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="f3d4b-104">Служба Windows Communication Foundation (WCF) указывает конечные точки объявления в [ \<элементе > сервицедисковери](servicediscovery.md) и использует аннаунцементклиент для выполнения объявлений.</span><span class="sxs-lookup"><span data-stu-id="f3d4b-104">A Windows Communication Foundation (WCF) service specifies the announcement endpoints in the [\<serviceDiscovery>](servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="f3d4b-105">Клиент, желающий прослушивать объявление от другой службы, фактически выступает в роли службы WCF. Поэтому необходимо настроить конечные точки объявления для этого клиента в разделе " [ \<службы >](services.md) ".</span><span class="sxs-lookup"><span data-stu-id="f3d4b-105">A client wishing to listen for the announcement from other service is actually acting as a WCF service; thus you have to configure the announcement endpoints for that client in the [\<services>](services.md) section.</span></span>  
  
<span data-ttu-id="f3d4b-106">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f3d4b-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="f3d4b-107">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="f3d4b-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3d4b-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3d4b-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3d4b-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f3d4b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f3d4b-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f3d4b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3d4b-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f3d4b-111">Attributes</span></span>  
  
|<span data-ttu-id="f3d4b-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f3d4b-112">Attribute</span></span>|<span data-ttu-id="f3d4b-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f3d4b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f3d4b-114">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="f3d4b-114">discoveryVersion</span></span>|<span data-ttu-id="f3d4b-115">Строка, указывающая одну из двух версий протокола WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="f3d4b-115">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="f3d4b-116">Допустимые значения: WSDiscovery11 и WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="f3d4b-116">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="f3d4b-117">Это значение имеет тип <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="f3d4b-117">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="f3d4b-118">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="f3d4b-118">maxAnnouncementDelay</span></span>|<span data-ttu-id="f3d4b-119">Значение «Timespan», указывающее максимальную задержку, в течение которой протокол Discovery не будет отправлять сообщение Hello.</span><span class="sxs-lookup"><span data-stu-id="f3d4b-119">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="f3d4b-120">Перед отправкой сообщения ожидают произвольное время в диапазоне от 0 до значения этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="f3d4b-120">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="f3d4b-121">Этот атрибут используется для назначения короткой произвольной задержки для предотвращения перегрузки сети, когда сеть становится недоступной, а все службы входят в сеть одновременно.</span><span class="sxs-lookup"><span data-stu-id="f3d4b-121">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="f3d4b-122">имя</span><span class="sxs-lookup"><span data-stu-id="f3d4b-122">name</span></span>|<span data-ttu-id="f3d4b-123">Строка, указывающая имя конфигурации стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f3d4b-123">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="f3d4b-124">Это имя используется в атрибуте `endpointConfiguration` конечной точки службы для связывания стандартной конечной точки с ее конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="f3d4b-124">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f3d4b-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f3d4b-125">Child Elements</span></span>  
 <span data-ttu-id="f3d4b-126">Нет.</span><span class="sxs-lookup"><span data-stu-id="f3d4b-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f3d4b-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f3d4b-127">Parent Elements</span></span>  
  
|<span data-ttu-id="f3d4b-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="f3d4b-128">Element</span></span>|<span data-ttu-id="f3d4b-129">Описание</span><span class="sxs-lookup"><span data-stu-id="f3d4b-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f3d4b-130">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="f3d4b-130">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="f3d4b-131">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="f3d4b-131">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f3d4b-132">Пример</span><span class="sxs-lookup"><span data-stu-id="f3d4b-132">Example</span></span>  
 <span data-ttu-id="f3d4b-133">В следующем примере показано прослушивание клиентом сообщений с объявлениями по протоколам http и peernet.</span><span class="sxs-lookup"><span data-stu-id="f3d4b-133">The following example demonstrates a client listening for announcements messages over http and peernet.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f3d4b-134">См. также</span><span class="sxs-lookup"><span data-stu-id="f3d4b-134">See also</span></span>

- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
