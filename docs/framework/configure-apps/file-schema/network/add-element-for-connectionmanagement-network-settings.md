---
title: "Элемент &lt;add&gt; для connectionManagement (параметры сети) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/add"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<add> - элемент, connectionManagement"
  - "<connectionManagement>, add - элемент"
  - "add - элемент, connectionManagement"
  - "connectionManagement, add - элемент"
ms.assetid: 856bf57d-1c63-46c7-a178-03d97b0a4149
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# Элемент &lt;add&gt; для connectionManagement (параметры сети)
Добавляет IP\-адрес или DNS\-имя в список управления подключениями.  
  
## Синтаксис  
  
```  
  
        <add   
   address = "address expression"   
   maxconnection = integer   
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|**Атрибут**|**Описание**|  
|-----------------|------------------|  
|`address`|Строка, описывающая IP\-адрес или DNS\-имя.|  
|`maxconnection`|Максимальное число разрешенных подключений к серверу.  Если значение не предоставлено, используется значение по умолчанию 2.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[connectionManagement](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|Задает максимальное число подключений к сетевому узлу.|  
  
## Заметки  
 В качестве значения атрибута `address` должна быть задана либо звездочка, указывающая все подключения, либо строка в форме `<schema>://<idn_hostname>[:<port>]`.  
  
 Если URI, переданный в какие\-либо API HTTP, содержит символы Юникода, то имя будет преобразовано внутренним образом с помощью свойства <xref:System.Uri.DnsSafeHost%2A>, которое может возвращать строку Punycode \(поведение, зависящее от текущей конфигурации IDN\).  
  
## Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера \(Machine.config\).  
  
## Пример  
 В следующем примере кода приложение настраивается для использования четырех подключений к серверу www.contoso.com и двух подключений ко всем другим серверам.  
  
```  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## См. также  
 <xref:System.Net.ServicePoint>   
 <xref:System.Net.ServicePointManager>   
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)