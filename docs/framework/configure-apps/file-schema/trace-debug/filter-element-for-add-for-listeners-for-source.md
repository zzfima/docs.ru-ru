---
title: "Элемент &lt;filter&gt; для &lt;add&gt; для &lt;listeners&gt; для &lt;source&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#filter"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<filter> - элемент для <add> для <listeners> для <source>"
  - "элемент filter для элемента <add> для элемента <listeners> для элемента <source>"
  - "initializeData - атрибут"
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# Элемент &lt;filter&gt; для &lt;add&gt; для &lt;listeners&gt; для &lt;source&gt;
Добавляет фильтр к прослушивателю в коллекции `Listeners` для источника трассировки.  
  
## Синтаксис  
  
```  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`type`|Обязательный атрибут.<br /><br /> Определяет тип фильтра, который должен наследоваться от класса <xref:System.Diagnostics.TraceFilter>.  Можно использовать полное имя типа с указанием пространства имен, соответствующее свойству <xref:System.Type.FullName%2A> данного типа, или же полное имя типа с информацией о сборке, соответствующее свойству <xref:System.Type.AssemblyQualifiedName%2A>.  Для получения более подробных сведений о полных именах см. [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Необязательный атрибут.<br /><br /> Строка, передаваемая в конструктор для заданного класса фильтра.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором устанавливается переключатель трассировки.|  
|`sources`|Элемент, содержащий источники трассировки, инициирующие трассировочные сообщения.|  
|`source`|Источник трассировки, инициирующий сообщения трассировки.|  
|`listeners`|Содержит прослушиватели, собирающие, хранящие и маршрутизирующие сообщения.  Прослушиватели направляют выходные данные трассировки соответствующему целевому объекту.|  
|`add`|Добавляет прослушиватель в коллекцию `Listeners` для источника трассировки.|  
  
## Заметки  
 Элемент `<filter>` должен содержаться в элементе `<add>` для прослушивателя источника трассировки, который задает тип прослушивателя, а не только имя прослушивателя, определенное в [\<sharedListeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).  Если прослушиватель определен в [\<sharedListeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), то фильтр для этого прослушивателя должен быть определен в данном элементе.  
  
 Этот элемент может быть использован в файле конфигурации компьютера \(Machine.config\) и в файле конфигурации приложения.  
  
## Пример  
 В следующем примере показано, как использовать элемент `<filter>` для добавления фильтра прослушивателю `console` в коллекцию `Listeners` для источника трассировки `myTraceSource`, задающее уровень события фильтра как `Error`.  
  
```  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" switchName="SourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="SourceSwitch" value="Warning" />  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## См. также  
 <xref:System.Diagnostics.TraceSource>   
 <xref:System.Diagnostics.TraceListener>   
 <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=fullName>   
 <xref:System.Diagnostics.TraceFilter>   
 [Схема параметров трассировки и отладки](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)