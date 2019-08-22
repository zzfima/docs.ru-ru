---
title: Элемент <namedCaches> (параметры кэша)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: 9cedd462aa539745ddab844dff158912914cb024
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663583"
---
# <a name="namedcaches-element-cache-settings"></a><span data-ttu-id="00f82-102">\<Элемент > Намедкачес (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="00f82-102">\<namedCaches> Element (Cache Settings)</span></span>
<span data-ttu-id="00f82-103">Задает коллекцию параметров конфигурации для именованных <xref:System.Runtime.Caching.MemoryCache> экземпляров.</span><span class="sxs-lookup"><span data-stu-id="00f82-103">Specifies a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span> <span data-ttu-id="00f82-104">Свойство ссылается на коллекцию параметров конфигурации из одного или нескольких `namedCaches` элементов файла конфигурации. <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A></span><span class="sxs-lookup"><span data-stu-id="00f82-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> property references the collection of configuration settings from one or more `namedCaches` elements of the configuration file.</span></span>  
  
 <span data-ttu-id="00f82-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="00f82-105">\<configuration></span></span>  
<span data-ttu-id="00f82-106">\<System. Runtime. Caching ></span><span class="sxs-lookup"><span data-stu-id="00f82-106">\< system.runtime.caching></span></span>  
<span data-ttu-id="00f82-107">\<memoryCache ></span><span class="sxs-lookup"><span data-stu-id="00f82-107">\<memoryCache></span></span>  
<span data-ttu-id="00f82-108">\<Намедкачес ></span><span class="sxs-lookup"><span data-stu-id="00f82-108">\<namedCaches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00f82-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="00f82-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
  <add name="default"/>   
</namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="00f82-110">Тип</span><span class="sxs-lookup"><span data-stu-id="00f82-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00f82-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="00f82-111">Attributes and Elements</span></span>  
 <span data-ttu-id="00f82-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="00f82-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00f82-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="00f82-113">Attributes</span></span>  
  
|<span data-ttu-id="00f82-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="00f82-114">Attribute</span></span>|<span data-ttu-id="00f82-115">Описание</span><span class="sxs-lookup"><span data-stu-id="00f82-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|<span data-ttu-id="00f82-116">Целочисленное значение, указывающее максимально допустимый размер (в мегабайтах), до которого <xref:System.Runtime.Caching.MemoryCache> может увеличиваться экземпляр.</span><span class="sxs-lookup"><span data-stu-id="00f82-116">An integer value that specifies the maximum allowable size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="00f82-117">Значение по умолчанию — 0. Это означает, что по умолчанию используется эвристика <xref:System.Runtime.Caching.MemoryCache> автоподбора размера класса.</span><span class="sxs-lookup"><span data-stu-id="00f82-117">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`name`|<span data-ttu-id="00f82-118">Имя кэша.</span><span class="sxs-lookup"><span data-stu-id="00f82-118">The name of the cache.</span></span>|  
|`physicalMemoryLimitPercentage`|<span data-ttu-id="00f82-119">Целочисленное значение от 0 до 100, которое указывает максимальный процент физической памяти компьютера, который может потребляться кэшем.</span><span class="sxs-lookup"><span data-stu-id="00f82-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="00f82-120">Значение по умолчанию — 0. Это означает, что по умолчанию используется эвристика <xref:System.Runtime.Caching.MemoryCache> автоподбора размера класса.</span><span class="sxs-lookup"><span data-stu-id="00f82-120">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`pollingInterval`|<span data-ttu-id="00f82-121">Значение, указывающее интервал, по истечении которого реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями по памяти, заданными для данного экземпляра кэша.</span><span class="sxs-lookup"><span data-stu-id="00f82-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="00f82-122">Это значение указывается в формате "чч: мм: СС".</span><span class="sxs-lookup"><span data-stu-id="00f82-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="00f82-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="00f82-123">Child Elements</span></span>  
  
