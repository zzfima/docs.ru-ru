---
title: <add> из <scopes>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: 2681d5e757a1c1efc33fb3ef8804e94f8b391757
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55288682"
---
# <a name="add-of-scopes"></a><span data-ttu-id="0b579-102">\<Добавить > из \<области ></span><span class="sxs-lookup"><span data-stu-id="0b579-102">\<add> of \<scopes></span></span>
<span data-ttu-id="0b579-103">Добавляет URI пользовательский области, который при выполнении запроса можно использовать для фильтрации конечных точек службы.</span><span class="sxs-lookup"><span data-stu-id="0b579-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="0b579-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0b579-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0b579-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="0b579-105">\<behaviors></span></span>  
<span data-ttu-id="0b579-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="0b579-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="0b579-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="0b579-107">\<behavior></span></span>  
<span data-ttu-id="0b579-108">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="0b579-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="0b579-109">\<области ></span><span class="sxs-lookup"><span data-stu-id="0b579-109">\<scopes></span></span>  
<span data-ttu-id="0b579-110">\<add></span><span class="sxs-lookup"><span data-stu-id="0b579-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b579-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b579-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b579-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0b579-112">Attributes and Elements</span></span>  
 <span data-ttu-id="0b579-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0b579-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b579-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0b579-114">Attributes</span></span>  
  
|<span data-ttu-id="0b579-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0b579-115">Attribute</span></span>|<span data-ttu-id="0b579-116">Описание</span><span class="sxs-lookup"><span data-stu-id="0b579-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0b579-117">область действия</span><span class="sxs-lookup"><span data-stu-id="0b579-117">scope</span></span>|<span data-ttu-id="0b579-118">URI, содержащий сведения об области для конечной точки, которую можно использовать в критериях соответствия при поиске служб.</span><span class="sxs-lookup"><span data-stu-id="0b579-118">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0b579-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0b579-119">Child Elements</span></span>  
 <span data-ttu-id="0b579-120">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0b579-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0b579-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0b579-121">Parent Elements</span></span>  
  
|<span data-ttu-id="0b579-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="0b579-122">Element</span></span>|<span data-ttu-id="0b579-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="0b579-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b579-124">\<области ></span><span class="sxs-lookup"><span data-stu-id="0b579-124">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="0b579-125">Содержит коллекцию элементов конфигурации, указывающие идентификаторы URI пользовательских областей, которые можно использовать для фильтрации конечных точек службы во время выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="0b579-125">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0b579-126">См. также</span><span class="sxs-lookup"><span data-stu-id="0b579-126">See also</span></span>
- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
