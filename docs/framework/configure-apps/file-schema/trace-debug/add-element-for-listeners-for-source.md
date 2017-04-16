---
title: "Элемент &lt;add&gt; для &lt;listeners&gt; для &lt;source&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<add> - элемент для <listeners> для <source>"
  - "add - элемент для <listeners> для <source>"
  - "initializeData - атрибут"
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# Элемент &lt;add&gt; для &lt;listeners&gt; для &lt;source&gt;
Добавляет прослушиватель в коллекцию `Listeners` для источника трассировки.  
  
## Синтаксис  
  
```  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`type`|Обязательный атрибут.<br /><br /> Задает тип прослушивателя.  Строка должна отвечать требованиям, указанным в разделе [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Необязательный атрибут.<br /><br /> Строка, передаваемая в конструктор для заданного класса.  Если класс не содержит конструктора, принимающего в качестве значения строковое выражение, происходит исключение <xref:System.Configuration.ConfigurationException>.|  
|`name`|Необязательный атрибут.<br /><br /> Указывает имя прослушивателя.|  
|`traceOutputOptions`|Необязательный атрибут.<br /><br /> Задает значение свойства <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> для прослушивателя трассировки.|  
|\[настраиваемые атрибуты\]|Необязательные атрибуты.<br /><br /> Определяет значение специфичных для прослушивателя атрибутов, идентифицируемых методом <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> данного прослушивателя.  <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> — пример дополнительного атрибута, уникального для класса <xref:System.Diagnostics.DelimitedListTraceListener>.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<filter\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-source.md)|Добавляет фильтр к прослушивателю в коллекции `Listeners` для источника трассировки.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором устанавливается переключатель трассировки.|  
|`sources`|Элемент, содержащий источники трассировки, инициирующие трассировочные сообщения.|  
|`source`|Источник трассировки, инициирующий сообщения трассировки.|  
|`listeners`|Задает прослушиватели, предназначенные для сбора, хранения и маршрутизации сообщений.|  
  
## Заметки  
 Классы прослушивателей, поставляемые с .NET Framework, являются производными от класса <xref:System.Diagnostics.TraceListener>.  
  
 Если атрибут `name` для прослушивателя трассировки не задан, в качестве значения свойства <xref:System.Diagnostics.TraceListener.Name%2A> по умолчанию устанавливается пустая строка \(""\).  Если у приложения имеется только один прослушиватель, его можно добавить без указания имени и удалить, указав в качестве имени пустую строку.  Однако если у приложения более одного прослушивателя, следует задать для каждого из них уникальное имя, позволяющее идентифицировать отдельные прослушиватели трассировки и управлять ими в коллекции <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=fullName>.  
  
> [!NOTE]
>  При добавлении более одного прослушивателя трассировки одного типа и с одинаковым именем приводит к тому, что лишь один прослушиватель этого типа с этим именем добавляется к коллекции `Listeners`.  Однако несколько одинаковых прослушивателей могут быть добавлены к коллекции `Listeners` программным путем.  
  
 Значение атрибута `initializeData` зависит от типа создаваемого прослушивателя.  Не всем прослушивателям требуется определение атрибута `initializeData`.  
  
> [!NOTE]
>  Когда используется атрибут `initializeData`, можно получить сообщение компилятора "Атрибут 'initializeData' не объявлен". Это предупреждение возникает из\-за того, что параметры конфигурации проверяются на абстрактный базовый класс <xref:System.Diagnostics.TraceListener>, который не распознает атрибут `initializeData`.  Как правило, можно игнорировать это предупреждение для реализаций прослушивателя трассировки, имеющих конструктор, который принимает параметр.  
  
 Следующая таблица содержит перечень прослушивателей трассировки, входящих в комплект поставки .NET Framework, и описание значения их атрибутов `initializeData`.  
  
|Класс прослушивателей трассировки|Значение атрибута initializeData|  
|---------------------------------------|--------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=fullName>|Значение `useErrorStream` для конструктора <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>.  Задайте для атрибута `initializeData` значение "`true`", чтобы вести запись трассировки и отладку вывода в стандартный поток ошибок; задайте значение "`false`", чтобы вести запись в стандартный выходной поток.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=fullName>|Имя файла, в который осуществляет запись объект <xref:System.Diagnostics.DelimitedListTraceListener>.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=fullName>|Имя существующего источника журнала событий.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=fullName>|Имя файла, в который осуществляет запись объект <xref:System.Diagnostics.EventSchemaTraceListener>.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=fullName>|Имя файла, в который осуществляет запись объект <xref:System.Diagnostics.TextWriterTraceListener>.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=fullName>|Имя файла, в который осуществляет запись объект <xref:System.Diagnostics.XmlWriterTraceListener>.|  
  
## Файл конфигурации  
 Этот элемент может быть использован в файле конфигурации компьютера \(Machine.config\) и в файле конфигурации приложения.  
  
## Пример  
 В следующем примере показано использование элементов `<add>` для добавления прослушивателей `console` и `textListener` в коллекцию `Listeners` для источника трассировки `TraceSourceApp`.  Прослушиватель `textListener` записывает результат трассировки в файл myListener.log.  
  
```  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
          <remove name="Default"/>  
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