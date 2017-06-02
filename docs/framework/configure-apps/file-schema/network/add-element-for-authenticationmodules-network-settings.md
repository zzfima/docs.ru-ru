---
title: "Элемент &lt;add&gt; для authenticationModules (параметры сети) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#add"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/add"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<add> - элемент, authenticationModules"
  - "<authenticationModules>, add - элемент"
  - "add - элемент, authenticationModules"
  - "authenticationModules, add - элемент"
ms.assetid: 333c5fb0-a2ab-4db8-8531-a7fe37bb9b5b
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# Элемент &lt;add&gt; для authenticationModules (параметры сети)
Добавляет в приложение модуль проверки подлинности.  
  
## Синтаксис  
  
```  
  
      <add   
   type = "client type", System, Version="version number", Culture="culture", PublicKeyToken="token"   
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|**Атрибут**|**Описание**|  
|-----------------|------------------|  
|`type`|Имя класса и разновидности модуля, в которых реализована проверка подлинности.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[authenticationModules](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|Модули, используемые для проверки подлинности сетевых запросов.|  
  
## Заметки  
 Элемент `add` добавляет модуль проверки подлинности в конец списка зарегистрированных модулей проверки подлинности.  Эти модули вызываются в том порядке, в котором они были добавлены в список.  
  
 Значением атрибута `type` должно быть допустимое имя библиотеки DLL или соответствующее имя класса, отделенное запятой.  
  
## Файлы конфигурации  
 Этот элемент может быть использован в файле конфигурации приложения или в файле конфигурации компьютера \(Machine.config\).  
  
## Пример  
 В следующем примере кода показано включение используемых по умолчанию модулей проверки подлинности.  Необходимо заменить значения для параметров Version и PublicKeyToken правильными значениями для указанного модуля.  
  
```  
<configuration>  
  <system.net>  
        <authenticationModules>  
            <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NegotiateClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.KerberosClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NtlmClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.BasicClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
        </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## См. также  
 <xref:System.Net.IAuthenticationModule>   
 <xref:System.Net.AuthenticationManager>   
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)