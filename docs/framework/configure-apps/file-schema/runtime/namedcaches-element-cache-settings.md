---
title: "&lt;namedCaches&gt; элемент (параметры кэша)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: bdafddcb05dd50f059c9f6804573beec085a4a2a
ms.sourcegitcommit: d0f7646d67db5809cf43ff1d27b399a4020e8ee2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2017
---
# <a name="ltnamedcachesgt-element-cache-settings"></a>&lt;namedCaches&gt; элемент (параметры кэша)
Задает коллекцию параметров конфигурации для именованного <xref:System.Runtime.Caching.MemoryCache> экземпляров. <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> Свойство ссылается на коллекцию параметров конфигурации из одного или нескольких `namedCaches` элементы файла конфигурации.  
  
 \<configuration>  
\<System.Runtime.Caching >  
\<memoryCache >  
\<namedCaches >  
  
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
|`cacheMemoryLimitMegabytes`|Целочисленное значение, указывающее максимально допустимый размер в мегабайтах, который экземпляр <xref:System.Runtime.Caching.MemoryCache> могут увеличиваться до. Значение по умолчанию — 0, это означает, что эвристические методы из <xref:System.Runtime.Caching.MemoryCache> класс, используемый по умолчанию.|  
|`name`|Имя кэша.|  
|`physicalMemoryLimitPercentage`|Целочисленное значение от 0 до 100, указывающее максимальную долю физической памяти, может использоваться кэшем. Значение по умолчанию — 0, это означает, что эвристические методы из <xref:System.Runtime.Caching.MemoryCache> класс, используемый по умолчанию.|  
|`pollingInterval`|Значение, указывающее интервал, по истечении которого реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями по памяти, заданными для данного экземпляра кэша. Это значение вводится в формате «Чч».|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/runtime/add-element-for-namedcaches.md)|Добавляет именованный кэш к коллекции `namedCaches` для кэша памяти.|  
|[\<clear>](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md)|Очищает коллекцию `namedCaches` для кэша памяти.|  
|[\<remove>](../../../../../docs/framework/configure-apps/file-schema/runtime/remove-element-for-namedcaches.md)|Удаляет элемент именованного кэша из коллекции `namedCaches` для кэша памяти.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<memoryCache>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|Определяет элемент, используемый для настройки кэша, который основан на классе <xref:System.Runtime.Caching.MemoryCache> .|  
  
## <a name="remarks"></a>Примечания  
 Раздел конфигурации памяти кэша в файле Web.config может содержать `add`, `remove`, и `clear` атрибутов для `namedCaches` коллекции. Каждый `namedCaches` входа однозначно идентифицируется `name` атрибута.  
  
 Экземпляры записей кэша памяти можно получить путем ссылки на сведения в файлах конфигурации приложения. По умолчанию экземпляр кэша по умолчанию имеет запись в файле конфигурации. Экземпляр кэша по умолчанию является экземпляр, возвращаемый <xref:System.Runtime.Caching.MemoryCache.Default%2A> свойство.  
  
 Если задать атрибут "name" to «default», элемент использует экземпляр кэша памяти по умолчанию.  
  
## <a name="example"></a>Пример  
 Приведенный ниже показано, как присвоить имя кэша имя записи кэша по умолчанию, задав `name` атрибута значение «default».  
  
 Атрибутам `cacheMemoryLimitMegabytes` и `physicalMemoryPercentage` присваивается нулевое значение. Установка этих атрибутов в ноль означает, что эвристические методы из <xref:System.Runtime.Caching.MemoryCache> класса используются. Реализация кэша сравнивает текущую загрузку памяти с абсолютными и относительными ограничениями памяти каждые две минуты.  
  
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
 [\<memoryCache > элемент (параметры кэша)](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)
