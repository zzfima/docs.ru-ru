---
title: "Элемент &lt;specifiedPickupDirectory&gt; (параметры сети) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#specifiedPickupDirectory"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/specifiedPickupDirectory"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<specifiedPickupDirectory> - элемент"
  - "specifiedPickupDirectory - элемент"
ms.assetid: 0121f49d-bff2-4bc6-af06-f1628dcd61f1
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# Элемент &lt;specifiedPickupDirectory&gt; (параметры сети)
Настраивает локальный каталог для SMTP\-сервера.  
  
## Синтаксис  
  
```  
  
      <specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`pickupDirectoryLocation`|Каталог, где приложения сохраняют электронную почту для последующей обработки SMTP\-сервером.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[Элемент \<smtp\> \(параметры сети\)](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|Настраивает параметры отправки электронной почты по протоколу SMTP.|  
  
## Заметки  
 Атрибут `specifiedPickupDirectory` задает каталог, где приложения сохраняют почтовые сообщения для последующей обработки SMTP\-сервером.  
  
## Пример  
 Следующий пример кода определяет c:\\maildrop как каталог раскладки почты.  
  
```  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="specifiedPickupDirectory">  
        <specifiedPickupDirectory  
          pickupDirectoryLocation="c:\maildrop"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## См. также  
 <xref:System.Net.Mail.SmtpClient?displayProperty=fullName>   
 <xref:System.Net.Configuration.SmtpSection?displayProperty=fullName>   
 <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=fullName>   
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)