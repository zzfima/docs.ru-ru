---
title: '&lt;defaultFtpCachePolicy&gt; (сетевые параметры)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultFtpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultFtpCachePolicy
helpviewer_keywords:
- <defaultFtpCachePolicy> element
- defaultFtpCachePolicy element
ms.assetid: 0eb0c5cb-dd97-484d-8614-785e88877abb
author: mcleblanc
ms.author: markl
ms.openlocfilehash: e03fb02bd351058c1fcdedb8367d03318418a12c
ms.sourcegitcommit: d88024e6d6d8b242feae5f4007a709379355aa24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2018
ms.locfileid: "49316445"
---
# <a name="ltdefaultftpcachepolicygt-element-network-settings"></a>&lt;defaultFtpCachePolicy&gt; (сетевые параметры)
Описывает указывает, активна ли функция FTP-кэширования и описывает политику кэширования по умолчанию.  
  
 \<configuration>  
\<System.NET >  
\<requestCaching >  
\<defaultFtpCachePolicy >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`policyLevel`|Указывает политику кэширования FTP. Значение по умолчанию — `Default`.|  
  
## <a name="policylevel-attribute"></a>policyLevel атрибут  
  
|Значение|Описание|  
|-----------|-----------------|  
|`Default`|Возвращает кэшированный ресурс, если ресурс является новым, длина содержимого точна и присутствуют атрибуты content-length, модификации и истечения срока действия.|  
|`BypassCache`|Возвращает ресурс с сервера.|  
|`CacheOnly`|Возвращает кэшированный ресурс, если длина содержимого присутствует и соответствует размеру записи.|  
|`CacheIfAvailable`|Возвращает кэшированный ресурс, если длина содержимого и соответствует размеру записи; в противном случае ресурс загружается с сервера и возвращается вызывающему объекту.|  
|`Revalidate`|Возвращает кэшированный ресурс, если метка времени используется кэшированный ресурс совпадает с меткой времени ресурса на сервере; в противном случае ресурс загружается с сервера, сохраняется в кэше и возвращается вызывающей стороне.|  
|`Reload`|Загружает ресурс с сервера, сохраняется в кэше и возвращает ресурс вызывающему объекту.|  
|`NoCacheNoStore`|Если кэшируемый ресурс существует, она удаляется. Ресурс загружается с сервера и возвращается вызывающему объекту.|  
|`Revalidate`|Выполняет запрос с помощью кэшированной копии ресурса, если метка времени совпадает с меткой времени ресурса на сервере; в противном случае ресурс загружается с сервера, представляется вызывающему и сохраняется в кэше.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[requestCaching](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Определяет механизм кэширования для сетевых запросов.|  
  
## <a name="remarks"></a>Примечания  
  
## <a name="example"></a>Пример  
 В следующем примере показано задание политики кэширования для FTP `NoCacheNoStore`.  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultFtpCachePolicy  
        policyLevel="NoCacheNoStore">  
      </defaultFtpCachePolicy>  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Net.Cache>  
 <xref:System.Net.WebRequest>  
 <xref:System.Net.Cache.RequestCacheLevel>  
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
