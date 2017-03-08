---
title: "Строки настраиваемых форматов даты и времени"
description: "Строки настраиваемых форматов даты и времени"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/25/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 45f286f5-92c9-4150-957c-fa6d394bc29b
translationtype: Human Translation
ms.sourcegitcommit: 28625def4199a660fe0ea04ab75f4f65d2e0c9c4
ms.openlocfilehash: 285e4bfd6a53d576ce4538b09a2561065c93e399
ms.lasthandoff: 02/23/2017

---

# <a name="custom-date-and-time-format-strings"></a>Строки настраиваемых форматов даты и времени

Строки форматов даты и времени определяют текстовое представление значений [DateTime](xref:System.DateTime) и [DateTimeOffset](xref:System.DateTimeOffset), получаемое после операции форматирования. Также они могут определять представление значения даты и времени, необходимое при операции синтаксического анализа для успешного преобразования строки в дату и время. Строка настраиваемого формата состоит из одного или нескольких настраиваемых описателей формата даты и времени. Любая строка, не являющаяся [строкой стандартного формата даты и времени](standard-datetime.md), воспринимается как строка настраиваемого формата даты и времени. 

Строки настраиваемого формата даты и времени могут использоваться как со значением [DateTime](xref:System.DateTime), так и со значением [DateTimeOffset](xref:System.DateTimeOffset).

В операциях форматирования пользовательские строки формата даты и времени можно использовать с методом `ToString` экземпляра даты и времени или с методом, поддерживающим составное форматирование. В следующем примере демонстрируются оба варианта использования. 

```csharp
DateTime thisDate1 = new DateTime(2011, 6, 10);
Console.WriteLine("Today is " + thisDate1.ToString("MMMM dd, yyyy") + ".");

DateTimeOffset thisDate2 = new DateTimeOffset(2011, 6, 10, 15, 24, 16, 
                                              TimeSpan.Zero);
Console.WriteLine("The current date and time: {0:MM/dd/yy H:mm:ss zzz}", 
                   thisDate2); 
// The example displays the following output:
//    Today is June 10, 2011.
//    The current date and time: 06/10/11 15:24:16 +00:00
```

```vb
Dim thisDate1 As Date = #6/10/2011#
Console.WriteLine("Today is " + thisDate1.ToString("MMMM dd, yyyy") + ".")

Dim thisDate2 As New DateTimeOffset(2011, 6, 10, 15, 24, 16, TimeSpan.Zero)
Console.WriteLine("The current date and time: {0:MM/dd/yy H:mm:ss zzz}", 
                   thisDate2) 
' The example displays the following output:
'    Today is June 10, 2011.
'    The current date and time: 06/10/11 15:24:16 +00:00
```

В операциях синтаксического анализа пользовательские строки формата даты и времени можно использовать с методами [DateTime.ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)), [DateTime.TryParseExact](xref:System.DateTime.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTime@)), [DateTimeOffset.ParseExact](xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)) и [DateTimeOffset.TryParseExact](xref:System.DateTimeOffset.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTimeOffset@)). Чтобы операция синтаксического анализа прошла успешно, эти методы требуют, чтобы входная строка строго соответствовала конкретному шаблону. В следующем примере демонстрируется вызов метода [DateTimeOffset.ParseExact(String, String, IFormatProvider)](xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)) для анализа даты, которая должна включать в себя указание дня, месяца и года из двух цифр.

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      string[] dateValues = { "30-12-2011", "12-30-2011", 
                              "30-12-11", "12-30-11" };
      string pattern = "MM-dd-yy";
      DateTime parsedDate;

      foreach (var dateValue in dateValues) {
         if (DateTime.TryParseExact(dateValue, pattern, null, 
                                   DateTimeStyles.None, out parsedDate))
            Console.WriteLine("Converted '{0}' to {1:d}.", 
                              dateValue, parsedDate);
         else
            Console.WriteLine("Unable to convert '{0}' to a date and time.", 
                              dateValue);
      }
   }
}
// The example displays the following output:
//    Unable to convert '30-12-2011' to a date and time.
//    Unable to convert '12-30-2011' to a date and time.
//    Unable to convert '30-12-11' to a date and time.
//    Converted '12-30-11' to 12/30/2011.
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim dateValues() As String = { "30-12-2011", "12-30-2011", 
                                      "30-12-11", "12-30-11" }
      Dim pattern As String = "MM-dd-yy"
      Dim parsedDate As Date

      For Each dateValue As String In dateValues
         If DateTime.TryParseExact(dateValue, pattern, Nothing, 
                                   DateTimeStyles.None, parsedDate) Then
            Console.WriteLine("Converted '{0}' to {1:d}.", 
                              dateValue, parsedDate)
         Else
            Console.WriteLine("Unable to convert '{0}' to a date and time.", 
                              dateValue)
         End If                                                         
      Next
   End Sub
