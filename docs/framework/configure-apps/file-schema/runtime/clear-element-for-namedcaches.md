---
title: Элемент <clear> для <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: a90970e468359714bbbb858f3f300c26b5757a4d
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658865"
---
# <a name="clear-element-for-namedcaches"></a><span data-ttu-id="9d9b6-102">\<Очистка элемента > для \<намедкачес ></span><span class="sxs-lookup"><span data-stu-id="9d9b6-102">\<clear> Element for \<namedCaches></span></span>
<span data-ttu-id="9d9b6-103">Очищает все `namedCache` записи `namedCaches` в коллекции для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="9d9b6-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="9d9b6-104">\<System. Runtime. Caching ></span><span class="sxs-lookup"><span data-stu-id="9d9b6-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="9d9b6-105">\<memoryCache ></span><span class="sxs-lookup"><span data-stu-id="9d9b6-105">\<memoryCache></span></span>  
<span data-ttu-id="9d9b6-106">\<Намедкачес ></span><span class="sxs-lookup"><span data-stu-id="9d9b6-106">\<namedCaches></span></span>  
<span data-ttu-id="9d9b6-107">\<add></span><span class="sxs-lookup"><span data-stu-id="9d9b6-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d9b6-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d9b6-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="9d9b6-109">Тип</span><span class="sxs-lookup"><span data-stu-id="9d9b6-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9d9b6-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9d9b6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9d9b6-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9d9b6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9d9b6-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9d9b6-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="9d9b6-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9d9b6-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="9d9b6-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9d9b6-114">Parent Elements</span></span>  
  
|<span data-ttu-id="9d9b6-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="9d9b6-115">Element</span></span>|<span data-ttu-id="9d9b6-116">Описание</span><span class="sxs-lookup"><span data-stu-id="9d9b6-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9d9b6-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="9d9b6-117">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="9d9b6-118">Содержит коллекцию параметров конфигурации для именованных <xref:System.Runtime.Caching.MemoryCache> экземпляров.</span><span class="sxs-lookup"><span data-stu-id="9d9b6-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d9b6-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="9d9b6-119">Remarks</span></span>  
 <span data-ttu-id="9d9b6-120">Элемент очищает все `namedCache` записи в именованной коллекции кэша для кэша памяти. `clear`</span><span class="sxs-lookup"><span data-stu-id="9d9b6-120">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="9d9b6-121">`clear` Элемент можно использовать перед тем, как `add` использовать элемент для добавления новой именованной записи кэша, чтобы быть уверенным в том, что в коллекции нет других именованных кэшей.</span><span class="sxs-lookup"><span data-stu-id="9d9b6-121">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d9b6-122">См. также</span><span class="sxs-lookup"><span data-stu-id="9d9b6-122">See also</span></span>

- [<span data-ttu-id="9d9b6-123">\<Элемент > Намедкачес (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="9d9b6-123">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
