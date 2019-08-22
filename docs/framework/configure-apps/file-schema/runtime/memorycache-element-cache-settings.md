---
title: Элемент <memoryCache> (параметры кэша)
ms.date: 03/30/2017
helpviewer_keywords:
- <memoryCache> element
- caching [.NET Framework], configuration
- memoryCache element
ms.assetid: 182a622f-f7cf-472d-9d0b-451d2fd94525
ms.openlocfilehash: 46f430f7cf112da40aa3b25bfb280c5014612eae
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663622"
---
# <a name="memorycache-element-cache-settings"></a><span data-ttu-id="afa23-102">\<Элемент > memoryCache (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="afa23-102">\<memoryCache> Element (Cache Settings)</span></span>
<span data-ttu-id="afa23-103">Определяет элемент, используемый для настройки кэша, который основан на классе <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="afa23-103">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="afa23-104">Класс <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> определяет элемент [memoryCache](memorycache-element-cache-settings.md) , который можно использовать для настройки кэша.</span><span class="sxs-lookup"><span data-stu-id="afa23-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> class defines a [memoryCache](memorycache-element-cache-settings.md) element that you can use to configure the cache.</span></span> <span data-ttu-id="afa23-105">В одном приложении может использоваться несколько экземпляров класса <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="afa23-105">Multiple instances of the <xref:System.Runtime.Caching.MemoryCache> class can be used in a single application.</span></span> <span data-ttu-id="afa23-106">Каждый элемент `memoryCache` в файле конфигурации может содержать параметры для именованного экземпляра <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="afa23-106">Each `memoryCache` element in the configuration file can contain settings for a named <xref:System.Runtime.Caching.MemoryCache> instance.</span></span>  
  
 <span data-ttu-id="afa23-107">\<configuration></span><span class="sxs-lookup"><span data-stu-id="afa23-107">\<configuration></span></span>  
<span data-ttu-id="afa23-108">\<System. Runtime. Caching ></span><span class="sxs-lookup"><span data-stu-id="afa23-108">\<system.runtime.caching></span></span>  
<span data-ttu-id="afa23-109">\<memoryCache ></span><span class="sxs-lookup"><span data-stu-id="afa23-109">\<memoryCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afa23-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="afa23-110">Syntax</span></span>  
  
```xml  
<memoryCache>   
    <namedCaches>  
        <!-- child elements -->  
    </namedCaches>   
</memoryCache>  
```  
  
## <a name="type"></a><span data-ttu-id="afa23-111">Тип</span><span class="sxs-lookup"><span data-stu-id="afa23-111">Type</span></span>  
 <span data-ttu-id="afa23-112">Класс<xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="afa23-112"><xref:System.Runtime.Caching.MemoryCache> class.</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="afa23-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="afa23-113">Attributes and Elements</span></span>  
 <span data-ttu-id="afa23-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="afa23-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="afa23-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="afa23-115">Attributes</span></span>  
  
|<span data-ttu-id="afa23-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="afa23-116">Attribute</span></span>|<span data-ttu-id="afa23-117">Описание</span><span class="sxs-lookup"><span data-stu-id="afa23-117">Description</span></span>|  
|---------------|-----------------|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="afa23-118">Максимальный объем памяти в мегабайтах, который может занимать экземпляр объекта <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="afa23-118">The maximum memory size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> object can grow to.</span></span> <span data-ttu-id="afa23-119">Значение по умолчанию — 0. Это означает, что эвристика автомасштабирования класса <xref:System.Runtime.Caching.MemoryCache> используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="afa23-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="afa23-120">Имя конфигурации кэша.</span><span class="sxs-lookup"><span data-stu-id="afa23-120">The name of the cache configuration.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="afa23-121">Процент физической памяти, который может использоваться кэшем.</span><span class="sxs-lookup"><span data-stu-id="afa23-121">The percentage of physical memory that can be used by the cache.</span></span> <span data-ttu-id="afa23-122">Значение по умолчанию — 0. Это означает, что эвристика автомасштабирования класса <xref:System.Runtime.Caching.MemoryCache> используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="afa23-122">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="afa23-123">Значение, указывающее интервал, по истечении которого реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями по памяти, заданными для данного экземпляра кэша.</span><span class="sxs-lookup"><span data-stu-id="afa23-123">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="afa23-124">Значение вводится в формате "ЧЧ:ММ:СС".</span><span class="sxs-lookup"><span data-stu-id="afa23-124">The value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="afa23-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="afa23-125">Child Elements</span></span>  
  
|<span data-ttu-id="afa23-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="afa23-126">Element</span></span>|<span data-ttu-id="afa23-127">Описание</span><span class="sxs-lookup"><span data-stu-id="afa23-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="afa23-128">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="afa23-128">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="afa23-129">Содержит коллекцию параметров конфигурации для экземпляра `namedCache` .</span><span class="sxs-lookup"><span data-stu-id="afa23-129">Contains a collection of configuration settings for the `namedCache` instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="afa23-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="afa23-130">Parent Elements</span></span>  
  
