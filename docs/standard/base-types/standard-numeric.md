---
title: "Строки стандартных числовых форматов"
description: "Строки стандартных числовых форматов"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 285faf73-466a-4af0-8eba-7e509958f240
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 5f5ee73c7c9e0ecdce8aa0d75a630decea57704b

---

# <a name="standard-numeric-format-strings"></a>Строки стандартных числовых форматов

Строки стандартных числовых форматов служат для форматирования стандартных числовых типов. Строка стандартных числовых форматов использует формат **A**_xx_, где: 

* **A** — это один буквенный символ, который называют *описателем формата*. Любая строка числового формата, содержащая более одной буквы, включая пробелы, интерпретируется как строка настраиваемого числового формата. Дополнительные сведения см. в разделе [Строки настраиваемых числовых форматов](custom-numeric.md). 

* *xx* — это необязательное целое число, которое называют *описателем точности*. Спецификатор точности находится в диапазоне от 0 до 99 и влияет на число цифр в результате. Описатель точности управляет количеством цифр в строковом представлении числа. Он не округляет само число. Для выполнения операции округления используйте методы [Math.Ceiling](xref:System.Math), [Math.Floor](xref:System.Math) или [Math.Round](xref:System.Math). 

Если *описатель точности* определяет число цифр дробной части в итоговой строке, в итоговых строках содержатся числа, округляемые в большую сторону (то есть с использованием [MidpointRounding.AwayFromZero](xref:System.MidpointRounding.AwayFromZero)). 

> [!NOTE]
> Описатель точности определяет число цифр в результирующей строке. Чтобы заполнить строку результата начальными или конечными пробелами, используйте функцию [составного форматирования](composite-format.md) и определите * компонент выравнивания* в элементе форматирования. 

Строки стандартного числового формата поддерживаются некоторыми перегрузками метода `ToString` всех числовых типов. Например, можно задать строку числового формата для методов [ToString(String)](xref:System.Int32.ToString(System.String)) и [ToString(String, IFormatProvider)](xref:System.Int32.ToString(System.String,System.IFormatProvider)) типа [Int32](xref:System.Int32). Строки стандартного числового формата также поддерживаются функцией [составного форматирования](composite-format.md) .NET, используемой некоторыми методами `Write` и `WriteLine` классов [Console](xref:System.Console) и [StreamWriter](xref:System.IO.StreamWriter), методом [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) и методом [StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)). Композитный формат позволяет включить строковое представление нескольких элементов данных в одну строку, чтобы задать ширину поля и выровнять числа в поле. Дополнительные сведения см. в разделе [Составное форматирование](composite-format.md). 

