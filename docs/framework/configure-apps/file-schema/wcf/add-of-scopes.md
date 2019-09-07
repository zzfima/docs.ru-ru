---
title: <add> из <scopes>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: bcde6b18c34dccf1716c809dddeb45b1b4da90f0
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398305"
---
# <a name="add-of-scopes"></a><span data-ttu-id="15282-102">\<Добавление > \<областей ></span><span class="sxs-lookup"><span data-stu-id="15282-102">\<add> of \<scopes></span></span>
<span data-ttu-id="15282-103">Добавляет URI пользовательский области, который при выполнении запроса можно использовать для фильтрации конечных точек службы.</span><span class="sxs-lookup"><span data-stu-id="15282-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="15282-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="15282-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="15282-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="15282-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="15282-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="15282-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="15282-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="15282-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="15282-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="15282-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="15282-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Ендпоинтдисковери >** ](endpointdiscovery.md)</span><span class="sxs-lookup"><span data-stu-id="15282-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)</span></span>\
<span data-ttu-id="15282-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<области >** ](scopes.md)</span><span class="sxs-lookup"><span data-stu-id="15282-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopes>**](scopes.md)</span></span>\
<span data-ttu-id="15282-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Добавить >**</span><span class="sxs-lookup"><span data-stu-id="15282-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15282-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="15282-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15282-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="15282-113">Attributes and Elements</span></span>  
 <span data-ttu-id="15282-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="15282-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15282-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="15282-115">Attributes</span></span>  
  
|<span data-ttu-id="15282-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="15282-116">Attribute</span></span>|<span data-ttu-id="15282-117">Описание</span><span class="sxs-lookup"><span data-stu-id="15282-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="15282-118">область</span><span class="sxs-lookup"><span data-stu-id="15282-118">scope</span></span>|<span data-ttu-id="15282-119">URI, содержащий сведения об области для конечной точки, которую можно использовать в критериях соответствия при поиске служб.</span><span class="sxs-lookup"><span data-stu-id="15282-119">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="15282-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="15282-120">Child Elements</span></span>  
 <span data-ttu-id="15282-121">Нет.</span><span class="sxs-lookup"><span data-stu-id="15282-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="15282-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="15282-122">Parent Elements</span></span>  
  
|<span data-ttu-id="15282-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="15282-123">Element</span></span>|<span data-ttu-id="15282-124">Описание</span><span class="sxs-lookup"><span data-stu-id="15282-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15282-125">\<области ></span><span class="sxs-lookup"><span data-stu-id="15282-125">\<scopes></span></span>](scopes.md)|<span data-ttu-id="15282-126">Содержит коллекцию элементов конфигурации, указывающие идентификаторы URI пользовательских областей, которые можно использовать для фильтрации конечных точек службы во время выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="15282-126">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="15282-127">См. также</span><span class="sxs-lookup"><span data-stu-id="15282-127">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
