---
title: "Строки стандартного формата TimeSpan"
description: "Строки стандартного формата TimeSpan"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 4e0f02f1-4abd-47b5-8995-5c3ff45b0ce1
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 4e6b58cd8b29b4a9d46bd43a03c1e8c6c45dfcaa
ms.lasthandoff: 03/02/2017

---

# <a name="standard-timespan-format-strings"></a>Строки стандартного формата TimeSpan

Строка стандартного формата [TimeSpan](xref:System.TimeSpan) использует один описатель формата для определения текстового представления значения [TimeSpan](xref:System.TimeSpan), получаемого после выполнения операции форматирования. Любая строка формата, содержащая более одной буквы, включая пробелы, интерпретируется как строка настраиваемого формата [TimeSpan](xref:System.TimeSpan). Дополнительные сведения см. в разделе [Строки пользовательского формата TimeSpan](custom-timespan.md).

Строковые представления значений [TimeSpan](xref:System.TimeSpan) создаются вызовами перегрузок метода [TimeSpan.ToString](xref:System.TimeSpan.ToString), а также методами, поддерживающими составное форматирование, такими как [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)). Дополнительные сведения см. в разделах [Типы форматирования](formatting-types.md) и [Составное форматирование](composite-format.md). В следующем примере показано использование строк стандартного формата в операциях форматирования.

```csharp
using System;

public class Example
{
   public static void Main()
   {
      TimeSpan duration = new TimeSpan(1, 12, 23, 62);
      string output = "Time of Travel: " + duration.ToString("c");
      Console.WriteLine(output);

      Console.WriteLine("Time of Travel: {0:c}", duration); 
   }
}
// The example displays the following output:
//       Time of Travel: 1.12:24:02
//       Time of Travel: 1.12:24:02
```

```vb
Module Example
   Public Sub Main()
      Dim duration As New TimeSpan(1, 12, 23, 62)
      Dim output As String = "Time of Travel: " + duration.ToString("c")
      Console.WriteLine(output)

      Console.WriteLine("Time of Travel: {0:c}", duration) 
   End Sub
End Module
' The example displays the following output:
'       Time of Travel: 1.12:24:02
'       Time of Travel: 1.12:24:02
```

Строки стандартного формата [TimeSpan](xref:System.TimeSpan) также используется методами [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider)) и [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@)) для определения необходимого формата входных строк для операций анализа. (Анализ преобразует строковое представление значения в это значение). В следующем примере показано использование строк стандартного формата в операциях анализа.

```csharp
using System;

public class Example
{
   public static void Main()
   {
      string value = "1.03:14:56.1667";
      TimeSpan interval;
      try {
         interval = TimeSpan.ParseExact(value, "c", null);
         Console.WriteLine("Converted '{0}' to {1}", value, interval);
      }   
      catch (FormatException) {
         Console.WriteLine("{0}: Bad Format", value);
      }   
      catch (OverflowException) {
         Console.WriteLine("{0}: Out of Range", value);
      }

      if (TimeSpan.TryParseExact(value, "c", null, out interval))
         Console.WriteLine("Converted '{0}' to {1}", value, interval);
      else
         Console.WriteLine("Unable to convert {0} to a time interval.", 
                           value);
   }
}
// The example displays the following output:
//       Converted '1.03:14:56.1667' to 1.03:14:56.1667000
//       Converted '1.03:14:56.1667' to 1.03:14:56.1667000
```

```vb
Module Example
   Public Sub Main()
      Dim value As String = "1.03:14:56.1667"
      Dim interval As TimeSpan
      Try
         interval = TimeSpan.ParseExact(value, "c", Nothing)
         Console.WriteLine("Converted '{0}' to {1}", value, interval)
      Catch e As FormatException
         Console.WriteLine("{0}: Bad Format", value)
      Catch e As OverflowException
         Console.WriteLine("{0}: Out of Range", value)
      End Try

      If TimeSpan.TryParseExact(value, "c", Nothing, interval) Then
         Console.WriteLine("Converted '{0}' to {1}", value, interval)
      Else
         Console.WriteLine("Unable to convert {0} to a time interval.", 
                           value)
      End If                
   End Sub
End Module
' The example displays the following output:
'       Converted '1.03:14:56.1667' to 1.03:14:56.1667000
'       Converted '1.03:14:56.1667' to 1.03:14:56.1667000
```

В следующей таблице перечислены описатели стандартного формата временных интервалов.

