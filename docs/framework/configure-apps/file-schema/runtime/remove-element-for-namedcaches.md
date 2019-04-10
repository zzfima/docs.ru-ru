---
title: <remove> Элемент для <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: 053e2776153489dfdd61547fdc039980646ae697
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229775"
---
# <a name="remove-element-for-namedcaches"></a><span data-ttu-id="90c33-102">\<Удалить > элемент для \<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="90c33-102">\<remove> Element for \<namedCaches></span></span>
<span data-ttu-id="90c33-103">Удаляет элемент именованного кэша из коллекции `namedCaches` для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="90c33-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="90c33-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="90c33-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="90c33-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="90c33-105">\<memoryCache></span></span>  
<span data-ttu-id="90c33-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="90c33-106">\<namedCaches></span></span>  
<span data-ttu-id="90c33-107">\<Удалить ></span><span class="sxs-lookup"><span data-stu-id="90c33-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90c33-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="90c33-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="90c33-109">Тип</span><span class="sxs-lookup"><span data-stu-id="90c33-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="90c33-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="90c33-110">Attributes and Elements</span></span>  
 <span data-ttu-id="90c33-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="90c33-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90c33-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="90c33-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="90c33-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="90c33-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="90c33-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="90c33-114">Parent Elements</span></span>  
  
|<span data-ttu-id="90c33-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="90c33-115">Element</span></span>|<span data-ttu-id="90c33-116">Описание</span><span class="sxs-lookup"><span data-stu-id="90c33-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="90c33-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="90c33-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="90c33-118">Содержит коллекцию параметров конфигурации для именованного <xref:System.Runtime.Caching.MemoryCache> экземпляров.</span><span class="sxs-lookup"><span data-stu-id="90c33-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90c33-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="90c33-119">Remarks</span></span>  
 <span data-ttu-id="90c33-120">`remove` Приводит к удалению `namedCache` запись из коллекции именованных кэшей для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="90c33-120">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90c33-121">См. также</span><span class="sxs-lookup"><span data-stu-id="90c33-121">See also</span></span>

- [<span data-ttu-id="90c33-122">\<namedCaches > (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="90c33-122">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
