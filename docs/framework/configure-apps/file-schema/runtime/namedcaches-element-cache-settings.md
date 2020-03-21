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
# <a name="namedcaches-element-cache-settings"></a>\<имени Кэши> элемент (Настройки кэша)
Определяет набор параметров конфигурации для названных <xref:System.Runtime.Caching.MemoryCache> экземпляров. Свойство <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> ссылается на набор параметров конфигурации из одного или нескольких `namedCaches` элементов файла конфигурации.  
  
[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.кэширования>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<памятьCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<имени Кэшес>**  
  
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
  
|attribute|Описание|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|Значение, которое определяет максимально допустимый размер, в мегабайтах, что <xref:System.Runtime.Caching.MemoryCache> экземпляр может вырасти до. Значение по умолчанию составляет 0, что означает, что <xref:System.Runtime.Caching.MemoryCache> аупизионизация эвристики класса используется по умолчанию.|  
|`name`|Имя кэша.|  
|`physicalMemoryLimitPercentage`|Значение всей доли от 0 до 100, которое определяет максимальный процент физически установленной памяти компьютера, который может быть использован кэшем. Значение по умолчанию составляет 0, что означает, что <xref:System.Runtime.Caching.MemoryCache> аупизионизация эвристики класса используется по умолчанию.|  
|`pollingInterval`|Значение, указывающее интервал, по истечении которого реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями по памяти, заданными для данного экземпляра кэша. Это значение вводится в формате "HH:MM:SS".|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<добавить>](add-element-for-namedcaches.md)|Добавляет именованный кэш к коллекции `namedCaches` для кэша памяти.|  
|[\<ясно>](clear-element-for-namedcaches.md)|Очищает коллекцию `namedCaches` для кэша памяти.|  
|[\<удалить>](remove-element-for-namedcaches.md)|Удаляет элемент именованного кэша из коллекции `namedCaches` для кэша памяти.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<конфигурация>](../configuration-element.md)|Определяет корневой элемент в каждом файле конфигурации, который используется приложениями общего языка и приложениями .NET Framework.|  
|[\<памятьCache>](memorycache-element-cache-settings.md)|Определяет элемент, используемый для настройки кэша, который основан на классе <xref:System.Runtime.Caching.MemoryCache> .|  
|[\<system.runtime.кэширования>](system-runtime-caching-element-cache-settings.md)|Содержит типы, которые позволяют реализовать кэширование в приложениях, встроенных в рамку .NET.|  
  
## <a name="remarks"></a>Remarks  
 Раздел конфигурации кэша памяти файла `add`Web.config может содержать `remove`атрибуты для `clear` коллекции. `namedCaches` Каждая `namedCaches` запись однозначно идентифицируется `name` атрибутом.  
  
 Вы можете получить экземпляры записей кэша памяти, ссылаясь на информацию в файлах конфигурации приложения. По умолчанию только экземпляр кэша по умолчанию имеет запись в файле конфигурации. Экземпляр кэша по умолчанию — <xref:System.Runtime.Caching.MemoryCache.Default%2A> это экземпляр, который возвращается из свойства.  
  
 При установке атрибута имени на "по умолчанию" элемент использует экземпляр кэша памяти по умолчанию.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как установить имя кэша к `name` имени входа кэша по умолчанию, установив атрибут на "по умолчанию".  
  
 Атрибутам `cacheMemoryLimitMegabytes` и `physicalMemoryPercentage` присваивается нулевое значение. Установка этих атрибутов до нуля означает, что используются <xref:System.Runtime.Caching.MemoryCache> ауотизирующие эвристики класса. Реализация кэша сравнивает текущую нагрузку памяти с абсолютными и процентными ограничениями памяти каждые две минуты.  
  
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
  
## <a name="see-also"></a>См. также раздел

- [\<memoryCache> элемент (Настройки кэша)](memorycache-element-cache-settings.md)
