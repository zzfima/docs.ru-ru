---
title: "Практическое руководство. Отображение дат в календарях, отличных от григорианского"
description: "Практическое руководство. Отображение дат в календарях, отличных от григорианского"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 93f06e1d-544b-4ccc-a0b2-95cd674852cb
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 783b51f3145d8b11e79b99cfdc4baefe127306e3

---

# <a name="how-to-display-dates-in-nongregorian-calendars"></a>Практическое руководство. Отображение дат в календарях, отличных от григорианского

Типы [DateTime](xref:System.DateTime) и [DateTimeOffset](xref:System.DateTimeOffset) используют григорианский календарь в качестве календаря по умолчанию. Это означает, что вызов метода `ToString` для значения даты и времени выведет строковое представление даты и времени по григорианскому календарю даже в том случае, если значение даты и времени создавалось с помощью другого календаря. Это показано в следующем примере, в котором используется два различных способа создания значения даты и времени с персидским календарем. Однако при вызове метода [ToString](xref:System.DateTime.ToString) значения даты и времени в нем по-прежнему отображаются в григорианском календаре. В этом примере представлены два часто используемых неверных способа отображения даты в заданном календаре.

```csharp
PersianCalendar persianCal = new PersianCalendar();

DateTime persianDate = persianCal.ToDateTime(1387, 3, 18, 12, 0, 0, 0);
Console.WriteLine(persianDate.ToString());

persianDate = new DateTime(1387, 3, 18, persianCal);
Console.WriteLine(persianDate.ToString());
// The example displays the following output to the console:
//       6/7/2008 12:00:00 PM
//       6/7/2008 12:00:00 AM
```

```vb
Dim persianCal As New PersianCalendar()

Dim persianDate As Date = persianCal.ToDateTime(1387, 3, 18, _
                                                12, 0, 0, 0)
Console.WriteLine(persianDate.ToString())

persianDate = New DateTime(1387, 3, 18, persianCal)
Console.WriteLine(persianDate.ToString())
' The example displays the following output to the console:
'       6/7/2008 12:00:00 PM
'       6/7/2008 12:00:00 AM
```

Для отображения даты в конкретном календаре можно использовать два различных способа. Для первого необходимо, чтобы календарь был установлен в качестве календаря по умолчанию в соответствующих региональных параметрах. Второй может использоваться с любым календарем.

## <a name="to-display-the-date-for-a-cultures-default-calendar"></a>Отображение даты в календаре, который является календарем по умолчанию доя определенного языка и региональных параметров

1. Создайте экземпляр календаря, производного от класса [Calendar](xref:System.Globalization.Calendar), представляющего календарь, который будет использоваться.

2. Создать экземпляр объекта [CultureInfo](xref:System.Globalization.CultureInfo), представляющего язык и региональные параметры, которые будут использоваться для отображения даты.

3. Вызовите метод [Array.Exists&lt;T&gt;](xref:System.Array.Exists``1(``0[],System.Predicate{``0})), чтобы определить, является ли объект календаря элементом массива, возвращаемого свойством [CultureInfo.OptionalCalendars](xref:System.Globalization.CultureInfo.OptionalCalendars). Это означает, что календарь можно использовать в качестве календаря по умолчанию для объекта [CultureInfo](xref:System.Globalization.CultureInfo). Если это не является элементом массива, следуйте инструкциям в разделе "Отображение даты в любом календаре".

4. Присвойте объект календаря свойству [Calendar](xref:System.Globalization.DateTimeFormatInfo.Calendar) объекта [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), возвращаемого свойством [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat).

  > [!NOTE]
  > Класс [CultureInfo](xref:System.Globalization.CultureInfo) также имеет свойство [Calendar](xref:System.Globalization.CultureInfo.Calendar). Однако это свойство доступно только для чтения и является константой. Оно не изменяется для отражения нового календаря по умолчанию, присвоенного свойству [DateTimeFormatInfo.Calendar](xref:System.Globalization.DateTimeFormatInfo.Calendar).
  