В следующей таблице описаны спецификаторы стандартных числовых форматов и отображены примеры выходных данных, производимых каждым спецификатором формата. Дополнительные сведения о использовании строк стандартных числовых форматов см. в разделе [Примечания](#notes). Обширную демонстрацию их использования см. в разделе [Пример](#example).

|Описатель формата|Имя|Описание|Примеры|  
|----------------------|----------|-----------------|--------------|  
|"C" или "c"|Валюта|Результат: значение валюты.<br /><br /> Поддерживается: всеми числовыми типами данных.<br /><br /> Описатель точности: количество цифр в дробной части.<br /><br /> Описатель точности по умолчанию: определяется [NumberFormatInfo.CurrencyDecimalDigits](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits).<br /><br /> |123.456 ("C", en-US) -> $123.46<br /><br /> 123.456 ("C", fr-FR) -> 123,46 €<br /><br /> 123.456 ("C", ja-JP) -> ¥123<br /><br /> -123.456 ("C3", en-US) -> ($123.456)<br /><br /> -123.456 ("C3", fr-FR) -> -123,456 €<br /><br /> -123.456 ("C3", ja-JP) -> -¥123.456|  
|"D" или "d"|Десятичное число|Результат: целочисленные цифры с необязательным отрицательным знаком.<br /><br /> Поддерживается: только целочисленными типами данных.<br /><br /> Описатель точности: минимальное число цифр.<br /><br /> Описатель точности по умолчанию: минимальное необходимое число цифр.<br /><br /> |1234 ("D") -> 1234<br /><br /> -1234 ("D6") -> -001234|  
|"E" или "e"|Экспоненциальный (научный)|Результат: экспоненциальная нотация.<br /><br /> Поддерживается: всеми числовыми типами данных.<br /><br /> Описатель точности: количество цифр дробной части.<br /><br /> Описатель точности по умолчанию: 6.<br /><br /> |1052.0329112756 ("E", en-US) -> 1.052033E+003<br /><br /> 1052.0329112756 ("e", fr-FR) -> 1,052033e+003<br /><br /> -1052.0329112756 ("e2", en-US) -> -1.05e+003<br /><br /> -1052.0329112756 ("E2", fr_FR) -> -1,05E+003|  
|"F" или "f"|С фиксированной запятой|Результат: цифры целой и дробной частей с необязательным отрицательным знаком.<br /><br /> Поддерживается: всеми числовыми типами данных.<br /><br /> Описатель точности: количество цифр в дробной части.<br /><br /> Описатель точности по умолчанию: определяется [NumberFormatInfo.NumberDecimalDigits](xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits).<br /><br /> |1234.567 ("F", en-US) -> 1234.57<br /><br /> 1234.567 ("F", de-DE) -> 1234,57<br /><br /> 1234 ("F1", en-US) -> 1234.0<br /><br /> 1234 ("F1", de-DE) -> 1234,0<br /><br /> -1234.56 ("F4", en-US) -> -1234.5600<br /><br /> -1234.56 ("F4", de-DE) -> -1234,5600|  
|"G" или "g"|Общие|Результат: наиболее компактная запись из двух вариантов — экспоненциального и с фиксированной запятой.<br /><br /> Поддерживается: для всех числовых типов данных.<br /><br /> Описатель точности: количество значащих цифр.<br /><br /> Описатель точности по умолчанию: определяется численным типом.<br /><br /> |-123.456 ("G", en-US) -> -123.456<br /><br /> -123.456 ("G", sv-SE) -> -123,456<br /><br /> 123.4546 ("G4", en-US) -> 123.5<br /><br /> 123.4546 ("G4", sv-SE) -> 123,5<br /><br /> -1.234567890e-25 ("G", en-US) -> -1.23456789E-25<br /><br /> -1.234567890e-25 ("G", sv-SE) -> -1,23456789E-25|  
|"N" или "n"|Числовой|Результат: цифры целой и дробной частей, разделители групп и разделитель целой и дробной частей с необязательным отрицательным знаком.<br /><br /> Поддерживается: всеми числовыми типами данных.<br /><br /> Описатель точности: желаемое число знаков дробной части.<br /><br /> Описатель точности по умолчанию: определяется [NumberFormatInfo.NumberDecimalDigits](xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits).<br /><br /> |1234.567 ("N", en-US) -> 1,234.57<br /><br /> 1234.567 ("N", ru-RU) -> 1 234,57<br /><br /> 1234 ("N1", en-US) -> 1,234.0<br /><br /> 1234 ("N1", ru-RU) -> 1 234,0<br /><br /> -1234.56 ("N3", en-US) -> -1,234.560<br /><br /> -1234.56 ("N3", ru-RU) -> -1 234,560|  
|"P" или "p"|Процент|Результат: число, умноженное на 100 и отображаемое с символом процента.<br /><br /> Поддерживается: всеми числовыми типами данных.<br /><br /> Описатель точности: желаемое число знаков дробной части.<br /><br /> Описатель точности по умолчанию: определяется [NumberFormatInfo.PercentDecimalDigits](assetId:///P:System.Globalization.NumberFormatInfo.PercentDecimalDigits?qualifyHint=True&autoUpgrade=True).<br /><br /> |1 ("P", en-US) -> 100.00 %<br /><br /> 1 ("P", fr-FR) -> 100,00 %<br /><br /> -0.39678 ("P1", en-US) -> -39.7 %<br /><br /> -0.39678 ("P1", fr-FR) -> -39,7 %|  
|"R" или "r"|Приемо-передача|Результат: строка, дающая при обратном преобразовании идентичное число.<br /><br /> Поддерживается: типами данных [Single](xref:System.Single), [Double](xref:System.Double) и [BigInteger](xref:System.Numerics.BigInteger).<br /><br /> Описатель точности: игнорируется.<br /><br /> |123456789.12345678 ("R") -> 123456789.12345678<br /><br /> -1234567890.12345678 ("R") -> -1234567890.1234567|  
|"X" или "x"|Шестнадцатеричный|Результат: шестнадцатеричная строка.<br /><br /> Поддерживается: только целочисленными типами данных.<br /><br /> Описатель точности: число цифр в результирующей строке.<br /><br /> |255 ("X") -> FF<br /><br /> -1 ("x") -> ff<br /><br /> 255 ("x4") -> 00ff<br /><br /> -1 ("X4") -> 00FF|  
|Любой другой символ|Неизвестный описатель|Результат: создание исключения [FormatException](xref:System.FormatException) во время выполнения.|| 

## <a name="using-standard-numeric-format-strings"></a>Использование строк стандартных числовых форматов

Строку стандартного числового формата можно использовать для определения форматирования числового значения одним из двух следующих способов:

* Ее можно передать перегруженному методу `ToString`, у которого есть параметр *format*. В следующем примере осуществляется форматирование числового значения в качестве строки со значением валюты с использованием текущего языка и региональных параметров (в примере это "en-US"). 

  ```csharp
  decimal value = 123.456m;
  Console.WriteLine(value.ToString("C2"));
  // Displays $123.46
  ```

  ```vb
  Dim value As Decimal = 123.456d
  Console.WriteLine(value.ToString("C2"))         
  ' Displays $123.46
  ```
  
* Эту строку можно передать в качестве аргумента *formatString* в элемент форматирования, используемый с такими методами, как [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)), [Console.WriteLine](xref:System.Console.WriteLine) и [StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)). Дополнительные сведения см. в разделе [Составное форматирование](composite-format.md). В следующем примере элемент форматирования используется для вставки значения валюты в строку.

  ```csharp
  decimal value = 123.456m;
  Console.WriteLine("Your account balance is {0:C2}.", value);
  // Displays "Your account balance is $123.46."
  ```

  ```vb
  Dim value As Decimal = 123.456d
  Console.WriteLine("Your account balance is {0:C2}.", value)
  ' Displays "Your account balance is $123.46."
  ```
  
  При необходимости можно предоставить аргумент alignment, чтобы указать ширину числового поля и его выравнивание по правому или левому краю. В следующем примере денежное значение в поле длиной 28 символов выравнивается по левому краю, а денежное значение в поле длиной 14 символов выравнивается по правому краю.
  
  ```csharp
  decimal[] amounts = { 16305.32m, 18794.16m };
  Console.WriteLine("   Beginning Balance           Ending Balance");
  Console.WriteLine("   {0,-28:C2}{1,14:C2}", amounts[0], amounts[1]);
  // Displays:
  //        Beginning Balance           Ending Balance
  //        $16,305.32                      $18,794.16
  ```

  ```vb
  Dim amounts() As Decimal = { 16305.32d, 18794.16d }
  Console.WriteLine("   Beginning Balance           Ending Balance")
  Console.WriteLine("   {0,-28:C2}{1,14:C2}", amounts(0), amounts(1))
  ' Displays:
  '        Beginning Balance           Ending Balance
  '        $16,305.32                      $18,794.16
  ```
  
