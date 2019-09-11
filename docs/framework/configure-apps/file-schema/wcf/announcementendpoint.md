---
title: <announcementEndpoint>
ms.date: 03/30/2017
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
ms.openlocfilehash: decaaa1cea5345ff971b16cbb20a85dd803a52d5
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850286"
---
# <a name="announcementendpoint"></a><span data-ttu-id="847bf-101">\<Аннаунцементендпоинт ></span><span class="sxs-lookup"><span data-stu-id="847bf-101">\<announcementEndpoint></span></span>
<span data-ttu-id="847bf-102">Этот элемент конфигурации определяет стандартную конечную точку с фиксированным контрактом объявления.</span><span class="sxs-lookup"><span data-stu-id="847bf-102">This configuration element defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="847bf-103">Служба может также объявлять свою доступность путем отправки сообщения в режимах «в сети» и «не в сети» соответственно при открытии и закрытии службы.</span><span class="sxs-lookup"><span data-stu-id="847bf-103">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="847bf-104">Служба Windows Communication Foundation (WCF) указывает конечные точки объявления в [ \<элементе > сервицедисковери](servicediscovery.md) и использует аннаунцементклиент для выполнения объявлений.</span><span class="sxs-lookup"><span data-stu-id="847bf-104">A Windows Communication Foundation (WCF) service specifies the announcement endpoints in the [\<serviceDiscovery>](servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="847bf-105">Клиент, желающий прослушивать объявление от другой службы, фактически выступает в роли службы WCF. Поэтому необходимо настроить конечные точки объявления для этого клиента в разделе " [ \<службы >](services.md) ".</span><span class="sxs-lookup"><span data-stu-id="847bf-105">A client wishing to listen for the announcement from other service is actually acting as a WCF service; thus you have to configure the announcement endpoints for that client in the [\<services>](services.md) section.</span></span>  
  
<span data-ttu-id="847bf-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="847bf-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="847bf-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="847bf-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="847bf-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Стандардендпоинтс >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="847bf-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="847bf-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Аннаунцементендпоинт >**</span><span class="sxs-lookup"><span data-stu-id="847bf-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<announcementEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="847bf-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="847bf-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="847bf-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="847bf-111">Attributes and Elements</span></span>  
 <span data-ttu-id="847bf-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="847bf-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="847bf-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="847bf-113">Attributes</span></span>  
  
|<span data-ttu-id="847bf-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="847bf-114">Attribute</span></span>|<span data-ttu-id="847bf-115">Описание</span><span class="sxs-lookup"><span data-stu-id="847bf-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="847bf-116">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="847bf-116">discoveryVersion</span></span>|<span data-ttu-id="847bf-117">Строка, указывающая одну из двух версий протокола WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="847bf-117">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="847bf-118">Допустимые значения: WSDiscovery11 и WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="847bf-118">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="847bf-119">Это значение имеет тип <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="847bf-119">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="847bf-120">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="847bf-120">maxAnnouncementDelay</span></span>|<span data-ttu-id="847bf-121">Значение «Timespan», указывающее максимальную задержку, в течение которой протокол Discovery не будет отправлять сообщение Hello.</span><span class="sxs-lookup"><span data-stu-id="847bf-121">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="847bf-122">Перед отправкой сообщения ожидают произвольное время в диапазоне от 0 до значения этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="847bf-122">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="847bf-123">Этот атрибут используется для назначения короткой произвольной задержки для предотвращения перегрузки сети, когда сеть становится недоступной, а все службы входят в сеть одновременно.</span><span class="sxs-lookup"><span data-stu-id="847bf-123">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="847bf-124">имя</span><span class="sxs-lookup"><span data-stu-id="847bf-124">name</span></span>|<span data-ttu-id="847bf-125">Строка, указывающая имя конфигурации стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="847bf-125">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="847bf-126">Это имя используется в атрибуте `endpointConfiguration` конечной точки службы для связывания стандартной конечной точки с ее конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="847bf-126">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="847bf-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="847bf-127">Child Elements</span></span>  
 <span data-ttu-id="847bf-128">Нет.</span><span class="sxs-lookup"><span data-stu-id="847bf-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="847bf-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="847bf-129">Parent Elements</span></span>  
  
|<span data-ttu-id="847bf-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="847bf-130">Element</span></span>|<span data-ttu-id="847bf-131">Описание</span><span class="sxs-lookup"><span data-stu-id="847bf-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="847bf-132">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="847bf-132">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="847bf-133">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="847bf-133">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="847bf-134">Пример</span><span class="sxs-lookup"><span data-stu-id="847bf-134">Example</span></span>  
 <span data-ttu-id="847bf-135">В следующем примере показано прослушивание клиентом сообщений с объявлениями по протоколам http и peernet.</span><span class="sxs-lookup"><span data-stu-id="847bf-135">The following example demonstrates a client listening for announcements messages over http and peernet.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="847bf-136">См. также</span><span class="sxs-lookup"><span data-stu-id="847bf-136">See also</span></span>

- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
