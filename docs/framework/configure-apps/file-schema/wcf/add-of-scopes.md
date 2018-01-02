---
title: "&lt;add&gt; для &lt;scopes&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 012d86297f75874b57231d7c347c7412ad04aa1f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltscopesgt"></a><span data-ttu-id="e765e-102">&lt;add&gt; для &lt;scopes&gt;</span><span class="sxs-lookup"><span data-stu-id="e765e-102">&lt;add&gt; of &lt;scopes&gt;</span></span>
<span data-ttu-id="e765e-103">Добавляет URI пользовательский области, который при выполнении запроса можно использовать для фильтрации конечных точек службы.</span><span class="sxs-lookup"><span data-stu-id="e765e-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="e765e-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e765e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e765e-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="e765e-105">\<behaviors></span></span>  
<span data-ttu-id="e765e-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e765e-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="e765e-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="e765e-107">\<behavior></span></span>  
<span data-ttu-id="e765e-108">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="e765e-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="e765e-109">\<области ></span><span class="sxs-lookup"><span data-stu-id="e765e-109">\<scopes></span></span>  
<span data-ttu-id="e765e-110">\<add></span><span class="sxs-lookup"><span data-stu-id="e765e-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e765e-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e765e-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e765e-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e765e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e765e-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e765e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e765e-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e765e-114">Attributes</span></span>  
  
|<span data-ttu-id="e765e-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e765e-115">Attribute</span></span>|<span data-ttu-id="e765e-116">Описание</span><span class="sxs-lookup"><span data-stu-id="e765e-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e765e-117">область действия</span><span class="sxs-lookup"><span data-stu-id="e765e-117">scope</span></span>|<span data-ttu-id="e765e-118">URI, содержащий сведения об области для конечной точки, которую можно использовать в критериях соответствия при поиске служб.</span><span class="sxs-lookup"><span data-stu-id="e765e-118">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e765e-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e765e-119">Child Elements</span></span>  
 <span data-ttu-id="e765e-120">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e765e-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e765e-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e765e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e765e-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="e765e-122">Element</span></span>|<span data-ttu-id="e765e-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="e765e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e765e-124">\<области ></span><span class="sxs-lookup"><span data-stu-id="e765e-124">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="e765e-125">Содержит коллекцию элементов конфигурации, указывающие идентификаторы URI пользовательских областей, которые можно использовать для фильтрации конечных точек службы во время выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="e765e-125">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e765e-126">См. также</span><span class="sxs-lookup"><span data-stu-id="e765e-126">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
