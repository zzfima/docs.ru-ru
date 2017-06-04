---
title: "Элемент &lt;assert&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/assert"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#assert"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<assert> - элемент"
  - "assert - элемент"
ms.assetid: ef4c3229-b151-4d85-8091-e6456af9b935
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Элемент &lt;assert&gt;
Указывает, следует ли отображать сообщение при вызове метода <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>, а также задает имя файла для записи сообщений.  
  
## Синтаксис  
  
```  
  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`assertuienabled`|Необязательный атрибут.<br /><br /> Указывает, следует ли отображать окно сообщения, если метод **Debug.Assert** возвратит значение **false**.|  
|`logfilename`|Необязательный атрибут.<br /><br /> Задает имя файла, в который следует записать сообщение, если метод **Debug.Assert** возвратит значение **false**.|  
  
## Атрибут assertuienabled  
  
|Значение|Описание|  
|--------------|--------------|  
|`true`|Вызывает отображение окна сообщения.  Это значение по умолчанию.|  
|`false`|Отключает отображение окна сообщения.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором устанавливается переключатель трассировки.|  
  
## Заметки  
 Оба атрибута в элементе **\<assert\>** являются необязательными.  Можно отключить окна сообщений, не назначая файл для записи сообщений, или задать этот файл и при этом не отключать окна сообщений.  
  
## Пример  
 В следующем примере показано, как отключить отображение окон сообщений при вызове метода **Debug.Assert** и организовать запись сообщений в файл `c:\log.txt`.  
  
```  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## См. также  
 <xref:System.Diagnostics.Debug>   
 [Схема параметров трассировки и отладки](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)