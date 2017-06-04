---
title: "Элемент &lt;remove&gt; для connectionManagement (параметры сети) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/remove"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#remove"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<connectionManagement>, remove - элемент"
  - "<remove> - элемент, connectionManagement"
  - "connectionManagement, remove - элемент"
  - "remove - элемент, connectionManagement"
ms.assetid: 94b81775-5a22-4975-8c47-8620c40c3f35
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# Элемент &lt;remove&gt; для connectionManagement (параметры сети)
Удаление IP\-адреса или DNS\-имени из списка управления подключениями.  
  
## Синтаксис  
  
```  
  
      <remove   
   name = "server name or IP address"   
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|**Атрибут**|**Описание**|  
|-----------------|------------------|  
|`address`|IP\-адрес или DNS\-имя.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[connectionManagement](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|Задает максимальное число подключений к сетевому узлу.|  
  
## Заметки  
 Элемент `remove` удаляет запись списка управления подключением для указанного сервера.  
  
 Значение атрибута `address` должно быть допустимым IP\-адресом или именем узла.  
  
## Файлы конфигурации  
 Этот элемент может быть использован в файле конфигурации приложения или в файле конфигурации компьютера \(Machine.config\).  
  
## Пример  
 В следующем примере кода из списка управления подключением удаляются все записи для сервера www.adventure\-works.com, а затем настройка приложения выполняется таким образом, чтобы для сервера www.contoso.com использовались четыре подключения, а для иных серверов — два.  
  
```  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <remove address = "http://www.adventure-works.com"/>  
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