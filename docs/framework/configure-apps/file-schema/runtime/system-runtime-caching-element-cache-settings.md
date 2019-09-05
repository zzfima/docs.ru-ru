---
title: Элемент <system.runtime.caching> (параметры кэша)
ms.date: 03/30/2017
helpviewer_keywords:
- <system.runtime.caching> element
- caching [.NET Framework], configuration
- system.runtime.caching element
ms.assetid: 9b44daee-874a-4bd1-954e-83bf53565590
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e36e2ed96a0748a69f2bd9ee32432901f0bf0898
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252292"
---
# <a name="systemruntimecaching-element-cache-settings"></a><span data-ttu-id="467cf-102">\<Элемент System. Runtime. Caching > (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="467cf-102">\<system.runtime.caching> Element (Cache Settings)</span></span>

<span data-ttu-id="467cf-103">Обеспечивает настройку реализации <xref:System.Runtime.Caching.ObjectCache> в памяти по умолчанию посредством записи `memoryCache` в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="467cf-103">Provides configuration for the default in-memory <xref:System.Runtime.Caching.ObjectCache> implementation through the `memoryCache` entry in the configuration file.</span></span>  
  
<span data-ttu-id="467cf-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="467cf-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="467cf-105">&nbsp;&nbsp; **\<System. Runtime. Caching >**</span><span class="sxs-lookup"><span data-stu-id="467cf-105">&nbsp;&nbsp;**\<system.runtime.caching>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="467cf-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="467cf-106">Syntax</span></span>  
  
```xml  
<system.runtime.caching >  
   <!-- child elements -->  
</system.runtime.caching >  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="467cf-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="467cf-107">Attributes and Elements</span></span>

<span data-ttu-id="467cf-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="467cf-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="467cf-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="467cf-109">Attributes</span></span>

`None`  

### <a name="child-elements"></a><span data-ttu-id="467cf-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="467cf-110">Child Elements</span></span>

|<span data-ttu-id="467cf-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="467cf-111">Element</span></span>|<span data-ttu-id="467cf-112">Описание</span><span class="sxs-lookup"><span data-stu-id="467cf-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="467cf-113">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="467cf-113">\<memoryCache></span></span>](memorycache-element-cache-settings.md)|<span data-ttu-id="467cf-114">Определяет элемент, используемый для настройки кэша, который основан на классе <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="467cf-114">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="467cf-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="467cf-115">Parent Elements</span></span>  
  
|<span data-ttu-id="467cf-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="467cf-116">Element</span></span>|<span data-ttu-id="467cf-117">Описание</span><span class="sxs-lookup"><span data-stu-id="467cf-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="467cf-118">\<configuration></span><span class="sxs-lookup"><span data-stu-id="467cf-118">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="467cf-119">Указывает корневой элемент в каждом файле конфигурации, который используется средой CLR и .NET Framework приложениями.</span><span class="sxs-lookup"><span data-stu-id="467cf-119">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="467cf-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="467cf-120">Remarks</span></span>

<span data-ttu-id="467cf-121">Классы в этом пространстве имен предоставляют способ использования средств кэширования, например таких, которые имеются в ASP.NET, но без зависимости от сборки `System.Web` .</span><span class="sxs-lookup"><span data-stu-id="467cf-121">The classes in this namespace provide a way to use caching facilities like those in ASP.NET, but without a dependency on the `System.Web` assembly.</span></span> <span data-ttu-id="467cf-122">Для получения дополнительной информации см. [Caching in .NET Framework Applications](../../../performance/caching-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="467cf-122">For more information, see [Caching in .NET Framework Applications](../../../performance/caching-in-net-framework-applications.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="467cf-123">Функции кэширования вывода и типы в <xref:System.Runtime.Caching> пространстве имен являются новыми в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="467cf-123">The output caching functionality and types in the <xref:System.Runtime.Caching> namespace are new in .NET Framework 4.</span></span>  
  
## <a name="example"></a><span data-ttu-id="467cf-124">Пример</span><span class="sxs-lookup"><span data-stu-id="467cf-124">Example</span></span>

<span data-ttu-id="467cf-125">В следующем примере кода показано, как настроить кэш, основанный на классе <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="467cf-125">The following example shows how to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="467cf-126">В примере показано, как построить экземпляр записи `namedCaches` для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="467cf-126">The example shows how to configure an instance of the `namedCaches` entry for memory cache.</span></span> <span data-ttu-id="467cf-127">Для имени кэша задается имя записи кэша по умолчанию, присвоенное `name` атрибуту значения "default".</span><span class="sxs-lookup"><span data-stu-id="467cf-127">The name of the cache is set to the default cache entry name by setting the `name` attribute to "Default".</span></span>  
  
<span data-ttu-id="467cf-128">Атрибутам `cacheMemoryLimitMegabytes` и `physicalMemoryPercentage` присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="467cf-128">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="467cf-129">Это означает, что эвристика автомасштабирования <xref:System.Runtime.Caching.MemoryCache> используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="467cf-129">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="467cf-130">Реализация кэша должна каждые две минуты сравнивать текущую загрузку памяти с абсолютными и процентными ограничениями по памяти.</span><span class="sxs-lookup"><span data-stu-id="467cf-130">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="467cf-131">См. также</span><span class="sxs-lookup"><span data-stu-id="467cf-131">See also</span></span>

- [<span data-ttu-id="467cf-132">\<Элемент > memoryCache (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="467cf-132">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
