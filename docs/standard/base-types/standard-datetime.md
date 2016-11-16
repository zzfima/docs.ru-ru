---
title: "Строки стандартных форматов даты и времени"
description: "Строки стандартных форматов даты и времени"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/25/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: be239871-10cc-4949-b548-200bb260630a
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 1196459d74038edb1268c619dac3da69f38e7860

---

# <a name="standard-date-and-time-format-strings"></a>Строки стандартных форматов даты и времени

Строка стандартного формата даты и времени использует один описатель формата для определения текстового представления значения даты и времени. Любая строка формата даты и времени, содержащая более одного символа, включая пробелы, интерпретируется как строка настраиваемого формата даты и времени. Дополнительные сведения см. в статье [Строки настраиваемых форматов даты и времени](custom-datetime.md). Строку стандартного или пользовательского формата можно использовать двумя способами:

* Для определения строки, являющейся результатом операции форматирования.

* Для определения текстового представления значения даты и времени, которое можно преобразовать в значение [DateTime](xref:System.DateTime) или [DateTimeOffset](xref:System.DateTimeOffset) с помощью операции синтаксического анализа.

Строки стандартного формата даты и времени могут использоваться как со значением [DateTime](xref:System.DateTime), так и со значением [DateTimeOffset](xref:System.DateTimeOffset). 

