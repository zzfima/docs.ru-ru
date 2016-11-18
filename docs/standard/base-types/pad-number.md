---
title: "Практическое руководство. Добавление к числу начальных нулей"
description: "Практическое руководство. Добавление к числу начальных нулей"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: a517c066-b11e-4815-826b-9262611eac40
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 0a136d88dfbc83d40ff8a204f275537c24f9748b

---

# <a name="how-to-pad-a-number-with-leading-zeros"></a>Практическое руководство. Добавление к числу начальных нулей

К целому числу можно добавить начальные нули, используя [строку стандартного числового формата](standard-numeric.md) "D" с описателем точности. С помощью [строки настраиваемого числового формата](custom-numeric.md) начальные нули можно добавлять как к целым числам, так и к числам с плавающей запятой. В этой статье показано, как использовать оба метода для дополнения числа начальными нулями.

## <a name="to-pad-an-integer-with-leading-zeros-to-a-specific-length"></a>Дополнение целого числа начальными нулями до определенной длины

1. Определите минимальное число разрядов для целого числа. Добавьте к этому значению число начальных разрядов.

2. Определите, хотите ли вы показывать целое число как десятичное или шестнадцатеричное.

    * Для отображения целого числа в виде десятичного значения вызовите его метод `ToString(String)` и передайте строку "D*n*" в качестве значения параметра format, где *n* представляет минимальную длину строки.
    
    * Для отображения целого числа в виде шестнадцатеричного значения вызовите его метод `ToString(String)` и передайте строку "X*n*" в качестве значения параметра format, где *n* представляет минимальную длину строки.
    
  Строку формата можно также использовать в методе, например [Console.WriteLine](xref:System.Console.WriteLine) или [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)), в котором применяется [составное форматирование](composite-format.md).  
  
Следующий пример форматирует несколько целых значений с добавлением начальных нулей, чтобы общая длина форматированного числа составляла по крайней мере 8 символов.

```csharp
byte byteValue = 254;
short shortValue = 10342;
int intValue = 1023983;
long lngValue = 6985321;               
ulong ulngValue = UInt64.MaxValue;

// Display integer values by calling the ToString method.
Console.WriteLine("{0,22} {1,22}", byteValue.ToString("D8"), byteValue.ToString("X8"));
Console.WriteLine("{0,22} {1,22}", shortValue.ToString("D8"), shortValue.ToString("X8"));
Console.WriteLine("{0,22} {1,22}", intValue.ToString("D8"), intValue.ToString("X8"));
Console.WriteLine("{0,22} {1,22}", lngValue.ToString("D8"), lngValue.ToString("X8"));
Console.WriteLine("{0,22} {1,22}", ulngValue.ToString("D8"), ulngValue.ToString("X8"));
Console.WriteLine();

// Display the same integer values by using composite formatting.
Console.WriteLine("{0,22:D8} {0,22:X8}", byteValue);
Console.WriteLine("{0,22:D8} {0,22:X8}", shortValue);
Console.WriteLine("{0,22:D8} {0,22:X8}", intValue);
Console.WriteLine("{0,22:D8} {0,22:X8}", lngValue);
Console.WriteLine("{0,22:D8} {0,22:X8}", ulngValue);
// The example displays the following output:
//                     00000254               000000FE
//                     00010342               00002866
//                     01023983               000F9FEF
//                     06985321               006A9669
//         18446744073709551615       FFFFFFFFFFFFFFFF
//       
//                     00000254               000000FE
//                     00010342               00002866
//                     01023983               000F9FEF
//                     06985321               006A9669
//         18446744073709551615       FFFFFFFFFFFFFFFF
//         18446744073709551615       FFFFFFFFFFFFFFFF
```

