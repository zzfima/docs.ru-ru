---
title: "Элемент &lt;system.Net&gt; (параметры сети) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<system.Net> - элемент"
  - "system.Net - элемент"
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# Элемент &lt;system.Net&gt; (параметры сети)
Содержит параметры, определяющие способ подключения платформы .NET Framework к сети.  
  
## Синтаксис  
  
```  
  
      <system.net>   
</system.net>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Нет.  
  
### Дочерние элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[authenticationModules](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|Описывает модули, используемые для проверки подлинности интернет\-запросов.|  
|[connectionManagement](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|Задает максимальное число подключений к интернет\-узлу.|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Настраивает протокол HTTP прокси\-сервера.|  
|[mailSettings](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|Настраивает параметры отправки электронной почты по протоколу SMTP.|  
|[requestCaching](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Управляет механизмом кэширования сетевых запросов.|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Настраивает основные сетевые параметров для классов в <xref:System.Net> и связанных дочерних пространствах имен.|  
|[Элемент \<webRequestModules\> \(параметры сети\)](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|Описывает модули, используемые для запроса данных от интернет\-узлов.|  
  
### Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[configuration](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Содержит настройки всех пространств имен.|  
  
## Заметки  
 Элемент [\<system.net\>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) содержит параметры для классов в <xref:System.Net> и связанных дочерних пространствах имен.  Эти параметры используются для настройки модулей проверки подлинности, управления подключением, настройки параметров почты, настройки прокси\-сервера и модулей интернет\-запросов при получении данных от интернет\-узлов.  
  
## Пример  
 Следующий пример кода показывает типичную конфигурацию, используемую классом <xref:System.Net>.  
  
```  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type = "System.Net.DigestClient" />  
      <add type = "System.Net.NegotiateClient" />  
      <add type = "System.Net.KerberosClient" />  
      <add type = "System.Net.NtlmClient" />  
      <add type = "System.Net.BasicClient" />  
    </authenticationModules>  
    <connectionManagement>  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
    <defaultProxy>  
      <proxy  
        usesystemdefault = "true"  
        bypassonlocal = "true"  
      />  
    </defaultProxy>  
    <webRequestModules>  
      <add prefix = "http"  
        type = "System.Net.HttpRequestCreator"  
      />  
      <add prefix = "https"  
        type = "System.Net.HttpRequestCreator"  
      />  
      <add prefix = "file"  
        type = "System.Net.FileWebRequestCreator"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## См. также  
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)