---
title: "Элемент &lt;filter&gt; для &lt;add&gt; для &lt;sharedListeners&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add/filter"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<filter> - элемент для <add> для <listeners> для <sharedListeners>"
  - "элемент filter для элемента <add> для элемента <sharedListeners>"
  - "фильтры, прослушиватели трассировки"
  - "initializeData - атрибут"
  - "прослушиватели трассировки, фильтры"
ms.assetid: 7d4e7faa-2e4e-4379-ac76-f6cd7f2f8fac
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# Элемент &lt;filter&gt; для &lt;add&gt; для &lt;sharedListeners&gt;
Добавляет фильтр в прослушиватель в коллекции `sharedListeners`.  
  
## Синтаксис  
  
```  
<filter type="System.Diagnostics.EventTypeFilter"   
  initializeData="Warning" />  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|**type**|Обязательный атрибут.<br /><br /> Задает типа фильтра.  Можно использовать только полное имя типа \(в формате свойства <xref:System.Type.FullName%2A?displayProperty=fullName>\) или полное имя типа, включающее информацию о сборке \(в формате свойства <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=fullName>\).  Для получения более подробных сведений о создании полного имени см. раздел [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|**initializeData**|Необязательный атрибут.<br /><br /> Строка, передаваемая в конструктор для заданного класса.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором устанавливается переключатель трассировки.|  
|`sharedListeners`|Коллекция прослушивателей, на которые может ссылаться любой источник или элемент трассировки.|  
|`add`|Добавляет прослушиватель в коллекцию **sharedListeners**.|  
  
## Заметки  
 Если прослушиватель задан в элементе `<add>` элемента `<sharedListeners>`, фильтр прослушивателя должен быть задан в элементе `<filter>`, являющимся дочерним по отношению к элементу `<add>`.  
  
 Этот элемент может быть использован в файле конфигурации компьютера \(Machine.config\) и в файле конфигурации приложения.  
  
## Пример  
 В следующем примере показано, как использовать элемент `<filter>` для добавления фильтра трассировки прослушивателя `console` в коллекцию `sharedListeners`.  
  
```  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" >  
        <listeners>  
          <add name="console" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="console"   
        type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"   
          initializeData="Error" />  
      </add>  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## См. также  
 <xref:System.Diagnostics.TraceFilter>   
 <xref:System.Diagnostics.TraceListener>   
 <xref:System.Diagnostics.TraceSource>   
 [Схема параметров трассировки и отладки](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)