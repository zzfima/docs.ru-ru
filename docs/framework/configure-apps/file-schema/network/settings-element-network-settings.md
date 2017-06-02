---
title: "Элемент &lt;settings&gt; (параметры сети) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#settings"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<settings> - элемент"
  - "settings - элемент"
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
caps.latest.revision: 21
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 21
---
# Элемент &lt;settings&gt; (параметры сети)
Настраивает основные сетевые параметры для пространства имен <xref:System.Net?displayProperty=fullName>.  
  
## Синтаксис  
  
```  
  
      <settings>  
..<httpListener> … </httpListener>  
..<httpWebRequest> … </httpWebRequest>  
..<ipv6> … </ipv6>  
..<performanceCounters> … </performanceCounters>  
  <servicePointManager> … </servicePointManager>  
..<socket> … </socket>  
..<webProxyScript> … </webProxyScript>  
</settings>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Нет.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[httpListener](../../../../../docs/framework/configure-apps/file-schema/network/httplistener-element-network-settings.md)|Настраивает параметры, используемые классом <xref:System.Net.HttpListener>.|  
|[httpWebRequest](../../../../../docs/framework/configure-apps/file-schema/network/httpwebrequest-element-network-settings.md)|Настраивает параметры веб\-запроса.|  
|[ipv6](../../../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)|Включает поддержку IP\-протокола версии 6 \(IPv6\).|  
|[Элемент \<performanceCounter\> \(параметры сети\)](../../../../../docs/framework/configure-apps/file-schema/network/performancecounter-element-network-settings.md)|Включает счетчики производительности сети.|  
|[servicePointManager](../../../../../docs/framework/configure-apps/file-schema/network/servicepointmanager-element-network-settings.md)|Настраивает подключения к сетевым ресурсам.|  
|[сокет](../../../../../docs/framework/configure-apps/file-schema/network/socket-element-network-settings.md)|Указывает, используют ли операции сокета порты завершения.|  
|[Элемент \<WebProxyScript\> \(сетевые параметры\)](../../../../../docs/framework/configure-apps/file-schema/network/webproxyscript-element-network-settings.md)|Настройка характеристик скрипта, используемого для обнаружения веб\-прокси.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[system.net](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Содержит параметры, определяющие способ подключения платформы .NET Framework к сети.|  
  
## Заметки  
  
## Файлы конфигурации  
 Этот элемент может быть использован в файле конфигурации приложения или в файле конфигурации компьютера \(Machine.config\).  
  
## См. также  
 <xref:System.Net?displayProperty=fullName>   
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)