---
title: '&lt;Очистить&gt; элемент для &lt;namedCaches&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 17043cdd4bcabf2e5e14c7b9c31b8c1747d2c866
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47171950"
---
# <a name="ltcleargt-element-for-ltnamedcachesgt"></a><span data-ttu-id="6a4d3-102">&lt;Очистить&gt; элемент для &lt;namedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="6a4d3-102">&lt;clear&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="6a4d3-103">Очищает все `namedCache` записей в `namedCaches` коллекции для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="6a4d3-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="6a4d3-104">\<System.Runtime.Caching ></span><span class="sxs-lookup"><span data-stu-id="6a4d3-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="6a4d3-105">\<memoryCache ></span><span class="sxs-lookup"><span data-stu-id="6a4d3-105">\<memoryCache></span></span>  
<span data-ttu-id="6a4d3-106">\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="6a4d3-106">\<namedCaches></span></span>  
<span data-ttu-id="6a4d3-107">\<add></span><span class="sxs-lookup"><span data-stu-id="6a4d3-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a4d3-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6a4d3-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="6a4d3-109">Тип</span><span class="sxs-lookup"><span data-stu-id="6a4d3-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6a4d3-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6a4d3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6a4d3-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6a4d3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6a4d3-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6a4d3-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="6a4d3-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6a4d3-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="6a4d3-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6a4d3-114">Parent Elements</span></span>  
  
|<span data-ttu-id="6a4d3-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="6a4d3-115">Element</span></span>|<span data-ttu-id="6a4d3-116">Описание</span><span class="sxs-lookup"><span data-stu-id="6a4d3-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6a4d3-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="6a4d3-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="6a4d3-118">Содержит коллекцию параметров конфигурации для именованного <xref:System.Runtime.Caching.MemoryCache> экземпляров.</span><span class="sxs-lookup"><span data-stu-id="6a4d3-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a4d3-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="6a4d3-119">Remarks</span></span>  
 <span data-ttu-id="6a4d3-120">`clear` Элемент очищает все `namedCache` записей в коллекции именованных кэшей для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="6a4d3-120">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="6a4d3-121">Можно использовать `clear` элемент, прежде чем использовать `add` элемент, чтобы добавить новую запись именованного кэша, чтобы быть уверенным, никакие другие именованные кэши в коллекции.</span><span class="sxs-lookup"><span data-stu-id="6a4d3-121">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a4d3-122">См. также</span><span class="sxs-lookup"><span data-stu-id="6a4d3-122">See Also</span></span>  
 [<span data-ttu-id="6a4d3-123">\<namedCaches > (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="6a4d3-123">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
