---
title: "&lt;области&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6b35696cbecb0badf397d6d48e7c97aae3d0232e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltscopesgt"></a><span data-ttu-id="cca6d-102">&lt;области&gt;</span><span class="sxs-lookup"><span data-stu-id="cca6d-102">&lt;scopes&gt;</span></span>
<span data-ttu-id="cca6d-103">Содержит коллекцию элементов конфигурации, указывающие идентификаторы URI пользовательских областей, которые можно использовать для фильтрации конечных точек службы во время выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="cca6d-103">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="cca6d-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="cca6d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="cca6d-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="cca6d-105">\<behaviors></span></span>  
<span data-ttu-id="cca6d-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="cca6d-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="cca6d-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="cca6d-107">\<behavior></span></span>  
<span data-ttu-id="cca6d-108">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="cca6d-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="cca6d-109">\<области ></span><span class="sxs-lookup"><span data-stu-id="cca6d-109">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cca6d-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cca6d-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cca6d-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cca6d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="cca6d-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cca6d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cca6d-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cca6d-113">Attributes</span></span>  
 <span data-ttu-id="cca6d-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="cca6d-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cca6d-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cca6d-115">Child Elements</span></span>  
  
|<span data-ttu-id="cca6d-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="cca6d-116">Attribute</span></span>|<span data-ttu-id="cca6d-117">Описание</span><span class="sxs-lookup"><span data-stu-id="cca6d-117">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="cca6d-118">\<add></span><span class="sxs-lookup"><span data-stu-id="cca6d-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|<span data-ttu-id="cca6d-119">Добавляет данные об области для конечной точки, которая может использоваться в критериях соответствия при поиске служб.</span><span class="sxs-lookup"><span data-stu-id="cca6d-119">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cca6d-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cca6d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="cca6d-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="cca6d-121">Element</span></span>|<span data-ttu-id="cca6d-122">Описание</span><span class="sxs-lookup"><span data-stu-id="cca6d-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cca6d-123">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="cca6d-123">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="cca6d-124">Указывает различные параметры обнаружения для конечной точки, такие как возможность обнаружения, области и любые пользовательские модули для ее метаданных.</span><span class="sxs-lookup"><span data-stu-id="cca6d-124">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cca6d-125">См. также</span><span class="sxs-lookup"><span data-stu-id="cca6d-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
