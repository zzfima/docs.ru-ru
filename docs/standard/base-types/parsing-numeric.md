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
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 85cd57d33b03f7a2105ee3f770b2f8bcc0a57ee4
ms.lasthandoff: 03/02/2017

---

# <a name="parsing-numeric-strings-in-net"></a>Анализ числовых строк в .NET

Все числовые типы имеют два статических метода синтаксического анализа — `Parse` и `TryParse`, которые можно использовать для преобразования строкового представления числа в числовой тип. Эти методы позволяют анализировать строки, которые были созданы с помощью строк формата, описанных в разделах [Строки стандартных числовых форматов](standard-numeric.md) и [Строки настраиваемых числовых форматов](custom-numeric.md). По умолчанию методы `Parse` и `TryParse` могут успешно преобразовывать строки, содержащие целые десятичные числа, только в целочисленные значения. Они могут успешно преобразовывать строки, содержащие целые и дробные десятичные числа, разделители групп и десятичные разделители, в значения с плавающей запятой. Если операцию выполнить не удалось, метод `Parse` создает исключение, а метод `TryParse` возвращает значение `false`.

## <a name="parsing-and-format-providers"></a>Синтаксический анализ и поставщики формата

Как правило, строковые представления числовых значений зависят от языка и региональных параметров. Для различных языков и региональных параметров используются различные элементы численных строк, такие как обозначения денежной единицы, разделители групп (тысяч) и десятичные разделители. Методы анализа неявно или явно используют поставщик формата, распознающий эти различия для разных языков и региональных параметров. Если поставщик формата не задан в вызове метода `Parse` или `TryParse`, используется поставщик формата, связанный с текущим языком и региональными параметрами (объект [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), возвращаемый свойством [NumberFormatInfo.CurrentInfo](xref:System.Globalization.NumberFormatInfo.CurrentInfo)). 

Поставщик формата представлен реализацией интерфейса [IFormatProvider](xref:System.Globalization.NumberFormatInfo.CurrentInfo). Этот интерфейс содержит только один член — метод [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)), единственным параметром которого является объект [Type](xref:System.Type), представляющий тип для форматирования. Этот метод возвращает объект, предоставляющий сведения о форматировании. .NET поддерживает следующие две реализации [IFormatProvider](xref:System.Globalization.NumberFormatInfo.CurrentInfo) для синтаксического анализа числовых строк:

* объект [CultureInfo](xref:System.Globalization.CultureInfo), метод [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) которого возвращает объект [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), предоставляющий характерные для конкретного языка и региональных параметров сведения о форматировании;

* объект [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), метод [NumberFormatInfo.GetFormat](xref:System.Globalization.NumberFormatInfo.GetFormat(System.Type)) которого возвращает сам себя.

В следующем примере предпринимается попытка преобразования каждой строки массива в значение [Double](xref:System.Double). Сначала предпринимается попытка выполнить анализ строки с помощью поставщика формата, отражающего правила для языка и региональных параметров "Английский (США)". Если в ходе операции создается исключение [FormatException](xref:System.FormatException), предпринимается попытка выполнить анализ строки с помощью поставщика формата, отражающего правила для языка и региональных параметров "Французский (Франция)".

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

## <a name="parsing-and-numberstyles-values"></a>Синтаксический анализ и значения NumberStyles

Элементы стиля, такие как пробелы, разделители групп и десятичные разделители, которые могут быть обработаны при синтаксическом анализе, определяются значением перечисления [NumberStyles](xref:System.Globalization.NumberStyles). По умолчанию строки, представляющие целые значения, обрабатываются с использованием значения [NumberStyles.Integer](xref:System.Globalization.NumberStyles.Integer), разрешающего только цифры, начальные и конечные пробелы и знак в начале. Строки, представляющие значения с плавающей запятой, анализируются с использованием сочетания значений [NumberStyles.Float](xref:System.Globalization.NumberStyles.Float) и [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands). Такой смешанный стиль разрешает десятичные числа, начальные и конечные пробелы, знак в начале, десятичный разделитель, разделитель групп и показатель экспоненциального представления. Вызвав перегрузку метода `Parse` или `TryParse`, включающего параметр типа [NumberStyles](xref:System.Globalization.NumberStyles), и установив один или несколько флагов [NumberStyles](xref:System.Globalization.NumberStyles), можно управлять элементами стиля, которые могут присутствовать в строке, для успешного выполнения операции синтаксического анализа. 

Например, строка, содержащая разделитель групп, не может быть преобразована в значение [Int32](xref:System.Int32) с помощью метода [Int32.Parse(String)](xref:System.Int32.Parse(System.String)). Однако преобразование пройдет успешно, если установить флаг [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands), как показано в следующем примере.

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

> **Предупреждение**
>
> Операция синтаксического анализа всегда использует правила форматирования конкретного языка и региональных параметров. Если не задать язык и региональные параметры, передав объект [CultureInfo](xref:System.Globalization.CultureInfo) или [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), используются язык и региональные параметры, связанные с текущим потоком.
 
