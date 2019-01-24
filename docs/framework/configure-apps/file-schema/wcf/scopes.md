---
title: '&lt;Области&gt;'
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 1235b483f63ab71405803c16f2d3c9926b15cfad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642991"
---
# <a name="ltscopesgt"></a><span data-ttu-id="71d0f-102">&lt;Области&gt;</span><span class="sxs-lookup"><span data-stu-id="71d0f-102">&lt;scopes&gt;</span></span>
<span data-ttu-id="71d0f-103">Содержит коллекцию элементов конфигурации, указывающие идентификаторы URI пользовательских областей, которые можно использовать для фильтрации конечных точек службы во время выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="71d0f-103">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="71d0f-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="71d0f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="71d0f-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="71d0f-105">\<behaviors></span></span>  
<span data-ttu-id="71d0f-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="71d0f-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="71d0f-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="71d0f-107">\<behavior></span></span>  
<span data-ttu-id="71d0f-108">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="71d0f-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="71d0f-109">\<области ></span><span class="sxs-lookup"><span data-stu-id="71d0f-109">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71d0f-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="71d0f-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71d0f-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="71d0f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="71d0f-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="71d0f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71d0f-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="71d0f-113">Attributes</span></span>  
 <span data-ttu-id="71d0f-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="71d0f-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="71d0f-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="71d0f-115">Child Elements</span></span>  
  
|<span data-ttu-id="71d0f-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="71d0f-116">Attribute</span></span>|<span data-ttu-id="71d0f-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="71d0f-117">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="71d0f-118">\<add></span><span class="sxs-lookup"><span data-stu-id="71d0f-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|<span data-ttu-id="71d0f-119">Добавляет данные об области для конечной точки, которая может использоваться в критериях соответствия при поиске служб.</span><span class="sxs-lookup"><span data-stu-id="71d0f-119">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="71d0f-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="71d0f-120">Parent Elements</span></span>  
  
|<span data-ttu-id="71d0f-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="71d0f-121">Element</span></span>|<span data-ttu-id="71d0f-122">Описание:</span><span class="sxs-lookup"><span data-stu-id="71d0f-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71d0f-123">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="71d0f-123">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="71d0f-124">Указывает различные параметры обнаружения для конечной точки, такие как возможность обнаружения, области и любые пользовательские модули для ее метаданных.</span><span class="sxs-lookup"><span data-stu-id="71d0f-124">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="71d0f-125">См. также</span><span class="sxs-lookup"><span data-stu-id="71d0f-125">See also</span></span>
- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
