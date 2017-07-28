---
title: "Элемент &lt;requestCaching&gt; (параметры сети) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#requestCaching"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<requestCaching> - элемент"
  - "requestCaching - элемент"
ms.assetid: 9962a2fe-cbda-41a6-9377-571811eaea84
caps.latest.revision: 20
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 20
---
# Элемент &lt;requestCaching&gt; (параметры сети)
Управляет механизмом кэширования сетевых запросов.  
  
## Синтаксис  
  
```  
  
      <requestCaching  
  isPrivateCache ="true|false"  
  disableAllCaching="true|false"  
  defaultPolicyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
  unspecifiedMaximumAge= "d.hh.mm.ss""  
  <defaultHttpCachePolicy> … </defaultHttpCachePolicy>  
  <defaultFtpCachePolicy> … </defaultFtpCachePolicy>  
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`isPrivateCache`|Задание того, обеспечивает ли кэш изоляцию сведений различных пользователей.  Значение по умолчанию — `true`.  Для приложений среднего уровня это значение должно быть равно `false`.|  
|`disableAllCaching`|Задание того, что кэширование отключено для всех веб\-откликов и не может быть переопределено программным способом.|  
|`defaultPolicyLevel`|Одно из значений перечисления <xref:System.Net.Cache.RequestCacheLevel>.  Значение по умолчанию — `BypassCache`.|  
|`unspecifiedMaximumAge`|Задание времени по умолчанию, по истечении которого содержимое помечается как устаревшее.|  
  
## Атрибут policyLevel  
  
|Значение|Описание|  
|--------------|--------------|  
|`Default`|Возвращение кэшируемого ресурса, если ресурс является новым, длина содержимого точна и присутствуют атрибуты истечения срока, модификации и длины содержания.|  
|`BypassCache`|Возвращение ресурса с сервера.|  
|`CacheOnly`|Возвращает кэшируемый ресурс, если длина содержания указана и соответствует размеру записи.|  
|`CacheIfAvailable`|Возвращение кэшируемого ресурса, если указана длина содержания и она соответствует размеру записи, в противном случае ресурс загружается с сервера и возвращается вызывающему абоненту.|  
|`Revalidate`|Возвращает кэшируемый ресурс, если метка времени кэшируемого ресурса совпадает с меткой времени ресурса на сервере, в противном случае ресурс загружается с сервера, сохраняется в кэше и возвращается вызывающему объекту.|  
|`Reload`|Загрузка ресурса с сервера, сохранение его в кэше и возвращение ресурса вызывающему объекту.|  
|`NoCacheNoStore`|Если кэшируемый ресурс существует, он удаляется.  Ресурс загружается с сервера и возвращается вызывающему абоненту.|  
|`Revalidate`|Удовлетворение запроса с помощью кэшируемой копии ресурса, если метка времени ресурса совпадает с меткой времени ресурса на сервере, в противном случае ресурс загружается с сервера, представляется вызывающему объекту и сохраняется в кэше.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[defaultHttpCachePolicy](../../../../../docs/framework/configure-apps/file-schema/network/defaulthttpcachepolicy-element-network-settings.md)|Необязательный элемент.<br /><br /> Указывает, активна ли функция HTTP\-кэширования, и описывает политику кэширования по умолчанию.|  
|[Элемент \<defaultFtpCachePolicy\> \(параметры сети\)](../../../../../docs/framework/configure-apps/file-schema/network/defaultftpcachepolicy-element-network-settings.md)|Необязательный элемент.<br /><br /> Указывает, активна ли функция FTP\-кэширования, и описывает политику кэширования по умолчанию.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[system.net](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Содержит параметры, определяющие способ подключения платформы .NET Framework к сети.|  
  
## Пример  
 В следующем примере кода показано, как выключить все кэширование.  
  
```  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## См. также  
 <xref:System.Net.Cache?displayProperty=fullName>   
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)