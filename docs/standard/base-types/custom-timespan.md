---
title: "Строки пользовательского формата TimeSpan"
description: "Строки пользовательского формата TimeSpan"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/25/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: e79745eb-6ebd-4e62-85c4-4f2830c27285
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 168bd497891ead884413fad4542943a24de7a7f4

---

# <a name="custom-timespan-format-strings"></a>Строки пользовательского формата TimeSpan

Строка формата [TimeSpan](xref:System.TimeSpan) определяет строковое представление значения [TimeSpan](xref:System.TimeSpan), получаемого после операции форматирования. Строка настраиваемого формата состоит из одного или нескольких описателей настраиваемого формата [TimeSpan](xref:System.TimeSpan) вместе с любым числом литеральных символов. Любая строка, не являющаяся [строкой стандартного формата TimeSpan](standard-timespan.md), воспринимается как строка настраиваемого формата [TimeSpan](xref:System.TimeSpan).

> [!IMPORTANT]
> Описатели настраиваемого формата [TimeSpan](xref:System.TimeSpan) не включают разделяющие символы, то есть символы, которые отделяют дни от часов, часы от минут или секунды от долей секунд. Вместо этого эти символы должны быть включены в строку настраиваемого формата как строковые литералы. Например, строка `"dd\.hh\:mm"` определяет точку (.) как разделитель дней и часов и двоеточие (:) как разделитель часов и минут. 

> Настраиваемые описатели формата [TimeSpan](xref:System.TimeSpan) также не содержат символ знака, позволяющий различать положительные и отрицательные временные интервалы. Чтобы включить символ знака, необходимо построить строку формата с помощью условной логики. См. пример в разделе [Остальные символы](#other-characters). 

Строковые представления значений [TimeSpan](xref:System.TimeSpan) создаются вызовами перегрузок метода [TimeSpan](xref:System.TimeSpan) `ToString`, а также методами, поддерживающими составное форматирование, такими как [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)). Дополнительные сведения см. в разделах [Типы форматирования](formatting-types.md) и [Составное форматирование](composite-format.md). В следующем примере показано использование строк стандартного формата в операциях форматирования.

```csharp
using System;

public class Example
{
   public static void Main()
   {
      TimeSpan duration = new TimeSpan(1, 12, 23, 62);

      string output = null;
      output = "Time of Travel: " + duration.ToString("%d") + " days";
      Console.WriteLine(output);
      output = "Time of Travel: " + duration.ToString(xref:"dd\.hh\:mm\:ss"); 
      Console.WriteLine(output);

      Console.WriteLine("Time of Travel: {0:%d} day(s)", duration);
      Console.WriteLine("Time of Travel: {0:dd\\.hh\\:mm\\:ss} days", duration);
   }
}
// The example displays the following output:
//       Time of Travel: 1 days
//       Time of Travel: 01.12:24:02
//       Time of Travel: 1 day(s)
//       Time of Travel: 01.12:24:02 days
```

```vb
Module Example
   Public Sub Main()
      Dim duration As New TimeSpan(1, 12, 23, 62)

      Dim output As String = Nothing
      output = "Time of Travel: " + duration.ToString("%d") + " days"
      Console.WriteLine(output)
      output = "Time of Travel: " + duration.ToString("dd\.hh\:mm\:ss") 
      Console.WriteLine(output)

      Console.WriteLine("Time of Travel: {0:%d} day(s)", duration)
      Console.WriteLine("Time of Travel: {0:dd\.hh\:mm\:ss} days", duration)
   End Sub
End Module
' The example displays the following output:
'       Time of Travel: 1 days
'       Time of Travel: 01.12:24:02
'       Time of Travel: 1 day(s)
'       Time of Travel: 01.12:24:02 days
```

Строки настраиваемого формата [TimeSpan](xref:System.TimeSpan) также используется методами [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider)) и [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@)) для определения необходимого формата входных строк для операций анализа. (Анализ преобразует строковое представление значения в это значение). В следующем примере показано использование строк стандартного формата в операциях анализа.

```csharp
using System;

public class Example
{
   public static void Main()
   {
      string value = null;
      TimeSpan interval;

      value = "6";
      if (TimeSpan.TryParseExact(value, "%d", null, out interval))
         Console.WriteLine("{0} --> {1}", value, interval.ToString("c"));
      else
         Console.WriteLine("Unable to parse '{0}'", value);

      value = "16:32.05";
      if (TimeSpan.TryParseExact(value, @"mm\:ss\.ff", null, out interval))
         Console.WriteLine("{0} --> {1}", value, interval.ToString("c"));
      else
         Console.WriteLine("Unable to parse '{0}'", value);

      value= "12.035";
      if (TimeSpan.TryParseExact(value, "ss\\.fff", null, out interval))
         Console.WriteLine("{0} --> {1}", value, interval.ToString("c"));
      else
         Console.WriteLine("Unable to parse '{0}'", value);
   }
}
// The example displays the following output:
//       6 --> 6.00:00:00
//       16:32.05 --> 00:16:32.0500000
//       12.035 --> 00:00:12.0350000
```

```vb
Module Example
   Public Sub Main()
      Dim value As String = Nothing
      Dim interval As TimeSpan

      value = "6"
      If TimeSpan.TryParseExact(value, "%d", Nothing, interval) Then
         Console.WriteLine("{0} --> {1}", value, interval.ToString("c"))
      Else
         Console.WriteLine("Unable to parse '{0}'", value)
      End If

      value = "16:32.05"
      If TimeSpan.TryParseExact(value, "mm\:ss\.ff", Nothing, interval) Then
         Console.WriteLine("{0} --> {1}", value, interval.ToString("c"))
      Else
         Console.WriteLine("Unable to parse '{0}'", value)
      End If

      value= "12.035"
      If TimeSpan.TryParseExact(value, "ss\.fff", Nothing, interval) Then
         Console.WriteLine("{0} --> {1}", value, interval.ToString("c"))
      Else
         Console.WriteLine("Unable to parse '{0}'", value)
      End If
   End Sub
End Module
' The example displays the following output:
'       6 --> 6.00:00:00
'       16:32.05 --> 00:16:32.0500000
'       12.035 --> 00:00:12.0350000
```

В следующей таблице представлены описатели настраиваемых форматов даты и времени.

Описатель формата | Описание | Примеры
---------------- | ----------- | --------
"d", "%d" | Число целых дней в интервале времени. | `new TimeSpan(6, 14, 32, 17, 685):` `%d --> "6"`;  `d\.hh\:mm --> "6.14:32"`
"dd", "dddddddd" | Число целых дней в интервале времени, при необходимости дополненное предшествующими нулями. | `new TimeSpan(6, 14, 32, 17, 685):` `ddd --> "006"`; `dd\.hh\:mm --> "06.14:32"`
"h", "%h" | Число целых часов в интервале времени, не учтенных в качестве составной части дней. Нуль не предшествует однозначным числам, обозначающим часы. | `new TimeSpan(6, 14, 32, 17, 685):` `%h --> "14"`; `hh\:mm --> "14:32"`
"чч" | Число целых часов в интервале времени, не учтенных в качестве составной части дней. Однозначным числам, обозначающим часы, предшествует нуль. | `new TimeSpan(6, 14, 32, 17, 685):` `hh --> "14"`  `new TimeSpan(6, 8, 32, 17, 685):` `hh --> 08`
"m", "%m" | Число целых минут в интервале времени, не учтенных в качестве составной части часов или дней. Нуль не предшествует однозначным числам, обозначающим минуты. | `new TimeSpan(6, 14, 8, 17, 685):` `%m --> "8"`; `h\:m --> "14:8"`
"mm" | Число целых минут в интервале времени, не учтенных в качестве составной части часов или дней. Однозначным числам, обозначающим минуты, предшествует нуль. | `new TimeSpan(6, 14, 8, 17, 685):` `mm --> "08"` `new TimeSpan(6, 8, 5, 17, 685):` `d\.hh\:mm\:ss --> 6.08:05:17`
"s", "%s" | Число целых секунд в интервале времени, не учтенных в качестве составной части часов, дней или минут. Нуль не предшествует однозначным числам, обозначающим секунды. | `TimeSpan.FromSeconds(12.965):` `%s --> 12`; `s\.fff --> 12.965`
"сс" | Число целых секунд в интервале времени, не учтенных в качестве составной части часов, дней или минут. Однозначным числам, обозначающим секунды, предшествует нуль. | `TimeSpan.FromSeconds(6.965):` `ss --> 06`; `ss\.fff --> 06.965`
"f", "%f" | Десятые доли секунды в интервале времени. | `TimeSpan.FromSeconds(6.895):` `f --> 8`; `ss\.f --> 06.8`
"ff" | Сотые доли секунды в интервале времени. | `TimeSpan.FromSeconds(6.895):` `ff --> 89`; `ss\.ff --> 06.89`
"fff" | Миллисекунды в интервале времени. | `TimeSpan.FromSeconds(6.895):` `fff --> 895`; `ss\.fff --> 06.895`
"ffff" | Десятитысячные доли секунды в интервале времени. | `TimeSpan.Parse("0:0:6.8954321"):` `ffff --> 8954`; `ss\.ffff --> 06.8954`
"fffff" | Стотысячные доли секунды в интервале времени. | `TimeSpan.Parse("0:0:6.8954321"):` `ffff --> 89543`; `ss\.ffff --> 06.89543`
"ffffff" | Миллионные доли секунды в интервале времени. | `TimeSpan.Parse("0:0:6.8954321"):` `ffff --> 895432`; `ss\.ffff --> 06.895432`
"fffffff" | Десятимиллионные доли секунды (или дробные такты) в интервале времени. | `TimeSpan.Parse("0:0:6.8954321"):` `ffff --> 8954321`; `ss\.ffff --> 06.8954321`
"F", "%F" | Десятые доли секунды в интервале времени. Если цифра равна нулю, то ничего не отображается. | `TimeSpan.Parse("00:00:06.32"):` `%F: 3`  `TimeSpan.Parse("0:0:3.091"):` `ss\.F: 03.`
"FF" | Сотые доли секунды в интервале времени. Любые нули в конце дробной части или два нуля не включаются. |  `TimeSpan.Parse("00:00:06.3291791"):` `FFFFFF: 32`  `TimeSpan.Parse("0:0:3.1900000"):` `ss\.FFFFFF: 03.1`
"FFF" | Миллисекунды в интервале времени. Любые нули в конце дробной части не включаются. |  `TimeSpan.Parse("00:00:06.3291791"):` `FFFFFF: 329`  `TimeSpan.Parse("0:0:3.1900000"):` `ss\.FFFFFF: 03.1`
"FFFF" | Десятитысячные доли секунды в интервале времени. Любые нули в конце дробной части не включаются. |  `TimeSpan.Parse("00:00:06.3291791"):` `FFFFFF: 3291`  `TimeSpan.Parse("0:0:3.1900000"):` `ss\.FFFFFF: 03.1`
"FFFFF" | Стотысячные доли секунды в интервале времени. Любые нули в конце дробной части не включаются. | `TimeSpan.Parse("00:00:06.3291791"):` `FFFFFF: 32917`  `TimeSpan.Parse("0:0:3.1900000"):` `ss\.FFFFFF: 03.1`
"FFFFFF" | Миллионные доли секунды в интервале времени. Любые нули в конце дробной части не отображаются. | `TimeSpan.Parse("00:00:06.3291791"):` `FFFFFF: 329179`  `TimeSpan.Parse("0:0:3.1900000"):` `ss\.FFFFFF: 03.1`
"FFFFFFF" | Десятимиллионные доли секунды в интервале времени. Любые нули в конце дробной части или семь нулей не отображаются. | `TimeSpan.Parse("00:00:06.3291791"):` `FFFFFF: 3291791`  `TimeSpan.Parse("0:0:3.1900000"):` `ss\.FFFFFF: 03.19`
'string' | Разделитель строк-литералов | `new TimeSpan(14, 32, 17):` `hh':'mm':'ss --> "14:32:17"`
\ | Escape-символ. | `new TimeSpan(14, 32, 17):` `hh\:mm\:ss --> "14:32:17"`
Любой другой знак | Любой другой символ, не являющийся escape-символом, интерпретируется как описатель настраиваемого формата. | `new TimeSpan(14, 32, 17):` `hh\:mm\:ss --> "14:32:17"`

