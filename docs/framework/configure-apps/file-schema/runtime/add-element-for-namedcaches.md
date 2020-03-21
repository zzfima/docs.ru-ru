---
title: Элемент <add> для <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: c1345022b79df371ad9c89a39a0a8b625e26608c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154509"
---
# <a name="add-element-for-namedcaches"></a><span data-ttu-id="5feb7-102">\<добавить> \<элемент для названныхCaches></span><span class="sxs-lookup"><span data-stu-id="5feb7-102">\<add> Element for \<namedCaches></span></span>
<span data-ttu-id="5feb7-103">Добавляет `namedCache` запись в `namedCaches` коллекцию для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="5feb7-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
<span data-ttu-id="5feb7-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5feb7-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5feb7-105">&nbsp;&nbsp;[**\<system.runtime.кэширования>**](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="5feb7-105">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="5feb7-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<памятьCache>**](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="5feb7-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="5feb7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<имени Кэшес>**](namedcaches-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="5feb7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)</span></span>\
<span data-ttu-id="5feb7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<добавить>**</span><span class="sxs-lookup"><span data-stu-id="5feb7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5feb7-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5feb7-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="5feb7-110">Тип</span><span class="sxs-lookup"><span data-stu-id="5feb7-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5feb7-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5feb7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5feb7-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5feb7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5feb7-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5feb7-113">Attributes</span></span>  
  
|<span data-ttu-id="5feb7-114">attribute</span><span class="sxs-lookup"><span data-stu-id="5feb7-114">Attribute</span></span>|<span data-ttu-id="5feb7-115">Описание</span><span class="sxs-lookup"><span data-stu-id="5feb7-115">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="5feb7-116">Значение, которое определяет максимально допустимый размер (в мегабайтах), <xref:System.Runtime.Caching.MemoryCache> до которого может вырасти экземпляр а.</span><span class="sxs-lookup"><span data-stu-id="5feb7-116">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="5feb7-117">Значение по умолчанию составляет 0, что означает, что аупизилистика <xref:System.Runtime.Caching.MemoryCache> класса используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5feb7-117">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="5feb7-118">Имя кэша.</span><span class="sxs-lookup"><span data-stu-id="5feb7-118">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="5feb7-119">Значение всей доли от 0 до 100, которое определяет максимальный процент физически установленной памяти компьютера, который может быть использован кэшем.</span><span class="sxs-lookup"><span data-stu-id="5feb7-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="5feb7-120">Значение по умолчанию составляет 0, что означает, что аупизилистика <xref:System.Runtime.Caching.MemoryCache> класса используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5feb7-120">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="5feb7-121">Значение, указывающее интервал, по истечении которого реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями по памяти, заданными для данного экземпляра кэша.</span><span class="sxs-lookup"><span data-stu-id="5feb7-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="5feb7-122">Это значение вводится в формате "HH:MM:SS".</span><span class="sxs-lookup"><span data-stu-id="5feb7-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5feb7-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5feb7-123">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="5feb7-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5feb7-124">Parent Elements</span></span>  
  
|<span data-ttu-id="5feb7-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="5feb7-125">Element</span></span>|<span data-ttu-id="5feb7-126">Описание</span><span class="sxs-lookup"><span data-stu-id="5feb7-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5feb7-127">\<имени Кэшес></span><span class="sxs-lookup"><span data-stu-id="5feb7-127">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="5feb7-128">Содержит набор параметров конфигурации <xref:System.Runtime.Caching.MemoryCache> для названных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="5feb7-128">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5feb7-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="5feb7-129">Remarks</span></span>  
 <span data-ttu-id="5feb7-130">Элемент `add` добавляет запись в `namedCaches` коллекцию для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="5feb7-130">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="5feb7-131">Вы можете использовать [четкий](clear-element-for-namedcaches.md) элемент, прежде чем использовать `add` элемент, чтобы быть уверенным, что в коллекции нет других названных кэшов.</span><span class="sxs-lookup"><span data-stu-id="5feb7-131">You can use the [clear](clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="5feb7-132">Этот элемент может быть использован в файле machine.config и в файле Web.config.</span><span class="sxs-lookup"><span data-stu-id="5feb7-132">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5feb7-133">Пример</span><span class="sxs-lookup"><span data-stu-id="5feb7-133">Example</span></span>  
 <span data-ttu-id="5feb7-134">В следующем примере показано, как `namedCache` определить параметры `namedCaches` для входа по умолчанию в коллекцию для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="5feb7-134">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5feb7-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5feb7-135">See also</span></span>

- [<span data-ttu-id="5feb7-136">\<имени Кэши> элемент (Настройки кэша)</span><span class="sxs-lookup"><span data-stu-id="5feb7-136">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
