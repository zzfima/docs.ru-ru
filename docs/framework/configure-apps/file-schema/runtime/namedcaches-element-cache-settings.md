---
title: '&lt;namedCaches&gt; (параметры кэша)'
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
author: mcleblanc
ms.author: markl
ms.openlocfilehash: a824e958a2b75b28aa66a15212e0276d6c127739
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536533"
---
# <a name="ltnamedcachesgt-element-cache-settings"></a>&lt;namedCaches&gt; (параметры кэша)
Определяет коллекцию параметров конфигурации для именованного <xref:System.Runtime.Caching.MemoryCache> экземпляров. <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> Свойство ссылается на коллекцию параметров конфигурации из одного или нескольких `namedCaches` элементов файла конфигурации.  
  
 \<configuration>  
\< System.Runtime.Caching >  
\<memoryCache>  
\<namedCaches>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<namedCaches>  
  <add name="default"/>   
</namedCaches>  
```  
  
## <a name="type"></a>Тип  
 `None`  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|Целочисленное значение, указывающее максимально допустимый размер в мегабайтах, который экземпляр <xref:System.Runtime.Caching.MemoryCache> может увеличиться. Значение по умолчанию — 0, это означает, что эвристика из <xref:System.Runtime.Caching.MemoryCache> класс используются по умолчанию.|  
|`name`|Имя кэша.|  
|`physicalMemoryLimitPercentage`|Целочисленное значение от 0 до 100, указывающее максимальную долю физической памяти, который может использоваться кэшем. Значение по умолчанию — 0, это означает, что эвристика из <xref:System.Runtime.Caching.MemoryCache> класс используются по умолчанию.|  
|`pollingInterval`|Значение, указывающее интервал, по истечении которого реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями по памяти, заданными для данного экземпляра кэша. Это значение вводится в формате «Чч: мм:».|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/runtime/add-element-for-namedcaches.md)|Добавляет именованный кэш к коллекции `namedCaches` для кэша памяти.|  
|[\<clear>](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md)|Очищает коллекцию `namedCaches` для кэша памяти.|  
|[\<remove>](../../../../../docs/framework/configure-apps/file-schema/runtime/remove-element-for-namedcaches.md)|Удаляет элемент именованного кэша из коллекции `namedCaches` для кэша памяти.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<memoryCache>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|Определяет элемент, используемый для настройки кэша, который основан на классе <xref:System.Runtime.Caching.MemoryCache> .|  
  
## <a name="remarks"></a>Примечания  
 Раздел конфигурации кэша памяти файла Web.config может содержать `add`, `remove`, и `clear` атрибуты для `namedCaches` коллекции. Каждый `namedCaches` запись однозначно идентифицируется по `name` атрибута.  
  
 Экземпляры записей кэша памяти можно получить путем ссылки на сведения в файлах конфигурации приложения. По умолчанию экземпляр кэша по умолчанию присутствует в файле конфигурации. Экземпляр кэша по умолчанию — экземпляр, который возвращается из <xref:System.Runtime.Caching.MemoryCache.Default%2A> свойство.  
  
 Если задать атрибут "name" to «default», элемент использует экземпляр по умолчанию для кэша памяти.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как присвоено имя записи кэша по умолчанию имя кэша, установив `name` атрибута значение «default».  
  
 Атрибутам `cacheMemoryLimitMegabytes` и `physicalMemoryPercentage` присваивается нулевое значение. Установка этих атрибутов в ноль означает, что эвристика из <xref:System.Runtime.Caching.MemoryCache> класс используются. Реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями памяти каждые две минуты.  
  
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