В приведенных ниже разделах содержится подробная информация о всех строках стандартных числовых форматов.

## <a name="the-currency-c-format-specifier"></a>Описатель формата валюты ("C")

При использовании описателя формата валюты ("C") число преобразуется в строку, представляющую сумму в некоторой валюте. Желаемое количество знаков дробной части в результирующей строке задается описателем точности. Если описатель точности не задан, точность по умолчанию определяется свойством [NumberFormatInfo.CurrencyDecimalDigits](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits).

Если форматируемое значение содержит больше десятичных знаков, чем задано или возможно по умолчанию, в результирующей строке дробное значение округляется. Если значение справа от заданного числа десятичных знаков больше или равно 5, последний знак в результирующей строке округляется в сторону от нуля.

Форматирование результирующей строки определяется сведениями о форматировании в текущем объекте [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo). В следующей таблице представлены свойства объекта [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), обеспечивающие управление форматированием возвращаемой строки.

Свойство NumberFormatInfo | Описание
------------------------- | -----------
[CurrencyPositivePattern](xref:System.Globalization.NumberFormatInfo.CurrencyPositivePattern) | Определяет положение символа валюты в положительных значениях.
[CurrencyNegativePattern](xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern) | Определяет положение символа валюты в отрицательных значениях и указывает, как именно представляется отрицательный знак: круглыми скобками или свойством [NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign).
[NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) | Задает отрицательный знак, используемый в случае, если свойство [CurrencyNegativePattern](xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern) указывает на то, что скобки для отрицания не используются. 
[CurrencySymbol](xref:System.Globalization.NumberFormatInfo.CurrencySymbol) | Определяет символ валюты.
[CurrencyDecimalDigits](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits) | Определяет количество цифр дробной части в значении валюты по умолчанию. Это значение можно переопределить с помощью описателя точности.
[CurrencyDecimalSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator) | Определяет строку, разделяющую целую и дробную части числа.
[CurrencyGroupSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator) | Определяет строку, разделяющую группы цифр целой части. 
[CurrencyGroupSizes](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSizes) | Определяет число целочисленных цифр, входящих в группу.

В следующем примере значение [Double](xref:System.Double) форматируется с помощью описателя денежного формата. 

```csharp
double value = 12345.6789;
Console.WriteLine(value.ToString("C", CultureInfo.CurrentCulture));

Console.WriteLine(value.ToString("C3", CultureInfo.CurrentCulture));

Console.WriteLine(value.ToString("C3", 
                  CultureInfo.CreateSpecificCulture("da-DK")));
// The example displays the following output on a system whose
// current culture is English (United States):
//       $12,345.68
//       $12,345.679
//       kr 12.345,679
```

```vb
Dim value As Double = 12345.6789
Console.WriteLine(value.ToString("C", CultureInfo.CurrentCulture))

Console.WriteLine(value.ToString("C3", CultureInfo.CurrentCulture))

Console.WriteLine(value.ToString("C3", _
                  CultureInfo.CreateSpecificCulture("da-DK")))
' The example displays the following output on a system whose
' current culture is English (United States):
'       $12,345.68
'       $12,345.679
'       kr 12.345,679
```

## <a name="the-decimal-d-format-specifier"></a>Описатель десятичного формата ("D")

При использовании описателя десятичного формата ("D") число преобразуется в строку, состоящую из десятичных цифр (0–9); если число отрицательное, перед ним ставится отрицательный знак. Этот формат доступен только для целых типов.

Минимальное количество знаков в выходной строке задается спецификатором точности. Недостающие знаки в строке заменяются нулями. Если описатель точности не задан, по умолчанию используется минимальное значение, позволяющее представить целое число без нулей в начале.

Форматирование результирующей строки определяется сведениями о форматировании в текущем объекте [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo). Как показано в следующей таблице, управление форматированием результирующей строки осуществляется с помощью одного свойства. 

Свойство NumberFormatInfo | Описание
------------------------- | -----------
[NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) | Определяет строку, указывающую, что число является отрицательным. 

В следующем примере значение [Int32](xref:System.Int32) форматируется с помощью описателя десятичного формата.

```csharp
int value; 

value = 12345;
Console.WriteLine(value.ToString("D"));
// Displays 12345
Console.WriteLine(value.ToString("D8"));
// Displays 00012345

value = -12345;
Console.WriteLine(value.ToString("D"));
// Displays -12345
Console.WriteLine(value.ToString("D8"));
// Displays -00012345
```

```vb
Dim value As Integer 

value = 12345
Console.WriteLine(value.ToString("D"))
' Displays 12345   
Console.WriteLine(value.ToString("D8"))
' Displays 00012345

value = -12345
Console.WriteLine(value.ToString("D"))
' Displays -12345
Console.WriteLine(value.ToString("D8"))
' Displays -00012345
```

## <a name="the-exponential-e-format-specifier"></a>Описатель экспоненциального формата ("E")