Описатель формата | Имя | Описание | Примеры
---------------- | ---- | ----------- | --------
"c" | Постоянный (инвариантный) формат | Этот описатель не учитывает язык и региональные параметры. Он принимает форму [-][d’.’]hh’:’mm’:’ss[‘.’fffffff]. (Строки формата "t" и "T" дают одинаковые результаты). | `TimeSpan.Zero -> 00:00:00`; `New TimeSpan(0, 0, 30, 0) -> 00:30:00`; `New TimeSpan(3, 17, 25, 30, 500) -> 3.17:25:30.5000000`
"g" | Общий короткий формат | Этот описатель выводит только необходимые данные. Он зависит от языка и региональных параметров и принимает форму [-][d’:’]h’:’mm’:’ss[.FFFFFFF]. | `New TimeSpan(1, 3, 16, 50, 500) -> 1:3:16:50.5 (en-US)`; `New TimeSpan(1, 3, 16, 50, 500) -> 1:3:16:50,5 (fr-FR)`; `New TimeSpan(1, 3, 16, 50, 599) -> 1:3:16:50.599 (en-US)`; `New TimeSpan(1, 3, 16, 50, 599) -> 1:3:16:50,599 (fr-FR)`
"G" | Общий длинный формат | Этот описатель всегда отображает дни и семь цифр после запятой. Он зависит от языка и региональных параметров и принимает форму [-]d’:’hh’:’mm’:’ss.fffffff. | `New TimeSpan(18, 30, 0) -> 0:18:30:00.0000000 (en-US)`; `New TimeSpan(18, 30, 0) -> 0:18:30:00,0000000 (fr-FR)` 

## <a name="the-constant-c-format-specifier"></a>Описатель постоянного ("c") формата.

Описатель формата "c" возвращает строковое представление значения [TimeSpan](xref:System.TimeSpan) в следующем виде:

[-][_d_.]_hh_:_mm_:_ss_[._fffffff_]

Элементы в квадратных скобках ([и]) являются необязательными. Точка (.) и двоеточие (:) являются литеральными символами. В следующей таблице описываются остальные элементы. 

Элемент | Описание
------- | -----------
- | Необязательный знак минуса, который означает отрицательный интервал времени.
*d* | Необязательное число дней без предшествующих нулей.
*hh* | Количество часов в диапазоне от "00" до "23".
*mm* | Количество минут в диапазоне от "00" до "59".
*ss* | Количество секунд в диапазоне от "0" до "59".
*fffffff* | Необязательная доля секунды. Это значение может входит в диапазон от "0000001" (одной десятимиллионной секунды) до "9999999" (9 999 999 десятимиллионных секунды). 

В отличие от описателей формата "g" и "G" описатель формата "c" не учитывает язык и региональные параметры. Он создает строковое представление значения [TimeSpan](xref:System.TimeSpan), которое является инвариантным и общим для всех предыдущих версий платформы .NET Framework до выхода .NET Framework 4. "c" является строкой формата [TimeSpan](xref:System.TimeSpan) по умолчанию. Метод [TimeSpan.ToString](xref:System.TimeSpan.ToString) форматирует значение временного интервала с помощью строки формата "c".

> [!NOTE]
> [TimeSpan](xref:System.TimeSpan) также поддерживает строки стандартного формата "t" и "T", поведение которых идентично поведению строки стандартного формата "c".

В следующем примере создаются два объекта [TimeSpan](xref:System.TimeSpan), которые используются для выполнения арифметических операций, после чего выводится результат. В каждом случае используется составное форматирование для отображения значения [TimeSpan](xref:System.TimeSpan) с помощью описателя формата "c".

```csharp
using System;

public class Example
{
   public static void Main()
   {
      TimeSpan interval1, interval2;
      interval1 = new TimeSpan(7, 45, 16);
      interval2 = new TimeSpan(18, 12, 38);

      Console.WriteLine("{0:c} - {1:c} = {2:c}", interval1, 
                        interval2, interval1 - interval2);
      Console.WriteLine("{0:c} + {1:c} = {2:c}", interval1, 
                        interval2, interval1 + interval2);

      interval1 = new TimeSpan(0, 0, 1, 14, 365);
      interval2 = TimeSpan.FromTicks(2143756);  
      Console.WriteLine("{0:c} + {1:c} = {2:c}", interval1, 
                        interval2, interval1 + interval2);
   }
}
// The example displays the following output:
//       07:45:16 - 18:12:38 = -10:27:22
//       07:45:16 + 18:12:38 = 1.01:57:54
//       00:01:14.3650000 + 00:00:00.2143756 = 00:01:14.5793756
```

