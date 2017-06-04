---
title: "Элемент &lt;remove&gt; для bypasslist (параметры сети) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/remove"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#remove"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<bypasslist>, remove - элемент"
  - "bypasslist, remove - элемент"
  - "remove - элемент, bypasslist"
  - "remove - элемент, bypasslist"
ms.assetid: 61dcfb4a-e3d9-4abf-a2cd-7d685fe2f64b
caps.latest.revision: 16
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 16
---
# Элемент &lt;remove&gt; для bypasslist (параметры сети)
Удаление IP\-адреса или DNS\-имени из списка обхода прокси\-серверов.  
  
## Синтаксис  
  
```  
  
      <remove   
   name = "regular expression"   
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|**Атрибут**|**Описание**|  
|-----------------|------------------|  
|`name`|Регулярное выражение, описывающее IP\-адрес или DNS\-имя.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[bypasslist](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|Набор регулярных выражений, описывающих адреса, пропускаемые прокси\-сервером.|  
  
## Заметки  
 Элемент `remove` удаляет регулярное выражение, описывающее IP\-адреса или DNS\-имена сервера, из списка адресов, для которых не используется прокси\-сервер.  Эти адреса были заданы ранее в файле конфигурации или на более высоком уровне в иерархии конфигурации.  
  
 Значение атрибута `name` должно быть регулярным выражением, описывающим набор IP\-адресов или имен узлов.  
  
 Дополнительные сведения о регулярных выражениях см. в разделе [Регулярные выражения в .NET Framework](../../../../../docs/standard/base-types/regular-expressions.md).  
  
## Файлы конфигурации  
 Этот элемент может быть использован в файле конфигурации приложения или в файле конфигурации компьютера \(Machine.config\).  
  
## Пример  
 В следующем примере кода для домена adventure\-works.com удаляются все предыдущие определения, а затем в список пропускаемых адресов добавляется домен contoso.com.  
  
```  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <remove name = "[a-z]+\.adventure-works\.com$" />  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## См. также  
 <xref:System.Net.WebProxy?displayProperty=fullName>   
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)