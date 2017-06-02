---
title: "Элемент &lt;remove&gt; для &lt;listeners&gt; для &lt;source&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<remove> - элемент для <listeners> для <source>"
  - "элемент remove для элемента <listeners> для элемента <source>"
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# Элемент &lt;remove&gt; для &lt;listeners&gt; для &lt;source&gt;
Удаляет прослушиватель из коллекции `Listeners` для источника трассировки.  
  
## Синтаксис  
  
```  
<remove name="listenerName" />  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`name`|Обязательный атрибут.<br /><br /> Имя прослушивателя для удаления из коллекции `Listeners`.|  
  
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
 Элемент `<remove>` удаляет указанный прослушиватель из коллекции `Listeners` для источника трассировки.  
  
 Можно удалить элемент из коллекции `Listeners` для источника трассировки программными средствами, вызвав метод <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> для свойства <xref:System.Diagnostics.TraceSource.Listeners%2A> экземпляра <xref:System.Diagnostics.TraceSource>.  
  
 Этот элемент может быть использован в файле конфигурации компьютера \(Machine.config\) и в файле конфигурации приложения.  
  
## Пример  
 В следующем примере показано использование элемента `<remove>` перед использованием элемента `<add>` для добавления прослушивателя `console` в коллекцию `Listeners` для источника трассировки `TraceSourceApp`.  
  
```  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch" >  
         <listeners>  
           <remove name="Default"/>  
           <add name="console"   
             type="System.Diagnostics.ConsoleTraceListener" />  
         </listeners>  
      </source>  
    </sources>  
  </system.diagnostics>  
</configuration>   
```  
  
## См. также  
 <xref:System.Diagnostics.TraceSource.Listeners%2A>   
 <xref:System.Diagnostics.TraceSource>   
 [Схема параметров трассировки и отладки](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)   
 [\<clear\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)   
 [Trace Listeners](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)