```vb
Dim byteValue As Byte = 254
Dim shortValue As Short = 10342
Dim intValue As Integer = 1023983
Dim lngValue As Long = 6985321               
Dim ulngValue As ULong = UInt64.MaxValue

' Display integer values by calling the ToString method.
Console.WriteLine("{0,22} {1,22}", byteValue.ToString("D8"), byteValue.ToString("X8"))
Console.WriteLine("{0,22} {1,22}", shortValue.ToString("D8"), shortValue.ToString("X8"))
Console.WriteLine("{0,22} {1,22}", intValue.ToString("D8"), intValue.ToString("X8"))
Console.WriteLine("{0,22} {1,22}", lngValue.ToString("D8"), lngValue.ToString("X8"))
Console.WriteLine("{0,22} {1,22}", ulngValue.ToString("D8"), ulngValue.ToString("X8"))
Console.WriteLine()

' Display the same integer values by using composite formatting.
Console.WriteLine("{0,22:D8} {0,22:X8}", byteValue)
Console.WriteLine("{0,22:D8} {0,22:X8}", shortValue)
Console.WriteLine("{0,22:D8} {0,22:X8}", intValue)
Console.WriteLine("{0,22:D8} {0,22:X8}", lngValue)
Console.WriteLine("{0,22:D8} {0,22:X8}", ulngValue)
' The example displays the following output:
'                     00000254               000000FE
'                     00010342               00002866
'                     01023983               000F9FEF
'                     06985321               006A9669
'         18446744073709551615       FFFFFFFFFFFFFFFF
'       
'                     00000254               000000FE
'                     00010342               00002866
'                     01023983               000F9FEF
'                     06985321               006A9669
'         18446744073709551615       FFFFFFFFFFFFFFFF
```

## <a name="to-pad-an-integer-with-a-specific-number-of-leading-zeros"></a>Дополнение целого числа определенным количеством начальных нулей

1. Определите, сколько начальных нулей должно быть в целом числе.

2. Определите, хотите ли вы показывать целое число как десятичное или шестнадцатеричное. Чтобы отформатировать число как десятичное значение, необходимо использовать стандартный описатель формата "D", чтобы отформатировать число как шестнадцатеричное значение, используйте стандартный описатель формата "X".

3. Определите длину недополненной числовой строки, вызвав метод `ToString("D").Length` или `ToString("X").Length` целого числа. 

4. Добавьте число начальных нулей, которое следует добавить в форматированную строку, к длине недополненной числовой строки. Будет получена общая длина результирующей строки.

5. Вызовите для целого значения метод `ToString(String)` и передайте строку "D*n*" для десятичных строк или строку "X*n*" для шестнадцатеричных строк, где *n* означает общую длину дополненной строки. Строку форматирования "D*n*" или "X*n*" можно также использовать в методе, поддерживающем составное форматирование.

Следующий пример дополняет целое число пятью начальными нулями.

```csharp
int value = 160934;
int decimalLength = value.ToString("D").Length + 5;
int hexLength = value.ToString("X").Length + 5;
Console.WriteLine(value.ToString("D" + decimalLength.ToString()));
Console.WriteLine(value.ToString("X" + hexLength.ToString()));
// The example displays the following output:
//       00000160934
//       00000274A6
```

```vb
Dim value As Integer = 160934
Dim decimalLength As Integer = value.ToString("D").Length + 5
Dim hexLength As Integer = value.ToString("X").Length + 5
Console.WriteLine(value.ToString("D" + decimalLength.ToString()))
Console.WriteLine(value.ToString("X" + hexLength.ToString()))
' The example displays the following output:
'       00000160934
'       00000274A6 
```

## <a name="to-pad-a-numeric-value-with-leading-zeros-to-a-specific-length"></a>Дополнение числового значения начальными нулями до определенной длины

1. Определите, сколько разрядов слева от десятичного разделителя должно быть в строковом представлении числа. Добавьте к этому значению число начальных нулей.

2. Определите строку настраиваемого формата числа, использующую местозаполнитель нуля ("0") для представления минимального количества нулей.

3. Вызовите метод `ToString(String)` числа и передайте ему строку настраиваемого формата. Вы также можете использовать строку настраиваемого формата с методом, поддерживающим составное форматирование.

Следующий пример форматирует несколько числовых значений с добавлением начальных нулей, чтобы общая длина форматированного числа составляла по крайней мере 8 символов слева от десятичного разделителя.

```csharp
string fmt = "00000000.##";
int intValue = 1053240;
decimal decValue = 103932.52m;
float sngValue = 1549230.10873992f;
double dblValue = 9034521202.93217412;

// Display the numbers using the ToString method.
Console.WriteLine(intValue.ToString(fmt));
Console.WriteLine(decValue.ToString(fmt));           
Console.WriteLine(sngValue.ToString(fmt));
Console.WriteLine(dblValue.ToString(fmt));           
Console.WriteLine();

// Display the numbers using composite formatting.
string formatString = " {0,15:" + fmt + "}";
Console.WriteLine(formatString, intValue);      
Console.WriteLine(formatString, decValue);      
Console.WriteLine(formatString, sngValue);      
Console.WriteLine(formatString, dblValue);      
// The example displays the following output:
//       01053240
//       00103932.52
//       01549230
//       9034521202.93
//       
//               01053240
//            00103932.52
//               01549230
//          9034521202.93  
```