End Module
' The example displays the following output:
'    Unable to convert '30-12-2011' to a date and time.
'    Unable to convert '12-30-2011' to a date and time.
'    Unable to convert '30-12-11' to a date and time.
'    Converted '12-30-11' to 12/30/2011.
```

В следующей таблице приведены настраиваемые описатели формата даты и времени с примерами строк, формируемых каждым описателем формата. По умолчанию результирующие строки отражают соглашения о форматировании для языка и региональных параметров en-US. Если конкретный описатель формата создает локализованную строку, то в примере также указываются язык и региональные параметры, для которых применяется полученная строка. Дополнительные сведения об использовании настраиваемых строк формата даты и времени см. в подразделе Примечания.

Описатель формата | Описание | Примеры
---------------- | ----------- | --------
"d" | День месяца, в диапазоне от 1 до 31. | `2019-06-01T13:45:30 -> 1`; `2019-06-15T13:45:30 -> 15`
"dd" | День месяца, в диапазоне от 01 до 31. | `2019-06-01T13:45:30 -> 1`; `2019-06-15T13:45:30 -> 15`
"ddd" | Сокращенное название дня недели. | `2019-06-15T13:45:30 -> Mon (en-US)`; `2019-06-15T13:45:30 -> Пн (ru-RU)`; `2019-06-15T13:45:30 -> lun. (fr-FR)`
"dddd" | Полное название дня недели. | `2019-06-15T13:45:30 -> Monday (en-US)`; `2019-06-15T13:45:30 -> понедельник (ru-RU)`; `2019-06-15T13:45:30 -> lundi (fr-FR)`
"f" | Десятые доли секунды в значении даты и времени. | `2019-06-15T13:45:30.6170000 -> 6`; `2019-06-15T13:45:30.05 -> 0` 
"ff" | Сотые доли секунды в значении даты и времени. | `2019-06-15T13:45:30.6170000 -> 61`; `2019-06-15T13:45:30.0050000 -> 00`
"fff" | Тысячные доли секунды в значении даты и времени. | `6/15/2019 13:45:30.617 -> 617`; `6/15/2019 13:45:30.0005 -> 000`
"ffff" | Десятитысячные доли секунды в значении даты и времени. | `2019-06-15T13:45:30.6175000 -> 6175`; `2019-06-15T13:45:30.0000500 -> 0000`
"fffff" | Стотысячные доли секунды в значении даты и времени. | `2019-06-15T13:45:30.6175400 -> 61754`; `6/15/2019 13:45:30.000005 -> 00000`
"ffffff" | Миллионные доли секунды в значении даты и времени. | `2019-06-15T13:45:30.6175420 -> 617542`; `2019-06-15T13:45:30.0000005 -> 000000`
"fffffff" | Десятимиллионные доли секунды в значении даты и времени. | `2019-06-15T13:45:30.6175425 -> 6175425`;`2019-06-15T13:45:30.0001150 -> 0001150`
"F" | Если ненулевое значение, то десятые доли секунды в значении даты и времени. | `2019-06-15T13:45:30.6170000 -> 6`; `2019-06-15T13:45:30.0500000 -> (no output)`
"FF" | Если ненулевое значение, то сотые доли секунды в значении даты и времени. | `2019-06-15T13:45:30.6170000 -> 61`; `2019-06-15T13:45:30.0050000 -> (no output)`
"FFF" | Если ненулевое значение, то тысячные доли секунды в значении даты и времени. | `2019-06-15T13:45:30.6170000 -> 617`; `2019-06-15T13:45:30.0005000 -> (no output)`
"FFFF" | Если ненулевое значение, то десятитысячные доли секунды в значении даты и времени. | `2019-06-15T13:45:30.5275000 -> 5275`; `2019-06-15T13:45:30.0000500 -> (no output)`
"FFFFF" | Если ненулевое значение, то стотысячные доли секунды в значении даты и времени. | `2019-06-15T13:45:30.6175400 -> 61754`; `2019-06-15T13:45:30.0000050 -> (no output)`
"FFFFFF" | Если ненулевое значение, то миллионные доли секунды в значении даты и времени. | `2019-06-15T13:45:30.6175420 -> 617542`; `2019-06-15T13:45:30.0000005 -> (no output)`
"FFFFFFF" | Если ненулевое значение, то десятимиллионные доли секунды в значении даты и времени. | `2019-06-15T13:45:30.6175425 -> 6175425`; `2019-06-15T13:45:30.0001150 -> 000115`
"g", "gg" | Период или эра. | `2019-06-15T13:45:30.6170000 -> A.D.`
"h" | Час в 12-часовом формате от 1 до 12. | `2019-06-15T01:45:30 -> 1`; `2019-06-15T13:45:30 -> 1`
"чч" | Час в 12-часовом формате от 01 до 12. | `2019-06-15T01:45:30 -> 01`; `2019-06-15T13:45:30 -> 01`
"H" | Час в 24-часовом формате от 0 до 23. | `2019-06-15T01:45:30 -> 1`; `2019-06-15T13:45:30 -> 13`
"HH" | Час в 24-часовом формате от 00 до 23. | `2019-06-15T01:45:30 -> 01`; `2019-06-15T13:45:30 -> 13`
"K" | Данные о часовом поясе. | Со значениями [DateTime](xref:System.DateTime): `2019-06-15T13:45:30, Kind Unspecified ->`; `2019-06-15T13:45:30, Kind Utc -> Z`; `2019-06-15T13:45:30, Kind Local -> -07:00 (depends on local computer settings)`; со значениями [DateTimeOffset](xref:System.DateTimeOffset): `2019-06-15T01:45:30-07:00 --> -07:00`; `2019-06-15T08:45:30+00:00 --> +00:00`
"m" | Минуты, в диапазоне от 0 до 59. | `2019-06-15T01:09:30 -> 9`; `2019-06-15T13:29:30 -> 29`
"mm" | Минуты, в диапазоне от 00 до 59. | `2019-06-15T01:09:30 -> 09`; `2019-06-15T01:45:30 -> 45`
"M" | Месяц, в диапазоне от 1 до 12. | `2019-06-15T13:45:30 -> 6`
"MM" | Месяц, в диапазоне от 01 до 12. | `2019-06-15T13:45:30 -> 06`
"MMM" | Сокращенное название месяца. | `2019-06-15T13:45:30 -> Jun (en-US)`; `2019-06-15T13:45:30 -> juin (fr-FR)`; `2019-06-15T13:45:30 -> Jun (zu-ZA)`
"MMMM" | Полное название месяца. | `2019-06-15T13:45:30 -> June (en-US)`; `2019-06-15T13:45:30 -> juni (da-DK)`; `2019-06-15T13:45:30 -> uJuni (zu-ZA)`
"s" | Секунды, в диапазоне от 0 до 59. | `2019-06-15T13:45:09 -> 9`
"сс" | Секунды, в диапазоне от 00 до 59. | `2019-06-15T13:45:09 -> 09`
"t" | Первый символ указателя AM/PM (до полудня/после полудня). | `2019-06-15T13:45:30 -> P (en-US)`; `2019-06-15T13:45:30 -> 午 (ja-JP)`; `2019-06-15T13:45:30 -> (fr-FR)`
"tt" | Указатель AM/PM (до полудня/после полудня). | `2019-06-15T13:45:30 -> PM (en-US)`; `2019-06-15T13:45:30 -> 午後 (ja-JP)`; `2019-06-15T13:45:30 -> (fr-FR)`
"y" | Год, в диапазоне от 0 до 99. | `0001-01-01T00:00:00 -> 1`; `0900-01-01T00:00:00 -> 0`; `1900-01-01T00:00:00 -> 0`; `2019-06-15T13:45:30 -> 9`; `2019-06-15T13:45:30 -> 19`
"yy" | Год, в диапазоне от 00 до 99. | `0001-01-01T00:00:00 -> 01`; `0900-01-01T00:00:00 -> 00`; `1900-01-01T00:00:00 -> 00`; `2019-06-15T13:45:30 -> 19`
"yyy" | Год в виде как минимум трех цифр. | `0001-01-01T00:00:00 -> 001`; `0900-01-01T00:00:00 -> 900`; `1900-01-01T00:00:00 -> 1900`; `2019-06-15T13:45:30 -> 2019`
"yyyy" | Год в виде четырехзначного числа. | `0001-01-01T00:00:00 -> 0001`; `0900-01-01T00:00:00 -> 0900`; `1900-01-01T00:00:00 -> 1900`; `2019-06-15T13:45:30 -> 2019`
"yyyyy" | Год в виде пятизначного числа. | `0001-01-01T00:00:00 -> 00001`; `2019-06-15T13:45:30 -> 02019`
"z" | Часовой сдвиг от времени в формате UTC (универсального времени), без нулей в начале. | `2019-06-15T13:45:30-07:00 -> -7`
"zz" | Часовой сдвиг от времени в формате UTC (универсального времени) с нулями в начале для значений из одной цифры. | `2019-06-15T13:45:30-07:00 -> -07`
"zzz" | Сдвиг в часах и минутах от времени в формате UTC (универсального времени). | `2019-06-15T13:45:30-07:00 -> -07:00`
":" | Разделитель компонентов времени. | `2019-06-15T13:45:30 -> : (en-US)`; `2019-06-15T13:45:30 -> . (it-IT)`; `2019-06-15T13:45:30 -> : (ja-JP)`
"/" | Разделитель компонентов даты. | `2019-06-15T13:45:30 -> / (en-US)`; `2019-06-15T13:45:30 -> - (ar-DZ)`; `2019-06-15T13:45:30 -> . (tr-TR)`
"строка", 'строка' | Буквенный разделитель строк. | `2019-06-15T13:45:30 ("arr:" h:m t) -> arr: 1:45 P`; `2019-06-15T13:45:30 ('arr:' h:m t) -> arr: 1:45 P`
% | Задает следующий символ в качестве настраиваемого описателя формата. | `2019-06-15T13:45:30 (%h) -> 1`
\ | Escape-символ. | `2019-06-15T13:45:30 (h \h) -> 1 h`
Любой другой знак | Символ копируется в результирующую строку без изменений. | `2019-06-15T01:45:30 (arr hh:mm t) -> arr 01:45 A`

В следующих подразделах предоставляются дополнительные сведения о всех настраиваемых описателях формата даты и времени. Если не указано иное, каждый настраиваемый описатель формата даты и времени формирует одинаковое строковое представление независимо от того, используется ли он со значением [DateTime](xref:System.DateTime) или со значением [DateTimeOffset](xref:System.DateTimeOffset). 

## <a name="the-d-custom-format-specifier"></a>Настраиваемый описатель формата "d"

Настраиваемый описатель формата "d" представляет день месяца в виде числа в диапазоне от 1 до 31. День в виде одной цифры форматируется без нуля в начале. 

Если описатель формата "d" используется без других настраиваемых описателей формата, то он интерпретируется как описатель "d" стандартного формата даты и времени. Дополнительные сведения об использовании единичных описателей форматов см. в подразделе [Использование единичных настраиваемых описателей форматов](#using-single-custom-format-specifiers) ниже.

В следующем примере настраиваемый описатель формата "d" используется в нескольких строках формата. 

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15); 

Console.WriteLine(date1.ToString("d, M", 
                  CultureInfo.InvariantCulture)); 
// Displays 29, 8

Console.WriteLine(date1.ToString("d MMMM", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays 29 August
Console.WriteLine(date1.ToString("d MMMM", 
                  CultureInfo.CreateSpecificCulture("es-MX")));
// Displays 29 agosto  
```

```vb
Dim date1 As Date = #08/29/2008 7:27:15PM#

Console.WriteLine(date1.ToString("d, M", _
                  CultureInfo.InvariantCulture)) 
' Displays 29, 8

Console.WriteLine(date1.ToString("d MMMM", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays 29 August
Console.WriteLine(date1.ToString("d MMMM", _
                  CultureInfo.CreateSpecificCulture("es-MX")))
' Displays 29 agosto 
```

## <a name="the-dd-custom-format-specifier"></a>Настраиваемый описатель формата "dd"

Настраиваемый описатель формата "dd" представляет день месяца в виде числа в диапазоне от 01 до 31. День в виде одной цифры форматируется с нулем в начале. 

В следующем примере настраиваемый описатель формата "dd" используется в строке настраиваемого формата.

```csharp
DateTime date1 = new DateTime(2008, 1, 2, 6, 30, 15);

Console.WriteLine(date1.ToString("dd, MM", 
                  CultureInfo.InvariantCulture)); 
// 02, 01
```

```vb
Dim date1 As Date = #1/2/2008 6:30:15AM#

Console.WriteLine(date1.ToString("dd, MM", _
                  CultureInfo.InvariantCulture)) 
' 02, 01
```

## <a name="the-ddd-custom-format-specifier"></a>Настраиваемый описатель формата "ddd"

Настраиваемый описатель формата "ddd" представляет сокращенное название дня недели. Локализованное сокращенное название дня недели извлекается из свойства [DateTimeFormatInfo.AbbreviatedDayNames](xref:System.Globalization.DateTimeFormatInfo.AbbreviatedDayNames) текущей или заданной среды языка и региональных параметров. 

В следующем примере описатель настраиваемый описатель формата "ddd" используется в строке настраиваемого формата. 

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15);

