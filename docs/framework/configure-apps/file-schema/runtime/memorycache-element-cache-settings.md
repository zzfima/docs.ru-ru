---
title: Элемент <memoryCache> (параметры кэша)
ms.date: 03/30/2017
helpviewer_keywords:
- <memoryCache> element
- caching [.NET Framework], configuration
- memoryCache element
ms.assetid: 182a622f-f7cf-472d-9d0b-451d2fd94525
ms.openlocfilehash: 25e87aa9fa4e56c5042eb25c41f6cfe1b65aea24
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266381"
---
# <a name="memorycache-element-cache-settings"></a><span data-ttu-id="cfab1-102">\<memoryCache > (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="cfab1-102">\<memoryCache> Element (Cache Settings)</span></span>
<span data-ttu-id="cfab1-103">Определяет элемент, используемый для настройки кэша, который основан на классе <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="cfab1-103">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="cfab1-104">Класс <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> определяет элемент [memoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) , который можно использовать для настройки кэша.</span><span class="sxs-lookup"><span data-stu-id="cfab1-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> class defines a [memoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) element that you can use to configure the cache.</span></span> <span data-ttu-id="cfab1-105">В одном приложении может использоваться несколько экземпляров класса <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="cfab1-105">Multiple instances of the <xref:System.Runtime.Caching.MemoryCache> class can be used in a single application.</span></span> <span data-ttu-id="cfab1-106">Каждый элемент `memoryCache` в файле конфигурации может содержать параметры для именованного экземпляра <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="cfab1-106">Each `memoryCache` element in the configuration file can contain settings for a named <xref:System.Runtime.Caching.MemoryCache> instance.</span></span>  
  
 <span data-ttu-id="cfab1-107">\<configuration></span><span class="sxs-lookup"><span data-stu-id="cfab1-107">\<configuration></span></span>  
<span data-ttu-id="cfab1-108">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="cfab1-108">\<system.runtime.caching></span></span>  
<span data-ttu-id="cfab1-109">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="cfab1-109">\<memoryCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfab1-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cfab1-110">Syntax</span></span>  
  
```xml  
<memoryCache>   
    <namedCaches>  
        <!-- child elements -->  
    </namedCaches>   
</memoryCache>  
```  
  
## <a name="type"></a><span data-ttu-id="cfab1-111">Тип</span><span class="sxs-lookup"><span data-stu-id="cfab1-111">Type</span></span>  
 <span data-ttu-id="cfab1-112">Класс<xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="cfab1-112"><xref:System.Runtime.Caching.MemoryCache> class.</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cfab1-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cfab1-113">Attributes and Elements</span></span>  
 <span data-ttu-id="cfab1-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cfab1-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cfab1-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cfab1-115">Attributes</span></span>  
  
|<span data-ttu-id="cfab1-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="cfab1-116">Attribute</span></span>|<span data-ttu-id="cfab1-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="cfab1-117">Description</span></span>|  
|---------------|-----------------|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="cfab1-118">Максимальный объем памяти в мегабайтах, который может занимать экземпляр объекта <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="cfab1-118">The maximum memory size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> object can grow to.</span></span> <span data-ttu-id="cfab1-119">Значение по умолчанию — 0. Это означает, что эвристика автомасштабирования класса <xref:System.Runtime.Caching.MemoryCache> используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cfab1-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="cfab1-120">Имя конфигурации кэша.</span><span class="sxs-lookup"><span data-stu-id="cfab1-120">The name of the cache configuration.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="cfab1-121">Процент физической памяти, который может использоваться кэшем.</span><span class="sxs-lookup"><span data-stu-id="cfab1-121">The percentage of physical memory that can be used by the cache.</span></span> <span data-ttu-id="cfab1-122">Значение по умолчанию — 0. Это означает, что эвристика автомасштабирования класса <xref:System.Runtime.Caching.MemoryCache> используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cfab1-122">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="cfab1-123">Значение, указывающее интервал, по истечении которого реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями по памяти, заданными для данного экземпляра кэша.</span><span class="sxs-lookup"><span data-stu-id="cfab1-123">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="cfab1-124">Значение вводится в формате "ЧЧ:ММ:СС".</span><span class="sxs-lookup"><span data-stu-id="cfab1-124">The value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cfab1-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cfab1-125">Child Elements</span></span>  
  
|<span data-ttu-id="cfab1-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="cfab1-126">Element</span></span>|<span data-ttu-id="cfab1-127">Описание</span><span class="sxs-lookup"><span data-stu-id="cfab1-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cfab1-128">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="cfab1-128">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="cfab1-129">Содержит коллекцию параметров конфигурации для экземпляра `namedCache` .</span><span class="sxs-lookup"><span data-stu-id="cfab1-129">Contains a collection of configuration settings for the `namedCache` instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cfab1-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cfab1-130">Parent Elements</span></span>  
  
