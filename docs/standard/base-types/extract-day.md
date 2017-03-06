---
title: "Практическое руководство. Извлечение дня недели из конкретной даты"
description: "Практическое руководство. Извлечение дня недели из конкретной даты"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 88a8f8b9-f5c9-4503-b968-84468b52bb8e
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 1b9d1d497524e62e5758c9be7be7b586a421a258
ms.lasthandoff: 03/03/2017

---

# <a name="how-to-extract-the-day-of-the-week-from-a-specific-date"></a>Практическое руководство. Извлечение дня недели из конкретной даты

Платформа .NET упрощает определение дня недели и отображение локализованного дня для определенной даты. Значение перечисления, которое указывает день недели, соответствующий определенной дате, можно получить из свойства [Datetime.DayOfWeek](xref:System.DateTime.DayOfWeek) или [DateTimeOffset.DayOfWeek](xref:System.DateTimeOffset.DayOfWeek). Напротив, получение названия дня недели — это операция форматирования, которую можно выполнить с помощью метода форматирования, например метода `ToString` значения даты и времени или метода [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)). В этом разделе показано, как выполнить эти операции форматирования.

## <a name="to-extract-a-number-indicating-the-day-of-the-week-from-a-specific-date"></a>Извлечение числа, обозначающего день недели, из определенной даты

1. Если вы работаете со строковым представлением даты, преобразуйте ее в значение типа [DateTime](xref:System.DateTime) или [DateTimeOffset](xref:System.DateTimeOffset), используя статичный метод [DateTime.Parse](xref:System.DateTime.Parse(System.String)) или [DateTimeOffset.Parse](xref:System.DateTimeOffset.Parse(System.String)).

2. Используйте свойство [Datetime.DayOfWeek](xref:System.DateTime.DayOfWeek) или [DateTimeOffset.DayOfWeek](xref:System.DateTimeOffset.DayOfWeek) для получения значения [DayOfWeek](xref:System.DayOfWeek), указывающего день недели.

3. При необходимости приведите значение [DayOfWeek](xref:System.DayOfWeek) в целочисленный тип. 

Следующий пример отображает целое число, представляющее день недели для определенной даты. 

```csharp
using System;

public class Example
{
   public static void Main()
   {
      DateTime dateValue = new DateTime(2008, 6, 11);
      Console.WriteLine((int) dateValue.DayOfWeek);      
   }
}
// The example displays the following output:
//       3
```

```vb
Module Example
   Public Sub Main()
      Dim dateValue As Date = #6/11/2008#
      Console.WriteLine(dateValue.DayOfWeek)           
   End Sub
End Module
' The example displays the following output:
'    3
```

## <a name="to-extract-the-abbreviated-weekday-name-from-a-specific-date"></a>Извлечение сокращенного названия дня недели из определенной даты

1. Если вы работаете со строковым представлением даты, преобразуйте ее в значение типа [DateTime](xref:System.DateTime) или [DateTimeOffset](xref:System.DateTimeOffset), используя статичный метод [DateTime.Parse](xref:System.DateTime.Parse(System.String)) или [DateTimeOffset.Parse](xref:System.DateTimeOffset.Parse(System.String)).

