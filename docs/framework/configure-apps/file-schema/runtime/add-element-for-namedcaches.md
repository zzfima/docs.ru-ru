---
title: Элемент <add> для <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: cbe7c98e9603e51aa381f07ea35ffe46e6d3adfb
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257364"
---
# <a name="add-element-for-namedcaches"></a><span data-ttu-id="83004-102">\<Добавить > элемент для \<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="83004-102">\<add> Element for \<namedCaches></span></span>
<span data-ttu-id="83004-103">Добавляет `namedCache` запись `namedCaches` коллекции для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="83004-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="83004-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="83004-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="83004-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="83004-105">\<memoryCache></span></span>  
<span data-ttu-id="83004-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="83004-106">\<namedCaches></span></span>  
<span data-ttu-id="83004-107">\<add></span><span class="sxs-lookup"><span data-stu-id="83004-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83004-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83004-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="83004-109">Тип</span><span class="sxs-lookup"><span data-stu-id="83004-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83004-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="83004-110">Attributes and Elements</span></span>  
 <span data-ttu-id="83004-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="83004-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83004-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="83004-112">Attributes</span></span>  
  
|<span data-ttu-id="83004-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="83004-113">Attribute</span></span>|<span data-ttu-id="83004-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="83004-114">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="83004-115">Целочисленное значение, указывающее максимально допустимый размер (в мегабайтах), экземпляр <xref:System.Runtime.Caching.MemoryCache> может увеличиться.</span><span class="sxs-lookup"><span data-stu-id="83004-115">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="83004-116">Значение по умолчанию — 0, это означает, что <xref:System.Runtime.Caching.MemoryCache> класса эвристические методы, используемые по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="83004-116">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="83004-117">Имя кэша.</span><span class="sxs-lookup"><span data-stu-id="83004-117">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="83004-118">Целочисленное значение от 0 до 100, указывающее максимальную долю физической памяти, который может использоваться кэшем.</span><span class="sxs-lookup"><span data-stu-id="83004-118">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="83004-119">Значение по умолчанию — 0, это означает, что <xref:System.Runtime.Caching.MemoryCache> класса эвристические методы, используемые по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="83004-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="83004-120">Значение, указывающее интервал, по истечении которого реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями по памяти, заданными для данного экземпляра кэша.</span><span class="sxs-lookup"><span data-stu-id="83004-120">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="83004-121">Это значение вводится в формате «Чч: мм:».</span><span class="sxs-lookup"><span data-stu-id="83004-121">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="83004-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="83004-122">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="83004-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="83004-123">Parent Elements</span></span>  
  
|<span data-ttu-id="83004-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="83004-124">Element</span></span>|<span data-ttu-id="83004-125">Описание:</span><span class="sxs-lookup"><span data-stu-id="83004-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="83004-126">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="83004-126">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="83004-127">Содержит коллекцию параметров конфигурации для именованного <xref:System.Runtime.Caching.MemoryCache> экземпляров.</span><span class="sxs-lookup"><span data-stu-id="83004-127">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83004-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="83004-128">Remarks</span></span>  
 <span data-ttu-id="83004-129">`add` Элемент добавляет запись в `namedCaches` коллекции для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="83004-129">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="83004-130">Можно использовать [снимите](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) элемент, прежде чем использовать `add` элемент, чтобы быть уверенным, что никакие другие именованные кэши в коллекции.</span><span class="sxs-lookup"><span data-stu-id="83004-130">You can use the [clear](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="83004-131">Этот элемент может использоваться в файле machine.config и в файле Web.config.</span><span class="sxs-lookup"><span data-stu-id="83004-131">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83004-132">Пример</span><span class="sxs-lookup"><span data-stu-id="83004-132">Example</span></span>  
 <span data-ttu-id="83004-133">В следующем примере показано, как для определения параметров по умолчанию `namedCache` запись `namedCaches` коллекции для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="83004-133">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="83004-134">См. также</span><span class="sxs-lookup"><span data-stu-id="83004-134">See also</span></span>
- [<span data-ttu-id="83004-135">\<namedCaches > (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="83004-135">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
