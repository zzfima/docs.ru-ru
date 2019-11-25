---
title: Элемент <defaultHttpCachePolicy> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy
helpviewer_keywords:
- defaultHttpCachePolicy element
- <defaultHttpCachePolicy> element
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
ms.openlocfilehash: c5029a7d1e53c28d0abb232efdc3e0bd2c9658d4
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088420"
---
# <a name="defaulthttpcachepolicy-element-network-settings"></a>Элемент \<Дефаулсттпкачеполици > (параметры сети)
Описывает, активно ли кэширование HTTP и описывает политику кэширования по умолчанию.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<элемент requestcaching >** ](requestcaching-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<дефаулсттпкачеполици >**

## <a name="syntax"></a>Синтаксис  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`maximumAge`|Указывает максимальный интервал времени, по истечении которого кэшированный объект помечается как истекший.|  
|`maximumStale`|Указывает максимальное время после истечения срока действия вычисленного объекта до пометки времени, когда кэшированный объект помечается как истекший.|  
|`minimumFresh`|Указывает минимальное время, в течение которого кэшированный объект будет считаться актуальным.|  
|`policyLevel`|Указывает, является ли политика кэширования автоматическим, или же кэш будет пропущен. Значение по умолчанию — `BypassCache`.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствуют  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[Элемент requestcaching](requestcaching-element-network-settings.md)|Управляет механизмом кэширования для сетевых запросов.|  
  
## <a name="remarks"></a>Заметки  
 Значением атрибута `policyLevel` является либо `BypassCache`, либо `Default`.  
  
 Значения для элементов `maximumAge`, `maximumStale`и `minimumFresh` являются либо явным интервалом времени, форматом *d*. *чч*:*мм*:*СС* (дни, часы, минуты и секунды) или константы `minValue` или `maxValue`, соответственно.  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как задать минимальное новое время в 6 часов, максимальное время существования, равное двум дням, и максимальное устаревшее время, равное четырем часам.  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultHttpCachePolicy  
        minimumFresh="0.06:00:00"  
        maximumAge="2.00:00:00"  
        maximumStale="0.04:00:00"
      />  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [Схема параметров сети](index.md)