2. Вы можете извлечь сокращенное название дня недели для текущих или заданных региональных параметров:

    1. Чтобы извлечь сокращенное название дня недели для текущих языка и региональных параметров, вызовите метод [DateTime.ToString(String)](xref:System.DateTimeSystem.DateTime.ToString(System.String) значения даты и времени или метод экземпляра [DateTimeOffset.ToString(String)](xref:System.DateTimeOffset.ToString(System.String)) и передайте строку "ddd" в параметре *format*. В следующем примере показано использование метода `ToString(String)`.
    
```csharp
using System;

public class Example
{
   public static void Main()
   {
  DateTime dateValue = new DateTime(2008, 6, 11);
  Console.WriteLine(dateValue.ToString("ddd"));   
   }
}
// The example displays the following output:
//       Wed
```

```vb
Module Example
   Public Sub Main()
  Dim dateValue As Date = #6/11/2008#
      Console.WriteLine(dateValue.ToString("ddd"))    
   End Sub
End Module
' The example displays the following output:
'       Wed
```

    b. To extract the abbreviated weekday name for a specific culture, call the date and time value’s [DateTime.ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) or [DateTimeOffset.ToString(String, IFormatProvider)](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)) instance method. Pass the string "ddd" as the *format* parameter. Pass either a [CultureInfo](xref:System.Globalization.CultureInfo) or a [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object that represents the culture whose weekday name you want to retrieve as the *provider* parameter. The following code illustrates a call to the [ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) method using a [CultureInfo](xref:System.Globalization.CultureInfo) object that represents the fr-FR culture.
    
```csharp
using System;
using System.Globalization;

public class Example
{
    public static void Main()
    {
        DateTime dateValue = new DateTime(2008, 6, 11);
        Console.WriteLine(dateValue.ToString("ddd", 
                            new CultureInfo("fr-FR")));    
    }
}
// The example displays the following output:
//       mer. 
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim dateValue As Date = #6/11/2008#
      Console.WriteLine(dateValue.ToString("ddd", 
                        New CultureInfo("fr-FR")))
   End Sub
End Module
' The example displays the following output:
'       mer.
```

## <a name="to-extract-the-full-weekday-name-from-a-specific-date"></a>Извлечение полного названия дня недели из определенной даты

1. Если вы работаете со строковым представлением даты, преобразуйте ее в значение типа [DateTime](xref:System.DateTime) или [DateTimeOffset](xref:System.DateTimeOffset), используя статичный метод [DateTime.Parse](xref:System.DateTime.Parse(System.String)) или [DateTimeOffset.Parse](xref:System.DateTimeOffset.Parse(System.String)).

2. Вы можете извлечь сокращенное название дня недели для текущих или заданных региональных параметров:

    1. Чтобы извлечь сокращенное название дня недели для текущего языка и региональных параметров, вызовите метод [DateTime.ToString(String)](xref:System.DateTimeSystem.DateTime.ToString(System.String) значения даты и времени или метод экземпляра [DateTimeOffset.ToString(String)](xref:System.DateTimeOffset.ToString(System.String)) и передайте строку "dddd" в параметре *format*. В следующем примере показано использование метода `ToString(String)`.

```csharp
using System;

public class Example
{
    public static void Main()
    {
        DateTime dateValue = new DateTime(2008, 6, 11);
        Console.WriteLine(dateValue.ToString("dddd"));    
    }
}
// The example displays the following output:
//       Wednesday
```

```vb
Module Example
   Public Sub Main()
      Dim dateValue As Date = #6/11/2008#
      Console.WriteLine(dateValue.ToString("dddd"))
   End Sub
End Module
' The example displays the following output:
'       Wednesday
```

    b. To extract the weekday name for a specific culture, call the date and time value’s [DateTime.ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) or [DateTimeOffset.ToString(String, IFormatProvider)](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)) instance method. Pass the string "dddd" as the *format* parameter. Pass either a [CultureInfo](xref:System.Globalization.CultureInfo) or a [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object that represents the culture whose weekday name you want to retrieve as the *provider* parameter. The following code illustrates a call to the [ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) method using a [CultureInfo](xref:System.Globalization.CultureInfo) object that represents the es-ES  culture.

```csharp
using System;
using System.Globalization;

public class Example
{
    public static void Main()
    {
        DateTime dateValue = new DateTime(2008, 6, 11);
        Console.WriteLine(dateValue.ToString("dddd", 
                            new CultureInfo("es-ES")));    
    }
}
// The example displays the following output:
//       miércoles.
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim dateValue As Date = #6/11/2008#
      Console.WriteLine(dateValue.ToString("dddd", _
                        New CultureInfo("es-ES"))) 
   End Sub
End Module
' The example displays the following output:
'       miércoles.
```

## <a name="example"></a>Пример

В этом примере показаны вызовы свойств [Datetime.DayOfWeek](xref:System.DateTime.DayOfWeek) и [DateTimeOffset.DayOfWeek](xref:System.DateTimeOffset.DayOfWeek), а также методов [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String) и [DateTimeOffset.ToString(String)](xref:System.DateTimeOffset.ToString(System.String)) для получения числа, представляющего день недели, сокращенное и полное название дня недели для определенной даты. 

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      string dateString = "6/11/2007";
      DateTime dateValue;
      DateTimeOffset dateOffsetValue;

      try
      {
         DateTimeFormatInfo dateTimeFormats;
         // Convert date representation to a date value
         dateValue = DateTime.Parse(dateString, CultureInfo.InvariantCulture);
         dateOffsetValue = new DateTimeOffset(dateValue, 
                                      TimeZoneInfo.Local.GetUtcOffset(dateValue));         

         // Convert date representation to a number indicating the day of week
         Console.WriteLine((int) dateValue.DayOfWeek);
         Console.WriteLine((int) dateOffsetValue.DayOfWeek);

         // Display abbreviated weekday name using current culture
         Console.WriteLine(dateValue.ToString("ddd"));
         Console.WriteLine(dateOffsetValue.ToString("ddd"));

         // Display full weekday name using current culture
         Console.WriteLine(dateValue.ToString("dddd"));
         Console.WriteLine(dateOffsetValue.ToString("dddd"));

         // Display abbreviated weekday name for de-DE culture
         Console.WriteLine(dateValue.ToString("ddd", new CultureInfo("de-DE")));
         Console.WriteLine(dateOffsetValue.ToString("ddd", 
                                                     new CultureInfo("de-DE")));

         // Display abbreviated weekday name with de-DE DateTimeFormatInfo object
         dateTimeFormats = new CultureInfo("de-DE").DateTimeFormat;
         Console.WriteLine(dateValue.ToString("ddd", dateTimeFormats));
         Console.WriteLine(dateOffsetValue.ToString("ddd", dateTimeFormats));

         // Display full weekday name for fr-FR culture
         Console.WriteLine(dateValue.ToString("ddd", new CultureInfo("fr-FR")));
         Console.WriteLine(dateOffsetValue.ToString("ddd", 
                                                    new CultureInfo("fr-FR")));

         // Display abbreviated weekday name with fr-FR DateTimeFormatInfo object
         dateTimeFormats = new CultureInfo("fr-FR").DateTimeFormat;
         Console.WriteLine(dateValue.ToString("dddd", dateTimeFormats));
         Console.WriteLine(dateOffsetValue.ToString("dddd", dateTimeFormats));
      }
      catch (FormatException)
      {
         Console.WriteLine("Unable to convert {0} to a date.", dateString);
      }
   }
}
// The example displays the following output:
//       1
//       1
//       Mon
//       Mon
//       Monday
//       Monday
//       Mo
//       Mo
//       Mo
//       Mo
//       lun.
//       lun.
//       lundi
//       lundi
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim dateString As String = "6/11/2007"
      Dim dateValue As Date
      Dim dateOffsetValue As DateTimeOffset

      Try
         Dim dateTimeFormats As DateTimeFormatInfo
         ' Convert date representation to a date value
         dateValue = Date.Parse(dateString, CultureInfo.InvariantCulture)
         dateOffsetValue = New DateTimeOffset(dateValue, _
                                     TimeZoneInfo.Local.GetUtcOffset(dateValue))            
         ' Convert date representation to a number indicating the day of week
         Console.WriteLine(dateValue.DayOfWeek)
         Console.WriteLine(dateOffsetValue.DayOfWeek)

         ' Display abbreviated weekday name using current culture
         Console.WriteLine(dateValue.ToString("ddd"))
         Console.WriteLine(dateOffsetValue.ToString("ddd"))

         ' Display full weekday name using current culture
         Console.WriteLine(dateValue.ToString("dddd"))
         Console.WriteLine(dateOffsetValue.ToString("dddd"))

         ' Display abbreviated weekday name for de-DE culture
         Console.WriteLine(dateValue.ToString("ddd", New CultureInfo("de-DE")))
         Console.WriteLine(dateOffsetValue.ToString("ddd", _
                                                    New CultureInfo("de-DE")))

         ' Display abbreviated weekday name with de-DE DateTimeFormatInfo object
         dateTimeFormats = New CultureInfo("de-DE").DateTimeFormat
         Console.WriteLine(dateValue.ToString("ddd", dateTimeFormats))
         Console.WriteLine(dateOffsetValue.ToString("ddd", dateTimeFormats))

         ' Display full weekday name for fr-FR culture
         Console.WriteLine(dateValue.ToString("ddd", New CultureInfo("fr-FR")))
         Console.WriteLine(dateOffsetValue.ToString("ddd", _
                                                    New CultureInfo("fr-FR")))

         ' Display abbreviated weekday name with fr-FR DateTimeFormatInfo object
         dateTimeFormats = New CultureInfo("fr-FR").DateTimeFormat
         Console.WriteLine(dateValue.ToString("dddd", dateTimeFormats))
         Console.WriteLine(dateOffsetValue.ToString("dddd", dateTimeFormats))
      Catch e As FormatException
         Console.WriteLine("Unable to convert {0} to a date.", dateString)
      End Try
   End Sub
