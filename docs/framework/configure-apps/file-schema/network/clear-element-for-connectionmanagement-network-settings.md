---
title: "Элемент &lt;clear&gt; для connectionManagement (параметры сети) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/clear"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#clear"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<clear> - элемент, connectionManagement"
  - "<connectionManagement>, clear - элемент"
  - "clear - элемент, connectionManagement"
  - "connectionManagement, clear - элемент"
ms.assetid: fb259282-84c4-4dc4-a226-78d904a6edc3
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# Элемент &lt;clear&gt; для connectionManagement (параметры сети)
Удаляет список управления подключениями.  
  
## Синтаксис  
  
```  
  
<clear/>  
  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Нет.  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[connectionManagement](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|Задает максимальное число подключений к сетевому узлу.|  
  
## Заметки  
 Элемент `clear` удаляет все записи из списка управления подключениями.  
  
## Файлы конфигурации  
 Этот элемент может быть использован в файле конфигурации приложения или в файле конфигурации компьютера \(Machine.config\).  
  
## Пример  
 В следующем примере кода список управления подключениями очищается, после чего к нему добавляются новые записи управления подключениями, соответствующие серверу www.contoso.com и всем другим сетевым узлам.  
  
```  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <clear/>  
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