---
title: "Анализ строк даты и времени в .NET"
description: "Анализ строк даты и времени в .NET"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: e61514cd-5329-4eb8-b122-482fffb54ab7
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: ad1976f44d8c4ec3a22c6156b4f6ad58f867908b

---

# <a name="parsing-date-and-time-strings-in-net"></a>Анализ строк даты и времени в .NET

Методы синтаксического анализа преобразуют заданное строковое представление даты и времени в эквивалентный объект [DateTime](xref:System.DateTime). Методы [Parse](xref:System.DateTime.Parse(System.String)) и [TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) преобразуют любое из нескольких общих представлений даты и времени. Методы [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) и [TryParseExact](xref:System.DateTime.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTime@)) преобразуют строковое представление, соответствующее шаблону, заданному строкой формата даты и времени. (См. разделы [Строки стандартных форматов даты и времени](standard-datetime.md) и [Строки настраиваемых форматов даты и времени](custom-datetime.md).) 

На синтаксический анализ влияют свойства поставщика формата, который предоставляет такие сведения, как строки, используемые для разделителей даты и времени, обозначения месяцев, дней и периодов. Поставщик формата является текущим объектом [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), неявно предоставляемым языком и региональными параметрами текущего потока или явно заданным параметром [IFormatProvider](xref:System.IFormatProvider) метода анализа. Для параметра [IFormatProvider](xref:System.IFormatProvider) необходимо указать объект [CultureInfo](xref:System.Globalization.CultureInfo), представляющий язык и региональные параметры, или объект [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo). 

Для выполнения синтаксического анализа строковое представление даты должно содержать месяц и, по крайней мере, день или год. Строковое представление времени должно содержать часы и, по крайней мере, минуты или обозначение AM/PM. Однако при разборе опущенных компонентов для них указываются значения по умолчанию, если это возможно. Отсутствующая дата по умолчанию становится текущей датой, отсутствующий год по умолчанию становится текущим годом, отсутствующий день месяца по умолчанию становится первым днем месяца, а отсутствующие время по умолчанию задается как полночь. 

Если строковое представление указывает только время, то при анализе возвращается объект [DateTime](xref:System.DateTime) с его свойствами [Year](xref:System.DateTime.Year), [Month](xref:System.DateTime.Month) и [Day](xref:System.DateTime.Day), которым присвоены соответствующие значения свойства [Today](xref:System.DateTime.Today). Однако если константа [DateTimeStyles.NoCurrentDateDefault](xref:System.Globalization.DateTimeStyles.NoCurrentDateDefault) указана в методе разбора, то свойствам год, месяц и день присваивается значение 1.

Помимо компонента даты и времени строковое представление даты и времени может содержать смещение, которое указывает, насколько время отличается от универсального синхронизированного времени (UTC). Например, строка "14/02/2007 5:32:00 -7: 00" определяет время, которое на семь часов меньше, чем UTC. Если смещение не задано в строковом представлении времени, то при анализе возвращается объект [DateTime](xref:System.DateTime) со свойством [Kind](xref:System.DateTime.Kind), имеющим значение [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified). Если смещение задано, то при разборе возвращается объект [DateTime](xref:System.DateTime) со свойством [Kind](xref:System.DateTime.Kind), имеющим значение [Local](xref:System.DateTimeKind.Local), а его значение настраивается на местный часовой пояс компьютера. Это поведение можно изменить с помощью константы [DateTimeStyles](xref:System.Globalization.DateTimeStyles) вместе с методом анализа.

Поставщик формата также используется для интерпретации неоднозначных числовых дат. Например, неясно, какие компоненты даты в строке "02/03/04" соответствуют месяцу, дню и году. В этом случае компоненты интерпретируются согласно их порядку расположения в схожих форматах даты в поставщике формата. 

## <a name="parse"></a>Анализ

В следующем примере кода показано использование метода `Parse` для преобразования строки в `DateTime`. В этом примере для разбора используется язык и региональные параметры, связанные с текущим потоком. Если [CultureInfo](xref:System.Globalization.CultureInfo), связанному с текущими языком и региональными параметрами, не удается выполнить синтаксический анализ входной строки, то создается исключение [FormatException](xref:System.FormatException).

```csharp
string MyString = "Jan 1, 2009";
DateTime MyDateTime = DateTime.Parse(MyString);
Console.WriteLine(MyDateTime);
// Displays the following output on a system whose culture is en-US:
//       1/1/2009 12:00:00 AM
```

```vb
Dim MyString As String = "Jan 1, 2009"
Dim MyDateTime As DateTime = DateTime.Parse(MyString)
Console.WriteLine(MyDateTime)
' Displays the following output on a system whose culture is en-US:
'       1/1/2009 12:00:00 AM
```

