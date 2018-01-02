---
title: "&lt;System.Runtime.Caching&gt; элемент (параметры кэша)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <system.runtime.caching> element
- caching [.NET Framework], configuration
- system.runtime.caching element
ms.assetid: 9b44daee-874a-4bd1-954e-83bf53565590
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 83964d3a6e07267eaa946fa306301bc6d0d16e8f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltsystemruntimecachinggt-element-cache-settings"></a><span data-ttu-id="cf05e-102">&lt;System.Runtime.Caching&gt; элемент (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="cf05e-102">&lt;system.runtime.caching&gt; Element (Cache Settings)</span></span>
<span data-ttu-id="cf05e-103">Обеспечивает настройку реализации <xref:System.Runtime.Caching.ObjectCache> в памяти по умолчанию посредством записи `memoryCache` в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cf05e-103">Provides configuration for the default in-memory <xref:System.Runtime.Caching.ObjectCache> implementation through the `memoryCache` entry in the configuration file.</span></span>  
  
 <span data-ttu-id="cf05e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="cf05e-104">\<configuration></span></span>  
<span data-ttu-id="cf05e-105">\<System.Runtime.Caching ></span><span class="sxs-lookup"><span data-stu-id="cf05e-105">\<system.runtime.caching></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf05e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cf05e-106">Syntax</span></span>  
  
```xml  
<system.runtime.caching >  
   <!-- child elements -->  
</system.runtime.caching >  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cf05e-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cf05e-107">Attributes and Elements</span></span>  
 <span data-ttu-id="cf05e-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cf05e-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cf05e-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cf05e-109">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="cf05e-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cf05e-110">Child Elements</span></span>  
  
|<span data-ttu-id="cf05e-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="cf05e-111">Element</span></span>|<span data-ttu-id="cf05e-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="cf05e-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cf05e-113">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="cf05e-113">\<memoryCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|<span data-ttu-id="cf05e-114">Определяет элемент, используемый для настройки кэша, который основан на классе <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="cf05e-114">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cf05e-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cf05e-115">Parent Elements</span></span>  
  
|<span data-ttu-id="cf05e-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="cf05e-116">Element</span></span>|<span data-ttu-id="cf05e-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="cf05e-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cf05e-118">\<configuration></span><span class="sxs-lookup"><span data-stu-id="cf05e-118">\<configuration></span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="cf05e-119">Указывает корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cf05e-119">Specifies the root element in every configuration file that is used by the common language runtime and [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf05e-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="cf05e-120">Remarks</span></span>  
 <span data-ttu-id="cf05e-121">Классы в этом пространстве имен предоставляют способ использования средств кэширования, например таких, которые имеются в ASP.NET, но без зависимости от сборки `System.Web` .</span><span class="sxs-lookup"><span data-stu-id="cf05e-121">The classes in this namespace provide a way to use caching facilities like those in ASP.NET, but without a dependency on the `System.Web` assembly.</span></span> <span data-ttu-id="cf05e-122">Для получения дополнительной информации см. [Caching in .NET Framework Applications](../../../../../docs/framework/performance/caching-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="cf05e-122">For more information, see [Caching in .NET Framework Applications](../../../../../docs/framework/performance/caching-in-net-framework-applications.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf05e-123">Функции кэширования вывода и типы в пространстве имен <xref:System.Runtime.Caching> являются новыми в [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf05e-123">The output caching functionality and types in the <xref:System.Runtime.Caching> namespace are new in [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf05e-124">Пример</span><span class="sxs-lookup"><span data-stu-id="cf05e-124">Example</span></span>  
 <span data-ttu-id="cf05e-125">В следующем примере кода показано, как настроить кэш, основанный на классе <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="cf05e-125">The following example shows how to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="cf05e-126">В примере показано, как построить экземпляр записи `namedCaches` для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="cf05e-126">The example shows how to configure an instance of the `namedCaches` entry for memory cache.</span></span> <span data-ttu-id="cf05e-127">В качестве имени кэша задано имя записи кэша по умолчанию посредством задания для атрибута `name` значения "default".</span><span class="sxs-lookup"><span data-stu-id="cf05e-127">The name of the cache is set to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="cf05e-128">Атрибутам `cacheMemoryLimitMegabytes` и `physicalMemoryPercentage` присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="cf05e-128">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="cf05e-129">Это означает, что эвристика автомасштабирования <xref:System.Runtime.Caching.MemoryCache> используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cf05e-129">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="cf05e-130">Реализация кэша должна каждые две минуты сравнивать текущую загрузку памяти с абсолютными и процентными ограничениями по памяти.</span><span class="sxs-lookup"><span data-stu-id="cf05e-130">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
```xml  
<configuration>  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf05e-131">См. также</span><span class="sxs-lookup"><span data-stu-id="cf05e-131">See Also</span></span>  
 [<span data-ttu-id="cf05e-132">\<memoryCache > элемент (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="cf05e-132">\<memoryCache> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)
