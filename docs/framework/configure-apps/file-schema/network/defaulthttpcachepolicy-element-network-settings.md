---
title: '&lt;defaultHttpCachePolicy&gt; (сетевые параметры)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy
helpviewer_keywords:
- defaultHttpCachePolicy element
- <defaultHttpCachePolicy> element
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
ms.openlocfilehash: d88d99b663b0aaeb0ae432cf02675a45c4c8bc1f
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192009"
---
# <a name="ltdefaulthttpcachepolicygt-element-network-settings"></a>&lt;defaultHttpCachePolicy&gt; (сетевые параметры)
Описывает указывает, активна ли HTTP-кэширования и описывает политику кэширования по умолчанию.  
  
 \<configuration>  
\<System.NET >  
\<requestCaching >  
\<defaultHttpCachePolicy >  
  
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
|`maximumAge`|Указывает максимальный интервал времени, кэшированный объект будет помечена как просроченная.|  
|`maximumStale`|Указывает максимальное время после запрограммированного обновления срока действия кэшированного объекта будет помечена как просроченная.|  
|`minimumFresh`|Указывает минимальное время актуальности кэшированного объекта.|  
|`policyLevel`|Указывает, является ли политика кэширования автоматической или кэш пропускается. Значение по умолчанию — `BypassCache`.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[requestCaching](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Определяет механизм кэширования для сетевых запросов.|  
  
## <a name="remarks"></a>Примечания  
 Значение для `policyLevel` атрибут является либо `BypassCache` или `Default`.  
  
 Значения для `maximumAge`, `maximumStale`, и `minimumFresh` элементы, либо как явные временные интервалы в формате *d*. *hh*:*мм*:*ss* (дни, часы, минуты и секунды), либо как константы `minValue` или `maxValue`, соответствующим образом.  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
 Приведенный ниже показано, как указать минимальное время актуальности шести часов, максимальный срок жизни за два дня и максимальное время устаревания четыре часа.  
  
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
- [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
