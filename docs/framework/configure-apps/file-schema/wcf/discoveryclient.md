---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: 512a91bf25180606213eb9eb3b4f7c6a0cb4cbbf
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55284809"
---
# <a name="discoveryclient"></a><span data-ttu-id="42b0b-101">\<discoveryClient ></span><span class="sxs-lookup"><span data-stu-id="42b0b-101">\<discoveryClient></span></span>
<span data-ttu-id="42b0b-102">Элемент конфигурации для создания пользовательской привязки, которая позволяет клиентскому приложению автоматически выполнять поиск обнаруживаемой службы и определять ее адрес во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="42b0b-102">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="42b0b-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="42b0b-103">\<system.serviceModel></span></span>  
<span data-ttu-id="42b0b-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="42b0b-104">\<bindings></span></span>  
<span data-ttu-id="42b0b-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="42b0b-105">\<customBinding></span></span>  
<span data-ttu-id="42b0b-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="42b0b-106">\<binding></span></span>  
<span data-ttu-id="42b0b-107">\<discoveryClient ></span><span class="sxs-lookup"><span data-stu-id="42b0b-107">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42b0b-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="42b0b-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42b0b-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="42b0b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="42b0b-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="42b0b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42b0b-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="42b0b-111">Attributes</span></span>  
  
|<span data-ttu-id="42b0b-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="42b0b-112">Attribute</span></span>|<span data-ttu-id="42b0b-113">Описание</span><span class="sxs-lookup"><span data-stu-id="42b0b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="42b0b-114">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="42b0b-114">discoveryEndpoint</span></span>|<span data-ttu-id="42b0b-115">Строка, содержащая имя конечной точки обнаружения, которая позволяет клиентскому приложению выполнять автоматический поиск необходимой службы и находить ее адрес во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="42b0b-115">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42b0b-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="42b0b-116">Child Elements</span></span>  
  
|<span data-ttu-id="42b0b-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="42b0b-117">Element</span></span>|<span data-ttu-id="42b0b-118">Описание</span><span class="sxs-lookup"><span data-stu-id="42b0b-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="42b0b-119">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="42b0b-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="42b0b-120">Элемент конфигурации, который предоставляет набор критериев, используемых клиентским приложением для поиска службы обнаружения.</span><span class="sxs-lookup"><span data-stu-id="42b0b-120">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="42b0b-121">Критерии могут быть сгруппированы в критерии поиска (с указанием какие службы вы ищете) и (в том, как долго должен длиться поиск данных) критерии прекращения поиска.</span><span class="sxs-lookup"><span data-stu-id="42b0b-121">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="42b0b-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="42b0b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="42b0b-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="42b0b-123">Element</span></span>|<span data-ttu-id="42b0b-124">Описание:</span><span class="sxs-lookup"><span data-stu-id="42b0b-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="42b0b-125">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="42b0b-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="42b0b-126">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="42b0b-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="42b0b-127">См. также</span><span class="sxs-lookup"><span data-stu-id="42b0b-127">See also</span></span>
- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
