---
title: Элемент <clear> для <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: e563f8f27538e70ba90465fc28d300754509f7a4
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423320"
---
# <a name="clear-element-for-namedcaches"></a><span data-ttu-id="25c90-102">\<Очистить > элемент для \<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="25c90-102">\<clear> Element for \<namedCaches></span></span>
<span data-ttu-id="25c90-103">Очищает все `namedCache` записей в `namedCaches` коллекции для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="25c90-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="25c90-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="25c90-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="25c90-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="25c90-105">\<memoryCache></span></span>  
<span data-ttu-id="25c90-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="25c90-106">\<namedCaches></span></span>  
<span data-ttu-id="25c90-107">\<add></span><span class="sxs-lookup"><span data-stu-id="25c90-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25c90-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="25c90-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="25c90-109">Тип</span><span class="sxs-lookup"><span data-stu-id="25c90-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="25c90-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="25c90-110">Attributes and Elements</span></span>  
 <span data-ttu-id="25c90-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="25c90-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="25c90-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="25c90-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="25c90-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="25c90-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="25c90-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="25c90-114">Parent Elements</span></span>  
  
|<span data-ttu-id="25c90-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="25c90-115">Element</span></span>|<span data-ttu-id="25c90-116">Описание</span><span class="sxs-lookup"><span data-stu-id="25c90-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="25c90-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="25c90-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="25c90-118">Содержит коллекцию параметров конфигурации для именованного <xref:System.Runtime.Caching.MemoryCache> экземпляров.</span><span class="sxs-lookup"><span data-stu-id="25c90-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25c90-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="25c90-119">Remarks</span></span>  
 <span data-ttu-id="25c90-120">`clear` Элемент очищает все `namedCache` записей в коллекции именованных кэшей для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="25c90-120">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="25c90-121">Можно использовать `clear` элемент, прежде чем использовать `add` элемент, чтобы добавить новую запись именованного кэша, чтобы быть уверенным, никакие другие именованные кэши в коллекции.</span><span class="sxs-lookup"><span data-stu-id="25c90-121">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25c90-122">См. также</span><span class="sxs-lookup"><span data-stu-id="25c90-122">See also</span></span>

- [<span data-ttu-id="25c90-123">\<namedCaches > (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="25c90-123">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