При использовании описателя экспоненциального формата ("E") число преобразуется в строку вида "-d.ddd…E+ddd" или "-d.ddd…e+ddd", где каждый символ "d" обозначает цифру (0–9). Если число отрицательное, в начале строки ставится отрицательный знак. Перед разделителем целой и дробной части всегда стоит ровно одна цифра. 

Требуемое число знаков дробной части задается спецификатором точности. Если спецификатор точности отсутствует, по умолчанию число знаков дробной части равно шести. 

Регистр описателя формата задает регистр буквы, стоящей перед экспонентой ("E" или "e"). Экспонента состоит из знака "плюс" или "минус" и трех цифр. Недостающие до минимума цифры заменяются нулями, если это необходимо.

Форматирование результирующей строки определяется сведениями о форматировании в текущем объекте [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo). В следующей таблице представлены свойства объекта [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), обеспечивающие управление форматированием возвращаемой строки.

Свойство NumberFormatInfo | Описание
------------------------- | -----------
[NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) | Определяет строку, указывающую на то, что число является отрицательным (как мантисса, так и экспонента). 
[NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator) | Определяет строку, разделяющую целую и дробную части мантиссы.
[PositiveSign](xref:System.Globalization.NumberFormatInfo.PositiveSign) | Определяет строку, указывающую, что экспонента является положительной.

В следующем примере значение [Double](xref:System.Double) форматируется с помощью описателя экспоненциального формата. 

```csharp
double value = 12345.6789;
Console.WriteLine(value.ToString("E", CultureInfo.InvariantCulture));
// Displays 1.234568E+004

Console.WriteLine(value.ToString("E10", CultureInfo.InvariantCulture));
// Displays 1.2345678900E+004

Console.WriteLine(value.ToString("e4", CultureInfo.InvariantCulture));
// Displays 1.2346e+004

Console.WriteLine(value.ToString("E", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));
// Displays 1,234568E+004
```

```vb
Dim value As Double = 12345.6789
Console.WriteLine(value.ToString("E", CultureInfo.InvariantCulture))
' Displays 1.234568E+004

Console.WriteLine(value.ToString("E10", CultureInfo.InvariantCulture))
' Displays 1.2345678900E+004

Console.WriteLine(value.ToString("e4", CultureInfo.InvariantCulture))
' Displays 1.2346e+004

Console.WriteLine(value.ToString("E", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))
' Displays 1,234568E+004
```

## <a name="the-fixedpoint-f-format-specifier"></a>Описатель формата с фиксированной запятой ("F")

При использовании спецификатора формата с фиксированной точкой ("F") число преобразуется в строку вида "-ddd.ddd…", где каждое "d" обозначает цифру (0–9). Если число отрицательное, в начале строки ставится отрицательный знак. 

Требуемое число знаков дробной части задается спецификатором точности. Если описатель точности отсутствует, то используется численная точность, определяемая текущим значением свойства [NumberFormatInfo.NumberDecimalDigits](xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits).

Форматирование результирующей строки определяется сведениями о форматировании в текущем объекте [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo). В следующей таблице представлены свойства объекта [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), обеспечивающие управление форматированием результирующей строки.

Свойство NumberFormatInfo | Описание
------------------------- | -----------
[NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) | Определяет строку, указывающую, что число является отрицательным.
[NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator) | Определяет строку, разделяющую целую и дробную части числа.
[NumberFormatInfo.NumberDecimalDigits](xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits) | Определяет количество цифр дробной части по умолчанию. Это значение можно переопределить с помощью описателя точности.

В следующем примере значение [Double](xref:System.Double) и значение [Int32](xref:System.Int32) форматируются с помощью описателя формата с фиксированной точкой.

```csharp
int integerNumber;
integerNumber = 17843;
Console.WriteLine(integerNumber.ToString("F", 
                  CultureInfo.InvariantCulture));
// Displays 17843.00

integerNumber = -29541;
Console.WriteLine(integerNumber.ToString("F3", 
                  CultureInfo.InvariantCulture));
// Displays -29541.000

double doubleNumber;
doubleNumber = 18934.1879;
Console.WriteLine(doubleNumber.ToString("F", CultureInfo.InvariantCulture));
// Displays 18934.19

Console.WriteLine(doubleNumber.ToString("F0", CultureInfo.InvariantCulture));
// Displays 18934

doubleNumber = -1898300.1987;
Console.WriteLine(doubleNumber.ToString("F1", CultureInfo.InvariantCulture));  
// Displays -1898300.2

Console.WriteLine(doubleNumber.ToString("F3", 
                  CultureInfo.CreateSpecificCulture("es-ES")));
// Displays -1898300,199 
```

```vb
Dim integerNumber As Integer
integerNumber = 17843
Console.WriteLine(integerNumber.ToString("F", CultureInfo.InvariantCulture))
' Displays 17843.00

integerNumber = -29541
Console.WriteLine(integerNumber.ToString("F3", CultureInfo.InvariantCulture))
' Displays -29541.000

Dim doubleNumber As Double
doubleNumber = 18934.1879
Console.WriteLine(doubleNumber.ToString("F", CultureInfo.InvariantCulture))
' Displays 18934.19

Console.WriteLine(doubleNumber.ToString("F0", CultureInfo.InvariantCulture))
' Displays 18934

doubleNumber = -1898300.1987
Console.WriteLine(doubleNumber.ToString("F1", CultureInfo.InvariantCulture))  
' Displays -1898300.2

Console.WriteLine(doubleNumber.ToString("F3", _ 
                  CultureInfo.CreateSpecificCulture("es-ES")))
' Displays -1898300,199                        
```

