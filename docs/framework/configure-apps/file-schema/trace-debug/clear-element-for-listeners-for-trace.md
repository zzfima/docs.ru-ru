---
title: "Элемент &lt;clear&gt; для &lt;listeners&gt; для &lt;trace&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<clear> - элемент для <listeners> для <trace>"
  - "элемент clear для элемента <listeners> для элемента <trace>"
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Элемент &lt;clear&gt; для &lt;listeners&gt; для &lt;trace&gt;
Очищает коллекцию `Listeners` для трассировки.  
  
## Синтаксис  
  
```  
<clear/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Нет.  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором устанавливается переключатель трассировки.|  
|`trace`|Содержит прослушиватели, собирающие, хранящие и маршрутизирующие сообщения трассировки.|  
|`listeners`|Содержит прослушиватели, собирающие, хранящие и маршрутизирующие сообщения.  Прослушиватели направляют выходные данные трассировки соответствующему целевому объекту.|  
  
## Заметки  
 Элемент `<clear>` удаляет все прослушиватели из коллекции `Listeners` для трассировки.  Элемент `<clear>` можно использовать перед элементом `<add>`, чтобы убедиться в том, что в коллекции отсутствуют другие активные прослушиватели.  
  
 Можно очистить коллекцию `Listeners` программными средствами путем вызова метода <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> в свойстве <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=fullName> \(`System.Diagnostics.Trace.Listeners.Clear()`\).  
  
 Этот элемент может быть использован в файле конфигурации компьютера \(Machine.config\) и в файле конфигурации приложения.  
  
> [!NOTE]
>  Элемент `<clear>` удаляет <xref:System.Diagnostics.DefaultTraceListener> из коллекции `Listeners`, изменяя свойства методов <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=fullName> и <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=fullName>.  При вызове метода `Assert` или `Fail` обычно отображается окно с сообщением об ошибке.  Однако это окно сообщения не отображается, если <xref:System.Diagnostics.DefaultTraceListener> не входит в коллекцию `Listeners`.  
  
## Пример  
 В следующем примере показано, как использовать элемент `<clear>` перед элементом `<add>`, чтобы добавить прослушиватель `console` в коллекцию `Listeners` для трассировки.  
  
```  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <clear/>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>   
```  
  
## См. также  
 <xref:System.Diagnostics.Trace.Listeners%2A>   
 <xref:System.Diagnostics.Trace>   
 <xref:System.Diagnostics.Debug>   
 <xref:System.Diagnostics.TraceSource>   
 [Схема параметров трассировки и отладки](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)   
 [\<remove\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)   
 [Trace Listeners](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)