End Module
' The example displays the following output to the console:
'       1
'       1
'       Mon
'       Mon
'       Monday
'       Monday
'       Mo
'       Mo
'       Mo
'       Mo
'       lun.
'       lun.
'       lundi
'       lundi
```

Отдельные языки могут предоставлять возможности, дублирующие или дополняющие функции .NET. Например, Visual Basic предоставляет две такие функции:

* `Weekday`, которая возвращает число, обозначающее день недели для определенной даты. Функция считает порядковое значение первого дня недели равным&1;, а свойство [Datetime.DayOfWeek](xref:System.DateTime.DayOfWeek) — равным&0;.

* `WeekdayName`, которая возвращает название дня недели для текущих региональных параметров, которое соответствует определенному номеру дня недели.

В следующем примере показано использование функций `Weekday` и `WeekdayName` Visual Basic.

```vb
Imports System.Globalization
Imports System.Threading

Module Example
   Public Sub Main()
      Dim dateValue As Date = #6/11/2008#

      ' Get weekday number using Visual Basic Weekday function
      Console.WriteLine(Weekday(dateValue))                 ' Displays 4
      ' Compare with .NET DateTime.DayOfWeek property
      Console.WriteLine(dateValue.DayOfWeek)                ' Displays 3

      ' Get weekday name using Weekday and WeekdayName functions
      Console.WriteLine(WeekdayName(Weekday(dateValue)))    ' Displays Wednesday

      ' Change culture to de-DE
      Dim originalCulture As CultureInfo = Thread.CurrentThread.CurrentCulture
      Thread.CurrentThread.CurrentCulture = New CultureInfo("de-DE")
      ' Get weekday name using Weekday and WeekdayName functions
      Console.WriteLine(WeekdayName(Weekday(dateValue)))   ' Displays Donnerstag

      ' Restore original culture
      Thread.CurrentThread.CurrentCulture = originalCulture   
   End Sub