В следующей таблице описаны спецификаторы стандартных форматов даты и времени. Если не указано иное, то описатель стандартного формата даты и времени выдает одинаковое строковое представление независимо от того, используется ли он со значением [DateTime](xref:System.DateTime) или [DateTimeOffset](xref:System.DateTimeOffset). Дополнительные сведения об использовании стандартных строк формата даты и времени см. в подразделе [Примечания](#notes).

Описатель формата | Описание | Примеры
---------------- | ----------- | --------
"d" | Короткий шаблон даты. | `2009-06-15T13:45:30 -> 6/15/2009 (en-US)`; `2009-06-15T13:45:30 -> 15/06/2009 (fr-FR)`; `2009-06-15T13:45:30 -> 2009/06/15 (ja-JP)`
"D" | Полный шаблон даты. | `2009-06-15T13:45:30 -> Monday, June 15, 2009 (en-US)`; `2009-06-15T13:45:30 -> 15 июня 2009 г. (ru-RU)`; `2009-06-15T13:45:30 -> Montag, 15. Juni 2009 (de-DE)`
"f" | Полный шаблон даты и времени (короткий шаблон времени). | `2009-06-15T13:45:30 -> Monday, June 15, 2009 1:45 PM (en-US)`; `2009-06-15T13:45:30 -> den 15 juni 2009 13:45 (sv-SE)`; `2009-06-15T13:45:30 -> Δευτέρα, 15 Ιουνίου 2009 1:45 μμ (el-GR)`
"F" | Полный шаблон даты и времени (полный шаблон времени). | `2009-06-15T13:45:30 -> Monday, June 15, 2009 1:45:30 PM (en-US)`; `2009-06-15T13:45:30 -> den 15 juni 2009 13:45:30 (sv-SE)`; `2009-06-15T13:45:30 -> Δευτέρα, 15 Ιουνίου 2009 1:45:30 μμ (el-GR)`
"g" | Общий шаблон даты и времени (короткий шаблон времени). | `2009-06-15T13:45:30 -> 6/15/2009 1:45 PM (en-US)`; `2009-06-15T13:45:30 -> 15/06/2009 13:45 (es-ES)`; `2009-06-15T13:45:30 -> 2009/6/15 13:45 (zh-CN)`
"G" | Общий шаблон даты и времени (полный шаблон времени). | `2009-06-15T13:45:30 -> 6/15/2009 1:45:30 PM (en-US)`; `2009-06-15T13:45:30 -> 15/06/2009 13:45:30 (es-ES)`; `2009-06-15T13:45:30 -> 2009/6/15 13:45:30 (zh-CN)`
"M", "m" | Шаблон дней месяца. | `2009-06-15T13:45:30 -> June 15 (en-US)`; `2009-06-15T13:45:30 -> 15. juni (da-DK)`; `2009-06-15T13:45:30 -> 15 Juni (id-ID)`
"O", "o" | Шаблон обратного преобразования даты и времени. | Значения типа [DateTime](xref:System.DateTime): `2009-06-15T13:45:30 (DateTimeKind.Local) --> 2009-06-15T13:45:30.0000000-07:00`; `2009-06-15T13:45:30 (DateTimeKind.Utc) --> 2009-06-15T13:45:30.0000000Z`; `2009-06-15T13:45:30 (DateTimeKind.Unspecified) --> 2009-06-15T13:45:30.0000000`. Значения типа [DateTimeOffset](xref:System.DateTimeOffset): `2009-06-15T13:45:30-07:00 --> 2009-06-15T13:45:30.0000000-07:00`
"R", "r" | Шаблон RFC1123. | `2009-06-15T13:45:30 -> Mon, 15 Jun 2009 20:45:30 GMT`
"s" | Сортируемый шаблон времени и даты. | `2009-06-15T13:45:30 (DateTimeKind.Local) -> 2009-06-15T13:45:30`; `2009-06-15T13:45:30 (DateTimeKind.Utc) -> 2009-06-15T13:45:30`
"t" | Короткий шаблон времени. | `2009-06-15T13:45:30 -> 1:45 PM (en-US)`; `2009-06-15T13:45:30 -> 13:45 (hr-HR)`; `2009-06-15T13:45:30 -> 01:45 م (ar-EG)` 
"T" | Полный шаблон времени. | `2009-06-15T13:45:30 -> 1:45:30 PM (en-US)`; `2009-06-15T13:45:30 -> 13:45:30 (hr-HR)`; `2009-06-15T13:45:30 -> 01:45:30 م (ar-EG)`
"u" | Универсальный сортируемый шаблон времени и даты. | Со значением [DateTime](xref:System.DateTime): `2009-06-15T13:45:30 -> 2009-06-15 13:45:30Z`. Со значением [DateTimeOffset](xref:System.DateTimeOffset): `2009-06-15T13:45:30 -> 2009-06-15 20:45:30Z`
"U" | Универсальный полный шаблон даты и времени. | `2009-06-15T13:45:30 -> Monday, June 15, 2009 8:45:30 PM (en-US)`; `2009-06-15T13:45:30 -> den 15 juni 2009 20:45:30 (sv-SE)`; `2009-06-15T13:45:30 -> Δευτέρα, 15 Ιουνίου 2009 8:45:30 μμ (el-GR)`
"Y", "y" | Шаблон месяца года. | `2009-06-15T13:45:30 -> June, 2009 (en-US)`; `2009-06-15T13:45:30 -> juni 2009 (da-DK)`; `2009-06-15T13:45:30 -> Juni 2009 (id-ID)`
Любой другой символ | Неизвестный описатель. | Создает исключение времени выполнения [FormatException](xref:System.FormatException).

## <a name="how-standard-format-strings-work"></a>Как работают строки стандартного формата

В операции форматирования строка стандартного формата — это всего лишь псевдоним для строки пользовательского формата. Преимуществом использования псевдонима для ссылки на строку пользовательского формата является то, что при изменении строки пользовательского формата псевдоним может оставаться неизменным. Это важно, поскольку строковые представления значений даты и времени обычно зависят от региональных параметров. Например, строка стандартного формата "d" указывает, что значение даты и времени будет отображаться с использованием шаблона короткого формата даты. Для инвариантных региональных параметров таким шаблоном является "мм/дд/гггг". Для региональных параметров fr-FR это "дд/мм/гггг". Для региональных параметров ja-JP это "гггг/мм/дд".

Если строка стандартного формата в операции форматирования сопоставлена со строкой пользовательского формата для определенных региональных параметров, то приложение может определить конкретные региональные параметры, для которых строки пользовательского формата используются одним из следующих способов:

* Можно использовать региональные параметры по умолчанию (или текущие). Следующий пример отображает дату в формате короткой даты, соответствующем текущим региональным параметрам. В этом случае текущими региональными параметрами являются en-US. 

  ```csharp
  // Display using current (en-us) culture's short date format
  DateTime thisDate = new DateTime(2008, 3, 15);
  Console.WriteLine(thisDate.ToString("d"));           // Displays 3/15/2008
  ```

  ```vb
  ' Display using current (en-us) culture's short date format
  Dim thisDate As Date = #03/15/2008#
  Console.WriteLine(thisDate.ToString("d"))     ' Displays 3/15/2008
  ```
  
* Можно передать объект [CultureInfo](xref:System.Globalization.CultureInfo), представляющий язык и региональные параметры, соответствующее которым форматирование будет использоваться методом с параметром [IFormatProvider](xref:System.IFormatProvider). Следующий пример отображает дату в формате короткой даты, соответствующем региональным параметрам pt-BR.
  
  ```csharp
  // Display using pt-BR culture's short date format
  DateTime thisDate = new DateTime(2008, 3, 15);
  CultureInfo culture = new CultureInfo("pt-BR");      
  Console.WriteLine(thisDate.ToString("d", culture));  // Displays 15/3/2008
  ```

  ```vb
  ' Display using pt-BR culture's short date format
  Dim thisDate As Date = #03/15/2008#
  Dim culture As New CultureInfo("pt-BR")      
  Console.WriteLine(thisDate.ToString("d", culture))   ' Displays 15/3/2008
  ```
  
* Можно передать объект [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), предоставляющий данные форматирования, методу с параметром[IFormatProvider](xref:System.IFormatProvider). В следующем примере дата отображается с помощью короткого формата даты из объекта DateTimeFormatInfo, соответствующего региональным параметрам hr-HR.  

  ```csharp
  // Display using date format information from hr-HR culture
  DateTime thisDate = new DateTime(2008, 3, 15);
  DateTimeFormatInfo fmt = (new CultureInfo("hr-HR")).DateTimeFormat;
  Console.WriteLine(thisDate.ToString("d", fmt));      // Displays 15.3.2008
  ```

  ```vb
  ' Display using date format information from hr-HR culture
  Dim thisDate As Date = #03/15/2008#
  Dim fmt As DateTimeFormatInfo = (New CultureInfo("hr-HR")).DateTimeFormat
  Console.WriteLine(thisDate.ToString("d", fmt))   ' Displays 15.3.2008
  ```
  
В некоторых случаях строка стандартного формата служит удобным сокращением длинной строки пользовательского формата, который является неизменяемым. В эту категорию попадают четыре строки стандартного формата: "O" (или "o"), "R" (или "r"), "s" и "u". Эти строки соответствуют строкам пользовательского формата, соответствующего инвариантным региональным параметрам. Они создают строковые представления значений даты и времени, которые, предположительно, совпадают для различных региональных параметров. В следующей таблице приведены сведения об этих четырех строках стандартных форматов даты и времени.

Строка стандартного формата | Определена свойством DateTimeFormatInfo.InvariantInfo | Строка пользовательского формата
---------------------- | ---------------------------------------------------- | --------------------
"O" или "o" | Нет | гггг'-'мм'-'дд'T'чч':'мм':'сс'.'fffffffzz
"R" или "r" | [RFC1123Pattern](xref:System.Globalization.DateTimeFormatInfo.RFC1123Pattern) | ддд, дд ммм гггг чч':'мм':'сс 'GMT'
"s" | [SortableDateTime](xref:System.Globalization.DateTimeFormatInfo.SortableDateTimePattern) | гггг'-'мм'-'дд'T'чч':'мм':'сс
"u" | [UniversalSortableDateTime](xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern) | гггг'-'мм'-'дд чч':'мм':'сс'Z'

В следующих разделах представлены описатели стандартных форматов для значений [DateTime](xref:System.DateTime) и [DateTimeOffset](xref:System.DateTimeOffset).

## <a name="the-short-date-d-format-specifier"></a>Описатель короткого формата даты ("d")

Описатель стандартного формата "d" представляет строку настраиваемого формата даты и времени, определяемую свойством [DateTimeFormatInfo.ShortDatePattern](xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern) для конкретного языка и региональных параметров. Например, строкой настраиваемого формата, возвращаемой свойством [ShortDatePattern](xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern) для инвариантного языка и региональных параметров, будет строка "ММ/дд/гггг". 

В следующей таблице представлены свойства объекта [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), обеспечивающие управление форматированием возвращаемой строки.
В следующем примере описатель формата "d" используется для отображения значения даты и времени.

```csharp
DateTime date1 = new DateTime(2008,4, 10);
Console.WriteLine(date1.ToString("d", DateTimeFormatInfo.InvariantInfo));
// Displays 04/10/2008
Console.WriteLine(date1.ToString("d", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays 4/10/2008                       
Console.WriteLine(date1.ToString("d", 
                  CultureInfo.CreateSpecificCulture("en-NZ")));
// Displays 10/04/2008                       
Console.WriteLine(date1.ToString("d", 
                  CultureInfo.CreateSpecificCulture("de-DE")));
// Displays 10.04.2008 
```

```vb
Dim date1 As Date = #4/10/2008#
Console.WriteLine(date1.ToString("d", DateTimeFormatInfo.InvariantInfo))
' Displays 04/10/2008
Console.WriteLine(date1.ToString("d", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays 4/10/2008                       
Console.WriteLine(date1.ToString("d", _
                  CultureInfo.CreateSpecificCulture("en-NZ")))
' Displays 10/04/2008                       
Console.WriteLine(date1.ToString("d", _
                  CultureInfo.CreateSpecificCulture("de-DE")))
' Displays 10.04.2008 
```

## <a name="the-long-date-d-format-specifier"></a>Описатель полного формата даты ("D")

Описатель стандартного формата "D" представляет строку настраиваемого формата даты и времени, определяемую текущим свойством [DateTimeFormatInfo.LongDatePattern](xref:System.Globalization.DateTimeFormatInfo.LongDatePattern). Например, строкой пользовательского формата для инвариантных региональных параметров является "дддд, дд мммм гггг".

В следующей таблице представлены свойства объекта [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), обеспечивающие управление форматированием возвращаемой строки.

Свойство | Описание
-------- | -----------
[LongDatePattern](xref:System.Globalization.DateTimeFormatInfo.LongDatePattern) | Определяет общий формат результирующей строки.
[DayNames](xref:System.Globalization.DateTimeFormatInfo.DayNames) | Определяет переведенные названия дней, которые могут входить в результирующую строку.
[MonthNames](xref:System.Globalization.DateTimeFormatInfo.MonthNames) | Определяет переведенные названия месяцев, которые могут входить в результирующую строку.

В следующем примере описатель формата "D" используется для отображения значения даты и времени.

```csharp
DateTime date1 = new DateTime(2008, 4, 10);
Console.WriteLine(date1.ToString("D", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays Thursday, April 10, 2008                        
Console.WriteLine(date1.ToString("D", 
                  CultureInfo.CreateSpecificCulture("pt-BR")));
// Displays quinta-feira, 10 de abril de 2008                        
Console.WriteLine(date1.ToString("D", 
                  CultureInfo.CreateSpecificCulture("es-MX")));
// Displays jueves, 10 de abril de 2008
```

```vb
Dim date1 As Date = #4/10/2008#
Console.WriteLine(date1.ToString("D", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays Thursday, April 10, 2008                        
Console.WriteLine(date1.ToString("D", _
                  CultureInfo.CreateSpecificCulture("pt-BR")))
' Displays quinta-feira, 10 de abril de 2008                        
Console.WriteLine(date1.ToString("D", _
                  CultureInfo.CreateSpecificCulture("es-MX")))
' Displays jueves, 10 de abril de 2008
```

## <a name="the-full-date-short-time-f-format-specifier"></a>Описатель полного формата даты и краткого формата времени ("f")

Описатель стандартного формата "f" представляет сочетание полного формата даты ("D") и короткого формата времени ("t"), разделенных пробелом.

Форматирование результирующей строки определяется сведениями о форматировании в указанном объекте [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo). В следующей таблице представлены свойства объекта [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), который может управлять форматированием возвращаемой строки. Описатель настраиваемого формата, возвращаемый свойствами [DateTimeFormatInfo.LongDatePattern](xref:System.Globalization.DateTimeFormatInfo.LongDatePattern) и [DateTimeFormatInfo.ShortTimePattern](xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern) некоторых языков и региональных параметров, может использовать не все свойства.

Свойство | Описание
-------- | -----------
[LongDatePattern](xref:System.Globalization.DateTimeFormatInfo.LongDatePattern) | Определяет формат компонента даты результирующей строки.
[ShortTimePattern](xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern) | Определяет формат компонента времени результирующей строки.
[DayNames](xref:System.Globalization.DateTimeFormatInfo.DayNames) | Определяет переведенные названия дней, которые могут входить в результирующую строку.
[MonthNames](xref:System.Globalization.DateTimeFormatInfo.MonthNames) | Определяет переведенные названия месяцев, которые могут входить в результирующую строку.
[AMDesignator](xref:System.Globalization.DateTimeFormatInfo.AMDesignator) | Определяет строку, указывающую на время в интервале от полуночи до полудня в 12-часовом формате указания времени.
[PMDesignator](xref:System.Globalization.DateTimeFormatInfo.PMDesignator) | Определяет строку, указывающую на время в интервале от полудня до полуночи в 12-часовом формате указания времени.

В следующем примере описатель формата "f" используется для отображения значения даты и времени.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("f", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays Thursday, April 10, 2008 6:30 AM                        
Console.WriteLine(date1.ToString("f", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));
// Displays jeudi 10 avril 2008 06:30 
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("f", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays Thursday, April 10, 2008 6:30 AM                        
Console.WriteLine(date1.ToString("f", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))
' Displays jeudi 10 avril 2008 06:30 
```

## <a name="the-full-date-long-time-f-format-specifier"></a>Описатель полного формата даты и полного формата времени ("F")

Описатель стандартного формата "F" представляет строку настраиваемого формата даты и времени, определяемую текущим свойством [DateTimeFormatInfo.FullDateTimePattern](xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern). Например, строкой пользовательского формата для инвариантных региональных параметров является "дддд, дд мммм гггг чч:мм:сс".

В следующей таблице представлены свойства объекта [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), который может управлять форматированием возвращаемой строки. Описатель настраиваемого формата, возвращаемый свойством [FullDateTimePattern](xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern) некоторых языков и региональных параметров, может использовать не все свойства.

Свойство | Описание
-------- | -----------
[FullDateTimePattern](xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern) | Определяет общий формат результирующей строки.
[DayNames](xref:System.Globalization.DateTimeFormatInfo.DayNames) | Определяет переведенные названия дней, которые могут входить в результирующую строку.
[MonthNames](xref:System.Globalization.DateTimeFormatInfo.MonthNames) | Определяет переведенные названия месяцев, которые могут входить в результирующую строку.
[AMDesignator](xref:System.Globalization.DateTimeFormatInfo.AMDesignator) | Определяет строку, указывающую на время в интервале от полуночи до полудня в 12-часовом формате указания времени.
[PMDesignator](xref:System.Globalization.DateTimeFormatInfo.PMDesignator) | Определяет строку, указывающую на время в интервале от полудня до полуночи в 12-часовом формате указания времени.

В следующем примере описатель формата "F" используется для отображения значения даты и времени.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("F", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays Thursday, April 10, 2008 6:30:00 AM                        
Console.WriteLine(date1.ToString("F", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));
// Displays jeudi 10 avril 2008 06:30:00 
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("F", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays Thursday, April 10, 2008 6:30:00 AM                        
Console.WriteLine(date1.ToString("F", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))
' Displays jeudi 10 avril 2008 06:30:00 
```

## <a name="the-general-date-short-time-g-format-specifier"></a>Описатель общего формата даты и краткого формата времени ("g")

Описатель стандартного формата "g" представляет сочетание краткого формата даты ("d") и краткого формата времени ("t"), разделенных пробелом.

Форматирование результирующей строки определяется сведениями о форматировании в указанном объекте [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo). В следующей таблице представлены свойства объекта [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), который может управлять форматированием возвращаемой строки. Описатель настраиваемого формата, возвращаемый свойствами [DateTimeFormatInfo.ShortDatePattern](xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern) и [DateTimeFormatInfo.ShortTimePattern](xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern) некоторых языков и региональных параметров, может использовать не все свойства.

Свойство | Описание
-------- | -----------
[ShortDatePattern](xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern) | Определяет формат компонента даты результирующей строки.
[ShortTimePattern](xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern) | Определяет формат компонента времени результирующей строки.
[AMDesignator](xref:System.Globalization.DateTimeFormatInfo.AMDesignator) | Определяет строку, указывающую на время в интервале от полуночи до полудня в 12-часовом формате указания времени.
[PMDesignator](xref:System.Globalization.DateTimeFormatInfo.PMDesignator) | Определяет строку, указывающую на время в интервале от полудня до полуночи в 12-часовом формате указания времени.

В следующем примере описатель формата "g" используется для отображения значения даты и времени. 

``` csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("g", 
                  DateTimeFormatInfo.InvariantInfo));
// Displays 04/10/2008 06:30                      
Console.WriteLine(date1.ToString("g", 
                  CultureInfo.CreateSpecificCulture("en-us")));
// Displays 4/10/2008 6:30 AM                       
Console.WriteLine(date1.ToString("g", 
                  CultureInfo.CreateSpecificCulture("fr-BE")));
// Displays 10/04/2008 6:30 
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("g", _
                  DateTimeFormatInfo.InvariantInfo))
' Displays 04/10/2008 06:30                      
Console.WriteLine(date1.ToString("g", _
                  CultureInfo.CreateSpecificCulture("en-us")))
' Displays 4/10/2008 6:30 AM                       
Console.WriteLine(date1.ToString("g", _
                  CultureInfo.CreateSpecificCulture("fr-BE")))
' Displays 10/04/2008 6:30  
```

## <a name="the-general-date-long-time-g-format-specifier"></a>Описатель общего формата даты и полного формата времени ("G")

Описатель стандартного формата "G" представляет сочетание краткого формата даты ("d") и полного формата времени ("T"), разделенных пробелом.

Форматирование результирующей строки определяется сведениями о форматировании в указанном объекте [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo). В следующей таблице представлены свойства объекта [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), который может управлять форматированием возвращаемой строки. Описатель настраиваемого формата, возвращаемый свойствами [DateTimeFormatInfo.ShortDatePattern](xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern) и [DateTimeFormatInfo.LongTimePattern](xref:System.Globalization.DateTimeFormatInfo.LongTimePattern) некоторых языков и региональных параметров, может использовать не все свойства.

Свойство | Описание
-------- | -----------
[ShortDatePattern](xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern) | Определяет формат компонента даты результирующей строки.
[LongTimePattern](xref:System.Globalization.DateTimeFormatInfo.LongTimePattern) | Определяет формат компонента времени результирующей строки.
[AMDesignator](xref:System.Globalization.DateTimeFormatInfo.AMDesignator) | Определяет строку, указывающую на время в интервале от полуночи до полудня в 12-часовом формате указания времени.
[PMDesignator](xref:System.Globalization.DateTimeFormatInfo.PMDesignator) | Определяет строку, указывающую на время в интервале от полудня до полуночи в 12-часовом формате указания времени.

В следующем примере описатель формата "G" используется для отображения значения даты и времени.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("G", 
                  DateTimeFormatInfo.InvariantInfo));
// Displays 04/10/2008 06:30:00
Console.WriteLine(date1.ToString("G", 
                  CultureInfo.CreateSpecificCulture("en-us")));
// Displays 4/10/2008 6:30:00 AM                        
Console.WriteLine(date1.ToString("G", 
                  CultureInfo.CreateSpecificCulture("nl-BE")));
// Displays 10/04/2008 6:30:00  
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("G", _
                  DateTimeFormatInfo.InvariantInfo))
' Displays 04/10/2008 06:30:00
Console.WriteLine(date1.ToString("G", _
                  CultureInfo.CreateSpecificCulture("en-us")))
' Displays 4/10/2008 6:30:00 AM                        
Console.WriteLine(date1.ToString("G", _
                  CultureInfo.CreateSpecificCulture("nl-BE")))
' Displays 10/04/2008 6:30:00                       
```

## <a name="the-month-m-m-format-specifier"></a>Описатель формата месяца ("M", "m")

Описатель стандартного формата "M" или "m" представляет строку настраиваемого формата даты и времени, определяемую текущим свойством [DateTimeFormatInfo.MonthDayPattern](xref:System.Globalization.DateTimeFormatInfo.MonthDayPattern). Например, строкой пользовательского формата для инвариантных региональных параметров является "мммм дд".

В следующей таблице представлены свойства объекта [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), обеспечивающие управление форматированием возвращаемой строки.

Свойство | Описание
-------- | -----------
[MonthDayPattern](xref:System.Globalization.DateTimeFormatInfo.MonthDayPattern) | Определяет общий формат результирующей строки.
[MonthNames](xref:System.Globalization.DateTimeFormatInfo.MonthNames) | Определяет переведенные названия месяцев, которые могут входить в результирующую строку.

В следующем примере описатель формата "m" используется для отображения значения даты и времени.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("m", 
                  CultureInfo.CreateSpecificCulture("en-us")));
// Displays April 10                        
Console.WriteLine(date1.ToString("m", 
                  CultureInfo.CreateSpecificCulture("ms-MY")));
// Displays 10 April  
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("m", _
                  CultureInfo.CreateSpecificCulture("en-us")))
' Displays April 10                        
Console.WriteLine(date1.ToString("m", _
                  CultureInfo.CreateSpecificCulture("ms-MY")))
' Displays 10 April
```

## <a name="the-roundtrip-o-o-format-specifier"></a>Описатель формата обратного преобразования ("O", "o")

Описатель формата обратного преобразования ("O", "o") представляет строку настраиваемого формата даты и времени, используя шаблон, который сохраняет данные о часовом поясе и возвращает строковое значение, соответствующее стандарту ISO 8601. Для значений [DateTime](xref:System.DateTime) этот спецификатор формата предназначен для сохранения значений даты и времени вместе со свойством [DateTime.Kind](xref:System.DateTime.Kind) в тексте. Форматированная строка может быть преобразована обратно с помощью метода [DateTime.Parse(String, IFormatProvider, DateTimeStyles)](xref:System.DateTime.Parse(System.String,System.IFormatProvider,System.Globalization.DateTimeStyles)) или [DateTime.ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles)), если для параметра styles задано значение [DateTimeStyles.RoundtripKind](xref:System.Globalization.DateTimeStyles.RoundtripKind). 

