---
title: "Элемент &lt;ipv6&gt; (параметры сети) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/ipv6"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#ipv6"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<ipv6> - элемент"
  - "ipv6 - элемент"
ms.assetid: 10b79aef-327b-4718-a892-e11f55e4d169
caps.latest.revision: 19
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 19
---
# Элемент &lt;ipv6&gt; (параметры сети)
Включает IPv6\-отклики от устаревших членов класса <xref:System.Net.Dns>.  
  
## Синтаксис  
  
```  
  
      <ipv6  
  enabled="true|false"  
/ipv6>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|**Атрибут**|**Описание**|  
|-----------------|------------------|  
|`enabled`|Указывает, возвращают ли члены класса <xref:System.Net.Dns> IP\-адреса IPv6.  Значение по умолчанию — `false`.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Настраивает основные сетевые параметры для пространства имен <xref:System.Net>.|  
  
## Заметки  
 Этот параметр включает поддержку IPv6 для устаревших членов класса <xref:System.Net.Dns>: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A> и <xref:System.Net.Dns.Resolve%2A>.  Для других членов пространства имен <xref:System.Net?displayProperty=fullName> IPv6\-адреса могут быть возвращены, если IPv6 включен в операционной системе.  
  
## Файлы конфигурации  
 Этот элемент может быть использован в файле конфигурации приложения или в файле конфигурации компьютера \(Machine.config\).  
  
## Пример  
 В следующем примере кода демонстрируется способ включения поддержки IPv6 для класса <xref:System.Net.Dns>.  
  
```  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## См. также  
 <xref:System.Net?displayProperty=fullName>   
 <xref:System.Net.Dns?displayProperty=fullName>   
 <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=fullName>   
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)