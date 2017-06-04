---
title: "Элемент &lt;add&gt; для &lt;sharedListeners&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<add> - элемент для <sharedListeners>"
  - "add - элемент для <sharedListeners>"
  - "initializeData - атрибут"
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# Элемент &lt;add&gt; для &lt;sharedListeners&gt;
Добавляет прослушиватель в коллекцию `sharedListeners`.  `sharedListeners` — это коллекция прослушивателей, на которую может ссылаться любой [\<source\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) или [\<trace\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md).  По умолчанию прослушиватели в коллекции `sharedListeners` не помещаются в коллекцию `Listeners`.  Они должны добавляться по именам в [\<source\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) или [\<trace\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md).  Невозможно получить прослушиватели в коллекцию `sharedListeners` в коде во время выполнения.  
  
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
|`name`|Обязательный атрибут.<br /><br /> Указывает имя прослушивателя, который используется для добавления общего прослушивателя в коллекцию `Listeners`.|  
|`type`|Обязательный атрибут.<br /><br /> Задает тип прослушивателя.  Строка должна отвечать требованиям, указанным в разделе [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Необязательный атрибут.<br /><br /> Строка, передаваемая в конструктор для заданного класса.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<filter\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-sharedlisteners.md)|Добавляет фильтр в прослушиватель в коллекции `sharedListeners`.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором устанавливается переключатель трассировки.|  
|`sharedListeners`|Коллекция прослушивателей, на которые может ссылаться любой источник или элемент трассировки.|  
  
## Заметки  
 Классы прослушивателей, поставляемые с .NET Framework, являются производными от класса <xref:System.Diagnostics.TraceListener>.  Значение для атрибута `name` используется для добавления общего прослушивателя в коллекцию `Listeners` для прослеживания или источника прослеживания.  Значение атрибута `initializeData` зависит от типа создаваемого прослушивателя.  Не всем прослушивателям требуется определение атрибута `initializeData`.  
  
> [!NOTE]
>  Когда используется атрибут `initializeData`, можно получить сообщение компилятора "Атрибут 'initializeData' не объявлен". Это предупреждение возникает из\-за того, что параметры конфигурации проверяются на абстрактный базовый класс <xref:System.Diagnostics.TraceListener>, который не распознает атрибут `initializeData`.  Как правило, можно игнорировать это предупреждение для реализаций прослушивателя трассировки, имеющих конструктор, который принимает параметр.  
  
 Следующая таблица содержит перечень прослушивателей трассировки, входящих в комплект поставки .NET Framework, и описание значения их атрибутов `initializeData`.  
  
|Класс прослушивателей трассировки|Значение атрибута initializeData|  
|---------------------------------------|--------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|Значение `useErrorStream` для конструктора <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>.  Задайте для атрибута `initializeData` значение "`true`", чтобы вести запись трассировки и отладку вывода в стандартный поток ошибок; задайте значение "`false`", чтобы вести запись в стандартный выходной поток.|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|Имя файла, в который осуществляет запись объект <xref:System.Diagnostics.DelimitedListTraceListener>.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=fullName>|Имя существующего источника журнала событий.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=fullName>|Имя файла, в который осуществляет запись объект <xref:System.Diagnostics.EventSchemaTraceListener>.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=fullName>|Имя файла, в который осуществляет запись объект <xref:System.Diagnostics.TextWriterTraceListener>.|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|Имя файла, в который осуществляет запись объект <xref:System.Diagnostics.XmlWriterTraceListener>.|  
  
## Файл конфигурации  
 Этот элемент может быть использован в файле конфигурации компьютера \(Machine.config\) и в файле конфигурации приложения.  
  
## Пример  
 В следующем примере показано, как использовать элементы `<add>` для добавления <xref:System.Diagnostics.TextWriterTraceListener> `textListener` в коллекцию `sharedListeners`.  `textListener` добавляется по имени в коллекции `Listeners` для источника трассировки `TraceSourceApp`.  Прослушиватель `textListener` записывает результат трассировки в файл myListener.log.  
  
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