---
title: "Практическое руководство. Отображение миллисекунд в значениях даты и времени"
description: "Практическое руководство. Отображение миллисекунд в значениях даты и времени"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 78599e33-1c3f-4335-b320-751e35906338
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 7a110cf28ac8de558cd1460c61a650fc8a80e51a
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-display-milliseconds-in-date-and-time-values"></a>Практическое руководство. Отображение миллисекунд в значениях даты и времени

Методы форматирования даты и времени по умолчанию, такие как [DateTime.ToString()](xref:System.DateTime.ToString), включают в себя часы, минуты и секунды значения времени, но не содержат миллисекунды. В этом разделе показано, как включить компонент миллисекунд даты и времени в форматированные строки даты и времени.

## <a name="to-display-the-millisecond-component-of-a-datetime-value"></a>Отображение компонента миллисекунд для значения DateTime

1. Если вы работаете со строковым представлением даты, преобразуйте его в значение типа [DateTime](xref:System.DateTime) или [DateTimeOffset](xref:System.DateTimeOffset), используя статичный метод [DateTime.Parse(String)](xref:System.DateTime.Parse(System.String)) или [DateTimeOffset.Parse(String)](xref:System.DateTimeOffset.Parse(System.String)).

2. Чтобы извлечь строковое представление компонента миллисекунд, вызовите метод [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String)) или [DateTimeOffset.ToString](xref:System.DateTimeOffset.ToString(System.String)) значения даты и времени и передайте шаблон пользовательского формата `fff` или `FFF` отдельно или с другим описателем пользовательского формата в качестве параметра.

## <a name="example"></a>Пример

В этом примере на консоль по отдельности выводятся компонент миллисекунд [DateTime](xref:System.DateTime) и значение [DateTimeOffset](xref:System.DateTimeOffset), содержащиеся в более длинной строке даты и времени. 

```csharp
using System;
using System.Globalization;
using System.Text.RegularExpressions;

public class MillisecondDisplay
{
   public static void Main()
   {
      string dateString = "7/16/2008 8:32:45.126 AM";

      try
      {
         DateTime dateValue = DateTime.Parse(dateString);
         DateTimeOffset dateOffsetValue = DateTimeOffset.Parse(dateString);

         // Display Millisecond component alone.
         Console.WriteLine("Millisecond component only: {0}", 
                           dateValue.ToString("fff"));
         Console.WriteLine("Millisecond component only: {0}", 
                           dateOffsetValue.ToString("fff"));

         // Display Millisecond component with full date and time.
         Console.WriteLine("Date and Time with Milliseconds: {0}", 
                           dateValue.ToString("MM/dd/yyyy hh:mm:ss.fff tt"));                        
         Console.WriteLine("Date and Time with Milliseconds: {0}", 
                           dateOffsetValue.ToString("MM/dd/yyyy hh:mm:ss.fff tt"));

         // Append millisecond pattern to current culture's full date time pattern
         string fullPattern = DateTimeFormatInfo.CurrentInfo.FullDateTimePattern;
         fullPattern = Regex.Replace(fullPattern, "(:ss|:s)", "$1.fff");

         // Display Millisecond component with modified full date and time pattern.
         Console.WriteLine("Modified full date time pattern: {0}", 
                           dateValue.ToString(fullPattern));
         Console.WriteLine("Modified full date time pattern: {0}",
                           dateOffsetValue.ToString(fullPattern));
      }
      catch (FormatException)
      {
         Console.WriteLine("Unable to convert {0} to a date.", dateString);
      }
   }
}
// The example displays the following output if the current culture is en-US:
//    Millisecond component only: 126
//    Millisecond component only: 126
//    Date and Time with Milliseconds: 07/16/2008 08:32:45.126 AM
//    Date and Time with Milliseconds: 07/16/2008 08:32:45.126 AM
//    Modified full date time pattern: Wednesday, July 16, 2008 8:32:45.126 AM
//    Modified full date time pattern: Wednesday, July 16, 2008 8:32:45.126 AM
```

