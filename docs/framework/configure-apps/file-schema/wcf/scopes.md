---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 8bc720238ca3039106345783381cd26134fc46b5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213081"
---
# <a name="scopes"></a><span data-ttu-id="78a7e-101">\<области ></span><span class="sxs-lookup"><span data-stu-id="78a7e-101">\<scopes></span></span>
<span data-ttu-id="78a7e-102">Содержит коллекцию элементов конфигурации, указывающие идентификаторы URI пользовательских областей, которые можно использовать для фильтрации конечных точек службы во время выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="78a7e-102">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="78a7e-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="78a7e-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="78a7e-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="78a7e-104">\<behaviors></span></span>  
<span data-ttu-id="78a7e-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="78a7e-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="78a7e-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="78a7e-106">\<behavior></span></span>  
<span data-ttu-id="78a7e-107">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="78a7e-107">\<endpointDiscovery></span></span>  
<span data-ttu-id="78a7e-108">\<области ></span><span class="sxs-lookup"><span data-stu-id="78a7e-108">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78a7e-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78a7e-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78a7e-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="78a7e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="78a7e-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="78a7e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78a7e-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="78a7e-112">Attributes</span></span>  
 <span data-ttu-id="78a7e-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="78a7e-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="78a7e-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="78a7e-114">Child Elements</span></span>  
  
|<span data-ttu-id="78a7e-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="78a7e-115">Attribute</span></span>|<span data-ttu-id="78a7e-116">Описание</span><span class="sxs-lookup"><span data-stu-id="78a7e-116">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="78a7e-117">\<add></span><span class="sxs-lookup"><span data-stu-id="78a7e-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|<span data-ttu-id="78a7e-118">Добавляет данные об области для конечной точки, которая может использоваться в критериях соответствия при поиске служб.</span><span class="sxs-lookup"><span data-stu-id="78a7e-118">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="78a7e-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="78a7e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="78a7e-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="78a7e-120">Element</span></span>|<span data-ttu-id="78a7e-121">Описание</span><span class="sxs-lookup"><span data-stu-id="78a7e-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78a7e-122">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="78a7e-122">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="78a7e-123">Указывает различные параметры обнаружения для конечной точки, такие как возможность обнаружения, области и любые пользовательские модули для ее метаданных.</span><span class="sxs-lookup"><span data-stu-id="78a7e-123">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78a7e-124">См. также</span><span class="sxs-lookup"><span data-stu-id="78a7e-124">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