## <a name="the-general-g-format-specifier"></a>Описатель общего формата ("G")

При использовании описателя общего формата ("G") число преобразуется в более короткий из двух вариантов: запись с фиксированной запятой или экспоненциальная запись. При этом учитывается тип числа и наличие описателя точности. Описатель точности определяет максимальное количество значащих цифр, которые могут быть использованы в результирующей строке. Если описатель точности не задан или равен нулю, точность определяется типом числа, как показано в следующей таблице. 

Числовой тип | Точность по умолчанию
------------ | -----------------
[Byte](xref:System.Byte) или [SByte](xref:System.SByte) | 3 знака
[Int16](xref:System.Int16) или [UInt16](xref:System.UInt16) | 5 знака
[Int32](xref:System.Int32) или [UInt32](xref:System.UInt32) | 10 знака
[Int64](xref:System.Int64) | 19 знака
[UInt64](xref:System.UInt64) | 20 знака
[BigInteger](xref:System.Numerics.BigInteger) | Без ограничений (то же, что и "R")
[Single](xref:System.Single) | 7 знака
[Double](xref:System.Double) | 15 знака
[Decimal](xref:System.Decimal) | 29 знака

Нотация с фиксированной запятой используется, если экспонента результата в экспоненциальной нотации длиннее пяти знаков, но меньше спецификатора точности, в противном случае используется научная нотация. При необходимости результат содержит разделитель целой и дробной частей; нули в конце дробной части после разделителя отбрасываются. Если описатель точности задан и число значащих цифр результата превосходит указанное значение точности, лишние цифры отбрасываются округлением. 

Тем не менее, если число относится к типу [Decimal](xref:System.Decimal) и описатель точности не задан, всегда используется нотация с фиксированной запятой, а нули в конце не отбрасываются.

Если используется экспоненциальная нотация, регистр буквы, стоящей перед экспонентой, определяется регистром описателя формата (буква "E" соответствует "G", "e" соответствует "g"). Экспонента содержит не менее двух цифр. Это отличает данный формат от экспоненциальной записи, создаваемой при использовании описателя экспоненциального формата, поскольку в последнем случае экспонента содержит не менее трех цифр.

Форматирование результирующей строки определяется сведениями о форматировании в текущем объекте [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo). В следующей таблице представлены свойства объекта [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), обеспечивающие управление форматированием результирующей строки.

Свойство NumberFormatInfo | Описание
------------------------- | -----------
[NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) | Определяет строку, указывающую, что число является отрицательным.
[NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator) | Определяет строку, разделяющую целую и дробную части числа.
[PositiveSign](xref:System.Globalization.NumberFormatInfo.PositiveSign) | Определяет строку, указывающую, что экспонента является положительной. 

В следующем примере различные значения с плавающей запятой форматируются с помощью спецификатора общего формата.

```csharp
double number;

number = 12345.6789;      
Console.WriteLine(number.ToString("G", CultureInfo.InvariantCulture));
// Displays  12345.6789
Console.WriteLine(number.ToString("G", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));
// Displays 12345,6789

Console.WriteLine(number.ToString("G7", CultureInfo.InvariantCulture));
// Displays 12345.68 

number = .0000023;
Console.WriteLine(number.ToString("G", CultureInfo.InvariantCulture));
// Displays 2.3E-06       
Console.WriteLine(number.ToString("G", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));
// Displays 2,3E-06

number = .0023;
Console.WriteLine(number.ToString("G", CultureInfo.InvariantCulture));
// Displays 0.0023

number = 1234;
Console.WriteLine(number.ToString("G2", CultureInfo.InvariantCulture));
// Displays 1.2E+03

number = Math.PI;
Console.WriteLine(number.ToString("G5", CultureInfo.InvariantCulture));
// Displays 3.1416    
```

```vb
Dim number As Double

number = 12345.6789      
Console.WriteLine(number.ToString("G", CultureInfo.InvariantCulture))
' Displays  12345.6789
Console.WriteLine(number.ToString("G", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))
' Displays 12345,6789

Console.WriteLine(number.ToString("G7", CultureInfo.InvariantCulture))
' Displays 12345.68 

number = .0000023
Console.WriteLine(number.ToString("G", CultureInfo.InvariantCulture))
' Displays 2.3E-06       
Console.WriteLine(number.ToString("G", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))
' Displays 2,3E-06

number = .0023
Console.WriteLine(number.ToString("G", CultureInfo.InvariantCulture))
' Displays 0.0023

number = 1234
Console.WriteLine(number.ToString("G2", CultureInfo.InvariantCulture))
' Displays 1.2E+03

number = Math.Pi
Console.WriteLine(number.ToString("G5", CultureInfo.InvariantCulture))
' Displays 3.1416
```

## <a name="the-numeric-n-format-specifier"></a>Описатель числового формата ("N")

Спецификатор числового формата ("N") преобразует число в стоку вида "-d,ddd,ddd.ddd… ", где знак "-" при необходимости представляет знак отрицательного числа, знак "d" означает цифру (0-9), знак "," — разделитель групп, а знак "." —- разделитель целой и дробной части. Требуемое число знаков дробной части задается спецификатором точности. Если описатель точности не задан, число десятичных знаков определяется текущим свойством [NumberFormatInfo.NumberDecimalDigits](xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits).