```vb
Imports System.Globalization
Imports System.Text.REgularExpressions

Module MillisecondDisplay
   Public Sub Main()

      Dim dateString As String = "7/16/2008 8:32:45.126 AM"

      Try
         Dim dateValue As Date = Date.Parse(dateString)
         Dim dateOffsetValue As DateTimeOffset = DateTimeOffset.Parse(dateString)

         ' Display Millisecond component alone.
         Console.WriteLine("Millisecond component only: {0}", _
                           dateValue.ToString("fff"))
         Console.WriteLine("Millisecond component only: {0}", _
                           dateOffsetValue.ToString("fff"))

         ' Display Millisecond component with full date and time.
         Console.WriteLine("Date and Time with Milliseconds: {0}", _
                           dateValue.ToString("MM/dd/yyyy hh:mm:ss.fff tt"))                        
         Console.WriteLine("Date and Time with Milliseconds: {0}", _
                           dateOffsetValue.ToString("MM/dd/yyyy hh:mm:ss.fff tt"))

         ' Append millisecond pattern to current culture's full date time pattern
         Dim fullPattern As String = DateTimeFormatInfo.CurrentInfo.FullDateTimePattern
         fullPattern = Regex.Replace(fullPattern, "(:ss|:s)", "$1.fff")

         ' Display Millisecond component with modified full date and time pattern.
         Console.WriteLine("Modified full date time pattern: {0}", _
                           dateValue.ToString(fullPattern))                        
         Console.WriteLine("Modified full date time pattern: {0}", _
                           dateOffsetValue.ToString(fullPattern))
      Catch e As FormatException
         Console.WriteLine("Unable to convert {0} to a date.", dateString)      
      End Try
   End Sub
End Module
' The example displays the following output if the current culture is en-US:
'    Millisecond component only: 126
'    Millisecond component only: 126
'    Date and Time with Milliseconds: 07/16/2008 08:32:45.126 AM
'    Date and Time with Milliseconds: 07/16/2008 08:32:45.126 AM
'    Modified full date time pattern: Wednesday, July 16, 2008 8:32:45.126 AM
'    Modified full date time pattern: Wednesday, July 16, 2008 8:32:45.126 AM
```

Шаблон формата `fff` содержит конечные нули в значении миллисекунд. Шаблон формата `FFF` запрещает их. Эта разница показана в следующем примере.

```csharp
DateTime dateValue = new DateTime(2008, 7, 16, 8, 32, 45, 180); 
Console.WriteLine(dateValue.ToString("fff"));    
Console.WriteLine(dateValue.ToString("FFF"));
// The example displays the following output to the console:
//    180
//    18 
```

```vb
Dim dateValue As New Date(2008, 7, 16, 8, 32, 45, 180) 
Console.WriteLIne(dateValue.ToString("fff"))    
Console.WriteLine(dateValue.ToString("FFF"))
' The example displays the following output to the console:
'    180
'    18
```

Проблема с определением полного описателя пользовательского формата, содержащего компонент миллисекунд, состоит в том, что он жестко задает формат, который может не соответствовать взаимному расположению элементов времени в текущих региональных параметрах приложения. Лучшим вариантом будет его извлечение из шаблонов отображения даты и времени, определенных объектом текущих региональных параметров [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), и его изменение с целью включения миллисекунд. Этот подход также показан в примере. Извлекается полный шаблон даты и времени для текущих региональных параметров из свойства [DateTimeFormatInfo.FullDateTimePattern](xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern). Затем вставляется пользовательский шаблон `.ffff` после шаблона секунд. Обратите внимание, что в примере используется регулярное выражение для выполнения этой операции в одном методе.

Описатель настраиваемого формата также используется для отображения дробной части секунд, отличной от миллисекунд. Например, описатель пользовательского формата `f` или `F` отображает десятые доли секунды, описатель `ff` или `FF` — сотые доли секунды, а описатель `ffff` или `FFFF` — десятитысячные доли секунды. Дробные части миллисекунд усекаются, а не округляются в возвращаемой строке. Эти описатели формата используются в следующем примере.

```csharp
DateTime dateValue = new DateTime(2008, 7, 16, 8, 32, 45, 180); 
Console.WriteLine("{0} seconds", dateValue.ToString("s.f"));
Console.WriteLine("{0} seconds", dateValue.ToString("s.ff"));      
Console.WriteLine("{0} seconds", dateValue.ToString("s.ffff"));
// The example displays the following output to the console:
//    45.1 seconds
//    45.18 seconds
//    45.1800 seconds
```

```vb
Dim dateValue As New DateTime(2008, 7, 16, 8, 32, 45, 180) 
Console.WriteLine("{0} seconds", dateValue.ToString("s.f"))
Console.WriteLine("{0} seconds", dateValue.ToString("s.ff"))      
Console.WriteLine("{0} seconds", dateValue.ToString("s.ffff"))
' The example displays the following output to the console:
'    45.1 seconds
'    45.18 seconds
'    45.1800 seconds
```

> [!NOTE]
> Существует возможность отображать малые дробные части секунды, например десятитысячные или стотысячные доли секунды. Однако эти значения могут не иметь смысла. Точность значений даты и времени зависит от разрешения системных часов.

## <a name="see-also"></a>См. также

[System.Globalization.DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)

[Строки настраиваемых форматов даты и времени](custom-datetime.md)


