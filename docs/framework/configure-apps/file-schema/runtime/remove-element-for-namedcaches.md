---
title: '&lt;Удалить&gt; элемент для &lt;namedCaches&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: ceeef00cb688c725cc595582fb6845b9e3fa9b92
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083396"
---
# <a name="ltremovegt-element-for-ltnamedcachesgt"></a><span data-ttu-id="4f23f-102">&lt;Удалить&gt; элемент для &lt;namedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="4f23f-102">&lt;remove&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="4f23f-103">Удаляет элемент именованного кэша из коллекции `namedCaches` для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="4f23f-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="4f23f-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="4f23f-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="4f23f-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="4f23f-105">\<memoryCache></span></span>  
<span data-ttu-id="4f23f-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="4f23f-106">\<namedCaches></span></span>  
<span data-ttu-id="4f23f-107">\<Удалить ></span><span class="sxs-lookup"><span data-stu-id="4f23f-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f23f-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f23f-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="4f23f-109">Тип</span><span class="sxs-lookup"><span data-stu-id="4f23f-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f23f-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4f23f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4f23f-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4f23f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f23f-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4f23f-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="4f23f-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4f23f-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="4f23f-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4f23f-114">Parent Elements</span></span>  
  
|<span data-ttu-id="4f23f-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="4f23f-115">Element</span></span>|<span data-ttu-id="4f23f-116">Описание</span><span class="sxs-lookup"><span data-stu-id="4f23f-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f23f-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="4f23f-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="4f23f-118">Содержит коллекцию параметров конфигурации для именованного <xref:System.Runtime.Caching.MemoryCache> экземпляров.</span><span class="sxs-lookup"><span data-stu-id="4f23f-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f23f-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="4f23f-119">Remarks</span></span>  
 <span data-ttu-id="4f23f-120">`remove` Приводит к удалению `namedCache` запись из коллекции именованных кэшей для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="4f23f-120">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f23f-121">См. также</span><span class="sxs-lookup"><span data-stu-id="4f23f-121">See also</span></span>
- [<span data-ttu-id="4f23f-122">\<namedCaches > (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="4f23f-122">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
