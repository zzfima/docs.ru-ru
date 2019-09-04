---
title: Элемент <namedCaches> (параметры кэша)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: 4587234ad91fa3b1abbb376bd7ae517d5abea6c3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252461"
---
# <a name="namedcaches-element-cache-settings"></a>\<Элемент > Намедкачес (параметры кэша)
Задает коллекцию параметров конфигурации для именованных <xref:System.Runtime.Caching.MemoryCache> экземпляров. Свойство ссылается на коллекцию параметров конфигурации из одного или нескольких `namedCaches` элементов файла конфигурации. <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A>  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. Runtime. Caching >** ](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<memoryCache >** ](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Намедкачес >**  
  
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
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|Целочисленное значение, указывающее максимально допустимый размер (в мегабайтах), до которого <xref:System.Runtime.Caching.MemoryCache> может увеличиваться экземпляр. Значение по умолчанию — 0. Это означает, что по умолчанию используется эвристика <xref:System.Runtime.Caching.MemoryCache> автоподбора размера класса.|  
|`name`|Имя кэша.|  
|`physicalMemoryLimitPercentage`|Целочисленное значение от 0 до 100, которое указывает максимальный процент физической памяти компьютера, который может потребляться кэшем. Значение по умолчанию — 0. Это означает, что по умолчанию используется эвристика <xref:System.Runtime.Caching.MemoryCache> автоподбора размера класса.|  
|`pollingInterval`|Значение, указывающее интервал, по истечении которого реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями по памяти, заданными для данного экземпляра кэша. Это значение указывается в формате "чч: мм: СС".|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<add>](add-element-for-namedcaches.md)|Добавляет именованный кэш к коллекции `namedCaches` для кэша памяти.|  
|[\<clear>](clear-element-for-namedcaches.md)|Очищает коллекцию `namedCaches` для кэша памяти.|  
|[\<remove>](remove-element-for-namedcaches.md)|Удаляет элемент именованного кэша из коллекции `namedCaches` для кэша памяти.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|Указывает корневой элемент в каждом файле конфигурации, который используется средой CLR и .NET Framework приложениями.|  
|[\<memoryCache>](memorycache-element-cache-settings.md)|Определяет элемент, используемый для настройки кэша, который основан на классе <xref:System.Runtime.Caching.MemoryCache> .|  
|[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)|Содержит типы, позволяющие реализовать кэширование вывода в приложениях, встроенных в .NET Framework.|  
  
## <a name="remarks"></a>Примечания  
 Раздел конфигурации кэша памяти файла Web. `add`config может содержать атрибуты, `remove`и `clear` для `namedCaches` коллекции. Каждая `namedCaches` запись уникально идентифицируется `name` атрибутом.  
  
 Экземпляры записей кэша памяти можно получить, обратившись к сведениям в файлах конфигурации приложения. По умолчанию в файле конфигурации содержится запись только для экземпляра кэша по умолчанию. Экземпляром кэша по умолчанию является экземпляр, который возвращается из <xref:System.Runtime.Caching.MemoryCache.Default%2A> свойства.  
  
 Если для атрибута name задано значение Default, то элемент использует экземпляр кэша памяти по умолчанию.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как задать имя кэша в качестве имени записи кэша по умолчанию, задав `name` для атрибута значение Default.  
  
 Атрибутам `cacheMemoryLimitMegabytes` и `physicalMemoryPercentage` присваивается нулевое значение. Установка этих атрибутов равным нулю означает, что используется эвристический <xref:System.Runtime.Caching.MemoryCache> подход автоподбора размера класса. Реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями памяти каждые две минуты.  
  
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

- [\<Элемент > memoryCache (параметры кэша)](memorycache-element-cache-settings.md)
