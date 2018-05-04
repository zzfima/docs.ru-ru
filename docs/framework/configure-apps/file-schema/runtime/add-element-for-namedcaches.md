---
title: '&lt;Добавить&gt; элемент для &lt;namedCaches&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d65dfd9a1560f2657f48b327277b64ab77014b47
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-element-for-ltnamedcachesgt"></a>&lt;Добавить&gt; элемент для &lt;namedCaches&gt;
Добавляет `namedCache` запись `namedCaches` коллекции для кэш-памяти.  
  
 \<System.Runtime.Caching >  
\<memoryCache >  
\<namedCaches >  
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
  
|Атрибут|Описание|  
|-|-|  
|`CacheMemoryLimitMegabytes`|Целочисленное значение, указывающее максимально допустимый размер (в мегабайтах), экземпляр <xref:System.Runtime.Caching.MemoryCache> могут увеличиваться до. Значение по умолчанию — 0, это означает, что <xref:System.Runtime.Caching.MemoryCache> эвристические методы класса используются по умолчанию.|  
|`Name`|Имя кэша.|  
|`PhysicalMemoryLimitPercentage`|Целочисленное значение от 0 до 100, указывающее максимальную долю физической памяти, может использоваться кэшем. Значение по умолчанию — 0, это означает, что <xref:System.Runtime.Caching.MemoryCache> эвристические методы класса используются по умолчанию.|  
|`PollingInterval`|Значение, указывающее интервал, по истечении которого реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями по памяти, заданными для данного экземпляра кэша. Это значение вводится в формате «Чч».|  
  
### <a name="child-elements"></a>Дочерние элементы  
 `None`  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<namedCaches>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|Содержит коллекцию параметров конфигурации для именованного <xref:System.Runtime.Caching.MemoryCache> экземпляров.|  
  
## <a name="remarks"></a>Примечания  
 `add` Элемент добавляет запись `namedCaches` коллекции для кэш-памяти. Можно использовать [снимите](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) элемент, прежде чем использовать `add` элемент, чтобы быть уверенным, что никакие другие именованные кэши в коллекции. Этот элемент может использоваться в файле machine.config и в файле Web.config.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как для определения параметров по умолчанию `namedCache` запись `namedCaches` коллекции для кэш-памяти.  
  
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
 [\<namedCaches > элемент (параметры кэша)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
