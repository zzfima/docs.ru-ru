---
title: "Элемент &lt;add&gt; для bypasslist (параметры сети) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/add"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#add"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<add> - элемент, bypasslist"
  - "<bypasslist>, add - элемент"
  - "add - элемент, bypasslist"
  - "bypasslist, add - элемент"
ms.assetid: a0b86e28-86b4-4497-abe8-d5fd614c7926
caps.latest.revision: 17
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 17
---
# Элемент &lt;add&gt; для bypasslist (параметры сети)
Добавление IP\-адреса или DNS\-имени в список адресов, пропускаемых прокси\-сервером.  
  
## Синтаксис  
  
```  
  
      <add   
   address = "regular expression"   
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|**Атрибут**|**Описание**|  
|-----------------|------------------|  
|**address**|Регулярное выражение, описывающее IP\-адрес или DNS\-имя.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[bypasslist](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|Набор регулярных выражений, описывающих адреса, пропускаемые прокси\-сервером.|  
  
## Заметки  
 Элемент `add` добавляет в список адресов, для которых не используется прокси\-сервер, регулярные выражения, описывающие IP\-адреса или имена DNS\-серверов.  
  
 Значение атрибута `address` должно быть регулярным выражением, описывающим набор IP\-адресов или имен узлов.  
  
 Соблюдайте осторожность при вводе регулярного выражения для этого элемента.  Регулярное выражение "\[a\-z\]\+\\.contoso\\.com" соответствует любому узлу в домене contoso.com, но при этом оно соответствует и любому узлу в домене contoso.com.cpandl.com.  Чтобы задать однозначное соответствие только одному узлу в домене contoso.com, используйте символ привязки \("$"\): "\[a\-z\]\+\\.contoso\\.com$".  
  
 Дополнительные сведения о регулярных выражениях см. в разделе [Регулярные выражения в .NET Framework](../../../../../docs/standard/base-types/regular-expressions.md).  
  
## Файлы конфигурации  
 Этот элемент может быть использован в файле конфигурации приложения или в файле конфигурации компьютера \(Machine.config\).  
  
## Пример  
 В следующем примере кода в список пропускаемых адресов добавляются два адреса.  Первая запись отменяет использование прокси\-сервера для всех серверов домена contoso.com, а вторая — для всех серверов, IP\-адреса которых начинаются с 192.168.  
  
```  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
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