Console.WriteLine(date1.ToString("ddd d MMM", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays Fri 29 Aug
Console.WriteLine(date1.ToString("ddd d MMM", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));
// Displays ven. 29 août    
```

```vb
Dim date1 As Date = #08/29/2008 7:27:15PM#

Console.WriteLine(date1.ToString("ddd d MMM", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays Fri 29 Aug
Console.WriteLine(date1.ToString("ddd d MMM", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))
' Displays ven. 29 août
```

## <a name="the-dddd-custom-format-specifier"></a>Настраиваемый описатель формата "dddd"

Настраиваемый описатель формата "dddd" (плюс любое количество дополнительных описателей "d") представляет полное название дня недели. Локализованное название дня недели извлекается из свойства [DateTimeFormatInfo.DayName](xref:System.Globalization.DateTimeFormatInfo.DayNames) текущей или заданной среды языка и региональных параметров. 

В следующем примере настраиваемый описатель формата "dddd" используется в строке настраиваемого формата.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15);

Console.WriteLine(date1.ToString("dddd dd MMMM", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays Friday 29 August
Console.WriteLine(date1.ToString("dddd dd MMMM", 
                  CultureInfo.CreateSpecificCulture("it-IT")));
// Displays venerdì 29 agosto    
```

```vb
Dim date1 As Date = #08/29/2008 7:27:15PM#

Console.WriteLine(date1.ToString("dddd dd MMMM", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays Friday 29 August
Console.WriteLine(date1.ToString("dddd dd MMMM", _
                  CultureInfo.CreateSpecificCulture("it-IT")))
' Displays venerdì 29 agosto                                          
```

## <a name="the-f-custom-format-specifier"></a>Настраиваемый описатель формата "f"

Настраиваемый описатель формата "f" представляет наиболее значимую цифру секунд, то есть десятые доли секунды в значении даты и времени.

Если описатель формата "f" используется без других описателей формата, то он интерпретируется как описатель "f" стандартного формата даты и времени. Дополнительные сведения об использовании единичных описателей форматов см. в подразделе [Использование единичных настраиваемых описателей форматов](#using-single-custom-format-specifiers) ниже.

При использовании описателей формата "f" в составе строки формата, передаваемой методу [DateTime.ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)), [DateTime.TryParseExact](xref:System.DateTime.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTime@)), [DateTimeOffset.ParseExact](xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)) или [DateTimeOffset.TryParseExact](xref:System.DateTimeOffset.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTimeOffset@)), количество описателей формата "f" указывает на количество наиболее значимых цифр секунд, которые должны присутствовать для обеспечения успешного анализа строки.

В следующем примере настраиваемый описатель формата "f" используется в строке настраиваемого формата.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15, 18);
CultureInfo ci = CultureInfo.InvariantCulture;

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci));
// Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci));
// Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci));
// Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci));
// Displays 07:27:15.018
```

```vb
Dim date1 As New Date(2008, 8, 29, 19, 27, 15, 018)
Dim ci As CultureInfo = CultureInfo.InvariantCulture

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci))
' Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci))
' Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci))
' Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci))
' Displays 07:27:15.018
```

## <a name="the-ff-custom-format-specifier"></a>Настраиваемый описатель формата "ff"

Настраиваемый описатель формата "ff" представляет две наиболее значимые цифры секунд, то есть сотые доли секунды в значении даты и времени. 

В следующем примере настраиваемый описатель формата "ff" используется в строке настраиваемого формата.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15, 18);
CultureInfo ci = CultureInfo.InvariantCulture;

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci));
// Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci));
// Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci));
// Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci));
// Displays 07:27:15.018
```

```vb
Dim date1 As New Date(2008, 8, 29, 19, 27, 15, 018)
Dim ci As CultureInfo = CultureInfo.InvariantCulture

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci))
' Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci))
' Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci))
' Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci))
' Displays 07:27:15.018
```

## <a name="the-fff-custom-format-specifier"></a>Настраиваемый описатель формата "fff"

Настраиваемый описатель формата "fff" представляет три наиболее значимые цифры секунд, то есть миллисекунды в значении даты и времени. 

В следующем примере настраиваемый описатель формата "fff" используется в строке настраиваемого формата.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15, 18);
CultureInfo ci = CultureInfo.InvariantCulture;

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci));
// Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci));
// Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci));
// Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci));
// Displays 07:27:15.018
```

```vb
Dim date1 As New Date(2008, 8, 29, 19, 27, 15, 018)
Dim ci As CultureInfo = CultureInfo.InvariantCulture

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci))
' Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci))
' Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci))
' Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci))
' Displays 07:27:15.018
```

## <a name="the-ffff-custom-format-specifier"></a>Настраиваемый описатель формата "ffff"

Настраиваемый описатель формата "ffff" представляет четыре наиболее значимые цифры секунд, то есть десятитысячные доли секунды в значении даты и времени.

Хотя и существует возможность отображения десятитысячных долей секунды в значении времени, это значение может не иметь особого смысла. Точность значений даты и времени зависит от разрешения системных часов.

## <a name="the-fffff-custom-format-specifier"></a>Настраиваемый описатель формата "fffff"

Настраиваемый описатель формата "FFFFF" представляет пять наиболее значимых цифр секунд, то есть стотысячные доли секунды в значении даты и времени.

Хотя и существует возможность отображения стотысячных долей секунды в значении времени, это значение может не иметь особого смысла. Точность значений даты и времени зависит от разрешения системных часов. 

## <a name="the-ffffff-custom-format-specifier"></a>Настраиваемый описатель формата "ffffff"

Настраиваемый описатель формата "fffff" представляет шесть наиболее значимых цифр секунд, то есть миллионные доли секунды в значении даты и времени.

Хотя и существует возможность отображения миллионных долей секунды, это значение может не иметь особого смысла. Точность значений даты и времени зависит от разрешения системных часов. 

## <a name="the-fffffff-custom-format-specifier"></a>Настраиваемый описатель формата "fffffff"

Настраиваемый описатель формата "ffffff" представляет семь наиболее значимых цифр секунд, то есть десятимиллионные доли секунды в значении даты и времени.

Хотя и существует возможность отображения десятимиллионных долей секунды, это значение может не иметь особого смысла. Точность значений даты и времени зависит от разрешения системных часов. 

## <a name="the-f-custom-format-specifier"></a>Настраиваемый описатель формата "F"

Настраиваемый описатель формата "F" представляет наиболее значимую цифру секунд, то есть десятые доли секунды в значении даты и времени. Если цифра равна нулю, то ничего не отображается. 

Если описатель формата "F" используется без других описателей формата, то он интерпретируется как описатель "F" стандартного формата даты и времени. Дополнительные сведения об использовании единичных описателей форматов см. в подразделе [Использование единичных настраиваемых описателей форматов](#using-single-custom-format-specifiers) ниже.

Число описателей формата "F", используемых с методом [DateTime.ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)), [DateTime.TryParseExact](xref:System.DateTime.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTime@)), [DateTimeOffset.ParseExact](xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)) или [DateTimeOffset.TryParseExact](xref:System.DateTimeOffset.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTimeOffset@)), задает максимальное количество наиболее значимых цифр секунд, которые должны присутствовать для успешного анализа строки.

В следующем примере настраиваемый описатель формата "F" используется в строке настраиваемого формата.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15, 18);
CultureInfo ci = CultureInfo.InvariantCulture;

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci));
// Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci));
// Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci));
// Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci));
// Displays 07:27:15.018
```

```vb
Dim date1 As New Date(2008, 8, 29, 19, 27, 15, 018)
Dim ci As CultureInfo = CultureInfo.InvariantCulture

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci))
' Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci))
' Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci))
' Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci))
' Displays 07:27:15.018
```

## <a name="the-ff-custom-format-specifier"></a>Настраиваемый описатель формата "FF"

Настраиваемый описатель формата "FF" представляет две наиболее значимые цифры секунд, то есть сотые доли секунды в значении даты и времени. При этом нули в конце или два нуля не отображаются. 

В следующем примере настраиваемый описатель формата "FF" используется в строке настраиваемого формата.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15, 18);
CultureInfo ci = CultureInfo.InvariantCulture;

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci));
// Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci));
// Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci));
// Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci));
// Displays 07:27:15.018
```

```vb
Dim date1 As New Date(2008, 8, 29, 19, 27, 15, 018)
Dim ci As CultureInfo = CultureInfo.InvariantCulture

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci))
' Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci))
' Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci))
' Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci))
' Displays 07:27:15.018
```

## <a name="the-fff-custom-format-specifier"></a>Настраиваемый описатель формата "FFF"

Настраиваемый описатель формата "FFF" представляет три наиболее значимые цифры секунд, то есть миллисекунды в значении даты и времени. При этом нули в конце или три нуля не отображаются. 

В следующем примере настраиваемый описатель формата "FFF" используется в строке настраиваемого формата.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15, 18);
CultureInfo ci = CultureInfo.InvariantCulture;

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci));
// Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci));
// Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci));
// Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci));
// Displays 07:27:15.018
````

```vb
Dim date1 As New Date(2008, 8, 29, 19, 27, 15, 018)
Dim ci As CultureInfo = CultureInfo.InvariantCulture

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci))
' Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci))
' Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci))
' Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci))
' Displays 07:27:15.018
```

## <a name="the-ffff-custom-format-specifier"></a>Настраиваемый описатель формата "FFFF"

Настраиваемый описатель формата "FFFF" представляет четыре наиболее значимые цифры секунд, то есть десятитысячные доли секунды в значении даты и времени. При этом нули в конце или четыре нуля не отображаются.

Хотя и существует возможность отображения десятитысячных долей секунды в значении времени, это значение может не иметь особого смысла. Точность значений даты и времени зависит от разрешения системных часов.

## <a name="the-fffff-custom-format-specifier"></a>Настраиваемый описатель формата "FFFFF"

Настраиваемый описатель формата "FFFFF" представляет пять наиболее значимых цифр секунд, то есть стотысячные доли секунды в значении даты и времени. При этом нули в конце или пять нулей не отображаются.

Хотя и существует возможность отображения стотысячных долей секунды в значении времени, это значение может не иметь особого смысла. Точность значений даты и времени зависит от разрешения системных часов.

## <a name="the-ffffff-custom-format-specifier"></a>Настраиваемый описатель формата "FFFFFF"

Настраиваемый описатель формата "FFFFFF" представляет шесть наиболее значимых цифр секунд, то есть миллионные доли секунды в значении даты и времени. При этом нули в конце или шесть нулей не отображаются.

Хотя и существует возможность отображения миллионных долей секунды, это значение может не иметь особого смысла. Точность значений даты и времени зависит от разрешения системных часов.

## <a name="the-fffffff-custom-format-specifier"></a>Настраиваемый описатель формата "FFFFFFF"

Настраиваемый описатель формата "FFFFFFF" представляет семь наиболее значимых цифр секунд, то есть десятимиллионные доли секунды в значении даты и времени. При этом нули в конце или семь нулей не отображаются.

Хотя и существует возможность отображения десятимиллионных долей секунды, это значение может не иметь особого смысла. Точность значений даты и времени зависит от разрешения системных часов.

## <a name="the-g-or-gg-custom-format-specifier"></a>Настраиваемый описатель формата "g" или "gg"

Настраиваемые описатели формата "g" и "gg" (плюс любое число дополнительных описателей "g") представляют период или эру, например A.D. (н. э.). Операция форматирования игнорирует этот описатель, если форматируемой дате не сопоставлена строка периода или эры. 

Если описатель формата "g" используется без других настраиваемых описателей формата, то он интерпретируется как описатель "g" стандартного формата даты и времени. Дополнительные сведения об использовании единичных описателей форматов см. в подразделе [Использование единичных настраиваемых описателей форматов](#using-single-custom-format-specifiers) ниже.

В следующем примере настраиваемый описатель формата "g" используется в строке настраиваемого формата.

```csharp
DateTime date1 = new DateTime(70, 08, 04);

