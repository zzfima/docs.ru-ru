---
title: "Анализ числовых строк в .NET"
description: "Анализ числовых строк в .NET"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: e393430a-731a-49fa-83de-ff7ed52d5704
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 85cd57d33b03f7a2105ee3f770b2f8bcc0a57ee4
ms.contentlocale: ru-ru
ms.lasthandoff: 03/02/2017

---

# <a name="parsing-numeric-strings-in-net"></a><span data-ttu-id="c1bbe-104">Анализ числовых строк в .NET</span><span class="sxs-lookup"><span data-stu-id="c1bbe-104">Parsing numeric strings in .NET</span></span>

<span data-ttu-id="c1bbe-105">Все числовые типы имеют два статических метода синтаксического анализа — `Parse` и `TryParse`, которые можно использовать для преобразования строкового представления числа в числовой тип.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-105">All numeric types have two static parsing methods, `Parse` and `TryParse`, that you can use to convert the string representation of a number into a numeric type.</span></span> <span data-ttu-id="c1bbe-106">Эти методы позволяют анализировать строки, которые были созданы с помощью строк формата, описанных в разделах [Строки стандартных числовых форматов](standard-numeric.md) и [Строки настраиваемых числовых форматов](custom-numeric.md).</span><span class="sxs-lookup"><span data-stu-id="c1bbe-106">These methods enable you to parse strings that were produced by using the format strings documented in [Standard Numeric Format Strings](standard-numeric.md) and [Custom Numeric Format Strings](custom-numeric.md).</span></span> <span data-ttu-id="c1bbe-107">По умолчанию методы `Parse` и `TryParse` могут успешно преобразовывать строки, содержащие целые десятичные числа, только в целочисленные значения.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-107">By default, the `Parse` and `TryParse` methods can successfully convert strings that contain integral decimal digits only to integer values.</span></span> <span data-ttu-id="c1bbe-108">Они могут успешно преобразовывать строки, содержащие целые и дробные десятичные числа, разделители групп и десятичные разделители, в значения с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-108">They can successfully convert strings that contain integral and fractional decimal digits, group separators, and a decimal separator to floating-point values.</span></span> <span data-ttu-id="c1bbe-109">Если операцию выполнить не удалось, метод `Parse` создает исключение, а метод `TryParse` возвращает значение `false`.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-109">The `Parse` method throws an exception if the operation fails, whereas the `TryParse` method returns `false`.</span></span>

## <a name="parsing-and-format-providers"></a><span data-ttu-id="c1bbe-110">Синтаксический анализ и поставщики формата</span><span class="sxs-lookup"><span data-stu-id="c1bbe-110">Parsing and format providers</span></span>

<span data-ttu-id="c1bbe-111">Как правило, строковые представления числовых значений зависят от языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-111">Typically, the string representations of numeric values differ by culture.</span></span> <span data-ttu-id="c1bbe-112">Для различных языков и региональных параметров используются различные элементы численных строк, такие как обозначения денежной единицы, разделители групп (тысяч) и десятичные разделители.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-112">Elements of numeric strings such as currency symbols, group (or thousands) separators, and decimal separators all vary by culture.</span></span> <span data-ttu-id="c1bbe-113">Методы анализа неявно или явно используют поставщик формата, распознающий эти различия для разных языков и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-113">Parsing methods either implicitly or explicitly use a format provider that recognizes these culture-specific variations.</span></span> <span data-ttu-id="c1bbe-114">Если поставщик формата не задан в вызове метода `Parse` или `TryParse`, используется поставщик формата, связанный с текущим языком и региональными параметрами (объект [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), возвращаемый свойством [NumberFormatInfo.CurrentInfo](xref:System.Globalization.NumberFormatInfo.CurrentInfo)).</span><span class="sxs-lookup"><span data-stu-id="c1bbe-114">If no format provider is specified in a call to the `Parse` or `TryParse` method, the format provider associated with the current thread culture (the [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object returned by the [NumberFormatInfo.CurrentInfo](xref:System.Globalization.NumberFormatInfo.CurrentInfo) property) is used.</span></span> 

