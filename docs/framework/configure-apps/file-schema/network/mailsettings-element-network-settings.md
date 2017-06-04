---
title: "Элемент &lt;mailSettings&gt; (параметры сети) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<mailSettings> - элемент"
  - "mailSettings - элемент"
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
caps.latest.revision: 20
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 20
---
# Элемент &lt;mailSettings&gt; (параметры сети)
Настраивает параметры отправки сообщений.  
  
## Синтаксис  
  
```  
  
      <mailSettings  
  <smtp> … </smtp>  
/mailsettings>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Нет.  
  
### Дочерние элементы  
  
|Атрибут|Описание|  
|-------------|--------------|  
|[Элемент \<smtp\> \(параметры сети\)](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|Настраивает параметры отправки электронной почты по протоколу SMTP.|  
  
### Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[Элемент \<system.Net\> \(параметры сети\)](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Содержит параметры, определяющие способ подключения платформы .NET Framework к сети.|  
  
## Пример  
 В следующем примере кода задаются соответствующие параметры протокола SMTP для отправки сообщений электронной почты с использованием сетевых учетных данных по умолчанию.  
  
```  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network">  
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
 <xref:System.Net.Mail.SmtpClient>   
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)