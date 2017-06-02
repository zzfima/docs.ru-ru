---
title: "Элемент &lt;namedCaches&gt; (параметры кэша) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<namedCaches> - элемент"
  - "кэширование [платформа .NET Framework], конфигурация"
  - "namedCaches - элемент"
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# Элемент &lt;namedCaches&gt; (параметры кэша)
Задает коллекцию параметров конфигурации для именованных экземпляров <xref:System.Runtime.Caching.MemoryCache>.  Свойство <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> ссылается на коллекцию параметров конфигурации из одного или нескольких элементов `namedCaches` файла конфигурации.  
  
## Синтаксис  
  
```  
<namedCaches>  
  <add name="default"   
</namedCaches>  
```  
  
## Тип  
 `None`  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`CacheMemoryLimitMegabytes`|Целое значение, которое задает максимально допустимый размер \(в мегабайтах\), до которого может увеличиться объект <xref:System.Runtime.Caching.MemoryCache>.  Значение по умолчанию равно 0, что свидетельствует о том, что эвристические механизмы автоматического изменения размера класса <xref:System.Runtime.Caching.MemoryCache> используются по умолчанию.|  
|`Name`|Имя кэша.|  
|`PhysicalMemoryLimitPercentage`|Целое число от 0 до 100, задающее максимальный процент физической памяти, который может использоваться кэшем.  Значение по умолчанию равно 0, что свидетельствует о том, что эвристические механизмы автоматического изменения размера класса <xref:System.Runtime.Caching.MemoryCache> используются по умолчанию.|  
|`PollingInterval`|Значение, обозначающее интервал времени, по истечении которого реализация кэша сравнивает текущую загрузку памяти с абсолютными и относительными ограничениями памяти, заданными для экземпляра кэша.  Это значение вводится в формате "ЧЧ: ММ: СС".|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/runtime/add-element-for-namedcaches.md)|Добавляет именованный кэш в коллекцию `namedCaches` для кэша памяти.|  
|[\<clear\>](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md)|Очищает коллекцию `namedCaches` для кэша памяти.|  
|[\<remove\>](../../../../../docs/framework/configure-apps/file-schema/runtime/remove-element-for-namedcaches.md)|Удаляет запись именованного кэша из коллекции `namedCaches` для кэша памяти.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<memoryCache\>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|Определяет элемент, используемый для настройки кэша, основанного на классе <xref:System.Runtime.Caching.MemoryCache>.|  
  
## Заметки  
 Раздел конфигурации кэша памяти в файле Web.config может содержать атрибуты `add`, `remove` и `clear` коллекции `namedCaches`.  Каждая запись `namedCaches` однозначно определяется атрибутом `name`.  
  
 Экземпляры записей кэша памяти можно получить путем ссылки на сведения в файлах конфигурации приложения.  По умолчанию в файле конфигурации имеется запись только для экземпляра кэша по умолчанию.  Экземпляр кэша по умолчанию — это экземпляр, возвращаемый свойством <xref:System.Runtime.Caching.MemoryCache.Default%2A>.  
  
 Если задано имя атрибута "default", элемент использует экземпляр кэша памяти по умолчанию.  
  
## Пример  
 В следующем примере показано, как задать для имени кэша имя записи кэша по умолчанию, указав для атрибута `name` значение "default".  
  
 Атрибуты `cacheMemoryLimitMegabytes` и `physicalMemoryPercentage` установлены равными нулю.  Установка этих атрибутов в нулевое значение означает, что используются эвристические методы класса <xref:System.Runtime.Caching.MemoryCache> для автоматического изменения размера.  Реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями памяти каждые две минуты.  
  
```  
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
  
## См. также  
 [Элемент \<MemoryCache\> \(параметры кэша\)](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)