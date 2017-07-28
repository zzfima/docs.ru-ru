---
title: "Элемент &lt;etwEnable&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<etwEnable> - элемент"
  - "etwEnable - элемент"
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Элемент &lt;etwEnable&gt;
Указывает, следует ли включать отслеживание событий для Windows \(трассировка событий Windows\) для событий среды CLR.  
  
## Синтаксис  
  
```  
<etwEnable enabled="true|false"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|enabled|Обязательный атрибут.<br /><br /> Указывает, следует ли включать ETW.|  
  
## Атрибут enabled  
  
|Значение|Описание|  
|--------------|--------------|  
|true|Enable ETW.  Это значение по умолчанию для версий Windows, начиная с операционных системам Windows Vista и Windows Server 2008.|  
|false|Отключите ETW.  Это значение по умолчанию для более ранних версиях Windows.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`runtime`|Элемент, содержащий сведения о привязке сборок и сборке мусора.|  
  
## Заметки  
 Начиная с Windows Vista, ETW включена по умолчанию.  Используйте этот элемент для отключения трассировки событий Windows для приложения.  В более ранних версиях Windows этот элемент используется для включения ETW для приложения.  
  
> [!NOTE]
>  Можно глобально включить или отключить ETW на сервере, используя параметр реестра.  См. раздел [Controlling .NET Framework Logging](../../../../../docs/framework/performance/controlling-logging.md).  
  
## Пример  
 В следующем примере показано, как включить отслеживание ETW для приложения.  
  
```  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Controlling .NET Framework Logging](../../../../../docs/framework/performance/controlling-logging.md)