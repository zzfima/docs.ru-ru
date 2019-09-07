---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 57e9e19025db5e1fa588f073fdf30de09837a25d
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399939"
---
# <a name="scopes"></a><span data-ttu-id="b3c08-101">\<области ></span><span class="sxs-lookup"><span data-stu-id="b3c08-101">\<scopes></span></span>
<span data-ttu-id="b3c08-102">Содержит коллекцию элементов конфигурации, указывающие идентификаторы URI пользовательских областей, которые можно использовать для фильтрации конечных точек службы во время выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="b3c08-102">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="b3c08-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b3c08-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b3c08-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b3c08-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b3c08-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b3c08-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="b3c08-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b3c08-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="b3c08-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b3c08-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="b3c08-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Ендпоинтдисковери >** ](endpointdiscovery.md)</span><span class="sxs-lookup"><span data-stu-id="b3c08-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)</span></span>\
<span data-ttu-id="b3c08-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<области >**</span><span class="sxs-lookup"><span data-stu-id="b3c08-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<scopes>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3c08-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3c08-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b3c08-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b3c08-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b3c08-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b3c08-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b3c08-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b3c08-113">Attributes</span></span>  
 <span data-ttu-id="b3c08-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="b3c08-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b3c08-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b3c08-115">Child Elements</span></span>  
  
|<span data-ttu-id="b3c08-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b3c08-116">Attribute</span></span>|<span data-ttu-id="b3c08-117">Описание</span><span class="sxs-lookup"><span data-stu-id="b3c08-117">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="b3c08-118">\<add></span><span class="sxs-lookup"><span data-stu-id="b3c08-118">\<add></span></span>](add-of-scopes.md)|<span data-ttu-id="b3c08-119">Добавляет данные об области для конечной точки, которая может использоваться в критериях соответствия при поиске служб.</span><span class="sxs-lookup"><span data-stu-id="b3c08-119">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b3c08-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b3c08-120">Parent Elements</span></span>  
  
|<span data-ttu-id="b3c08-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="b3c08-121">Element</span></span>|<span data-ttu-id="b3c08-122">Описание</span><span class="sxs-lookup"><span data-stu-id="b3c08-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3c08-123">\<Ендпоинтдисковери ></span><span class="sxs-lookup"><span data-stu-id="b3c08-123">\<endpointDiscovery></span></span>](endpointdiscovery.md)|<span data-ttu-id="b3c08-124">Указывает различные параметры обнаружения для конечной точки, такие как возможность обнаружения, области и любые пользовательские модули для ее метаданных.</span><span class="sxs-lookup"><span data-stu-id="b3c08-124">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b3c08-125">См. также</span><span class="sxs-lookup"><span data-stu-id="b3c08-125">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