Описатель стандартного формата "O" или "o" соответствует строке настраиваемого формата "yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'fffffffK" для значений DateTime и строке настраиваемого формата "yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'fffffffzzz" — для значений [DateTimeOffset](xref:System.DateTimeOffset). В данной строке пары апострофов, разделяющие отдельные символы, такие как дефисы, двоеточия и букву "T", указывают, что отдельный символ является литералом, который не может быть изменен. Сами апострофы не отображаются в выходной строке. 

Описатель стандартного формата "O" или "o" (и строка настраиваемого формата "yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'fffffffK") использует преимущества ISO 8601, а именно три способа представления сведений о часовом поясе для сохранения свойства [Kind](xref:System.DateTime.Kind) значений [DateTime](xref:System.DateTime): 

* Компонент часового пояса значений даты и времени типа [DateTimeKind.Local](xref:System.DateTimeKind.Local) — это смещение от часового пояса от UTC (например, +01:00, -07:00). Все значения DateTimeOffset также представлены в этом формате. 

* Компонент часового пояса значений даты и времени типа [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) использует символ "Z" (т. е. нулевое смещение) для представления часового пояса UTC. 

* Значения даты и времени типа [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified) не содержат сведения о часовом поясе. 

Так как стандартный описатель формата "O" и "o" соответствует международному стандарту, операция форматирования или синтаксического анализа, использующая описатель, всегда использует инвариантный региональный параметр и грегорианский календарь. 

