---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: a5ea10601732021af578c17d4f5c5ab69c98f17a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59128444"
---
# <a name="discoveryclient"></a><span data-ttu-id="b96a3-101">\<discoveryClient ></span><span class="sxs-lookup"><span data-stu-id="b96a3-101">\<discoveryClient></span></span>
<span data-ttu-id="b96a3-102">Элемент конфигурации для создания пользовательской привязки, которая позволяет клиентскому приложению автоматически выполнять поиск обнаруживаемой службы и определять ее адрес во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b96a3-102">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="b96a3-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b96a3-103">\<system.serviceModel></span></span>  
<span data-ttu-id="b96a3-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="b96a3-104">\<bindings></span></span>  
<span data-ttu-id="b96a3-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="b96a3-105">\<customBinding></span></span>  
<span data-ttu-id="b96a3-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="b96a3-106">\<binding></span></span>  
<span data-ttu-id="b96a3-107">\<discoveryClient ></span><span class="sxs-lookup"><span data-stu-id="b96a3-107">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b96a3-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b96a3-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b96a3-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b96a3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b96a3-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b96a3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b96a3-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b96a3-111">Attributes</span></span>  
  
|<span data-ttu-id="b96a3-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b96a3-112">Attribute</span></span>|<span data-ttu-id="b96a3-113">Описание</span><span class="sxs-lookup"><span data-stu-id="b96a3-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b96a3-114">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="b96a3-114">discoveryEndpoint</span></span>|<span data-ttu-id="b96a3-115">Строка, содержащая имя конечной точки обнаружения, которая позволяет клиентскому приложению выполнять автоматический поиск необходимой службы и находить ее адрес во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b96a3-115">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b96a3-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b96a3-116">Child Elements</span></span>  
  
|<span data-ttu-id="b96a3-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="b96a3-117">Element</span></span>|<span data-ttu-id="b96a3-118">Описание</span><span class="sxs-lookup"><span data-stu-id="b96a3-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b96a3-119">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="b96a3-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="b96a3-120">Элемент конфигурации, который предоставляет набор критериев, используемых клиентским приложением для поиска службы обнаружения.</span><span class="sxs-lookup"><span data-stu-id="b96a3-120">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="b96a3-121">Критерии могут быть сгруппированы в критерии поиска (с указанием какие службы вы ищете) и (в том, как долго должен длиться поиск данных) критерии прекращения поиска.</span><span class="sxs-lookup"><span data-stu-id="b96a3-121">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b96a3-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b96a3-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b96a3-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="b96a3-123">Element</span></span>|<span data-ttu-id="b96a3-124">Описание</span><span class="sxs-lookup"><span data-stu-id="b96a3-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b96a3-125">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="b96a3-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="b96a3-126">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="b96a3-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b96a3-127">См. также</span><span class="sxs-lookup"><span data-stu-id="b96a3-127">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
