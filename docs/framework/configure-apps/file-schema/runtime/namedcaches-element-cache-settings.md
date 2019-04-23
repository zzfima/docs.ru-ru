---
title: Элемент <namedCaches> (параметры кэша)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: 36920a5e585c0c7581fbc4f84043d68550fbdac1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104940"
---
# <a name="namedcaches-element-cache-settings"></a><span data-ttu-id="892f0-102">\<namedCaches > (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="892f0-102">\<namedCaches> Element (Cache Settings)</span></span>
<span data-ttu-id="892f0-103">Определяет коллекцию параметров конфигурации для именованного <xref:System.Runtime.Caching.MemoryCache> экземпляров.</span><span class="sxs-lookup"><span data-stu-id="892f0-103">Specifies a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span> <span data-ttu-id="892f0-104"><xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> Свойство ссылается на коллекцию параметров конфигурации из одного или нескольких `namedCaches` элементов файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="892f0-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> property references the collection of configuration settings from one or more `namedCaches` elements of the configuration file.</span></span>  
  
 <span data-ttu-id="892f0-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="892f0-105">\<configuration></span></span>  
<span data-ttu-id="892f0-106">\< System.Runtime.Caching ></span><span class="sxs-lookup"><span data-stu-id="892f0-106">\< system.runtime.caching></span></span>  
<span data-ttu-id="892f0-107">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="892f0-107">\<memoryCache></span></span>  
<span data-ttu-id="892f0-108">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="892f0-108">\<namedCaches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="892f0-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="892f0-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
  <add name="default"/>   
</namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="892f0-110">Тип</span><span class="sxs-lookup"><span data-stu-id="892f0-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="892f0-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="892f0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="892f0-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="892f0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="892f0-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="892f0-113">Attributes</span></span>  
  
|<span data-ttu-id="892f0-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="892f0-114">Attribute</span></span>|<span data-ttu-id="892f0-115">Описание</span><span class="sxs-lookup"><span data-stu-id="892f0-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|<span data-ttu-id="892f0-116">Целочисленное значение, указывающее максимально допустимый размер в мегабайтах, который экземпляр <xref:System.Runtime.Caching.MemoryCache> может увеличиться.</span><span class="sxs-lookup"><span data-stu-id="892f0-116">An integer value that specifies the maximum allowable size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="892f0-117">Значение по умолчанию — 0, это означает, что эвристика из <xref:System.Runtime.Caching.MemoryCache> класс используются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="892f0-117">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`name`|<span data-ttu-id="892f0-118">Имя кэша.</span><span class="sxs-lookup"><span data-stu-id="892f0-118">The name of the cache.</span></span>|  
|`physicalMemoryLimitPercentage`|<span data-ttu-id="892f0-119">Целочисленное значение от 0 до 100, указывающее максимальную долю физической памяти, который может использоваться кэшем.</span><span class="sxs-lookup"><span data-stu-id="892f0-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="892f0-120">Значение по умолчанию — 0, это означает, что эвристика из <xref:System.Runtime.Caching.MemoryCache> класс используются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="892f0-120">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`pollingInterval`|<span data-ttu-id="892f0-121">Значение, указывающее интервал, по истечении которого реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями по памяти, заданными для данного экземпляра кэша.</span><span class="sxs-lookup"><span data-stu-id="892f0-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="892f0-122">Это значение вводится в формате «Чч: мм:».</span><span class="sxs-lookup"><span data-stu-id="892f0-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="892f0-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="892f0-123">Child Elements</span></span>  
  