Строки, передаваемые методам `Parse`, `TryParse`, `ParseExact` и `TryParseExact` классов [DateTime](xref:System.DateTime) и [DateTimeOffset](xref:System.DateTimeOffset), можно анализировать с помощью описателя формата "O" или "o", если они не представлены в одном из этих форматов. Для объектов [DateTime](xref:System.DateTime) вызываемая перегрузка синтаксического анализа также должна содержать параметр styles со значением [DateTimeStyles.RoundtripKind](xref:System.Globalization.DateTimeStyles.RoundtripKind). Обратите внимание, что при вызове метода синтаксического анализа с настраиваемой строкой формата, которая соответствует описателю формата "O" или "o", вы не получите те же результаты, что при использовании описателя "O" и "o". Это вызвано тем, что методы синтаксического анализа, использующие настраиваемую строку формата, не могут обработать строковое представление значений даты и времени без компонента часового пояса и не могут использовать символ "Z" для указания часового пояса UTC. 

В следующем примере используется описатель формата "o" для отображения ряда значений [DateTime](xref:System.DateTime) и значения [DateTimeOffset](xref:System.DateTimeOffset) на компьютере в тихоокеанском стандартном часовом поясе США. 

```csharp
using System;

public class Example
{
   public static void Main()
   {
       DateTime dat = new DateTime(2009, 6, 15, 13, 45, 30, 
                                   DateTimeKind.Unspecified);
       Console.WriteLine("{0} ({1}) --> {0:O}", dat, dat.Kind); 

       DateTime uDat = new DateTime(2009, 6, 15, 13, 45, 30, 
                                    DateTimeKind.Utc);
       Console.WriteLine("{0} ({1}) --> {0:O}", uDat, uDat.Kind);

       DateTime lDat = new DateTime(2009, 6, 15, 13, 45, 30, 
                                    DateTimeKind.Local);
       Console.WriteLine("{0} ({1}) --> {0:O}\n", lDat, lDat.Kind);

       DateTimeOffset dto = new DateTimeOffset(lDat);
       Console.WriteLine("{0} --> {0:O}", dto);
   }
}
// The example displays the following output:
//    6/15/2009 1:45:30 PM (Unspecified) --> 2009-06-15T13:45:30.0000000
//    6/15/2009 1:45:30 PM (Utc) --> 2009-06-15T13:45:30.0000000Z
//    6/15/2009 1:45:30 PM (Local) --> 2009-06-15T13:45:30.0000000-07:00
//    
//    6/15/2009 1:45:30 PM -07:00 --> 2009-06-15T13:45:30.0000000-07:00
```

