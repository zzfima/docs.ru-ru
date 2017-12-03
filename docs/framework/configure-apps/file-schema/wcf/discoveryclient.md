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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 55c8b9a01eaf53105968e044aecb7e38ad691aac
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltdiscoveryclientgt"></a><span data-ttu-id="3683b-102">&lt;discoveryClient&gt;</span><span class="sxs-lookup"><span data-stu-id="3683b-102">&lt;discoveryClient&gt;</span></span>
<span data-ttu-id="3683b-103">Элемент конфигурации для создания пользовательской привязки, которая позволяет клиентскому приложению автоматически выполнять поиск обнаруживаемой службы и определять ее адрес во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="3683b-103">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="3683b-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="3683b-104">\<system.serviceModel></span></span>  
<span data-ttu-id="3683b-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="3683b-105">\<bindings></span></span>  
<span data-ttu-id="3683b-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="3683b-106">\<customBinding></span></span>  
<span data-ttu-id="3683b-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="3683b-107">\<binding></span></span>  
<span data-ttu-id="3683b-108">\<discoveryClient ></span><span class="sxs-lookup"><span data-stu-id="3683b-108">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3683b-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3683b-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3683b-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3683b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3683b-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3683b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3683b-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3683b-112">Attributes</span></span>  
  
|<span data-ttu-id="3683b-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3683b-113">Attribute</span></span>|<span data-ttu-id="3683b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="3683b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3683b-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="3683b-115">discoveryEndpoint</span></span>|<span data-ttu-id="3683b-116">Строка, содержащая имя конечной точки обнаружения, которая позволяет клиентскому приложению выполнять автоматический поиск необходимой службы и находить ее адрес во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="3683b-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3683b-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3683b-117">Child Elements</span></span>  
  
|<span data-ttu-id="3683b-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="3683b-118">Element</span></span>|<span data-ttu-id="3683b-119">Описание</span><span class="sxs-lookup"><span data-stu-id="3683b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3683b-120">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="3683b-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="3683b-121">Элемент конфигурации, который предоставляет набор критериев, используемых клиентским приложением для поиска службы обнаружения.</span><span class="sxs-lookup"><span data-stu-id="3683b-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="3683b-122">Критерии могут быть сгруппированы в критерии поиска (с указанием искомых служб, которые вы ищете) и критерии прекращения поиска (как долго поиска должно длиться).</span><span class="sxs-lookup"><span data-stu-id="3683b-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3683b-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3683b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="3683b-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="3683b-124">Element</span></span>|<span data-ttu-id="3683b-125">Описание</span><span class="sxs-lookup"><span data-stu-id="3683b-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3683b-126">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="3683b-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="3683b-127">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="3683b-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3683b-128">См. также</span><span class="sxs-lookup"><span data-stu-id="3683b-128">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>  
 <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