## <a name="the-d-custom-format-specifier"></a>Настраиваемый описатель формата "d"

Описатель настраиваемого формата "d" выводит значение свойства [TimeSpan.Days](xref:System.TimeSpan.Days), которое представляет число целых дней в интервале времени. Он выводит полное число дней в значении [TimeSpan](xref:System.TimeSpan), даже если значение состоит из нескольких цифр. Если значение свойства [TimeSpan.Days](xref:System.TimeSpan.Days) равно нулю, описатель выводит "0".

Если используется единственный описатель настраиваемого формата "d", необходимо задать "%d" для избежания неверной интерпретации в качестве строки стандартного формата. Ниже приведен пример.

```csharp
TimeSpan ts1 = new TimeSpan(16, 4, 3, 17, 250);
Console.WriteLine(ts1.ToString("%d"));
// Displays 16
```

```vb
Dim ts As New TimeSpan(16, 4, 3, 17, 250)
Console.WriteLine(ts.ToString("%d"))
' Displays 16 
```

В следующем примере показано использование описателя настраиваемого формата "d".

```csharp
TimeSpan ts2 = new TimeSpan(4, 3, 17);
Console.WriteLine(ts2.ToString(xref:"d\.hh\:mm\:ss"));

TimeSpan ts3 = new TimeSpan(3, 4, 3, 17);
Console.WriteLine(ts3.ToString(xref:"d\.hh\:mm\:ss"));
// The example displays the following output:
//       0.04:03:17
//       3.04:03:17
```

```vb
Dim ts2 As New TimeSpan(4, 3, 17)
Console.WriteLine(ts2.ToString("d\.hh\:mm\:ss"))

Dim ts3 As New TimeSpan(3, 4, 3, 17)
Console.WriteLine(ts3.ToString("d\.hh\:mm\:ss"))
' The example displays the following output:
'       0.04:03:17
'       3.04:03:17
```

## <a name="the-dddddddddd-custom-format-specifiers"></a>Описатели настраиваемого формата "dd"–"dddddddd"

Описатели настраиваемого формата "dd", "ddd", "dddd", "ddddd", "dddddd", "ddddddd" и "dddddddd" выводят значение свойства [TimeSpan.Days](xref:System.TimeSpan.Days), которое представляет число целых дней в интервале времени. 

Выходная строка включает минимальное количество знаков, заданных числом символов "d" в описателе формата; при необходимости она дополняется предшествующими нулями. Если количество цифр в числе дней превышает число символов "d" в описателе формата, в результирующей строке выводится полное число дней.

В следующем примере используются эти описатели формата для отображения строкового представления двух значений [TimeSpan](xref:System.TimeSpan). Значение компонента дней первого временного интервала равно нулю; значение компонента дней второго — 365.

```csharp
TimeSpan ts1 = new TimeSpan(0, 23, 17, 47);
TimeSpan ts2 = new TimeSpan(365, 21, 19, 45);

for (int ctr = 2; ctr <= 8; ctr++)
{
   string fmt = new String('d', ctr) + @"\.hh\:mm\:ss";
   Console.WriteLine("{0} --> {1:" + fmt + "}", fmt, ts1);  
   Console.WriteLine("{0} --> {1:" + fmt + "}", fmt, ts2);
   Console.WriteLine();
}  
// The example displays the following output:
//       dd\.hh\:mm\:ss --> 00.23:17:47
//       dd\.hh\:mm\:ss --> 365.21:19:45
//       
//       ddd\.hh\:mm\:ss --> 000.23:17:47
//       ddd\.hh\:mm\:ss --> 365.21:19:45
//       
//       dddd\.hh\:mm\:ss --> 0000.23:17:47
//       dddd\.hh\:mm\:ss --> 0365.21:19:45
//       
//       ddddd\.hh\:mm\:ss --> 00000.23:17:47
//       ddddd\.hh\:mm\:ss --> 00365.21:19:45
//       
//       dddddd\.hh\:mm\:ss --> 000000.23:17:47
//       dddddd\.hh\:mm\:ss --> 000365.21:19:45
//       
//       ddddddd\.hh\:mm\:ss --> 0000000.23:17:47
//       ddddddd\.hh\:mm\:ss --> 0000365.21:19:45
//       
//       dddddddd\.hh\:mm\:ss --> 00000000.23:17:47
//       dddddddd\.hh\:mm\:ss --> 00000365.21:19:45
```

```vb
Dim ts1 As New TimeSpan(0, 23, 17, 47)
Dim ts2 As New TimeSpan(365, 21, 19, 45)

For ctr As Integer = 2 To 8
   Dim fmt As String = New String("d"c, ctr) + "\.hh\:mm\:ss"
   Console.WriteLine("{0} --> {1:" + fmt + "}", fmt, ts1) 
   Console.WriteLine("{0} --> {1:" + fmt + "}", fmt, ts2)
   Console.WriteLine()
Next  
' The example displays the following output:
'       dd\.hh\:mm\:ss --> 00.23:17:47
'       dd\.hh\:mm\:ss --> 365.21:19:45
'       
'       ddd\.hh\:mm\:ss --> 000.23:17:47
'       ddd\.hh\:mm\:ss --> 365.21:19:45
'       
'       dddd\.hh\:mm\:ss --> 0000.23:17:47
'       dddd\.hh\:mm\:ss --> 0365.21:19:45
'       
'       ddddd\.hh\:mm\:ss --> 00000.23:17:47
'       ddddd\.hh\:mm\:ss --> 00365.21:19:45
'       
'       dddddd\.hh\:mm\:ss --> 000000.23:17:47
'       dddddd\.hh\:mm\:ss --> 000365.21:19:45
'       
'       ddddddd\.hh\:mm\:ss --> 0000000.23:17:47
'       ddddddd\.hh\:mm\:ss --> 0000365.21:19:45
'       
'       dddddddd\.hh\:mm\:ss --> 00000000.23:17:47
'       dddddddd\.hh\:mm\:ss --> 00000365.21:19:45
```

## <a name="the-h-custom-format-specifier"></a>Настраиваемый описатель формата "h"

Описатель настраиваемого формата "h" выводит значение свойства [TimeSpan.Hours](xref:System.TimeSpan.Hours), которое представляет число целых часов в интервале времени. Он возвращает однозначное строковое значение, если свойство [TimeSpan.Hours](xref:System.TimeSpan.Hours) имеет значение от 0 до 9, и возвращает двузначное строковое значение, если значение свойства [TimeSpan.Hours](xref:System.TimeSpan.Hours) находится в диапазоне от 10 до 23.

Если используется единственный описатель настраиваемого формата "h", необходимо задать "%h" для избежания неверной интерпретации в качестве строки стандартного формата. Ниже приведен пример.

```csharp
TimeSpan ts = new TimeSpan(3, 42, 0);
Console.WriteLine("{0:%h} hours {0:%m} minutes", ts);
// The example displays the following output:
//       3 hours 42 minutes
```

```vb
Dim ts As New TimeSpan(3, 42, 0)
Console.WriteLine("{0:%h} hours {0:%m} minutes", ts)
' The example displays the following output:
'       3 hours 42 minutes
```

Как правило, в операции анализа входная строка, которая содержит только одно число, интерпретируется как число дней. Можно использовать описатель настраиваемого формата "%h" вместо того, чтобы интерпретировать числовую строку как количество часов. Ниже приведен пример.

```csharp
string value = "8";
TimeSpan interval;
if (TimeSpan.TryParseExact(value, "%h", null, out interval))
   Console.WriteLine(interval.ToString("c"));
else
   Console.WriteLine("Unable to convert '{0}' to a time interval", 
                     value);   
// The example displays the following output:
//       08:00:00
```

```vb
Dim value As String = "8"
Dim interval As TimeSpan
If TimeSpan.TryParseExact(value, "%h", Nothing, interval) Then
   Console.WriteLine(interval.ToString("c"))
Else
   Console.WriteLine("Unable to convert '{0}' to a time interval", 
                     value)   
End If   
' The example displays the following output:
'       08:00:00
```

В следующем примере показано использование описателя настраиваемого формата "h".

