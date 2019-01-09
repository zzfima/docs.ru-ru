---
title: '&lt;DiscoveryClient&gt;'
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: 9aef599ebf8068a383fd093b126a6bde1670b291
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151403"
---
# <a name="ltdiscoveryclientgt"></a><span data-ttu-id="05c61-102">&lt;DiscoveryClient&gt;</span><span class="sxs-lookup"><span data-stu-id="05c61-102">&lt;discoveryClient&gt;</span></span>
<span data-ttu-id="05c61-103">Элемент конфигурации для создания пользовательской привязки, которая позволяет клиентскому приложению автоматически выполнять поиск обнаруживаемой службы и определять ее адрес во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="05c61-103">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="05c61-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="05c61-104">\<system.serviceModel></span></span>  
<span data-ttu-id="05c61-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="05c61-105">\<bindings></span></span>  
<span data-ttu-id="05c61-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="05c61-106">\<customBinding></span></span>  
<span data-ttu-id="05c61-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="05c61-107">\<binding></span></span>  
<span data-ttu-id="05c61-108">\<discoveryClient ></span><span class="sxs-lookup"><span data-stu-id="05c61-108">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05c61-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05c61-109">Syntax</span></span>  
  
```xml  
<discoveryClient discoveryEndpoint="String">
  <findCriteria duration="TimeSpan"
                maxResults="Integer"
                scopeMatchBy="Uri">
    <contractTypeNames>
      <add name="String"
           namespace="String" />
    </contractTypeNames>
    <extensions />
    <scopes>
      <add scope="URI"/>
    </scopes>
  </findCriteria>
</discoveryClient>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05c61-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="05c61-110">Attributes and Elements</span></span>  
 <span data-ttu-id="05c61-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="05c61-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05c61-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="05c61-112">Attributes</span></span>  
  
|<span data-ttu-id="05c61-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="05c61-113">Attribute</span></span>|<span data-ttu-id="05c61-114">Описание</span><span class="sxs-lookup"><span data-stu-id="05c61-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="05c61-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="05c61-115">discoveryEndpoint</span></span>|<span data-ttu-id="05c61-116">Строка, содержащая имя конечной точки обнаружения, которая позволяет клиентскому приложению выполнять автоматический поиск необходимой службы и находить ее адрес во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="05c61-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="05c61-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="05c61-117">Child Elements</span></span>  
  
|<span data-ttu-id="05c61-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="05c61-118">Element</span></span>|<span data-ttu-id="05c61-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="05c61-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="05c61-120">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="05c61-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="05c61-121">Элемент конфигурации, который предоставляет набор критериев, используемых клиентским приложением для поиска службы обнаружения.</span><span class="sxs-lookup"><span data-stu-id="05c61-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="05c61-122">Критерии могут быть сгруппированы в критерии поиска (с указанием какие службы вы ищете) и (в том, как долго должен длиться поиск данных) критерии прекращения поиска.</span><span class="sxs-lookup"><span data-stu-id="05c61-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="05c61-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="05c61-123">Parent Elements</span></span>  
  
|<span data-ttu-id="05c61-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="05c61-124">Element</span></span>|<span data-ttu-id="05c61-125">Описание</span><span class="sxs-lookup"><span data-stu-id="05c61-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="05c61-126">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="05c61-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="05c61-127">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="05c61-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="05c61-128">См. также</span><span class="sxs-lookup"><span data-stu-id="05c61-128">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>  
 <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
