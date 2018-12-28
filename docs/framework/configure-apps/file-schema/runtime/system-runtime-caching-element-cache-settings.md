---
title: '&lt;System.Runtime.Caching&gt; (параметры кэша)'
ms.date: 03/30/2017
helpviewer_keywords:
- <system.runtime.caching> element
- caching [.NET Framework], configuration
- system.runtime.caching element
ms.assetid: 9b44daee-874a-4bd1-954e-83bf53565590
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: daa08bb8a92a13941093a77f580318558dc14e9c
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610376"
---
# <a name="ltsystemruntimecachinggt-element-cache-settings"></a>&lt;System.Runtime.Caching&gt; (параметры кэша)
Обеспечивает настройку реализации <xref:System.Runtime.Caching.ObjectCache> в памяти по умолчанию посредством записи `memoryCache` в файле конфигурации.  
  
 \<configuration>  
\<System.Runtime.Caching >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.runtime.caching >  
   <!-- child elements -->  
</system.runtime.caching >  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 `None`  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<memoryCache>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|Определяет элемент, используемый для настройки кэша, который основан на классе <xref:System.Runtime.Caching.MemoryCache> .|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Указывает корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] .|  
  
## <a name="remarks"></a>Примечания  
 Классы в этом пространстве имен предоставляют способ использования средств кэширования, например таких, которые имеются в ASP.NET, но без зависимости от сборки `System.Web` . Для получения дополнительной информации см. [Caching in .NET Framework Applications](../../../../../docs/framework/performance/caching-in-net-framework-applications.md).  
  
> [!NOTE]
>  Функции кэширования вывода и типы в пространстве имен <xref:System.Runtime.Caching> являются новыми в [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как настроить кэш, основанный на классе <xref:System.Runtime.Caching.MemoryCache> . В примере показано, как построить экземпляр записи `namedCaches` для кэша памяти. В качестве имени кэша задано имя записи кэша по умолчанию посредством задания для атрибута `name` значения "default".  
  
 Атрибутам `cacheMemoryLimitMegabytes` и `physicalMemoryPercentage` присваивается нулевое значение. Это означает, что эвристика автомасштабирования <xref:System.Runtime.Caching.MemoryCache> используется по умолчанию. Реализация кэша должна каждые две минуты сравнивать текущую загрузку памяти с абсолютными и процентными ограничениями по памяти.  
  
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
  
## <a name="see-also"></a>См. также  
- [\<memoryCache > (параметры кэша)](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)
