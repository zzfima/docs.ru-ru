---
title: Элемент <remove> для <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: 991ad0eb9c04c27ded4d566115107ac7b47a71e1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252340"
---
# <a name="remove-element-for-namedcaches"></a><span data-ttu-id="29ebb-102">\<Удаление элемента > для \<намедкачес ></span><span class="sxs-lookup"><span data-stu-id="29ebb-102">\<remove> Element for \<namedCaches></span></span>
<span data-ttu-id="29ebb-103">Удаляет элемент именованного кэша из коллекции `namedCaches` для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="29ebb-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
<span data-ttu-id="29ebb-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="29ebb-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="29ebb-105">&nbsp;&nbsp;[ **\<System. Runtime. Caching >** ](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="29ebb-105">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="29ebb-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<memoryCache >** ](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="29ebb-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="29ebb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Намедкачес >** ](namedcaches-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="29ebb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)</span></span>\
<span data-ttu-id="29ebb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Удалить >**</span><span class="sxs-lookup"><span data-stu-id="29ebb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29ebb-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="29ebb-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="29ebb-110">Тип</span><span class="sxs-lookup"><span data-stu-id="29ebb-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29ebb-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="29ebb-111">Attributes and Elements</span></span>  
 <span data-ttu-id="29ebb-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="29ebb-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29ebb-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="29ebb-113">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="29ebb-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="29ebb-114">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="29ebb-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="29ebb-115">Parent Elements</span></span>  
  
|<span data-ttu-id="29ebb-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="29ebb-116">Element</span></span>|<span data-ttu-id="29ebb-117">Описание</span><span class="sxs-lookup"><span data-stu-id="29ebb-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="29ebb-118">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="29ebb-118">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="29ebb-119">Содержит коллекцию параметров конфигурации для именованных <xref:System.Runtime.Caching.MemoryCache> экземпляров.</span><span class="sxs-lookup"><span data-stu-id="29ebb-119">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29ebb-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="29ebb-120">Remarks</span></span>  
 <span data-ttu-id="29ebb-121">`remove` Элемент`namedCache` удаляет запись из именованной коллекции кэша для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="29ebb-121">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29ebb-122">См. также</span><span class="sxs-lookup"><span data-stu-id="29ebb-122">See also</span></span>

- [<span data-ttu-id="29ebb-123">\<Элемент > Намедкачес (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="29ebb-123">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