```vb
Dim fmt As String = "00000000.##"
Dim intValue As Integer = 1053240
Dim decValue As Decimal = 103932.52d
Dim sngValue As Single = 1549230.10873992
Dim dblValue As Double = 9034521202.93217412

' Display the numbers using the ToString method.
Console.WriteLine(intValue.ToString(fmt))
Console.WriteLine(decValue.ToString(fmt))            
Console.WriteLine(sngValue.ToString(fmt))
Console.WriteLine(dblValue.ToString(fmt))            
Console.WriteLine()

' Display the numbers using composite formatting.
Dim formatString As String = " {0,15:" + fmt + "}"
Console.WriteLine(formatString, intValue)      
Console.WriteLine(formatString, decValue)      
Console.WriteLine(formatString, sngValue)      
Console.WriteLine(formatString, dblValue)      
' The example displays the following output:
'       01053240
'       00103932.52
'       01549230
'       9034521202.93
'       
'               01053240
'            00103932.52
'               01549230
'          9034521202.93
```

## <a name="to-pad-a-numeric-value-with-a-specific-number-of-leading-zeros"></a>Дополнение числового значения определенным количеством начальных нулей

1. Определите, сколько начальных нулей должно быть в числовом значении.

2. Определите количество разрядов слева от десятичного разделителя в недополненной числовой строке. Для этого:

    1. Определите, содержит ли строковое представление числа символ десятичной точки.
    
    2. Если это так, определите число символов слева от десятичной точки.       
    
    -или-
       
    Если строка не содержит десятичную точку, определите длину строки. 
       
3. Создайте строку настраиваемого формата, использующую нулевой местозаполнитель ("0") для каждого начального нуля, которые будут добавлены в строку, и использующую нулевой местозаполнитель или местозаполнитель разряда ("#") для представления каждого разряда в строке по умолчанию. 

4. Передайте строку настраиваемого формата в качестве параметра методу ToString(String) числа или методу, поддерживающему составное форматирование.

В следующем примере в начало двух значений [Double](xref:System.Double) добавляется по пять нулей.

```csharp
double[] dblValues = { 9034521202.93217412, 9034521202 };
foreach (double dblValue in dblValues)
{
   string decSeparator = System.Globalization.NumberFormatInfo.CurrentInfo.NumberDecimalSeparator;
   string fmt, formatString;

   if (dblValue.ToString().Contains(decSeparator))
   {
      int digits = dblValue.ToString().IndexOf(decSeparator);
      fmt = new String('0', 5) + new String('#', digits) + ".##";
   }
   else
   {
      fmt = new String('0', dblValue.ToString().Length);   
   }
   formatString = "{0,20:" + fmt + "}";

   Console.WriteLine(dblValue.ToString(fmt));
   Console.WriteLine(formatString, dblValue);
}
// The example displays the following output:
//       000009034521202.93
//         000009034521202.93
//       9034521202
//                 9034521202 
```

```vb
Dim dblValues() As Double = { 9034521202.93217412, 9034521202 }
For Each dblValue As Double In dblValues
   Dim decSeparator As String = System.Globalization.NumberFormatInfo.CurrentInfo.NumberDecimalSeparator
   Dim fmt, formatString As String

   If dblValue.ToString.Contains(decSeparator) Then
      Dim digits As Integer = dblValue.ToString().IndexOf(decSeparator)
      fmt = New String("0"c, 5) + New String("#"c, digits) + ".##"
   Else
      fmt = New String("0"c, dblValue.ToString.Length)   
   End If
   formatString = "{0,20:" + fmt + "}"

   Console.WriteLine(dblValue.ToString(fmt))
   Console.WriteLine(formatString, dblValue)
Next
' The example displays the following output:
'       000009034521202.93
'         000009034521202.93
'       9034521202
'                 9034521202
```

## <a name="see-also"></a>См. также

[Строки стандартных числовых форматов](standard-numeric.md)

[Строки настраиваемых числовых форматов](custom-numeric.md)

[Составное форматирование](composite-format.md)




<!--HONumber=Nov16_HO3-->


