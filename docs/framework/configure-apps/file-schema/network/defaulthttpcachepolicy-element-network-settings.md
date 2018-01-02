---
title: "&lt;defaultHttpCachePolicy&gt; элемент (параметры сети)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy
helpviewer_keywords:
- defaultHttpCachePolicy element
- <defaultHttpCachePolicy> element
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
caps.latest.revision: "19"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 048d9a373c77e530bd352b3caa0e122b3833a5c2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltdefaulthttpcachepolicygt-element-network-settings"></a>&lt;defaultHttpCachePolicy&gt; элемент (параметры сети)
Описывает указывает, активна ли функция HTTP-кэширования и описывает политику кэширования по умолчанию.  
  
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
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|`maximumAge`|Указывает максимальный интервал времени перед кэшированный объект помечается как устаревшая.|  
|`maximumStale`|Указывает максимальный интервал времени после запрограммированного обновления время ожидания до кэшированный объект помечается как устаревшая.|  
|`minimumFresh`|Указывает минимальное время актуальности кэшированного объекта.|  
|`policyLevel`|Указывает, является ли политика кэширования автоматической или кэш пропускается. Значение по умолчанию — `BypassCache`.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[requestCaching](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Определяет механизм кэширования для сетевых запросов.|  
  
## <a name="remarks"></a>Примечания  
 Значение для `policyLevel` атрибут является либо `BypassCache` или `Default`.  
  
 Значения для `maximumAge`, `maximumStale`, и `minimumFresh` элементы, либо явные временной интервал, в формате *d*. *hh*:*мм*:*ss* (дней, часов, минут и секунд), или константы `minValue` или `maxValue`соответствующим образом.  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
 Приведенный ниже показано, как указать минимальное время актуальности шести часов, максимальный срок жизни двух дней и максимальное время устаревания, равной четырем часам.  
  
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
 <xref:System.Net.Cache>  
 <xref:System.Net.WebRequest>  
 <xref:System.Net.Cache.RequestCacheLevel>  
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