End Module
``` 

Вы также можете использовать значение, возвращенное свойством [Datetime.DayOfWeek](xref:System.DateTime.DayOfWeek), для получения названия дня недели для определенной даты. Для этого требуется просто вызвать метод [Enum.ToString](xref:System.Enum.ToString(System.String)) для значения [DayOfWeek](xref:System.DayOfWeek), возвращенного свойством. Однако этот способ не позволяет получить локализованное название дня недели для текущих региональных параметров, как показано в следующем примере. 

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      // Change current culture to fr-FR
      CultureInfo originalCulture = Thread.CurrentThread.CurrentCulture;
      Thread.CurrentThread.CurrentCulture = new CultureInfo("fr-FR");

      DateTime dateValue = new DateTime(2008, 6, 11);
      // Display the DayOfWeek string representation
      Console.WriteLine(dateValue.DayOfWeek.ToString());   
      // Restore original current culture
      Thread.CurrentThread.CurrentCulture = originalCulture;
   }
}
// The example displays the following output:
//       Wednesday
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim dateString As String = "6/11/2007"
      Dim dateValue As Date
      Dim dateOffsetValue As DateTimeOffset

      Try
         Dim dateTimeFormats As DateTimeFormatInfo
         ' Convert date representation to a date value
         dateValue = Date.Parse(dateString, CultureInfo.InvariantCulture)
         dateOffsetValue = New DateTimeOffset(dateValue, _
                                     TimeZoneInfo.Local.GetUtcOffset(dateValue))            
         ' Convert date representation to a number indicating the day of week
         Console.WriteLine(dateValue.DayOfWeek)
         Console.WriteLine(dateOffsetValue.DayOfWeek)

         ' Display abbreviated weekday name using current culture
         Console.WriteLine(dateValue.ToString("ddd"))
         Console.WriteLine(dateOffsetValue.ToString("ddd"))

         ' Display full weekday name using current culture
         Console.WriteLine(dateValue.ToString("dddd"))
         Console.WriteLine(dateOffsetValue.ToString("dddd"))

         ' Display abbreviated weekday name for de-DE culture
         Console.WriteLine(dateValue.ToString("ddd", New CultureInfo("de-DE")))
         Console.WriteLine(dateOffsetValue.ToString("ddd", _
                                                    New CultureInfo("de-DE")))

         ' Display abbreviated weekday name with de-DE DateTimeFormatInfo object
         dateTimeFormats = New CultureInfo("de-DE").DateTimeFormat
         Console.WriteLine(dateValue.ToString("ddd", dateTimeFormats))
         Console.WriteLine(dateOffsetValue.ToString("ddd", dateTimeFormats))

         ' Display full weekday name for fr-FR culture
         Console.WriteLine(dateValue.ToString("ddd", New CultureInfo("fr-FR")))
         Console.WriteLine(dateOffsetValue.ToString("ddd", _
                                                    New CultureInfo("fr-FR")))

         ' Display abbreviated weekday name with fr-FR DateTimeFormatInfo object
         dateTimeFormats = New CultureInfo("fr-FR").DateTimeFormat
         Console.WriteLine(dateValue.ToString("dddd", dateTimeFormats))
         Console.WriteLine(dateOffsetValue.ToString("dddd", dateTimeFormats))
      Catch e As FormatException
         Console.WriteLine("Unable to convert {0} to a date.", dateString)
      End Try
   End Sub
End Module
' The example displays the following output to the console:
'       1
'       1
'       Mon
'       Mon
'       Monday
'       Monday
'       Mo
'       Mo
'       Mo
'       Mo
'       lun.
'       lun.
'       lundi
'       lundi
```

## <a name="see-also"></a>См. также

[Выполнение операций форматирования](performing-formatting-operations.md)

[Строки стандартных форматов даты и времени](standard-datetime.md)

[Строки настраиваемых форматов даты и времени](custom-datetime.md)
    

