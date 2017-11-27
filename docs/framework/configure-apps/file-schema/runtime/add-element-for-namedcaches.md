---
title: "&lt;Добавить&gt; элемент для &lt;namedCaches&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 0baafcb53bf79a25618dad56c2dcf1412e48624b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltaddgt-element-for-ltnamedcachesgt"></a><span data-ttu-id="2c1c6-102">&lt;Добавить&gt; элемент для &lt;namedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="2c1c6-102">&lt;add&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="2c1c6-103">Добавляет `namedCache` запись `namedCaches` коллекции для кэш-памяти.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="2c1c6-104">\<System.Runtime.Caching ></span><span class="sxs-lookup"><span data-stu-id="2c1c6-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="2c1c6-105">\<memoryCache ></span><span class="sxs-lookup"><span data-stu-id="2c1c6-105">\<memoryCache></span></span>  
<span data-ttu-id="2c1c6-106">\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="2c1c6-106">\<namedCaches></span></span>  
<span data-ttu-id="2c1c6-107">\<add></span><span class="sxs-lookup"><span data-stu-id="2c1c6-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c1c6-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2c1c6-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="2c1c6-109">Тип</span><span class="sxs-lookup"><span data-stu-id="2c1c6-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c1c6-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2c1c6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2c1c6-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c1c6-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2c1c6-112">Attributes</span></span>  
  
|<span data-ttu-id="2c1c6-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2c1c6-113">Attribute</span></span>|<span data-ttu-id="2c1c6-114">Описание</span><span class="sxs-lookup"><span data-stu-id="2c1c6-114">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="2c1c6-115">Целочисленное значение, указывающее максимально допустимый размер (в мегабайтах), экземпляр <xref:System.Runtime.Caching.MemoryCache> могут увеличиваться до.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-115">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="2c1c6-116">Значение по умолчанию — 0, это означает, что <xref:System.Runtime.Caching.MemoryCache> эвристические методы класса используются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-116">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="2c1c6-117">Имя кэша.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-117">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="2c1c6-118">Целочисленное значение от 0 до 100, указывающее максимальную долю физической памяти, может использоваться кэшем.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-118">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="2c1c6-119">Значение по умолчанию — 0, это означает, что <xref:System.Runtime.Caching.MemoryCache> эвристические методы класса используются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="2c1c6-120">Значение, указывающее интервал, по истечении которого реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями по памяти, заданными для данного экземпляра кэша.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-120">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="2c1c6-121">Это значение вводится в формате «Чч».</span><span class="sxs-lookup"><span data-stu-id="2c1c6-121">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2c1c6-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2c1c6-122">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="2c1c6-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2c1c6-123">Parent Elements</span></span>  
  
|<span data-ttu-id="2c1c6-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="2c1c6-124">Element</span></span>|<span data-ttu-id="2c1c6-125">Описание</span><span class="sxs-lookup"><span data-stu-id="2c1c6-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c1c6-126">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="2c1c6-126">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="2c1c6-127">Содержит коллекцию параметров конфигурации для именованного <xref:System.Runtime.Caching.MemoryCache> экземпляров.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-127">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c1c6-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="2c1c6-128">Remarks</span></span>  
 <span data-ttu-id="2c1c6-129">`add` Элемент добавляет запись `namedCaches` коллекции для кэш-памяти.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-129">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="2c1c6-130">Можно использовать [снимите](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) элемент, прежде чем использовать `add` элемент, чтобы быть уверенным, что никакие другие именованные кэши в коллекции.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-130">You can use the [clear](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="2c1c6-131">Этот элемент может использоваться в файле machine.config и в файле Web.config.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-131">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c1c6-132">Пример</span><span class="sxs-lookup"><span data-stu-id="2c1c6-132">Example</span></span>  
 <span data-ttu-id="2c1c6-133">В следующем примере показано, как для определения параметров по умолчанию `namedCache` запись `namedCaches` коллекции для кэш-памяти.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-133">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2c1c6-134">См. также</span><span class="sxs-lookup"><span data-stu-id="2c1c6-134">See Also</span></span>  
 [<span data-ttu-id="2c1c6-135">\<namedCaches > элемент (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="2c1c6-135">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
