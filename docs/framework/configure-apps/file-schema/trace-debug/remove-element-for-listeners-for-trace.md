---
title: "Элемент &lt;remove&gt; для &lt;listeners&gt; для &lt;trace&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<remove> - элемент"
  - "remove - элемент"
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# Элемент &lt;remove&gt; для &lt;listeners&gt; для &lt;trace&gt;
Удаление прослушивателя из коллекции **Listeners**.  
  
## Синтаксис  
  
```  
  
<remove name="listener name" />  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|**name**|Обязательный атрибут.<br /><br /> Имя прослушивателя, которое необходимо удалить из коллекции **Listeners**.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`listeners`|Задает прослушиватель, собирающий, хранящий и маршрутизирующий сообщения.  Прослушиватели направляют выходные данные трассировки соответствующему целевому объекту.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором устанавливается переключатель трассировки.|  
|`trace`|Настройка службы трассировки ASP.NET.|  
  
## Заметки  
  
> [!NOTE]
>  Удаление класса <xref:System.Diagnostics.DefaultTraceListener> из коллекции `Listeners` изменяет свойства методов <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=fullName> и <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=fullName>.  Вызов метода `Assert` или `Fail` в обычной ситуации приводит к отображению окна сообщения, однако, если класс <xref:System.Diagnostics.DefaultTraceListener> отсутствует в коллекции `Listeners`, окно сообщения не отображается.  
  
## Пример  
 В следующем примере показано, как удалить прослушиватель трассировки, используемый по умолчанию, из коллекции трассировки **Listeners**.  
  
```  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <remove name="Default" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## См. также  
 <xref:System.Diagnostics.TraceListener>   
 <xref:System.Diagnostics.DefaultTraceListener>   
 <xref:System.Diagnostics.TextWriterTraceListener>   
 <xref:System.Diagnostics.EventLogTraceListener>   
 [Схема параметров трассировки и отладки](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)