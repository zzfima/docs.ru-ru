---
title: Математические функции
ms.date: 01/27/2020
helpviewer_keywords:
- math functions, Visual Basic
- arithmetic operations, math functions
- math routines
- Atn function
ms.assetid: 4d2d82e7-6924-42fe-a4a7-b4dd5bebbd0c
ms.openlocfilehash: ea30ae3b30484c1a13d6d540f121c03afb30ba26
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794597"
---
# <a name="math-functions-visual-basic"></a>Математические функции (Visual Basic)

Методы класса <xref:System.Math?displayProperty=nameWithType> предоставляют тригонометрические, Логарифмические и другие общие математические функции.

## <a name="remarks"></a>Заметки

В следующей таблице перечислены методы класса <xref:System.Math?displayProperty=nameWithType>. Их можно использовать в программе Visual Basic:
  
|Метод .NET|Описание|
|---------------------------|-----------------|
|<xref:System.Math.Abs%2A>|Возвращает абсолютное значение числа.|
|<xref:System.Math.Acos%2A>|Возвращает угол, косинус которого равен указанному числу.|
|<xref:System.Math.Asin%2A>|Возвращает угол, синус которого равен указанному числу.|
|<xref:System.Math.Atan%2A>|Возвращает угол, тангенс которого равен указанному числу.|
|<xref:System.Math.Atan2%2A>|Возвращает угол, тангенс которого равен отношению двух указанных чисел.|
|<xref:System.Math.BigMul%2A>|Возвращает полное произведение 2 32-разрядных чисел.|
|<xref:System.Math.Ceiling%2A>|Возвращает наименьшее целочисленное значение, которое больше или равно указанному `Decimal` или `Double`.|
|<xref:System.Math.Cos%2A>|Возвращает косинус указанного угла.|
|<xref:System.Math.Cosh%2A>|Возвращает гиперболический косинус указанного угла.|
|<xref:System.Math.DivRem%2A>|Возвращает частное от 2 32-битных или 64-битовых целых чисел со знаком, а также возвращает остаток в выходном параметре.|
|<xref:System.Math.Exp%2A>|Возвращает значение e (основание натуральных логарифмов), возведенное в указанную степень.|
|<xref:System.Math.Floor%2A>|Возвращает максимальное целое число, которое меньше или равно указанному `Decimal` или `Double`ному числу.|
|<xref:System.Math.IEEERemainder%2A>|Возвращает остаток, полученный от деления указанного числа на другое заданное число.|
|<xref:System.Math.Log%2A>|Возвращает натуральный (базовый e) логарифм указанного числа или логарифм указанного числа в заданном базовом массиве.|
|<xref:System.Math.Log10%2A>|Возвращает логарифм с основанием 10 указанного числа.|
|<xref:System.Math.Max%2A>|Возвращает большее из двух чисел.|
|<xref:System.Math.Min%2A>|Возвращает меньшее из двух чисел.|
|<xref:System.Math.Pow%2A>|Возвращает указанное число, возведенное в указанную степень.|
|<xref:System.Math.Round%2A>|Возвращает `Decimal` или `Double` значение, округленное до ближайшего целого значения или до указанного числа цифр дробной части.|
|<xref:System.Math.Sign%2A>|Возвращает значение типа `Integer`, указывающее знак числа.|
|<xref:System.Math.Sin%2A>|Возвращает синус указанного угла.|
|<xref:System.Math.Sinh%2A>|Возвращает гиперболический синус указанного угла.|
|<xref:System.Math.Sqrt%2A>|Возвращает квадратный корень из указанного числа.|
|<xref:System.Math.Tan%2A>|Возвращает тангенс указанного угла.|
|<xref:System.Math.Tanh%2A>|Возвращает гиперболический тангенс указанного угла.|
|<xref:System.Math.Truncate%2A>|Вычисляет целую часть указанного `Decimal` или `Double` числа.|

В следующей таблице перечислены методы класса <xref:System.Math?displayProperty=nameWithType>, которые не существуют в .NET Framework, но добавлены в .NET Standard или .NET Core:

|Метод .NET|Описание|Доступно в|
|---------------------------|-----------------|-----------|
|<xref:System.Math.Acosh%2A>|Возвращает угол, гиперболический косинус которого равен указанному числу.|Начиная с .NET Core 2,1 и .NET Standard 2,1|
|<xref:System.Math.Asinh%2A>|Возвращает угол, гиперболический синус которого равен указанному числу.|Начиная с .NET Core 2,1 и .NET Standard 2,1|
|<xref:System.Math.Atanh%2A>|Возвращает угол, гиперболический тангенс которого равен указанному числу.|Начиная с .NET Core 2,1 и .NET Standard 2,1|
|<xref:System.Math.BitDecrement%2A>|Возвращает ближайшее самое маленькое значение, которое меньше, чем `x`.|Начиная с .NET Core 3,0|
|<xref:System.Math.BitIncrement%2A>|Возвращает ближайшее самое большое значение, превышающее `x`.|Начиная с .NET Core 3,0|
|<xref:System.Math.Cbrt%2A>|Возвращает кубический корень из указанного числа.|Начиная с .NET Core 2,1 и .NET Standard 2,1|
|<xref:System.Math.Clamp%2A>|Возвращает `value`, ограниченное диапазоном от `min` до `max` включительно.|Начиная с .NET Core 2,0 и .NET Standard 2,1|
|<xref:System.Math.CopySign%2A>|Возвращает значение с величиной `x` и знаком `y`.|Начиная с .NET Core 3,0|
|<xref:System.Math.FusedMultiplyAdd%2A>|Возвращает (x \* y) + z, округленное как одна операция ternary.|Начиная с .NET Core 3,0|
|<xref:System.Math.ILogB%2A>|Возвращает целочисленный логарифм с основанием 2 указанного числа.|Начиная с .NET Core 3,0|
|<xref:System.Math.Log2%2A>|Возвращает логарифм с основанием 2 указанного числа.|Начиная с .NET Core 3,0|
|<xref:System.Math.MaxMagnitude%2A>|Возвращает большую величину из двух чисел двойной точности с плавающей запятой.|Начиная с .NET Core 3,0|
|<xref:System.Math.MinMagnitude%2A>|Возвращает меньшую величину из двух чисел двойной точности с плавающей запятой.|Начиная с .NET Core 3,0|
|<xref:System.Math.ScaleB%2A>|Возвращает значение x \* 2 ^ n, вычисленное эффективно.|Начиная с .NET Core 3,0|

