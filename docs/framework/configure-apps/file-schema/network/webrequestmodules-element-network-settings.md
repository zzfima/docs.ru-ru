---
title: "Элемент &lt;webRequestModules&gt; (параметры сети) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<webRequestModules> - элемент"
  - "webRequestModules - элемент"
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# Элемент &lt;webRequestModules&gt; (параметры сети)
Задает модули, используемые для запроса данных от сетевых узлов.  
  
## Синтаксис  
  
```  
  
      <webRequestModules>   
</webRequestModules>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Нет.  
  
### Дочерние элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[добавление;](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-webrequestmodules-network-settings.md)|Добавляет в приложение пользовательский модуль веб\-запросов.|  
|[clear](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-webrequestmodules-network-settings.md)|Удаляет из приложения все зарегистрированные модули веб\-запросов.|  
|[remove](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-webrequestmodules-network-settings.md)|Удаляет из приложения пользовательский модуль веб\-запросов.|  
  
### Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[system.net](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Содержит параметры, определяющие способ подключения платформы .NET Framework к сети.|  
  
## Заметки  
 Элемент `webRequestModules` регистрирует потомки класса <xref:System.Net.WebRequest>, чтобы обработать информацию о запросах к сетевым узлам.  Модули веб\-запросов должны реализовывать интерфейс <xref:System.Net.IWebRequestCreate>.  
  
 В состав платформы .NET Framework входят модули веб\-запросов для URI, начинающихся с http:\/\/, https:\/\/ и file:\/\/.  Модули по умолчанию можно переопределить исключительно путем регистрации в файле конфигурации пользовательского модуля.  
  
## Файлы конфигурации  
 Этот элемент может быть использован в файле конфигурации приложения или в файле конфигурации компьютера \(Machine.config\).  
  
## Пример  
 Код в следующем примере регистрирует модуль HTTP по умолчанию.  Необходимо заменить значения для параметров Version и PublicKeyToken правильными значениями для указанного модуля.  
  
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
 <xref:System.Net.IWebRequestCreate>   
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)