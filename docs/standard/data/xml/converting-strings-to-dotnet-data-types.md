---
title: "Преобразование строк в типы данных .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 65455ef3-9120-412c-819b-d0f59f88ac09
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ce594234e601cd8feb4723bbc383db9e3ed40522
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="converting-strings-to-net-framework-data-types"></a>Преобразование строк в типы данных .NET Framework
Если вы хотите преобразовать строку в тип данных .NET Framework, используйте **XmlConvert** метод, соответствующий требованиям приложения. Список всех методов преобразования в **XmlConvert** см. в описании <xref:System.Xml.XmlConvert>.  
  
 Строка, возвращаемая из **ToString** метод — это строковая версия, переданного в данных. Кроме того, существует несколько типов .NET Framework, которые преобразуются с помощью **XmlConvert** класса, но они не используют методы в **System.Convert** класса. **XmlConvert** класс соответствует спецификации типа данных схемы XML (XSD) и имеет тип данных, **XmlConvert** может быть сопоставлен.  
  
 В следующей таблице перечислены типы данных .NET Framework и строковые типы, возвращаемые с помощью сопоставления типа данных XSD. Эти типы .NET Framework не может обрабатываться с помощью **System.Convert**.  
  
|Тип платформы .NET Framework|Возвращаемая строка|  
|-------------------------|---------------------|  
|Boolean|"true", "false"|  
|Single.PositiveInfinity|"INF"|  
|Single.NegativeInfinity|"-INF"|  
|Double.PositiveInfinity|"INF"|  
|Double.NegativeInfinity|"-INF"|  
|DateTime|Используется формат «гггг-ММ-ддТЧЧ:мм:ссzzzzzz» и его сокращенные версии.|  
|TimeSpan|Используется формат PnYnMnTnHnMnS, то есть значение `P2Y10M15DT10H30M20S` соответствует длительности в 2 года, 10 месяцев, 15 дней, 10 часов, 30 минут и 20 секунд.|  
  
> [!NOTE]
>  Если преобразование любого типа .NET Framework, перечисленных в таблице в строку с помощью **ToString** метод, возвращаемая строка не является базовым типом, но строковый тип схемы XML (XSD).  
  
 **DateTime** и **Timespan** тип значения отличаются тем, что **DateTime** представляет момент времени, а **TimeSpan** представляет интервал времени. **DateTime** и **Timespan** форматы указаны в спецификации типов данных схемы XML (XSD). Пример:  
  
```vb  
Dim writer As New XmlTextWriter("myfile.xml", Nothing)  
Dim [date] As New DateTime(2001, 8, 4)  
writer.WriteElementString("Date", XmlConvert.ToString([date]))  
```  
  
```csharp  
XmlTextWriter writer = new XmlTextWriter("myfile.xml", null);  
DateTime date = new DateTime (2001, 08, 04);  
writer.WriteElementString("Date", XmlConvert.ToString(date));  
```  
  
 **Вывод**  
  
 `<Date>2001-08-04T00:00:00</Date>`.  
  
 В следующем примере кода целочисленное значение преобразуется в строку.  
  
```vb  
Dim writer As New XmlTextWriter("myfile.xml", Nothing)  
Dim value As Int32 = 200  
writer.WriteElementString("Number", XmlConvert.ToString(value))  
```  
  
```csharp  
XmlTextWriter writer = new XmlTextWriter("myfile.xml", null);  
Int32 value = 200;  
writer.WriteElementString("Number", XmlConvert.ToString(value));  
```  
  
 **Вывод**  
  
 `<Number>200</Number>`  
  
 Тем не менее при преобразовании строки **логическое**, **один**, или **двойные**, возвращаемый тип .NET Framework не совпадает с типом, возвращаемым при использовании **System.Convert** класса.  
  
## <a name="string-to-boolean"></a>Преобразование строки в тип Boolean  
 Следующая таблица показывает, какие типы создаются для заданных входных строк при преобразовании строки в **логическое** с помощью **ToBoolean** метод.  
  
|Допустимый строковый входной параметр|Выходной тип .NET Framework|  
|----------------------------------|--------------------------------|  
|"true"|Boolean.True|  
|"1"|Boolean.True|  
|"false"|Boolean.False|  
|"0"|Boolean.False|  
  
 Например, пусть задан следующий XML-код.  
  
 **Ввод**  
  
```xml  
<Boolean>true</Boolean>  
<Boolean>1</Boolean>   
```  
  
 Можно воспринимать как в следующем примере кода и **bvalue** — **System.Boolean.True**:  
  
```vb  
Dim bvalue As Boolean = _  
   XmlConvert.ToBoolean(reader.ReadElementString())  
Console.WriteLine(bvalue)  
```  
  
```csharp  
Boolean bvalue = XmlConvert.ToBoolean(reader.ReadElementString());  
Console.WriteLine(bvalue);  
```  
  
## <a name="string-to-single"></a>Преобразование строки в тип Single  
 Следующая таблица показывает, какие типы создаются для заданных входных строк при преобразовании строки в **один** с помощью **ToSingle** метод.  
  
|Допустимый строковый входной параметр|Выходной тип .NET Framework|  
|----------------------------------|--------------------------------|  
|"INF"|Single.PositiveInfinity|  
|"-INF"|Single.NegativeInfinity|  
  
## <a name="string-to-double"></a>Преобразование строки в тип Double  
 Следующая таблица показывает, какие типы создаются для заданных входных строк при преобразовании строки в **один** с помощью **ToDouble** метод.  
  
|Допустимый строковый входной параметр|Выходной тип .NET Framework|  
|----------------------------------|--------------------------------|  
|"INF"|Double.PositiveInfinity|  
|"-INF"|Double.NegativeInfinity|  
  
 Следующий код записывает строку `<Infinity>INF</Infinity>`:  
  
```vb  
Dim value As Double = Double.PositiveInfinity  
writer.WriteElementString("Infinity", XmlConvert.ToString(value))  
```  
  
```csharp  
Double value = Double.PositiveInfinity;  
writer.WriteElementString("Infinity", XmlConvert.ToString(value));  
```  
  
## <a name="see-also"></a>См. также  
 [Преобразование типов данных XML](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 [Преобразование типов .NET Framework в строки](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
