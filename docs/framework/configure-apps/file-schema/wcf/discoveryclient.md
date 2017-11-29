---
title: '&lt;discoveryClient&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a0b7161c9e4564367348d1c94d469d6fa4a4b79b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltdiscoveryclientgt"></a><span data-ttu-id="6c411-102">&lt;discoveryClient&gt;</span><span class="sxs-lookup"><span data-stu-id="6c411-102">&lt;discoveryClient&gt;</span></span>
<span data-ttu-id="6c411-103">Элемент конфигурации для создания пользовательской привязки, которая позволяет клиентскому приложению автоматически выполнять поиск обнаруживаемой службы и определять ее адрес во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="6c411-103">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="6c411-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="6c411-104">\<system.serviceModel></span></span>  
<span data-ttu-id="6c411-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="6c411-105">\<bindings></span></span>  
<span data-ttu-id="6c411-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="6c411-106">\<customBinding></span></span>  
<span data-ttu-id="6c411-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="6c411-107">\<binding></span></span>  
<span data-ttu-id="6c411-108">\<discoveryClient ></span><span class="sxs-lookup"><span data-stu-id="6c411-108">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c411-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c411-109">Syntax</span></span>  
  
```xml  
<discoveryClient discoveryEndpoint="String" >
  <findCriteria duration="TimeSpan" maxResults="Integer" scopeMatchBy="Uri">
    <contractTypeNames>
      <add name="String" namespace="String" />
    <contractTypeNames>
    <extensions />
    <scopes>
      <add scope="URI"/>
    </scopes>
  </findCriteria>
</discoveryClient>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c411-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6c411-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6c411-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6c411-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c411-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6c411-112">Attributes</span></span>  
  
|<span data-ttu-id="6c411-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6c411-113">Attribute</span></span>|<span data-ttu-id="6c411-114">Описание</span><span class="sxs-lookup"><span data-stu-id="6c411-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6c411-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="6c411-115">discoveryEndpoint</span></span>|<span data-ttu-id="6c411-116">Строка, содержащая имя конечной точки обнаружения, которая позволяет клиентскому приложению выполнять автоматический поиск необходимой службы и находить ее адрес во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="6c411-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6c411-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6c411-117">Child Elements</span></span>  
  
|<span data-ttu-id="6c411-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="6c411-118">Element</span></span>|<span data-ttu-id="6c411-119">Описание</span><span class="sxs-lookup"><span data-stu-id="6c411-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c411-120">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="6c411-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="6c411-121">Элемент конфигурации, который предоставляет набор критериев, используемых клиентским приложением для поиска службы обнаружения.</span><span class="sxs-lookup"><span data-stu-id="6c411-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="6c411-122">Критерии могут быть сгруппированы в критерии поиска (с указанием искомых служб, которые вы ищете) и критерии прекращения поиска (как долго поиска должно длиться).</span><span class="sxs-lookup"><span data-stu-id="6c411-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6c411-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6c411-123">Parent Elements</span></span>  
  
|<span data-ttu-id="6c411-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="6c411-124">Element</span></span>|<span data-ttu-id="6c411-125">Описание</span><span class="sxs-lookup"><span data-stu-id="6c411-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c411-126">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="6c411-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="6c411-127">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="6c411-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6c411-128">См. также</span><span class="sxs-lookup"><span data-stu-id="6c411-128">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>  
 <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
