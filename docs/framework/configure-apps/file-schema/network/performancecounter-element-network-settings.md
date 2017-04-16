---
title: "Элемент &lt;performanceCounter&gt; (параметры сети) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/performanceCounters"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<performanceCounter> - элемент"
  - "performanceCounter - элемент"
ms.assetid: 3afa1586-e1b8-473d-8985-c3fc90cf561b
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Элемент &lt;performanceCounter&gt; (параметры сети)
Включает или отключает сетевые счетчики производительности.  
  
## Синтаксис  
  
```  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`enabled`|Указывает, включены ли сетевые счетчики производительности.  Значение по умолчанию — `false`.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Настраивает основные сетевые параметры для пространства имен <xref:System.Net>.|  
  
## Заметки  
 Этот элемент может быть использован в файле конфигурации приложения или в файле конфигурации компьютера \(Machine.config\).  
  
 Чтобы можно было использовать сетевые счетчики производительности, их необходимо включить в файле конфигурации.  Все сетевые счетчики производительности были включены или отключены с помощью одного параметра в файле конфигурации.  Отдельные сетевые счетчики производительности не могут быть включены или отключены.  Дополнительные сведения о конкретных сетевых счетчиках производительности см. в разделе [Networking Performance Counters](http://msdn.microsoft.com/ru-ru/d1860235-f643-46ae-846c-ff0ed8b0e3cd).  
  
 По умолчанию установлено, что сетевые счетчики производительности отключены.  
  
 Свойство <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=fullName> может использоваться для получения текущего значения атрибута **enabled** из применимых файлов конфигурации.  
  
## Пример  
 В следующем примере кода показана настройка пространства имен <xref:System.Net> и связанных пространств имен для включения сетевых счетчиков производительности.  
  
```  
<configuration>  
  <system.net>  
    <settings>  
      <performanceCounters  
        enabled="true"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## См. также  
 <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=fullName>   
 <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=fullName>   
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)   
 [Networking Performance Counters](http://msdn.microsoft.com/ru-ru/d1860235-f643-46ae-846c-ff0ed8b0e3cd)