---
title: "&lt;requestCaching&gt; элемент (параметры сети)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requestCaching
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching
helpviewer_keywords:
- requestCaching element
- <requestCaching> element
ms.assetid: 9962a2fe-cbda-41a6-9377-571811eaea84
caps.latest.revision: "20"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 35665bd79a14b74e192fed439e935936411d85c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltrequestcachinggt-element-network-settings"></a>&lt;requestCaching&gt; элемент (параметры сети)
Определяет механизм кэширования для сетевых запросов.  
  
 \<configuration>  
\<System.NET >  
\<requestCaching >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
      <requestCaching>  
        isPrivateCache ="true|false"  
        disableAllCaching="true|false"  
        defaultPolicyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
        unspecifiedMaximumAge= "d.hh.mm.ss">  
          <defaultHttpCachePolicy> … </defaultHttpCachePolicy>  
          <defaultFtpCachePolicy> … </defaultFtpCachePolicy>  
      </requestCaching>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|`isPrivateCache`|Указывает, предоставляет ли кэш изоляцию сведений различных пользователей. Значение по умолчанию — `true`. Это значение должно быть `false` для приложений среднего уровня.|  
|`disableAllCaching`|Указывает, что кэширование отключено для всех веб-откликов и не может быть переопределено программным способом.|  
|`defaultPolicyLevel`|Одно из значений в перечислении <xref:System.Net.Cache.RequestCacheLevel>. Значение по умолчанию — `BypassCache`.|  
|`unspecifiedMaximumAge`|Указывает время по умолчанию, после которого содержимое помечается как устаревшая.|  
  
## <a name="policylevel-attribute"></a>Сохранить атрибут  
  
|Значение|Описание:|  
|-----------|-----------------|  
|`Default`|Возвращает кэшируемый ресурс, если ресурс является новым, длина содержимого точна и присутствуют истечения срока, изменения и атрибуты content-length.|  
|`BypassCache`|Возвращает ресурс с сервера.|  
|`CacheOnly`|Возвращает кэшируемый ресурс, если длина содержимого представлена и соответствует размеру записи.|  
|`CacheIfAvailable`|Возвращает кэшируемый ресурс, если длина содержимого предоставляется и соответствует размеру записи; в противном случае ресурс загружается с сервера и возвращается вызывающему.|  
|`Revalidate`|Возвращает кэшируемый ресурс, если метка времени кэшируемого ресурса совпадает с меткой времени ресурса на сервере. в противном случае ресурс загружается с сервера, хранящиеся в кэше и возвращается вызывающему объекту.|  
|`Reload`|Загружает ресурс с сервера, сохраняется в кэше и возвращает ресурс вызывающему объекту.|  
|`NoCacheNoStore`|Если кэшируемый ресурс существует, она удаляется. Ресурс загружается с сервера и возвращается вызывающему объекту.|  
|`Revalidate`|Выполняет запрос, используя кэшированную копию ресурса, если метка времени совпадает с меткой времени ресурса на сервере. в противном случае ресурс загружается с сервера, представленных вызывающему объекту и хранится в кэше,|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[defaultHttpCachePolicy](../../../../../docs/framework/configure-apps/file-schema/network/defaulthttpcachepolicy-element-network-settings.md)|Необязательный элемент.<br /><br /> Описывает указывает, активна ли функция HTTP-кэширования и описывает политику кэширования по умолчанию.|  
|[\<defaultFtpCachePolicy > Element (Network Settings)](../../../../../docs/framework/configure-apps/file-schema/network/defaultftpcachepolicy-element-network-settings.md)|Необязательный элемент.<br /><br /> Описывает указывает, активна ли функция FTP-кэширования и описывает политику кэширования по умолчанию.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
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
 <xref:System.Net.Cache?displayProperty=nameWithType>  
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
