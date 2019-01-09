---
title: '&lt;Области&gt;'
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 7afab700c2d9eb91ffe57bfefaf5864782a0af5f
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145332"
---
# <a name="ltscopesgt"></a><span data-ttu-id="7a0d2-102">&lt;Области&gt;</span><span class="sxs-lookup"><span data-stu-id="7a0d2-102">&lt;scopes&gt;</span></span>
<span data-ttu-id="7a0d2-103">Содержит коллекцию элементов конфигурации, указывающие идентификаторы URI пользовательских областей, которые можно использовать для фильтрации конечных точек службы во время выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="7a0d2-103">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="7a0d2-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7a0d2-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7a0d2-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="7a0d2-105">\<behaviors></span></span>  
<span data-ttu-id="7a0d2-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="7a0d2-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="7a0d2-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="7a0d2-107">\<behavior></span></span>  
<span data-ttu-id="7a0d2-108">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="7a0d2-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="7a0d2-109">\<области ></span><span class="sxs-lookup"><span data-stu-id="7a0d2-109">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a0d2-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7a0d2-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7a0d2-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7a0d2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7a0d2-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7a0d2-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7a0d2-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7a0d2-113">Attributes</span></span>  
 <span data-ttu-id="7a0d2-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7a0d2-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7a0d2-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7a0d2-115">Child Elements</span></span>  
  
|<span data-ttu-id="7a0d2-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7a0d2-116">Attribute</span></span>|<span data-ttu-id="7a0d2-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="7a0d2-117">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="7a0d2-118">\<add></span><span class="sxs-lookup"><span data-stu-id="7a0d2-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|<span data-ttu-id="7a0d2-119">Добавляет данные об области для конечной точки, которая может использоваться в критериях соответствия при поиске служб.</span><span class="sxs-lookup"><span data-stu-id="7a0d2-119">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7a0d2-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7a0d2-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7a0d2-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="7a0d2-121">Element</span></span>|<span data-ttu-id="7a0d2-122">Описание</span><span class="sxs-lookup"><span data-stu-id="7a0d2-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7a0d2-123">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="7a0d2-123">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="7a0d2-124">Указывает различные параметры обнаружения для конечной точки, такие как возможность обнаружения, области и любые пользовательские модули для ее метаданных.</span><span class="sxs-lookup"><span data-stu-id="7a0d2-124">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7a0d2-125">См. также</span><span class="sxs-lookup"><span data-stu-id="7a0d2-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
