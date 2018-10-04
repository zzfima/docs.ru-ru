---
title: '&lt;Удалить&gt; элемент для &lt;namedCaches&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
author: mcleblanc
ms.author: markl
ms.openlocfilehash: f885416629ae58949cc688f4e6fbd41e77e872aa
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48781678"
---
# <a name="ltremovegt-element-for-ltnamedcachesgt"></a><span data-ttu-id="c75ef-102">&lt;Удалить&gt; элемент для &lt;namedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="c75ef-102">&lt;remove&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="c75ef-103">Удаляет элемент именованного кэша из коллекции `namedCaches` для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="c75ef-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="c75ef-104">\<System.Runtime.Caching ></span><span class="sxs-lookup"><span data-stu-id="c75ef-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="c75ef-105">\<memoryCache ></span><span class="sxs-lookup"><span data-stu-id="c75ef-105">\<memoryCache></span></span>  
<span data-ttu-id="c75ef-106">\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="c75ef-106">\<namedCaches></span></span>  
<span data-ttu-id="c75ef-107">\<Удалить ></span><span class="sxs-lookup"><span data-stu-id="c75ef-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c75ef-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c75ef-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="c75ef-109">Тип</span><span class="sxs-lookup"><span data-stu-id="c75ef-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c75ef-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c75ef-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c75ef-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c75ef-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c75ef-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c75ef-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="c75ef-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c75ef-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="c75ef-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c75ef-114">Parent Elements</span></span>  
  
|<span data-ttu-id="c75ef-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="c75ef-115">Element</span></span>|<span data-ttu-id="c75ef-116">Описание</span><span class="sxs-lookup"><span data-stu-id="c75ef-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c75ef-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="c75ef-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="c75ef-118">Содержит коллекцию параметров конфигурации для именованного <xref:System.Runtime.Caching.MemoryCache> экземпляров.</span><span class="sxs-lookup"><span data-stu-id="c75ef-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c75ef-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="c75ef-119">Remarks</span></span>  
 <span data-ttu-id="c75ef-120">`remove` Приводит к удалению `namedCache` запись из коллекции именованных кэшей для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="c75ef-120">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c75ef-121">См. также</span><span class="sxs-lookup"><span data-stu-id="c75ef-121">See Also</span></span>  
 [<span data-ttu-id="c75ef-122">\<namedCaches > (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="c75ef-122">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
