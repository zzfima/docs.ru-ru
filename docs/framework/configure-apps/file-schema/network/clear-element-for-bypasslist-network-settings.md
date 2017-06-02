---
title: "Элемент &lt;clear&gt; для bypasslist (параметры сети) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/clear"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#clear"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<bypasslist>, clear - элемент"
  - "<clear> - элемент, bypasslist"
  - "bypasslist, clear - элемент"
  - "clear - элемент, bypasslist"
ms.assetid: 301584ca-a914-4100-b180-3b288d3b099e
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# Элемент &lt;clear&gt; для bypasslist (параметры сети)
Удаляет список пропускаемых адресов.  
  
## Синтаксис  
  
```  
  
<clear/>  
  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Нет.  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[bypasslist](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|Набор регулярных выражений, описывающих адреса, пропускаемые прокси\-сервером.|  
  
## Заметки  
 Элемент `clear` удаляет все записи из списка пропускаемых адресов.  
  
## Файлы конфигурации  
 Этот элемент может быть использован в файле конфигурации приложения или в файле конфигурации компьютера \(Machine.config\).  
  
## Пример  
 В следующем примере кода сначала выполняется очистка списка пропускаемых адресов, а затем – добавление в него двух адресов.  Первая запись отменяет использование прокси\-сервера для всех серверов домена contoso.com, а вторая — для всех серверов, IP\-адреса которых начинаются с 192.168.  
  
```  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
         <clear/>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>   
```  
  
## См. также  
 <xref:System.Net.WebProxy?displayProperty=fullName>   
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)