Можно также указать `CultureInfo`, для которого задан один из языков и региональных параметров, определяемых этим объектом, или можно указать один из стандартных объектов [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), возвращаемых свойством [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat). В следующем примере кода поставщик формата используется для разбора строки на немецком языке в `DateTime`. Для успешного анализа строки объект `CultureInfo`, представляющий немецкий язык и региональные параметры (de-DE), определен и передан вместе с анализируемой строкой. Это устраняет необходимость задания каких-либо параметров в `CurrentCulture` потока `CurrentThread`.

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      CultureInfo MyCultureInfo = new CultureInfo("de-DE");
      string MyString = "12 Juni 2008";
      DateTime MyDateTime = DateTime.Parse(MyString, MyCultureInfo);
      Console.WriteLine(MyDateTime);
   }
}
// The example displays the following output:
//       6/12/2008 12:00:00 AM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim MyCultureInfo As CultureInfo = new CultureInfo("de-DE")
      Dim MyString As String = "12 Juni 2008"
      Dim MyDateTime As DateTime = DateTime.Parse(MyString, MyCultureInfo)
      Console.WriteLine(MyDateTime)
   End Sub
End Module
' The example displays the following output:
'       6/12/2008 12:00:00 AM
```

Хотя можно использовать перегрузки метода [Parse](xref:System.DateTime.Parse(System.String)) для задания поставщиков пользовательских форматов, такой метод не поддерживает использование поставщиков нестандартных форматов. Для анализа даты и времени, выраженных в нестандартном формате, используйте метод [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)).

В следующем примере кода используется перечисление [DateTimeStyles](xref:System.Globalization.DateTimeStyles) для того, чтобы указать, что в `DateTime` не требуется возвращать текущие дату и время для полей, не определенных в строке.

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      CultureInfo MyCultureInfo = new CultureInfo("de-DE");
      string MyString = "12 Juni 2008";
      DateTime MyDateTime = DateTime.Parse(MyString, MyCultureInfo, 
                                           DateTimeStyles.NoCurrentDateDefault);
      Console.WriteLine(MyDateTime);
   }
}
// The example displays the following output if the current culture is en-US:
//      6/12/2008 12:00:00 AM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim MyCultureInfo As CultureInfo = new CultureInfo("de-DE")
      Dim MyString As String = "12 Juni 2008"
      Dim MyDateTime As DateTime = DateTime.Parse(MyString, MyCultureInfo)
      Console.WriteLine(MyDateTime)
   End Sub
End Module
' The example displays the following output:
'       6/12/2008 12:00:00 AM
```

## <a name="parseexact"></a>ParseExact

Метод [DateTime.ParseExact] ((xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) преобразует строку, которая соответствует указанному шаблону, в объект `DateTime`. Когда этому методу передается строка, не соответствующая указанному шаблону, создается исключение [FormatException](xref:System.FormatException). Можно задать один из стандартных описателей формата даты и времени или ограниченное сочетание пользовательских описателей формата для даты и времени. При использовании пользовательских описателей формата можно сконструировать пользовательскую строку распознавания. Сведения об описателях см. в разделах [Строки стандартных форматов даты и времени](standard-datetime.md) и [Строки настраиваемых форматов даты и времени](custom-datetime.md). 

Каждая перегрузка метода [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) также имеет параметр [IFormatProvider](xref:System.IFormatProvider), который, как правило, при форматировании строк предоставляет сведения о языке и региональных параметрах. Обычно этот объект [IFormatProvider](xref:System.IFormatProvider) является объектом [CultureInfo](xref:System.Globalization.CultureInfo), который представляет стандартные язык и региональные параметры, или объектом [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), возвращаемым свойством [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat). Однако, в отличие от других функций разбора даты и времени, этот метод также поддерживает [IFormatProvider](xref:System.IFormatProvider), который определяет нестандартный формат даты и времени. 

В следующем примере кода методу `ParseExact` передается переназначенный для анализа строковый объект, затем следует описатель формата, после которого идет объект `CultureInfo`. Этот метод `ParseExact` может анализировать только строки с шаблоном длинной даты на американском английском (en-US) языке.

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      CultureInfo MyCultureInfo = new CultureInfo("en-US");
      string[] MyString = {" Friday, April 10, 2009", "Friday, April 10, 2009"};
      foreach (string dateString in MyString)
      {
         try {
            DateTime MyDateTime = DateTime.ParseExact(dateString, "D", MyCultureInfo);
            Console.WriteLine(MyDateTime);
         }
         catch (FormatException) {
            Console.WriteLine("Unable to parse '{0}'", dateString);
         }
      }
   }
}
// The example displays the following output:
//       Unable to parse ' Friday, April 10, 2009'
//       4/10/2009 12:00:00 AM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim MyCultureInfo As CultureInfo = new CultureInfo("en-US")
      Dim MyString() As String = {" Friday, April 10, 2009", "Friday, April 10, 2009"}
      For Each dateString As String In MyString
         Try
            Dim MyDateTime As DateTime = DateTime.ParseExact(dateString, "D", _
                                                             MyCultureInfo)
            Console.WriteLine(MyDateTime)
         Catch e As FormatException
            Console.WriteLine("Unable to parse '{0}'", dateString)
         End Try
      Next
   End Sub
End Module
' The example displays the following output:
'       Unable to parse ' Friday, April 10, 2009'
'       4/10/2009 12:00:00 AM
```

## <a name="see-also"></a>См. также

[Анализ строк в .NET](parsing-strings.md)

[Типы форматирования в .NET](formatting-types.md)

[Преобразование типов в .NET](type-conversion.md)




<!--HONumber=Nov16_HO1-->


