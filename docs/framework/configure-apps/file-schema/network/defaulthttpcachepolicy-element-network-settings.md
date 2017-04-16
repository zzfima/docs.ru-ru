---
title: "Элемент &lt;defaultHttpCachePolicy&gt; (параметры сети) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<defaultHttpCachePolicy> - элемент"
  - "defaultHttpCachePolicy - элемент"
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
caps.latest.revision: 19
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 19
---
# Элемент &lt;defaultHttpCachePolicy&gt; (параметры сети)
Указывает, активна ли функция HTTP\-кэширования, и описывает политику кэширования по умолчанию.  
  
## Синтаксис  
  
```  
< defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss"|"minValue"  
  maximumAge  ="d.hh:mm:ss"|"maxValue"  
  maximumStale="d.hh:mm:ss"|"maxValue"  
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`maximumAge`|Задает максимальный интервал времени до присвоения кэшированному объекту пометки об истечении срока действия.|  
|`maximumStale`|Задает максимальный интервал времени после запрограммированного обновления до присвоения кэшированному объекту пометки об истечении срока действия.|  
|`minimumFresh`|Задает минимальное время актуальности кэшированного объекта.|  
|`policyLevel`|Указывает, является ли политика кэширования автоматической или кэш пропускается.  Значение по умолчанию — `BypassCache`.|  
  
### Дочерние элементы  
 Нет  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[requestCaching](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Управляет механизмом кэширования сетевых запросов.|  
  
## Заметки  
 Значение атрибута `policyLevel` равно `BypassCache` или `Default`.  
  
 Значения элементов `maximumAge`, `maximumStale` и `minimumFresh` задаются либо как явные временные интервалы в формате *d*.*hh*:*mm*:*ss* \(дни, часы, минуты и секунды\), либо константами `minValue` или `maxValue`, в зависимости от ситуации.  
  
## Файлы конфигурации  
 Этот элемент может быть использован в файле конфигурации приложения или в файле конфигурации компьютера \(Machine.config\).  
  
## Пример  
 Следующий пример кода задает минимальное время актуальности равное шести часам, максимальный срок жизни равный двум дням и максимальное время устаревания равное четырем часам.  
  
```  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultHttpCachePolicy>  
        <set minimumFresh="0.06:00:00" />  
        <set maximumAge  ="2.00:00:00" />  
        <set maximumStale="0.04:00:00" />  
      </defaultHttpCachePolicy>  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## См. также  
 <xref:System.Net.Cache>   
 <xref:System.Net.WebRequest>   
 <xref:System.Net.Cache.RequestCacheLevel>   
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)