---
title: Элемент <add> для <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: b0487ba5025557f07d9991f911cd71a677a04e2c
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423378"
---
# <a name="add-element-for-namedcaches"></a><span data-ttu-id="672cb-102">\<Добавить > элемент для \<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="672cb-102">\<add> Element for \<namedCaches></span></span>
<span data-ttu-id="672cb-103">Добавляет `namedCache` запись `namedCaches` коллекции для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="672cb-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="672cb-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="672cb-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="672cb-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="672cb-105">\<memoryCache></span></span>  
<span data-ttu-id="672cb-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="672cb-106">\<namedCaches></span></span>  
<span data-ttu-id="672cb-107">\<add></span><span class="sxs-lookup"><span data-stu-id="672cb-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="672cb-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="672cb-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="672cb-109">Тип</span><span class="sxs-lookup"><span data-stu-id="672cb-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="672cb-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="672cb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="672cb-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="672cb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="672cb-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="672cb-112">Attributes</span></span>  
  
|<span data-ttu-id="672cb-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="672cb-113">Attribute</span></span>|<span data-ttu-id="672cb-114">Описание</span><span class="sxs-lookup"><span data-stu-id="672cb-114">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="672cb-115">Целочисленное значение, указывающее максимально допустимый размер (в мегабайтах), экземпляр <xref:System.Runtime.Caching.MemoryCache> может увеличиться.</span><span class="sxs-lookup"><span data-stu-id="672cb-115">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="672cb-116">Значение по умолчанию — 0, это означает, что <xref:System.Runtime.Caching.MemoryCache> класса эвристические методы, используемые по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="672cb-116">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="672cb-117">Имя кэша.</span><span class="sxs-lookup"><span data-stu-id="672cb-117">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="672cb-118">Целочисленное значение от 0 до 100, указывающее максимальную долю физической памяти, который может использоваться кэшем.</span><span class="sxs-lookup"><span data-stu-id="672cb-118">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="672cb-119">Значение по умолчанию — 0, это означает, что <xref:System.Runtime.Caching.MemoryCache> класса эвристические методы, используемые по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="672cb-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="672cb-120">Значение, указывающее интервал, по истечении которого реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями по памяти, заданными для данного экземпляра кэша.</span><span class="sxs-lookup"><span data-stu-id="672cb-120">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="672cb-121">Это значение вводится в формате «Чч: мм:».</span><span class="sxs-lookup"><span data-stu-id="672cb-121">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="672cb-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="672cb-122">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="672cb-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="672cb-123">Parent Elements</span></span>  
  
|<span data-ttu-id="672cb-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="672cb-124">Element</span></span>|<span data-ttu-id="672cb-125">Описание</span><span class="sxs-lookup"><span data-stu-id="672cb-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="672cb-126">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="672cb-126">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="672cb-127">Содержит коллекцию параметров конфигурации для именованного <xref:System.Runtime.Caching.MemoryCache> экземпляров.</span><span class="sxs-lookup"><span data-stu-id="672cb-127">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="672cb-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="672cb-128">Remarks</span></span>  
 <span data-ttu-id="672cb-129">`add` Элемент добавляет запись в `namedCaches` коллекции для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="672cb-129">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="672cb-130">Можно использовать [снимите](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) элемент, прежде чем использовать `add` элемент, чтобы быть уверенным, что никакие другие именованные кэши в коллекции.</span><span class="sxs-lookup"><span data-stu-id="672cb-130">You can use the [clear](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="672cb-131">Этот элемент может использоваться в файле machine.config и в файле Web.config.</span><span class="sxs-lookup"><span data-stu-id="672cb-131">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="672cb-132">Пример</span><span class="sxs-lookup"><span data-stu-id="672cb-132">Example</span></span>  
 <span data-ttu-id="672cb-133">В следующем примере показано, как для определения параметров по умолчанию `namedCache` запись `namedCaches` коллекции для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="672cb-133">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="672cb-134">См. также</span><span class="sxs-lookup"><span data-stu-id="672cb-134">See also</span></span>

- [<span data-ttu-id="672cb-135">\<namedCaches > (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="672cb-135">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
