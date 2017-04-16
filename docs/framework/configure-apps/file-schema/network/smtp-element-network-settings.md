---
title: "Элемент &lt;smtp&gt; (параметры сети) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<smtp> - элемент"
  - "smtp - элемент"
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# Элемент &lt;smtp&gt; (параметры сети)
Настраивает формат, способ доставки и адрес отправителя для отправки сообщений электронной почты.  
  
## Синтаксис  
  
```  
  
      <smtp  
  deliveryFormat="format"   
  deliveryMethod="method"   
  from="from address"   
  <specifiedPickupDirectory> … </ specifiedPickupDirectory >  
  <network> … </network>  
/smtp>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`deliveryFormat`|Определяет формат доставки для исходящих сообщений по электронной почте.  Допустимые значения: SevenBit и International.|  
|`deliveryMethod`|Определяет способ доставки сообщений электронной почты.  Допустимые значения: network, pickupDirectoryFromIis, specifiedPickupDirectory.|  
|`from`|Задает адрес электронной почты отправителя для исходящих сообщений.|  
  
### Дочерние элементы  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`specifiedPickupDirectory`|Настраивает локальный каталог для SMTP\-сервера.|  
|`network`|Настраивает сетевые параметры для внешнего SMTP\-сервера.|  
  
### Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[Элемент \<mailSettings\> \(параметры сети\)](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|Настраивает параметры отправки сообщений.|  
  
## Пример  
 В следующем примере кода задаются соответствующие параметры протокола SMTP для отправки сообщений электронной почты с использованием сетевых учетных данных по умолчанию.  
  
```  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network" deliveryFormat="SevenBit"  from="ben@contoso.com">  
        <network  
          host="localhost"  
          port="25"  
          defaultCredentials="true"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## См. также  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=fullName>   
 <xref:System.Net.Mail.SmtpClient?displayProperty=fullName>   
 <xref:System.Net.Mail.SmtpDeliveryFormat>   
 <xref:System.Net.Mail.SmtpDeliveryMethod>   
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)