Форматирование результирующей строки определяется сведениями о форматировании в текущем объекте [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo). В следующей таблице представлены свойства объекта [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), обеспечивающие управление форматированием результирующей строки.

Свойство NumberFormatInfo | Описание
------------------------- | -----------
[NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) | Определяет строку, указывающую, что число является отрицательным.
[NumberNegativePattern](xref:System.Globalization.NumberFormatInfo.NumberNegativePattern) | Определяет формат отрицательных значений и указывает, как именно представляется отрицательный знак: круглыми скобками или свойством [NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign).
[NumberGroupSizes](xref:System.Globalization.NumberFormatInfo.NumberGroupSizes) | Определяет число цифр целой части, стоящих между разделителями групп.
[NumberGroupSeparator](xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator) | Определяет строку, разделяющую группы цифр целой части.
[NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator) | Определяет строку, разделяющую целую и дробную части числа.
[NumberDecimalDigits](xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits) | Определяет количество цифр дробной части по умолчанию. Это значение можно переопределить с помощью описателя точности.

В следующем примере различные значения с плавающей запятой форматируются с помощью спецификатора числового формата.

```csharp
double dblValue = -12445.6789;
Console.WriteLine(dblValue.ToString("N", CultureInfo.InvariantCulture));
// Displays -12,445.68
Console.WriteLine(dblValue.ToString("N1", 
                  CultureInfo.CreateSpecificCulture("sv-SE")));
// Displays -12 445,7

int intValue = 123456789;
Console.WriteLine(intValue.ToString("N1", CultureInfo.InvariantCulture));
// Displays 123,456,789.0 
```

```vb
Dim dblValue As Double = -12445.6789
Console.WriteLine(dblValue.ToString("N", CultureInfo.InvariantCulture))
' Displays -12,445.68
Console.WriteLine(dblValue.ToString("N1", _
                  CultureInfo.CreateSpecificCulture("sv-SE")))
' Displays -12 445,7

Dim intValue As Integer = 123456789
Console.WriteLine(intValue.ToString("N1", CultureInfo.InvariantCulture))
' Displays 123,456,789.0 
```

## <a name="the-percent-p-format-specifier"></a>Описатель формата процента ("P")

При использовании описателя формата процента ("P") число умножается на 100 и преобразуется в строку, представляющую процентную долю. Требуемое число знаков дробной части задается спецификатором точности. Если описатель точности отсутствует, то используется значение точности числа по умолчанию, заданное свойством [PercentDecimalDigits](xref:System.Globalization.NumberFormatInfo.PercentDecimalDigits).

В следующей таблице представлены свойства объекта [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), обеспечивающие управление форматированием возвращаемой строки.

umberFormatInfo property | Описание
------------------------- | -----------
[PercentPositivePattern](xref:System.Globalization.NumberFormatInfo.PercentPositivePattern) | Определяет положение символа процента в положительных значениях.
[PercentNegativePattern](xref:System.Globalization.NumberFormatInfo.PercentNegativePattern) | 
[NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) | Определяет строку, указывающую, что число является отрицательным.
[PercentSymbol](xref:System.Globalization.NumberFormatInfo.PercentSymbol) | Определяет символ процента.
[PercentDecimalDigits](xref:System.Globalization.NumberFormatInfo.PercentDecimalDigits) | Определяет количество цифр дробной части в значении процента по умолчанию. Это значение можно переопределить с помощью описателя точности.
[PercentDecimalSeparator](xref:System.Globalization.NumberFormatInfo.PercentDecimalSeparator) | Определяет строку, разделяющую целую и дробную части числа.
[PercentGroupSeparator](xref:System.Globalization.NumberFormatInfo.PercentGroupSeparator) | Определяет строку, разделяющую группы цифр целой части. 
[PercentGroupSizes](xref:System.Globalization.NumberFormatInfo.PercentGroupSizes) | Определяет число целочисленных цифр, входящих в группу.

В следующем примере значения с плавающей запятой форматируются с помощью спецификатора процентного формата.

```csharp
double number = .2468013;
Console.WriteLine(number.ToString("P", CultureInfo.InvariantCulture));
// Displays 24.68 %
Console.WriteLine(number.ToString("P", 
                  CultureInfo.CreateSpecificCulture("hr-HR")));
// Displays 24,68%     
Console.WriteLine(number.ToString("P1", CultureInfo.InvariantCulture));
// Displays 24.7 %
```

```vb
Dim number As Double = .2468013
Console.WriteLine(number.ToString("P", CultureInfo.InvariantCulture))
' Displays 24.68 %
Console.WriteLine(number.ToString("P", _
                  CultureInfo.CreateSpecificCulture("hr-HR")))
' Displays 24,68%     
Console.WriteLine(number.ToString("P1", CultureInfo.InvariantCulture))
' Displays 24.7 %
```

## <a name="the-roundtrip-r-format-specifier"></a>Описатель формата обратного преобразования ("R")

Описатель формата обратного преобразования ("R") гарантирует, что строка, полученная преобразованием из числового значения, при обратном преобразовании даст то же самое числовое значение. Этот формат поддерживается только для типов [Single](xref:System.Single), [Double](xref:System.Double) и [BigInteger](xref:System.Numerics.BigInteger). 

