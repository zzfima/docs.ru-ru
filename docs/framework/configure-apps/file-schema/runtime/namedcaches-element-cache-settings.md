---
title: "&lt;namedCaches&gt; элемент (параметры кэша)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 7c25f0039f75ba1c736cff946dbaaff9252dc93e
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2018
---
# <a name="ltnamedcachesgt-element-cache-settings"></a><span data-ttu-id="17097-102">&lt;namedCaches&gt; элемент (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="17097-102">&lt;namedCaches&gt; Element (Cache Settings)</span></span>
<span data-ttu-id="17097-103">Задает коллекцию параметров конфигурации для именованного <xref:System.Runtime.Caching.MemoryCache> экземпляров.</span><span class="sxs-lookup"><span data-stu-id="17097-103">Specifies a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span> <span data-ttu-id="17097-104"><xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> Свойство ссылается на коллекцию параметров конфигурации из одного или нескольких `namedCaches` элементы файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="17097-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> property references the collection of configuration settings from one or more `namedCaches` elements of the configuration file.</span></span>  
  
 <span data-ttu-id="17097-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="17097-105">\<configuration></span></span>  
<span data-ttu-id="17097-106">\<System.Runtime.Caching ></span><span class="sxs-lookup"><span data-stu-id="17097-106">\< system.runtime.caching></span></span>  
<span data-ttu-id="17097-107">\<memoryCache ></span><span class="sxs-lookup"><span data-stu-id="17097-107">\<memoryCache></span></span>  
<span data-ttu-id="17097-108">\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="17097-108">\<namedCaches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17097-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="17097-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
  <add name="default"/>   
</namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="17097-110">Тип</span><span class="sxs-lookup"><span data-stu-id="17097-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="17097-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="17097-111">Attributes and Elements</span></span>  
 <span data-ttu-id="17097-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="17097-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="17097-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="17097-113">Attributes</span></span>  
  
|<span data-ttu-id="17097-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="17097-114">Attribute</span></span>|<span data-ttu-id="17097-115">Описание:</span><span class="sxs-lookup"><span data-stu-id="17097-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|<span data-ttu-id="17097-116">Целочисленное значение, указывающее максимально допустимый размер в мегабайтах, который экземпляр <xref:System.Runtime.Caching.MemoryCache> могут увеличиваться до.</span><span class="sxs-lookup"><span data-stu-id="17097-116">An integer value that specifies the maximum allowable size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="17097-117">Значение по умолчанию — 0, это означает, что эвристические методы из <xref:System.Runtime.Caching.MemoryCache> класс, используемый по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="17097-117">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`name`|<span data-ttu-id="17097-118">Имя кэша.</span><span class="sxs-lookup"><span data-stu-id="17097-118">The name of the cache.</span></span>|  
|`physicalMemoryLimitPercentage`|<span data-ttu-id="17097-119">Целочисленное значение от 0 до 100, указывающее максимальную долю физической памяти, может использоваться кэшем.</span><span class="sxs-lookup"><span data-stu-id="17097-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="17097-120">Значение по умолчанию — 0, это означает, что эвристические методы из <xref:System.Runtime.Caching.MemoryCache> класс, используемый по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="17097-120">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`pollingInterval`|<span data-ttu-id="17097-121">Значение, указывающее интервал, по истечении которого реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями по памяти, заданными для данного экземпляра кэша.</span><span class="sxs-lookup"><span data-stu-id="17097-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="17097-122">Это значение вводится в формате «Чч».</span><span class="sxs-lookup"><span data-stu-id="17097-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="17097-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="17097-123">Child Elements</span></span>  
  
