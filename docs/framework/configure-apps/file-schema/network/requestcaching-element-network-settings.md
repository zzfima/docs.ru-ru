---
title: '&lt;requestCaching&gt; (сетевые параметры)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requestCaching
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching
helpviewer_keywords:
- requestCaching element
- <requestCaching> element
ms.assetid: 9962a2fe-cbda-41a6-9377-571811eaea84
ms.openlocfilehash: e5d74a033b14d5f1b523422d0afd360206c0cb48
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685017"
---
# <a name="ltrequestcachinggt-element-network-settings"></a>&lt;requestCaching&gt; (сетевые параметры)
Определяет механизм кэширования для сетевых запросов.  
  
 \<configuration>  
\<system.net>  
\<requestCaching>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<requestCaching  
  isPrivateCache ="true|false"  
  disableAllCaching="true|false"  
  defaultPolicyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
  unspecifiedMaximumAge= "d.hh.mm.ss">  
    <defaultHttpCachePolicy>...</defaultHttpCachePolicy>  
    <defaultFtpCachePolicy>...</defaultFtpCachePolicy>  
</requestCaching>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|`isPrivateCache`|Указывает, обеспечивает ли кэш изоляцию сведений различных пользователей. Значение по умолчанию — `true`. Это значение должно быть `false` для приложений среднего уровня.|  
|`disableAllCaching`|Указывает, что кэширование отключено для всех веб-откликов и не может быть переопределен программным способом.|  
|`defaultPolicyLevel`|Одно из значений в перечислении <xref:System.Net.Cache.RequestCacheLevel>. Значение по умолчанию — `BypassCache`.|  
|`unspecifiedMaximumAge`|Указывает время по умолчанию, после чего содержимое отмечено как устаревшая.|  
  
## <a name="policylevel-attribute"></a>policyLevel атрибут  
  
|Значение|Описание:|  
|-----------|-----------------|  
|`Default`|Возвращает кэшированный ресурс, если ресурс является новым, длина содержимого точна и присутствуют атрибуты content-length, модификации и истечения срока действия.|  
|`BypassCache`|Возвращает ресурс с сервера.|  
|`CacheOnly`|Возвращает кэшированный ресурс, если длина содержимого присутствует и соответствует размеру записи.|  
|`CacheIfAvailable`|Возвращает кэшированный ресурс, если длина содержимого и соответствует размеру записи; в противном случае ресурс загружается с сервера и возвращается вызывающему объекту.|  
|`Revalidate`|Возвращает кэшированный ресурс, если метка времени используется кэшированный ресурс совпадает с меткой времени ресурса на сервере; в противном случае ресурс загружается с сервера, сохраняется в кэше и возвращается вызывающему объекту.|  
|`Reload`|Загружает ресурс с сервера, сохраняется в кэше и возвращает ресурс вызывающему объекту.|  
|`NoCacheNoStore`|Если кэшируемый ресурс существует, она удаляется. Ресурс загружается с сервера и возвращается вызывающему объекту.|  
|`Revalidate`|Выполняет запрос с помощью кэшированной копии ресурса, если метка времени совпадает с меткой времени ресурса на сервере; в противном случае ресурс загружается с сервера, представляется вызывающему и хранится в кэше,|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[defaultHttpCachePolicy](../../../../../docs/framework/configure-apps/file-schema/network/defaulthttpcachepolicy-element-network-settings.md)|Необязательный элемент.<br /><br /> Описывает указывает, активна ли HTTP-кэширования и описывает политику кэширования по умолчанию.|  
|[\<defaultFtpCachePolicy > (сетевые параметры)](../../../../../docs/framework/configure-apps/file-schema/network/defaultftpcachepolicy-element-network-settings.md)|Необязательный элемент.<br /><br /> Описывает указывает, активна ли функция FTP-кэширования и описывает политику кэширования по умолчанию.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[System.NET](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.|  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как отключить кэширование всех.  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также
- <xref:System.Net.Cache?displayProperty=nameWithType>
- [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