<span data-ttu-id="c1bbe-115">Поставщик формата представлен реализацией интерфейса [IFormatProvider](xref:System.Globalization.NumberFormatInfo.CurrentInfo).</span><span class="sxs-lookup"><span data-stu-id="c1bbe-115">A format provider is represented by an [IFormatProvider](xref:System.Globalization.NumberFormatInfo.CurrentInfo) implementation.</span></span> <span data-ttu-id="c1bbe-116">Этот интерфейс содержит только один член — метод [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)), единственным параметром которого является объект [Type](xref:System.Type), представляющий тип для форматирования.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-116">This interface has a single member, the [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) method, whose single parameter is a [Type](xref:System.Type) object that represents the type to be formatted.</span></span> <span data-ttu-id="c1bbe-117">Этот метод возвращает объект, предоставляющий сведения о форматировании.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-117">This method returns the object that provides formatting information.</span></span> <span data-ttu-id="c1bbe-118">.NET поддерживает следующие две реализации [IFormatProvider](xref:System.Globalization.NumberFormatInfo.CurrentInfo) для синтаксического анализа числовых строк:</span><span class="sxs-lookup"><span data-stu-id="c1bbe-118">.NET supports the following two [IFormatProvider](xref:System.Globalization.NumberFormatInfo.CurrentInfo) implementations for parsing numeric strings:</span></span>

* <span data-ttu-id="c1bbe-119">объект [CultureInfo](xref:System.Globalization.CultureInfo), метод [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) которого возвращает объект [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), предоставляющий характерные для конкретного языка и региональных параметров сведения о форматировании;</span><span class="sxs-lookup"><span data-stu-id="c1bbe-119">A [CultureInfo](xref:System.Globalization.CultureInfo) object whose [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) method returns a [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object that provides culture-specific formatting information.</span></span>

* <span data-ttu-id="c1bbe-120">объект [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), метод [NumberFormatInfo.GetFormat](xref:System.Globalization.NumberFormatInfo.GetFormat(System.Type)) которого возвращает сам себя.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-120">A [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object whose [NumberFormatInfo.GetFormat](xref:System.Globalization.NumberFormatInfo.GetFormat(System.Type)) method returns itself.</span></span>

<span data-ttu-id="c1bbe-121">В следующем примере предпринимается попытка преобразования каждой строки массива в значение [Double](xref:System.Double).</span><span class="sxs-lookup"><span data-stu-id="c1bbe-121">The following example tries to convert each string in an array to a [Double](xref:System.Double) value.</span></span> <span data-ttu-id="c1bbe-122">Сначала предпринимается попытка выполнить анализ строки с помощью поставщика формата, отражающего правила для языка и региональных параметров "Английский (США)".</span><span class="sxs-lookup"><span data-stu-id="c1bbe-122">It first tries to parse the string by using a format provider that reflects the conventions of the English (United States) culture.</span></span> <span data-ttu-id="c1bbe-123">Если в ходе операции создается исключение [FormatException](xref:System.FormatException), предпринимается попытка выполнить анализ строки с помощью поставщика формата, отражающего правила для языка и региональных параметров "Французский (Франция)".</span><span class="sxs-lookup"><span data-stu-id="c1bbe-123">If this operation throws a [FormatException](xref:System.FormatException), it tries to parse the string by using a format provider that reflects the conventions of the French (France) culture.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      string[] values = { "1,304.16", "$1,456.78", "1,094", "152", 
                          "123,45 €", "1 304,16", "Ae9f" };
      double number;
      CultureInfo culture = null;

      foreach (string value in values) {
         try {
            culture = CultureInfo.CreateSpecificCulture("en-US");
            number = Double.Parse(value, culture);
            Console.WriteLine("{0}: {1} --> {2}", culture.Name, value, number);
         }   
         catch (FormatException) {
            Console.WriteLine("{0}: Unable to parse '{1}'.", 
                              culture.Name, value);
            culture = CultureInfo.CreateSpecificCulture("fr-FR");
            try {
               number = Double.Parse(value, culture);
               Console.WriteLine("{0}: {1} --> {2}", culture.Name, value, number);
            }
            catch (FormatException) {
               Console.WriteLine("{0}: Unable to parse '{1}'.", 
                                 culture.Name, value);
            }
         }
         Console.WriteLine();
      }   
   }
}
// The example displays the following output:
//    en-US: 1,304.16 --> 1304.16
//    
//    en-US: Unable to parse '$1,456.78'.
//    fr-FR: Unable to parse '$1,456.78'.
//    
//    en-US: 1,094 --> 1094
//    
//    en-US: 152 --> 152
//    
//    en-US: Unable to parse '123,45 €'.
//    fr-FR: Unable to parse '123,45 €'.
//    
//    en-US: Unable to parse '1 304,16'.
//    fr-FR: 1 304,16 --> 1304.16
//    
//    en-US: Unable to parse 'Ae9f'.
//    fr-FR: Unable to parse 'Ae9f'.
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim values() As String = { "1,304.16", "$1,456.78", "1,094", "152", 
                                 "123,45 €", "1 304,16", "Ae9f" }
      Dim number As Double
      Dim culture As CultureInfo = Nothing

      For Each value As String In values
         Try
            culture = CultureInfo.CreateSpecificCulture("en-US")
            number = Double.Parse(value, culture)
            Console.WriteLine("{0}: {1} --> {2}", culture.Name, value, number)
         Catch e As FormatException
            Console.WriteLine("{0}: Unable to parse '{1}'.", 
                              culture.Name, value)
            culture = CultureInfo.CreateSpecificCulture("fr-FR")
            Try
               number = Double.Parse(value, culture)
               Console.WriteLine("{0}: {1} --> {2}", culture.Name, value, number)
            Catch ex As FormatException
               Console.WriteLine("{0}: Unable to parse '{1}'.", 
                                 culture.Name, value)
            End Try
         End Try
         Console.WriteLine()
      Next
   End Sub
