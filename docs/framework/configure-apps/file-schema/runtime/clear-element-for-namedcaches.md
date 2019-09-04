---
title: Элемент <clear> для <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: bcc0e23f0c47ad3a98430e36da31d39612caa3c9
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252761"
---
# <a name="clear-element-for-namedcaches"></a><span data-ttu-id="fccac-102">\<Очистка элемента > для \<намедкачес ></span><span class="sxs-lookup"><span data-stu-id="fccac-102">\<clear> Element for \<namedCaches></span></span>
<span data-ttu-id="fccac-103">Очищает все `namedCache` записи `namedCaches` в коллекции для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="fccac-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
<span data-ttu-id="fccac-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fccac-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fccac-105">&nbsp;&nbsp;[ **\<System. Runtime. Caching >** ](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="fccac-105">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="fccac-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<memoryCache >** ](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="fccac-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="fccac-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Намедкачес >** ](namedcaches-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="fccac-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)</span></span>\
<span data-ttu-id="fccac-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<очистить >**</span><span class="sxs-lookup"><span data-stu-id="fccac-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fccac-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fccac-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="fccac-110">Тип</span><span class="sxs-lookup"><span data-stu-id="fccac-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fccac-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fccac-111">Attributes and Elements</span></span>  
 <span data-ttu-id="fccac-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fccac-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fccac-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fccac-113">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="fccac-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fccac-114">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="fccac-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fccac-115">Parent Elements</span></span>  
  
|<span data-ttu-id="fccac-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="fccac-116">Element</span></span>|<span data-ttu-id="fccac-117">Описание</span><span class="sxs-lookup"><span data-stu-id="fccac-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fccac-118">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="fccac-118">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="fccac-119">Содержит коллекцию параметров конфигурации для именованных <xref:System.Runtime.Caching.MemoryCache> экземпляров.</span><span class="sxs-lookup"><span data-stu-id="fccac-119">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fccac-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="fccac-120">Remarks</span></span>  
 <span data-ttu-id="fccac-121">Элемент очищает все `namedCache` записи в именованной коллекции кэша для кэша памяти. `clear`</span><span class="sxs-lookup"><span data-stu-id="fccac-121">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="fccac-122">`clear` Элемент можно использовать перед тем, как `add` использовать элемент для добавления новой именованной записи кэша, чтобы быть уверенным в том, что в коллекции нет других именованных кэшей.</span><span class="sxs-lookup"><span data-stu-id="fccac-122">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fccac-123">См. также</span><span class="sxs-lookup"><span data-stu-id="fccac-123">See also</span></span>

- [<span data-ttu-id="fccac-124">\<Элемент > Намедкачес (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="fccac-124">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
