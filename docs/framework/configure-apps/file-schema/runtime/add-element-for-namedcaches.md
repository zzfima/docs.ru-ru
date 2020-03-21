---
title: Элемент <add> для <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: c1345022b79df371ad9c89a39a0a8b625e26608c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154509"
---
# <a name="add-element-for-namedcaches"></a>\<добавить> \<элемент для названныхCaches>
Добавляет `namedCache` запись в `namedCaches` коллекцию для кэша памяти.  
  
[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.кэширования>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<памятьCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<имени Кэшес>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<добавить>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a>Тип  
 `None`  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|attribute|Описание|  
|-|-|  
|`CacheMemoryLimitMegabytes`|Значение, которое определяет максимально допустимый размер (в мегабайтах), <xref:System.Runtime.Caching.MemoryCache> до которого может вырасти экземпляр а. Значение по умолчанию составляет 0, что означает, что аупизилистика <xref:System.Runtime.Caching.MemoryCache> класса используется по умолчанию.|  
|`Name`|Имя кэша.|  
|`PhysicalMemoryLimitPercentage`|Значение всей доли от 0 до 100, которое определяет максимальный процент физически установленной памяти компьютера, который может быть использован кэшем. Значение по умолчанию составляет 0, что означает, что аупизилистика <xref:System.Runtime.Caching.MemoryCache> класса используется по умолчанию.|  
|`PollingInterval`|Значение, указывающее интервал, по истечении которого реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями по памяти, заданными для данного экземпляра кэша. Это значение вводится в формате "HH:MM:SS".|  
  
### <a name="child-elements"></a>Дочерние элементы  
 `None`  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<имени Кэшес>](namedcaches-element-cache-settings.md)|Содержит набор параметров конфигурации <xref:System.Runtime.Caching.MemoryCache> для названных экземпляров.|  
  
## <a name="remarks"></a>Remarks  
 Элемент `add` добавляет запись в `namedCaches` коллекцию для кэша памяти. Вы можете использовать [четкий](clear-element-for-namedcaches.md) элемент, прежде чем использовать `add` элемент, чтобы быть уверенным, что в коллекции нет других названных кэшов. Этот элемент может быть использован в файле machine.config и в файле Web.config.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как `namedCache` определить параметры `namedCaches` для входа по умолчанию в коллекцию для кэша памяти.  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"
               cacheMemoryLimitMegabytes="0"
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a>См. также раздел

- [\<имени Кэши> элемент (Настройки кэша)](namedcaches-element-cache-settings.md)
