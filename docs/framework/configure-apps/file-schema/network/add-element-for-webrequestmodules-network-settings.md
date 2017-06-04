---
title: "Элемент &lt;add&gt; для webRequestModules (параметры сети) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/add"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#add"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<add> - элемент, webRequestModules"
  - "<webRequestModules>, add - элемент"
  - "add - элемент, webRequestModules"
  - "webRequestModules, add - элемент"
ms.assetid: 47ec4adc-f39f-4bcd-8680-1ec21fd26890
caps.latest.revision: 16
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 16
---
# Элемент &lt;add&gt; для webRequestModules (параметры сети)
Добавляет в приложение пользовательский модуль веб\-запросов.  
  
## Синтаксис  
  
```  
  
      <add   
  prefix = "URI prefix"   
  type = "module name, Version, Culture, PublicKeyToken"   
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|**Атрибут**|**Описание**|  
|-----------------|------------------|  
|`prefix`|Префикс URI для запросов, обрабатываемых данным модулем веб\-запросов.|  
|`type`|Имя сборки и класса модуля, реализующего данный модуль веб\-запросов.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[webRequestModules](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|Задает модули, используемые для запроса данных от сетевых узлов.|  
  
## Заметки  
 Атрибут `prefix` определяет префикс URI, используемый заданным модулем веб\-запросов.  Такие модули веб\-запросов обычно регистрируются для обработки конкретных протоколов, например HTTP или FTP, но они также могут быть зарегистрированы и для обработки запросов к заданному серверу или пути на сервере.  
  
 Модуль веб\-запроса создается, когда URI, соответствующий префиксу, передается методу <xref:System.Net.WebRequest.Create%2A?displayProperty=fullName>.  
  
 Значением атрибута `prefix` должны быть первые символы действительного URI, например "http" или "http:\/\/www.contoso.com".  
  
 Значением атрибута `type` должно быть допустимое имя библиотеки DLL или соответствующее имя класса, отделенное запятой.  
  
## Файлы конфигурации  
 Этот элемент может быть использован в файле конфигурации приложения или в файле конфигурации компьютера \(Machine.config\).  
  
## Пример  
 В следующем примере кода выполняется регистрация пользовательского модуля веб\-запросов для HTTP.  Необходимо заменить значения для параметров Version и PublicKeyToken правильными значениями для указанного модуля.  
  
```  
<configuration>  
  <system.net>  
    <webRequestModules>  
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