5. Вызовите метод [DateTime.ToString(IFormatProvider)](xref:System.DateTime.ToString(System.IFormatProvider)) или [DateTime.ToString(String,IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) и передайте ему объект [CultureInfo](xref:System.Globalization.CultureInfo), для которого на предыдущем шаге был изменен календарь по умолчанию.

## <a name="to-display-the-date-in-any-calendar"></a>Отображение даты в любом календаре

1. Создайте экземпляр календаря, производного от класса [Calendar](xref:System.Globalization.Calendar), представляющего календарь, который будет использоваться.

2. Определите, какие элементы даты и времени должны отображаться в строковом представлении значения даты и времени.

3. Для каждого элемента даты и времени, который требуется отобразить, вызовите метод объекта календаря `Get…`. Доступны указанные далее методы.

    * [GetYear](xref:System.Globalization.Calendar.GetYear(System.DateTime)) — отображение года в соответствующем календаре.
    
    * [GetMonth](xref:System.Globalization.Calendar.GetMonth(System.DateTime)) — отображение месяца в соответствующем календаре. 
    
    * [GetDayOfMonth](xref:System.Globalization.Calendar.GetDayOfMonth(System.DateTime)) — отображение числа дней в месяце в соответствующем календаре.
    
    * [GetHour](xref:System.Globalization.Calendar.GetHour(System.DateTime)) — отображение часа дня в соответствующем календаре.
    
    * [GetMinute](xref:System.Globalization.Calendar.GetMinute(System.DateTime)) — отображение минут в часе в соответствующем календаре.
    
    * [GetSecond](xref:System.Globalization.Calendar.GetSecond(System.DateTime)) — отображение секунд в минуте в соответствующем календаре. 
    
    * [GetMilliseconds](xref:System.Globalization.Calendar.GetMilliseconds(System.DateTime)) — отображение миллисекунд в секунде в соответствующем календаре.
    
## <a name="example"></a>Пример
    
В примере отображается дата с помощью двух различных календарей. Отображается дата после определения исламского календаря в качестве календаря по умолчанию для региональных параметров ar-JO, а также дата с помощью персидского календаря, который не поддерживается в региональных параметрах fa-IR как дополнительный календарь.

```csharp
using System;
using System.Globalization;

public class CalendarDates
{
   public static void Main()
   {
      HijriCalendar hijriCal = new HijriCalendar();
      CalendarUtility hijriUtil = new CalendarUtility(hijriCal);
      DateTime dateValue1 = new DateTime(1429, 6, 29, hijriCal);
      DateTimeOffset dateValue2 = new DateTimeOffset(dateValue1, 
                                  TimeZoneInfo.Local.GetUtcOffset(dateValue1));
      CultureInfo jc = CultureInfo.CreateSpecificCulture("ar-JO");

      // Display the date using the Gregorian calendar.
      Console.WriteLine("Using the system default culture: {0}", 
                        dateValue1.ToString("d"));
      // Display the date using the ar-JO culture's original default calendar.
      Console.WriteLine("Using the ar-JO culture's original default calendar: {0}", 
                        dateValue1.ToString("d", jc));
      // Display the date using the Hijri calendar.
      Console.WriteLine("Using the ar-JO culture with Hijri as the default calendar:");
      // Display a Date value.
      Console.WriteLine(hijriUtil.DisplayDate(dateValue1, jc));
      // Display a DateTimeOffset value.
      Console.WriteLine(hijriUtil.DisplayDate(dateValue2, jc));

      Console.WriteLine();

      PersianCalendar persianCal = new PersianCalendar();
      CalendarUtility persianUtil = new CalendarUtility(persianCal);
      CultureInfo ic = CultureInfo.CreateSpecificCulture("fa-IR");

      // Display the date using the ir-FA culture's default calendar.
      Console.WriteLine("Using the ir-FA culture's default calendar: {0}",       
                        dateValue1.ToString("d", ic));
      // Display a Date value.
      Console.WriteLine(persianUtil.DisplayDate(dateValue1, ic));
      // Display a DateTimeOffset value.
      Console.WriteLine(persianUtil.DisplayDate(dateValue2, ic));
   }
}

public class CalendarUtility
{
   private Calendar thisCalendar;
   private CultureInfo targetCulture;

   public CalendarUtility(Calendar cal)
   {
      this.thisCalendar = cal;
   }

   private bool CalendarExists(CultureInfo culture)
   {
      this.targetCulture = culture;
      return Array.Exists(this.targetCulture.OptionalCalendars, 
                          this.HasSameName);
   }

   private bool HasSameName(Calendar cal)
   {
      if (cal.ToString() == thisCalendar.ToString())
         return true;
      else
         return false;
   }

   public string DisplayDate(DateTime dateToDisplay, CultureInfo culture)
   {
      DateTimeOffset displayOffsetDate = dateToDisplay;
      return DisplayDate(displayOffsetDate, culture);
   }

   public string DisplayDate(DateTimeOffset dateToDisplay, 
                             CultureInfo culture)
   {
      string specifier = "yyyy/MM/dd";

      if (this.CalendarExists(culture))
      {
         Console.WriteLine("Displaying date in supported {0} calendar...", 
                           this.thisCalendar.GetType().Name);
         culture.DateTimeFormat.Calendar = this.thisCalendar;
         return dateToDisplay.ToString(specifier, culture);
      }
      else
      {
         Console.WriteLine("Displaying date in unsupported {0} calendar...", 
                           thisCalendar.GetType().Name);

         string separator = targetCulture.DateTimeFormat.DateSeparator;

         return thisCalendar.GetYear(dateToDisplay.DateTime).ToString("0000") +
                separator +
                thisCalendar.GetMonth(dateToDisplay.DateTime).ToString("00") + 
                separator +
                thisCalendar.GetDayOfMonth(dateToDisplay.DateTime).ToString("00"); 
      }
   } 
}
// The example displays the following output to the console:
//       Using the system default culture: 7/3/2008
//       Using the ar-JO culture's original default calendar: 03/07/2008
//       Using the ar-JO culture with Hijri as the default calendar:
//       Displaying date in supported HijriCalendar calendar...
//       1429/06/29
//       Displaying date in supported HijriCalendar calendar...
//       1429/06/29
//       
//       Using the ir-FA culture's default calendar: 7/3/2008
//       Displaying date in unsupported PersianCalendar calendar...
//       1387/04/13
//       Displaying date in unsupported PersianCalendar calendar...
//       1387/04/13
```

```vb
Imports System.Globalization

Public Class CalendarDates
   Public Shared Sub Main()
      Dim hijriCal As New HijriCalendar()
      Dim hijriUtil As New CalendarUtility(hijriCal)
      Dim dateValue1 As Date = New Date(1429, 6, 29, hijriCal)
      Dim dateValue2 As DateTimeOffset = New DateTimeOffset(dateValue1, _
                                         TimeZoneInfo.Local.GetUtcOffset(dateValue1))
      Dim jc As CultureInfo = CultureInfo.CreateSpecificCulture("ar-JO")

      ' Display the date using the Gregorian calendar.
      Console.WriteLine("Using the system default culture: {0}", _
                        dateValue1.ToString("d"))
      ' Display the date using the ar-JO culture's original default calendar.
      Console.WriteLine("Using the ar-JO culture's original default calendar: {0}", _
                        dateValue1.ToString("d", jc))
      ' Display the date using the Hijri calendar.
      Console.WriteLine("Using the ar-JO culture with Hijri as the default calendar:")
      ' Display a Date value.
      Console.WriteLine(hijriUtil.DisplayDate(dateValue1, jc))
      ' Display a DateTimeOffset value.
      Console.WriteLine(hijriUtil.DisplayDate(dateValue2, jc))

      Console.WriteLine()

      Dim persianCal As New PersianCalendar()
      Dim persianUtil As New CalendarUtility(persianCal)
      Dim ic As CultureInfo = CultureInfo.CreateSpecificCulture("fa-IR")

      ' Display the date using the ir-FA culture's default calendar.
      Console.WriteLine("Using the ir-FA culture's default calendar: {0}", _      
                        dateValue1.ToString("d", ic))
      ' Display a Date value.
      Console.WriteLine(persianUtil.DisplayDate(dateValue1, ic))
      ' Display a DateTimeOffset value.
      Console.WriteLine(persianUtil.DisplayDate(dateValue2, ic))
   End Sub
End Class

Public Class CalendarUtility
   Private thisCalendar As Calendar
   Private targetCulture As CultureInfo

   Public Sub New(cal As Calendar)
      Me.thisCalendar = cal
   End Sub

   Private Function CalendarExists(culture As CultureInfo) As Boolean
      Me.targetCulture = culture
      Return Array.Exists(Me.targetCulture.OptionalCalendars, _
                          AddressOf Me.HasSameName)
   End Function 

   Private Function HasSameName(cal As Calendar) As Boolean
      If cal.ToString() = thisCalendar.ToString() Then
         Return True
      Else
         Return False
      End If
   End Function

   Public Function DisplayDate(dateToDisplay As Date, _
                               culture As CultureInfo) As String
      Dim displayOffsetDate As DateTimeOffset = dateToDisplay
      Return DisplayDate(displayOffsetDate, culture)
   End Function

   Public Function DisplayDate(dateToDisplay As DateTimeOffset, _
                               culture As CultureInfo) As String
      Dim specifier As String = "yyyy/MM/dd"

      If Me.CalendarExists(culture) Then
         Console.WriteLine("Displaying date in supported {0} calendar...", _
                           thisCalendar.GetType().Name)
         culture.DateTimeFormat.Calendar = Me.thisCalendar
         Return dateToDisplay.ToString(specifier, culture)
      Else
         Console.WriteLine("Displaying date in unsupported {0} calendar...", _
                           thisCalendar.GetType().Name)

         Dim separator As String = targetCulture.DateTimeFormat.DateSeparator

         Return thisCalendar.GetYear(dateToDisplay.DateTime).ToString("0000") & separator & _
                thisCalendar.GetMonth(dateToDisplay.DateTime).ToString("00") & separator & _
                thisCalendar.GetDayOfMonth(dateToDisplay.DateTime).ToString("00") 
      End If             
   End Function
End Class
' The example displays the following output to the console:
'       Using the system default culture: 7/3/2008
'       Using the ar-JO culture's original default calendar: 03/07/2008
'       Using the ar-JO culture with Hijri as the default calendar:
'       Displaying date in supported HijriCalendar calendar...
'       1429/06/29
'       Displaying date in supported HijriCalendar calendar...
'       1429/06/29
'       
'       Using the ir-FA culture's default calendar: 7/3/2008
'       Displaying date in unsupported PersianCalendar calendar...
'       1387/04/13
'       Displaying date in unsupported PersianCalendar calendar...
'       1387/04/13
```

Каждый объект [CultureInfo](xref:System.Globalization.CultureInfo) может поддерживать один или несколько календарей, которые обозначены свойством [OptionalCalendars](xref:System.Globalization.CultureInfo.OptionalCalendars). Один из них обозначается как календарь культуры по умолчанию для языка и региональных параметров и возвращается свойством только для чтения [CultureInfo.Calendar](xref:System.Globalization.CultureInfo.Calendar). Другие дополнительные календари могут быть назначены как календари по умолчанию путем присваивания объекта [Calendar](xref:System.Globalization.Calendar), представляющего календарь, свойству [DateTimeFormatInfo.Calendar](xref:System.Globalization.DateTimeFormatInfo.Calendar), возвращаемому свойством [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat). Однако некоторые календари, например персидский календарь, представленный классом [PersianCalendar](xref:System.Globalization.PersianCalendar), не могут служить дополнительными календарями для любого языка и региональных параметров.   

В примере определяется повторно используемый служебный класс календаря `CalendarUtility` для обработки множества данных, связанных с созданием строкового представления даты с помощью конкретного календаря. В классе `CalendarUtility`представлены следующие члены: 

* Параметризованный конструктор, единственным параметром которого является объект [Calendar](xref:System.Globalization.Calendar), которым представлена дата. Он присваивается закрытому полю класса.

* `CalendarExists` — закрытый метод, который возвращает логическое значение, показывающее, поддерживается ли календарь (представленный объектом `CalendarUtility`) объектом [CultureInfo](xref:System.Globalization.CultureInfo), который был передан методу в качестве параметра. Этот метод создает оболочку вызова для метода [Array.Exists&lt;T&gt;](xref:System.Array.Exists``1(``0[],System.Predicate{``0})), которому он передает массив [CultureInfo.OptionalCalendars](xref:System.Globalization.CultureInfo.OptionalCalendars).

* `HasSameName` — закрытый метод, назначенный делегату [Predicate&lt;T&gt;](xref:System.Predicate%601), который передается в качестве параметра методу [Array.Exists&lt;T&gt;](xref:System.Array.Exists``1(``0[],System.Predicate{``0})). Каждый элемент массива передается методу до тех пор, пока метод не вернет значение `true`. Этот метод определяет, совпадает ли имя дополнительного календаря с именем календаря, представленного объектом `CalendarUtility`.

* `DisplayDate` — перегруженный открытый метод, которому передается два параметра: значение [DateTime](xref:System.DateTime) или [DateTimeOffset](xref:System.DateTimeOffset) из календаря, представленного объектом `CalendarUtility`, а также язык и региональные параметры, правила форматирования которых будут использоваться. Его поведение при возврате строкового представления даты зависит от того, поддерживается ли целевой календарь в языке и региональных параметрах, правила форматирования которых будут использоваться.

Независимо от календаря, используемого для создания значения [DateTime](xref:System.DateTime) или значения [DateTimeOffset](xref:System.DateTimeOffset) в этом примере, это значение обычно выражается в виде григорианской даты. Это происходит потому, что типы [DateTime](xref:System.DateTime) и [DateTimeOffset](xref:System.DateTimeOffset) не сохраняют никаких данных календаря. Внутренне они представлены как число тактов, прошедших с момента полуночи 1 января 0001 г. Интерпретация этого числа зависит от календаря. Для большинства языков и региональных параметров по умолчанию используется григорианский календарь. 

## <a name="see-also"></a>См. также

[Выполнение операций форматирования](performing-formatting-operations.md)



<!--HONumber=Nov16_HO1-->


