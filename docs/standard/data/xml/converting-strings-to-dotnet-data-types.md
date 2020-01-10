---
title: Преобразование строк в типы данных .NET Framework
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 65455ef3-9120-412c-819b-d0f59f88ac09
ms.openlocfilehash: ac7e1b68f3f43a0c84c7330666825207e5b90004
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711055"
---
# <a name="converting-strings-to-net-framework-data-types"></a>Преобразование строк в типы данных .NET Framework
Если нужно преобразовать строку в тип данных .NET Framework, используйте метод **XmlConvert**, соответствующий требованиям приложения. Список всех методов преобразования, доступных в классе **XmlConvert**, можно найти в <xref:System.Xml.XmlConvert>.  
  
 Строка, возвращаемая методом **ToString**, представляет строковую версию переданных ему данных. Кроме того, существует несколько типов платформы .NET Framework, которые преобразуются с помощью класса **XmlConvert**, но не используют методы класса **System.Convert**. Класс **XmlConvert** следует спецификации типа данных XSD и содержит тип данных, для которого может выполняться сопоставление **XmlConvert**.  
  
 В следующей таблице перечислены типы данных .NET Framework и строковые типы, возвращаемые с помощью сопоставления типа данных XSD. **System.Convert** не поддерживает обработку этих типов .NET Framework.  
  
|Тип платформы .NET Framework|Возвращаемая строка|  
|-------------------------|---------------------|  
|Логическое значение .|"true", "false"|  
|Single.PositiveInfinity|"INF"|  
|Single.NegativeInfinity|"-INF"|  
|Double.PositiveInfinity|"INF"|  
|Double.NegativeInfinity|"-INF"|  
|DateTime|Используется формат «гггг-ММ-ддТЧЧ:мм:ссzzzzzz» и его сокращенные версии.|  
|TimeSpan|Используется формат PnYnMnTnHnMnS, то есть значение `P2Y10M15DT10H30M20S` соответствует длительности в 2 года, 10 месяцев, 15 дней, 10 часов, 30 минут и 20 секунд.|  
  
> [!NOTE]
> Если любой из типов .NET Framework, представленных в таблице, преобразуется в строку с использованием метода **ToString**, возвращаемая строка имеет не базовый тип, а тип строки XSD.  
  
 Типы значений **DateTime** и **Timespan** отличаются тем, что **DateTime** представляет момент времени, а **TimeSpan** — интервал времени. Форматы **DateTime** и **Timespan** приведены в спецификации типов данных схемы XML (XSD). Например:  
  
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
  
 Однако если строка преобразуется в тип **Boolean**, **Single** или **Double**, то возвращаемый тип .NET Framework не совпадает с типом, который возвращается при использовании класса **System.Convert**.  
  
## <a name="string-to-boolean"></a>Преобразование строки в тип Boolean  
 В следующей таблице показано, какие типы создаются для заданных входных строк при преобразовании строки в значение **Boolean** с помощью метода **ToBoolean**.  
  
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
  
 Обе записи обрабатываются следующим кодом, где **bvalue** имеет значение **System.Boolean.True**.  
  
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
 В следующей таблице показано, какие типы создаются для заданных входных строк при преобразовании строки в значение **Single** с помощью метода **ToSingle**.  
  
|Допустимый строковый входной параметр|Выходной тип .NET Framework|  
|----------------------------------|--------------------------------|  
|"INF"|Single.PositiveInfinity|  
|"-INF"|Single.NegativeInfinity|  
  
## <a name="string-to-double"></a>Преобразование строки в тип Double  
 В следующей таблице показано, какие типы создаются для заданных входных строк при преобразовании строки в значение **Double** с помощью метода **ToDouble**.  
  
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
  
## <a name="see-also"></a>См. также:

- [Преобразование типов XML-данных](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)
- [Преобразование типов .NET Framework в строки](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
