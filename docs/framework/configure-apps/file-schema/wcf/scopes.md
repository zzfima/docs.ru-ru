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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9f198811483edb8a7be882588c38b1f3942f8bb4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltscopesgt"></a><span data-ttu-id="a8b81-102">&lt;области&gt;</span><span class="sxs-lookup"><span data-stu-id="a8b81-102">&lt;scopes&gt;</span></span>
<span data-ttu-id="a8b81-103">Содержит коллекцию элементов конфигурации, указывающие идентификаторы URI пользовательских областей, которые можно использовать для фильтрации конечных точек службы во время выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="a8b81-103">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="a8b81-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a8b81-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a8b81-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="a8b81-105">\<behaviors></span></span>  
<span data-ttu-id="a8b81-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="a8b81-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="a8b81-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="a8b81-107">\<behavior></span></span>  
<span data-ttu-id="a8b81-108">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="a8b81-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="a8b81-109">\<области ></span><span class="sxs-lookup"><span data-stu-id="a8b81-109">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8b81-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8b81-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a8b81-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a8b81-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a8b81-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a8b81-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a8b81-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a8b81-113">Attributes</span></span>  
 <span data-ttu-id="a8b81-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a8b81-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a8b81-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a8b81-115">Child Elements</span></span>  
  
|<span data-ttu-id="a8b81-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a8b81-116">Attribute</span></span>|<span data-ttu-id="a8b81-117">Описание</span><span class="sxs-lookup"><span data-stu-id="a8b81-117">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="a8b81-118">\<add></span><span class="sxs-lookup"><span data-stu-id="a8b81-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|<span data-ttu-id="a8b81-119">Добавляет данные об области для конечной точки, которая может использоваться в критериях соответствия при поиске служб.</span><span class="sxs-lookup"><span data-stu-id="a8b81-119">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a8b81-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a8b81-120">Parent Elements</span></span>  
  
|<span data-ttu-id="a8b81-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="a8b81-121">Element</span></span>|<span data-ttu-id="a8b81-122">Описание</span><span class="sxs-lookup"><span data-stu-id="a8b81-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a8b81-123">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="a8b81-123">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="a8b81-124">Указывает различные параметры обнаружения для конечной точки, такие как возможность обнаружения, области и любые пользовательские модули для ее метаданных.</span><span class="sxs-lookup"><span data-stu-id="a8b81-124">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a8b81-125">См. также</span><span class="sxs-lookup"><span data-stu-id="a8b81-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
