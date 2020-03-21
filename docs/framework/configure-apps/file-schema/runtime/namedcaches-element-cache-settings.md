---
title: Элемент <namedCaches> (параметры кэша)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: e0640ca18d386141f3c03135019eb4fe959b5bf8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153962"
---
# <a name="namedcaches-element-cache-settings"></a><span data-ttu-id="b5f56-102">\<имени Кэши> элемент (Настройки кэша)</span><span class="sxs-lookup"><span data-stu-id="b5f56-102">\<namedCaches> Element (Cache Settings)</span></span>
<span data-ttu-id="b5f56-103">Определяет набор параметров конфигурации для названных <xref:System.Runtime.Caching.MemoryCache> экземпляров.</span><span class="sxs-lookup"><span data-stu-id="b5f56-103">Specifies a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span> <span data-ttu-id="b5f56-104">Свойство <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> ссылается на набор параметров конфигурации из одного или нескольких `namedCaches` элементов файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b5f56-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> property references the collection of configuration settings from one or more `namedCaches` elements of the configuration file.</span></span>  
  
<span data-ttu-id="b5f56-105">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b5f56-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b5f56-106">&nbsp;&nbsp;[**\<system.runtime.кэширования>**](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b5f56-106">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="b5f56-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<памятьCache>**](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b5f56-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="b5f56-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<имени Кэшес>**</span><span class="sxs-lookup"><span data-stu-id="b5f56-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedCaches>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5f56-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5f56-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
  <add name="default"/>
</namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="b5f56-110">Тип</span><span class="sxs-lookup"><span data-stu-id="b5f56-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b5f56-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b5f56-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b5f56-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b5f56-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b5f56-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b5f56-113">Attributes</span></span>  
  
|<span data-ttu-id="b5f56-114">attribute</span><span class="sxs-lookup"><span data-stu-id="b5f56-114">Attribute</span></span>|<span data-ttu-id="b5f56-115">Описание</span><span class="sxs-lookup"><span data-stu-id="b5f56-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|<span data-ttu-id="b5f56-116">Значение, которое определяет максимально допустимый размер, в мегабайтах, что <xref:System.Runtime.Caching.MemoryCache> экземпляр может вырасти до.</span><span class="sxs-lookup"><span data-stu-id="b5f56-116">An integer value that specifies the maximum allowable size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="b5f56-117">Значение по умолчанию составляет 0, что означает, что <xref:System.Runtime.Caching.MemoryCache> аупизионизация эвристики класса используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b5f56-117">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`name`|<span data-ttu-id="b5f56-118">Имя кэша.</span><span class="sxs-lookup"><span data-stu-id="b5f56-118">The name of the cache.</span></span>|  
|`physicalMemoryLimitPercentage`|<span data-ttu-id="b5f56-119">Значение всей доли от 0 до 100, которое определяет максимальный процент физически установленной памяти компьютера, который может быть использован кэшем.</span><span class="sxs-lookup"><span data-stu-id="b5f56-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="b5f56-120">Значение по умолчанию составляет 0, что означает, что <xref:System.Runtime.Caching.MemoryCache> аупизионизация эвристики класса используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b5f56-120">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`pollingInterval`|<span data-ttu-id="b5f56-121">Значение, указывающее интервал, по истечении которого реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями по памяти, заданными для данного экземпляра кэша.</span><span class="sxs-lookup"><span data-stu-id="b5f56-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="b5f56-122">Это значение вводится в формате "HH:MM:SS".</span><span class="sxs-lookup"><span data-stu-id="b5f56-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b5f56-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b5f56-123">Child Elements</span></span>  
  
|<span data-ttu-id="b5f56-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="b5f56-124">Element</span></span>|<span data-ttu-id="b5f56-125">Описание</span><span class="sxs-lookup"><span data-stu-id="b5f56-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5f56-126">\<добавить></span><span class="sxs-lookup"><span data-stu-id="b5f56-126">\<add></span></span>](add-element-for-namedcaches.md)|<span data-ttu-id="b5f56-127">Добавляет именованный кэш к коллекции `namedCaches` для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="b5f56-127">Adds a named cache to the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="b5f56-128">\<ясно></span><span class="sxs-lookup"><span data-stu-id="b5f56-128">\<clear></span></span>](clear-element-for-namedcaches.md)|<span data-ttu-id="b5f56-129">Очищает коллекцию `namedCaches` для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="b5f56-129">Clears the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="b5f56-130">\<удалить></span><span class="sxs-lookup"><span data-stu-id="b5f56-130">\<remove></span></span>](remove-element-for-namedcaches.md)|<span data-ttu-id="b5f56-131">Удаляет элемент именованного кэша из коллекции `namedCaches` для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="b5f56-131">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b5f56-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b5f56-132">Parent Elements</span></span>  
  
