---
title: '&lt;add&gt; для &lt;scopes&gt;'
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: a889100da4723a1f5e8f84ca88ea426ccaa2e77f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745803"
---
# <a name="ltaddgt-of-ltscopesgt"></a><span data-ttu-id="e6f05-102">&lt;add&gt; для &lt;scopes&gt;</span><span class="sxs-lookup"><span data-stu-id="e6f05-102">&lt;add&gt; of &lt;scopes&gt;</span></span>
<span data-ttu-id="e6f05-103">Добавляет URI пользовательский области, который при выполнении запроса можно использовать для фильтрации конечных точек службы.</span><span class="sxs-lookup"><span data-stu-id="e6f05-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="e6f05-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e6f05-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e6f05-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="e6f05-105">\<behaviors></span></span>  
<span data-ttu-id="e6f05-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e6f05-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="e6f05-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="e6f05-107">\<behavior></span></span>  
<span data-ttu-id="e6f05-108">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="e6f05-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="e6f05-109">\<области ></span><span class="sxs-lookup"><span data-stu-id="e6f05-109">\<scopes></span></span>  
<span data-ttu-id="e6f05-110">\<add></span><span class="sxs-lookup"><span data-stu-id="e6f05-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6f05-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e6f05-111">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enable="Boolean">
        <scopes>
          <add scope="URI"/>
        </scopes>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e6f05-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e6f05-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e6f05-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e6f05-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6f05-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e6f05-114">Attributes</span></span>  
  
|<span data-ttu-id="e6f05-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e6f05-115">Attribute</span></span>|<span data-ttu-id="e6f05-116">Описание</span><span class="sxs-lookup"><span data-stu-id="e6f05-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e6f05-117">область действия</span><span class="sxs-lookup"><span data-stu-id="e6f05-117">scope</span></span>|<span data-ttu-id="e6f05-118">URI, содержащий сведения об области для конечной точки, которую можно использовать в критериях соответствия при поиске служб.</span><span class="sxs-lookup"><span data-stu-id="e6f05-118">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e6f05-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e6f05-119">Child Elements</span></span>  
 <span data-ttu-id="e6f05-120">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e6f05-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e6f05-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e6f05-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e6f05-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="e6f05-122">Element</span></span>|<span data-ttu-id="e6f05-123">Описание</span><span class="sxs-lookup"><span data-stu-id="e6f05-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e6f05-124">\<области ></span><span class="sxs-lookup"><span data-stu-id="e6f05-124">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="e6f05-125">Содержит коллекцию элементов конфигурации, указывающие идентификаторы URI пользовательских областей, которые можно использовать для фильтрации конечных точек службы во время выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="e6f05-125">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e6f05-126">См. также</span><span class="sxs-lookup"><span data-stu-id="e6f05-126">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
