---
title: '&lt;Области&gt;'
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 7e2dda0d0def4d1f90bf1b4dbf54f18983355222
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltscopesgt"></a><span data-ttu-id="83d12-102">&lt;Области&gt;</span><span class="sxs-lookup"><span data-stu-id="83d12-102">&lt;scopes&gt;</span></span>
<span data-ttu-id="83d12-103">Содержит коллекцию элементов конфигурации, указывающие идентификаторы URI пользовательских областей, которые можно использовать для фильтрации конечных точек службы во время выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="83d12-103">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="83d12-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="83d12-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="83d12-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="83d12-105">\<behaviors></span></span>  
<span data-ttu-id="83d12-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="83d12-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="83d12-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="83d12-107">\<behavior></span></span>  
<span data-ttu-id="83d12-108">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="83d12-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="83d12-109">\<области ></span><span class="sxs-lookup"><span data-stu-id="83d12-109">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83d12-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83d12-110">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enable="Boolean">
        <scopes>
          <add scope="URI" />
        </scopes>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83d12-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="83d12-111">Attributes and Elements</span></span>  
 <span data-ttu-id="83d12-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="83d12-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83d12-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="83d12-113">Attributes</span></span>  
 <span data-ttu-id="83d12-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="83d12-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="83d12-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="83d12-115">Child Elements</span></span>  
  
|<span data-ttu-id="83d12-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="83d12-116">Attribute</span></span>|<span data-ttu-id="83d12-117">Описание</span><span class="sxs-lookup"><span data-stu-id="83d12-117">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="83d12-118">\<add></span><span class="sxs-lookup"><span data-stu-id="83d12-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|<span data-ttu-id="83d12-119">Добавляет данные об области для конечной точки, которая может использоваться в критериях соответствия при поиске служб.</span><span class="sxs-lookup"><span data-stu-id="83d12-119">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="83d12-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="83d12-120">Parent Elements</span></span>  
  
|<span data-ttu-id="83d12-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="83d12-121">Element</span></span>|<span data-ttu-id="83d12-122">Описание</span><span class="sxs-lookup"><span data-stu-id="83d12-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="83d12-123">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="83d12-123">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="83d12-124">Указывает различные параметры обнаружения для конечной точки, такие как возможность обнаружения, области и любые пользовательские модули для ее метаданных.</span><span class="sxs-lookup"><span data-stu-id="83d12-124">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="83d12-125">См. также</span><span class="sxs-lookup"><span data-stu-id="83d12-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