```csharp
TimeSpan ts1 = new TimeSpan(14, 3, 17);
Console.WriteLine(ts1.ToString(xref:"d\.h\:mm\:ss"));

TimeSpan ts2 = new TimeSpan(3, 4, 3, 17);
Console.WriteLine(ts2.ToString(xref:"d\.h\:mm\:ss"));
// The example displays the following output:
//       0.14:03:17
//       3.4:03:17
```

```vb
Dim ts1 As New TimeSpan(14, 3, 17)
Console.WriteLine(ts1.ToString("d\.h\:mm\:ss"))

Dim ts2 As New TimeSpan(3, 4, 3, 17)
Console.WriteLine(ts2.ToString("d\.h\:mm\:ss"))
' The example displays the following output:
'       0.14:03:17
'       3.4:03:17
```

## <a name="the-hh-custom-format-specifier"></a>Настраиваемый описатель формата "hh"

Описатель настраиваемого формата "hh" выводит значение свойства [TimeSpan.Hours](xref:System.TimeSpan.Hours), представляющего число целых часов в интервале времени, который не учитывается в качестве части его дневного компонента. Выходная строка включает предшествующий нуль для значений от 0 до 9. 

Как правило, в операции анализа входная строка, которая содержит только одно число, интерпретируется как число дней. Можно использовать описатель настраиваемого формата "hh" вместо того, чтобы интерпретировать числовую строку как количество часов. Ниже приведен пример.

```csharp
string value = "08";
TimeSpan interval;
if (TimeSpan.TryParseExact(value, "hh", null, out interval))
   Console.WriteLine(interval.ToString("c"));
else
   Console.WriteLine("Unable to convert '{0}' to a time interval", 
                     value);   
// The example displays the following output:
//       08:00:00 
```

```vb
Dim value As String = "08"
Dim interval As TimeSpan
If TimeSpan.TryParseExact(value, "hh", Nothing, interval) Then
   Console.WriteLine(interval.ToString("c"))
Else
   Console.WriteLine("Unable to convert '{0}' to a time interval", 
                     value)   
End If   
' The example displays the following output:
'       08:00:00
```

В следующем примере показано использование описателя настраиваемого формата "hh".

```csharp
TimeSpan ts1 = new TimeSpan(14, 3, 17);
Console.WriteLine(ts1.ToString(xref:"d\.hh\:mm\:ss"));

TimeSpan ts2 = new TimeSpan(3, 4, 3, 17);
Console.WriteLine(ts2.ToString(xref:"d\.hh\:mm\:ss"));
// The example displays the following output:
//       0.14:03:17
//       3.04:03:17
```

```vb
Dim ts1 As New TimeSpan(14, 3, 17)
Console.WriteLine(ts1.ToString("d\.hh\:mm\:ss"))

Dim ts2 As New TimeSpan(3, 4, 3, 17)
Console.WriteLine(ts2.ToString("d\.hh\:mm\:ss"))
' The example displays the following output:
'       0.14:03:17
'       3.04:03:17
```

## <a name="the-m-custom-format-specifier"></a>Настраиваемый описатель формата "m"

Описатель настраиваемого формата "m" выводит значение свойства [TimeSpan.Minutes](xref:System.TimeSpan.Minutes), представляющего число целых минут в интервале времени, который не учитывается в качестве части его дневного компонента. Он возвращает однозначное строковое значение, если свойство [TimeSpan.Minutes](xref:System.TimeSpan.Minutes) имеет значение от 0 до 9, и возвращает двузначное строковое значение, если значение свойства [TimeSpan.Minutes](xref:System.TimeSpan.Minutes) находится в диапазоне от 10 до 59.

Если используется единственный описатель настраиваемого формата "m", необходимо задать "%m" для избежания неверной интерпретации в качестве строки стандартного формата. Ниже приведен пример.

```csharp
TimeSpan ts = new TimeSpan(3, 42, 0);
Console.WriteLine("{0:%h} hours {0:%m} minutes", ts);
// The example displays the following output:
//       3 hours 42 minutes
```

```vb
Dim ts As New TimeSpan(3, 42, 0)
Console.WriteLine("{0:%h} hours {0:%m} minutes", ts)
' The example displays the following output:
'       3 hours 42 minutes
```

Как правило, в операции анализа входная строка, которая содержит только одно число, интерпретируется как число дней. Можно использовать описатель настраиваемого формата "%m" вместо того, чтобы интерпретировать числовую строку как количество часов. Ниже приведен пример.

```csharp
string value = "3";
TimeSpan interval;
if (TimeSpan.TryParseExact(value, "%m", null, out interval))
   Console.WriteLine(interval.ToString("c"));
else
   Console.WriteLine("Unable to convert '{0}' to a time interval", 
                     value);   
// The example displays the following output:
//       00:03:00
```

```vb
Dim value As String = "3"
Dim interval As TimeSpan
If TimeSpan.TryParseExact(value, "%m", Nothing, interval) Then
   Console.WriteLine(interval.ToString("c"))
Else
   Console.WriteLine("Unable to convert '{0}' to a time interval", 
                     value)   
End If   
' The example displays the following output:
'       00:03:00                              
```

В следующем примере показано использование описателя настраиваемого формата "m".

```csharp
TimeSpan ts1 = new TimeSpan(0, 6, 32);
Console.WriteLine("{0:m\\:ss} minutes", ts1);

TimeSpan ts2 = new TimeSpan(3, 4, 3, 17);
Console.WriteLine("Elapsed time: {0:m\\:ss}", ts2);
// The example displays the following output:
//       6:32 minutes
//       Elapsed time: 18:44
```

```vb
Dim ts1 As New TimeSpan(0, 6, 32)
Console.WriteLine("{0:m\:ss} minutes", ts1)

Dim ts2 As New TimeSpan(0, 18, 44)
Console.WriteLine("Elapsed time: {0:m\:ss}", ts2)
' The example displays the following output:
'       6:32 minutes
'       Elapsed time: 18:44
```

## <a name="the-mm-custom-format-specifier"></a>Настраиваемый описатель формата "mm"

Описатель настраиваемого формата "mm" выводит значение свойства [TimeSpan.Minutes](xref:System.TimeSpan.Minutes), представляющего число целых минут в интервале времени, который не учитывается в качестве части его дневного компонента. Выходная строка включает предшествующий нуль для значений от 0 до 9. 

Как правило, в операции анализа входная строка, которая содержит только одно число, интерпретируется как число дней. Можно использовать описатель настраиваемого формата "mm" вместо того, чтобы интерпретировать числовую строку как количество минут. Ниже приведен пример.

```csharp
string value = "07";
TimeSpan interval;
if (TimeSpan.TryParseExact(value, "mm", null, out interval))
   Console.WriteLine(interval.ToString("c"));
else
   Console.WriteLine("Unable to convert '{0}' to a time interval", 
                     value);   
// The example displays the following output:
//       00:07:00
```

```vb
Dim value As String = "05"
Dim interval As TimeSpan
If TimeSpan.TryParseExact(value, "mm", Nothing, interval) Then
   Console.WriteLine(interval.ToString("c"))
Else
   Console.WriteLine("Unable to convert '{0}' to a time interval", 
                     value)   
End If   
' The example displays the following output:
'       00:05:00
```

В следующем примере показано использование описателя настраиваемого формата "mm".

```csharp
TimeSpan departTime = new TimeSpan(11, 12, 00);
TimeSpan arriveTime = new TimeSpan(16, 28, 00);
Console.WriteLine("Travel time: {0:hh\\:mm}", 
                  arriveTime - departTime);
// The example displays the following output:
//       Travel time: 05:16
```

```vb
Dim departTime As New TimeSpan(11, 12, 00)
Dim arriveTime As New TimeSpan(16, 28, 00)
Console.WriteLine("Travel time: {0:hh\:mm}", 
                  arriveTime - departTime)
' The example displays the following output:
'       Travel time: 05:16
```

## <a name="the-s-custom-format-specifier"></a>Настраиваемый описатель формата "s"

Описатель настраиваемого формата "s" выводит значение свойства [TimeSpan.Seconds](xref:System.TimeSpan.Seconds), представляющего число целых секунд в интервале времени, который не учитывается в качестве части его дневного компонента. Он возвращает однозначное строковое значение, если свойство [TimeSpan.Seconds](xref:System.TimeSpan.Seconds) имеет значение от 0 до 9, и возвращает двузначное строковое значение, если значение свойства [TimeSpan.Seconds](xref:System.TimeSpan.Seconds) находится в диапазоне от 10 до 59. 

Если используется единственный описатель настраиваемого формата "s", необходимо задать "%s" для избежания неверной интерпретации в качестве строки стандартного формата. Ниже приведен пример.

```csharp
TimeSpan ts = TimeSpan.FromSeconds(12.465);
Console.WriteLine(ts.ToString("%s"));
// The example displays the following output:
//       12
```

```vb
Dim ts As TimeSpan = TimeSpan.FromSeconds(12.465)
Console.WriteLine(ts.ToString("%s"))
' The example displays the following output:
'       12
```

Как правило, в операции анализа входная строка, которая содержит только одно число, интерпретируется как число дней. Можно использовать описатель настраиваемого формата "%s" вместо того, чтобы интерпретировать числовую строку как количество секунд. Ниже приведен пример.

```csharp
string value = "9";
TimeSpan interval;
if (TimeSpan.TryParseExact(value, "%s", null, out interval))
   Console.WriteLine(interval.ToString("c"));
else
   Console.WriteLine("Unable to convert '{0}' to a time interval", 
                     value);   
// The example displays the following output:
//       00:00:09
```

```vb
Dim value As String = "9"
Dim interval As TimeSpan
If TimeSpan.TryParseExact(value, "%s", Nothing, interval) Then
   Console.WriteLine(interval.ToString("c"))
Else
   Console.WriteLine("Unable to convert '{0}' to a time interval", 
                     value)   
End If   
' The example displays the following output:
'       00:00:09
```

В следующем примере показано использование описателя настраиваемого формата "s".

```csharp
TimeSpan startTime = new TimeSpan(0, 12, 30, 15, 0);
TimeSpan endTime = new TimeSpan(0, 12, 30, 21, 3);
Console.WriteLine(xref:"Elapsed Time: {0:s\:fff} seconds", 
                  endTime - startTime);
// The example displays the following output:
//       Elapsed Time: 6:003 seconds      
```

