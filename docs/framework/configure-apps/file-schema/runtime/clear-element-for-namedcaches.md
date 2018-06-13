---
title: '&lt;Очистить&gt; элемент для &lt;namedCaches&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: cdd6e4a4849a031dc6bcad909509498406fcb129
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745517"
---
# <a name="ltcleargt-element-for-ltnamedcachesgt"></a><span data-ttu-id="55431-102">&lt;Очистить&gt; элемент для &lt;namedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="55431-102">&lt;clear&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="55431-103">Удаляет все `namedCache` записей в `namedCaches` коллекции для кэш-памяти.</span><span class="sxs-lookup"><span data-stu-id="55431-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="55431-104">\<System.Runtime.Caching ></span><span class="sxs-lookup"><span data-stu-id="55431-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="55431-105">\<memoryCache ></span><span class="sxs-lookup"><span data-stu-id="55431-105">\<memoryCache></span></span>  
<span data-ttu-id="55431-106">\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="55431-106">\<namedCaches></span></span>  
<span data-ttu-id="55431-107">\<add></span><span class="sxs-lookup"><span data-stu-id="55431-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55431-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55431-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="55431-109">Тип</span><span class="sxs-lookup"><span data-stu-id="55431-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="55431-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="55431-110">Attributes and Elements</span></span>  
 <span data-ttu-id="55431-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="55431-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="55431-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="55431-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="55431-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="55431-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="55431-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="55431-114">Parent Elements</span></span>  
  
|<span data-ttu-id="55431-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="55431-115">Element</span></span>|<span data-ttu-id="55431-116">Описание</span><span class="sxs-lookup"><span data-stu-id="55431-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="55431-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="55431-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="55431-118">Содержит коллекцию параметров конфигурации для именованного <xref:System.Runtime.Caching.MemoryCache> экземпляров.</span><span class="sxs-lookup"><span data-stu-id="55431-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55431-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="55431-119">Remarks</span></span>  
 <span data-ttu-id="55431-120">`clear` Элемент очищает все `namedCache` записи в коллекции именованных кэшей для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="55431-120">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="55431-121">Можно использовать `clear` элемент, прежде чем использовать `add` элемента, который требуется добавить новую запись именованного кэша, чтобы быть уверенным, никакие другие именованные кэши в коллекции.</span><span class="sxs-lookup"><span data-stu-id="55431-121">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55431-122">См. также</span><span class="sxs-lookup"><span data-stu-id="55431-122">See Also</span></span>  
 [<span data-ttu-id="55431-123">\<namedCaches > элемент (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="55431-123">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
