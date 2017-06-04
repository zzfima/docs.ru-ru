---
title: "Элемент &lt;clear&gt; для &lt;listeners&gt; для &lt;source&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<clear> - элемент для <listeners> для <source>"
  - "элемент clear для элемента <listeners> для элемента <source>"
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# Элемент &lt;clear&gt; для &lt;listeners&gt; для &lt;source&gt;
Очистка коллекции `Listeners` для источника трассировки.  
  
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
|`sources`|Элемент, содержащий источники трассировки, инициирующие трассировочные сообщения.|  
|`source`|Источник трассировки, инициирующий сообщения трассировки.|  
|`listeners`|Задает прослушиватели, предназначенные для сбора, хранения и маршрутизации сообщений.|  
  
## Заметки  
 Элемент `<clear>` удаляет всех прослушивателей из коллекции `Listeners` источника трассировки, включая <xref:System.Diagnostics.DefaultTraceListener>.  Элемент `<clear>` можно использовать перед элементом `<add>`, чтобы убедиться в том, что в коллекции отсутствуют другие активные прослушиватели.  
  
## Файл конфигурации  
 Этот элемент может быть использован в файле конфигурации компьютера \(Machine.config\) и в файле конфигурации приложения.  
  
## Пример  
 В следующем примере показано, как использовать элемент `<clear>` перед элементами `<add>`, чтобы добавить прослушиватели `console` и `textListener` к коллекции `Listeners` источника трассировки `TraceSourceApp`.  
  
```  
<configuration>  
  <system.diagnostics>  
    <sources>  
       <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <clear/>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"   
        type="System.Diagnostics.TextWriterTraceListener"   
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>   
```  
  
## См. также  
 <xref:System.Diagnostics.TraceSource>   
 <xref:System.Diagnostics.TraceListener>   
 [Схема параметров трассировки и отладки](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)   
 [Trace Listeners](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)