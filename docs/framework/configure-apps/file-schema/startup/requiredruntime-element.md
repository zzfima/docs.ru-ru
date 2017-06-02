---
title: "Элемент &lt;requiredRuntime&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<requiredRuntime> - элемент"
  - "теги контейнеров, <requiredRuntime> - элемент"
  - "requiredRuntime - элемент"
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Элемент &lt;requiredRuntime&gt;
Указывает, что приложение поддерживает только версию 1.0 среды CLR.  
  
## Синтаксис  
  
```  
  
   <requiredRuntime    
version="runtime version"  
safemode="true|false"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`version`|Необязательный атрибут.<br /><br /> Строковое значение, указывающее поддерживаемую этим приложением версию платформы .NET Framework.  Строковый параметр должен точно соответствовать имени вложенной папки корневой папки установки платформы .NET Framework.  Содержимое строки не анализируется.|  
|`safemode`|Необязательный атрибут.<br /><br /> Указание того, должен ли код запуска среды выполнения производить поиск в системном реестре для определения версии среды выполнения.|  
  
## Атрибут safemode  
  
|Значение|Описание|  
|--------------|--------------|  
|`false`|Код запуска среды выполнения проверяет реестр.  Это значение по умолчанию.|  
|`true`|Код запуска среды выполнения не проверяет реестр.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`startup`|Содержит элемент `<requiredRuntime>`.|  
  
## Заметки  
 Приложения, собранные для поддержки только версии 1.0 среды выполнения, должны использовать элемент `<requiredRuntime>`.  Приложения, построенные с помощью версии 1.1 или более поздней версии среды выполнения, должны использовать элемент `<supportedRuntime>`.  
  
> [!NOTE]
>  При использовании функции [CorBindToRuntimeByCfg](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) для указания файла конфигурации необходимо использовать элемент `<requiredRuntime>` для всех версий среды выполнения.  Элемент `<supportedRuntime>` игнорируется при использовании [CorBindToRuntimeByCfg](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).  
  
 Строка атрибута `version` должна совпадать с именем папки установки заданной версии платформы .NET Framework.  Эта строка не интерпретируется.  Если код запуска среды выполнения не находит соответствующей папки, среда выполнения не загружается; при этом код запуска выводит сообщение об ошибке и прекращает работу.  
  
> [!NOTE]
>  Код запуска для приложения, выполняемого в Microsoft Internet Explorer, не обрабатывает элемент `<requiredRuntime>`.  
  
## Пример  
 В следующем примере показан способ указания в файле конфигурации версии среды выполнения.  
  
```  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
```  
  
## См. также  
 [Схема параметров запуска](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<PaveOver\> Specifying Which Runtime Version to Use](http://msdn.microsoft.com/ru-ru/c376208d-980d-42b4-865b-fbe0d9cc97c2)