|<span data-ttu-id="00f82-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="00f82-124">Element</span></span>|<span data-ttu-id="00f82-125">Описание</span><span class="sxs-lookup"><span data-stu-id="00f82-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00f82-126">\<add></span><span class="sxs-lookup"><span data-stu-id="00f82-126">\<add></span></span>](add-element-for-namedcaches.md)|<span data-ttu-id="00f82-127">Добавляет именованный кэш к коллекции `namedCaches` для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="00f82-127">Adds a named cache to the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="00f82-128">\<clear></span><span class="sxs-lookup"><span data-stu-id="00f82-128">\<clear></span></span>](clear-element-for-namedcaches.md)|<span data-ttu-id="00f82-129">Очищает коллекцию `namedCaches` для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="00f82-129">Clears the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="00f82-130">\<remove></span><span class="sxs-lookup"><span data-stu-id="00f82-130">\<remove></span></span>](remove-element-for-namedcaches.md)|<span data-ttu-id="00f82-131">Удаляет элемент именованного кэша из коллекции `namedCaches` для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="00f82-131">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="00f82-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="00f82-132">Parent Elements</span></span>  
  
|<span data-ttu-id="00f82-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="00f82-133">Element</span></span>|<span data-ttu-id="00f82-134">Описание</span><span class="sxs-lookup"><span data-stu-id="00f82-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00f82-135">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="00f82-135">\<memoryCache></span></span>](memorycache-element-cache-settings.md)|<span data-ttu-id="00f82-136">Определяет элемент, используемый для настройки кэша, который основан на классе <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="00f82-136">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00f82-137">Примечания</span><span class="sxs-lookup"><span data-stu-id="00f82-137">Remarks</span></span>  
 <span data-ttu-id="00f82-138">Раздел конфигурации кэша памяти файла Web. `add`config может содержать атрибуты, `remove`и `clear` для `namedCaches` коллекции.</span><span class="sxs-lookup"><span data-stu-id="00f82-138">The memory cache configuration section of the Web.config file can contain `add`, `remove`, and `clear` attributes for the `namedCaches` collection.</span></span> <span data-ttu-id="00f82-139">Каждая `namedCaches` запись уникально идентифицируется `name` атрибутом.</span><span class="sxs-lookup"><span data-stu-id="00f82-139">Each `namedCaches` entry is uniquely identified by the `name` attribute.</span></span>  
  
 <span data-ttu-id="00f82-140">Экземпляры записей кэша памяти можно получить, обратившись к сведениям в файлах конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="00f82-140">You can retrieve instances of memory cache entries by referencing the information in the application configuration files.</span></span> <span data-ttu-id="00f82-141">По умолчанию в файле конфигурации содержится запись только для экземпляра кэша по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="00f82-141">By default, only the default cache instance has an entry in the configuration file.</span></span> <span data-ttu-id="00f82-142">Экземпляром кэша по умолчанию является экземпляр, который возвращается из <xref:System.Runtime.Caching.MemoryCache.Default%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="00f82-142">The default cache instance is the instance that is returned from the <xref:System.Runtime.Caching.MemoryCache.Default%2A> property.</span></span>  
  
 <span data-ttu-id="00f82-143">Если для атрибута name задано значение Default, то элемент использует экземпляр кэша памяти по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="00f82-143">If you set the name attribute to "default", the element uses the default memory cache instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00f82-144">Пример</span><span class="sxs-lookup"><span data-stu-id="00f82-144">Example</span></span>  
 <span data-ttu-id="00f82-145">В следующем примере показано, как задать имя кэша в качестве имени записи кэша по умолчанию, задав `name` для атрибута значение Default.</span><span class="sxs-lookup"><span data-stu-id="00f82-145">The following example shows how to set the name of the cache to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="00f82-146">Атрибутам `cacheMemoryLimitMegabytes` и `physicalMemoryPercentage` присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="00f82-146">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="00f82-147">Установка этих атрибутов равным нулю означает, что используется эвристический <xref:System.Runtime.Caching.MemoryCache> подход автоподбора размера класса.</span><span class="sxs-lookup"><span data-stu-id="00f82-147">Setting these attributes to zero means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used.</span></span> <span data-ttu-id="00f82-148">Реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями памяти каждые две минуты.</span><span class="sxs-lookup"><span data-stu-id="00f82-148">The cache implementation compares the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="00f82-149">См. также</span><span class="sxs-lookup"><span data-stu-id="00f82-149">See also</span></span>

- [<span data-ttu-id="00f82-150">\<Элемент > memoryCache (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="00f82-150">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
