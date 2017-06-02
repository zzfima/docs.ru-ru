---
title: "Элемент &lt;bypasslist&gt; (параметры сети) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<bypasslist> - элемент"
  - "bypasslist - элемент"
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
caps.latest.revision: 17
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 17
---
# Элемент &lt;bypasslist&gt; (параметры сети)
Набор регулярных выражений, описывающих адреса, пропускаемые прокси\-сервером.  
  
## Синтаксис  
  
```  
  
      <bypasslist>   
</bypasslist>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Нет.  
  
### Дочерние элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[добавление;](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-bypasslist-network-settings.md)|Добавление IP\-адреса или DNS\-имени в список адресов, пропускаемых прокси\-сервером.|  
|[clear](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-bypasslist-network-settings.md)|Удаляет список пропускаемых адресов.|  
|[remove](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-bypasslist-network-settings.md)|Удаление IP\-адреса или DNS\-имени из списка обхода прокси\-серверов.|  
  
### Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Настраивает протокол HTTP прокси\-сервера.|  
  
## Заметки  
 Список пропускаемых адресов содержит описывающие URI регулярные выражения, доступ к которым экземплярами <xref:System.Net.WebRequest> осуществляется напрямую, а не через прокси\-сервер.  
  
 Соблюдайте осторожность при вводе регулярного выражения для этого элемента.  Регулярное выражение "\[a\-z\]\+\\.contoso\\.com" соответствует любому узлу в домене contoso.com, но при этом оно соответствует и любому узлу в домене contoso.com.cpandl.com.  Чтобы задать однозначное соответствие только одному узлу в домене contoso.com, используйте символ привязки \("$"\): "\[a\-z\]\+\\.contoso\\.com$".  
  
 Дополнительные сведения о регулярных выражениях см. в разделе [Регулярные выражения в .NET Framework](../../../../../docs/standard/base-types/regular-expressions.md).  
  
## Файлы конфигурации  
 Этот элемент может быть использован в файле конфигурации приложения или в файле конфигурации компьютера \(Machine.config\).  
  
## Пример  
 В следующем примере кода в список пропускаемых адресов добавляются два адреса.  Первая запись задает для прокси пропуск всех серверов, содержащихся в домене contoso.com, а вторая — всех серверов, IP\-адреса которых начинаются с 192.168.  
  
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