|<span data-ttu-id="cfab1-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="cfab1-131">Element</span></span>|<span data-ttu-id="cfab1-132">Описание:</span><span class="sxs-lookup"><span data-stu-id="cfab1-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cfab1-133">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="cfab1-133">\<system.runtime.caching></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="cfab1-134">Содержит типы, которые позволяют реализовать кэширование выводимых данных в приложениях, встроенных в [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cfab1-134">Contains types that let you implement output caching in applications that are built into the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cfab1-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="cfab1-135">Remarks</span></span>  
 <span data-ttu-id="cfab1-136">Класс <xref:System.Runtime.Caching.MemoryCache> — это конкретная реализация абстрактного класса <xref:System.Runtime.Caching.ObjectCache> .</span><span class="sxs-lookup"><span data-stu-id="cfab1-136">The <xref:System.Runtime.Caching.MemoryCache> class is a concrete implementation of the abstract <xref:System.Runtime.Caching.ObjectCache> class.</span></span> <span data-ttu-id="cfab1-137">Экземпляры класса <xref:System.Runtime.Caching.MemoryCache> можно снабдить сведениями о конфигурации из файлов конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="cfab1-137">Instances of the <xref:System.Runtime.Caching.MemoryCache> class can be supplied with configuration information from application configuration files.</span></span> <span data-ttu-id="cfab1-138">Раздел конфигурации [MemoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) содержит коллекцию конфигураций `namedCaches` .</span><span class="sxs-lookup"><span data-stu-id="cfab1-138">The [memoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) configuration section contains a `namedCaches` configuration collection.</span></span>  
  
 <span data-ttu-id="cfab1-139">При инициализации объекта кэша на базе памяти он сначала пытается найти запись `namedCaches` , которая соответствует имени в параметре, передаваемом конструктору кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="cfab1-139">When a memory-based cache object is initialized, it first tries to find a `namedCaches` entry that matches the name in the parameter that is passed to the memory cache constructor.</span></span> <span data-ttu-id="cfab1-140">Если запись `namedCaches` найдена, из файла конфигурации извлекаются сведения об опросах и управлении памятью.</span><span class="sxs-lookup"><span data-stu-id="cfab1-140">If a `namedCaches` entry is found, the polling and memory-management information are retrieved from the configuration file.</span></span>  
  
 <span data-ttu-id="cfab1-141">После этого процесс инициализации определяет, были ли переопределены какие-либо записи конфигурации, с помощью дополнительной коллекцию пар имя-значение для сведений о конфигурации в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="cfab1-141">The initialization process then determines whether any configuration entries were overridden, by using the optional collection of name/value pairs of configuration information in the constructor.</span></span> <span data-ttu-id="cfab1-142">Если передать в коллекцию пар имя-значение любое из следующих значений, оно переопределит сведения, полученные из файла конфигурации:</span><span class="sxs-lookup"><span data-stu-id="cfab1-142">If you pass any one of the following values in the name/value pair collection, these values override information obtained from the configuration file:</span></span>  
  
-   <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.CacheMemoryLimitMegabytes%2A>  
  
-   <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.PhysicalMemoryLimitPercentage%2A>  
  
-   <xref:System.Runtime.Caching.MemoryCache.PollingInterval%2A>  
  
## <a name="example"></a><span data-ttu-id="cfab1-143">Пример</span><span class="sxs-lookup"><span data-stu-id="cfab1-143">Example</span></span>  
 <span data-ttu-id="cfab1-144">В следующем примере показано, как задать в качестве имени объекта <xref:System.Runtime.Caching.MemoryCache> имя объекта кэша по умолчанию, задав для атрибута `name` значение "default".</span><span class="sxs-lookup"><span data-stu-id="cfab1-144">The following example shows how to set the name of the <xref:System.Runtime.Caching.MemoryCache> object to the default cache object name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="cfab1-145">Атрибутам `cacheMemoryLimitMegabytes` и `physicalMemoryLimitPercentage` присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="cfab1-145">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryLimitPercentage` attribute are set to zero.</span></span> <span data-ttu-id="cfab1-146">Это означает, что эвристика автомасштабирования <xref:System.Runtime.Caching.MemoryCache> используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cfab1-146">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="cfab1-147">Реализация кэша должна каждые две минуты сравнивать текущую загрузку памяти с абсолютными и процентными ограничениями по памяти.</span><span class="sxs-lookup"><span data-stu-id="cfab1-147">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
```xml  
<configuration>  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cfab1-148">См. также</span><span class="sxs-lookup"><span data-stu-id="cfab1-148">See also</span></span>
- <xref:System.Runtime.Caching.MemoryCache>
- [<span data-ttu-id="cfab1-149">\<System.Runtime.Caching > (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="cfab1-149">\<system.runtime.caching> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/system-runtime-caching-element-cache-settings.md)
- [<span data-ttu-id="cfab1-150">\<namedCaches > (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="cfab1-150">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