|<span data-ttu-id="892f0-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="892f0-124">Element</span></span>|<span data-ttu-id="892f0-125">Описание</span><span class="sxs-lookup"><span data-stu-id="892f0-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="892f0-126">\<add></span><span class="sxs-lookup"><span data-stu-id="892f0-126">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/add-element-for-namedcaches.md)|<span data-ttu-id="892f0-127">Добавляет именованный кэш к коллекции `namedCaches` для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="892f0-127">Adds a named cache to the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="892f0-128">\<clear></span><span class="sxs-lookup"><span data-stu-id="892f0-128">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md)|<span data-ttu-id="892f0-129">Очищает коллекцию `namedCaches` для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="892f0-129">Clears the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="892f0-130">\<remove></span><span class="sxs-lookup"><span data-stu-id="892f0-130">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/remove-element-for-namedcaches.md)|<span data-ttu-id="892f0-131">Удаляет элемент именованного кэша из коллекции `namedCaches` для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="892f0-131">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="892f0-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="892f0-132">Parent Elements</span></span>  
  
|<span data-ttu-id="892f0-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="892f0-133">Element</span></span>|<span data-ttu-id="892f0-134">Описание</span><span class="sxs-lookup"><span data-stu-id="892f0-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="892f0-135">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="892f0-135">\<memoryCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|<span data-ttu-id="892f0-136">Определяет элемент, используемый для настройки кэша, который основан на классе <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="892f0-136">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="892f0-137">Примечания</span><span class="sxs-lookup"><span data-stu-id="892f0-137">Remarks</span></span>  
 <span data-ttu-id="892f0-138">Раздел конфигурации кэша памяти файла Web.config может содержать `add`, `remove`, и `clear` атрибуты для `namedCaches` коллекции.</span><span class="sxs-lookup"><span data-stu-id="892f0-138">The memory cache configuration section of the Web.config file can contain `add`, `remove`, and `clear` attributes for the `namedCaches` collection.</span></span> <span data-ttu-id="892f0-139">Каждый `namedCaches` запись однозначно идентифицируется по `name` атрибута.</span><span class="sxs-lookup"><span data-stu-id="892f0-139">Each `namedCaches` entry is uniquely identified by the `name` attribute.</span></span>  
  
 <span data-ttu-id="892f0-140">Экземпляры записей кэша памяти можно получить путем ссылки на сведения в файлах конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="892f0-140">You can retrieve instances of memory cache entries by referencing the information in the application configuration files.</span></span> <span data-ttu-id="892f0-141">По умолчанию экземпляр кэша по умолчанию присутствует в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="892f0-141">By default, only the default cache instance has an entry in the configuration file.</span></span> <span data-ttu-id="892f0-142">Экземпляр кэша по умолчанию — экземпляр, который возвращается из <xref:System.Runtime.Caching.MemoryCache.Default%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="892f0-142">The default cache instance is the instance that is returned from the <xref:System.Runtime.Caching.MemoryCache.Default%2A> property.</span></span>  
  
 <span data-ttu-id="892f0-143">Если задать атрибут "name" to «default», элемент использует экземпляр по умолчанию для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="892f0-143">If you set the name attribute to "default", the element uses the default memory cache instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="892f0-144">Пример</span><span class="sxs-lookup"><span data-stu-id="892f0-144">Example</span></span>  
 <span data-ttu-id="892f0-145">В следующем примере показано, как присвоено имя записи кэша по умолчанию имя кэша, установив `name` атрибута значение «default».</span><span class="sxs-lookup"><span data-stu-id="892f0-145">The following example shows how to set the name of the cache to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="892f0-146">Атрибутам `cacheMemoryLimitMegabytes` и `physicalMemoryPercentage` присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="892f0-146">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="892f0-147">Установка этих атрибутов в ноль означает, что эвристика из <xref:System.Runtime.Caching.MemoryCache> класс используются.</span><span class="sxs-lookup"><span data-stu-id="892f0-147">Setting these attributes to zero means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used.</span></span> <span data-ttu-id="892f0-148">Реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями памяти каждые две минуты.</span><span class="sxs-lookup"><span data-stu-id="892f0-148">The cache implementation compares the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="892f0-149">См. также</span><span class="sxs-lookup"><span data-stu-id="892f0-149">See also</span></span>

- [<span data-ttu-id="892f0-150">\<memoryCache > (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="892f0-150">\<memoryCache> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)