```vb
Module Example
   Public Sub Main()
       Dim dat As New Date(2009, 6, 15, 13, 45, 30, 
                           DateTimeKind.Unspecified)
       Console.WriteLine("{0} ({1}) --> {0:O}", dat, dat.Kind) 

       Dim uDat As New Date(2009, 6, 15, 13, 45, 30, DateTimeKind.Utc)
       Console.WriteLine("{0} ({1}) --> {0:O}", uDat, uDat.Kind)

       Dim lDat As New Date(2009, 6, 15, 13, 45, 30, DateTimeKind.Local)
       Console.WriteLine("{0} ({1}) --> {0:O}", lDat, lDat.Kind)
       Console.WriteLine()

       Dim dto As New DateTimeOffset(lDat)
       Console.WriteLine("{0} --> {0:O}", dto)
   End Sub
End Module
' The example displays the following output:
'    6/15/2009 1:45:30 PM (Unspecified) --> 2009-06-15T13:45:30.0000000
'    6/15/2009 1:45:30 PM (Utc) --> 2009-06-15T13:45:30.0000000Z
'    6/15/2009 1:45:30 PM (Local) --> 2009-06-15T13:45:30.0000000-07:00
'    
'    6/15/2009 1:45:30 PM -07:00 --> 2009-06-15T13:45:30.0000000-07:00
```

В следующем примере описатель формата "o" используется для создания форматированной строки, а затем для восстановления первоначальных значений даты и времени путем вызова метода `Parse`.