Console.WriteLine(date1.ToString("MM/dd/yyyy g", 
                  CultureInfo.InvariantCulture));
// Displays 08/04/0070 A.D.                        
Console.WriteLine(date1.ToString("MM/dd/yyyy g", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));                         
// Displays 08/04/0070 ap. J.-C.
```

```vb
Dim date1 As Date = #08/04/0070#

Console.WriteLine(date1.ToString("MM/dd/yyyy g", _
                  CultureInfo.InvariantCulture))
' Displays 08/04/0070 A.D.                        
Console.WriteLine(date1.ToString("MM/dd/yyyy g", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))                         
' Displays 08/04/0070 ap. J.-C.
```

## <a name="the-h-custom-format-specifier"></a>Настраиваемый описатель формата "h"

Настраиваемый описатель формата "h" представляет часы в виде числа в диапазоне от 1 до 12, то есть в 12-часовом формате, в котором полные часы отсчитываются от полуночи или от полудня. Час после полуночи неотличим от того же часа после полудня. Часы не округляются, и часы с одной цифрой форматируются без нуля в начале. Например, для времени 5:43 утра или вечера этот настраиваемый описатель формата выведет "5". 

Если описатель формата "h" используется без других настраиваемых описателей формата, то он интерпретируется как описатель стандартного формата даты и времени, и возникает исключение [FormatException](xref:System.FormatException). Дополнительные сведения об использовании единичных описателей форматов см. в подразделе [Использование единичных настраиваемых описателей форматов](#using-single-custom-format-specifiers) ниже.

В следующем примере настраиваемый описатель формата "h" используется в строке настраиваемого формата.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1 µ                        
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1.5 µ
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1 µ                        
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1.5 µ
```

## <a name="the-hh-custom-format-specifier"></a>Настраиваемый описатель формата "hh"

Настраиваемый описатель формата "hh" (плюс любое количество дополнительных описателей "h") представляет часы в виде числа в диапазоне от 01 до 12, то есть в 12-часовом формате, в котором полные часы отсчитываются от полуночи или от полудня. Час после полуночи неотличим от того же часа после полудня. Часы не округляются, и часы с одной цифрой форматируются с нулем в начале. Например, для времени 5:43 утра или вечера этот описатель формата выведет "05".

В следующем примере настраиваемый описатель формата "hh" используется в строке настраиваемого формата.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01 du.
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01.50 du.
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01 du.
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01.50 du.
```

## <a name="the-h-custom-format-specifier"></a>Настраиваемый описатель формата "H"

Настраиваемый описатель формата "H" представляет часы в виде числа в диапазоне от 0 до 23, то есть в 24-часовом формате, в котором полные часы отсчитываются от полуночи, начиная с 0. Часы с одной цифрой форматируются без нуля в начале. 

Если описатель формата "H" используется без других настраиваемых описателей формата, то он интерпретируется как описатель стандартного формата даты и времени, и возникает исключение [FormatException](xref:System.FormatException). Дополнительные сведения об использовании единичных описателей форматов см. в подразделе [Использование единичных настраиваемых описателей форматов](#using-single-custom-format-specifiers) ниже.

В следующем примере настраиваемый описатель формата "H" используется в строке настраиваемого формата.

```csharp
DateTime date1 = new DateTime(2008, 1, 1, 6, 9, 1);
Console.WriteLine(date1.ToString("H:mm:ss", 
                  CultureInfo.InvariantCulture));
// Displays 6:09:01 
```

```vb
Dim date1 As Date = #6:09:01AM#
Console.WriteLine(date1.ToString("H:mm:ss", _
                  CultureInfo.InvariantCulture))
