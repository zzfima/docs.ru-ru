---
title: "Элемент &lt;configuration&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<configuration> - элемент"
  - "configuration - элемент"
  - "теги контейнеров, <configuration> - элемент"
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# Элемент &lt;configuration&gt;
Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.  
  
 **\<configuration\>**  
  
## Синтаксис  
  
```  
  
      <configuration>   
   <!-- configuration settings -->   
</configuration>  
```  
  
## Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[Элемент \<assemblyBinding\>](../../../../docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)|Определяет политику привязки сборок на уровне конфигурации.|  
|[Схема параметров запуска](../../../../docs/framework/configure-apps/file-schema/startup/index.md)|Все элементы в схеме параметров запуска.|  
|[Схема параметров среды выполнения](../../../../docs/framework/configure-apps/file-schema/runtime/index.md)|Все элементы в схеме параметров среды выполнения.|  
|[Схема параметров удаленного взаимодействия](http://msdn.microsoft.com/ru-ru/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e)|Все элементы в схеме параметров удаленного взаимодействия.|  
|[Схема параметров сети](../../../../docs/framework/configure-apps/file-schema/network/index.md)|Все элементы в схеме параметров сети.|  
|[Схема параметров криптографии](../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)|Все элементы в схеме параметров криптографии.|  
|[Схема разделов конфигурации](../../../../docs/framework/configure-apps/file-schema/configuration-sections-schema.md)|Все элементы в схеме параметров раздела конфигурации.|  
|[Схема параметров трассировки и отладки](../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)|Все элементы в схеме параметров трассировки и отладки.|  
|[Схема параметров ASP.NET](http://msdn.microsoft.com/ru-ru/116608f3-c03d-4413-9fc7-978703e18b0f)|Все элементы в схеме конфигурации ASP.NET, которая включает элементы для настройки веб\-сайтов ASP.NET и приложений.  Используется в файлах Web.config.|  
|[Схема параметров веб\-служб XML](http://msdn.microsoft.com/ru-ru/f84d6d55-1add-4eb7-ae46-33df5833ea2e)|Все элементы в схеме параметров веб\-служб.|  
|[Схема веб\-параметров](../../../../docs/framework/configure-apps/file-schema/web/index.md)|Все элементы схемы веб\-параметров, в том числе элементы настройки способов работы ASP.NET с ведущими приложениями, такими как службы IIS.  Используются в файлах aspnet.config.|  
  
## Заметки  
 Каждый файл конфигурации должен содержать только один элемент **\<configuration\>**.  
  
## См. также  
 [Схема файла конфигурации](../../../../docs/framework/configure-apps/file-schema/index.md)