```csharp
// Round-trip DateTime values.
DateTime originalDate, newDate;
string dateString;
// Round-trip a local time.
originalDate = DateTime.SpecifyKind(new DateTime(2008, 4, 10, 6, 30, 0), DateTimeKind.Local);
dateString = originalDate.ToString("o");
newDate = DateTime.Parse(dateString, null, DateTimeStyles.RoundtripKind);
Console.WriteLine("Round-tripped {0} {1} to {2} {3}.", originalDate, originalDate.Kind, 
                  newDate, newDate.Kind);
// Round-trip a UTC time.
originalDate = DateTime.SpecifyKind(new DateTime(2008, 4, 12, 9, 30, 0), DateTimeKind.Utc);                  
dateString = originalDate.ToString("o");
newDate = DateTime.Parse(dateString, null, DateTimeStyles.RoundtripKind);
Console.WriteLine("Round-tripped {0} {1} to {2} {3}.", originalDate, originalDate.Kind, 
                  newDate, newDate.Kind);
// Round-trip time in an unspecified time zone.
originalDate = DateTime.SpecifyKind(new DateTime(2008, 4, 13, 12, 30, 0), DateTimeKind.Unspecified);                  
dateString = originalDate.ToString("o");
newDate = DateTime.Parse(dateString, null, DateTimeStyles.RoundtripKind);
Console.WriteLine("Round-tripped {0} {1} to {2} {3}.", originalDate, originalDate.Kind, 
                  newDate, newDate.Kind);

// Round-trip a DateTimeOffset value.
DateTimeOffset originalDTO = new DateTimeOffset(2008, 4, 12, 9, 30, 0, new TimeSpan(-8, 0, 0));
dateString = originalDTO.ToString("o");
DateTimeOffset newDTO = DateTimeOffset.Parse(dateString, null, DateTimeStyles.RoundtripKind);
Console.WriteLine("Round-tripped {0} to {1}.", originalDTO, newDTO);
// The example displays the following output:
//    Round-tripped 4/10/2008 6:30:00 AM Local to 4/10/2008 6:30:00 AM Local.
//    Round-tripped 4/12/2008 9:30:00 AM Utc to 4/12/2008 9:30:00 AM Utc.
//    Round-tripped 4/13/2008 12:30:00 PM Unspecified to 4/13/2008 12:30:00 PM Unspecified.
//    Round-tripped 4/12/2008 9:30:00 AM -08:00 to 4/12/2008 9:30:00 AM -08:00.
```

```vb
' Round-trip DateTime values.
Dim originalDate, newDate As Date
Dim dateString As String
' Round-trip a local time.
originalDate = Date.SpecifyKind(#4/10/2008 6:30AM#, DateTimeKind.Local)
dateString = originalDate.ToString("o")
newDate = Date.Parse(dateString, Nothing, DateTimeStyles.RoundtripKind)
Console.WriteLine("Round-tripped {0} {1} to {2} {3}.", originalDate, originalDate.Kind, _
                  newDate, newDate.Kind)
' Round-trip a UTC time.
originalDate = Date.SpecifyKind(#4/12/2008 9:30AM#, DateTimeKind.Utc)                  
dateString = originalDate.ToString("o")
newDate = Date.Parse(dateString, Nothing, DateTimeStyles.RoundtripKind)
Console.WriteLine("Round-tripped {0} {1} to {2} {3}.", originalDate, originalDate.Kind, _
                  newDate, newDate.Kind)
' Round-trip time in an unspecified time zone.
originalDate = Date.SpecifyKind(#4/13/2008 12:30PM#, DateTimeKind.Unspecified)                  
dateString = originalDate.ToString("o")
newDate = Date.Parse(dateString, Nothing, DateTimeStyles.RoundtripKind)
Console.WriteLine("Round-tripped {0} {1} to {2} {3}.", originalDate, originalDate.Kind, _
                  newDate, newDate.Kind)

' Round-trip a DateTimeOffset value.
Dim originalDTO As New DateTimeOffset(#4/12/2008 9:30AM#, New TimeSpan(-8, 0, 0))
dateString = originalDTO.ToString("o")
Dim newDTO As DateTimeOffset = DateTimeOffset.Parse(dateString, Nothing, DateTimeStyles.RoundtripKind)
Console.WriteLine("Round-tripped {0} to {1}.", originalDTO, newDTO)
' The example displays the following output:
'    Round-tripped 4/10/2008 6:30:00 AM Local to 4/10/2008 6:30:00 AM Local.
'    Round-tripped 4/12/2008 9:30:00 AM Utc to 4/12/2008 9:30:00 AM Utc.
'    Round-tripped 4/13/2008 12:30:00 PM Unspecified to 4/13/2008 12:30:00 PM Unspecified.
'    Round-tripped 4/12/2008 9:30:00 AM -08:00 to 4/12/2008 9:30:00 AM -08:00.
```

## <a name="the-rfc1123-r-r-format-specifier"></a>Описатель формата RFC1123 ("R", "r")

Описатель стандартного формата "R" или "r" представляет строку настраиваемого формата даты и времени, определяемую свойством [DateTimeFormatInfo.RFC1123Pattern](xref:System.Globalization.DateTimeFormatInfo.RFC1123Pattern). Шаблон отражает определенный стандарт. Свойство предназначено только для чтения. Таким образом, оно не изменяется в зависимости от используемых региональных параметров или предоставленного поставщика формата. Строкой пользовательского формата является "ддд, дд ммм гггг чч':'мм':'сс 'GMT'". Когда используется этот спецификатор стандартного формата, операция форматирования или разбора всегда использует инвариантные региональные параметры.

Результирующая строка обусловлена следующими свойствами объекта [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), возвращаемого свойством [DateTimeFormatInfo.InvariantInfo](xref:System.Globalization.DateTimeFormatInfo.InvariantInfo), представляющим инвариант языка и региональных параметров.

Свойство | Описание
-------- | -----------
[RFC1123Pattern](xref:System.Globalization.DateTimeFormatInfo.RFC1123Pattern) | Определяет формат результирующей строки.
[AbbreviatedDayNames](xref:System.Globalization.DateTimeFormatInfo.AbbreviatedDayNames) | Определяет сокращенные названия дней, которые могут входить в результирующую строку.
[AbbreviatedMonthNames](xref:System.Globalization.DateTimeFormatInfo.AbbreviatedMonthNames) | Определяет сокращенные названия месяцев, которые могут входить в результирующую строку.

Хотя стандарт RFC 1123 выражает время в формате UTC, операция форматирования не изменяет значение объекта [DateTime](xref:System.DateTime), подлежащего форматированию. Таким образом, необходимо преобразовать значение [DateTime](xref:System.DateTime) в UTC, вызвав метод [DateTime.ToUniversalTime](xref:System.DateTime.ToUniversalTime) до выполнения операции форматирования. В то же время для значений [DateTimeOffset](xref:System.DateTimeOffset) преобразование выполняется автоматически; нет необходимости вызывать метод [DateTimeOffset.ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime) перед операцией форматирования. 

