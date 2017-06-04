---
title: "Элемент &lt;add&gt; для &lt;switches&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches/add"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<add> - элемент для <switches>"
  - "add - элемент для < <switches>"
ms.assetid: 712ac3a7-7abf-4a9e-8db4-acd241c2f369
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Элемент &lt;add&gt; для &lt;switches&gt;
Задает уровень, на котором устанавливается переключатель трассировки.  
  
## Синтаксис  
  
```  
<add name="switch name"  
     value="value"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|**name**|Обязательный атрибут.<br /><br /> Указание имени переключателя.  Значение этого атрибута соответствует параметру *displayName*, который передается конструктору переключателя.|  
|**value**|Обязательный атрибут.<br /><br /> Указание уровня переключателя.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`switches`|Содержит переключатели трассировки и уровень, на котором установлены эти переключатели.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором устанавливается переключатель трассировки.|  
  
## Заметки  
 Уровень переключателя трассировки можно изменить, внеся его в файл конфигурации.  Если используется переключатель <xref:System.Diagnostics.BooleanSwitch>, его можно включать и отключать.  Если используется переключатель <xref:System.Diagnostics.TraceSwitch>, ему можно назначать различные уровни, определяющие типы трассировки или сообщения отладки, выводимые приложением.  
  
## Пример  
 В следующем примере показано, как использовать элемент **\<add\>** для установки для переключателя трассировки `General` уровня [TraceLevel.Error](frlrfSystemDiagnosticsTraceLevelClassTopic), а также для включения логического переключателя трассировки `Data`.  
  
```  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
         <add name="Data" value="1" />  
      </switches>  
   </system.diagnostics>  
</configuration>  
```  
  
## См. также  
 <xref:System.Diagnostics.Switch>   
 <xref:System.Diagnostics.TraceSwitch>   
 <xref:System.Diagnostics.BooleanSwitch>   
 [Схема параметров трассировки и отладки](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)