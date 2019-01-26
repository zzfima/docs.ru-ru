---
title: '&lt;Добавить&gt; элемент для &lt;namedCaches&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: 0a292d5bdde019c4c01385a2126de29c3eea7afb
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/26/2019
ms.locfileid: "55084085"
---
# <a name="ltaddgt-element-for-ltnamedcachesgt"></a>&lt;Добавить&gt; элемент для &lt;namedCaches&gt;
Добавляет `namedCache` запись `namedCaches` коллекции для кэша памяти.  
  
 \<system.runtime.caching>  
\<memoryCache>  
\<namedCaches>  
\<add>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<namedCaches>  
    <add name="default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a>Тип  
 `None`  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание:|  
|-|-|  
|`CacheMemoryLimitMegabytes`|Целочисленное значение, указывающее максимально допустимый размер (в мегабайтах), экземпляр <xref:System.Runtime.Caching.MemoryCache> может увеличиться. Значение по умолчанию — 0, это означает, что <xref:System.Runtime.Caching.MemoryCache> класса эвристические методы, используемые по умолчанию.|  
|`Name`|Имя кэша.|  
|`PhysicalMemoryLimitPercentage`|Целочисленное значение от 0 до 100, указывающее максимальную долю физической памяти, который может использоваться кэшем. Значение по умолчанию — 0, это означает, что <xref:System.Runtime.Caching.MemoryCache> класса эвристические методы, используемые по умолчанию.|  
|`PollingInterval`|Значение, указывающее интервал, по истечении которого реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями по памяти, заданными для данного экземпляра кэша. Это значение вводится в формате «Чч: мм:».|  
  
### <a name="child-elements"></a>Дочерние элементы  
 `None`  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<namedCaches>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|Содержит коллекцию параметров конфигурации для именованного <xref:System.Runtime.Caching.MemoryCache> экземпляров.|  
  
## <a name="remarks"></a>Примечания  
 `add` Элемент добавляет запись в `namedCaches` коллекции для кэша памяти. Можно использовать [снимите](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) элемент, прежде чем использовать `add` элемент, чтобы быть уверенным, что никакие другие именованные кэши в коллекции. Этот элемент может использоваться в файле machine.config и в файле Web.config.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как для определения параметров по умолчанию `namedCache` запись `namedCaches` коллекции для кэша памяти.  
  
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
  
## <a name="see-also"></a>См. также
- [\<namedCaches > (параметры кэша)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
