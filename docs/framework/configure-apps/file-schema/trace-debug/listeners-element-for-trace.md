---
title: "Элемент &lt;listeners&gt; для &lt;trace&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<listeners> - элемент"
  - "listeners - элемент"
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
caps.latest.revision: 17
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 17
---
# Элемент &lt;listeners&gt; для &lt;trace&gt;
Задает прослушиватель, собирающий, хранящий и маршрутизирующий сообщения.  Прослушиватели направляют выходные данные трассировки соответствующему целевому объекту.  
  
## Синтаксис  
  
```  
<listeners>   
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Нет.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|Добавляет прослушиватель в коллекцию `Listeners`.|  
|[\<clear\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-trace.md)|Очищает коллекцию `Listeners` для трассировки.|  
|[\<remove\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)|Удаляет прослушиватель из коллекции `Listeners`.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`system.diagnostics`|Определяет корневой элемент для раздела конфигурации ASP.NET.|  
|`trace`|Содержит прослушиватели, собирающие, хранящие и маршрутизирующие сообщения трассировки.|  
  
## Заметки  
 Классы <xref:System.Diagnostics.Debug> и <xref:System.Diagnostics.Trace> совместно используют коллекцию **Listeners**.  Если в одном из этих классов в коллекцию добавляется объект прослушивателя, то этот прослушиватель используется и в другом классе.  Классы прослушивателей, поставляемые с .NET Framework, являются производными от класса <xref:System.Diagnostics.TraceListener>.  
  
## Файл конфигурации  
 Этот элемент может быть использован в файле конфигурации компьютера \(Machine.config\) и в файле конфигурации приложения.  
  
## Пример  
 В следующем примере показано, как использовать элемент **\<listeners\>** для добавления прослушивателей `MyListener` и `MyEventListener` коллекцию **Listeners**.  `MyListener` создает файл `MyListener.log` и записывает в него результат.  `MyEventListener` создает запись в журнале событий.  
  
```  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="true" indentsize="0">  
      <listeners>  
        <add name="myListener"   
          type="System.Diagnostics.TextWriterTraceListener,   
            system, version=1.0.3300.0, Culture=neutral,   
            PublicKeyToken=b77a5c561934e089"   
          initializeData="c:\myListener.log" />  
        <add name="MyEventListener"  
          type="System.Diagnostics.EventLogTraceListener,   
            system, version=1.0.3300.0, Culture=neutral,   
            PublicKeyToken=b77a5c561934e089"  
          initializeData="MyConfigEventLog"/>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## См. также  
 <xref:System.Diagnostics.TraceListener>   
 [Схема параметров трассировки и отладки](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)