```vb
Module Example
   Public Sub Main()
      Dim interval1, interval2 As TimeSpan
      interval1 = New TimeSpan(7, 45, 16)
      interval2 = New TimeSpan(18, 12, 38)

      Console.WriteLine("{0:c} - {1:c} = {2:c}", interval1, 
                        interval2, interval1 - interval2)
      Console.WriteLine("{0:c} + {1:c} = {2:c}", interval1, 
                        interval2, interval1 + interval2)

      interval1 = New TimeSpan(0, 0, 1, 14, 365)
      interval2 = TimeSpan.FromTicks(2143756)      
      Console.WriteLine("{0:c} + {1:c} = {2:c}", interval1, 
                        interval2, interval1 + interval2)
   End Sub
End Module
' The example displays the following output:
'       07:45:16 - 18:12:38 = -10:27:22
'       07:45:16 + 18:12:38 = 1.01:57:54
'       00:01:14.3650000 + 00:00:00.2143756 = 00:01:14.5793756
```

## <a name="the-general-short-g-format-specifier"></a>Описатель общего короткого ("g") формата

Описатель формата "g" [TimeSpan](xref:System.TimeSpan) возвращает строковое представление значения [TimeSpan](xref:System.TimeSpan) в компактной форме, включая только необходимые элементы. Представление имеет следующую форму:

[-][_d_:]_h_:_mm_:_ss_[._FFFFFFF_]

Элементы в квадратных скобках ([и]) являются необязательными. Двоеточие (:) является литеральным символом. В следующей таблице описываются остальные элементы.

Элемент | Описание
------- | -----------
- | Необязательный знак минуса, который означает отрицательный интервал времени.
*d* | Необязательное число дней без предшествующих нулей.
*hh* | Количество часов в диапазоне от "0" до "23" без предшествующих нулей. 
*mm* | Количество минут в диапазоне от "00" до "59".
*ss* | Количество секунд в диапазоне от "0" до "59".
. | Разделитель долей секунд.
*FFFFFFF* | Доли секунд. Отображается как можно меньше цифр.

Как и описатель формата "G", описатель формата "g" является локализуемым. Его разделитель долей секунд зависит от текущего языка и региональных параметров.

В следующем примере создаются два объекта [TimeSpan](xref:System.TimeSpan), которые используются для выполнения арифметических операций, после чего выводится результат. В каждом случае используется составное форматирование для отображения значения [TimeSpan](xref:System.TimeSpan) с помощью описателя формата "g". Кроме того, он форматирует значение [TimeSpan](xref:System.TimeSpan) с использованием соглашений о форматировании текущего системного языка и региональных параметров (в данном случае это английский язык, США или en-US) и французского языка, Франция (fr-FR).

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      TimeSpan interval1, interval2;
      interval1 = new TimeSpan(7, 45, 16);
      interval2 = new TimeSpan(18, 12, 38);

      Console.WriteLine("{0:g} - {1:g} = {2:g}", interval1, 
                        interval2, interval1 - interval2);
      Console.WriteLine(String.Format(new CultureInfo("fr-FR"), 
                        "{0:g} + {1:g} = {2:g}", interval1, 
                        interval2, interval1 + interval2));

      interval1 = new TimeSpan(0, 0, 1, 14, 36);
      interval2 = TimeSpan.FromTicks(2143756);      
      Console.WriteLine("{0:g} + {1:g} = {2:g}", interval1, 
                        interval2, interval1 + interval2);
   }
}
// The example displays the following output:
//       7:45:16 - 18:12:38 = -10:27:22
//       7:45:16 + 18:12:38 = 1:1:57:54
//       0:01:14.036 + 0:00:00.2143756 = 0:01:14.2503756
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim interval1, interval2 As TimeSpan
      interval1 = New TimeSpan(7, 45, 16)
      interval2 = New TimeSpan(18, 12, 38)

      Console.WriteLine("{0:g} - {1:g} = {2:g}", interval1, 
                        interval2, interval1 - interval2)
      Console.WriteLine(String.Format(New CultureInfo("fr-FR"), 
                        "{0:g} + {1:g} = {2:g}", interval1, 
                        interval2, interval1 + interval2))

      interval1 = New TimeSpan(0, 0, 1, 14, 36)
      interval2 = TimeSpan.FromTicks(2143756)      
      Console.WriteLine("{0:g} + {1:g} = {2:g}", interval1, 
                        interval2, interval1 + interval2)
   End Sub