Чтобы использовать эти функции без уточнения, импортируйте <xref:System.Math?displayProperty=nameWithType>ое пространство имен в проект, добавив следующий код в начало исходного файла:

```vb
Imports System.Math
```

## <a name="example---abs"></a>Пример-ABS

В этом примере используется метод <xref:System.Math.Abs%2A> класса <xref:System.Math> для расчета абсолютного значения числа.

```vb
Dim x As Double = Math.Abs(50.3)
Dim y As Double = Math.Abs(-50.3)
Console.WriteLine(x)
Console.WriteLine(y)
' This example produces the following output:
' 50.3
' 50.3
```  

## <a name="example---atan"></a>Пример — Atan

В этом примере используется метод <xref:System.Math.Atan%2A> класса <xref:System.Math> для вычисления значения PI.

```vb
Public Function GetPi() As Double
    ' Calculate the value of pi.
    Return 4.0 * Math.Atan(1.0)
End Function
```

> [!NOTE]
> Класс <xref:System.Math?displayProperty=nameWithType> содержит <xref:System.Math.PI?displayProperty=nameWithType> Константное поле. Его можно использовать вместо вычисления.

## <a name="example---cos"></a>Пример — COS

В этом примере используется метод <xref:System.Math.Cos%2A> класса <xref:System.Math>, чтобы получить косинус угла.

```vb
Public Function Sec(angle As Double) As Double
    ' Calculate the secant of angle, in radians.
    Return 1.0 / Math.Cos(angle)
End Function
```

## <a name="example---exp"></a>Пример — exp

В этом примере используется метод <xref:System.Math.Exp%2A> класса <xref:System.Math>, возвращающего значение e, возведенное в степень.

```vb
Public Function Sinh(angle As Double) As Double
    ' Calculate hyperbolic sine of an angle, in radians.
    Return (Math.Exp(angle) - Math.Exp(-angle)) / 2.0
End Function
```

## <a name="example---log"></a>Пример журнала

В этом примере используется метод <xref:System.Math.Log%2A> класса <xref:System.Math>, чтобы получить натуральный логарифм числа.

```vb
Public Function Asinh(value As Double) As Double
    ' Calculate inverse hyperbolic sine, in radians.
    Return Math.Log(value + Math.Sqrt(value * value + 1.0))
End Function
```

## <a name="example---round"></a>Пример-Round

В этом примере используется метод <xref:System.Math.Round%2A> класса <xref:System.Math> для округления числа до ближайшего целого числа.

```vb
Dim myVar2 As Double = Math.Round(2.8)
Console.WriteLine(myVar2)
' The code produces the following output:
' 3
```

## <a name="example---sign"></a>Пример — подпись

В этом примере используется метод <xref:System.Math.Sign%2A> класса <xref:System.Math> для определения знака числа.

```vb
Dim mySign1 As Integer = Math.Sign(12)
Dim mySign2 As Integer = Math.Sign(-2.4)
Dim mySign3 As Integer = Math.Sign(0)
Console.WriteLine(mySign1)
Console.WriteLine(mySign2)
Console.WriteLine(mySign3)
' The code produces the following output:
' 1
' -1
' 0
```

## <a name="example---sin"></a>Пример — Sin

В этом примере используется метод <xref:System.Math.Sin%2A> класса <xref:System.Math>, чтобы получить синус угла.

```vb
Public Function Csc(angle As Double) As Double
    ' Calculate cosecant of an angle, in radians.
    Return 1.0 / Math.Sin(angle)
End Function
```

## <a name="example---sqrt"></a>Пример. Sqrt

В этом примере используется метод <xref:System.Math.Sqrt%2A> класса <xref:System.Math> для вычисления квадратного корня числа.

```vb
Dim mySqrt1 As Double = Math.Sqrt(4)
Dim mySqrt2 As Double = Math.Sqrt(23)
Dim mySqrt3 As Double = Math.Sqrt(0)
Dim mySqrt4 As Double = Math.Sqrt(-4)
Console.WriteLine(mySqrt1)
Console.WriteLine(mySqrt2)
Console.WriteLine(mySqrt3)
Console.WriteLine(mySqrt4)
' The code produces the following output:
' 2
' 4.79583152331272
' 0
' NaN
```

## <a name="example---tan"></a>Пример — Tan

В этом примере используется метод <xref:System.Math.Tan%2A> класса <xref:System.Math>, чтобы получить тангенс угла.

```vb
Public Function Ctan(angle As Double) As Double
    ' Calculate cotangent of an angle, in radians.
    Return 1.0 / Math.Tan(angle)
End Function
```

## <a name="see-also"></a>См. также:

- <xref:Microsoft.VisualBasic.VBMath.Rnd%2A>
- <xref:Microsoft.VisualBasic.VBMath.Randomize%2A>
- <xref:System.Double.NaN>
- [Производные математические функции](../keywords/derived-math-functions.md)
- [Арифметические операторы](../operators/arithmetic-operators.md)
