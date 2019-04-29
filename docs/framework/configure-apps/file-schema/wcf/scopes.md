---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 8bc720238ca3039106345783381cd26134fc46b5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670629"
---
# <a name="scopes"></a><span data-ttu-id="b02ca-101">\<области ></span><span class="sxs-lookup"><span data-stu-id="b02ca-101">\<scopes></span></span>
<span data-ttu-id="b02ca-102">Содержит коллекцию элементов конфигурации, указывающие идентификаторы URI пользовательских областей, которые можно использовать для фильтрации конечных точек службы во время выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="b02ca-102">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="b02ca-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b02ca-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="b02ca-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="b02ca-104">\<behaviors></span></span>  
<span data-ttu-id="b02ca-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="b02ca-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="b02ca-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="b02ca-106">\<behavior></span></span>  
<span data-ttu-id="b02ca-107">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="b02ca-107">\<endpointDiscovery></span></span>  
<span data-ttu-id="b02ca-108">\<области ></span><span class="sxs-lookup"><span data-stu-id="b02ca-108">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b02ca-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b02ca-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b02ca-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b02ca-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b02ca-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b02ca-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b02ca-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b02ca-112">Attributes</span></span>  
 <span data-ttu-id="b02ca-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b02ca-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b02ca-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b02ca-114">Child Elements</span></span>  
  
|<span data-ttu-id="b02ca-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b02ca-115">Attribute</span></span>|<span data-ttu-id="b02ca-116">Описание</span><span class="sxs-lookup"><span data-stu-id="b02ca-116">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="b02ca-117">\<add></span><span class="sxs-lookup"><span data-stu-id="b02ca-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|<span data-ttu-id="b02ca-118">Добавляет данные об области для конечной точки, которая может использоваться в критериях соответствия при поиске служб.</span><span class="sxs-lookup"><span data-stu-id="b02ca-118">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b02ca-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b02ca-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b02ca-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="b02ca-120">Element</span></span>|<span data-ttu-id="b02ca-121">Описание</span><span class="sxs-lookup"><span data-stu-id="b02ca-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b02ca-122">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="b02ca-122">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="b02ca-123">Указывает различные параметры обнаружения для конечной точки, такие как возможность обнаружения, области и любые пользовательские модули для ее метаданных.</span><span class="sxs-lookup"><span data-stu-id="b02ca-123">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b02ca-124">См. также</span><span class="sxs-lookup"><span data-stu-id="b02ca-124">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