' Displays 6:09:01 
```

## <a name="the-hh-custom-format-specifier"></a>Настраиваемый описатель формата "HH"

Настраиваемый описатель формата "HH" (плюс любое количество дополнительных описателей "H") представляет часы в виде числа в диапазоне от 00 до 23, то есть в 24-часовом формате, в котором полные часы отсчитываются от полуночи начиная с 0. Часы с одной цифрой форматируются с нулем в начале. 

В следующем примере настраиваемый описатель формата "HH" используется в строке настраиваемого формата.

```csharp
DateTime date1 = new DateTime(2008, 1, 1, 6, 9, 1);
Console.WriteLine(date1.ToString("HH:mm:ss", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01                        
```

```vb
Dim date1 As Date = #6:09:01AM#
Console.WriteLine(date1.ToString("HH:mm:ss", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01
```

## <a name="the-k-custom-format-specifier"></a>Настраиваемый описатель формата "K"

Настраиваемый описатель формата "K" представляет данные о часовом поясе значения даты и времени. При использовании этого описателя формата со значениями [DateTime](xref:System.DateTime) результирующая строка определяется значением свойства [DateTime.Kind](xref:System.DateTime.Kind). 
 
* Для местного часового пояса (свойства [DateTime.Kind](xref:System.DateTime.Kind) со значением [DateTimeKind.Local](xref:System.DateTimeKind.Local)) этот описатель равнозначен описателю "zzz" и формирует результирующую строку, содержащую локальное смещение от универсального времени (UTC), например "-07:00". 

* Для времени UTC (свойства [DateTime.Kind](xref:System.DateTime.Kind) со значением [DateTimeKind.Utc](xref:System.DateTimeKind.Utc)) результирующая строка содержит знак "Z", указывающий дату в формате UTC. 

* Для времени в неопределенном часовом поясе (времени, свойство [DateTime.Kind](xref:System.DateTime.Kind) которого имеет значение [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified)), результат равен [String.Empty](xref:System.String#System_String_Empty). 

Для значений [DateTimeOffset](xref:System.DateTimeOffset) описатель формата "K" равнозначен описателю формата "zz", который формирует результирующую строку, содержащую смещение значения от времени UTC в виде [DateTimeOffset](xref:System.DateTimeOffset). 

Если описатель формата "K" используется без других настраиваемых описателей формата, то он интерпретируется как описатель стандартного формата даты и времени, и возникает исключение [FormatException](xref:System.FormatException). Дополнительные сведения об использовании единичных описателей форматов см. в подразделе [Использование единичных настраиваемых описателей форматов](#using-single-custom-format-specifiers) ниже.

В следующем примере показаны строки, полученные с использованием спецификатора настраиваемого формата "K" с различными значениями [DateTime](xref:System.DateTime) и [DateTimeOffset](xref:System.DateTimeOffset) в тихоокеанском стандартном часовом поясе США.

```csharp
Console.WriteLine(DateTime.Now.ToString("%K"));
// Displays -07:00
Console.WriteLine(DateTime.UtcNow.ToString("%K"));
// Displays Z      
Console.WriteLine("'{0}'", 
                  DateTime.SpecifyKind(DateTime.Now, 
                       DateTimeKind.Unspecified).ToString("%K"));
// Displays ''      
Console.WriteLine(DateTimeOffset.Now.ToString("%K"));
// Displays -07:00
Console.WriteLine(DateTimeOffset.UtcNow.ToString("%K"));
// Displays +00:00
Console.WriteLine(new DateTimeOffset(2008, 5, 1, 6, 30, 0, 
                      new TimeSpan(5, 0, 0)).ToString("%K"));
// Displays +05:00  
```

```vb
Console.WriteLine(Date.Now.ToString("%K"))
' Displays -07:00
Console.WriteLine(Date.UtcNow.ToString("%K"))
' Displays Z      
Console.WriteLine("'{0}'", _
                  Date.SpecifyKind(Date.Now, _
                                   DateTimeKind.Unspecified). _
                  ToString("%K"))
' Displays ''      
Console.WriteLine(DateTimeOffset.Now.ToString("%K"))
' Displays -07:00
Console.WriteLine(DateTimeOffset.UtcNow.ToString("%K"))
' Displays +00:00
Console.WriteLine(New DateTimeOffset(2008, 5, 1, 6, 30, 0, _
                                     New TimeSpan(5, 0, 0)). _
                  ToString("%K"))
' Displays +05:00 
```

## <a name="the-m-custom-format-specifier"></a>Настраиваемый описатель формата "m"

Настраиваемый описатель формата "m" представляет минуты в виде числа в диапазоне от 0 до 59. Это число целых минут, прошедших с последнего часа. Минуты с одной цифрой форматируются без нуля в начале. 

Если описатель формата "m" используется без других настраиваемых описателей формата, то он интерпретируется как описатель "m" стандартного формата даты и времени. Дополнительные сведения об использовании единичных описателей форматов см. в подразделе [Использование единичных настраиваемых описателей форматов](#using-single-custom-format-specifiers) ниже. 

В следующем примере настраиваемый описатель формата "m" используется в строке настраиваемого формата.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1 µ                        
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1.5 µ
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1 µ                        
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1.5 µ
```

## <a name="the-mm-custom-format-specifier"></a>Настраиваемый описатель формата "mm"

Настраиваемый описатель формата "mm" (плюс любое число дополнительных описателей "m") представляет минуты в виде числа в диапазоне от 00 до 59. Это число целых минут, прошедших с последнего часа. Минуты с одной цифрой форматируются с нулем в начале. 

В следующем примере настраиваемый описатель формата "mm" используется в строке настраиваемого формата.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01 du.
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01.50 du.
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01 du.
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01.50 du.
```

## <a name="the-m-custom-format-specifier"></a>Настраиваемый описатель формата "M"

Описатель настраиваемого формата "М" представляет месяц как число от "1" до "12" (или от "1" до "13" для календарей, в которых 13 месяцев). Месяц, номер которого представляет одну цифру, форматируется без нуля в начале. 

Если описатель формата "M" используется без других настраиваемых описателей формата, то он интерпретируется как описатель "M" стандартного формата даты и времени. Дополнительные сведения об использовании единичных описателей форматов см. в подразделе [Использование единичных настраиваемых описателей форматов](#using-single-custom-format-specifiers) ниже.

В следующем примере настраиваемый описатель формата "M" используется в строке настраиваемого формата.

```csharp
DateTime date1 = new DateTime(2008, 8, 18);
Console.WriteLine(date1.ToString("(M) MMM, MMMM", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays (8) Aug, August
Console.WriteLine(date1.ToString("(M) MMM, MMMM", 
                  CultureInfo.CreateSpecificCulture("nl-NL")));                       
// Displays (8) aug, augustus
Console.WriteLine(date1.ToString("(M) MMM, MMMM", 
                  CultureInfo.CreateSpecificCulture("lv-LV")));                        
// Displays (8) Aug, augusts
```

```vb
Dim date1 As Date = #8/18/2008#
Console.WriteLine(date1.ToString("(M) MMM, MMMM", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays (8) Aug, August
Console.WriteLine(date1.ToString("(M) MMM, MMMM", _
                  CultureInfo.CreateSpecificCulture("nl-NL")))                        
' Displays (8) aug, augustus
Console.WriteLine(date1.ToString("(M) MMM, MMMM", _
                  CultureInfo.CreateSpecificCulture("lv-LV")))                        
' Displays (8) Aug, augusts 
```

## <a name="the-mm-custom-format-specifier"></a>Настраиваемый описатель формата "MM"

Описатель настраиваемого формата "ММ" представляет месяц как число от "01" до "12" (или от "1" до "13" для календарей, в которых 13 месяцев). Месяц, номер которого представляет одну цифру, форматируется с нулем в начале. 

В следующем примере настраиваемый описатель формата "MM" используется в строке настраиваемого формата.

```csharp
DateTime date1 = new DateTime(2008, 1, 2, 6, 30, 15);

Console.WriteLine(date1.ToString("dd, MM", 
                  CultureInfo.InvariantCulture)); 
// 02, 01
```

```vb
Dim date1 As Date = #1/2/2008 6:30:15AM#

Console.WriteLine(date1.ToString("dd, MM", _
                  CultureInfo.InvariantCulture)) 
' 02, 01
```

## <a name="the-mmm-custom-format-specifier"></a>Настраиваемый описатель формата "MMM"

Настраиваемый описатель формата "MMM" представляет сокращенное название месяца. Локализованное сокращенное название месяца извлекается из свойства [DateTimeFormatInfo.AbbreviatedMonthNames](xref:System.Globalization.DateTimeFormatInfo.AbbreviatedMonthNames) текущей или заданной среды языка и региональных параметров.

В следующем примере настраиваемый описатель формата "MMM" используется в строке настраиваемого формата.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15);

Console.WriteLine(date1.ToString("ddd d MMM", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays Fri 29 Aug
Console.WriteLine(date1.ToString("ddd d MMM", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));
// Displays ven. 29 août
```

```vb
Dim date1 As Date = #08/29/2008 7:27:15PM#

Console.WriteLine(date1.ToString("ddd d MMM", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays Fri 29 Aug
Console.WriteLine(date1.ToString("ddd d MMM", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))
' Displays ven. 29 août
```

## <a name="the-mmmm-custom-format-specifier"></a>Настраиваемый описатель формата "MMMM"

Настраиваемый описатель формата "MMMM" представляет полное название месяца. Локализованное название месяца извлекается из свойства [DateTimeFormatInfo.MonthName](xref:System.Globalization.DateTimeFormatInfo.MonthNames) текущей или заданной среды языка и региональных параметров. 

В следующем примере настраиваемый описатель формата "MMMM" используется в строке настраиваемого формата.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15);

Console.WriteLine(date1.ToString("dddd dd MMMM", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays Friday 29 August
Console.WriteLine(date1.ToString("dddd dd MMMM", 
                  CultureInfo.CreateSpecificCulture("it-IT")));
// Displays venerdì 29 agosto 
```

```vb
Dim date1 As Date = #08/29/2008 7:27:15PM#

Console.WriteLine(date1.ToString("dddd dd MMMM", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays Friday 29 August
Console.WriteLine(date1.ToString("dddd dd MMMM", _
                  CultureInfo.CreateSpecificCulture("it-IT")))
' Displays venerdì 29 agosto  
```

## <a name="the-s-custom-format-specifier"></a>Настраиваемый описатель формата "s"

Настраиваемый описатель формата "s" представляет секунды в виде числа в диапазоне от 0 до 59. Это число целых секунд, прошедших с последней полной минуты. Секунды с одной цифрой форматируются без нуля в начале. 

Если описатель формата "s" используется без других настраиваемых описателей формата, то он интерпретируется как описатель "s" стандартного формата даты и времени. Дополнительные сведения об использовании единичных описателей форматов см. в подразделе [Использование единичных настраиваемых описателей форматов](#using-single-custom-format-specifiers) ниже. 

В следующем примере настраиваемый описатель формата "s" используется в строке настраиваемого формата.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1 µ                        
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1.5 µ
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1 µ                        
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1.5 µ
```

## <a name="the-ss-custom-format-specifier"></a>Настраиваемый описатель формата "ss"

Настраиваемый описатель формата "ss" (плюс любое число дополнительных описателей "s") представляет секунды в виде числа в диапазоне от 00 до 59. Это число целых секунд, прошедших с последней полной минуты. Секунды с одной цифрой форматируются с нулем в начале. 

В следующем примере настраиваемый описатель формата "ss" используется в строке настраиваемого формата.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01 du.
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01.50 du.
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01 du.
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01.50 du.
```

## <a name="the-t-custom-format-specifier"></a>Настраиваемый описатель формата "t"

Настраиваемый описатель формата "t" представляет первый символ указателя AM/PM (до полудня/после полудня). Соответствующий локализованный указатель извлекается из свойства [DateTimeFormatInfo.AMDesignator](xref:System.Globalization.DateTimeFormatInfo.AMDesignator) или [DateTimeFormatInfo.PMDesignator](xref:System.Globalization.DateTimeFormatInfo.PMDesignator) текущей или заданной среды языка и региональных параметров. Указатель AM (до полудня) используется для всех значений времени от 0:00:00 (от полуночи) до 11:59:59.999. Указатель PM (после полудня) используется для всех значений времени от 12:00:00 (от полудня) до 23:59:59.999. 

Если описатель формата "t" используется без других настраиваемых описателей формата, то он интерпретируется как описатель "t" стандартного формата даты и времени. Дополнительные сведения об использовании единичных описателей форматов см. в подразделе [Использование единичных настраиваемых описателей форматов](#using-single-custom-format-specifiers) ниже.

В следующем примере настраиваемый описатель формата "t" используется в строке настраиваемого формата.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1 µ                        
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1.5 µ
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1 µ                        
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1.5 µ
```

## <a name="the-tt-custom-format-specifier"></a>Настраиваемый описатель формата "tt"

Настраиваемый описатель формата "tt" (плюс любое количество дополнительных описателей "t") представляет полный указатель AM/PM (до полудня/после полудня). Соответствующий локализованный указатель извлекается из свойства [DateTimeFormatInfo.AMDesignator](xref:System.Globalization.DateTimeFormatInfo.AMDesignator) или [DateTimeFormatInfo.PMDesignator](xref:System.Globalization.DateTimeFormatInfo.PMDesignator) текущей или заданной среды языка и региональных параметров. Указатель AM (до полудня) используется для всех значений времени от 0:00:00 (от полуночи) до 11:59:59.999. Указатель PM (после полудня) используется для всех значений времени от 12:00:00 (от полудня) до 23:59:59.999.

Следует проверить, используется ли описатель "tt" для тех языков, в которых необходимо поддерживать различие между временем до полудня и после полудня. Например, японский язык, для которого AM и PM указатели различаются во втором символе вместо первого.

В следующем примере настраиваемый описатель формата "tt" используется в строке настраиваемого формата.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01 du.
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01.50 du.
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01 du.
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01.50 du.
```

## <a name="the-y-custom-format-specifier"></a>Настраиваемый описатель формата "y"

Настраиваемый описатель формата "y" представляет год в виде одно- или двузначного числа. Если год имеет более двух цифр, то в результате отображаются только две младшие цифры. Если первая цифра двузначного года начинается с нуля (например, 2008), то число форматируется без нуля в начале. 

Если описатель формата "y" используется без других настраиваемых описателей формата, то он интерпретируется как описатель "y" стандартного формата даты и времени. Дополнительные сведения об использовании единичных описателей форматов см. в подразделе [Использование единичных настраиваемых описателей форматов](#using-single-custom-format-specifiers) ниже.

В следующем примере настраиваемый описатель формата "y" используется в строке настраиваемого формата.

```csharp
DateTime date1 = new DateTime(1, 12, 1);
DateTime date2 = new DateTime(2010, 1, 1);
Console.WriteLine(date1.ToString("%y"));
// Displays 1
Console.WriteLine(date1.ToString("yy"));
// Displays 01
Console.WriteLine(date1.ToString("yyy"));
// Displays 001
Console.WriteLine(date1.ToString("yyyy"));
// Displays 0001
Console.WriteLine(date1.ToString("yyyyy"));
// Displays 00001
Console.WriteLine(date2.ToString("%y"));
// Displays 10
Console.WriteLine(date2.ToString("yy"));
// Displays 10
Console.WriteLine(date2.ToString("yyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"));
// Displays 02010
```

```vb
Dim date1 As Date = #12/1/0001#
Dim date2 As Date = #1/1/2010#
Console.WriteLine(date1.ToString("%y"))
' Displays 1
Console.WriteLine(date1.ToString("yy"))
' Displays 01
Console.WriteLine(date1.ToString("yyy"))
' Displays 001
Console.WriteLine(date1.ToString("yyyy"))
' Displays 0001
Console.WriteLine(date1.ToString("yyyyy"))
' Displays 00001
Console.WriteLine(date2.ToString("%y"))
' Displays 10
Console.WriteLine(date2.ToString("yy"))
' Displays 10
Console.WriteLine(date2.ToString("yyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"))
' Displays 02010
```

## <a name="the-yy-custom-format-specifier"></a>Настраиваемый описатель формата "yy"

Настраиваемый описатель формата "yy" представляет год в виде двузначного числа. Если год имеет более двух цифр, то в результате отображаются только две младшие цифры. Если двузначное обозначение года имеет менее двух значащих цифр, то число дополняется нулями, стоящими в начале, до двух цифр.

В операции синтаксического анализа представленный в виде двузначного числа год, анализируемый с использованием описателя настраиваемого формата "yy", обрабатывается на основе свойства [Calendar.TwoDigitYearMax](xref:System.Globalization.Calendar.TwoDigitYearMax) текущего календаря поставщика формата. В следующем примере анализируется строковое представление даты, год в которой представлен в виде двузначного числа, с использованием григорианского календаря языка и региональных параметров en-US, которые в данном случае являются текущими языком и региональными параметрами. Затем объект [CultureInfo](xref:System.Globalization.CultureInfo) текущих языка и региональных параметров изменяется так, чтобы использовался объект [GregorianCalendar](xref:System.Globalization.GregorianCalendar), свойство [TwoDigitYearMax](xref:System.Globalization.GregorianCalendar.TwoDigitYearMax) которого было изменено.

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string fmt = "dd-MMM-yy";
      string value = "24-Jan-49";

      Calendar cal = (Calendar) CultureInfo.CurrentCulture.Calendar.Clone();
      Console.WriteLine("Two Digit Year Range: {0} - {1}", 
                        cal.TwoDigitYearMax - 99, cal.TwoDigitYearMax);

      Console.WriteLine("{0:d}", DateTime.ParseExact(value, fmt, null));
      Console.WriteLine();

      cal.TwoDigitYearMax = 2099;
      CultureInfo culture = (CultureInfo) CultureInfo.CurrentCulture.Clone();
      culture.DateTimeFormat.Calendar = cal;
      Thread.CurrentThread.CurrentCulture = culture;

      Console.WriteLine("Two Digit Year Range: {0} - {1}", 
                        cal.TwoDigitYearMax - 99, cal.TwoDigitYearMax);
      Console.WriteLine("{0:d}", DateTime.ParseExact(value, fmt, null));
   }
}
// The example displays the following output:
//       Two Digit Year Range: 1930 - 2029
//       1/24/1949
//       
//       Two Digit Year Range: 2000 - 2099
//       1/24/2049
```

```vb
Imports System.Globalization
Imports System.Threading

Module Example
   Public Sub Main()
      Dim fmt As String = "dd-MMM-yy"
      Dim value As String = "24-Jan-49"

      Dim cal As Calendar = CType(CultureInfo.CurrentCulture.Calendar.Clone(), Calendar)
      Console.WriteLine("Two Digit Year Range: {0} - {1}", 
                        cal.TwoDigitYearMax - 99, cal.TwoDigitYearMax)

      Console.WriteLine("{0:d}", DateTime.ParseExact(value, fmt, Nothing))
      Console.WriteLine()

      cal.TwoDigitYearMax = 2099
      Dim culture As CultureInfo = CType(CultureInfo.CurrentCulture.Clone(), CultureInfo)
      culture.DateTimeFormat.Calendar = cal
      Thread.CurrentThread.CurrentCulture = culture

      Console.WriteLine("Two Digit Year Range: {0} - {1}", 
                        cal.TwoDigitYearMax - 99, cal.TwoDigitYearMax)
      Console.WriteLine("{0:d}", DateTime.ParseExact(value, fmt, Nothing))
   End Sub
End Module
' The example displays the following output:
'       Two Digit Year Range: 1930 - 2029
'       1/24/1949
'       
'       Two Digit Year Range: 2000 - 2099
'       1/24/2049
```

В следующем примере настраиваемый описатель формата "yy" используется в строке настраиваемого формата.

```csharp
DateTime date1 = new DateTime(1, 12, 1);
DateTime date2 = new DateTime(2010, 1, 1);
Console.WriteLine(date1.ToString("%y"));
// Displays 1
Console.WriteLine(date1.ToString("yy"));
// Displays 01
Console.WriteLine(date1.ToString("yyy"));
// Displays 001
Console.WriteLine(date1.ToString("yyyy"));
// Displays 0001
Console.WriteLine(date1.ToString("yyyyy"));
// Displays 00001
Console.WriteLine(date2.ToString("%y"));
// Displays 10
Console.WriteLine(date2.ToString("yy"));
// Displays 10
Console.WriteLine(date2.ToString("yyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"));
// Displays 02010
```

```vb
Dim date1 As Date = #12/1/0001#
Dim date2 As Date = #1/1/2010#
Console.WriteLine(date1.ToString("%y"))
' Displays 1
Console.WriteLine(date1.ToString("yy"))
' Displays 01
Console.WriteLine(date1.ToString("yyy"))
' Displays 001
Console.WriteLine(date1.ToString("yyyy"))
' Displays 0001
Console.WriteLine(date1.ToString("yyyyy"))
' Displays 00001
Console.WriteLine(date2.ToString("%y"))
' Displays 10
Console.WriteLine(date2.ToString("yy"))
' Displays 10
Console.WriteLine(date2.ToString("yyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"))
' Displays 02010
```

## <a name="the-yyy-custom-format-specifier"></a>Настраиваемый описатель формата "yyy"

Настраиваемый описатель формата "yyy" представляет год в виде как минимум трех цифр. Если в году больше трех значащих цифр, то они включаются в результат. Если значение года имеет меньше трех цифр, то число дополняется стоящими в начале нулями до трех цифр.

> [!NOTE]
> Для Тайского (буддистского) календаря, в котором годы могут состоять из пяти цифр, этот описатель формата отображает все значимые цифры.

В следующем примере настраиваемый описатель формата "yyy" используется в строке настраиваемого формата.

```csharp
DateTime date1 = new DateTime(1, 12, 1);
DateTime date2 = new DateTime(2010, 1, 1);
Console.WriteLine(date1.ToString("%y"));
// Displays 1
Console.WriteLine(date1.ToString("yy"));
// Displays 01
Console.WriteLine(date1.ToString("yyy"));
// Displays 001
Console.WriteLine(date1.ToString("yyyy"));
// Displays 0001
Console.WriteLine(date1.ToString("yyyyy"));
// Displays 00001
Console.WriteLine(date2.ToString("%y"));
// Displays 10
Console.WriteLine(date2.ToString("yy"));
// Displays 10
Console.WriteLine(date2.ToString("yyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"));
// Displays 02010      
```

```vb
Dim date1 As Date = #12/1/0001#
Dim date2 As Date = #1/1/2010#
Console.WriteLine(date1.ToString("%y"))
' Displays 1
Console.WriteLine(date1.ToString("yy"))
' Displays 01
Console.WriteLine(date1.ToString("yyy"))
' Displays 001
Console.WriteLine(date1.ToString("yyyy"))
' Displays 0001
Console.WriteLine(date1.ToString("yyyyy"))
' Displays 00001
Console.WriteLine(date2.ToString("%y"))
' Displays 10
Console.WriteLine(date2.ToString("yy"))
' Displays 10
Console.WriteLine(date2.ToString("yyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"))
' Displays 02010 
```

## <a name="the-yyyy-custom-format-specifier"></a>Настраиваемый описатель формата "yyyy"

Описатель настраиваемого формата "yyyy" представляет год в виде как минимум четырех цифр. Если в году больше четырех значащих цифр, они включаются в результирующую строку. Если в году меньше четырех цифр, число дополняется предшествующими нулями до достижения четырех цифр.

> [!NOTE]
> Для Тайского (буддистского) календаря, в котором годы могут состоять из пяти цифр, этот описатель формата отображает все значимые цифры.

В следующем примере настраиваемый описатель формата "yyyy" используется в строке настраиваемого формата.

```csharp
DateTime date1 = new DateTime(1, 12, 1);
DateTime date2 = new DateTime(2010, 1, 1);
Console.WriteLine(date1.ToString("%y"));
// Displays 1
Console.WriteLine(date1.ToString("yy"));
// Displays 01
Console.WriteLine(date1.ToString("yyy"));
// Displays 001
Console.WriteLine(date1.ToString("yyyy"));
// Displays 0001
Console.WriteLine(date1.ToString("yyyyy"));
// Displays 00001
Console.WriteLine(date2.ToString("%y"));
// Displays 10
Console.WriteLine(date2.ToString("yy"));
// Displays 10
Console.WriteLine(date2.ToString("yyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"));
// Displays 02010 
```

```vb
Dim date1 As Date = #12/1/0001#
Dim date2 As Date = #1/1/2010#
Console.WriteLine(date1.ToString("%y"))
' Displays 1
Console.WriteLine(date1.ToString("yy"))
' Displays 01
Console.WriteLine(date1.ToString("yyy"))
' Displays 001
Console.WriteLine(date1.ToString("yyyy"))
' Displays 0001
Console.WriteLine(date1.ToString("yyyyy"))
' Displays 00001
Console.WriteLine(date2.ToString("%y"))
' Displays 10
Console.WriteLine(date2.ToString("yy"))
' Displays 10
Console.WriteLine(date2.ToString("yyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"))
' Displays 02010
```

## <a name="the-yyyyy-custom-format-specifier"></a>Настраиваемый описатель формата "yyyyy"

Описатель настраиваемого формата "yyyyy" (плюс любое число дополнительных описателей "y") представляет год в виде минимум пяти цифр. Если в году больше пяти значащих цифр, они включаются в результирующую строку. Если в году меньше пяти цифр, то число дополняется стоящими в начале нулями до пяти цифр.

Если имеются дополнительные описатели "y", то число дополняется нулями в начале до достижения указанного количества описателей "у". 

В следующем примере настраиваемый описатель формата "yyyyy" используется в строке настраиваемого формата.

```csharp
DateTime date1 = new DateTime(1, 12, 1);
DateTime date2 = new DateTime(2010, 1, 1);
Console.WriteLine(date1.ToString("%y"));
// Displays 1
Console.WriteLine(date1.ToString("yy"));
// Displays 01
Console.WriteLine(date1.ToString("yyy"));
// Displays 001
Console.WriteLine(date1.ToString("yyyy"));
// Displays 0001
Console.WriteLine(date1.ToString("yyyyy"));
// Displays 00001
Console.WriteLine(date2.ToString("%y"));
// Displays 10
Console.WriteLine(date2.ToString("yy"));
// Displays 10
Console.WriteLine(date2.ToString("yyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"));
// Displays 02010 
```

```vb
Dim date1 As Date = #12/1/0001#
Dim date2 As Date = #1/1/2010#
Console.WriteLine(date1.ToString("%y"))
' Displays 1
Console.WriteLine(date1.ToString("yy"))
' Displays 01
Console.WriteLine(date1.ToString("yyy"))
' Displays 001
Console.WriteLine(date1.ToString("yyyy"))
' Displays 0001
Console.WriteLine(date1.ToString("yyyyy"))
' Displays 00001
Console.WriteLine(date2.ToString("%y"))
' Displays 10
Console.WriteLine(date2.ToString("yy"))
' Displays 10
Console.WriteLine(date2.ToString("yyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"))
' Displays 02010 
```

## <a name="the-z-custom-format-specifier"></a>Настраиваемый описатель формата "z"

Совместно со значениями [DateTime](xref:System.DateTime) настраиваемый описатель формата "z" представляет указанное со знаком смещение часового пояса локальной операционной системы от времени UTC, измеренное в часах. Описатель не отражает значение свойства [DateTime.Kind](xref:System.DateTime.Kind) экземпляра. По этой причине описатель формата "z" не рекомендуется использовать со значениями [DateTime](xref:System.DateTime).

Для значений [DateTimeOffset](xref:System.DateTimeOffset) этот описатель формата представляет смещение значения [DateTimeOffset](xref:System.DateTimeOffset) от времени UTC в часах. 

Смещение всегда отображается со знаком в начале. Плюс (+) указывает на то, что часы опережают время UTC, а минус (-) — на то, что они от него отстают. Смещение с одной цифрой форматируется без нуля в начале. 

Если описатель формата "z" используется без других настраиваемых описателей формата, то он интерпретируется как описатель стандартного формата даты и времени, и возникает исключение [FormatException](xref:System.FormatException). Дополнительные сведения об использовании единичных описателей форматов см. в подразделе [Использование единичных настраиваемых описателей форматов](#using-single-custom-format-specifiers) ниже. 

В следующем примере настраиваемый описатель формата "z" используется в строке настраиваемого формата.

```csharp
DateTime date1 = DateTime.UtcNow;
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", 
                  date1));
// Displays -7, -07, -07:00                     

DateTimeOffset date2 = new DateTimeOffset(2008, 8, 1, 0, 0, 0, 
                                          new TimeSpan(6, 0, 0));
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", 
                  date2));
// Displays +6, +06, +06:00
```

```vb
Dim date1 As Date = Date.UtcNow
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", _
                  date1))
' Displays -7, -07, -07:00                     

Dim date2 As New DateTimeOffset(2008, 8, 1, 0, 0, 0, _
                                New Timespan(6, 0, 0))
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", _
                  date2))                                     
' Displays +6, +06, +06:00
```

## <a name="the-zz-custom-format-specifier"></a>Настраиваемый описатель формата "zz"

Совместно со значениями [DateTime](xref:System.DateTime) настраиваемый описатель формата "zz" представляет указанное со знаком смещение часового пояса локальной операционной системы от времени UTC, измеренное в часах. Описатель не отражает значение свойства [DateTime.Kind](xref:System.DateTime.Kind) экземпляра. По этой причине описатель формата "zz" не рекомендуется использовать со значениями [DateTime](xref:System.DateTime).

Для значений [DateTimeOffset](xref:System.DateTimeOffset) этот описатель формата представляет смещение значения [DateTimeOffset](xref:System.DateTimeOffset) от времени UTC в часах.

Смещение всегда отображается со знаком в начале. Плюс (+) указывает на то, что часы опережают время UTC, а минус (-) — на то, что они от него отстают. Смещение с одной цифрой форматируется c нулем в начале. 

В следующем примере настраиваемый описатель формата "zz" используется в строке настраиваемого формата.

```csharp
DateTime date1 = DateTime.UtcNow;
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", 
                  date1));
// Displays -7, -07, -07:00                     

DateTimeOffset date2 = new DateTimeOffset(2008, 8, 1, 0, 0, 0, 
                                          new TimeSpan(6, 0, 0));
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", 
                  date2));
// Displays +6, +06, +06:00
```

```vb
Dim date1 As Date = Date.UtcNow
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", _
                  date1))
' Displays -7, -07, -07:00                     

Dim date2 As New DateTimeOffset(2008, 8, 1, 0, 0, 0, _
                                New Timespan(6, 0, 0))
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", _
                  date2))                                     
' Displays +6, +06, +06:00
```

## <a name="the-zzz-custom-format-specifier"></a>Настраиваемый описатель формата "zzz"

Совместно со значениями [DateTime](xref:System.DateTime) настраиваемый описатель формата "zzz" представляет указанное со знаком смещение часового пояса локальной операционной системы от времени UTC, измеренное в часах. Описатель не отражает значение свойства [DateTime.Kind](xref:System.DateTime.Kind) экземпляра. По этой причине описатель формата "zzz" не рекомендуется использовать со значениями [DateTime](xref:System.DateTime).

Для значений [DateTimeOffset](xref:System.DateTimeOffset) этот описатель формата представляет смещение значения [DateTimeOffset](xref:System.DateTimeOffset) от времени UTC в часах.

Смещение всегда отображается со знаком в начале. Плюс (+) указывает на то, что часы опережают время UTC, а минус (-) — на то, что они от него отстают. Смещение с одной цифрой форматируется c нулем в начале. 

В следующем примере настраиваемый описатель формата "zzz" используется в строке настраиваемого формата.

```csharp
DateTime date1 = DateTime.UtcNow;
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", 
                  date1));
// Displays -7, -07, -07:00                     

DateTimeOffset date2 = new DateTimeOffset(2008, 8, 1, 0, 0, 0, 
                                          new TimeSpan(6, 0, 0));
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", 
                  date2));
// Displays +6, +06, +06:00
```

```vb
Dim date1 As Date = Date.UtcNow
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", _
                  date1))
' Displays -7, -07, -07:00                     

Dim date2 As New DateTimeOffset(2008, 8, 1, 0, 0, 0, _
                                New Timespan(6, 0, 0))
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", _
                  date2))                                     
' Displays +6, +06, +06:00
```

## <a name="the--custom-format-specifier"></a>Настраиваемый описатель формата ":"

Настраиваемый описатель формата ":" представляет разделитель компонентов времени, который используется для разделения часов, минут и секунд. 

Если описатель формата ":" используется без других настраиваемых описателей формата, то он интерпретируется как описатель стандартного формата даты и времени, и возникает исключение [FormatException](xref:System.FormatException). Дополнительные сведения об использовании единичных описателей форматов см. в подразделе [Использование единичных настраиваемых описателей форматов](#using-single-custom-format-specifiers) ниже.

## <a name="the--custom-format-specifier"></a>Настраиваемый описатель формата "/"

Описатель настраиваемого формата "/" представляет разделитель компонентов даты, который используется для разделения года, месяца и дня. 

Если описатель формата "/" используется без других настраиваемых описателей формата, то он интерпретируется как описатель стандартного формата даты и времени, и возникает исключение [FormatException](xref:System.FormatException). Дополнительные сведения об использовании единичных описателей форматов см. в подразделе [Использование единичных настраиваемых описателей форматов](#using-single-custom-format-specifiers) ниже.

## <a name="character-literals"></a>Символьные литералы

Следующие символы в строке настраиваемого формата даты зарезервированы и всегда интерпретируются как символы форматирования или в случае использования ", ', / и \, — как специальные символы. 

  |   |   |   |      
- | - | - | - | -
F | H | K | M | d
f | н | h | m | s
Y | Y | з | % | :
/ | " | ' | \ |
  |   |   |   |
  
Все остальные символы всегда интерпретируется как символьные литералы. В операции форматирования они включаются в результирующую строку без изменений. В операции анализа они должны точно соответствовать символам во входной строке. При сравнении учитывается регистр. 

В следующем примере литеральные символы "PST" (стандартное тихоокеанское время) и "PDT" (тихоокеанское летнее время) представляют в строке формата местный часовой пояс. Обратите внимание, что строка включена в результирующую строку и строка, которая включает строку местного часового пояса зоны местного времени, успешно проходит синтаксический анализ. 

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      String[] formats = { "dd MMM yyyy hh:mm tt PST", 
                           "dd MMM yyyy hh:mm tt PDT" };
      var dat = new DateTime(2016, 8, 18, 16, 50, 0);
      // Display the result string. 
      Console.WriteLine(dat.ToString(formats[1]));

      // Parse a string. 
      String value = "25 Dec 2016 12:00 pm PST";
      DateTime newDate;
      if (DateTime.TryParseExact(value, formats, null, 
                                 DateTimeStyles.None, out newDate)) 
         Console.WriteLine(newDate);
      else
         Console.WriteLine("Unable to parse '{0}'", value);
   }
}
// The example displays the following output:
//       18 Aug 2016 04:50 PM PDT
//       12/25/2016 12:00:00 PM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim formats() As String = { "dd MMM yyyy hh:mm tt PST", 
                                  "dd MMM yyyy hh:mm tt PDT" }
      Dim dat As New Date(2016, 8, 18, 16, 50, 0)
      ' Display the result string. 
      Console.WriteLine(dat.ToString(formats(1)))

      ' Parse a string. 
      Dim value As String = "25 Dec 2016 12:00 pm PST"
      Dim newDate As Date
      If Date.TryParseExact(value, formats, Nothing, 
                            DateTimeStyles.None, newDate) Then 
         Console.WriteLine(newDate)
      Else
         Console.WriteLine("Unable to parse '{0}'", value)
      End If                               
   End Sub
End Module
' The example displays the following output:
'       18 Aug 2016 04:50 PM PDT
'       12/25/2016 12:00:00 PM
```

Указать необходимость интерпретации символов как литеральных, а не как зарезервированных, для их последующего включения в результирующую строку или успешного анализа во входной строке можно двумя способами.

* Путем экранирования каждого зарезервированного символа. Дополнительные сведения см. в разделе [Использование escape-символов](#using-the-escape-character). 
  
  В следующем примере литеральные символы "pst" (стандартное тихоокеанское время) представляют в строке формата местный часовой пояс. Поскольку "s" и "t" представляют собой строки настраиваемых форматов даты и времени, перед ними необходимо поставить знак обратной косой черты, чтобы интерпретировать их как символьные литералы. 
  
```csharp
using System;
using System.Globalization;

public class Example
{
  public static void Main()
  {
      String format = "dd MMM yyyy hh:mm tt p\\s\\t";
      var dat = new DateTime(2016, 8, 18, 16, 50, 0);
      // Display the result string. 
      Console.WriteLine(dat.ToString(format));

      // Parse a string. 
      String value = "25 Dec 2016 12:00 pm pst";
      DateTime newDate;
      if (DateTime.TryParseExact(value, format, null, 
                                  DateTimeStyles.None, out newDate)) 
          Console.WriteLine(newDate);
      else
          Console.WriteLine("Unable to parse '{0}'", value);
  }
}
// The example displays the following output:
//       18 Aug 2016 04:50 PM PDT
//       12/25/2016 12:00:00 PM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim fmt As String = "dd MMM yyyy hh:mm tt p\s\t" 
      Dim dat As New Date(2016, 8, 18, 16, 50, 0)
      ' Display the result string. 
      Console.WriteLine(dat.ToString(fmt))

      ' Parse a string. 
      Dim value As String = "25 Dec 2016 12:00 pm pst"
      Dim newDate As Date
      If Date.TryParseExact(value, fmt, Nothing, 
                            DateTimeStyles.None, newDate) Then 
         Console.WriteLine(newDate)
      Else
         Console.WriteLine("Unable to parse '{0}'", value)
      End If                               
   End Sub
End Module
' The example displays the following output:
'       18 Aug 2016 04:50 PM pst
'       12/25/2016 12:00:00 PM
```
  
* Путем заключения всей литеральной строки в двойные или одинарные кавычки. Следующий пример аналогичен предыдущему, за исключением того, что "pst" заключается в кавычки, чтобы указать, что вся строка с разделителями должна интерпретироваться как символьные литералы. 

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      String format = "dd MMM yyyy hh:mm tt \"pst\"";
      var dat = new DateTime(2016, 8, 18, 16, 50, 0);
      // Display the result string. 
      Console.WriteLine(dat.ToString(format));

      // Parse a string. 
      String value = "25 Dec 2016 12:00 pm pst";
      DateTime newDate;
      if (DateTime.TryParseExact(value, format, null, 
                                 DateTimeStyles.None, out newDate)) 
         Console.WriteLine(newDate);
      else
         Console.WriteLine("Unable to parse '{0}'", value);
   }
}
// The example displays the following output:
//       18 Aug 2016 04:50 PM PDT
//       12/25/2016 12:00:00 PM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim fmt As String = "dd MMM yyyy hh:mm tt ""pst"""  
      Dim dat As New Date(2016, 8, 18, 16, 50, 0)
      ' Display the result string. 
      Console.WriteLine(dat.ToString(fmt))

      ' Parse a string. 
      Dim value As String = "25 Dec 2016 12:00 pm pst"
      Dim newDate As Date
      If Date.TryParseExact(value, fmt, Nothing, 
                            DateTimeStyles.None, newDate) Then 
         Console.WriteLine(newDate)
      Else
         Console.WriteLine("Unable to parse '{0}'", value)
      End If                               
   End Sub
End Module
' The example displays the following output:
'       18 Aug 2016 04:50 PM pst
'       12/25/2016 12:00:00 PM
```

## <a name="notes"></a>Примечания


### <a name="using-single-custom-format-specifiers"></a>Использование единичных описателей настраиваемого формата

Строка настраиваемого формата даты и времени состоит из двух или более знаков. Методы форматирования даты и времени интерпретируют любую односимвольную строку как строку стандартного формата даты и времени. Если они не распознают этот символ как допустимый описатель формата, возникает исключение [FormatException](xref:System.FormatException). Например, строка формата, состоящая только из описателя "h", интерпретируется как строка стандартного формата даты и времени. Однако в этом случае создается исключение, так как отсутствует описатель стандартного формата даты и времени "h". 

Чтобы использовать какой-либо настраиваемый описатель формата даты и времени в качестве единственного описателя в строке формата (т. е. использовать единственный настраиваемый описатель формата "d", "f", "F", "g", "h", "H", "K", "m", "M", "s", "t", "y", "z", ":" или "/"), следует включить пробел до или после описателя или указать описатель формата "%" (процент) перед единственным настраиваемым описателем формата даты и времени.

Например, "`%h`" интерпретируется как строка настраиваемого формата даты и времени, которая отображает час, представленный текущим значением даты и времени. Можно также использовать строки формата " h" или "h ", хотя в этом случае в результирующей строке час будет указан с пробелом. В следующем примере демонстрируется использование этих трех строк формата.


```csharp
DateTime dat1 = new DateTime(2009, 6, 15, 13, 45, 0);

Console.WriteLine("'{0:%h}'", dat1);
Console.WriteLine("'{0: h}'", dat1);
Console.WriteLine("'{0:h }'", dat1);
// The example displays the following output:
//       '1'
//       ' 1'
//       '1 '
```

```vb
Dim dat1 As Date = #6/15/2009 1:45PM#

Console.WriteLine("'{0:%h}'", dat1)
Console.WriteLine("'{0: h}'", dat1)
Console.WriteLine("'{0:h }'", dat1)
' The example displays the following output:
'       '1'
'       ' 1'
'       '1 '
```

### <a name="using-the-escape-character"></a>Использование escape-символов

Символы "d", "f", "F", "g", "h", "H", "K", "m", "M", "s", "t", "y", "z", ":" и "/" в строке формата интерпретируются как настраиваемые описатели формата, а не как литералы. Чтобы такие символы не обрабатывались как описатели формата, можно указывать перед ними обратную косую черту (\)), называемую также escape-символом. Наличие escape-символа означает, что следующий за ним символ является литералом, который следует перенести в результирующую строку без изменений.

Чтобы включить в результирующую строку обратную косую черту, перед ней нужно поставить дополнительную обратную косую черту (`\\`).

> [!NOTE]
> Кроме того, в некоторых компиляторах, например компиляторе C#, одиночная обратная косая черта также может восприниматься как escape-символ. Чтобы гарантировать, что строка будет правильно воспринята при форматировании, можно поставить символ буквального строкового литерала (символ "@") перед строкой или добавить дополнительный символ обратной косой черты перед каждой обратной косой чертой. В следующем примере кода на языке C# демонстрируются оба подхода.

В следующем примере с помощью escape-символа предотвращается интерпретация операцией форматирования символов "h" и "m" в качестве описателей формата. 

```csharp
DateTime date = new DateTime(2009, 06, 15, 13, 45, 30, 90);
string fmt1 = "h \\h m \\m";
string fmt2 = @"h \h m \m";

Console.WriteLine("{0} ({1}) -> {2}", date, fmt1, date.ToString(fmt1));
Console.WriteLine("{0} ({1}) -> {2}", date, fmt2, date.ToString(fmt2));
// The example displays the following output:
//       6/15/2009 1:45:30 PM (h \h m \m) -> 1 h 45 m
//       6/15/2009 1:45:30 PM (h \h m \m) -> 1 h 45 m
```

```vb
Dim date1 As Date = #6/15/2009 13:45#
Dim fmt As String = "h \h m \m"

Console.WriteLine("{0} ({1}) -> {2}", date1, fmt, date1.ToString(fmt))
' The example displays the following output:
'       6/15/2009 1:45:00 PM (h \h m \m) -> 1 h 45 m 
```

### <a name="datetimeformatinfo-properties"></a>Свойства DateTimeFormatInfo

На форматирование влияют свойства текущего объекта [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), которые задаются либо неявно, языком и региональными параметрами текущего потока, либо явно, параметром [IFormatProvider](xref:System.IFormatProvider) метода, который вызывает форматирование. Для параметра [IFormatProvider](xref:System.IFormatProvider) необходимо указать объект [CultureInfo](xref:System.Globalization.CultureInfo), представляющий язык и региональные параметры, или объект [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo). 

Результирующая строка, формируемая многими настраиваемыми описателями формата даты и времени, также зависит от свойств текущего объекта [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo). Приложение может изменить результат использования некоторых описателей настраиваемых форматов даты и времени, изменив соответствующее свойство [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo). Например, описатель формата "ddd" добавляет в результирующую строку сокращенное название дня недели, найденное в массиве строк [AbbreviatedDayNames](xref:System.Globalization.DateTimeFormatInfo.AbbreviatedDayNames). Аналогичным образом описатель формата "MMMM" добавляет в результирующую строку полное название месяца, найденное в массиве строк [MonthNames](xref:System.Globalization.DateTimeFormatInfo.MonthNames).

## <a name="see-also"></a>См. также

[System.DateTime](xref:System.DateTime)

[System.IFormatProvider](xref:System.IFormatProvider)

[Типы форматирования](formatting-types.md)

[Строки стандартных форматов даты и времени](standard-datetime.md)


