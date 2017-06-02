---
title: "Элемент &lt;defaultFtpCachePolicy&gt; (параметры сети) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultFtpCachePolicy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultFtpCachePolicy"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<defaultFtpCachePolicy> - элемент"
  - "defaultFtpCachePolicy - элемент"
ms.assetid: 0eb0c5cb-dd97-484d-8614-785e88877abb
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# Элемент &lt;defaultFtpCachePolicy&gt; (параметры сети)
Указывает, активна ли функция FTP\-кэширования, и описывает политику кэширования по умолчанию.  
  
## Синтаксис  
  
```  
< defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`policyLevel`|Задает политику FTP\-кэширования.  Значение по умолчанию — `Default`.|  
  
## Атрибут policyLevel  
  
|Значение|Описание|  
|--------------|--------------|  
|`Default`|Возвращение кэшируемого ресурса, если ресурс является новым, длина содержимого точна и присутствуют атрибуты истечения срока, модификации и длины содержания.|  
|`BypassCache`|Возвращение ресурса с сервера.|  
|`CacheOnly`|Возвращает кэшируемый ресурс, если длина содержания указана и соответствует размеру записи.|  
|`CacheIfAvailable`|Возвращение кэшируемого ресурса, если указана длина содержания и она соответствует размеру записи, в противном случае ресурс загружается с сервера и возвращается вызывающему абоненту.|  
|`Revalidate`|Возвращает кэшируемый ресурс, если метка времени кэшируемого ресурса совпадает с меткой времени ресурса на сервере, в противном случае ресурс загружается с сервера, сохраняется в кэше и возвращается вызывающему абоненту.|  
|`Reload`|Загрузка ресурса с сервера, сохранение его в кэше и возвращение ресурса вызывающему объекту.|  
|`NoCacheNoStore`|Если кэшируемый ресурс существует, он удаляется.  Ресурс загружается с сервера и возвращается вызывающему абоненту.|  
|`Revalidate`|Выполняет запрос, используя кэшированную копию ресурса, если метка времени ресурса совпадает с меткой времени ресурса на сервере, в противном случае ресурс загружается с сервера, представляется вызывающему объекту и сохраняется в кэше.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[requestCaching](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Управляет механизмом кэширования сетевых запросов.|  
  
## Заметки  
  
## Пример  
 В приведенном ниже примере кода показано, как определить политику кэширования FTP `NoCacheNoStore`.  
  
```  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultFtpCachePolicy  
        Level="NoCacheNoStore">  
      </defaultFtpCachePolicy>  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## См. также  
 <xref:System.Net.Cache>   
 <xref:System.Net.WebRequest>   
 <xref:System.Net.Cache.RequestCacheLevel>   
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)