---
title: "Элемент &lt;source&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#source"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<source> - элемент"
  - "source - элемент"
ms.assetid: ecf86505-735d-4844-aaba-266fdd134218
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Элемент &lt;source&gt;
Источник трассировки, инициирующий сообщения трассировки.  
  
## Синтаксис  
  
```  
<source>   
  <listeners>...</listeners>  
</source>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`name`|Необязательный атрибут.<br /><br /> Задает имя источника трассировки.|  
|`switchName`|Необязательный атрибут.<br /><br /> Задает имя экземпляра переключателя трассировки в приложении.  Если переключатель не идентифицирован в элементе `<switches>`, это значение задает уровень для переключателя.|  
|`switchType`|Необязательный атрибут.<br /><br /> Задает тип переключателя трассировки.  Если этот атрибут указан, тип должен представлять собой действительное имя класса и не может быть пустой строкой.|  
|`extraAttribute`|Необязательный атрибут.<br /><br /> Задает значение атрибута конкретного источника трассировки, идентифицируемого методом <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> данного источника.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<listeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|Содержит прослушиватели, собирающие, хранящие и маршрутизирующие сообщения.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором устанавливается переключатель трассировки.|  
|`sources`|Элемент, содержащий источники трассировки, инициирующие трассировочные сообщения.|  
  
## Заметки  
 Этот элемент может быть использован в файле конфигурации компьютера \(Machine.config\) и в файле конфигурации приложения.  
  
## Пример  
 В следующем примере показано, как использовать элемент `<source>`  для добавления источника трассировки `mySource` и установки уровня переключателя источника с именем `sourceSwitch`.  Добавляется прослушиватель трассировки консоли, выводящий трассировочную информацию на консоль.  
  
```  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch" switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter" initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
        <switches>  
           <add name="sourceSwitch" value="Warning" />  
        </switches>    
  </system.diagnostics>   
</configuration>  
```  
  
## См. также  
 [Схема параметров трассировки и отладки](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)   
 [Trace Switches](../../../../../docs/framework/debug-trace-profile/trace-switches.md)