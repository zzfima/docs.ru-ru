---
title: "Строки настраиваемых числовых форматов"
description: "Строки настраиваемых числовых форматов"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/25/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 7b1c16ee-956f-4e9c-8502-c3dd6598c51d
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 017ee2b6feb87841f31660fe6cb76ccbefd5c83b
ms.lasthandoff: 03/02/2017

---

# <a name="custom-numeric-format-strings"></a>Строки настраиваемых числовых форматов

Чтобы определить способ форматирования числовых данных, можно создать строку настраиваемого числового формата, состоящую из одного или нескольких описателей настраиваемого формата. Строка настраиваемого числового формата — это любая строка формата, не являющаяся [строкой стандартного числового формата](standard-numeric.md). 

Строки настраиваемых числовых форматов поддерживаются некоторыми перегрузками метода `ToString` всех числовых типов. Например, можно задать строку числового формата для методов [ToString(String)](xref:System.Int32.ToString(System.String)) и [ToString(String, IFormatProvider)](xref:System.Int32.ToString(System.String,System.IFormatProvider)) типа [Int32](xref:System.Int32). Строки настраиваемых числовых форматов также поддерживаются функцией [составного форматирования](composite-format.md) .NET Framework, используемой некоторыми методами `Write` и `WriteLine` классов [Console](xref:System.Console) и [StreamWriter](xref:System.IO.StreamWriter), методом [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) и методом [StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)).