```vb
Dim startTime As New TimeSpan(0, 12, 30, 15, 0)
Dim endTime As New TimeSpan(0, 12, 30, 21, 3)
Console.WriteLine("Elapsed Time: {0:s\:fff} seconds", 
                  endTime - startTime)
' The example displays the following output:
'       Elapsed Time: 6:003 seconds
```

## <a name="the-ss-custom-format-specifier"></a>Настраиваемый описатель формата "ss"

Описатель настраиваемого формата "ss" выводит значение свойства [TimeSpan.Seconds](xref:System.TimeSpan.Seconds), представляющего число целых секунд в интервале времени, который не учитывается в качестве части его дневного компонента. Выходная строка включает предшествующий нуль для значений от 0 до 9. 

Как правило, в операции анализа входная строка, которая содержит только одно число, интерпретируется как число дней. Можно использовать описатель настраиваемого формата "ss" вместо того, чтобы интерпретировать числовую строку как количество секунд. Ниже приведен пример.

```csharp
string[] values = { "49", "9", "06" };
TimeSpan interval;
foreach (string value in values)
{
   if (TimeSpan.TryParseExact(value, "ss", null, out interval))
      Console.WriteLine(interval.ToString("c"));
   else
      Console.WriteLine("Unable to convert '{0}' to a time interval", 
                        value);   
}
// The example displays the following output:
//       00:00:49
//       Unable to convert '9' to a time interval
//       00:00:06
```

```vb
Dim values() As String = { "49", "9", "06" }
Dim interval As TimeSpan
For Each value As String In values
   If TimeSpan.TryParseExact(value, "ss", Nothing, interval) Then
      Console.WriteLine(interval.ToString("c"))
   Else
      Console.WriteLine("Unable to convert '{0}' to a time interval", 
                        value)   
   End If   
Next   
' The example displays the following output:
'       00:00:49
'       Unable to convert '9' to a time interval
'       00:00:06
```

В следующем примере показано использование описателя настраиваемого формата "ss".

```csharp
TimeSpan interval1 = TimeSpan.FromSeconds(12.60);
Console.WriteLine(interval1.ToString(xref:"ss\.fff"));

TimeSpan interval2 = TimeSpan.FromSeconds(6.485);
Console.WriteLine(interval2.ToString(xref:"ss\.fff"));
// The example displays the following output:
//       12.600
//       06.485
```

```vb
Dim interval1 As TimeSpan = TimeSpan.FromSeconds(12.60)
Console.WriteLine(interval1.ToString("ss\.fff"))
Dim interval2 As TimeSpan = TimeSpan.FromSeconds(6.485)
Console.WriteLine(interval2.ToString("ss\.fff"))
' The example displays the following output:
'       12.600
'       06.485
```

## <a name="the-f-custom-format-specifier"></a>Настраиваемый описатель формата "f"

Описатель настраиваемого формата "f" выводит десятые доли секунды в интервале времени. В операции форматирования все оставшиеся цифры дробной части усекаются. В операции анализа, которая вызывает метод [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider)) или [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@)), входная строка должна содержать только одну дробную цифру. 

Если используется единственный описатель настраиваемого формата "f", необходимо задать "%f" для избежания неверной интерпретации в качестве строки стандартного формата.

В следующем примере описатель настраиваемого формата "f" используется для отображения десятых долей секунды в значении [TimeSpan](xref:System.TimeSpan). "f" используется сначала только как описатель формата, а затем объединяется с описателем "s" в строке настраиваемого формата.

```csharp
TimeSpan ts = new TimeSpan(1003498765432);
string fmt;
Console.WriteLine(ts.ToString("c"));
Console.WriteLine();

for (int ctr = 1; ctr <= 7; ctr++) {
   fmt = new String('f', ctr);
   if (fmt.Length == 1) fmt = "%" + fmt;
   Console.WriteLine("{0,10}: {1:" + fmt + "}", fmt, ts);
} 
Console.WriteLine();

for (int ctr = 1; ctr <= 7; ctr++) {
   fmt = new String('f', ctr);
   Console.WriteLine("{0,10}: {1:s\\." + fmt + "}", "s\\." + fmt, ts);
}
// The example displays the following output:
//               %f: 8
//               ff: 87
//              fff: 876
//             ffff: 8765
//            fffff: 87654
//           ffffff: 876543
//          fffffff: 8765432
//       
//              s\.f: 29.8
//             s\.ff: 29.87
//            s\.fff: 29.876
//           s\.ffff: 29.8765
//          s\.fffff: 29.87654
//         s\.ffffff: 29.876543
//        s\.fffffff: 29.8765432
```

```vb
Dim ts As New TimeSpan(1003498765432)
Dim fmt As String
Console.WriteLine(ts.ToString("c"))
Console.WriteLine()

For ctr = 1 To 7
   fmt = New String("f"c, ctr)
   If fmt.Length = 1 Then fmt = "%" + fmt
   Console.WriteLine("{0,10}: {1:" + fmt + "}", fmt, ts)
Next 
Console.WriteLine()

For ctr = 1 To 7
   fmt = New String("f"c, ctr)
   Console.WriteLine("{0,10}: {1:s\." + fmt + "}", "s\." + fmt, ts)
Next
' The example displays the following output:
'            %f: 8
'            ff: 87
'           fff: 876
'          ffff: 8765
'         fffff: 87654
'        ffffff: 876543
'       fffffff: 8765432
'    
'           s\.f: 29.8
'          s\.ff: 29.87
'         s\.fff: 29.876
'        s\.ffff: 29.8765
'       s\.fffff: 29.87654
'      s\.ffffff: 29.876543
'     s\.fffffff: 29.8765432
```

## <a name="the-ff-custom-format-specifier"></a>Настраиваемый описатель формата "ff"

Описатель настраиваемого формата "ff" выводит сотые доли секунды в интервале времени. В операции форматирования все оставшиеся цифры дробной части усекаются. В операции анализа, которая вызывает метод [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider)) или [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@)), входная строка должна содержать только две дробные цифры. 

В следующем примере описатель настраиваемого формата "ff" используется для отображения сотых долей секунды в значении [TimeSpan](xref:System.TimeSpan). "ff" используется сначала только как описатель формата, а затем объединяется с описателем "s" в строке настраиваемого формата.

```csharp
TimeSpan ts = new TimeSpan(1003498765432);
string fmt;
Console.WriteLine(ts.ToString("c"));
Console.WriteLine();

for (int ctr = 1; ctr <= 7; ctr++) {
   fmt = new String('f', ctr);
   if (fmt.Length == 1) fmt = "%" + fmt;
   Console.WriteLine("{0,10}: {1:" + fmt + "}", fmt, ts);
} 
Console.WriteLine();

for (int ctr = 1; ctr <= 7; ctr++) {
   fmt = new String('f', ctr);
   Console.WriteLine("{0,10}: {1:s\\." + fmt + "}", "s\\." + fmt, ts);
}
// The example displays the following output:
//               %f: 8
//               ff: 87
//              fff: 876
//             ffff: 8765
//            fffff: 87654
//           ffffff: 876543
//          fffffff: 8765432
//       
//              s\.f: 29.8
//             s\.ff: 29.87
//            s\.fff: 29.876
//           s\.ffff: 29.8765
//          s\.fffff: 29.87654
//         s\.ffffff: 29.876543
//        s\.fffffff: 29.8765432
```

```vb
Dim ts As New TimeSpan(1003498765432)
Dim fmt As String
Console.WriteLine(ts.ToString("c"))
Console.WriteLine()

For ctr = 1 To 7
   fmt = New String("f"c, ctr)
   If fmt.Length = 1 Then fmt = "%" + fmt
   Console.WriteLine("{0,10}: {1:" + fmt + "}", fmt, ts)
Next 
Console.WriteLine()

For ctr = 1 To 7
   fmt = New String("f"c, ctr)
   Console.WriteLine("{0,10}: {1:s\." + fmt + "}", "s\." + fmt, ts)
Next
' The example displays the following output:
'            %f: 8
'            ff: 87
'           fff: 876
'          ffff: 8765
'         fffff: 87654
'        ffffff: 876543
'       fffffff: 8765432
'    
'           s\.f: 29.8
'          s\.ff: 29.87
'         s\.fff: 29.876
'        s\.ffff: 29.8765
'       s\.fffff: 29.87654
'      s\.ffffff: 29.876543
'     s\.fffffff: 29.8765432
```

## <a name="the-fff-custom-format-specifier"></a>Настраиваемый описатель формата "fff"

Описатель настраиваемого формата "fff" (c тремя символами "f") выводит миллисекунды в интервале времени. В операции форматирования все оставшиеся цифры дробной части усекаются. В операции анализа, которая вызывает метод [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider)) или [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@)), входная строка должна содержать только три дробные цифры. 

В следующем примере описатель настраиваемого формата "fff" используется для отображения миллисекунд в значении [TimeSpan](xref:System.TimeSpan). "fff" используется сначала только как описатель формата, а затем объединяется с описателем "s" в строке настраиваемого формата.

```csharp
TimeSpan ts = new TimeSpan(1003498765432);
string fmt;
Console.WriteLine(ts.ToString("c"));
Console.WriteLine();

for (int ctr = 1; ctr <= 7; ctr++) {
   fmt = new String('f', ctr);
   if (fmt.Length == 1) fmt = "%" + fmt;
   Console.WriteLine("{0,10}: {1:" + fmt + "}", fmt, ts);
} 
Console.WriteLine();

for (int ctr = 1; ctr <= 7; ctr++) {
   fmt = new String('f', ctr);
   Console.WriteLine("{0,10}: {1:s\\." + fmt + "}", "s\\." + fmt, ts);
}
// The example displays the following output:
//               %f: 8
//               ff: 87
//              fff: 876
//             ffff: 8765
//            fffff: 87654
//           ffffff: 876543
//          fffffff: 8765432
//       
//              s\.f: 29.8
//             s\.ff: 29.87
//            s\.fff: 29.876
//           s\.ffff: 29.8765
//          s\.fffff: 29.87654
//         s\.ffffff: 29.876543
//        s\.fffffff: 29.8765432
```