End Module
' The example displays the following output:
'    en-US: 1,304.16 --> 1304.16
'    
'    en-US: Unable to parse '$1,456.78'.
'    fr-FR: Unable to parse '$1,456.78'.
'    
'    en-US: 1,094 --> 1094
'    
'    en-US: 152 --> 152
'    
'    en-US: Unable to parse '123,45 €'.
'    fr-FR: Unable to parse '123,45 €'.
'    
'    en-US: Unable to parse '1 304,16'.
'    fr-FR: 1 304,16 --> 1304.16
'    
'    en-US: Unable to parse 'Ae9f'.
'    fr-FR: Unable to parse 'Ae9f'.
```

## <a name="parsing-and-numberstyles-values"></a><span data-ttu-id="c1bbe-124">Синтаксический анализ и значения NumberStyles</span><span class="sxs-lookup"><span data-stu-id="c1bbe-124">Parsing and NumberStyles values</span></span>

<span data-ttu-id="c1bbe-125">Элементы стиля, такие как пробелы, разделители групп и десятичные разделители, которые могут быть обработаны при синтаксическом анализе, определяются значением перечисления [NumberStyles](xref:System.Globalization.NumberStyles).</span><span class="sxs-lookup"><span data-stu-id="c1bbe-125">The style elements (such as white space, group separators, and decimal separator) that the parse operation can handle are defined by a [NumberStyles](xref:System.Globalization.NumberStyles) enumeration value.</span></span> <span data-ttu-id="c1bbe-126">По умолчанию строки, представляющие целые значения, обрабатываются с использованием значения [NumberStyles.Integer](xref:System.Globalization.NumberStyles.Integer), разрешающего только цифры, начальные и конечные пробелы и знак в начале.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-126">By default, strings that represent integer values are parsed by using the [NumberStyles.Integer](xref:System.Globalization.NumberStyles.Integer) value, which permits only numeric digits, leading and trailing white space, and a leading sign.</span></span> <span data-ttu-id="c1bbe-127">Строки, представляющие значения с плавающей запятой, анализируются с использованием сочетания значений [NumberStyles.Float](xref:System.Globalization.NumberStyles.Float) и [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands). Такой смешанный стиль разрешает десятичные числа, начальные и конечные пробелы, знак в начале, десятичный разделитель, разделитель групп и показатель экспоненциального представления.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-127">Strings that represent floating-point values are parsed using a combination of the [NumberStyles.Float](xref:System.Globalization.NumberStyles.Float) and [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands) values; this composite style permits decimal digits along with leading and trailing white space, a leading sign, a decimal separator, a group separator, and an exponent.</span></span> <span data-ttu-id="c1bbe-128">Вызвав перегрузку метода `Parse` или `TryParse`, включающего параметр типа [NumberStyles](xref:System.Globalization.NumberStyles), и установив один или несколько флагов [NumberStyles](xref:System.Globalization.NumberStyles), можно управлять элементами стиля, которые могут присутствовать в строке, для успешного выполнения операции синтаксического анализа.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-128">By calling an overload of the `Parse` or `TryParse` method that includes a parameter of type [NumberStyles](xref:System.Globalization.NumberStyles) and setting one or more [NumberStyles](xref:System.Globalization.NumberStyles) flags, you can control the style elements that can be present in the string for the parse operation to succeed.</span></span> 

<span data-ttu-id="c1bbe-129">Например, строка, содержащая разделитель групп, не может быть преобразована в значение [Int32](xref:System.Int32) с помощью метода [Int32.Parse(String)](xref:System.Int32.Parse(System.String)).</span><span class="sxs-lookup"><span data-stu-id="c1bbe-129">For example, a string that contains a group separator cannot be converted to an [Int32](xref:System.Int32) value by using the [Int32.Parse(String)](xref:System.Int32.Parse(System.String)) method.</span></span> <span data-ttu-id="c1bbe-130">Однако преобразование пройдет успешно, если установить флаг [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-130">However, the conversion succeeds if you use the [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands) flag, as the following example illustrates.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      string value = "1,304";
      int number;
      IFormatProvider provider = CultureInfo.CreateSpecificCulture("en-US");
      if (Int32.TryParse(value, out number))
         Console.WriteLine("{0} --> {1}", value, number);
      else
         Console.WriteLine("Unable to convert '{0}'", value);

      if (Int32.TryParse(value, NumberStyles.Integer | NumberStyles.AllowThousands, 
                        provider, out number))
         Console.WriteLine("{0} --> {1}", value, number);
      else
         Console.WriteLine("Unable to convert '{0}'", value);
   }
}
// The example displays the following output:
//       Unable to convert '1,304'
//       1,304 --> 1304
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim value As String = "1,304"
      Dim number As Integer
      Dim provider As IFormatProvider = CultureInfo.CreateSpecificCulture("en-US")
      If Int32.TryParse(value, number) Then
         Console.WriteLine("{0} --> {1}", value, number)
      Else
         Console.WriteLine("Unable to convert '{0}'", value)
      End If

      If Int32.TryParse(value, NumberStyles.Integer Or NumberStyles.AllowThousands, 
                        provider, number) Then
         Console.WriteLine("{0} --> {1}", value, number)
      Else
         Console.WriteLine("Unable to convert '{0}'", value)
      End If
   End Sub
End Module
' The example displays the following output:
'       Unable to convert '1,304'
'       1,304 --> 1304
```