|<span data-ttu-id="b5f56-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="b5f56-133">Element</span></span>|<span data-ttu-id="b5f56-134">Описание</span><span class="sxs-lookup"><span data-stu-id="b5f56-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5f56-135">\<конфигурация></span><span class="sxs-lookup"><span data-stu-id="b5f56-135">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="b5f56-136">Определяет корневой элемент в каждом файле конфигурации, который используется приложениями общего языка и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b5f56-136">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="b5f56-137">\<памятьCache></span><span class="sxs-lookup"><span data-stu-id="b5f56-137">\<memoryCache></span></span>](memorycache-element-cache-settings.md)|<span data-ttu-id="b5f56-138">Определяет элемент, используемый для настройки кэша, который основан на классе <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="b5f56-138">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
|[<span data-ttu-id="b5f56-139">\<system.runtime.кэширования></span><span class="sxs-lookup"><span data-stu-id="b5f56-139">\<system.runtime.caching></span></span>](system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="b5f56-140">Содержит типы, которые позволяют реализовать кэширование в приложениях, встроенных в рамку .NET.</span><span class="sxs-lookup"><span data-stu-id="b5f56-140">Contains types that let you implement output caching in applications that are built into the .NET Framework.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5f56-141">Remarks</span><span class="sxs-lookup"><span data-stu-id="b5f56-141">Remarks</span></span>  
 <span data-ttu-id="b5f56-142">Раздел конфигурации кэша памяти файла `add`Web.config может содержать `remove`атрибуты для `clear` коллекции. `namedCaches`</span><span class="sxs-lookup"><span data-stu-id="b5f56-142">The memory cache configuration section of the Web.config file can contain `add`, `remove`, and `clear` attributes for the `namedCaches` collection.</span></span> <span data-ttu-id="b5f56-143">Каждая `namedCaches` запись однозначно идентифицируется `name` атрибутом.</span><span class="sxs-lookup"><span data-stu-id="b5f56-143">Each `namedCaches` entry is uniquely identified by the `name` attribute.</span></span>  
  
 <span data-ttu-id="b5f56-144">Вы можете получить экземпляры записей кэша памяти, ссылаясь на информацию в файлах конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="b5f56-144">You can retrieve instances of memory cache entries by referencing the information in the application configuration files.</span></span> <span data-ttu-id="b5f56-145">По умолчанию только экземпляр кэша по умолчанию имеет запись в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b5f56-145">By default, only the default cache instance has an entry in the configuration file.</span></span> <span data-ttu-id="b5f56-146">Экземпляр кэша по умолчанию — <xref:System.Runtime.Caching.MemoryCache.Default%2A> это экземпляр, который возвращается из свойства.</span><span class="sxs-lookup"><span data-stu-id="b5f56-146">The default cache instance is the instance that is returned from the <xref:System.Runtime.Caching.MemoryCache.Default%2A> property.</span></span>  
  
 <span data-ttu-id="b5f56-147">При установке атрибута имени на "по умолчанию" элемент использует экземпляр кэша памяти по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b5f56-147">If you set the name attribute to "default", the element uses the default memory cache instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5f56-148">Пример</span><span class="sxs-lookup"><span data-stu-id="b5f56-148">Example</span></span>  
 <span data-ttu-id="b5f56-149">В следующем примере показано, как установить имя кэша к `name` имени входа кэша по умолчанию, установив атрибут на "по умолчанию".</span><span class="sxs-lookup"><span data-stu-id="b5f56-149">The following example shows how to set the name of the cache to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="b5f56-150">Атрибутам `cacheMemoryLimitMegabytes` и `physicalMemoryPercentage` присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="b5f56-150">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="b5f56-151">Установка этих атрибутов до нуля означает, что используются <xref:System.Runtime.Caching.MemoryCache> ауотизирующие эвристики класса.</span><span class="sxs-lookup"><span data-stu-id="b5f56-151">Setting these attributes to zero means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used.</span></span> <span data-ttu-id="b5f56-152">Реализация кэша сравнивает текущую нагрузку памяти с абсолютными и процентными ограничениями памяти каждые две минуты.</span><span class="sxs-lookup"><span data-stu-id="b5f56-152">The cache implementation compares the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b5f56-153">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b5f56-153">See also</span></span>

- [<span data-ttu-id="b5f56-154">\<memoryCache> элемент (Настройки кэша)</span><span class="sxs-lookup"><span data-stu-id="b5f56-154">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
