---
title: '&lt;Добавить&gt; элемент для &lt;namedCaches&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d65dfd9a1560f2657f48b327277b64ab77014b47
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-element-for-ltnamedcachesgt"></a><span data-ttu-id="82f09-102">&lt;Добавить&gt; элемент для &lt;namedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="82f09-102">&lt;add&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="82f09-103">Добавляет `namedCache` запись `namedCaches` коллекции для кэш-памяти.</span><span class="sxs-lookup"><span data-stu-id="82f09-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="82f09-104">\<System.Runtime.Caching ></span><span class="sxs-lookup"><span data-stu-id="82f09-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="82f09-105">\<memoryCache ></span><span class="sxs-lookup"><span data-stu-id="82f09-105">\<memoryCache></span></span>  
<span data-ttu-id="82f09-106">\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="82f09-106">\<namedCaches></span></span>  
<span data-ttu-id="82f09-107">\<add></span><span class="sxs-lookup"><span data-stu-id="82f09-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82f09-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82f09-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="82f09-109">Тип</span><span class="sxs-lookup"><span data-stu-id="82f09-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82f09-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="82f09-110">Attributes and Elements</span></span>  
 <span data-ttu-id="82f09-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="82f09-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82f09-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="82f09-112">Attributes</span></span>  
  
|<span data-ttu-id="82f09-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="82f09-113">Attribute</span></span>|<span data-ttu-id="82f09-114">Описание</span><span class="sxs-lookup"><span data-stu-id="82f09-114">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="82f09-115">Целочисленное значение, указывающее максимально допустимый размер (в мегабайтах), экземпляр <xref:System.Runtime.Caching.MemoryCache> могут увеличиваться до.</span><span class="sxs-lookup"><span data-stu-id="82f09-115">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="82f09-116">Значение по умолчанию — 0, это означает, что <xref:System.Runtime.Caching.MemoryCache> эвристические методы класса используются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="82f09-116">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="82f09-117">Имя кэша.</span><span class="sxs-lookup"><span data-stu-id="82f09-117">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="82f09-118">Целочисленное значение от 0 до 100, указывающее максимальную долю физической памяти, может использоваться кэшем.</span><span class="sxs-lookup"><span data-stu-id="82f09-118">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="82f09-119">Значение по умолчанию — 0, это означает, что <xref:System.Runtime.Caching.MemoryCache> эвристические методы класса используются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="82f09-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="82f09-120">Значение, указывающее интервал, по истечении которого реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями по памяти, заданными для данного экземпляра кэша.</span><span class="sxs-lookup"><span data-stu-id="82f09-120">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="82f09-121">Это значение вводится в формате «Чч».</span><span class="sxs-lookup"><span data-stu-id="82f09-121">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="82f09-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="82f09-122">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="82f09-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="82f09-123">Parent Elements</span></span>  
  
|<span data-ttu-id="82f09-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="82f09-124">Element</span></span>|<span data-ttu-id="82f09-125">Описание</span><span class="sxs-lookup"><span data-stu-id="82f09-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="82f09-126">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="82f09-126">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="82f09-127">Содержит коллекцию параметров конфигурации для именованного <xref:System.Runtime.Caching.MemoryCache> экземпляров.</span><span class="sxs-lookup"><span data-stu-id="82f09-127">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82f09-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="82f09-128">Remarks</span></span>  
 <span data-ttu-id="82f09-129">`add` Элемент добавляет запись `namedCaches` коллекции для кэш-памяти.</span><span class="sxs-lookup"><span data-stu-id="82f09-129">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="82f09-130">Можно использовать [снимите](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) элемент, прежде чем использовать `add` элемент, чтобы быть уверенным, что никакие другие именованные кэши в коллекции.</span><span class="sxs-lookup"><span data-stu-id="82f09-130">You can use the [clear](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="82f09-131">Этот элемент может использоваться в файле machine.config и в файле Web.config.</span><span class="sxs-lookup"><span data-stu-id="82f09-131">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82f09-132">Пример</span><span class="sxs-lookup"><span data-stu-id="82f09-132">Example</span></span>  
 <span data-ttu-id="82f09-133">В следующем примере показано, как для определения параметров по умолчанию `namedCache` запись `namedCaches` коллекции для кэш-памяти.</span><span class="sxs-lookup"><span data-stu-id="82f09-133">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="82f09-134">См. также</span><span class="sxs-lookup"><span data-stu-id="82f09-134">See Also</span></span>  
 [<span data-ttu-id="82f09-135">\<namedCaches > элемент (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="82f09-135">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
