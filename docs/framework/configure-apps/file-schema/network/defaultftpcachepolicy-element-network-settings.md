---
title: Элемент <defaultFtpCachePolicy> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultFtpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultFtpCachePolicy
helpviewer_keywords:
- <defaultFtpCachePolicy> element
- defaultFtpCachePolicy element
ms.assetid: 0eb0c5cb-dd97-484d-8614-785e88877abb
ms.openlocfilehash: 36d174beea58ff96674bd873bfbcb8be89591669
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674562"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a>\<defaultFtpCachePolicy > (сетевые параметры)
Описывает указывает, активна ли функция FTP-кэширования и описывает политику кэширования по умолчанию.  
  
 \<configuration>  
\<system.net>  
\<requestCaching>  
\<defaultFtpCachePolicy>  
  
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

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