|<span data-ttu-id="afa23-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="afa23-131">Element</span></span>|<span data-ttu-id="afa23-132">Описание</span><span class="sxs-lookup"><span data-stu-id="afa23-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="afa23-133">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="afa23-133">\<system.runtime.caching></span></span>](system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="afa23-134">Содержит типы, позволяющие реализовать кэширование вывода в приложениях, встроенных в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="afa23-134">Contains types that let you implement output caching in applications that are built into the .NET Framework.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="afa23-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="afa23-135">Remarks</span></span>  
 <span data-ttu-id="afa23-136">Класс <xref:System.Runtime.Caching.MemoryCache> — это конкретная реализация абстрактного класса <xref:System.Runtime.Caching.ObjectCache> .</span><span class="sxs-lookup"><span data-stu-id="afa23-136">The <xref:System.Runtime.Caching.MemoryCache> class is a concrete implementation of the abstract <xref:System.Runtime.Caching.ObjectCache> class.</span></span> <span data-ttu-id="afa23-137">Экземпляры класса <xref:System.Runtime.Caching.MemoryCache> можно снабдить сведениями о конфигурации из файлов конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="afa23-137">Instances of the <xref:System.Runtime.Caching.MemoryCache> class can be supplied with configuration information from application configuration files.</span></span> <span data-ttu-id="afa23-138">Раздел конфигурации [MemoryCache](memorycache-element-cache-settings.md) содержит коллекцию конфигураций `namedCaches` .</span><span class="sxs-lookup"><span data-stu-id="afa23-138">The [memoryCache](memorycache-element-cache-settings.md) configuration section contains a `namedCaches` configuration collection.</span></span>  
  
 <span data-ttu-id="afa23-139">При инициализации объекта кэша на базе памяти он сначала пытается найти запись `namedCaches` , которая соответствует имени в параметре, передаваемом конструктору кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="afa23-139">When a memory-based cache object is initialized, it first tries to find a `namedCaches` entry that matches the name in the parameter that is passed to the memory cache constructor.</span></span> <span data-ttu-id="afa23-140">Если запись `namedCaches` найдена, из файла конфигурации извлекаются сведения об опросах и управлении памятью.</span><span class="sxs-lookup"><span data-stu-id="afa23-140">If a `namedCaches` entry is found, the polling and memory-management information are retrieved from the configuration file.</span></span>  
  
 <span data-ttu-id="afa23-141">После этого процесс инициализации определяет, были ли переопределены какие-либо записи конфигурации, с помощью дополнительной коллекцию пар имя-значение для сведений о конфигурации в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="afa23-141">The initialization process then determines whether any configuration entries were overridden, by using the optional collection of name/value pairs of configuration information in the constructor.</span></span> <span data-ttu-id="afa23-142">Если передать в коллекцию пар имя-значение любое из следующих значений, оно переопределит сведения, полученные из файла конфигурации:</span><span class="sxs-lookup"><span data-stu-id="afa23-142">If you pass any one of the following values in the name/value pair collection, these values override information obtained from the configuration file:</span></span>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.CacheMemoryLimitMegabytes%2A>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.PhysicalMemoryLimitPercentage%2A>  
  
- <xref:System.Runtime.Caching.MemoryCache.PollingInterval%2A>  
  
## <a name="example"></a><span data-ttu-id="afa23-143">Пример</span><span class="sxs-lookup"><span data-stu-id="afa23-143">Example</span></span>  
 <span data-ttu-id="afa23-144">В следующем примере показано, как задать имя <xref:System.Runtime.Caching.MemoryCache> объекта в качестве имени объекта кэша по умолчанию, `name` задав для атрибута значение Default.</span><span class="sxs-lookup"><span data-stu-id="afa23-144">The following example shows how to set the name of the <xref:System.Runtime.Caching.MemoryCache> object to the default cache object name by setting the `name` attribute to "Default".</span></span>  
  
 <span data-ttu-id="afa23-145">Атрибутам `cacheMemoryLimitMegabytes` и `physicalMemoryLimitPercentage` присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="afa23-145">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryLimitPercentage` attribute are set to zero.</span></span> <span data-ttu-id="afa23-146">Это означает, что эвристика автомасштабирования <xref:System.Runtime.Caching.MemoryCache> используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="afa23-146">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="afa23-147">Реализация кэша должна каждые две минуты сравнивать текущую загрузку памяти с абсолютными и процентными ограничениями по памяти.</span><span class="sxs-lookup"><span data-stu-id="afa23-147">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
```xml  
<configuration>  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="afa23-148">См. также</span><span class="sxs-lookup"><span data-stu-id="afa23-148">See also</span></span>

- <xref:System.Runtime.Caching.MemoryCache>
- [<span data-ttu-id="afa23-149">\<Элемент System. Runtime. Caching > (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="afa23-149">\<system.runtime.caching> Element (Cache Settings)</span></span>](system-runtime-caching-element-cache-settings.md)
- [<span data-ttu-id="afa23-150">\<Элемент > Намедкачес (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="afa23-150">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