В следующем примере используется описатель формата "r" для отображения значения [DateTime](xref:System.DateTime) и значения [DateTimeOffset](xref:System.DateTimeOffset) на компьютере в тихоокеанском стандартном часовом поясе США.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
DateTimeOffset dateOffset = new DateTimeOffset(date1, 
                            TimeZoneInfo.Local.GetUtcOffset(date1));
Console.WriteLine(date1.ToUniversalTime().ToString("r"));
// Displays Thu, 10 Apr 2008 13:30:00 GMT                       
Console.WriteLine(dateOffset.ToUniversalTime().ToString("r"));
// Displays Thu, 10 Apr 2008 13:30:00 GMT  
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Dim dateOffset As New DateTimeOffset(date1, TimeZoneInfo.Local.GetUtcOFfset(date1))
Console.WriteLine(date1.ToUniversalTime.ToString("r"))
' Displays Thu, 10 Apr 2008 13:30:00 GMT                       
Console.WriteLine(dateOffset.ToUniversalTime.ToString("r"))
' Displays Thu, 10 Apr 2008 13:30:00 GMT
```

## <a name="the-sortable-s-format-specifier"></a>Описатель сортируемого формата ("s")

Описатель стандартного формата "s" представляет строку настраиваемого формата даты и времени, определяемую свойством [DateTimeFormatInfo.SortableDateTimePattern](xref:System.Globalization.DateTimeFormatInfo.SortableDateTimePattern). Шаблон отражает определенный стандарт (ISO 8601). Свойство предназначено только для чтения. Таким образом, оно не изменяется в зависимости от используемых региональных параметров или предоставленного поставщика формата. Строкой пользовательского формата является "гггг'-'мм'-'дд'T'чч':'мм':'сс".

Описатель формата "s" предназначен для создания строк результатов, согласованно отсортированных по возрастанию или убыванию на основе значений даты и времени. Соответственно, хотя описатель стандартного формата "s" представляет значение даты и времени в согласованном формате, операция форматирования не изменяет значение объекта даты и времени, которое форматируется в соответствии с его свойством [DateTime.Kind](xref:System.DateTime.Kind) или значением [DateTimeOffset.Offset](xref:System.DateTimeOffset.Offset). Например, строки результатов, полученные при форматировании значений даты и времени 2014-11-15T18:32:17+00:00 и 2014-11-15T18:32:17+08:00, идентичны. 

Когда используется этот спецификатор стандартного формата, операция форматирования или разбора всегда использует инвариантные региональные параметры. 

В следующем примере используется описатель формата "s" для отображения значения [DateTime](xref:System.DateTime) и значения [DateTimeOffset](xref:System.DateTimeOffset) на компьютере в тихоокеанском стандартном часовом поясе США.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("s"));
// Displays 2008-04-10T06:30:00
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("s"))
' Displays 2008-04-10T06:30:00 
```

## <a name="the-short-time-t-format-specifier"></a>Описатель короткого формата времени ("t")

Описатель стандартного формата "t" представляет строку настраиваемого формата даты и времени, определяемую текущим свойством [DateTimeFormatInfo.ShortTimePattern](xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern). Например, строкой пользовательского формата для инвариантных региональных параметров является "чч:мм".

Форматирование результирующей строки определяется сведениями о форматировании в указанном объекте [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo). В следующей таблице представлены свойства объекта [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), который может управлять форматированием возвращаемой строки. Описатель настраиваемого формата, возвращаемый свойством [DateTimeFormatInfo.ShortTimePattern](xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern) некоторых языков и региональных параметров, может использовать не все свойства.

Свойство | Описание
-------- | -----------
[DateTimeFormatInfo.ShortTimePattern](xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern) | Определяет формат компонента времени результирующей строки.
[AMDesignator](xref:System.Globalization.DateTimeFormatInfo.AMDesignator) | Определяет строку, указывающую на время в интервале от полуночи до полудня в 12-часовом формате указания времени.
[PMDesignator](xref:System.Globalization.DateTimeFormatInfo.PMDesignator) | Определяет строку, указывающую на время в интервале от полудня до полуночи в 12-часовом формате указания времени.

В следующем примере описатель формата "t" используется для отображения значения даты и времени.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("t", 
                  CultureInfo.CreateSpecificCulture("en-us")));
// Displays 6:30 AM                        
Console.WriteLine(date1.ToString("t", 
                  CultureInfo.CreateSpecificCulture("es-ES")));
// Displays 6:30  
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("t", _
                  CultureInfo.CreateSpecificCulture("en-us")))
' Displays 6:30 AM                        
Console.WriteLine(date1.ToString("t", _
                  CultureInfo.CreateSpecificCulture("es-ES")))
' Displays 6:30
```

## <a name="the-long-time-t-format-specifier"></a>Описатель полного формата времени ("T")

Описатель стандартного формата "T" представляет строку настраиваемого формата даты и времени, определяемую свойством [DateTimeFormatInfo.LongTimePattern](xref:System.Globalization.DateTimeFormatInfo.LongTimePattern) для конкретного языка и региональных параметров. Например, строкой пользовательского формата для инвариантных региональных параметров является "чч:мм:сс".

В следующей таблице представлены свойства объекта [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), который может управлять форматированием возвращаемой строки. Описатель настраиваемого формата, возвращаемый свойством [DateTimeFormatInfo.LongTimePattern](xref:System.Globalization.DateTimeFormatInfo.LongTimePattern) некоторых языков и региональных параметров, может использовать не все свойства.

Свойство | Описание
-------- | -----------
[LongTimePattern](xref:System.Globalization.DateTimeFormatInfo.LongTimePattern) | Определяет формат компонента времени результирующей строки.
[AMDesignator](xref:System.Globalization.DateTimeFormatInfo.AMDesignator) | Определяет строку, указывающую на время в интервале от полуночи до полудня в 12-часовом формате указания времени.
[PMDesignator](xref:System.Globalization.DateTimeFormatInfo.PMDesignator) | Определяет строку, указывающую на время в интервале от полудня до полуночи в 12-часовом формате указания времени.

В следующем примере описатель формата "T" используется для отображения значения даты и времени.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("T", 
                  CultureInfo.CreateSpecificCulture("en-us")));
// Displays 6:30:00 AM                       
Console.WriteLine(date1.ToString("T", 
                  CultureInfo.CreateSpecificCulture("es-ES")));
// Displays 6:30:00  
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("T", _
                  CultureInfo.CreateSpecificCulture("en-us")))
' Displays 6:30:00 AM                       
Console.WriteLine(date1.ToString("T", _
                  CultureInfo.CreateSpecificCulture("es-ES")))
' Displays 6:30:00 
```

