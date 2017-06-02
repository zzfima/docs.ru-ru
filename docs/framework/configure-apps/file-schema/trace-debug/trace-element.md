---
title: "Элемент &lt;trace&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#trace"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<trace> - элемент"
  - "прослушиватели"
  - "trace - элемент"
  - "прослушиватель трассировки, <trace> - элемент"
ms.assetid: 7931c942-63c1-47c3-a045-9d9de3cacdbf
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# Элемент &lt;trace&gt;
Содержит прослушиватели, собирающие, хранящие и маршрутизирующие сообщения трассировки.  
  
## Синтаксис  
  
```  
<trace autoflush="true|false"   
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`autoflush`|Необязательный атрибут.<br /><br /> Указание того, должны ли прослушиватели трассировки автоматически очищать выходной буфер после каждой операции записи.|  
|`indentsize`|Необязательный атрибут.<br /><br /> Задание количества пробелов для отступа.|  
|`useGlobalLock`|Необязательный атрибут.<br /><br /> Определение того, необходимо ли использовать глобальную блокировку.|  
  
## Атрибут autoflush  
  
|Значение|Описание|  
|--------------|--------------|  
|`false`|Автоматическая очистка выходного буфера не выполняется.  Это значение по умолчанию.|  
|`true`|Выполняется автоматическая очистка выходного буфера.|  
  
## Атрибут useGlobalLock  
  
|Значение|Описание|  
|--------------|--------------|  
|`false`|Глобальная блокировка не используется, если прослушиватель потокобезопасен; в противном случае глобальная блокировка используется.|  
|`true`|Глобальная блокировка используется независимо от того, является ли прослушиватель потокобезопасным.  Это значение по умолчанию.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<прослушиватели\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|Задает прослушиватель, собирающий, хранящий и маршрутизирующий сообщения.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором устанавливается переключатель трассировки.|  
  
## Пример  
 В следующем примере показано, как использовать элемент `<trace>` для добавления прослушивателя `MyListener` в коллекцию `Listeners`.  `MyListener` создает файл `MyListener.log` и записывает в него результат.  Атрибуту `useGlobalLock` назначено значение `false`, поэтому при потокобезопасном прослушивателе глобальная блокировка использоваться не будет.  Атрибуту `autoflush` назначено значение `true`, поэтому прослушиватель трассировки выполняет запись в файл независимо от того, вызывается ли метод <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=fullName>.  Атрибуту `indentsize` назначено значение 0 \(ноль\), поэтому прослушиватель не вставляет пробелов в отступ при вызове метода <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=fullName>.  
  
```  
<configuration>  
   <system.diagnostics>  
      <trace useGlobalLock="false" autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## См. также  
 <xref:System.Diagnostics.TraceListener>   
 <xref:System.Diagnostics.DefaultTraceListener>   
 <xref:System.Diagnostics.TextWriterTraceListener>   
 <xref:System.Diagnostics.EventLogTraceListener>   
 [Схема параметров трассировки и отладки](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)