В следующей таблице перечислены члены перечисления [NumberStyles](xref:System.Globalization.NumberStyles) и описано их влияние на операцию синтаксического анализа.

Значение NumberStyles | Влияние на анализируемую строку
------------------ | --------------------------------- 
[NumberStyles.None](xref:System.Globalization.NumberStyles.None) | Разрешены только цифры.
[NumberStyles.AllowDecimalPoint](xref:System.Globalization.NumberStyles.AllowDecimalPoint) | Разрешены десятичный разделитель и дробные числа. Для целых чисел в качестве дробного числа разрешен только ноль. Допустимые десятичные разделители определяются свойством [NumberFormatInfo.NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator) или [NumberFormatInfo.CurrencyDecimalSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator).
[NumberStyles.AllowExponent](xref:System.Globalization.NumberStyles.AllowExponent) | Для указания экспоненциального представления может использоваться символ "e" или "E".
[NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite) | Разрешены начальные пробелы.
[NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite) | Разрешены конечные пробелы.
[NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign) | Разрешен знак плюс или минус перед числом.
[NumberStyles.AllowTrailingSign](xref:System.Globalization.NumberStyles.AllowTrailingSign) | Разрешен знак плюс или минус, следующий за числом.
[NumberStyles.AllowParentheses](xref:System.Globalization.NumberStyles.AllowParentheses) | Для обозначения отрицательных значений можно использовать скобки.
[NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands) | Разрешен разделитель групп. Символ разделителя групп определяется свойством [NumberFormatInfo.NumberGroupSeparator](xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator) или [NumberFormatInfo.CurrencyGroupSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator).
[NumberStyles.AllowCurrencySymbol](xref:System.Globalization.NumberStyles.AllowCurrencySymbol) | Разрешено обозначение денежной единицы. Обозначение денежной единицы определяется свойством [NumberFormatInfo.CurrencySymbol](xref:System.Globalization.NumberFormatInfo.CurrencySymbol) свойство.
[NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier) | Анализируемая строка интерпретируется как шестнадцатеричное число. Он может включать символы шестнадцатеричного формата 0–9, A–F или a–f. Этот флаг используется только для анализа целых значений.
 
Кроме того, перечисление [NumberStyles](xref:System.Globalization.NumberStyles) предоставляет следующие смешанные стили, включающие несколько флагов [NumberStyles](xref:System.Globalization.NumberStyles). 

Составное значение NumberStyles | Включает члены
---------------------------- | ---------------- 
[NumberStyles.Integer](xref:System.Globalization.NumberStyles.Integer) | Включает стили [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite) и [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign). Это стиль по умолчанию, используемый для анализа целых значений.
[NumberStyles.Number](xref:System.Globalization.NumberStyles.Number) | Включает стили [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign), [NumberStyles.AllowTrailingSign](xref:System.Globalization.NumberStyles.AllowTrailingSign), [NumberStyles.AllowDecimalPoint](xref:System.Globalization.NumberStyles.AllowDecimalPoint) и [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands).
[NumberStyles.Float](xref:System.Globalization.NumberStyles.Float) | Включает стили [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign), [NumberStyles.AllowDecimalPoint](xref:System.Globalization.NumberStyles.AllowDecimalPoint) и [NumberStyles.AllowExponent](xref:System.Globalization.NumberStyles.AllowExponent).
[NumberStyles.Currency](xref:System.Globalization.NumberStyles.Currency) | Включает все стили, кроме [NumberStyles.AllowExponent](xref:System.Globalization.NumberStyles.AllowExponent) и [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier).
[NumberStyles.Any](xref:System.Globalization.NumberStyles.Any) | Включает все стили, кроме [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier).
[NumberStyles.HexNumber](xref:System.Globalization.NumberStyles.HexNumber) | Включает стили [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite) и [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier).
 
## <a name="parsing-and-unicode-digits"></a>Синтаксический анализ и цифры в Юникоде

Стандарт Юникод определяет кодовые точки для цифр в различных системах письма. Например, кодовые точки в диапазоне от U+0030 до U+0039 представляют основные цифры от 0 до 9, кодовые точки в диапазоне от U+09E6 до U+09EF представляют бенгальские цифры от 0 до 9, а кодовые точки в диапазоне от U+FF10 до U+FF19 представляют полноширинные цифры от 0 до 9. Однако методами синтаксического анализа распознаются только основные цифры от 0 до 9 (кодовые точки от U+0030 до U+ 0039). Если методу анализа чисел передается строка, содержащая любые другие цифры, метод создает исключение [FormatException](xref:System.FormatException).

В следующем примере используется метод [Int32.Parse](xref:System.Int32.Parse(System.String)) для анализа строк, состоящий из цифр различных систем письма. Как показывает вывод, попытка анализа основных цифр завершается успешно, но попытка анализа полноширинных, арабо-индийских и бенгальских цифр заканчивается неудачей.

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

## <a name="see-also"></a>См. также

[System.Globalization.NumberStyles](xref:System.Globalization.NumberStyles)

[Анализ строк в .NET](parsing-strings.md)

[Типы форматирования в .NET](formatting-types.md)


