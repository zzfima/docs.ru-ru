---
title: "Элемент &lt;listeners&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<listeners> - элемент для <source>"
  - "элемент listeners для элемента <source>"
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Элемент &lt;listeners&gt;
Добавление или удаление прослушивателей в коллекции <xref:System.Diagnostics.TraceSource.Listeners%2A> для свойства <xref:System.Diagnostics.TraceSource>.  Прослушиватель направляет данные трассировки соответствующему целевому объекту, например в журнал событий, окно или текстовый файл.  
  
## Синтаксис  
  
```  
<listeners>   
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Нет.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-source.md)|Добавляет прослушиватель в коллекцию `Listeners`.|  
|[\<remove\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-source.md)|Удаляет прослушиватель из коллекции `Listeners`.|  
|[\<clear\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)|Очистка коллекции `Listeners` для источника трассировки.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором устанавливается переключатель трассировки.|  
|`sources`|Элемент, содержащий источники трассировки, инициирующие трассировочные сообщения.|  
|`source`|Источник трассировки, инициирующий сообщения трассировки.|  
  
## Заметки  
  
## Файл конфигурации  
 Этот элемент может быть использован в файле конфигурации компьютера \(Machine.config\) и в файле конфигурации приложения.  
  
## Пример  
 В следующем примере кода показано, как с помощью элемента `<listeners>`  добавить прослушиватель трассировки консоли в источник `mySource` и удалить прослушиватель трассировки по умолчанию.  
  
```  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener">  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error"/>  
          </add>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## См. также  
 <xref:System.Diagnostics.TraceListener>   
 [Схема параметров трассировки и отладки](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)   
 [Trace Listeners](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)