---
title: Элемент <add> для <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: fd6668a551663470a97b07ff131710dbe92a91f5
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659030"
---
# <a name="add-element-for-namedcaches"></a><span data-ttu-id="ea1a8-102">\<Добавление элемента > для \<намедкачес ></span><span class="sxs-lookup"><span data-stu-id="ea1a8-102">\<add> Element for \<namedCaches></span></span>
<span data-ttu-id="ea1a8-103">`namedCache` Добавляет запись`namedCaches` в коллекцию для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="ea1a8-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="ea1a8-104">\<System. Runtime. Caching ></span><span class="sxs-lookup"><span data-stu-id="ea1a8-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="ea1a8-105">\<memoryCache ></span><span class="sxs-lookup"><span data-stu-id="ea1a8-105">\<memoryCache></span></span>  
<span data-ttu-id="ea1a8-106">\<Намедкачес ></span><span class="sxs-lookup"><span data-stu-id="ea1a8-106">\<namedCaches></span></span>  
<span data-ttu-id="ea1a8-107">\<add></span><span class="sxs-lookup"><span data-stu-id="ea1a8-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea1a8-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ea1a8-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="ea1a8-109">Тип</span><span class="sxs-lookup"><span data-stu-id="ea1a8-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea1a8-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ea1a8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ea1a8-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ea1a8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea1a8-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ea1a8-112">Attributes</span></span>  
  
|<span data-ttu-id="ea1a8-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ea1a8-113">Attribute</span></span>|<span data-ttu-id="ea1a8-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ea1a8-114">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="ea1a8-115">Целочисленное значение, указывающее максимально допустимый размер (в мегабайтах), до которого <xref:System.Runtime.Caching.MemoryCache> может увеличиваться экземпляр.</span><span class="sxs-lookup"><span data-stu-id="ea1a8-115">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="ea1a8-116">Значение по умолчанию — 0. Это означает, <xref:System.Runtime.Caching.MemoryCache> что по умолчанию используется эвристика автоопределения размеров класса.</span><span class="sxs-lookup"><span data-stu-id="ea1a8-116">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="ea1a8-117">Имя кэша.</span><span class="sxs-lookup"><span data-stu-id="ea1a8-117">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="ea1a8-118">Целочисленное значение от 0 до 100, которое указывает максимальный процент физической памяти компьютера, который может потребляться кэшем.</span><span class="sxs-lookup"><span data-stu-id="ea1a8-118">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="ea1a8-119">Значение по умолчанию — 0. Это означает, <xref:System.Runtime.Caching.MemoryCache> что по умолчанию используется эвристика автоопределения размеров класса.</span><span class="sxs-lookup"><span data-stu-id="ea1a8-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="ea1a8-120">Значение, указывающее интервал, по истечении которого реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями по памяти, заданными для данного экземпляра кэша.</span><span class="sxs-lookup"><span data-stu-id="ea1a8-120">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="ea1a8-121">Это значение указывается в формате "чч: мм: СС".</span><span class="sxs-lookup"><span data-stu-id="ea1a8-121">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ea1a8-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ea1a8-122">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="ea1a8-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ea1a8-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ea1a8-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="ea1a8-124">Element</span></span>|<span data-ttu-id="ea1a8-125">Описание</span><span class="sxs-lookup"><span data-stu-id="ea1a8-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea1a8-126">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="ea1a8-126">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="ea1a8-127">Содержит коллекцию параметров конфигурации для именованных <xref:System.Runtime.Caching.MemoryCache> экземпляров.</span><span class="sxs-lookup"><span data-stu-id="ea1a8-127">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea1a8-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="ea1a8-128">Remarks</span></span>  
 <span data-ttu-id="ea1a8-129">Элемент добавляет запись `namedCaches` в коллекцию для кэша памяти. `add`</span><span class="sxs-lookup"><span data-stu-id="ea1a8-129">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="ea1a8-130">Элемент [clear](clear-element-for-namedcaches.md) можно использовать перед тем, как использовать `add` элемент, чтобы убедиться в отсутствии других именованных кэшей в коллекции.</span><span class="sxs-lookup"><span data-stu-id="ea1a8-130">You can use the [clear](clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="ea1a8-131">Этот элемент можно использовать в файле Machine. config и в файле Web. config.</span><span class="sxs-lookup"><span data-stu-id="ea1a8-131">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea1a8-132">Пример</span><span class="sxs-lookup"><span data-stu-id="ea1a8-132">Example</span></span>  
 <span data-ttu-id="ea1a8-133">В следующем примере показано, как определить параметры для записи `namedCache` `namedCaches` по умолчанию в коллекцию для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="ea1a8-133">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ea1a8-134">См. также</span><span class="sxs-lookup"><span data-stu-id="ea1a8-134">See also</span></span>

- [<span data-ttu-id="ea1a8-135">\<Элемент > Намедкачес (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="ea1a8-135">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
