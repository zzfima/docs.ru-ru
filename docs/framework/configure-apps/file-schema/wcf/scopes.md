---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: eee6382c578648866045fd9b283454d9e0e76fcb
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275032"
---
# <a name="scopes"></a><span data-ttu-id="ed862-101">\<области ></span><span class="sxs-lookup"><span data-stu-id="ed862-101">\<scopes></span></span>
<span data-ttu-id="ed862-102">Содержит коллекцию элементов конфигурации, указывающие идентификаторы URI пользовательских областей, которые можно использовать для фильтрации конечных точек службы во время выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="ed862-102">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="ed862-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ed862-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="ed862-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="ed862-104">\<behaviors></span></span>  
<span data-ttu-id="ed862-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="ed862-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="ed862-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="ed862-106">\<behavior></span></span>  
<span data-ttu-id="ed862-107">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="ed862-107">\<endpointDiscovery></span></span>  
<span data-ttu-id="ed862-108">\<области ></span><span class="sxs-lookup"><span data-stu-id="ed862-108">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed862-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ed862-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ed862-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ed862-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ed862-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ed862-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ed862-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ed862-112">Attributes</span></span>  
 <span data-ttu-id="ed862-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ed862-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ed862-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ed862-114">Child Elements</span></span>  
  
|<span data-ttu-id="ed862-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ed862-115">Attribute</span></span>|<span data-ttu-id="ed862-116">Описание:</span><span class="sxs-lookup"><span data-stu-id="ed862-116">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="ed862-117">\<add></span><span class="sxs-lookup"><span data-stu-id="ed862-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|<span data-ttu-id="ed862-118">Добавляет данные об области для конечной точки, которая может использоваться в критериях соответствия при поиске служб.</span><span class="sxs-lookup"><span data-stu-id="ed862-118">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ed862-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ed862-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ed862-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="ed862-120">Element</span></span>|<span data-ttu-id="ed862-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="ed862-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ed862-122">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="ed862-122">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="ed862-123">Указывает различные параметры обнаружения для конечной точки, такие как возможность обнаружения, области и любые пользовательские модули для ее метаданных.</span><span class="sxs-lookup"><span data-stu-id="ed862-123">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ed862-124">См. также</span><span class="sxs-lookup"><span data-stu-id="ed862-124">See also</span></span>
- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
