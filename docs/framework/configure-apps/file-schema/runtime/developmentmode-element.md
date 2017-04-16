---
title: "Элемент &lt;developmentMode&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/developmentMode"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#developmentMode"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<developmentMode> - элемент"
  - "теги контейнеров, <developmentMode> - элемент"
  - "developmentMode - элемент"
ms.assetid: 60e79a8c-415a-497d-be29-b9d0fd9bdee3
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Элемент &lt;developmentMode&gt;
Указывает, будет ли среда выполнять поиск сборок в папках, заданных в переменной среды DEVPATH.  
  
## Синтаксис  
  
```  
<developmentMode developerInstallation="true | false"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|**developerInstallation**|Указывает, будет ли среда выполнять поиск сборок в папках, заданных в переменной среды DEVPATH.|  
  
## Атрибут developerInstallation  
  
|Значение|Описание|  
|--------------|--------------|  
|**true**|Поиск сборок в папках, указанных в переменной среды DEVPATH, выполняется.|  
|**false**|Поиск сборок в папках, указанных в переменной среды DEVPATH, не выполняется.  Это значение используется по умолчанию.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`runtime`|Элемент, содержащий сведения о привязке сборок и сборке мусора.|  
  
## Заметки  
 Этот параметр применяется только во время разработки.  Среда выполнения не проверяет версии указанных в DEVPATH сборок со строгими именами.  Она просто использует первую найденную сборку.  
  
## Пример  
 В следующем примере показан способ выполнения средой выполнения поиска сборок в каталогах, указанных в переменной среды DEVPATH.  
  
```  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Практическое руководство. Поиск сборок с помощью DEVPATH](../../../../../docs/framework/configure-apps/how-to-locate-assemblies-by-using-devpath.md)