> <span data-ttu-id="c1bbe-131">**Предупреждение**</span><span class="sxs-lookup"><span data-stu-id="c1bbe-131">**Warning**</span></span>
>
> <span data-ttu-id="c1bbe-132">Операция синтаксического анализа всегда использует правила форматирования конкретного языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-132">The parse operation always uses the formatting conventions of a particular culture.</span></span> <span data-ttu-id="c1bbe-133">Если не задать язык и региональные параметры, передав объект [CultureInfo](xref:System.Globalization.CultureInfo) или [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), используются язык и региональные параметры, связанные с текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-133">If you do not specify a culture by passing a [CultureInfo](xref:System.Globalization.CultureInfo) or [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object, the culture associated with the current thread is used.</span></span>
 
<span data-ttu-id="c1bbe-134">В следующей таблице перечислены члены перечисления [NumberStyles](xref:System.Globalization.NumberStyles) и описано их влияние на операцию синтаксического анализа.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-134">The following table lists the members of the [NumberStyles](xref:System.Globalization.NumberStyles) enumeration and describes the effect that they have on the parsing operation.</span></span>

<span data-ttu-id="c1bbe-135">Значение NumberStyles</span><span class="sxs-lookup"><span data-stu-id="c1bbe-135">NumberStyles value</span></span> | <span data-ttu-id="c1bbe-136">Влияние на анализируемую строку</span><span class="sxs-lookup"><span data-stu-id="c1bbe-136">Effect on the string to be parsed</span></span>
------------------ | --------------------------------- 
[<span data-ttu-id="c1bbe-137">NumberStyles.None</span><span class="sxs-lookup"><span data-stu-id="c1bbe-137">NumberStyles.None</span></span>](xref:System.Globalization.NumberStyles.None) | <span data-ttu-id="c1bbe-138">Разрешены только цифры.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-138">Only numeric digits are permitted.</span></span>
[<span data-ttu-id="c1bbe-139">NumberStyles.AllowDecimalPoint</span><span class="sxs-lookup"><span data-stu-id="c1bbe-139">NumberStyles.AllowDecimalPoint</span></span>](xref:System.Globalization.NumberStyles.AllowDecimalPoint) | <span data-ttu-id="c1bbe-140">Разрешены десятичный разделитель и дробные числа.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-140">The decimal separator and fractional digits are permitted.</span></span> <span data-ttu-id="c1bbe-141">Для целых чисел в качестве дробного числа разрешен только ноль.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-141">For integer values, only zero is permitted as a fractional digit.</span></span> <span data-ttu-id="c1bbe-142">Допустимые десятичные разделители определяются свойством [NumberFormatInfo.NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator) или [NumberFormatInfo.CurrencyDecimalSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator).</span><span class="sxs-lookup"><span data-stu-id="c1bbe-142">Valid decimal separators are determined by the [NumberFormatInfo.NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator) or [NumberFormatInfo.CurrencyDecimalSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator) property.</span></span>
[<span data-ttu-id="c1bbe-143">NumberStyles.AllowExponent</span><span class="sxs-lookup"><span data-stu-id="c1bbe-143">NumberStyles.AllowExponent</span></span>](xref:System.Globalization.NumberStyles.AllowExponent) | <span data-ttu-id="c1bbe-144">Для указания экспоненциального представления может использоваться символ "e" или "E".</span><span class="sxs-lookup"><span data-stu-id="c1bbe-144">The "e" or "E" character can be used to indicate exponential notation.</span></span>
[<span data-ttu-id="c1bbe-145">NumberStyles.AllowLeadingWhite</span><span class="sxs-lookup"><span data-stu-id="c1bbe-145">NumberStyles.AllowLeadingWhite</span></span>](xref:System.Globalization.NumberStyles.AllowLeadingWhite) | <span data-ttu-id="c1bbe-146">Разрешены начальные пробелы.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-146">Leading white space is permitted.</span></span>
[<span data-ttu-id="c1bbe-147">NumberStyles.AllowTrailingWhite</span><span class="sxs-lookup"><span data-stu-id="c1bbe-147">NumberStyles.AllowTrailingWhite</span></span>](xref:System.Globalization.NumberStyles.AllowTrailingWhite) | <span data-ttu-id="c1bbe-148">Разрешены конечные пробелы.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-148">Trailing white space is permitted.</span></span>
[<span data-ttu-id="c1bbe-149">NumberStyles.AllowLeadingSign</span><span class="sxs-lookup"><span data-stu-id="c1bbe-149">NumberStyles.AllowLeadingSign</span></span>](xref:System.Globalization.NumberStyles.AllowLeadingSign) | <span data-ttu-id="c1bbe-150">Разрешен знак плюс или минус перед числом.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-150">A positive or negative sign can precede numeric digits.</span></span>
[<span data-ttu-id="c1bbe-151">NumberStyles.AllowTrailingSign</span><span class="sxs-lookup"><span data-stu-id="c1bbe-151">NumberStyles.AllowTrailingSign</span></span>](xref:System.Globalization.NumberStyles.AllowTrailingSign) | <span data-ttu-id="c1bbe-152">Разрешен знак плюс или минус, следующий за числом.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-152">A positive or negative sign can follow numeric digits.</span></span>
[<span data-ttu-id="c1bbe-153">NumberStyles.AllowParentheses</span><span class="sxs-lookup"><span data-stu-id="c1bbe-153">NumberStyles.AllowParentheses</span></span>](xref:System.Globalization.NumberStyles.AllowParentheses) | <span data-ttu-id="c1bbe-154">Для обозначения отрицательных значений можно использовать скобки.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-154">Parentheses can be used to indicate negative values.</span></span>
[<span data-ttu-id="c1bbe-155">NumberStyles.AllowThousands</span><span class="sxs-lookup"><span data-stu-id="c1bbe-155">NumberStyles.AllowThousands</span></span>](xref:System.Globalization.NumberStyles.AllowThousands) | <span data-ttu-id="c1bbe-156">Разрешен разделитель групп.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-156">The group separator is permitted.</span></span> <span data-ttu-id="c1bbe-157">Символ разделителя групп определяется свойством [NumberFormatInfo.NumberGroupSeparator](xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator) или [NumberFormatInfo.CurrencyGroupSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator).</span><span class="sxs-lookup"><span data-stu-id="c1bbe-157">The group separator character is determined by the [NumberFormatInfo.NumberGroupSeparator](xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator) or [NumberFormatInfo.CurrencyGroupSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator) property.</span></span>
[<span data-ttu-id="c1bbe-158">NumberStyles.AllowCurrencySymbol</span><span class="sxs-lookup"><span data-stu-id="c1bbe-158">NumberStyles.AllowCurrencySymbol</span></span>](xref:System.Globalization.NumberStyles.AllowCurrencySymbol) | <span data-ttu-id="c1bbe-159">Разрешено обозначение денежной единицы.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-159">The currency symbol is permitted.</span></span> <span data-ttu-id="c1bbe-160">Обозначение денежной единицы определяется свойством [NumberFormatInfo.CurrencySymbol](xref:System.Globalization.NumberFormatInfo.CurrencySymbol) свойство.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-160">The currency symbol is defined by the [NumberFormatInfo.CurrencySymbol](xref:System.Globalization.NumberFormatInfo.CurrencySymbol) property.</span></span>
[<span data-ttu-id="c1bbe-161">NumberStyles.AllowHexSpecifier</span><span class="sxs-lookup"><span data-stu-id="c1bbe-161">NumberStyles.AllowHexSpecifier</span></span>](xref:System.Globalization.NumberStyles.AllowHexSpecifier) | <span data-ttu-id="c1bbe-162">Анализируемая строка интерпретируется как шестнадцатеричное число.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-162">The string to be parsed is interpreted as a hexadecimal number.</span></span> <span data-ttu-id="c1bbe-163">Он может включать символы шестнадцатеричного формата 0–9, A–F или a–f.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-163">It can include the hexadecimal digits 0-9, A-F, and a-f.</span></span> <span data-ttu-id="c1bbe-164">Этот флаг используется только для анализа целых значений.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-164">This flag can be used only to parse integer values.</span></span>
 
<span data-ttu-id="c1bbe-165">Кроме того, перечисление [NumberStyles](xref:System.Globalization.NumberStyles) предоставляет следующие смешанные стили, включающие несколько флагов [NumberStyles](xref:System.Globalization.NumberStyles).</span><span class="sxs-lookup"><span data-stu-id="c1bbe-165">In addition, the [NumberStyles](xref:System.Globalization.NumberStyles) enumeration provides the following composite styles, which include multiple [NumberStyles](xref:System.Globalization.NumberStyles) flags.</span></span> 

<span data-ttu-id="c1bbe-166">Составное значение NumberStyles</span><span class="sxs-lookup"><span data-stu-id="c1bbe-166">Composite NumberStyles value</span></span> | <span data-ttu-id="c1bbe-167">Включает члены</span><span class="sxs-lookup"><span data-stu-id="c1bbe-167">Includes members</span></span>
---------------------------- | ---------------- 
[<span data-ttu-id="c1bbe-168">NumberStyles.Integer</span><span class="sxs-lookup"><span data-stu-id="c1bbe-168">NumberStyles.Integer</span></span>](xref:System.Globalization.NumberStyles.Integer) | <span data-ttu-id="c1bbe-169">Включает стили [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite) и [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign).</span><span class="sxs-lookup"><span data-stu-id="c1bbe-169">Includes the [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), and [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign) styles.</span></span> <span data-ttu-id="c1bbe-170">Это стиль по умолчанию, используемый для анализа целых значений.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-170">This is the default style used to parse integer values.</span></span>
[<span data-ttu-id="c1bbe-171">NumberStyles.Number</span><span class="sxs-lookup"><span data-stu-id="c1bbe-171">NumberStyles.Number</span></span>](xref:System.Globalization.NumberStyles.Number) | <span data-ttu-id="c1bbe-172">Включает стили [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign), [NumberStyles.AllowTrailingSign](xref:System.Globalization.NumberStyles.AllowTrailingSign), [NumberStyles.AllowDecimalPoint](xref:System.Globalization.NumberStyles.AllowDecimalPoint) и [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands).</span><span class="sxs-lookup"><span data-stu-id="c1bbe-172">Includes the [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign), [NumberStyles.AllowTrailingSign](xref:System.Globalization.NumberStyles.AllowTrailingSign), [NumberStyles.AllowDecimalPoint](xref:System.Globalization.NumberStyles.AllowDecimalPoint), and [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands) styles.</span></span>
[<span data-ttu-id="c1bbe-173">NumberStyles.Float</span><span class="sxs-lookup"><span data-stu-id="c1bbe-173">NumberStyles.Float</span></span>](xref:System.Globalization.NumberStyles.Float) | <span data-ttu-id="c1bbe-174">Включает стили [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign), [NumberStyles.AllowDecimalPoint](xref:System.Globalization.NumberStyles.AllowDecimalPoint) и [NumberStyles.AllowExponent](xref:System.Globalization.NumberStyles.AllowExponent).</span><span class="sxs-lookup"><span data-stu-id="c1bbe-174">Includes the [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign), [NumberStyles.AllowDecimalPoint](xref:System.Globalization.NumberStyles.AllowDecimalPoint), and [NumberStyles.AllowExponent](xref:System.Globalization.NumberStyles.AllowExponent) styles.</span></span>
[<span data-ttu-id="c1bbe-175">NumberStyles.Currency</span><span class="sxs-lookup"><span data-stu-id="c1bbe-175">NumberStyles.Currency</span></span>](xref:System.Globalization.NumberStyles.Currency) | <span data-ttu-id="c1bbe-176">Включает все стили, кроме [NumberStyles.AllowExponent](xref:System.Globalization.NumberStyles.AllowExponent) и [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier).</span><span class="sxs-lookup"><span data-stu-id="c1bbe-176">Includes all styles except [NumberStyles.AllowExponent](xref:System.Globalization.NumberStyles.AllowExponent) and [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier).</span></span>
[<span data-ttu-id="c1bbe-177">NumberStyles.Any</span><span class="sxs-lookup"><span data-stu-id="c1bbe-177">NumberStyles.Any</span></span>](xref:System.Globalization.NumberStyles.Any) | <span data-ttu-id="c1bbe-178">Включает все стили, кроме [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier).</span><span class="sxs-lookup"><span data-stu-id="c1bbe-178">Includes all styles except [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier).</span></span>
[<span data-ttu-id="c1bbe-179">NumberStyles.HexNumber</span><span class="sxs-lookup"><span data-stu-id="c1bbe-179">NumberStyles.HexNumber</span></span>](xref:System.Globalization.NumberStyles.HexNumber) | <span data-ttu-id="c1bbe-180">Включает стили [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite) и [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier).</span><span class="sxs-lookup"><span data-stu-id="c1bbe-180">Includes the [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), and [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier) styles.</span></span>
 
## <a name="parsing-and-unicode-digits"></a><span data-ttu-id="c1bbe-181">Синтаксический анализ и цифры в Юникоде</span><span class="sxs-lookup"><span data-stu-id="c1bbe-181">Parsing and Unicode digits</span></span>

<span data-ttu-id="c1bbe-182">Стандарт Юникод определяет кодовые точки для цифр в различных системах письма.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-182">The Unicode standard defines code points for digits in various writing systems.</span></span> <span data-ttu-id="c1bbe-183">Например, кодовые точки в диапазоне от U+0030 до U+0039 представляют основные цифры от 0 до 9, кодовые точки в диапазоне от U+09E6 до U+09EF представляют бенгальские цифры от 0 до 9, а кодовые точки в диапазоне от U+FF10 до U+FF19 представляют полноширинные цифры от 0 до 9.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-183">For example, code points from U+0030 to U+0039 represent the basic Latin digits 0 through 9, code points from U+09E6 to U+09EF represent the Bangla digits 0 through 9, and code points from U+FF10 to U+FF19 represent the Fullwidth digits 0 through 9.</span></span> <span data-ttu-id="c1bbe-184">Однако методами синтаксического анализа распознаются только основные цифры от 0 до 9 (кодовые точки от U+0030 до U+ 0039).</span><span class="sxs-lookup"><span data-stu-id="c1bbe-184">However, the only numeric digits recognized by parsing methods are the basic Latin digits 0-9 with code points from U+0030 to U+0039.</span></span> <span data-ttu-id="c1bbe-185">Если методу анализа чисел передается строка, содержащая любые другие цифры, метод создает исключение [FormatException](xref:System.FormatException).</span><span class="sxs-lookup"><span data-stu-id="c1bbe-185">If a numeric parsing method is passed a string that contains any other digits, the method throws a [FormatException](xref:System.FormatException).</span></span>

<span data-ttu-id="c1bbe-186">В следующем примере используется метод [Int32.Parse](xref:System.Int32.Parse(System.String)) для анализа строк, состоящий из цифр различных систем письма.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-186">The following example uses the [Int32.Parse](xref:System.Int32.Parse(System.String)) method to parse strings that consist of digits in different writing systems.</span></span> <span data-ttu-id="c1bbe-187">Как показывает вывод, попытка анализа основных цифр завершается успешно, но попытка анализа полноширинных, арабо-индийских и бенгальских цифр заканчивается неудачей.</span><span class="sxs-lookup"><span data-stu-id="c1bbe-187">As the output from the example shows, the attempt to parse the basic Latin digits succeeds, but the attempt to parse the Fullwidth, Arabic-Indic, and Bangla digits fails.</span></span>

```csharp
using System;

public class Example
{
   public static void Main()
   {
      string value;
      // Define a string of basic Latin digits 1-5.
      value = "\u0031\u0032\u0033\u0034\u0035";
      ParseDigits(value);

      // Define a string of Fullwidth digits 1-5.
      value = "\uFF11\uFF12\uFF13\uFF14\uFF15";
      ParseDigits(value);

      // Define a string of Arabic-Indic digits 1-5.
      value = "\u0661\u0662\u0663\u0664\u0665";
      ParseDigits(value);

      // Define a string of Bangla digits 1-5.
      value = "\u09e7\u09e8\u09e9\u09ea\u09eb";
      ParseDigits(value);
   }

   static void ParseDigits(string value)
   {
      try {
         int number = Int32.Parse(value);
         Console.WriteLine("'{0}' --> {1}", value, number);
      }   
      catch (FormatException) {
         Console.WriteLine("Unable to parse '{0}'.", value);      
      }     
   }
}
// The example displays the following output:
//       '12345' --> 12345
//       Unable to parse '１２３４５'.
//       Unable to parse '١٢٣٤٥'.
//       Unable to parse '১২৩৪৫'.
```

```vb
Module Example
   Public Sub Main()
      Dim value As String
      ' Define a string of basic Latin digits 1-5.
      value = ChrW(&h31) + ChrW(&h32) + ChrW(&h33) + ChrW(&h34) + ChrW(&h35)
      ParseDigits(value)

      ' Define a string of Fullwidth digits 1-5.
      value = ChrW(&hff11) + ChrW(&hff12) + ChrW(&hff13) + ChrW(&hff14) + ChrW(&hff15)
      ParseDigits(value)

      ' Define a string of Arabic-Indic digits 1-5.
      value = ChrW(&h661) + ChrW(&h662) + ChrW(&h663) + ChrW(&h664) + ChrW(&h665)
      ParseDigits(value)

      ' Define a string of Bangla digits 1-5.
      value = ChrW(&h09e7) + ChrW(&h09e8) + ChrW(&h09e9) + ChrW(&h09ea) + ChrW(&h09eb)
      ParseDigits(value)
   End Sub

   Sub ParseDigits(value As String)
      Try
         Dim number As Integer = Int32.Parse(value)
         Console.WriteLine("'{0}' --> {1}", value, number)
      Catch e As FormatException
         Console.WriteLine("Unable to parse '{0}'.", value)      
      End Try     
   End Sub
End Module
' The example displays the following output:
'       '12345' --> 12345
'       Unable to parse '１２３４５'.
'       Unable to parse '١٢٣٤٥'.
'       Unable to parse '১২৩৪৫'.
```

## <a name="see-also"></a><span data-ttu-id="c1bbe-188">См. также</span><span class="sxs-lookup"><span data-stu-id="c1bbe-188">See also</span></span>

[<span data-ttu-id="c1bbe-189">System.Globalization.NumberStyles</span><span class="sxs-lookup"><span data-stu-id="c1bbe-189">System.Globalization.NumberStyles</span></span>](xref:System.Globalization.NumberStyles)

[<span data-ttu-id="c1bbe-190">Анализ строк в .NET</span><span class="sxs-lookup"><span data-stu-id="c1bbe-190">Parsing strings in .NET</span></span>](parsing-strings.md)

[<span data-ttu-id="c1bbe-191">Типы форматирования в .NET</span><span class="sxs-lookup"><span data-stu-id="c1bbe-191">Formatting types in .NET</span></span>](formatting-types.md)