Если с помощью этого описателя форматируется значение типа [BigInteger](xref:System.Numerics.BigInteger), то его строковое представление будет содержать все значащие цифры [BigInteger](xref:System.Numerics.BigInteger). Если с помощью этого описателя форматируется значение типа [Single](xref:System.Single) или [Double](xref:System.Double), то сначала для него проверяется общий формат, при этом для [Double](xref:System.Double) используется 15-знаковая точность, а для [Single](xref:System.Single) — 7-знаковая точность. Если строка может быть разобрана так, чтобы переменная приняла то же значение, форматирование производится с помощью общего указателя формата. Если при обратном преобразовании значение все же меняется, то количество значащих цифр увеличивается до 17 для типа [Double](xref:System.Double) и 9 — для типа [Single](xref:System.Single). 

Хотя описатель точности можно указать, он будет проигнорирован. Приведенные указатели приема-передачи в данном случае имеют преимущество перед указателем точности. 

Форматирование результирующей строки определяется сведениями о форматировании в текущем объекте [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo). В следующей таблице представлены свойства объекта [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), обеспечивающие управление форматированием результирующей строки.

Свойство NumberFormatInfo | Описание
------------------------- | -----------
[NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) | Определяет строку, указывающую, что число является отрицательным.
[NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator) | Определяет строку, разделяющую целую и дробную части числа.
[PositiveSign](xref:System.Globalization.NumberFormatInfo.PositiveSign) | Определяет строку, указывающую, что экспонента является положительной.

 В следующем примере значения [Double](xref:System.Double) форматируются с помощью описателя формата приема-передачи.

```csharp
double value;

value = Math.PI;
Console.WriteLine(value.ToString("r"));
// Displays 3.1415926535897931
Console.WriteLine(value.ToString("r", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));
// Displays 3,1415926535897931
value = 1.623e-21;
Console.WriteLine(value.ToString("r"));
// Displays 1.623E-21
```

```vb
Dim value As Double

value = Math.Pi
Console.WriteLine(value.ToString("r"))
' Displays 3.1415926535897931
Console.WriteLine(value.ToString("r", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))
' Displays 3,1415926535897931
value = 1.623e-21
Console.WriteLine(value.ToString("r"))
' Displays 1.623E-21
```

## <a name="the-hexadecimal-x-format-specifier"></a>Описатель шестнадцатеричного формата ("X")

При использовании описателя шестнадцатеричного формата ("X") число преобразуется в строку шестнадцатеричных цифр. Регистр шестнадцатеричных цифр больше 9 совпадает с регистром описателя формата. Например, чтобы получить запись "ABCDEF", задайте описатель X" или, наоборот, задайте описатель "x", чтобы получить "abcdef". Этот формат доступен только для целых типов.

Минимальное количество знаков в выходной строке задается спецификатором точности. Недостающие знаки в строке заменяются нулями.

Форматирование результирующей строки не определяется сведениями о форматировании в текущем объекте [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo). 

В следующем примере значения [Int32](xref:System.Int32) форматируются с помощью описателя шестнадцатеричного формата.

```csharp
int value; 

value = 0x2045e;
Console.WriteLine(value.ToString("x"));
// Displays 2045e
Console.WriteLine(value.ToString("X"));
// Displays 2045E
Console.WriteLine(value.ToString("X8"));
// Displays 0002045E

value = 123456789;
Console.WriteLine(value.ToString("X"));
// Displays 75BCD15
Console.WriteLine(value.ToString("X2"));
// Displays 75BCD15
```

```vb
Dim value As Integer 

value = &h2045e
Console.WriteLine(value.ToString("x"))
' Displays 2045e
Console.WriteLine(value.ToString("X"))
' Displays 2045E
Console.WriteLine(value.ToString("X8"))
' Displays 0002045E

value = 123456789
Console.WriteLine(value.ToString("X"))
' Displays 75BCD15
Console.WriteLine(value.ToString("X2"))
' Displays 75BCD15
```

## <a name="notes"></a>Примечания

### <a name="numberformatinfo-properties"></a>Свойства NumberFormatInfo

На форматирование влияют свойства текущего объекта [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), которые задаются либо неявно, языком и региональными параметрами текущего потока, либо явно, параметром [IFormatProvider](xref:System.IFormatProvider) метода, который вызывает форматирование. Укажите объект [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) или объект [CultureInfo](xref:System.Globalization.CultureInfo) для этого параметра. 

### <a name="integral-and-floatingpoint-numeric-types"></a>Целочисленные типы и типы с плавающей запятой

Некоторые описания спецификаторов стандартных числовых форматов относятся к целочисленным типам и типам с плавающей запятой. Целочисленные типы — это [Byte](xref:System.Byte), [SByte](xref:System.SByte), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), [UInt64](xref:System.UInt64) и [BigInteger](xref:System.Numerics.BigInteger). Числовыми типами с плавающей запятой являются [Decimal](xref:System.Decimal), [Single](xref:System.Single) и [Double](xref:System.Double). 

### <a name="floatingpoint-infinities-and-nan"></a>Бесконечности действительных чисел с плавающей запятой и NaN

Если, вне зависимости от строки формата, значение типа с плавающей запятой [Single](xref:System.Single) или [Double](xref:System.Double) является положительной бесконечностью, отрицательной бесконечностью или не является числом (NaN), отформатированная строка будет содержать значение соответствующего свойства ([PositiveInfinitySymbol](xref:System.Globalization.NumberFormatInfo.PositiveInfinitySymbol), [NegativeInfinitySymbol](xref:System.Globalization.NumberFormatInfo.NegativeInfinitySymbol) или [NaNSymbol](xref:System.Globalization.NumberFormatInfo.NaNSymbol)) применимого в настоящий момент объекта [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo).

## <a name="example"></a>Пример

