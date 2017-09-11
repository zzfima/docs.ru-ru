---
title: "Анализ строк даты и времени в .NET"
description: "Анализ строк даты и времени в .NET"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: e61514cd-5329-4eb8-b122-482fffb54ab7
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: f0131baa0874880b6697458426da5ae9ce1705b7
ms.contentlocale: ru-ru
ms.lasthandoff: 03/02/2017

---

# <a name="parsing-date-and-time-strings-in-net"></a><span data-ttu-id="37840-104">Анализ строк даты и времени в .NET</span><span class="sxs-lookup"><span data-stu-id="37840-104">Parsing date and time strings in .NET</span></span>

<span data-ttu-id="37840-105">Методы синтаксического анализа преобразуют заданное строковое представление даты и времени в эквивалентный объект [DateTime](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="37840-105">Parsing methods convert the string representation of a date and time to an equivalent [DateTime](xref:System.DateTime) object.</span></span> <span data-ttu-id="37840-106">Методы [Parse](xref:System.DateTime.Parse(System.String)) и [TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) преобразуют любое из нескольких общих представлений даты и времени.</span><span class="sxs-lookup"><span data-stu-id="37840-106">The [Parse](xref:System.DateTime.Parse(System.String)) and [TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) methods convert any of several common representations of a date and time.</span></span> <span data-ttu-id="37840-107">Методы [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) и [TryParseExact](xref:System.DateTime.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTime@)) преобразуют строковое представление, соответствующее шаблону, заданному строкой формата даты и времени.</span><span class="sxs-lookup"><span data-stu-id="37840-107">The [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) and [TryParseExact](xref:System.DateTime.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTime@)) methods convert a string representation that conforms to the pattern specified by a date and time format string.</span></span> <span data-ttu-id="37840-108">(См. разделы [Строки стандартных форматов даты и времени](standard-datetime.md) и [Строки настраиваемых форматов даты и времени](custom-datetime.md).)</span><span class="sxs-lookup"><span data-stu-id="37840-108">(See the topics on [standard date and time format strings](standard-datetime.md) and [custom date and time format strings](custom-datetime.md).)</span></span> 