В следующей таблице приведены описатели стандартного числового формата и примеры выходных данных, формируемых каждым описателем формата. Дополнительные сведения об использовании строк настраиваемого числового формата см. в разделе [Примечания](#notes); обширную демонстрацию их использования см. в разделе [Пример](#example).

Описатель формата | Имя | Описание | Примеры
---------------- | ---- | ----------- | --------
"0" | Знак-заместитель нуля | Заменяет ноль соответствующей цифрой, если такая имеется. В противном случае в результирующей строке будет стоять ноль. | `1234.5678 ("00000") -> 01235`; `0.45678 ("0.00", en-US) -> 0.46`; `0.45678 ("0.00", fr-FR) -> 0,46`
"#" | Заместитель цифры | Заменяет знак "#" соответствующей цифрой, если такая имеется. В противном случае в результирующей строке не будет цифры. Обратите внимание, что в итоговой строке не будет отображаться цифра, если соответствующей цифрой в строке ввода является незначащий 0. Например, 0003 ("####") -> 3. | `1234.5678 ("#####") -> 1235`; `0.45678 ("#.##", en-US) -> .46`; `0.45678 ("#.##", fr-FR) -> ,46`
"." | Разделитель | Определяет расположение разделителя целой и дробной частей в результирующей строке. | `0.45678 ("0.00", en-US) -> 0.46`; `0.45678 ("0.00", fr-FR) -> 0,46`
"," | Разделитель групп и масштабирование чисел | Служит в качестве описателя разделителя групп и описателя масштабирования чисел. В качестве разделителя групп вставляет локализованный символ-разделитель групп между всеми группами. В качестве описателя масштабирования чисел делит число на 1000 для всех указанных запятых. | Описатель разделителя групп: `2147483647 ("##,#", en-US) -> 2,147,483,647`; `2147483647 ("##,#", es-ES) -> 2.147.483.647`. Описатель масштабирования: `2147483647 ("#,#,,", en-US) -> 2,147`; `2147483647 ("#,#,,", es-ES) -> 2.147`
"%" | Заместитель процентов | Умножает число на 100 и вставляет локализованный символ процента в результирующую строку. | `0.3697 ("%#0.00", en-US) -> %36.97`; `0.3697 ("%#0.00", el-GR) -> %36,97`; `0.3697 ("##.0 %", en-US) -> 37.0 %`; `0.3697 ("##.0 %", el-GR) -> 37,0 %`
"‰" | Местозаполнитель промилле | Умножает число на 1000 и вставляет локализованный символ промилле в результирующую строку. | `0.03697 ("#0.00‰", en-US) -> 36.97‰`; `0.03697 ("#0.00‰", ru-RU) -> 36,97‰`
"E0", "E+0", "E-0", "e0", "e+0", "e-0" | Экспоненциальная нотация | Если за этим описателем следует по меньшей мере один ноль (0), результат форматируется с использованием экспоненциальной нотации. Регистр ("E" или "e") определяет регистр символа экспоненты в результирующей строке. Минимальное число цифр экспоненты определяется количеством нулей, стоящих за символом "E" или "e". Знак "+" указывает на то, что перед экспонентой всегда должен ставиться символ знака. Знак "-" указывает на то, что символ знака должен ставиться только в случае, если экспонента имеет отрицательное значение. | `987654 ("#0.0e0") -> 98.8e4`; `1503.92311 ("0.0##e+00") -> 1.504e+03`; `1.8901385E-16 ("0.0e+00") -> 1.9e-16`
\ | Escape-символ | Указывает на то, что следующий за ним символ должен рассматриваться как литерал, а не как описатель настраиваемого формата. | `987654 ("\###00\#") -> #987654#`
'строка', "строка" | Разделитель строк-литералов | Указывает на то, что заключенные в разделители символы должны быть скопированы в результирующую строку без изменений. | `68 ("# ' degrees'") -> 68 degrees`
; | Разделитель секций | Определяет секции с раздельными строками формата для положительных чисел, отрицательных чисел и нуля. | `12.345 ("#0.0#;(#0.0#);-\0-") -> 12.35`; `0 ("#0.0#;(#0.0#);-\0-") -> -0-`; `-12.345 ("#0.0#;(#0.0#);-\0-") -> (12.35)`; `12.345 ("#0.0#;(#0.0#)") -> 12.35`; `0 ("#0.0#;(#0.0#)") -> 0.0 ; -12.345 ("#0.0#;(#0.0#)") -> (12.35)`
Другой | Все остальные символы | Символ копируется в результирующую строку без изменений. | `68 ("# °") -> 68 °`

В приведенных ниже разделах содержится подробная информация о всех описателях настраиваемого числового формата.

## <a name="the-0-custom-specifier"></a>Настраиваемый описатель "0"

Описатель настраиваемого формата "0" служит нулевым символом-заполнителем. Если форматируемое значение содержит цифру в позиции, где в строке формата стоит ноль, то эта цифра копируется в результирующую строку; в противном случае в результирующей строке будет стоять ноль. Позиция крайнего левого нуля перед разделителем целой и дробной частей и позиция крайнего правого нуля после разделителя целой и дробной частей определяют диапазон цифр, которые всегда включаются в результирующую строку. 

Спецификатор "00" приводит к округлению значения до ближайшего значения цифры, предшествующей десятичной точке-разделителю, если назначено использование округления от нуля. Например, в результате форматирования числа 34,5 с помощью строки "00" будет получена строка со значением"35".

В следующем примере показано форматирование нескольких значений с помощью строк настраиваемого формата, содержащих нулевые заполнители.

```csharp
double value;

value = 123;
Console.WriteLine(value.ToString("00000"));
Console.WriteLine(String.Format("{0:00000}", value));
// Displays 00123

value = 1.2;
Console.WriteLine(value.ToString("0.00", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                "{0:0.00}", value));
// Displays 1.20

Console.WriteLine(value.ToString("00.00", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:00.00}", value));
// Displays 01.20

CultureInfo daDK = CultureInfo.CreateSpecificCulture("da-DK");
Console.WriteLine(value.ToString("00.00", daDK)); 
Console.WriteLine(String.Format(daDK, "{0:00.00}", value));
// Displays 01,20

value = .56;
Console.WriteLine(value.ToString("0.0", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0.0}", value));
// Displays 0.6

value = 1234567890;
Console.WriteLine(value.ToString("0,0", CultureInfo.InvariantCulture));    
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0,0}", value));    
// Displays 1,234,567,890      

CultureInfo elGR = CultureInfo.CreateSpecificCulture("el-GR");
Console.WriteLine(value.ToString("0,0", elGR));    
Console.WriteLine(String.Format(elGR, "{0:0,0}", value));    
// Displays 1.234.567.890

value = 1234567890.123456;
Console.WriteLine(value.ToString("0,0.0", CultureInfo.InvariantCulture));    
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0,0.0}", value));    
// Displays 1,234,567,890.1  

value = 1234.567890;
Console.WriteLine(value.ToString("0,0.00", CultureInfo.InvariantCulture));    
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0,0.00}", value));    
// Displays 1,234.57
```

```vb
Dim value As Double

value = 123
Console.WriteLine(value.ToString("00000"))
Console.WriteLine(String.Format("{0:00000}", value))
' Displays 00123

value = 1.2
Console.Writeline(value.ToString("0.00", CultureInfo.InvariantCulture))
Console.Writeline(String.Format(CultureInfo.InvariantCulture, 
                  "{0:0.00}", value))
' Displays 1.20
Console.WriteLine(value.ToString("00.00", CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:00.00}", value))
' Displays 01.20
Dim daDK As CultureInfo = CultureInfo.CreateSpecificCulture("da-DK")
Console.WriteLine(value.ToString("00.00", daDK))
Console.WriteLine(String.Format(daDK, "{0:00.00}", value))
' Displays 01,20

value = .56
Console.WriteLine(value.ToString("0.0", CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0.0}", value))
' Displays 0.6

value = 1234567890
Console.WriteLine(value.ToString("0,0", CultureInfo.InvariantCulture))    
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0,0}", value))    
' Displays 1,234,567,890      
Dim elGR As CultureInfo = CultureInfo.CreateSpecificCulture("el-GR")
Console.WriteLine(value.ToString("0,0", elGR))
Console.WriteLine(String.Format(elGR, "{0:0,0}", value))    
' Displays 1.234.567.890

value = 1234567890.123456
Console.WriteLine(value.ToString("0,0.0", CultureInfo.InvariantCulture))    
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0,0.0}", value))    
' Displays 1,234,567,890.1  

value = 1234.567890
Console.WriteLine(value.ToString("0,0.00", CultureInfo.InvariantCulture))    
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0,0.00}", value))    
' Displays 1,234.57
```

## <a name="the--custom-specifier"></a>Настраиваемый описатель "#"

Описатель настраиваемого формата "#" служит символом-заполнителем для цифр. Если в форматируемом значении на позиции, где в строке формата присутствует символ "#", есть цифра, то эта цифра копируется в результирующую строку. В противном случае в выходной строке на этой позиции ничего не записывается. 

Обратите внимание, что при использовании этого описателя незначащие нули не отображаются, даже если ноль является единственной цифрой в строке. Ноль отображается только в том случае, если он является значащей цифрой отображаемого числа. 

Строка формата "##" приводит к округлению значения до ближайшего значения цифры, предшествующей десятичному разделителю, если назначено использование округления от нуля. Например, в результате форматирования числа 34,5 с помощью строки "##" будет получена строка со значением "35".

В следующем примере показано форматирование нескольких значений с помощью строк настраиваемого формата, содержащих заполнители для цифр.

```csharp
double value;

value = 1.2;
Console.WriteLine(value.ToString("#.##", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#.##}", value));
// Displays 1.2

value = 123;
Console.WriteLine(value.ToString("#####"));
Console.WriteLine(String.Format("{0:#####}", value));
// Displays 123

value = 123456;
Console.WriteLine(value.ToString("[##-##-##]"));      
Console.WriteLine(String.Format("{0:[##-##-##]}", value));      
// Displays [12-34-56]

value = 1234567890;
Console.WriteLine(value.ToString("#"));
Console.WriteLine(String.Format("{0:#}", value));
// Displays 1234567890

Console.WriteLine(value.ToString("(###) ###-####"));
Console.WriteLine(String.Format("{0:(###) ###-####}", value));
// Displays (123) 456-7890
```

```vb
Dim value As Double

value = 1.2
Console.WriteLine(value.ToString("#.##", CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#.##}", value))
' Displays 1.2

value = 123
Console.WriteLine(value.ToString("#####"))
Console.WriteLine(String.Format("{0:#####}", value))
' Displays 123

value = 123456
Console.WriteLine(value.ToString("[##-##-##]"))      
Console.WriteLine(String.Format("{0:[##-##-##]}", value))      
' Displays [12-34-56]

value = 1234567890
Console.WriteLine(value.ToString("#"))
Console.WriteLine(String.Format("{0:#}", value))
' Displays 1234567890

Console.WriteLine(value.ToString("(###) ###-####"))
Console.WriteLine(String.Format("{0:(###) ###-####}", value))
' Displays (123) 456-7890
```

Чтобы получить итоговую строку, в которой отсутствуют цифры или начальные нули заменены пробелами, используйте функцию [составного форматирования](composite-format.md) и укажите ширину поля, как показано в следующем примере.

```csharp
using System;

public class Example
{
   public static void Main()
   {
      Double value = .324;
      Console.WriteLine("The value is: '{0,5:#.###}'", value);
   }
}
// The example displays the following output if the current culture
// is en-US:
//      The value is: ' .324'
```

```vb
Module Example
   Public Sub Main()
      Dim value As Double = .324
      Console.WriteLine("The value is: '{0,5:#.###}'", value)
   End Sub
End Module
' The example displays the following output if the current culture
' is en-US:
'      The value is: ' .324'
```

## <a name="the--custom-specifier"></a>"." Настраиваемый описатель "."

Описатель настраиваемого формата "." вставляет в результирующую строку локализованный разделитель целой и дробной частей числа. Первая точка в строке формата определяет расположение разделителя целой и дробной частей форматированного значения, а все прочие точки игнорируются. 

Символ, используемый в качестве разделителя целой и дробной части в результирующей строке, не всегда будет точкой; его значение определяется свойством [NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator) объекта [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), управляющего форматированием.

В следующем примере спецификатор формата "." используется для определения местоположения десятичного разделителя в нескольких выходных строках.

```csharp
double value;

value = 1.2;
Console.WriteLine(value.ToString("0.00", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0.00}", value));
// Displays 1.20

Console.WriteLine(value.ToString("00.00", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:00.00}", value));
// Displays 01.20

Console.WriteLine(value.ToString("00.00", 
                CultureInfo.CreateSpecificCulture("da-DK")));
Console.WriteLine(String.Format(CultureInfo.CreateSpecificCulture("da-DK"),
                "{0:00.00}", value));
// Displays 01,20

value = .086;
Console.WriteLine(value.ToString("#0.##%", CultureInfo.InvariantCulture)); 
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#0.##%}", value)); 
// Displays 8.6%

value = 86000;
Console.WriteLine(value.ToString("0.###E+0", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                "{0:0.###E+0}", value));
// Displays 8.6E+4
```

```vb
Dim value As Double

  value = 1.2
  Console.Writeline(value.ToString("0.00", CultureInfo.InvariantCulture))
  Console.Writeline(String.Format(CultureInfo.InvariantCulture, 
                                  "{0:0.00}", value))
  ' Displays 1.20

  Console.WriteLine(value.ToString("00.00", CultureInfo.InvariantCulture))
  Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                  "{0:00.00}", value))
  ' Displays 01.20

  Console.WriteLine(value.ToString("00.00", _
                    CultureInfo.CreateSpecificCulture("da-DK")))
  Console.WriteLine(String.Format(CultureInfo.CreateSpecificCulture("da-DK"),
                    "{0:00.00}", value))
  ' Displays 01,20

  value = .086
  Console.WriteLine(value.ToString("#0.##%", CultureInfo.InvariantCulture)) 
  Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                  "{0:#0.##%}", value)) 
  ' Displays 8.6%

  value = 86000
  Console.WriteLine(value.ToString("0.###E+0", CultureInfo.InvariantCulture))
  Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                    "{0:0.###E+0}", value))
' Displays 8.6E+4
```

## <a name="the--custom-specifier"></a>Настраиваемый описатель ","

Символ "," служит в качестве описателя разделителя групп и описателя масштабирования чисел. 

* Разделитель групп: если между двумя заполнителями для цифр ("0" или "#"), задающими форматирование целой части числа, стоит одна или несколько запятых, то между всеми группами целой части числа вставляется символ-разделитель групп. 

  Свойства [NumberGroupSeparator](xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator) и [NumberGroupSizes](xref:System.Globalization.NumberFormatInfo.NumberGroupSizes) текущего объекта [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) определяют знак, используемый в качестве разделителя групп числа и размера каждой группы числа. Например, если строка "#,#" и неизменяемый язык и региональные параметры используются для форматирования числа 1000, то результатом является "1,000".
  
* Описатель масштабирования чисел: если сразу слева от явно или неявно заданного разделителя целой и дробной части стоит одна или несколько запятых, форматируемое число делится на 1000 для каждой указанной запятой. Например, если строка "0,," используется для форматирования числа 100 миллионов, то результатом является "100". 

Разделитель групп и описатель масштабирования чисел можно использовать в строке формата одновременно. Например, если строка "#,&0;,," и неизменяемый язык и региональные параметры используются для форматирования числа один миллиард, то результатом является "1,000". 

В следующем примере демонстрируется использование запятой в качестве разделителя групп.

```csharp
double value = 1234567890;
Console.WriteLine(value.ToString("#,#", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#,#}", value));
// Displays 1,234,567,890      

Console.WriteLine(value.ToString("#,##0,,", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#,##0,,}", value));
// Displays 1,235
```

```vb
Dim value As Double = 1234567890
Console.WriteLine(value.ToString("#,#", CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#,#}", value))
' Displays 1,234,567,890      

Console.WriteLine(value.ToString("#,##0,,", CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#,##0,,}", value))
' Displays 1,235
```

Следующий пример иллюстрирует использование запятой как спецификатора масштабирования числа.

```csharp
double value = 1234567890;
Console.WriteLine(value.ToString("#,,", CultureInfo.InvariantCulture));    
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#,,}", value));    
// Displays 1235   

Console.WriteLine(value.ToString("#,,,", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#,,,}", value));
// Displays 1  

Console.WriteLine(value.ToString("#,##0,,", CultureInfo.InvariantCulture));       
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#,##0,,}", value));       
// Displays 1,235
```  

```vb
Dim value As Double = 1234567890
  Console.WriteLine(value.ToString("#,,", CultureInfo.InvariantCulture))    
  Console.WriteLine(String.Format(CultureInfo.InvariantCulture, "{0:#,,}", value))    
  ' Displays 1235   

  Console.WriteLine(value.ToString("#,,,", CultureInfo.InvariantCulture))
  Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                  "{0:#,,,}", value))
' Displays 1  

  Console.WriteLine(value.ToString("#,##0,,", CultureInfo.InvariantCulture))       
  Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                  "{0:#,##0,,}", value))       
' Displays 1,235
```

## <a name="the--custom-specifier"></a>Настраиваемый описатель "%"

При использовании символа процента ("%") в строке формата число перед форматированием будет умножено на 100. В то место, где в строке формата стоит символ "%", в число будет вставлен локализованный символ процента. Используемый при этом символ процента определяется свойством [PercentSymbol](xref:System.Globalization.NumberFormatInfo.PercentSymbol) текущего объекта [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo).

В следующем примере определяется несколько строк настраиваемого формата, включающих настраиваемый описатель "%".

```csharp
double value = .086;
Console.WriteLine(value.ToString("#0.##%", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#0.##%}", value));
// Displays 8.6%     
```

```vb
Dim value As Double = .086
Console.WriteLine(value.ToString("#0.##%", CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#0.##%}", value))
' Displays 8.6% 
```

## <a name="the--custom-specifier"></a>Настраиваемый описатель "‰"

При использовании в строке формата символа промилле ("‰" или "\u2030") перед форматированием число будет умножено на 1000. В позицию возвращаемой строки, соответствующую положению символа "‰" в строке формата, будет вставлен необходимый символ промилле. Используемый знак промилле определяется значением свойства [NumberFormatInfo.PerMilleSymbol](xref:System.Globalization.NumberFormatInfo.PerMilleSymbol) объекта, содержащего сведения о форматировании для заданного языка и региональных параметров.

В следующем примере определяется строка настраиваемого формата, включающая настраиваемый описатель "‰".

```csharp
double value = .00354;
string perMilleFmt = "#0.## " + '\u2030';
Console.WriteLine(value.ToString(perMilleFmt, CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:" + perMilleFmt + "}", value));
// Displays 3.54‰   
```

```vb
Dim value As Double = .00354
Dim perMilleFmt As String = "#0.## " & ChrW(&h2030)
Console.WriteLine(value.ToString(perMilleFmt, CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:" + perMilleFmt + "}", value))
' Displays 3.54 ‰
```

## <a name="the-e-and-e-custom-specifiers"></a>Настраиваемые описатели "E" и "e"

Если в строке формата присутствует подстрока "E", "E+", "E-", "e", "e+" или "e-", за которой сразу следует по меньшей мере один ноль, то число форматируется с использованием экспоненциальной нотации. Между числом и экспонентой при этом вставляется символ "E" или "e". Минимальное число цифр экспоненты в результирующей строке определяется количеством нулей, стоящих после индикатора экспоненциальной нотации. Форматы "E+" и "e+" указывают на то, что перед экспонентой всегда должен стоять положительный или отрицательный знак. Форматы "E", "e", "E-" и "e-" указывают на то, что символ знака должен ставиться только перед экспонентой с отрицательным значением.

В следующем примере несколько числовых значений форматируются с помощью спецификаторов экспоненциального представления.

```csharp
double value = 86000;
Console.WriteLine(value.ToString("0.###E+0", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0.###E+0}", value));
// Displays 8.6E+4

Console.WriteLine(value.ToString("0.###E+000", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0.###E+000}", value));
// Displays 8.6E+004

Console.WriteLine(value.ToString("0.###E-000", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0.###E-000}", value));
// Displays 8.6E004
```

```vb
Dim value As Double = 86000
Console.WriteLine(value.ToString("0.###E+0", CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0.###E+0}", value))
' Displays 8.6E+4

Console.WriteLine(value.ToString("0.###E+000", CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0.###E+000}", value))
' Displays 8.6E+004

Console.WriteLine(value.ToString("0.###E-000", CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0.###E-000}", value))
' Displays 8.6E004
```

## <a name="the--escape-character"></a>Escape-символ "\"

Символы "#", "0", ".", ",", "%" и "‰" в строке формата воспринимаются как описатели формата, а не как символы-литералы. В зависимости от положения в строке настраиваемого формата символ "E" верхнего и нижнего регистра, также как и символы "+" и "-", могут восприниматься как описатели формата. 

Чтобы предотвратить интерпретацию символа в качестве описателя формата, перед ним можно поставить так называемый escape-символ — обратную косую черту. Наличие escape-символа означает, что следующий за ним символ является литералом, который следует перенести в результирующую строку без изменений.

Чтобы включить в результирующую строку обратную косую черту, перед ней нужно поставить дополнительную обратную косую черту (\\). 

> [!NOTE]
> Кроме того, в некоторых компиляторах, например компиляторе C#, одиночная обратная косая черта также может восприниматься как escape-символ. Чтобы гарантировать, что строка будет правильно воспринята при форматировании, можно поставить символ буквального строкового литерала (символ "@") перед строкой в C# или добавить дополнительный символ обратной косой черты перед каждой обратной косой чертой. В следующем примере кода на языке C# демонстрируются оба подхода.

В следующем примере интерпретация символов "#", "0" и "\" в качестве escape-символов или описателей формата при форматировании предотвращается с помощью escape-символа. В примере используется дополнительная обратная косая черта, позволяющая гарантировать, что обратная косая черта будет воспринята как символ-литерал.

```csharp
int value = 123;
Console.WriteLine(value.ToString("\\#\\#\\# ##0 dollars and \\0\\0 cents \\#\\#\\#"));
Console.WriteLine(String.Format("{0:\\#\\#\\# ##0 dollars and \\0\\0 cents \\#\\#\\#}",
                                value));
// Displays ### 123 dollars and 00 cents ###

Console.WriteLine(value.ToString(xref:"\#\#\# ##0 dollars and \0\0 cents \#\#\#"));
Console.WriteLine(String.Format(xref:"{0:\#\#\# ##0 dollars and \0\0 cents \#\#\#}",
                                value));
// Displays ### 123 dollars and 00 cents ###

Console.WriteLine(value.ToString("\\\\\\\\\\\\ ##0 dollars and \\0\\0 cents \\\\\\\\\\\\"));
Console.WriteLine(String.Format("{0:\\\\\\\\\\\\ ##0 dollars and \\0\\0 cents \\\\\\\\\\\\}",
                                value));
// Displays \\\ 123 dollars and 00 cents \\\

Console.WriteLine(value.ToString(xref:"\\\\\\ ##0 dollars and \0\0 cents \\\\\\"));
Console.WriteLine(String.Format(xref:"{0:\\\\\\ ##0 dollars and \0\0 cents \\\\\\}",
                                value));
// Displays \\\ 123 dollars and 00 cents \\\
```

```vb
Dim value As Integer = 123
Console.WriteLine(value.ToString("\#\#\# ##0 dollars and \0\0 cents \#\#\#"))
Console.WriteLine(String.Format("{0:\#\#\# ##0 dollars and \0\0 cents \#\#\#}", 
                                value))
' Displays ### 123 dollars and 00 cents ###

Console.WriteLine(value.ToString("\\\\\\ ##0 dollars and \0\0 cents \\\\\\"))
Console.WriteLine(String.Format("{0:\\\\\\ ##0 dollars and \0\0 cents \\\\\\}", 
                                value))
' Displays \\\ 123 dollars and 00 cents \\\
```

## <a name="the--section-separator"></a>Разделитель секций ";"

Точка с запятой (";") — это описатель условного формата, применяющий разное форматирование к числу в зависимости от того, является оно положительным числом, отрицательным числом или нулем. Для этого следует создать строку формата, состоящую из трех секций, разделенных точкой с запятой. Эти секции описаны в следующей таблице. 

Число секций | Описание
------------------ | -----------
Одна секция | Строка форматирования применяется ко всем значениям.
Две секции | Первая секция применяется для положительных значений и нулей, вторая секция применяется для отрицательных значений. Если форматируемое число является отрицательным, но становится нулем в результате округления в соответствии с форматом, заданным во второй секции, то результирующий ноль форматируется в соответствии с первой секцией.
Три секции | Первая секция применяется для положительных значений, вторая секция применяется для отрицательных значений, а третья — для нулей. Вторая секция может быть пустой (между двумя точками с запятой пусто), в этом случае первая секция будет использоваться для форматирования нулевых значений. Если форматируемое число является ненулевым, но становится нулем в результате округления в соответствии с форматом в первой или второй секции, то результирующий ноль форматируется в соответствии с третьей секцией.

При форматировании конечного значения разделители секций игнорируют любое существовавшее ранее форматирование, связанное с числом. Например, при использовании разделителей секций отрицательные значения всегда отображаются без знака "минус". Чтобы конечное отформатированное значение содержало знак "минус", его следует явным образом включить в настраиваемый спецификатор формата. 

В следующем примере описатель формата ";" используется для форматирования положительных чисел, отрицательных чисел и нулей различными способами.

```csharp
double posValue = 1234;
double negValue = -1234;
double zeroValue = 0;

string fmt2 = "##;(##)";
string fmt3 = "##;(##);**Zero**";

Console.WriteLine(posValue.ToString(fmt2));  
Console.WriteLine(String.Format("{0:" + fmt2 + "}", posValue));    
// Displays 1234

Console.WriteLine(negValue.ToString(fmt2));  
Console.WriteLine(String.Format("{0:" + fmt2 + "}", negValue));    
// Displays (1234)

Console.WriteLine(zeroValue.ToString(fmt3)); 
Console.WriteLine(String.Format("{0:" + fmt3 + "}", zeroValue));
// Displays **Zero**
```

```vb
Dim posValue As Double = 1234
Dim negValue As Double = -1234
Dim zeroValue As Double = 0

Dim fmt2 As String = "##;(##)"
Dim fmt3 As String = "##;(##);**Zero**"

Console.WriteLine(posValue.ToString(fmt2))   
Console.WriteLine(String.Format("{0:" + fmt2 + "}", posValue))    
' Displays 1234

Console.WriteLine(negValue.ToString(fmt2))   
Console.WriteLine(String.Format("{0:" + fmt2 + "}", negValue))    
' Displays (1234)

Console.WriteLine(zeroValue.ToString(fmt3))  
Console.WriteLine(String.Format("{0:" + fmt3 + "}", zeroValue))
' Displays **Zero**
```

## <a name="notes"></a>Примечания

### <a name="floating-point-infinities-and-nan"></a>Бесконечности действительных чисел с плавающей запятой и NaN

Если, вне зависимости от строки формата, значение типа с плавающей запятой [Single](xref:System.Single) или [Double](xref:System.Double) является положительной бесконечностью, отрицательной бесконечностью или не является числом (NaN), отформатированная строка будет содержать значение соответствующего свойства ([PositiveInfinitySymbol](xref:System.Globalization.NumberFormatInfo.PositiveInfinitySymbol), [NegativeInfinitySymbol](xref:System.Globalization.NumberFormatInfo.NegativeInfinitySymbol) или [NaNSymbol](xref:System.Globalization.NumberFormatInfo.NaNSymbol)) применимого в настоящий момент объекта [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo). 

### <a name="rounding-and-fixed-point-format-strings"></a>Строки формата с фиксированной запятой и округлением

Строки формата с фиксированной запятой (строки формата, не содержащие символов экспоненциальной нотации) округляют значение с точностью, определяемой количеством символов-заполнителей, стоящих справа от разделителя целой и дробной частей. Если в строке формата нет десятичной точки, то число округляется до ближайшего целого значения. Если слева от десятичной точки больше цифр, чем знаков-заместителей цифр, то лишние знаки копируются в выходную строку перед первым знаком-заместителем цифры.

## <a name="example"></a>Пример

В следующем примере показаны две строки настраиваемого числового формата. В обоих случаях заполнитель для цифр (#) отображает числовые данные, а все остальные символы копируются в результирующую строку.

```csharp
double number1 = 1234567890;
string value1 = number1.ToString("(###) ###-####");
Console.WriteLine(value1);

int number2 = 42;
string value2 = number2.ToString("My Number = #");
Console.WriteLine(value2);
// The example displays the following output:
//       (123) 456-7890
//       My Number = 42
```

```vb
Dim number1 As Double = 1234567890
Dim value1 As String = number1.ToString("(###) ###-####")
Console.WriteLine(value1)

Dim number2 As Integer = 42
Dim value2 As String = number2.ToString("My Number = #")
Console.WriteLine(value2)
' The example displays the following output:
'       (123) 456-7890
'       My Number = 42
```

## <a name="see-also"></a>См. также

[System.Globalization.NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)

[Типы форматирования](formatting-types.md)

[Строки стандартных числовых форматов](standard-numeric.md)

[Практическое руководство. Добавление начальных нулей к числу](pad-number.md)

[Составное форматирование](composite-format.md)


