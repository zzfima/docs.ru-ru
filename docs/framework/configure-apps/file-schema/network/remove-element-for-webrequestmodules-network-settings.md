---
title: "Элемент &lt;remove&gt; для webRequestModules (параметры сети) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/remove"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#remove"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<remove> - элемент, webRequestModules"
  - "<webRequestModules>, remove - элемент"
  - "remove - элемент, webRequestModules"
  - "webRequestModules, remove - элемент"
ms.assetid: dd84d2fe-2f4f-457a-9d3c-441d0d21cc10
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# Элемент &lt;remove&gt; для webRequestModules (параметры сети)
Удаляет из приложения пользовательский модуль веб\-запросов.  
  
## Синтаксис  
  
```  
  
      <remove   
  name = "URI prefix"   
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|**Атрибут**|**Описание**|  
|-----------------|------------------|  
|`name`|Префикс URI для запросов, обрабатываемых данным модулем веб\-запросов.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[webRequestModules](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|Задает модули, используемые для запроса данных от сетевых узлов.|  
  
## Заметки  
 Элемент `remove` удаляет зарегистрированный модуль веб\-запросов для заданного префикса URI.  
  
 Значением атрибута `prefix` должны быть первые символы действительного URI, например "http" или "http:\/\/www.contoso.com".  
  
## Файлы конфигурации  
 Этот элемент может быть использован в файле конфигурации приложения или в файле конфигурации компьютера \(Machine.config\).  
  
## Пример  
 В следующем примере кода удаляется имеющийся модуль веб\-запросов для протокола HTTP и затем регистрируется новый пользовательский модуль веб\-запросов для HTTP\-запросов к веб\-узлу www.contoso.com.  
  
```  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <remove prefix = "http">  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## См. также  
 <xref:System.Net.WebRequest>   
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)