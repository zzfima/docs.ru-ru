---
title: Элемент <remove> для <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: 22d06ab1df0d5ed74073772302421a680f1665ef
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257023"
---
# <a name="remove-element-for-namedcaches"></a><span data-ttu-id="69d32-102">\<Удалить > элемент для \<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="69d32-102">\<remove> Element for \<namedCaches></span></span>
<span data-ttu-id="69d32-103">Удаляет элемент именованного кэша из коллекции `namedCaches` для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="69d32-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="69d32-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="69d32-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="69d32-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="69d32-105">\<memoryCache></span></span>  
<span data-ttu-id="69d32-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="69d32-106">\<namedCaches></span></span>  
<span data-ttu-id="69d32-107">\<Удалить ></span><span class="sxs-lookup"><span data-stu-id="69d32-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69d32-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69d32-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="69d32-109">Тип</span><span class="sxs-lookup"><span data-stu-id="69d32-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69d32-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="69d32-110">Attributes and Elements</span></span>  
 <span data-ttu-id="69d32-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="69d32-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69d32-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="69d32-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="69d32-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="69d32-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="69d32-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="69d32-114">Parent Elements</span></span>  
  
|<span data-ttu-id="69d32-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="69d32-115">Element</span></span>|<span data-ttu-id="69d32-116">Описание:</span><span class="sxs-lookup"><span data-stu-id="69d32-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="69d32-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="69d32-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="69d32-118">Содержит коллекцию параметров конфигурации для именованного <xref:System.Runtime.Caching.MemoryCache> экземпляров.</span><span class="sxs-lookup"><span data-stu-id="69d32-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69d32-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="69d32-119">Remarks</span></span>  
 <span data-ttu-id="69d32-120">`remove` Приводит к удалению `namedCache` запись из коллекции именованных кэшей для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="69d32-120">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69d32-121">См. также</span><span class="sxs-lookup"><span data-stu-id="69d32-121">See also</span></span>
- [<span data-ttu-id="69d32-122">\<namedCaches > (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="69d32-122">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
