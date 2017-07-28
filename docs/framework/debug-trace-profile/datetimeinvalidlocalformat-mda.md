---
title: "dateTimeInvalidLocalFormat MDA | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "dates [.NET Framework], formatting"
  - "invalid date time local format"
  - "invalid local formats"
  - "MDAs (managed debugging assistants), invalid local formats"
  - "managed debugging assistants (MDAs), invalid local formats"
  - "dateTimeInvalidLocalFormat MDA"
  - "date formatting"
  - "time formatting"
  - "UTC formatting"
ms.assetid: c4a942bb-2651-4b65-8718-809f892a0659
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# dateTimeInvalidLocalFormat MDA
Помощник по отладке управляемого кода \(MDA\) `dateTimeInvalidLocalFormat` активируется в случае, когда экземпляр <xref:System.DateTime>, который хранится в формате UTC, форматируется с применением формата, который должен использоваться только для экземпляров <xref:System.DateTime> в локальном времени.  Данный помощник по отладке управляемого кода не активируется для экземпляров <xref:System.DateTime>, для которых не заданы дата и время, или экземпляров этого объекта по умолчанию.  
  
## Признаки  
 Приложение выполняет сериализацию экземпляра <xref:System.DateTime> в формате UTC вручную с применением локального формата:  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffzzz"));  
```  
  
### Причина  
 Формат "z" для метода <xref:System.DateTime.ToString%2A?displayProperty=fullName> включает смещение местного часового пояса, например "\+10:00" для времени Сиднея.  При этом результат применения данного формата будет значимым только в том случае, если значение <xref:System.DateTime> является локальным.  Если в качестве значения выступает время в формате UTC, метод <xref:System.DateTime.ToString%2A?displayProperty=fullName> включает смещение местного часового пояса, но не отображает и не регулирует спецификатор часового пояса.  
  
### Решение  
 Для форматирования экземпляров <xref:System.DateTime> в формате UTC необходимо выбрать способ, указывающий на то, что данные экземпляры являются экземплярами UTC.  Рекомендуется при форматировании времени UTC использовать "Z" для обозначения времени UTC:  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffZ"));  
```  
  
 Можно также использовать формат "o", который сериализует объект <xref:System.DateTime> с помощью свойства <xref:System.DateTime.Kind%2A>, правильно выполняющего сериализацию независимо от того, как указывается дата и время в экземпляре: в локальном времени, в формате UTC или они вовсе не заданы:  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("o"));  
```  
  
## Влияние на среду выполнения  
 Данный помощник по отладке управляемого кода не оказывает влияния на среду выполнения.  
  
## Output  
 В результате активации данного помощника по отладке управляемого кода не возникает каких\-либо особых выходных данных. Тем не менее, для определения местоположения вызова метода <xref:System.DateTime.ToString%2A>, активирующего данный помощник по отладке управляемого кода, можно использовать стек вызовов.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <dateTimeInvalidLocalFormat />  
  </assistants>  
</mdaConfig>  
```  
  
## Пример  
 Можно использовать приложение, которое опосредованно выполняет сериализацию объекта <xref:System.DateTime> в формате UTC, с помощью класса <xref:System.Xml.XmlConvert> или <xref:System.Data.DataSet>.  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XMLConvert.ToString(myDateTime);  
```  
  
 Классы <xref:System.Xml.XmlConvert> и <xref:System.Data.DataSet> используют локальные форматы для сериализации по умолчанию.  Для сериализации других типов значений <xref:System.DateTime>, например UTC, необходимы дополнительные параметры.  
  
 В данном конкретном примере при вызове метода `ToString` в классе `XmlConvert` передается значение `XmlDateTimeSerializationMode.RoundtripKind`.  В результате выполняется сериализация значения времени в формате UTC.  
  
 При использовании метода <xref:System.Data.DataSet> следует присвоить свойству <xref:System.Data.DataColumn.DateTimeMode%2A> объекта <xref:System.Data.DataColumn> значение <xref:System.Data.DataSetDateTime>.  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XmlConvert.ToString(myDateTime,   
    XmlDateTimeSerializationMode.RoundtripKind);  
```  
  
## См. также  
 <xref:System.Globalization.DateTimeFormatInfo>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)