<span data-ttu-id="37840-109">На синтаксический анализ влияют свойства поставщика формата, который предоставляет такие сведения, как строки, используемые для разделителей даты и времени, обозначения месяцев, дней и периодов.</span><span class="sxs-lookup"><span data-stu-id="37840-109">Parsing is influenced by the properties of a format provider that supplies information such as the strings used for date and time separators, and the names of months, days, and eras.</span></span> <span data-ttu-id="37840-110">Поставщик формата является текущим объектом [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), неявно предоставляемым языком и региональными параметрами текущего потока или явно заданным параметром [IFormatProvider](xref:System.IFormatProvider) метода анализа.</span><span class="sxs-lookup"><span data-stu-id="37840-110">The format provider is the current [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object, which is provided implicitly by the current thread culture or explicitly by the [IFormatProvider](xref:System.IFormatProvider) parameter of a parsing method.</span></span> <span data-ttu-id="37840-111">Для параметра [IFormatProvider](xref:System.IFormatProvider) необходимо указать объект [CultureInfo](xref:System.Globalization.CultureInfo), представляющий язык и региональные параметры, или объект [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo).</span><span class="sxs-lookup"><span data-stu-id="37840-111">For the [IFormatProvider](xref:System.IFormatProvider) parameter, specify a [CultureInfo](xref:System.Globalization.CultureInfo) object, which represents a culture, or a [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object.</span></span> 

<span data-ttu-id="37840-112">Для выполнения синтаксического анализа строковое представление даты должно содержать месяц и, по крайней мере, день или год.</span><span class="sxs-lookup"><span data-stu-id="37840-112">The string representation of a date to be parsed must include the month and at least a day or year.</span></span> <span data-ttu-id="37840-113">Строковое представление времени должно содержать часы и, по крайней мере, минуты или обозначение AM/PM.</span><span class="sxs-lookup"><span data-stu-id="37840-113">The string representation of a time must include the hour and at least minutes or the AM/PM designator.</span></span> <span data-ttu-id="37840-114">Однако при разборе опущенных компонентов для них указываются значения по умолчанию, если это возможно.</span><span class="sxs-lookup"><span data-stu-id="37840-114">However, parsing supplies default values for omitted components if possible.</span></span> <span data-ttu-id="37840-115">Отсутствующая дата по умолчанию становится текущей датой, отсутствующий год по умолчанию становится текущим годом, отсутствующий день месяца по умолчанию становится первым днем месяца, а отсутствующие время по умолчанию задается как полночь.</span><span class="sxs-lookup"><span data-stu-id="37840-115">A missing date defaults to the current date, a missing year defaults to the current year, a missing day of the month defaults to the first day of the month, and a missing time defaults to midnight.</span></span> 

<span data-ttu-id="37840-116">Если строковое представление указывает только время, то при анализе возвращается объект [DateTime](xref:System.DateTime) с его свойствами [Year](xref:System.DateTime.Year), [Month](xref:System.DateTime.Month) и [Day](xref:System.DateTime.Day), которым присвоены соответствующие значения свойства [Today](xref:System.DateTime.Today).</span><span class="sxs-lookup"><span data-stu-id="37840-116">If the string representation specifies only a time, parsing returns a [DateTime](xref:System.DateTime) object with its [Year](xref:System.DateTime.Year), [Month](xref:System.DateTime.Month), and [Day](xref:System.DateTime.Day) properties set to the corresponding values of the [Today](xref:System.DateTime.Today) property.</span></span> <span data-ttu-id="37840-117">Однако если константа [DateTimeStyles.NoCurrentDateDefault](xref:System.Globalization.DateTimeStyles.NoCurrentDateDefault) указана в методе разбора, то свойствам год, месяц и день присваивается значение 1.</span><span class="sxs-lookup"><span data-stu-id="37840-117">However, if the [DateTimeStyles.NoCurrentDateDefault](xref:System.Globalization.DateTimeStyles.NoCurrentDateDefault) constant is specified in the parsing method, the resulting year, month, and day properties are set to the value 1.</span></span>

<span data-ttu-id="37840-118">Помимо компонента даты и времени строковое представление даты и времени может содержать смещение, которое указывает, насколько время отличается от универсального синхронизированного времени (UTC).</span><span class="sxs-lookup"><span data-stu-id="37840-118">In addition to a date and a time component, the string representation of a date and time can include an offset that indicates how much the time differs from Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="37840-119">Например, строка "14/02/2007 5:32:00 -7: 00" определяет время, которое на семь часов меньше, чем UTC.</span><span class="sxs-lookup"><span data-stu-id="37840-119">For example, the string "2/14/2007 5:32:00 -7:00" defines a time that is seven hours earlier than UTC.</span></span> <span data-ttu-id="37840-120">Если смещение не задано в строковом представлении времени, то при анализе возвращается объект [DateTime](xref:System.DateTime) со свойством [Kind](xref:System.DateTime.Kind), имеющим значение [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified).</span><span class="sxs-lookup"><span data-stu-id="37840-120">If an offset is omitted from the string representation of a time, parsing returns a [DateTime](xref:System.DateTime) object with its [Kind](xref:System.DateTime.Kind) property set to [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified).</span></span> <span data-ttu-id="37840-121">Если смещение задано, то при разборе возвращается объект [DateTime](xref:System.DateTime) со свойством [Kind](xref:System.DateTime.Kind), имеющим значение [Local](xref:System.DateTimeKind.Local), а его значение настраивается на местный часовой пояс компьютера.</span><span class="sxs-lookup"><span data-stu-id="37840-121">If an offset is specified, parsing returns a [DateTime](xref:System.DateTime) object with its [Kind](xref:System.DateTime.Kind) property set to [Local](xref:System.DateTimeKind.Local) and its value adjusted to the local time zone of your machine.</span></span> <span data-ttu-id="37840-122">Это поведение можно изменить с помощью константы [DateTimeStyles](xref:System.Globalization.DateTimeStyles) вместе с методом анализа.</span><span class="sxs-lookup"><span data-stu-id="37840-122">You can modify this behavior by using a [DateTimeStyles](xref:System.Globalization.DateTimeStyles) constant with the parsing method.</span></span>

<span data-ttu-id="37840-123">Поставщик формата также используется для интерпретации неоднозначных числовых дат.</span><span class="sxs-lookup"><span data-stu-id="37840-123">The format provider is also used to interpret an ambiguous numeric date.</span></span> <span data-ttu-id="37840-124">Например, неясно, какие компоненты даты в строке "02/03/04" соответствуют месяцу, дню и году.</span><span class="sxs-lookup"><span data-stu-id="37840-124">For example, it is not clear which components of the date represented by the string "02/03/04" are the month, day, and year.</span></span> <span data-ttu-id="37840-125">В этом случае компоненты интерпретируются согласно их порядку расположения в схожих форматах даты в поставщике формата.</span><span class="sxs-lookup"><span data-stu-id="37840-125">In this case, the components are interpreted according to the order of similar date formats in the format provider.</span></span> 

## <a name="parse"></a><span data-ttu-id="37840-126">Анализ</span><span class="sxs-lookup"><span data-stu-id="37840-126">Parse</span></span>

<span data-ttu-id="37840-127">В следующем примере кода показано использование метода `Parse` для преобразования строки в `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="37840-127">The following code example illustrates the use of the `Parse` method to convert a string into a `DateTime`.</span></span> <span data-ttu-id="37840-128">В этом примере для разбора используется язык и региональные параметры, связанные с текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="37840-128">This example uses the culture associated with the current thread to perform the parse.</span></span> <span data-ttu-id="37840-129">Если [CultureInfo](xref:System.Globalization.CultureInfo), связанному с текущими языком и региональными параметрами, не удается выполнить синтаксический анализ входной строки, то создается исключение [FormatException](xref:System.FormatException).</span><span class="sxs-lookup"><span data-stu-id="37840-129">If the [CultureInfo](xref:System.Globalization.CultureInfo) associated with the current culture cannot parse the input string, a [FormatException](xref:System.FormatException) is thrown.</span></span>

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

<span data-ttu-id="37840-130">Можно также указать `CultureInfo`, для которого задан один из языков и региональных параметров, определяемых этим объектом, или можно указать один из стандартных объектов [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), возвращаемых свойством [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat).</span><span class="sxs-lookup"><span data-stu-id="37840-130">You can also specify a `CultureInfo` set to one of the cultures defined by that object, or you can specify one of the standard [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) objects returned by the [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat) property.</span></span> <span data-ttu-id="37840-131">В следующем примере кода поставщик формата используется для разбора строки на немецком языке в `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="37840-131">The following code example uses a format provider to parse a German string into a `DateTime`.</span></span> <span data-ttu-id="37840-132">Для успешного анализа строки объект `CultureInfo`, представляющий немецкий язык и региональные параметры (de-DE), определен и передан вместе с анализируемой строкой.</span><span class="sxs-lookup"><span data-stu-id="37840-132">A `CultureInfo` representing the de-DE culture is defined and passed with the string being parsed to ensure successful parsing of this particular string.</span></span> <span data-ttu-id="37840-133">Это устраняет необходимость задания каких-либо параметров в `CurrentCulture` потока `CurrentThread`.</span><span class="sxs-lookup"><span data-stu-id="37840-133">This precludes whatever setting is in the `CurrentCulture` of the `CurrentThread`.</span></span>

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

<span data-ttu-id="37840-134">Хотя можно использовать перегрузки метода [Parse](xref:System.DateTime.Parse(System.String)) для задания поставщиков пользовательских форматов, такой метод не поддерживает использование поставщиков нестандартных форматов.</span><span class="sxs-lookup"><span data-stu-id="37840-134">However, although you can use overloads of the [Parse](xref:System.DateTime.Parse(System.String)) method to specify custom format providers, the method does not support the use of non-standard format providers.</span></span> <span data-ttu-id="37840-135">Для анализа даты и времени, выраженных в нестандартном формате, используйте метод [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)).</span><span class="sxs-lookup"><span data-stu-id="37840-135">To parse a date and time expressed in a non-standard format, use the [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) method instead.</span></span>

<span data-ttu-id="37840-136">В следующем примере кода используется перечисление [DateTimeStyles](xref:System.Globalization.DateTimeStyles) для того, чтобы указать, что в `DateTime` не требуется возвращать текущие дату и время для полей, не определенных в строке.</span><span class="sxs-lookup"><span data-stu-id="37840-136">The following code example uses the [DateTimeStyles](xref:System.Globalization.DateTimeStyles) enumeration to specify that the current date and time information should not be added to the `DateTime` for fields that the string does not define.</span></span>

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

## <a name="parseexact"></a><span data-ttu-id="37840-137">ParseExact</span><span class="sxs-lookup"><span data-stu-id="37840-137">ParseExact</span></span>

<span data-ttu-id="37840-138">Метод [DateTime.ParseExact] ((xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) преобразует строку, которая соответствует указанному шаблону, в объект `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="37840-138">The [DateTime.ParseExact]((xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) method converts a string that conforms to a specified string pattern to a `DateTime` object.</span></span> <span data-ttu-id="37840-139">Когда этому методу передается строка, не соответствующая указанному шаблону, создается исключение [FormatException](xref:System.FormatException).</span><span class="sxs-lookup"><span data-stu-id="37840-139">When a string that is not of the form specified is passed to this method, a [FormatException](xref:System.FormatException) is thrown.</span></span> <span data-ttu-id="37840-140">Можно задать один из стандартных описателей формата даты и времени или ограниченное сочетание пользовательских описателей формата для даты и времени.</span><span class="sxs-lookup"><span data-stu-id="37840-140">You can specify one of the standard date and time format specifiers or a limited combination of the custom date and time format specifiers.</span></span> <span data-ttu-id="37840-141">При использовании пользовательских описателей формата можно сконструировать пользовательскую строку распознавания.</span><span class="sxs-lookup"><span data-stu-id="37840-141">Using the custom format specifiers, it is possible for you to construct a custom recognition string.</span></span> <span data-ttu-id="37840-142">Сведения об описателях см. в разделах [Строки стандартных форматов даты и времени](standard-datetime.md) и [Строки настраиваемых форматов даты и времени](custom-datetime.md).</span><span class="sxs-lookup"><span data-stu-id="37840-142">For an explanation of the specifiers, see the topics on [standard date and time format strings](standard-datetime.md) and [custom date and time format strings](custom-datetime.md).</span></span> 

<span data-ttu-id="37840-143">Каждая перегрузка метода [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) также имеет параметр [IFormatProvider](xref:System.IFormatProvider), который, как правило, при форматировании строк предоставляет сведения о языке и региональных параметрах.</span><span class="sxs-lookup"><span data-stu-id="37840-143">Each overload of the [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) method also has an [IFormatProvider](xref:System.IFormatProvider) parameter that typically provides culture-specific information about the formatting of the string.</span></span> <span data-ttu-id="37840-144">Обычно этот объект [IFormatProvider](xref:System.IFormatProvider) является объектом [CultureInfo](xref:System.Globalization.CultureInfo), который представляет стандартные язык и региональные параметры, или объектом [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), возвращаемым свойством [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat).</span><span class="sxs-lookup"><span data-stu-id="37840-144">Typically, this [IFormatProvider](xref:System.IFormatProvider) object is a [CultureInfo](xref:System.Globalization.CultureInfo) object that represents a standard culture or a [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object that is returned by the [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat) property.</span></span> <span data-ttu-id="37840-145">Однако, в отличие от других функций разбора даты и времени, этот метод также поддерживает [IFormatProvider](xref:System.IFormatProvider), который определяет нестандартный формат даты и времени.</span><span class="sxs-lookup"><span data-stu-id="37840-145">However, unlike the other date and time parsing functions, this method also supports an [IFormatProvider](xref:System.IFormatProvider) that defines a non-standard date and time format.</span></span> 

<span data-ttu-id="37840-146">В следующем примере кода методу `ParseExact` передается переназначенный для анализа строковый объект, затем следует описатель формата, после которого идет объект `CultureInfo`.</span><span class="sxs-lookup"><span data-stu-id="37840-146">In the following code example, the `ParseExact` method is passed a string object to parse, followed by a format specifier, followed by a `CultureInfo` object.</span></span> <span data-ttu-id="37840-147">Этот метод `ParseExact` может анализировать только строки с шаблоном длинной даты на американском английском (en-US) языке.</span><span class="sxs-lookup"><span data-stu-id="37840-147">This `ParseExact` method can only parse strings that exhibit the long date pattern in the en-US culture.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="37840-148">См. также</span><span class="sxs-lookup"><span data-stu-id="37840-148">See Also</span></span>

[<span data-ttu-id="37840-149">Анализ строк в .NET</span><span class="sxs-lookup"><span data-stu-id="37840-149">Parsing strings in .NET</span></span>](parsing-strings.md)

[<span data-ttu-id="37840-150">Типы форматирования в .NET</span><span class="sxs-lookup"><span data-stu-id="37840-150">Formatting types in .NET</span></span>](formatting-types.md)

[<span data-ttu-id="37840-151">Преобразование типов в .NET</span><span class="sxs-lookup"><span data-stu-id="37840-151">Type conversion in .NET</span></span>](type-conversion.md)