```vb
Dim ts As New TimeSpan(1003498765432)
Dim fmt As String
Console.WriteLine(ts.ToString("c"))
Console.WriteLine()

For ctr = 1 To 7
   fmt = New String("f"c, ctr)
   If fmt.Length = 1 Then fmt = "%" + fmt
   Console.WriteLine("{0,10}: {1:" + fmt + "}", fmt, ts)
Next 
Console.WriteLine()

For ctr = 1 To 7
   fmt = New String("f"c, ctr)
   Console.WriteLine("{0,10}: {1:s\." + fmt + "}", "s\." + fmt, ts)
Next
' The example displays the following output:
'            %f: 8
'            ff: 87
'           fff: 876
'          ffff: 8765
'         fffff: 87654
'        ffffff: 876543
'       fffffff: 8765432
'    
'           s\.f: 29.8
'          s\.ff: 29.87
'         s\.fff: 29.876
'        s\.ffff: 29.8765
'       s\.fffff: 29.87654
'      s\.ffffff: 29.876543
'     s\.fffffff: 29.8765432
```

## <a name="the-ffff-custom-format-specifier"></a>Настраиваемый описатель формата "ffff"
Описатель настраиваемого формата "ffff" (с четырьмя символами "f") выводит десятитысячные доли секунды в интервале времени. В операции форматирования все оставшиеся цифры дробной части усекаются. В операции анализа, которая вызывает метод [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider)) или [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@)), входная строка должна содержать только четыре дробные цифры. 

В следующем примере описатель настраиваемого формата "fffff" используется для отображения десятитысячных долей секунды в значении [TimeSpan](xref:System.TimeSpan). "ffff" используется сначала только как описатель формата, а затем объединяется с описателем "s" в строке настраиваемого формата.

```csharp
TimeSpan ts = new TimeSpan(1003498765432);
string fmt;
Console.WriteLine(ts.ToString("c"));
Console.WriteLine();

for (int ctr = 1; ctr <= 7; ctr++) {
   fmt = new String('f', ctr);
   if (fmt.Length == 1) fmt = "%" + fmt;
   Console.WriteLine("{0,10}: {1:" + fmt + "}", fmt, ts);
} 
Console.WriteLine();

for (int ctr = 1; ctr <= 7; ctr++) {
   fmt = new String('f', ctr);
   Console.WriteLine("{0,10}: {1:s\\." + fmt + "}", "s\\." + fmt, ts);
}
// The example displays the following output:
//               %f: 8
//               ff: 87
//              fff: 876
//             ffff: 8765
//            fffff: 87654
//           ffffff: 876543
//          fffffff: 8765432
//       
//              s\.f: 29.8
//             s\.ff: 29.87
//            s\.fff: 29.876
//           s\.ffff: 29.8765
//          s\.fffff: 29.87654
//         s\.ffffff: 29.876543
//        s\.fffffff: 29.8765432
```

```vb
Dim ts As New TimeSpan(1003498765432)
Dim fmt As String
Console.WriteLine(ts.ToString("c"))
Console.WriteLine()

For ctr = 1 To 7
   fmt = New String("f"c, ctr)
   If fmt.Length = 1 Then fmt = "%" + fmt
   Console.WriteLine("{0,10}: {1:" + fmt + "}", fmt, ts)
Next 
Console.WriteLine()

For ctr = 1 To 7
   fmt = New String("f"c, ctr)
   Console.WriteLine("{0,10}: {1:s\." + fmt + "}", "s\." + fmt, ts)
Next
' The example displays the following output:
'            %f: 8
'            ff: 87
'           fff: 876
'          ffff: 8765
'         fffff: 87654
'        ffffff: 876543
'       fffffff: 8765432
'    
'           s\.f: 29.8
'          s\.ff: 29.87
'         s\.fff: 29.876
'        s\.ffff: 29.8765
'       s\.fffff: 29.87654
'      s\.ffffff: 29.876543
'     s\.fffffff: 29.8765432
```

## <a name="the-fffff-custom-format-specifier"></a>Настраиваемый описатель формата "fffff"
Описатель настраиваемого формата "fffff" (с пятью символами "f") выводит стотысячные доли секунды в интервале времени. В операции форматирования все оставшиеся цифры дробной части усекаются. В операции анализа, которая вызывает метод [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider)) или [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@)), входная строка должна содержать только пять дробных цифр. 

В следующем примере описатель настраиваемого формата "fffff" используется для отображения стотысячных долей секунды в значении [TimeSpan](xref:System.TimeSpan). "fffff" используется сначала только как описатель формата, а затем объединяется с описателем "s" в строке настраиваемого формата.

```csharp
TimeSpan ts = new TimeSpan(1003498765432);
string fmt;
Console.WriteLine(ts.ToString("c"));
Console.WriteLine();

for (int ctr = 1; ctr <= 7; ctr++) {
   fmt = new String('f', ctr);
   if (fmt.Length == 1) fmt = "%" + fmt;
   Console.WriteLine("{0,10}: {1:" + fmt + "}", fmt, ts);
} 
Console.WriteLine();

for (int ctr = 1; ctr <= 7; ctr++) {
   fmt = new String('f', ctr);
   Console.WriteLine("{0,10}: {1:s\\." + fmt + "}", "s\\." + fmt, ts);
}
// The example displays the following output:
//               %f: 8
//               ff: 87
//              fff: 876
//             ffff: 8765
//            fffff: 87654
//           ffffff: 876543
//          fffffff: 8765432
//       
//              s\.f: 29.8
//             s\.ff: 29.87
//            s\.fff: 29.876
//           s\.ffff: 29.8765
//          s\.fffff: 29.87654
//         s\.ffffff: 29.876543
//        s\.fffffff: 29.8765432 
```

```vb
Dim ts As New TimeSpan(1003498765432)
Dim fmt As String
Console.WriteLine(ts.ToString("c"))
Console.WriteLine()

For ctr = 1 To 7
   fmt = New String("f"c, ctr)
   If fmt.Length = 1 Then fmt = "%" + fmt
   Console.WriteLine("{0,10}: {1:" + fmt + "}", fmt, ts)
Next 
Console.WriteLine()

For ctr = 1 To 7
   fmt = New String("f"c, ctr)
   Console.WriteLine("{0,10}: {1:s\." + fmt + "}", "s\." + fmt, ts)
Next
' The example displays the following output:
'            %f: 8
'            ff: 87
'           fff: 876
'          ffff: 8765
'         fffff: 87654
'        ffffff: 876543
'       fffffff: 8765432
'    
'           s\.f: 29.8
'          s\.ff: 29.87
'         s\.fff: 29.876
'        s\.ffff: 29.8765
'       s\.fffff: 29.87654
'      s\.ffffff: 29.876543
'     s\.fffffff: 29.8765432
```

## <a name="the-ffffff-custom-format-specifier"></a>Настраиваемый описатель формата "ffffff"

Описатель настраиваемого формата "ffffff" (с шестью символами "f") выводит миллионные доли секунды в интервале времени. В операции форматирования все оставшиеся цифры дробной части усекаются. В операции анализа, которая вызывает метод [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider)) или [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@)), входная строка должна содержать только шесть дробных цифр. 

В следующем примере описатель настраиваемого формата "ffffff" используется для отображения миллионных долей секунды в значении [TimeSpan](xref:System.TimeSpan). Он используется сначала только как описатель формата, а затем объединяется с описателем "s" в строке настраиваемого формата.

```csharp
TimeSpan ts = new TimeSpan(1003498765432);
string fmt;
Console.WriteLine(ts.ToString("c"));
Console.WriteLine();

for (int ctr = 1; ctr <= 7; ctr++) {
   fmt = new String('f', ctr);
   if (fmt.Length == 1) fmt = "%" + fmt;
   Console.WriteLine("{0,10}: {1:" + fmt + "}", fmt, ts);
} 
Console.WriteLine();

for (int ctr = 1; ctr <= 7; ctr++) {
   fmt = new String('f', ctr);
   Console.WriteLine("{0,10}: {1:s\\." + fmt + "}", "s\\." + fmt, ts);
}
// The example displays the following output:
//               %f: 8
//               ff: 87
//              fff: 876
//             ffff: 8765
//            fffff: 87654
//           ffffff: 876543
//          fffffff: 8765432
//       
//              s\.f: 29.8
//             s\.ff: 29.87
//            s\.fff: 29.876
//           s\.ffff: 29.8765
//          s\.fffff: 29.87654
//         s\.ffffff: 29.876543
//        s\.fffffff: 29.8765432 
```

```vb
Dim ts As New TimeSpan(1003498765432)
Dim fmt As String
Console.WriteLine(ts.ToString("c"))
Console.WriteLine()

For ctr = 1 To 7
   fmt = New String("f"c, ctr)
   If fmt.Length = 1 Then fmt = "%" + fmt
   Console.WriteLine("{0,10}: {1:" + fmt + "}", fmt, ts)
Next 
Console.WriteLine()

For ctr = 1 To 7
   fmt = New String("f"c, ctr)
   Console.WriteLine("{0,10}: {1:s\." + fmt + "}", "s\." + fmt, ts)
Next
' The example displays the following output:
'            %f: 8
'            ff: 87
'           fff: 876
'          ffff: 8765
'         fffff: 87654
'        ffffff: 876543
'       fffffff: 8765432
'    
'           s\.f: 29.8
'          s\.ff: 29.87
'         s\.fff: 29.876
'        s\.ffff: 29.8765
'       s\.fffff: 29.87654
'      s\.ffffff: 29.876543
'     s\.fffffff: 29.8765432
```

## <a name="the-fffffff-custom-format-specifier"></a>Настраиваемый описатель формата "fffffff"

Описатель настраиваемого формата "fffffff" (с семью символами "f") выводит десятимиллионные доли секунды (или дробное число тактов) в интервале времени. В операции анализа, которая вызывает метод [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider)) или [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@)), входная строка должна содержать только семь дробных цифр. 

В следующем примере описатель настраиваемого формата "fffffff" используется для отображения дробного числа тактов в значении [TimeSpan](xref:System.TimeSpan). Он используется сначала только как описатель формата, а затем объединяется с описателем "s" в строке настраиваемого формата.