|<span data-ttu-id="17097-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="17097-124">Element</span></span>|<span data-ttu-id="17097-125">Описание:</span><span class="sxs-lookup"><span data-stu-id="17097-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="17097-126">\<add></span><span class="sxs-lookup"><span data-stu-id="17097-126">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/add-element-for-namedcaches.md)|<span data-ttu-id="17097-127">Добавляет именованный кэш к коллекции `namedCaches` для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="17097-127">Adds a named cache to the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="17097-128">\<clear></span><span class="sxs-lookup"><span data-stu-id="17097-128">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md)|<span data-ttu-id="17097-129">Очищает коллекцию `namedCaches` для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="17097-129">Clears the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="17097-130">\<remove></span><span class="sxs-lookup"><span data-stu-id="17097-130">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/remove-element-for-namedcaches.md)|<span data-ttu-id="17097-131">Удаляет элемент именованного кэша из коллекции `namedCaches` для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="17097-131">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="17097-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="17097-132">Parent Elements</span></span>  
  
|<span data-ttu-id="17097-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="17097-133">Element</span></span>|<span data-ttu-id="17097-134">Описание:</span><span class="sxs-lookup"><span data-stu-id="17097-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="17097-135">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="17097-135">\<memoryCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|<span data-ttu-id="17097-136">Определяет элемент, используемый для настройки кэша, который основан на классе <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="17097-136">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17097-137">Примечания</span><span class="sxs-lookup"><span data-stu-id="17097-137">Remarks</span></span>  
 <span data-ttu-id="17097-138">Раздел конфигурации памяти кэша в файле Web.config может содержать `add`, `remove`, и `clear` атрибутов для `namedCaches` коллекции.</span><span class="sxs-lookup"><span data-stu-id="17097-138">The memory cache configuration section of the Web.config file can contain `add`, `remove`, and `clear` attributes for the `namedCaches` collection.</span></span> <span data-ttu-id="17097-139">Каждый `namedCaches` входа однозначно идентифицируется `name` атрибута.</span><span class="sxs-lookup"><span data-stu-id="17097-139">Each `namedCaches` entry is uniquely identified by the `name` attribute.</span></span>  
  
 <span data-ttu-id="17097-140">Экземпляры записей кэша памяти можно получить путем ссылки на сведения в файлах конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="17097-140">You can retrieve instances of memory cache entries by referencing the information in the application configuration files.</span></span> <span data-ttu-id="17097-141">По умолчанию экземпляр кэша по умолчанию имеет запись в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="17097-141">By default, only the default cache instance has an entry in the configuration file.</span></span> <span data-ttu-id="17097-142">Экземпляр кэша по умолчанию является экземпляр, возвращаемый <xref:System.Runtime.Caching.MemoryCache.Default%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="17097-142">The default cache instance is the instance that is returned from the <xref:System.Runtime.Caching.MemoryCache.Default%2A> property.</span></span>  
  
 <span data-ttu-id="17097-143">Если задать атрибут "name" to «default», элемент использует экземпляр кэша памяти по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="17097-143">If you set the name attribute to "default", the element uses the default memory cache instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17097-144">Пример</span><span class="sxs-lookup"><span data-stu-id="17097-144">Example</span></span>  
 <span data-ttu-id="17097-145">Приведенный ниже показано, как присвоить имя кэша имя записи кэша по умолчанию, задав `name` атрибута значение «default».</span><span class="sxs-lookup"><span data-stu-id="17097-145">The following example shows how to set the name of the cache to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="17097-146">Атрибутам `cacheMemoryLimitMegabytes` и `physicalMemoryPercentage` присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="17097-146">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="17097-147">Установка этих атрибутов в ноль означает, что эвристические методы из <xref:System.Runtime.Caching.MemoryCache> класса используются.</span><span class="sxs-lookup"><span data-stu-id="17097-147">Setting these attributes to zero means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used.</span></span> <span data-ttu-id="17097-148">Реализация кэша сравнивает текущую загрузку памяти с абсолютными и относительными ограничениями памяти каждые две минуты.</span><span class="sxs-lookup"><span data-stu-id="17097-148">The cache implementation compares the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="17097-149">См. также</span><span class="sxs-lookup"><span data-stu-id="17097-149">See Also</span></span>  
 [<span data-ttu-id="17097-150">\<memoryCache > элемент (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="17097-150">\<memoryCache> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)
