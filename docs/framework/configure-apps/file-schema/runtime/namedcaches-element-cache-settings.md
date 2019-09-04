---
title: Элемент <namedCaches> (параметры кэша)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: 4587234ad91fa3b1abbb376bd7ae517d5abea6c3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252461"
---
# <a name="namedcaches-element-cache-settings"></a><span data-ttu-id="e9f26-102">\<Элемент > Намедкачес (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="e9f26-102">\<namedCaches> Element (Cache Settings)</span></span>
<span data-ttu-id="e9f26-103">Задает коллекцию параметров конфигурации для именованных <xref:System.Runtime.Caching.MemoryCache> экземпляров.</span><span class="sxs-lookup"><span data-stu-id="e9f26-103">Specifies a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span> <span data-ttu-id="e9f26-104">Свойство ссылается на коллекцию параметров конфигурации из одного или нескольких `namedCaches` элементов файла конфигурации. <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A></span><span class="sxs-lookup"><span data-stu-id="e9f26-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> property references the collection of configuration settings from one or more `namedCaches` elements of the configuration file.</span></span>  
  
<span data-ttu-id="e9f26-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e9f26-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e9f26-106">&nbsp;&nbsp;[ **\<System. Runtime. Caching >** ](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e9f26-106">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="e9f26-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<memoryCache >** ](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e9f26-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="e9f26-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Намедкачес >**</span><span class="sxs-lookup"><span data-stu-id="e9f26-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedCaches>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9f26-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e9f26-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
  <add name="default"/>   
</namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="e9f26-110">Тип</span><span class="sxs-lookup"><span data-stu-id="e9f26-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9f26-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e9f26-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e9f26-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e9f26-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9f26-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e9f26-113">Attributes</span></span>  
  
|<span data-ttu-id="e9f26-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e9f26-114">Attribute</span></span>|<span data-ttu-id="e9f26-115">Описание</span><span class="sxs-lookup"><span data-stu-id="e9f26-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|<span data-ttu-id="e9f26-116">Целочисленное значение, указывающее максимально допустимый размер (в мегабайтах), до которого <xref:System.Runtime.Caching.MemoryCache> может увеличиваться экземпляр.</span><span class="sxs-lookup"><span data-stu-id="e9f26-116">An integer value that specifies the maximum allowable size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="e9f26-117">Значение по умолчанию — 0. Это означает, что по умолчанию используется эвристика <xref:System.Runtime.Caching.MemoryCache> автоподбора размера класса.</span><span class="sxs-lookup"><span data-stu-id="e9f26-117">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`name`|<span data-ttu-id="e9f26-118">Имя кэша.</span><span class="sxs-lookup"><span data-stu-id="e9f26-118">The name of the cache.</span></span>|  
|`physicalMemoryLimitPercentage`|<span data-ttu-id="e9f26-119">Целочисленное значение от 0 до 100, которое указывает максимальный процент физической памяти компьютера, который может потребляться кэшем.</span><span class="sxs-lookup"><span data-stu-id="e9f26-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="e9f26-120">Значение по умолчанию — 0. Это означает, что по умолчанию используется эвристика <xref:System.Runtime.Caching.MemoryCache> автоподбора размера класса.</span><span class="sxs-lookup"><span data-stu-id="e9f26-120">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`pollingInterval`|<span data-ttu-id="e9f26-121">Значение, указывающее интервал, по истечении которого реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями по памяти, заданными для данного экземпляра кэша.</span><span class="sxs-lookup"><span data-stu-id="e9f26-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="e9f26-122">Это значение указывается в формате "чч: мм: СС".</span><span class="sxs-lookup"><span data-stu-id="e9f26-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9f26-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e9f26-123">Child Elements</span></span>  
  
|<span data-ttu-id="e9f26-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="e9f26-124">Element</span></span>|<span data-ttu-id="e9f26-125">Описание</span><span class="sxs-lookup"><span data-stu-id="e9f26-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9f26-126">\<add></span><span class="sxs-lookup"><span data-stu-id="e9f26-126">\<add></span></span>](add-element-for-namedcaches.md)|<span data-ttu-id="e9f26-127">Добавляет именованный кэш к коллекции `namedCaches` для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="e9f26-127">Adds a named cache to the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="e9f26-128">\<clear></span><span class="sxs-lookup"><span data-stu-id="e9f26-128">\<clear></span></span>](clear-element-for-namedcaches.md)|<span data-ttu-id="e9f26-129">Очищает коллекцию `namedCaches` для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="e9f26-129">Clears the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="e9f26-130">\<remove></span><span class="sxs-lookup"><span data-stu-id="e9f26-130">\<remove></span></span>](remove-element-for-namedcaches.md)|<span data-ttu-id="e9f26-131">Удаляет элемент именованного кэша из коллекции `namedCaches` для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="e9f26-131">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e9f26-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e9f26-132">Parent Elements</span></span>  
  
|<span data-ttu-id="e9f26-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="e9f26-133">Element</span></span>|<span data-ttu-id="e9f26-134">Описание</span><span class="sxs-lookup"><span data-stu-id="e9f26-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9f26-135">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e9f26-135">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="e9f26-136">Указывает корневой элемент в каждом файле конфигурации, который используется средой CLR и .NET Framework приложениями.</span><span class="sxs-lookup"><span data-stu-id="e9f26-136">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="e9f26-137">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="e9f26-137">\<memoryCache></span></span>](memorycache-element-cache-settings.md)|<span data-ttu-id="e9f26-138">Определяет элемент, используемый для настройки кэша, который основан на классе <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="e9f26-138">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
|[<span data-ttu-id="e9f26-139">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="e9f26-139">\<system.runtime.caching></span></span>](system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="e9f26-140">Содержит типы, позволяющие реализовать кэширование вывода в приложениях, встроенных в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e9f26-140">Contains types that let you implement output caching in applications that are built into the .NET Framework.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9f26-141">Примечания</span><span class="sxs-lookup"><span data-stu-id="e9f26-141">Remarks</span></span>  
 <span data-ttu-id="e9f26-142">Раздел конфигурации кэша памяти файла Web. `add`config может содержать атрибуты, `remove`и `clear` для `namedCaches` коллекции.</span><span class="sxs-lookup"><span data-stu-id="e9f26-142">The memory cache configuration section of the Web.config file can contain `add`, `remove`, and `clear` attributes for the `namedCaches` collection.</span></span> <span data-ttu-id="e9f26-143">Каждая `namedCaches` запись уникально идентифицируется `name` атрибутом.</span><span class="sxs-lookup"><span data-stu-id="e9f26-143">Each `namedCaches` entry is uniquely identified by the `name` attribute.</span></span>  
  
 <span data-ttu-id="e9f26-144">Экземпляры записей кэша памяти можно получить, обратившись к сведениям в файлах конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="e9f26-144">You can retrieve instances of memory cache entries by referencing the information in the application configuration files.</span></span> <span data-ttu-id="e9f26-145">По умолчанию в файле конфигурации содержится запись только для экземпляра кэша по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e9f26-145">By default, only the default cache instance has an entry in the configuration file.</span></span> <span data-ttu-id="e9f26-146">Экземпляром кэша по умолчанию является экземпляр, который возвращается из <xref:System.Runtime.Caching.MemoryCache.Default%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="e9f26-146">The default cache instance is the instance that is returned from the <xref:System.Runtime.Caching.MemoryCache.Default%2A> property.</span></span>  
  
 <span data-ttu-id="e9f26-147">Если для атрибута name задано значение Default, то элемент использует экземпляр кэша памяти по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e9f26-147">If you set the name attribute to "default", the element uses the default memory cache instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9f26-148">Пример</span><span class="sxs-lookup"><span data-stu-id="e9f26-148">Example</span></span>  
 <span data-ttu-id="e9f26-149">В следующем примере показано, как задать имя кэша в качестве имени записи кэша по умолчанию, задав `name` для атрибута значение Default.</span><span class="sxs-lookup"><span data-stu-id="e9f26-149">The following example shows how to set the name of the cache to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="e9f26-150">Атрибутам `cacheMemoryLimitMegabytes` и `physicalMemoryPercentage` присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="e9f26-150">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="e9f26-151">Установка этих атрибутов равным нулю означает, что используется эвристический <xref:System.Runtime.Caching.MemoryCache> подход автоподбора размера класса.</span><span class="sxs-lookup"><span data-stu-id="e9f26-151">Setting these attributes to zero means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used.</span></span> <span data-ttu-id="e9f26-152">Реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями памяти каждые две минуты.</span><span class="sxs-lookup"><span data-stu-id="e9f26-152">The cache implementation compares the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e9f26-153">См. также</span><span class="sxs-lookup"><span data-stu-id="e9f26-153">See also</span></span>

- [<span data-ttu-id="e9f26-154">\<Элемент > memoryCache (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="e9f26-154">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