```csharp
TimeSpan ts = new TimeSpan(1003498765432);
string fmt;
Console.WriteLine(ts.ToString("c"));
Console.WriteLine();

for (int ctr = 1; ctr <= 7; ctr++) {
   fmt = new String('f', ctr);
   if (fmt.Length == 1) fmt = "%" + fmt;
   Console.WriteLine("{0,10}: {1:" + fmt + "}", fmt, ts);
} 
Console.WriteLine();

for (int ctr = 1; ctr <= 7; ctr++) {
   fmt = new String('f', ctr);
   Console.WriteLine("{0,10}: {1:s\\." + fmt + "}", "s\\." + fmt, ts);
}
// The example displays the following output:
//               %f: 8
//               ff: 87
//              fff: 876
//             ffff: 8765
//            fffff: 87654
//           ffffff: 876543
//          fffffff: 8765432
//       
//              s\.f: 29.8
//             s\.ff: 29.87
//            s\.fff: 29.876
//           s\.ffff: 29.8765
//          s\.fffff: 29.87654
//         s\.ffffff: 29.876543
//        s\.fffffff: 29.8765432 
```

```vb
Dim ts As New TimeSpan(1003498765432)
Dim fmt As String
Console.WriteLine(ts.ToString("c"))
Console.WriteLine()

For ctr = 1 To 7
   fmt = New String("f"c, ctr)
   If fmt.Length = 1 Then fmt = "%" + fmt
   Console.WriteLine("{0,10}: {1:" + fmt + "}", fmt, ts)
Next 
Console.WriteLine()

For ctr = 1 To 7
   fmt = New String("f"c, ctr)
   Console.WriteLine("{0,10}: {1:s\." + fmt + "}", "s\." + fmt, ts)
Next
' The example displays the following output:
'            %f: 8
'            ff: 87
'           fff: 876
'          ffff: 8765
'         fffff: 87654
'        ffffff: 876543
'       fffffff: 8765432
'    
'           s\.f: 29.8
'          s\.ff: 29.87
'         s\.fff: 29.876
'        s\.ffff: 29.8765
'       s\.fffff: 29.87654
'      s\.ffffff: 29.876543
'     s\.fffffff: 29.8765432
```

## <a name="the-f-custom-format-specifier"></a>Настраиваемый описатель формата "F"

Описатель настраиваемого формата "F" выводит десятые доли секунды в интервале времени. В операции форматирования все оставшиеся цифры дробной части усекаются. Если значение десятых долей секунды временного интервала равно нулю, оно не включается в строку результата. В операции анализа, которая вызывает метод [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider)) или [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@)), наличие десятых долей секунды является необязательным.

Если используется единственный описатель настраиваемого формата "F", необходимо задать "%F" для избежания неверной интерпретации в качестве строки стандартного формата.

В следующем примере описатель настраиваемого формата "F" используется для отображения десятых долей секунды в значении [TimeSpan](xref:System.TimeSpan). Этот описатель настраиваемого формата также используется в операции анализа.

```csharp
Console.WriteLine("Formatting:");
TimeSpan ts1 = TimeSpan.Parse("0:0:3.669");
Console.WriteLine("{0} ('%F') --> {0:%F}", ts1);

TimeSpan ts2 = TimeSpan.Parse("0:0:3.091");
Console.WriteLine("{0} ('ss\\.F') --> {0:ss\\.F}", ts2);
Console.WriteLine();

Console.WriteLine("Parsing:");
string[] inputs = { "0:0:03.", "0:0:03.1", "0:0:03.12" };
string fmt = @"h\:m\:ss\.F";
TimeSpan ts3;

foreach (string input in inputs) {
   if (TimeSpan.TryParseExact(input, fmt, null, out ts3))
      Console.WriteLine("{0} ('{1}') --> {2}", input, fmt, ts3);
   else
      Console.WriteLine("Cannot parse {0} with '{1}'.", 
                        input, fmt);
}                        
// The example displays the following output:
//       Formatting:
//       00:00:03.6690000 ('%F') --> 6
//       00:00:03.0910000 ('ss\.F') --> 03.
//       
//       Parsing:
//       0:0:03. ('h\:m\:ss\.F') --> 00:00:03
//       0:0:03.1 ('h\:m\:ss\.F') --> 00:00:03.1000000
//       Cannot parse 0:0:03.12 with 'h\:m\:ss\.F'.
```

```vb
Console.WriteLine("Formatting:")
Dim ts1 As TimeSpan = TimeSpan.Parse("0:0:3.669")
Console.WriteLine("{0} ('%F') --> {0:%F}", ts1)

Dim ts2 As TimeSpan = TimeSpan.Parse("0:0:3.091")
Console.WriteLine("{0} ('ss\.F') --> {0:ss\.F}", ts2)
Console.WriteLine()

Console.WriteLine("Parsing:")
Dim inputs() As String = { "0:0:03.", "0:0:03.1", "0:0:03.12" }
Dim fmt As String = "h\:m\:ss\.F"
Dim ts3 As TimeSpan

For Each input As String In inputs
   If TimeSpan.TryParseExact(input, fmt, Nothing, ts3)
      Console.WriteLine("{0} ('{1}') --> {2}", input, fmt, ts3)
   Else
      Console.WriteLine("Cannot parse {0} with '{1}'.", 
                        input, fmt)
   End If  
Next
' The example displays the following output:
'       Formatting:
'       00:00:03.6690000 ('%F') --> 6
'       00:00:03.0910000 ('ss\.F') --> 03.
'       
'       Parsing:
'       0:0:03. ('h\:m\:ss\.F') --> 00:00:03
'       0:0:03.1 ('h\:m\:ss\.F') --> 00:00:03.1000000
'       Cannot parse 0:0:03.12 with 'h\:m\:ss\.F'.
```

## <a name="the-ff-custom-format-specifier"></a>Настраиваемый описатель формата "FF"

Описатель настраиваемого формата "FF" выводит сотые доли секунды в интервале времени. В операции форматирования все оставшиеся цифры дробной части усекаются. Результирующая строка не включает нули в конце дробной части. В операции анализа, которая вызывает метод [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider)) или [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@)), наличие десятых и сотых долей секунды является необязательным.

В следующем примере описатель настраиваемого формата "FF" используется для отображения сотых долей секунды в значении [TimeSpan](xref:System.TimeSpan). Этот описатель настраиваемого формата также используется в операции анализа.

```csharp
Console.WriteLine("Formatting:");
TimeSpan ts1 = TimeSpan.Parse("0:0:3.697");
Console.WriteLine("{0} ('FF') --> {0:FF}", ts1);

TimeSpan ts2 = TimeSpan.Parse("0:0:3.809");
Console.WriteLine("{0} ('ss\\.FF') --> {0:ss\\.FF}", ts2);
Console.WriteLine();

Console.WriteLine("Parsing:");
string[] inputs = { "0:0:03.", "0:0:03.1", "0:0:03.127" };
string fmt = @"h\:m\:ss\.FF";
TimeSpan ts3;

foreach (string input in inputs) {
   if (TimeSpan.TryParseExact(input, fmt, null, out ts3))
      Console.WriteLine("{0} ('{1}') --> {2}", input, fmt, ts3);
   else
      Console.WriteLine("Cannot parse {0} with '{1}'.", 
                        input, fmt);
}
// The example displays the following output:
//       Formatting:
//       00:00:03.6970000 ('FF') --> 69
//       00:00:03.8090000 ('ss\.FF') --> 03.8
//       
//       Parsing:
//       0:0:03. ('h\:m\:ss\.FF') --> 00:00:03
//       0:0:03.1 ('h\:m\:ss\.FF') --> 00:00:03.1000000
//       Cannot parse 0:0:03.127 with 'h\:m\:ss\.FF'. 
```

```vb
Console.WriteLine("Formatting:")
Dim ts1 As TimeSpan = TimeSpan.Parse("0:0:3.697")
Console.WriteLine("{0} ('FF') --> {0:FF}", ts1)

Dim ts2 As TimeSpan = TimeSpan.Parse("0:0:3.809")
Console.WriteLine("{0} ('ss\.FF') --> {0:ss\.FF}", ts2)
Console.WriteLine()

Console.WriteLine("Parsing:")
Dim inputs() As String = { "0:0:03.", "0:0:03.1", "0:0:03.127" }
Dim fmt As String = "h\:m\:ss\.FF"
Dim ts3 As TimeSpan

For Each input As String In inputs
   If TimeSpan.TryParseExact(input, fmt, Nothing, ts3)
      Console.WriteLine("{0} ('{1}') --> {2}", input, fmt, ts3)
   Else
      Console.WriteLine("Cannot parse {0} with '{1}'.", 
                        input, fmt)
   End If  
Next
' The example displays the following output:
'       Formatting:
'       00:00:03.6970000 ('FF') --> 69
'       00:00:03.8090000 ('ss\.FF') --> 03.8
'       
'       Parsing:
'       0:0:03. ('h\:m\:ss\.FF') --> 00:00:03
'       0:0:03.1 ('h\:m\:ss\.FF') --> 00:00:03.1000000
'       Cannot parse 0:0:03.127 with 'h\:m\:ss\.FF'.
```

## <a name="the-fff-custom-format-specifier"></a>Настраиваемый описатель формата "FFF"

Описатель настраиваемого формата "FFF" (c тремя символами "F") выводит миллисекунды в интервале времени. В операции форматирования все оставшиеся цифры дробной части усекаются. Результирующая строка не включает нули в конце дробной части. В операции анализа, которая вызывает метод [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider)) или [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@)), наличие десятых, сотых и тысячных долей секунды является необязательным.

В следующем примере описатель настраиваемого формата "FFF" используется для отображения тысячных долей секунды в значении [TimeSpan](xref:System.TimeSpan). Этот описатель настраиваемого формата также используется в операции анализа.

