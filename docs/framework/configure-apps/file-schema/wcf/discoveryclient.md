---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: a5ea10601732021af578c17d4f5c5ab69c98f17a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704028"
---
# <a name="discoveryclient"></a><span data-ttu-id="2fd92-101">\<discoveryClient ></span><span class="sxs-lookup"><span data-stu-id="2fd92-101">\<discoveryClient></span></span>
<span data-ttu-id="2fd92-102">Элемент конфигурации для создания пользовательской привязки, которая позволяет клиентскому приложению автоматически выполнять поиск обнаруживаемой службы и определять ее адрес во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="2fd92-102">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="2fd92-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2fd92-103">\<system.serviceModel></span></span>  
<span data-ttu-id="2fd92-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="2fd92-104">\<bindings></span></span>  
<span data-ttu-id="2fd92-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="2fd92-105">\<customBinding></span></span>  
<span data-ttu-id="2fd92-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="2fd92-106">\<binding></span></span>  
<span data-ttu-id="2fd92-107">\<discoveryClient ></span><span class="sxs-lookup"><span data-stu-id="2fd92-107">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fd92-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2fd92-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2fd92-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2fd92-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2fd92-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2fd92-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2fd92-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2fd92-111">Attributes</span></span>  
  
|<span data-ttu-id="2fd92-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2fd92-112">Attribute</span></span>|<span data-ttu-id="2fd92-113">Описание</span><span class="sxs-lookup"><span data-stu-id="2fd92-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2fd92-114">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="2fd92-114">discoveryEndpoint</span></span>|<span data-ttu-id="2fd92-115">Строка, содержащая имя конечной точки обнаружения, которая позволяет клиентскому приложению выполнять автоматический поиск необходимой службы и находить ее адрес во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="2fd92-115">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2fd92-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2fd92-116">Child Elements</span></span>  
  
|<span data-ttu-id="2fd92-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="2fd92-117">Element</span></span>|<span data-ttu-id="2fd92-118">Описание</span><span class="sxs-lookup"><span data-stu-id="2fd92-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2fd92-119">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="2fd92-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="2fd92-120">Элемент конфигурации, который предоставляет набор критериев, используемых клиентским приложением для поиска службы обнаружения.</span><span class="sxs-lookup"><span data-stu-id="2fd92-120">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="2fd92-121">Критерии могут быть сгруппированы в критерии поиска (с указанием какие службы вы ищете) и (в том, как долго должен длиться поиск данных) критерии прекращения поиска.</span><span class="sxs-lookup"><span data-stu-id="2fd92-121">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2fd92-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2fd92-122">Parent Elements</span></span>  
  
|<span data-ttu-id="2fd92-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="2fd92-123">Element</span></span>|<span data-ttu-id="2fd92-124">Описание</span><span class="sxs-lookup"><span data-stu-id="2fd92-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2fd92-125">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="2fd92-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="2fd92-126">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="2fd92-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2fd92-127">См. также</span><span class="sxs-lookup"><span data-stu-id="2fd92-127">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