## <a name="the-universal-sortable-u-format-specifier"></a>Описатель универсального сортируемого формата ("u")

Описатель стандартного формата "u" представляет строку настраиваемого формата даты и времени, определяемую свойством [DateTimeFormatInfo.UniversalSortableDateTimePattern](xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern). Шаблон отражает определенный стандарт. Свойство предназначено только для чтения. Таким образом, оно не изменяется в зависимости от используемых региональных параметров или предоставленного поставщика формата. Строкой пользовательского формата является "гггг'-'мм'-'дд чч':'мм':'сс'Z'". Когда используется этот спецификатор стандартного формата, операция форматирования или разбора всегда использует инвариантные региональные параметры. 

Хотя результирующая строка должна отображать время в формате UTC, преобразование первоначального значения [DateTime](xref:System.DateTime) в процессе форматирования не выполняется. Таким образом, необходимо преобразовать значение [DateTime](xref:System.DateTime) в UTC, вызвав метод [DateTime.ToUniversalTime](xref:System.DateTime.ToUniversalTime) до форматирования. В то же время для значений [DateTimeOffset](xref:System.DateTimeOffset) преобразование выполняется автоматически; нет необходимости вызывать метод [DateTimeOffset.ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime) перед операцией форматирования.   

В следующем примере описатель формата "u" используется для отображения значения даты и времени.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToUniversalTime().ToString("u"));
// Displays 2008-04-10 13:30:00Z
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToUniversalTime.ToString("u"))
' Displays 2008-04-10 13:30:00Z                       
```

## <a name="the-universal-full-u-format-specifier"></a>Описатель универсального полного формата ("U")

Описатель стандартного формата "U" представляет строку настраиваемого формата даты и времени, определяемую свойством [DateTimeFormatInfo.FullDateTimePattern](xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern) для конкретного языка и региональных параметров. Этот шаблон совпадает с шаблоном "F". Тем не менее, значение [DateTime](xref:System.DateTime) автоматически преобразуется в формат UTC до форматирования.

В следующей таблице представлены свойства объекта [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), который может управлять форматированием возвращаемой строки. Описатель настраиваемого формата, возвращаемый свойством [FullDateTimePattern](xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern) некоторых языков и региональных параметров, может использовать не все свойства.

Свойство | Описание
-------- | -----------
[FullDateTimePattern](xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern) | Определяет общий формат результирующей строки.
[DayNames](xref:System.Globalization.DateTimeFormatInfo.DayNames) | Определяет переведенные названия дней, которые могут входить в результирующую строку.
[MonthNames](xref:System.Globalization.DateTimeFormatInfo.MonthNames) | Определяет переведенные названия месяцев, которые могут входить в результирующую строку.
[AMDesignator](xref:System.Globalization.DateTimeFormatInfo.AMDesignator) | Определяет строку, указывающую на время в интервале от полуночи до полудня в 12-часовом формате указания времени.
[PMDesignator](xref:System.Globalization.DateTimeFormatInfo.PMDesignator) | Определяет строку, указывающую на время в интервале от полудня до полуночи в 12-часовом формате указания времени.

Описатель формата "U" не поддерживается типом [DateTimeOffset](xref:System.DateTimeOffset) и выдает исключение [FormatException](xref:System.FormatException), если он используется для форматирования значения [DateTimeOffset](xref:System.DateTimeOffset).

В следующем примере описатель формата "U" используется для отображения значения даты и времени.

``` csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("U", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays Thursday, April 10, 2008 1:30:00 PM                       
Console.WriteLine(date1.ToString("U", 
                  CultureInfo.CreateSpecificCulture("sv-FI")));
// Displays den 10 april 2008 13:30:00  
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("U", CultureInfo.CreateSpecificCulture("en-US")))
' Displays Thursday, April 10, 2008 1:30:00 PM                       
Console.WriteLine(date1.ToString("U", CultureInfo.CreateSpecificCulture("sv-FI")))
' Displays den 10 april 2008 13:30:00                       
```

## <a name="the-year-month-y-y-format-specifier"></a>Описатель формата "год–месяц" ("Y", "y")

Описатель стандартного формата "Y" или "y" представляет строку настраиваемого формата даты и времени, определяемую свойством [DateTimeFormatInfo.YearMonthPattern](xref:System.Globalization.DateTimeFormatInfo.YearMonthPattern) для конкретного языка и региональных параметров. Например, строкой пользовательского формата для инвариантных региональных параметров является "гггг мммм".

В следующей таблице представлены свойства объекта [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), обеспечивающие управление форматированием возвращаемой строки.

Свойство | Описание
-------- | -----------
[YearMonthPattern](xref:System.Globalization.DateTimeFormatInfo.YearMonthPattern) | Определяет общий формат результирующей строки.
[MonthNames](xref:System.Globalization.DateTimeFormatInfo.MonthNames) | Определяет переведенные названия месяцев, которые могут входить в результирующую строку.

В следующем примере описатель формата "y" используется для отображения значения даты и времени.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("Y", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays April, 2008                       
Console.WriteLine(date1.ToString("y", 
                  CultureInfo.CreateSpecificCulture("af-ZA")));
// Displays April 2008 
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("Y", CultureInfo.CreateSpecificCulture("en-US")))
' Displays April, 2008                       
Console.WriteLine(date1.ToString("y", CultureInfo.CreateSpecificCulture("af-ZA")))
' Displays April 2008
```                       

## <a name="notes"></a>Примечания

### <a name="datetimeformatinfo-properties"></a>Свойства DateTimeFormatInfo

На форматирование влияют свойства текущего объекта [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), которые задаются либо неявно, языком и региональными параметрами текущего потока, либо явно, параметром [IFormatProvider](xref:System.IFormatProvider) метода, который вызывает форматирование. Для параметра [IFormatProvider](xref:System.IFormatProvider) приложение должно указать объект [CultureInfo](xref:System.Globalization.CultureInfo), представляющий региональные параметры, или объект [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), представляющий соглашения о форматировании даты и времени для конкретных региональных параметров. Многие спецификаторы стандартных форматов даты и времени являются псевдонимами для шаблонов форматирования, которые определены свойствами текущего объекта [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo). Приложение может изменить результат, полученный некоторыми спецификаторами стандартных форматов даты и времени, изменив соответствующие шаблоны форматирования соответствующего свойства [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo).

## <a name="see-also"></a>См. также

[Типы форматирования](formatting-types.md)

[Строки настраиваемых форматов даты и времени](custom-datetime.md)




<!--HONumber=Nov16_HO1-->