```csharp
Console.WriteLine("Formatting:");
TimeSpan ts1 = TimeSpan.Parse("0:0:3.6974");
Console.WriteLine("{0} ('FFF') --> {0:FFF}", ts1);

TimeSpan ts2 = TimeSpan.Parse("0:0:3.8009");
Console.WriteLine("{0} ('ss\\.FFF') --> {0:ss\\.FFF}", ts2);
Console.WriteLine();

Console.WriteLine("Parsing:");
string[] inputs = { "0:0:03.", "0:0:03.12", "0:0:03.1279" };
string fmt = @"h\:m\:ss\.FFF";
TimeSpan ts3;

foreach (string input in inputs) {
   if (TimeSpan.TryParseExact(input, fmt, null, out ts3))
      Console.WriteLine("{0} ('{1}') --> {2}", input, fmt, ts3);
   else
      Console.WriteLine("Cannot parse {0} with '{1}'.", 
                        input, fmt);
}
// The example displays the following output:
//       Formatting:
//       00:00:03.6974000 ('FFF') --> 697
//       00:00:03.8009000 ('ss\.FFF') --> 03.8
//       
//       Parsing:
//       0:0:03. ('h\:m\:ss\.FFF') --> 00:00:03
//       0:0:03.12 ('h\:m\:ss\.FFF') --> 00:00:03.1200000
//       Cannot parse 0:0:03.1279 with 'h\:m\:ss\.FFF'.  
```

```vb
Console.WriteLine("Formatting:")
Dim ts1 As TimeSpan = TimeSpan.Parse("0:0:3.6974")
Console.WriteLine("{0} ('FFF') --> {0:FFF}", ts1)

Dim ts2 As TimeSpan = TimeSpan.Parse("0:0:3.8009")
Console.WriteLine("{0} ('ss\.FFF') --> {0:ss\.FFF}", ts2)
Console.WriteLine()

Console.WriteLine("Parsing:")
Dim inputs() As String = { "0:0:03.", "0:0:03.12", "0:0:03.1279" }
Dim fmt As String = "h\:m\:ss\.FFF"
Dim ts3 As TimeSpan

For Each input As String In inputs
   If TimeSpan.TryParseExact(input, fmt, Nothing, ts3)
      Console.WriteLine("{0} ('{1}') --> {2}", input, fmt, ts3)
   Else
      Console.WriteLine("Cannot parse {0} with '{1}'.", 
                        input, fmt)
   End If  
Next
' The example displays the following output:
'       Formatting:
'       00:00:03.6974000 ('FFF') --> 697
'       00:00:03.8009000 ('ss\.FFF') --> 03.8
'       
'       Parsing:
'       0:0:03. ('h\:m\:ss\.FFF') --> 00:00:03
'       0:0:03.12 ('h\:m\:ss\.FFF') --> 00:00:03.1200000
'       Cannot parse 0:0:03.1279 with 'h\:m\:ss\.FFF'.
```

## <a name="the-ffff-custom-format-specifier"></a>Настраиваемый описатель формата "FFFF"

Описатель настраиваемого формата "FFFF" (с четырьмя символами "F") выводит десятитысячные доли секунды в интервале времени. В операции форматирования все оставшиеся цифры дробной части усекаются. Результирующая строка не включает нули в конце дробной части. В операции анализа, которая вызывает метод [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider)) или [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@)), наличие десятых, сотых, тысячных и десятитысячных долей секунды является необязательным.

В следующем примере описатель настраиваемого формата "FFFF" используется для отображения десятитысячных долей секунды в значении [TimeSpan](xref:System.TimeSpan). Описатель настраиваемого формата "FFFF" также используется в операции анализа.

```csharp
Console.WriteLine("Formatting:");
TimeSpan ts1 = TimeSpan.Parse("0:0:3.69749");
Console.WriteLine("{0} ('FFFF') --> {0:FFFF}", ts1);

TimeSpan ts2 = TimeSpan.Parse("0:0:3.80009");
Console.WriteLine("{0} ('ss\\.FFFF') --> {0:ss\\.FFFF}", ts2);
Console.WriteLine();

Console.WriteLine("Parsing:");
string[] inputs = { "0:0:03.", "0:0:03.12", "0:0:03.12795" };
string fmt = @"h\:m\:ss\.FFFF";
TimeSpan ts3;

foreach (string input in inputs) {
   if (TimeSpan.TryParseExact(input, fmt, null, out ts3))
      Console.WriteLine("{0} ('{1}') --> {2}", input, fmt, ts3);
   else
      Console.WriteLine("Cannot parse {0} with '{1}'.", 
                        input, fmt);
}
// The example displays the following output:
//       Formatting:
//       00:00:03.6974900 ('FFFF') --> 6974
//       00:00:03.8000900 ('ss\.FFFF') --> 03.8
//       
//       Parsing:
//       0:0:03. ('h\:m\:ss\.FFFF') --> 00:00:03
//       0:0:03.12 ('h\:m\:ss\.FFFF') --> 00:00:03.1200000
//       Cannot parse 0:0:03.12795 with 'h\:m\:ss\.FFFF'.
```

```vb
Console.WriteLine("Formatting:")
Dim ts1 As TimeSpan = TimeSpan.Parse("0:0:3.69749")
Console.WriteLine("{0} ('FFFF') --> {0:FFFF}", ts1)

Dim ts2 As TimeSpan = TimeSpan.Parse("0:0:3.80009")
Console.WriteLine("{0} ('ss\.FFFF') --> {0:ss\.FFFF}", ts2)
Console.WriteLine()

Console.WriteLine("Parsing:")
Dim inputs() As String = { "0:0:03.", "0:0:03.12", "0:0:03.12795" }
Dim fmt As String = "h\:m\:ss\.FFFF"
Dim ts3 As TimeSpan

For Each input As String In inputs
   If TimeSpan.TryParseExact(input, fmt, Nothing, ts3)
      Console.WriteLine("{0} ('{1}') --> {2}", input, fmt, ts3)
   Else
      Console.WriteLine("Cannot parse {0} with '{1}'.", 
                        input, fmt)
   End If  
Next
' The example displays the following output:
'       Formatting:
'       00:00:03.6974900 ('FFFF') --> 6974
'       00:00:03.8000900 ('ss\.FFFF') --> 03.8
'       
'       Parsing:
'       0:0:03. ('h\:m\:ss\.FFFF') --> 00:00:03
'       0:0:03.12 ('h\:m\:ss\.FFFF') --> 00:00:03.1200000
'       Cannot parse 0:0:03.12795 with 'h\:m\:ss\.FFFF'.
```

## <a name="the-fffff-custom-format-specifier"></a>Настраиваемый описатель формата "FFFFF"

Описатель настраиваемого формата "FFFFF" (с пятью символами "F") выводит стотысячные доли секунды в интервале времени. В операции форматирования все оставшиеся цифры дробной части усекаются. Результирующая строка не включает нули в конце дробной части. В операции анализа, которая вызывает метод [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider)) или [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@)), наличие десятых, сотых, тысячных, десяти- и стотысячных долей секунды является необязательным.

В следующем примере описатель настраиваемого формата "FFFFF" используется для отображения стотысячных долей секунды в значении [TimeSpan](xref:System.TimeSpan). Описатель настраиваемого формата "FFFFF" также используется в операции анализа.

```csharp
Console.WriteLine("Formatting:");
TimeSpan ts1 = TimeSpan.Parse("0:0:3.697497");
Console.WriteLine("{0} ('FFFFF') --> {0:FFFFF}", ts1);

TimeSpan ts2 = TimeSpan.Parse("0:0:3.800009");
Console.WriteLine("{0} ('ss\\.FFFFF') --> {0:ss\\.FFFFF}", ts2);
Console.WriteLine();

Console.WriteLine("Parsing:");
string[] inputs = { "0:0:03.", "0:0:03.12", "0:0:03.127956" };
string fmt = @"h\:m\:ss\.FFFFF";
TimeSpan ts3;

foreach (string input in inputs) {
   if (TimeSpan.TryParseExact(input, fmt, null, out ts3))
      Console.WriteLine("{0} ('{1}') --> {2}", input, fmt, ts3);
   else
      Console.WriteLine("Cannot parse {0} with '{1}'.", 
                        input, fmt);
}                       
// The example displays the following output:
//       Formatting:
//       00:00:03.6974970 ('FFFFF') --> 69749
//       00:00:03.8000090 ('ss\.FFFFF') --> 03.8
//       
//       Parsing:
//       0:0:03. ('h\:m\:ss\.FFFF') --> 00:00:03
//       0:0:03.12 ('h\:m\:ss\.FFFF') --> 00:00:03.1200000
//       Cannot parse 0:0:03.127956 with 'h\:m\:ss\.FFFF'. 
```

```vb
Console.WriteLine("Formatting:")
Dim ts1 As TimeSpan = TimeSpan.Parse("0:0:3.697497")
Console.WriteLine("{0} ('FFFFF') --> {0:FFFFF}", ts1)

Dim ts2 As TimeSpan = TimeSpan.Parse("0:0:3.800009")
Console.WriteLine("{0} ('ss\.FFFFF') --> {0:ss\.FFFFF}", ts2)
Console.WriteLine()

Console.WriteLine("Parsing:")
Dim inputs() As String = { "0:0:03.", "0:0:03.12", "0:0:03.127956" }
Dim fmt As String = "h\:m\:ss\.FFFFF"
Dim ts3 As TimeSpan

For Each input As String In inputs
   If TimeSpan.TryParseExact(input, fmt, Nothing, ts3)
      Console.WriteLine("{0} ('{1}') --> {2}", input, fmt, ts3)
   Else
      Console.WriteLine("Cannot parse {0} with '{1}'.", 
                        input, fmt)
   End If  
Next
' The example displays the following output:
'       Formatting:
'       00:00:03.6974970 ('FFFFF') --> 69749
'       00:00:03.8000090 ('ss\.FFFFF') --> 03.8
'       
'       Parsing:
'       0:0:03. ('h\:m\:ss\.FFFF') --> 00:00:03
'       0:0:03.12 ('h\:m\:ss\.FFFF') --> 00:00:03.1200000
'       Cannot parse 0:0:03.127956 with 'h\:m\:ss\.FFFF'.
```

## <a name="the-ffffff-custom-format-specifier"></a>Настраиваемый описатель формата "FFFFFF"

Описатель настраиваемого формата "FFFFFF" (с шестью символами "F") выводит миллионные доли секунды в интервале времени. В операции форматирования все оставшиеся цифры дробной части усекаются. Результирующая строка не включает нули в конце дробной части. В операции анализа, которая вызывает метод [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider)) или [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@)), наличие десятых, сотых, тысячных, десяти-, стотысячных и миллионных долей секунды является необязательным.

В следующем примере описатель настраиваемого формата "FFFFFF" используется для отображения миллионных долей секунды в значении [TimeSpan](xref:System.TimeSpan). Этот описатель настраиваемого формата также используется в операции анализа.