В следующем примере с помощью языка и региональных параметров "en-US" и всех описателей стандартных числовых форматов форматируется целочисленное значение и числовое значение с плавающей запятой. В этом примере используются два числовых типа ([Double](xref:System.Double) и [Int32](xref:System.Int32)), но аналогичные результаты были бы получены для любых других числовых типов ([Byte](xref:System.Byte), [SByte](xref:System.SByte), [Int16](xref:System.Int16), [Int64](xref:System.Int64), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), [UInt64](xref:System.UInt64), [BigInteger](xref:System.Numerics.BigInteger), [Decimal](xref:System.Decimal) и [Single](xref:System.Single)). 

```csharp
using System;
using System.Globalization;
using System.Threading;

public class NumericFormats
{
   public static void Main()
   {
      // Display string representations of numbers for en-us culture
      CultureInfo ci = new CultureInfo("en-us");

      // Output floating point values
      double floating = 10761.937554;
      Console.WriteLine("C: {0}", 
              floating.ToString("C", ci));           // Displays "C: $10,761.94"
      Console.WriteLine("E: {0}", 
              floating.ToString("E03", ci));         // Displays "E: 1.076E+004"
      Console.WriteLine("F: {0}", 
              floating.ToString("F04", ci));         // Displays "F: 10761.9376"         
      Console.WriteLine("G: {0}",  
              floating.ToString("G", ci));           // Displays "G: 10761.937554"
      Console.WriteLine("N: {0}", 
              floating.ToString("N03", ci));         // Displays "N: 10,761.938"
      Console.WriteLine("P: {0}", 
              (floating/10000).ToString("P02", ci)); // Displays "P: 107.62 %"
      Console.WriteLine("R: {0}", 
              floating.ToString("R", ci));           // Displays "R: 10761.937554"            
      Console.WriteLine();

      // Output integral values
      int integral = 8395;
      Console.WriteLine("C: {0}", 
              integral.ToString("C", ci));           // Displays "C: $8,395.00"
      Console.WriteLine("D: {0}", 
              integral.ToString("D6", ci));          // Displays "D: 008395" 
      Console.WriteLine("E: {0}", 
              integral.ToString("E03", ci));         // Displays "E: 8.395E+003"
      Console.WriteLine("F: {0}", 
              integral.ToString("F01", ci));         // Displays "F: 8395.0"    
      Console.WriteLine("G: {0}",  
              integral.ToString("G", ci));           // Displays "G: 8395"
      Console.WriteLine("N: {0}", 
              integral.ToString("N01", ci));         // Displays "N: 8,395.0"
      Console.WriteLine("P: {0}", 
              (integral/10000.0).ToString("P02", ci)); // Displays "P: 83.95 %"
      Console.WriteLine("X: 0x{0}", 
              integral.ToString("X", ci));           // Displays "X: 0x20CB"
      Console.WriteLine();
   }
}
```

```vb
Option Strict On

Imports System.Globalization
Imports System.Threading

Module NumericFormats
   Public Sub Main()
      ' Display string representations of numbers for en-us culture
      Dim ci As New CultureInfo("en-us")

      ' Output floating point values
      Dim floating As Double = 10761.937554
      Console.WriteLine("C: {0}", _
              floating.ToString("C", ci))           ' Displays "C: $10,761.94"
      Console.WriteLine("E: {0}", _
              floating.ToString("E03", ci))         ' Displays "E: 1.076E+004"
      Console.WriteLine("F: {0}", _
              floating.ToString("F04", ci))         ' Displays "F: 10761.9376"         
      Console.WriteLine("G: {0}", _ 
              floating.ToString("G", ci))           ' Displays "G: 10761.937554"
      Console.WriteLine("N: {0}", _
              floating.ToString("N03", ci))         ' Displays "N: 10,761.938"
      Console.WriteLine("P: {0}", _
              (floating/10000).ToString("P02", ci)) ' Displays "P: 107.62 %"
      Console.WriteLine("R: {0}", _
              floating.ToString("R", ci))           ' Displays "R: 10761.937554"            
      Console.WriteLine()

      ' Output integral values
      Dim integral As Integer = 8395
      Console.WriteLine("C: {0}", _
              integral.ToString("C", ci))           ' Displays "C: $8,395.00"
      Console.WriteLine("D: {0}", _
              integral.ToString("D6"))              ' Displays "D: 008395" 
      Console.WriteLine("E: {0}", _
              integral.ToString("E03", ci))         ' Displays "E: 8.395E+003"
      Console.WriteLine("F: {0}", _
              integral.ToString("F01", ci))         ' Displays "F: 8395.0"    
      Console.WriteLine("G: {0}", _ 
              integral.ToString("G", ci))           ' Displays "G: 8395"
      Console.WriteLine("N: {0}", _
              integral.ToString("N01", ci))         ' Displays "N: 8,395.0"
      Console.WriteLine("P: {0}", _
              (integral/10000).ToString("P02", ci)) ' Displays "P: 83.95 %"
      Console.WriteLine("X: 0x{0}", _
              integral.ToString("X", ci))           ' Displays "X: 0x20CB"
      Console.WriteLine()
   End Sub
End Module
```

## <a name="see-also"></a>См. также

[System.Globalization.NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)

[Строки настраиваемых числовых форматов](custom-numeric.md)

[Типы форматирования](formatting-types.md)

[Практическое руководство. Добавление начальных нулей к числу](pad-number.md)

[Составное форматирование](composite-format.md)



<!--HONumber=Nov16_HO1-->


