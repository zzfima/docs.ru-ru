---
title: "Элемент &lt;forcePerformanceCounterUniqueSharedMemoryReads&gt; | Microsoft Docs"
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
  - "<forcePerformanceCounterUniqueSharedMemoryReads> - элемент"
  - "forcePerformanceCounterUniqueSharedMemoryReads - элемент"
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Элемент &lt;forcePerformanceCounterUniqueSharedMemoryReads&gt;
Указывает, использует ли PerfCounter.dll параметр реестра CategoryOptions в приложениях .NET Framework 1.1 для определения необходимости загрузки данных счетчиков производительности из общей памяти конкретной категории или глобальной памяти.  
  
## Синтаксис  
  
```  
<forcePerformanceCounterUniqueSharedMemoryReads   
enabled="true|false"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, использует ли PerfCounter.dll параметр реестра CategoryOptions для определения необходимости загрузки данных счетчиков производительности из общей памяти конкретной категории или глобальной памяти.|  
  
## Атрибут enabled  
  
|Значение|Описание|  
|--------------|--------------|  
|`false`|PerfCounter.dll не использует параметр реестра CategoryOptions. Это значение по умолчанию.|  
|`true`|PerfCounter.dll использует параметр реестра CategoryOptions.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`runtime`|Элемент, содержащий сведения о привязке сборок и сборке мусора.|  
  
## Заметки  
 В версиях .NET Framework до [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] загружаемая версия PerfCounter.dll соответствовала среде выполнения, которая была загружена в процессе.  Если на компьютере установлены версии .NET Framework 1.1 и [!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)], приложения .NET Framework 1.1 будут загружать версию .NET Framework 1.1 файла PerfCounter.dll.  Начиная с [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] загружается последняя установленная версия PerfCounter.dll.  Это означает, что приложение .NET Framework 1.1 загрузит версию .NET Framework из [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], если на компьютере установлена [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].  
  
 Начиная с [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] при использовании счетчиков производительности PerfCounter.dll проверяет параметр реестра CategoryOptions для каждого поставщика, чтобы определить, должен ли он выполнять чтение из общей памяти конкретной категории или из глобальной общей памяти.  PerfCounter.dll .NET Framework 1.1 не может читать эту запись реестра, так как ему не известно об общей памяти конкретной категории; он всегда считывает из глобальной общей памяти.  
  
 Для обеспечения обратной совместимости [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll не выполняет проверку реестра CategoryOptions при работе в приложениях .NET Framework 1.1.  Он просто использует глобальную общую память, точно так же, как.NET Framework 1.1 PerfCounter.dll.  Тем не менее можно указать [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll, что необходимо проверять параметр реестра, включив элемент `<forcePerformanceCounterUniqueSharedMemoryReads>`.  
  
> [!NOTE]
>  Включение элемента `<forcePerformanceCounterUniqueSharedMemoryReads>` не гарантирует, что будет использоваться общая память конкретной категории.  Установка значения `true` для включения приводит только к тому, что PerfCounter.dll ссылается на параметр реестра CategoryOptions.  Значение по умолчанию для CategoryOptions — для использования общей памяти конкретной категории; тем не менее можно изменить CategoryOptions для указания, что следует использовать глобальную общую память.  
  
 Раздел реестра, содержащий параметр CategoryOptions имеет вид HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\\<categoryName\>\\Performance.  По умолчанию CategoryOptions равно 3, что указывает PerfCounter.dll на необходимость использования общей памяти, относящейся к определенной категории.  Если CategoryOptions равняется 0, PerfCounter.dll использует глобальную общую память.  Данные экземпляра будут повторно использоваться, только если имя создаваемого экземпляра идентично используемому экземпляру.  Все версии смогут записывать в категорию.  Если CategoryOptions равняется 1, используется глобальная общая память, но данные экземпляра могут быть повторно использованы, если имя категории имеет одинаковую длину с повторно используемой категорией.  
  
 Параметры 0 и 1 могут привести к утечке памяти и заполнению памяти счетчиков производительности.  
  
## Пример  
 В следующем примере показано, как указать, что PerfCounter.dll должен ссылаться на запись реестра CategoryOptions, чтобы определить, нужно ли использовать общую память конкретной категории.  
  
```  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)