```csharp
Console.WriteLine("Formatting:");
TimeSpan ts1 = TimeSpan.Parse("0:0:3.6974974");
Console.WriteLine("{0} ('FFFFFF') --> {0:FFFFFF}", ts1);

TimeSpan ts2 = TimeSpan.Parse("0:0:3.8000009");
Console.WriteLine("{0} ('ss\\.FFFFFF') --> {0:ss\\.FFFFFF}", ts2);
Console.WriteLine();

Console.WriteLine("Parsing:");
string[] inputs = { "0:0:03.", "0:0:03.12", "0:0:03.1279569" };
string fmt = @"h\:m\:ss\.FFFFFF";
TimeSpan ts3;

foreach (string input in inputs) {
   if (TimeSpan.TryParseExact(input, fmt, null, out ts3))
      Console.WriteLine("{0} ('{1}') --> {2}", input, fmt, ts3);
   else
      Console.WriteLine("Cannot parse {0} with '{1}'.", 
                        input, fmt);
}                       
// The example displays the following output:
//       Formatting:
//       00:00:03.6974974 ('FFFFFF') --> 697497
//       00:00:03.8000009 ('ss\.FFFFFF') --> 03.8
//       
//       Parsing:
//       0:0:03. ('h\:m\:ss\.FFFFFF') --> 00:00:03
//       0:0:03.12 ('h\:m\:ss\.FFFFFF') --> 00:00:03.1200000
//       Cannot parse 0:0:03.1279569 with 'h\:m\:ss\.FFFFFF'.
```

```vb
Console.WriteLine("Formatting:")
Dim ts1 As TimeSpan = TimeSpan.Parse("0:0:3.6974974")
Console.WriteLine("{0} ('FFFFFF') --> {0:FFFFFF}", ts1)

Dim ts2 As TimeSpan = TimeSpan.Parse("0:0:3.8000009")
Console.WriteLine("{0} ('ss\.FFFFFF') --> {0:ss\.FFFFFF}", ts2)
Console.WriteLine()

Console.WriteLine("Parsing:")
Dim inputs() As String = { "0:0:03.", "0:0:03.12", "0:0:03.1279569" }
Dim fmt As String = "h\:m\:ss\.FFFFFF"
Dim ts3 As TimeSpan

For Each input As String In inputs
   If TimeSpan.TryParseExact(input, fmt, Nothing, ts3)
      Console.WriteLine("{0} ('{1}') --> {2}", input, fmt, ts3)
   Else
      Console.WriteLine("Cannot parse {0} with '{1}'.", 
                        input, fmt)
   End If  
Next
' The example displays the following output:
'       Formatting:
'       00:00:03.6974974 ('FFFFFF') --> 697497
'       00:00:03.8000009 ('ss\.FFFFFF') --> 03.8
'       
'       Parsing:
'       0:0:03. ('h\:m\:ss\.FFFFFF') --> 00:00:03
'       0:0:03.12 ('h\:m\:ss\.FFFFFF') --> 00:00:03.1200000
'       Cannot parse 0:0:03.1279569 with 'h\:m\:ss\.FFFFFF'
```

## <a name="the-fffffff-custom-format-specifier"></a>Настраиваемый описатель формата "FFFFFFF"

Описатель настраиваемого формата "FFFFFFF" (с семью символами "F") выводит десятимиллионные доли секунды (или дробное число тактов) в интервале времени. Результирующая строка не включает нули в конце дробной части. В операции анализа, которая вызывает метод [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider)) или [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@)), наличие семиразрядной дробной части во входной строке является необязательным.

В следующем примере описатель настраиваемого формата "FFFFFFF" используется для отображения дробных частей секунды в значении [TimeSpan](xref:System.TimeSpan). Этот описатель настраиваемого формата также используется в операции анализа.

```csharp
Console.WriteLine("Formatting:");
TimeSpan ts1 = TimeSpan.Parse("0:0:3.6974974");
Console.WriteLine("{0} ('FFFFFFF') --> {0:FFFFFFF}", ts1);

TimeSpan ts2 = TimeSpan.Parse("0:0:3.9500000");
Console.WriteLine("{0} ('ss\\.FFFFFFF') --> {0:ss\\.FFFFFFF}", ts2);
Console.WriteLine();

Console.WriteLine("Parsing:");
string[] inputs = { "0:0:03.", "0:0:03.12", "0:0:03.1279569" };
string fmt = @"h\:m\:ss\.FFFFFFF";
TimeSpan ts3;

foreach (string input in inputs) {
   if (TimeSpan.TryParseExact(input, fmt, null, out ts3))
      Console.WriteLine("{0} ('{1}') --> {2}", input, fmt, ts3);
   else
      Console.WriteLine("Cannot parse {0} with '{1}'.", 
                        input, fmt);
}
// The example displays the following output:
//    Formatting:
//    00:00:03.6974974 ('FFFFFFF') --> 6974974
//    00:00:03.9500000 ('ss\.FFFFFFF') --> 03.95
//    
//    Parsing:
//    0:0:03. ('h\:m\:ss\.FFFFFFF') --> 00:00:03
//    0:0:03.12 ('h\:m\:ss\.FFFFFFF') --> 00:00:03.1200000
//    0:0:03.1279569 ('h\:m\:ss\.FFFFFFF') --> 00:00:03.1279569 
```

```vb
Console.WriteLine("Formatting:")
Dim ts1 As TimeSpan = TimeSpan.Parse("0:0:3.6974974")
Console.WriteLine("{0} ('FFFFFFF') --> {0:FFFFFFF}", ts1)

Dim ts2 As TimeSpan = TimeSpan.Parse("0:0:3.9500000")
Console.WriteLine("{0} ('ss\.FFFFFFF') --> {0:ss\.FFFFFFF}", ts2)
Console.WriteLine()

Console.WriteLine("Parsing:")
Dim inputs() As String = { "0:0:03.", "0:0:03.12", "0:0:03.1279569" }
Dim fmt As String = "h\:m\:ss\.FFFFFFF"
Dim ts3 As TimeSpan

For Each input As String In inputs
   If TimeSpan.TryParseExact(input, fmt, Nothing, ts3)
      Console.WriteLine("{0} ('{1}') --> {2}", input, fmt, ts3)
   Else
      Console.WriteLine("Cannot parse {0} with '{1}'.", 
                        input, fmt)
   End If  
Next
' The example displays the following output:
'    Formatting:
'    00:00:03.6974974 ('FFFFFFF') --> 6974974
'    00:00:03.9500000 ('ss\.FFFFFFF') --> 03.95
'    
'    Parsing:
'    0:0:03. ('h\:m\:ss\.FFFFFFF') --> 00:00:03
'    0:0:03.12 ('h\:m\:ss\.FFFFFFF') --> 00:00:03.1200000
'    0:0:03.1279569 ('h\:m\:ss\.FFFFFFF') --> 00:00:03.1279569  
```

## <a name="other-characters"></a>Остальные символы

Любой другой символ в строке формата, не являющийся escape-символом, включая знак пробела, интерпретируется как описатель настраиваемого формата. В большинстве случаев наличие любого другого символа, не являющегося escape-символом, приводит к возникновению исключения [FormatException](xref:System.FormatException). 

Существует два способа включить литеральный символ в строку формата.

* Заключить его в одиночные кавычки (разделитель строк-литералов). 

* Предварить его обратной косой чертой ("\""), которая интерпретируется как escape-символ. Это означает, что в C# строка формата должна представлять собой символ @-quoted, или что литеральный символ должен быть предварен дополнительной обратной косой чертой.

  В некоторых случаях может быть необходимо использовать условную логику, чтобы включить escape-символ в строку формата. В следующем примере условная логика используется для включения символа знака для отрицательных временных интервалов. 
  
  ```csharp
  using System;

  public class Example
  {
     public static void Main()
     {
        TimeSpan result = new DateTime(2010, 01, 01) - DateTime.Now; 
        String fmt = (result < TimeSpan.Zero ?  "\\-" : "") + "dd\\.hh\\:mm";

        Console.WriteLine(result.ToString(fmt));
        Console.WriteLine("Interval: {0:" + fmt + "}", result);
     }
  }
  // The example displays output like the following:
  //       -1291.10:54
  //       Interval: -1291.10:54
  ```

  ```vb
  Module Example
     Public Sub Main()
        Dim result As TimeSpan = New DateTime(2010, 01, 01) - Date.Now 
        Dim fmt As String = If(result < TimeSpan.Zero, "\-", "") + "dd\.hh\:mm"

        Console.WriteLine(result.ToString(fmt))
        Console.WriteLine("Interval: {0:" + fmt + "}", result)
     End Sub
  End Module
  ' The example displays output like the following:
  '       -1291.10:54
  '       Interval: -1291.10:54
  ```
  
.NET не определяет грамматику для разделителей в интервалах времени. Это означает, что разделители между днями и часами, часами и минутами, минутами и секундами, секундами и долями секунд должны быть обработаны как символьные литералы в строке формата.

В следующем примере используются как escape-символ, так и одиночная кавычка для определения строки настраиваемого формата, которая включает слово "minutes" в выходной строке. 

```csharp
TimeSpan interval = new TimeSpan(0, 32, 45);
// Escape literal characters in a format string.
string fmt = @"mm\:ss\ \m\i\n\u\t\e\s";
Console.WriteLine(interval.ToString(fmt));
// Delimit literal characters in a format string with the ' symbol.
fmt = "mm':'ss' minutes'";      
Console.WriteLine(interval.ToString(fmt));
// The example displays the following output: 
//       32:45 minutes      
//       32:45 minutes
```

```vb
Dim interval As New TimeSpan(0, 32, 45)
' Escape literal characters in a format string.
Dim fmt As String = "mm\:ss\ \m\i\n\u\t\e\s"
Console.WriteLine(interval.ToString(fmt))
' Delimit literal characters in a format string with the ' symbol.
fmt = "mm':'ss' minutes'"
Console.WriteLine(interval.ToString(fmt))
' The example displays the following output: 
'       32:45 minutes      
'       32:45 minutes
```

## <a name="see-also"></a>См. также

[Типы форматирования](formatting-types.md)

[Строки стандартного формата TimeSpan](standard-timespan.md)  




<!--HONumber=Nov16_HO1-->


