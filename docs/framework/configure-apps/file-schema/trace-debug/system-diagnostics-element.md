---
title: "Элемент &lt;system.diagnostics&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<system.diagnostics> - элемент"
  - "system.diagnostics - элемент"
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
caps.latest.revision: 17
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# Элемент &lt;system.diagnostics&gt;
Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором устанавливается переключатель трассировки.  
  
## Синтаксис  
  
```  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Нет.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<assert\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|Указывает, следует ли отображать сообщение при вызове метода <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>, а также задает имя файла для записи сообщений.|  
|[\<performanceCounters\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|Размер глобальной памяти, совместно используемой счетчиками производительности.|  
|[\<sharedListeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|Содержит прослушиватели, на которые может ссылаться любой источник или элемент трассировки.  Прослушиватели, определенные как общие, могут добавляться к источникам или трассировкам по имени|  
|[\<источники\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|Задает источники трассировки, от которых исходят трассировочные сообщения.|  
|[\<переключатели\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|Содержит переключатели трассировки и уровни установки этих переключателей.|  
|[\<trace\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|Содержит прослушиватели, собирающие, хранящие и маршрутизирующие сообщения трассировки.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
  
## Пример  
 В следующем примере показано внедрение переключателя трассировки и прослушивателя трассировки в элемент **\<system.diagnostics\>**.  Переключатель трассировки `General` установлен на уровне [TraceLevel.Error](frlrfSystemDiagnosticsTraceLevelClassTopic).  Пролушиватель трассировки `myListener` создает файл `MyListener.log` и записывает в него выходные сведения.  
  
> [!NOTE]
>  В .NET Framework версии 2.0 для указания значения переключателя можно использовать текст.  Например, можно указать значение `true` для <xref:System.Diagnostics.BooleanSwitch> или использовать текст, представляющий значение перечисления, такое как `Error`, для <xref:System.Diagnostics.TraceSwitch>.  Строка `<add name="myTraceSwitch" value="Error" />` эквивалентна `<add name="myTraceSwitch" value="1" />`.  
  
```  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
      </switches>  
      <trace autoflush="true" indentsize="2">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="MyListener.log" traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## См. также  
 <xref:System.Diagnostics.Trace>   
 <xref:System.Diagnostics.Debug>   
 [Схема параметров трассировки и отладки](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)