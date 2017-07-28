---
title: "Элемент &lt;switches&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#switches"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<switches> - элемент"
  - "switches - элемент"
  - "ключи трассировки, <switches> - элемент"
ms.assetid: 4cf36786-b89a-40e2-a0f1-86bb9b783343
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Элемент &lt;switches&gt;
Содержит переключатели трассировки и уровень, на котором установлены эти переключатели.  
  
## Синтаксис  
  
```  
  
      <switches>   
</switches>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Нет.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|Задает уровень, на котором устанавливается переключатель трассировки.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`System.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором устанавливается переключатель трассировки.|  
  
## Заметки  
 Уровень переключателя трассировки можно изменить, внеся его в файл конфигурации.  Если используется переключатель <xref:System.Diagnostics.BooleanSwitch>, его можно включать и отключать.  Если используется переключатель <xref:System.Diagnostics.TraceSwitch>, ему можно назначать различные уровни, определяющие типы трассировки или сообщения отладки, выводимые приложением.  
  
## Пример  
 В следующем примере показано использование элемента **\<switch\>** для установки переключателя трассировки `General` на уровне [TraceLevel.Error](frlrfSystemDiagnosticsTraceLevelClassTopic) и включения логического переключателя трассировки `Data`.  
  
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