End Module
' The example displays the following output:
'       7:45:16 - 18:12:38 = -10:27:22
'       7:45:16 + 18:12:38 = 1:1:57:54
'       0:01:14.036 + 0:00:00.2143756 = 0:01:14.2503756
```

## <a name="the-general-long-g-format-specifier"></a>Описатель общего длинного ("G") формата

Описатель формата "G" [TimeSpan](xref:System.TimeSpan) возвращает строковое представление значения [TimeSpan](xref:System.TimeSpan) в длинной форме, которая всегда включает и дни, и доли секунд. Строка, которая является результатом описателя стандартного формата "G" имеет следующий вид:

[-]*d*:*hh*:*mm*:*ss*.*fffffff*

Элементы в квадратных скобках ([и]) являются необязательными. Двоеточие (:) является литеральным символом. В следующей таблице описываются остальные элементы.

Элемент | Описание
------- | -----------
- | Необязательный знак минуса, который означает отрицательный интервал времени.
*d* | Необязательное число дней без предшествующих нулей.
*hh* | Количество часов в диапазоне от "0" до "23". 
*mm* | Количество минут в диапазоне от "00" до "59".
*ss* | Количество секунд в диапазоне от "0" до "59".
. | Разделитель долей секунд.
*fffffff* | Доли секунд.

Как и описатель формата "G", описатель формата "g" является локализуемым. Его разделитель долей секунд зависит от текущего языка и региональных параметров.

В следующем примере создаются два объекта [TimeSpan](xref:System.TimeSpan), которые используются для выполнения арифметических операций, после чего выводится результат. В каждом случае используется составное форматирование для отображения значения [TimeSpan](xref:System.TimeSpan) с помощью описателя формата "G". Кроме того, он форматирует значение [TimeSpan](xref:System.TimeSpan) с использованием соглашений о форматировании текущего системного языка и региональных параметров (в данном случае это английский язык, США или en-US) и французского языка, Франция (fr-FR). 

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      TimeSpan interval1, interval2;
      interval1 = new TimeSpan(7, 45, 16);
      interval2 = new TimeSpan(18, 12, 38);

      Console.WriteLine("{0:G} - {1:G} = {2:G}", interval1, 
                        interval2, interval1 - interval2);
      Console.WriteLine(String.Format(new CultureInfo("fr-FR"), 
                        "{0:G} + {1:G} = {2:G}", interval1, 
                        interval2, interval1 + interval2));

      interval1 = new TimeSpan(0, 0, 1, 14, 36);
      interval2 = TimeSpan.FromTicks(2143756);      
      Console.WriteLine("{0:G} + {1:G} = {2:G}", interval1, 
                        interval2, interval1 + interval2);
   }
}
// The example displays the following output:
//       0:07:45:16.0000000 - 0:18:12:38.0000000 = -0:10:27:22.0000000
//       0:07:45:16,0000000 + 0:18:12:38,0000000 = 1:01:57:54,0000000
//       0:00:01:14.0360000 + 0:00:00:00.2143756 = 0:00:01:14.2503756
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim interval1, interval2 As TimeSpan
      interval1 = New TimeSpan(7, 45, 16)
      interval2 = New TimeSpan(18, 12, 38)

      Console.WriteLine("{0:G} - {1:G} = {2:G}", interval1, 
                        interval2, interval1 - interval2)
      Console.WriteLine(String.Format(New CultureInfo("fr-FR"), 
                        "{0:G} + {1:G} = {2:G}", interval1, 
                        interval2, interval1 + interval2))

      interval1 = New TimeSpan(0, 0, 1, 14, 36)
      interval2 = TimeSpan.FromTicks(2143756)      
      Console.WriteLine("{0:G} + {1:G} = {2:G}", interval1, 
                        interval2, interval1 + interval2)
   End Sub
End Module
' The example displays the following output:
'       0:07:45:16.0000000 - 0:18:12:38.0000000 = -0:10:27:22.0000000
'       0:07:45:16,0000000 + 0:18:12:38,0000000 = 1:01:57:54,0000000
'       0:00:01:14.0360000 + 0:00:00:00.2143756 = 0:00:01:14.2503756
```

## <a name="see-also"></a>См. также

[Типы форматирования](formatting-types.md)

[Составное форматирование](composite-format.md)

[Анализ строк](parsing-strings.md)


