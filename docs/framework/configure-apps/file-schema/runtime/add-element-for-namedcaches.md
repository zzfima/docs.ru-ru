---
title: Элемент <add> для <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: 076d940e0c15cf48013480fef68b8fac42cf76e9
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252892"
---
# <a name="add-element-for-namedcaches"></a><span data-ttu-id="f16f2-102">\<Добавление элемента > для \<намедкачес ></span><span class="sxs-lookup"><span data-stu-id="f16f2-102">\<add> Element for \<namedCaches></span></span>
<span data-ttu-id="f16f2-103">`namedCache` Добавляет запись`namedCaches` в коллекцию для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="f16f2-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
<span data-ttu-id="f16f2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f16f2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f16f2-105">&nbsp;&nbsp;[ **\<System. Runtime. Caching >** ](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f16f2-105">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="f16f2-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<memoryCache >** ](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f16f2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="f16f2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Намедкачес >** ](namedcaches-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f16f2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)</span></span>\
<span data-ttu-id="f16f2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Добавить >**</span><span class="sxs-lookup"><span data-stu-id="f16f2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f16f2-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f16f2-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="f16f2-110">Тип</span><span class="sxs-lookup"><span data-stu-id="f16f2-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f16f2-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f16f2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f16f2-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f16f2-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f16f2-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f16f2-113">Attributes</span></span>  
  
|<span data-ttu-id="f16f2-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f16f2-114">Attribute</span></span>|<span data-ttu-id="f16f2-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f16f2-115">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="f16f2-116">Целочисленное значение, указывающее максимально допустимый размер (в мегабайтах), до которого <xref:System.Runtime.Caching.MemoryCache> может увеличиваться экземпляр.</span><span class="sxs-lookup"><span data-stu-id="f16f2-116">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="f16f2-117">Значение по умолчанию — 0. Это означает, <xref:System.Runtime.Caching.MemoryCache> что по умолчанию используется эвристика автоопределения размеров класса.</span><span class="sxs-lookup"><span data-stu-id="f16f2-117">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="f16f2-118">Имя кэша.</span><span class="sxs-lookup"><span data-stu-id="f16f2-118">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="f16f2-119">Целочисленное значение от 0 до 100, которое указывает максимальный процент физической памяти компьютера, который может потребляться кэшем.</span><span class="sxs-lookup"><span data-stu-id="f16f2-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="f16f2-120">Значение по умолчанию — 0. Это означает, <xref:System.Runtime.Caching.MemoryCache> что по умолчанию используется эвристика автоопределения размеров класса.</span><span class="sxs-lookup"><span data-stu-id="f16f2-120">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="f16f2-121">Значение, указывающее интервал, по истечении которого реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями по памяти, заданными для данного экземпляра кэша.</span><span class="sxs-lookup"><span data-stu-id="f16f2-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="f16f2-122">Это значение указывается в формате "чч: мм: СС".</span><span class="sxs-lookup"><span data-stu-id="f16f2-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f16f2-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f16f2-123">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="f16f2-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f16f2-124">Parent Elements</span></span>  
  
|<span data-ttu-id="f16f2-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="f16f2-125">Element</span></span>|<span data-ttu-id="f16f2-126">Описание</span><span class="sxs-lookup"><span data-stu-id="f16f2-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f16f2-127">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="f16f2-127">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="f16f2-128">Содержит коллекцию параметров конфигурации для именованных <xref:System.Runtime.Caching.MemoryCache> экземпляров.</span><span class="sxs-lookup"><span data-stu-id="f16f2-128">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f16f2-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="f16f2-129">Remarks</span></span>  
 <span data-ttu-id="f16f2-130">Элемент добавляет запись `namedCaches` в коллекцию для кэша памяти. `add`</span><span class="sxs-lookup"><span data-stu-id="f16f2-130">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="f16f2-131">Элемент [clear](clear-element-for-namedcaches.md) можно использовать перед тем, как использовать `add` элемент, чтобы убедиться в отсутствии других именованных кэшей в коллекции.</span><span class="sxs-lookup"><span data-stu-id="f16f2-131">You can use the [clear](clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="f16f2-132">Этот элемент можно использовать в файле Machine. config и в файле Web. config.</span><span class="sxs-lookup"><span data-stu-id="f16f2-132">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f16f2-133">Пример</span><span class="sxs-lookup"><span data-stu-id="f16f2-133">Example</span></span>  
 <span data-ttu-id="f16f2-134">В следующем примере показано, как определить параметры для записи `namedCache` `namedCaches` по умолчанию в коллекцию для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="f16f2-134">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f16f2-135">См. также</span><span class="sxs-lookup"><span data-stu-id="f16f2-135">See also</span></span>

- [<span data-ttu-id="f16f2-136">\<Элемент > Намедкачес (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="f16f2-136">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
