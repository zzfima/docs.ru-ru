---
title: "Элемент &lt;sharedListeners&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#sharedListeners"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<sharedListeners> - элемент"
  - "прослушиватели"
  - "общие прослушиватели"
  - "sharedListeners - элемент"
  - "прослушиватели трассировки, <sharedListeners> - элемент"
ms.assetid: de200534-19dd-4156-86cf-c50521802c4c
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Элемент &lt;sharedListeners&gt;
Содержит прослушиватели, на которые может ссылаться любой источник или элемент трассировки.  По умолчанию эти прослушиватели не принимают никакой трассировки, и извлечь эти прослушиватели во время выполнения невозможно.  Прослушиватели, определенные как общие, могут добавляться к источникам или трассировкам по имени  
  
## Синтаксис  
  
```  
<sharedListeners>   
  <add>...</add>  
</sharedListeners>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Нет.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|Добавляет прослушиватель в коллекцию `sharedListeners`.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`Configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`system.diagnostics`|Определяет корневой элемент для раздела конфигурации ASP.NET.|  
  
## Заметки  
 Добавление прослушивателя в коллекцию общих прослушивателей не делает его активным.  Его по\-прежнему необходимо добавить к источнику трассировки или трассировке, добавив его в коллекцию `Listeners` соответствующего элемента трассировки.  Классы слушателей платформы .NET Framework являются производными от класса <xref:System.Diagnostics.TraceListener>.  
  
 Этот элемент может быть использован в файле конфигурации компьютера \(Machine.config\) и в файле конфигурации приложения.  
  
## Пример  
 В следующем примере показано, как использовать `<sharedListeners>` для добавления прослушивателя `console` в коллекцию `Listeners` для классов <xref:System.Diagnostics.TraceSource> и <xref:System.Diagnostics.Trace>.  Прослушиватель трассировки консоли выводит трассировочную информацию на консоль путем вызова методов <xref:System.Diagnostics.TraceSource> или <xref:System.Diagnostics.Trace>.  
  
```  
<configuration>  
  <system.diagnostics>  
    <sharedListeners>  
      <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"  
          initializeData="Warning" />  
      </add>  
    </sharedListeners>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"  >  
        <listeners>  
          <add name="console" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Verbose"/>  
    </switches>  
    <trace>  
      <listeners>  
        <add name="console" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration></system.diagnostics>   
```  
  
## См. также  
 <xref:System.Diagnostics.TraceListener>   
 [Схема параметров трассировки и отладки](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)   
 [Trace Listeners](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)