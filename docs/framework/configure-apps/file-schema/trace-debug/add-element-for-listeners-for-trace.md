---
title: "Элемент &lt;add&gt; для &lt;listeners&gt; для &lt;trace&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<add> - элемент для <listeners>"
  - "add - элемент для <listeners>"
  - "initializeData - атрибут"
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
caps.latest.revision: 24
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 22
---
# Элемент &lt;add&gt; для &lt;listeners&gt; для &lt;trace&gt;
Добавление прослушивателя в коллекцию **Listeners**.  
  
## Синтаксис  
  
```  
<add name="name"   
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|**type**|Обязательный атрибут.<br /><br /> Задает тип прослушивателя.  Необходимо использовать строку, отвечающую требованиям, описанным в разделе [Указание полных имен типов](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|**initializeData**|Необязательный атрибут.<br /><br /> Строка, передаваемая в конструктор для заданного класса.|  
|**name**|Необязательный атрибут.<br /><br /> Указывает имя прослушивателя.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<filter\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|Добавляет фильтр в прослушиватель в коллекции `Listeners`для трассировки.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`listeners`|Задает прослушиватель, собирающий, хранящий и маршрутизирующий сообщения.  Прослушиватели направляют выходные данные трассировки соответствующему целевому объекту.|  
|`system.diagnostics`|Определяет корневой элемент для раздела конфигурации ASP.NET.|  
|`trace`|Содержит прослушиватели, собирающие, хранящие и маршрутизирующие сообщения трассировки.|  
  
## Заметки  
 Классы <xref:System.Diagnostics.Debug> и <xref:System.Diagnostics.Trace> совместно используют коллекцию **Listeners**.  Если в одном из этих классов в коллекцию добавляется объект прослушивателя, то этот прослушиватель используется и в другом классе.  Классы прослушивателей являются производными от класса [TraceListener](frlrfSystemDiagnosticsTraceListenerClassTopic).  
  
 Если атрибут `nam` прослушивателя трассировки не задан, то по умолчанию для свойства <xref:System.Diagnostics.TraceListener.Name%2A> прослушивателя трассировки устанавливается пустая строка \(""\).  Если у приложения имеется только один прослушиватель, то он может быть добавлен без указания имени и убран указанием пустой строки для его имени.  Однако если у приложения имеется более одного прослушивателя, то для каждого прослушивателя трассировки должно быть установлено свое уникальное имя, позволяющее распознавать и управлять индивидуальными прослушивателями трассировки в коллекциях <xref:System.Diagnostics.Debug.Listeners%2A> и <xref:System.Diagnostics.Trace.Listeners%2A>.  
  
> [!NOTE]
>  При добавлении более одного прослушивателя трассировки одного типа и с одинаковым именем приводит к тому, что лишь один прослушиватель этого типа с этим именем добавляется к коллекции `Listeners`.  Однако несколько одинаковых прослушивателей могут быть добавлены к коллекции `Listeners` программным путем.  
  
 Значение атрибута **initializeData** зависит от типа создаваемого прослушивателя.  Не для всех прослушивателей трассировки требуется задание атрибута **initializeData**.  
  
> [!NOTE]
>  Когда используется атрибут `initializeData`, можно получить сообщение компилятора "Атрибут 'initializeData' не объявлен". Это предупреждение возникает из\-за того, что параметры конфигурации проверяются на абстрактный базовый класс <xref:System.Diagnostics.TraceListener>, который не распознает атрибут `initializeData`.  Как правило, можно игнорировать это предупреждение для реализаций прослушивателя трассировки, имеющих конструктор, который принимает параметр.  
  
 В следующей таблице перечислены прослушиватели трассировки, поставляемые в комплекте с платформой .NET Framework, и описываются значения их атрибутов **initializeData**.  
  
|Класс прослушивателей трассировки|Значение атрибута initializeData|  
|---------------------------------------|--------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=fullName>|Значение `useErrorStream` для конструктора <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>.  Задайте для атрибута `initializeData` значение "`true`", чтобы записать трассировку и отладить выход в свойстве <xref:System.Console.Error%2A?displayProperty=fullName>; задайте значение "`false`", чтобы записать в свойстве <xref:System.Console.Out%2A?displayProperty=fullName>.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=fullName>|Имя файла, в который осуществляет запись объект <xref:System.Diagnostics.DelimitedListTraceListener>.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=fullName>|Имя существующего источника журнала событий.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=fullName>|Имя файла, в который осуществляет запись объект <xref:System.Diagnostics.EventSchemaTraceListener>.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=fullName>|Имя файла, в который осуществляет запись объект <xref:System.Diagnostics.TextWriterTraceListener>.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=fullName>|Имя файла, в который осуществляет запись объект <xref:System.Diagnostics.XmlWriterTraceListener>.|  
  
## Пример  
 В следующем примере показано, как использовать элементы **\<add\>** для добавления прослушивателей `MyListener` и `MyEventListener` в коллекцию **Listeners**.  `MyListener` создает файл `MyListener.log` и записывает в него результат.  `MyEventListener` создает запись в журнале событий.  
  
```  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
            <add name="MyEventListener"  
                 type="System.Diagnostics.EventLogTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"                 initializeData="MyConfigEventLog"/>  
            <add name="configConsoleListener"  
                 type="System.Diagnostics.ConsoleTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## См. также  
 <xref:System.Diagnostics.Trace>   
 <xref:System.Diagnostics.Debug>   
 <xref:System.Diagnostics.EventLogTraceListener>   
 <xref:System.Diagnostics.ConsoleTraceListener>   
 <xref:System.Diagnostics.TextWriterTraceListener>   
 [Схема параметров трассировки и отладки](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)   
 [Trace Listeners](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)