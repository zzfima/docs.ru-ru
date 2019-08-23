---
title: <add> из <scopes>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: b190cb72e21d47bdc62aab2daba0f6eea1ee04ac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926634"
---
# <a name="add-of-scopes"></a><span data-ttu-id="d8f22-102">\<Добавление > \<областей ></span><span class="sxs-lookup"><span data-stu-id="d8f22-102">\<add> of \<scopes></span></span>
<span data-ttu-id="d8f22-103">Добавляет URI пользовательский области, который при выполнении запроса можно использовать для фильтрации конечных точек службы.</span><span class="sxs-lookup"><span data-stu-id="d8f22-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="d8f22-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d8f22-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d8f22-105">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="d8f22-105">\<behaviors></span></span>  
<span data-ttu-id="d8f22-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d8f22-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="d8f22-107">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="d8f22-107">\<behavior></span></span>  
<span data-ttu-id="d8f22-108">\<Ендпоинтдисковери ></span><span class="sxs-lookup"><span data-stu-id="d8f22-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="d8f22-109">\<области ></span><span class="sxs-lookup"><span data-stu-id="d8f22-109">\<scopes></span></span>  
<span data-ttu-id="d8f22-110">\<add></span><span class="sxs-lookup"><span data-stu-id="d8f22-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8f22-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d8f22-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d8f22-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d8f22-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d8f22-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d8f22-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8f22-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d8f22-114">Attributes</span></span>  
  
|<span data-ttu-id="d8f22-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d8f22-115">Attribute</span></span>|<span data-ttu-id="d8f22-116">Описание</span><span class="sxs-lookup"><span data-stu-id="d8f22-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d8f22-117">область</span><span class="sxs-lookup"><span data-stu-id="d8f22-117">scope</span></span>|<span data-ttu-id="d8f22-118">URI, содержащий сведения об области для конечной точки, которую можно использовать в критериях соответствия при поиске служб.</span><span class="sxs-lookup"><span data-stu-id="d8f22-118">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d8f22-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d8f22-119">Child Elements</span></span>  
 <span data-ttu-id="d8f22-120">Нет.</span><span class="sxs-lookup"><span data-stu-id="d8f22-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d8f22-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d8f22-121">Parent Elements</span></span>  
  
|<span data-ttu-id="d8f22-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="d8f22-122">Element</span></span>|<span data-ttu-id="d8f22-123">Описание</span><span class="sxs-lookup"><span data-stu-id="d8f22-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d8f22-124">\<области ></span><span class="sxs-lookup"><span data-stu-id="d8f22-124">\<scopes></span></span>](scopes.md)|<span data-ttu-id="d8f22-125">Содержит коллекцию элементов конфигурации, указывающие идентификаторы URI пользовательских областей, которые можно использовать для фильтрации конечных точек службы во время выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="d8f22-125">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d8f22-126">См. также</span><span class="sxs-lookup"><span data-stu-id="d8f22-126">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
