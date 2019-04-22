---
title: Математические функции (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- math functions, Visual Basic
- arithmetic operations, math functions
- math routines
- Atn function
ms.assetid: 4d2d82e7-6924-42fe-a4a7-b4dd5bebbd0c
ms.openlocfilehash: e5f87a8e367e8c9df65b979fea3781b42ee3ce83
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58824966"
---
# <a name="math-functions-visual-basic"></a>Математические функции (Visual Basic)
Методы <xref:System.Math?displayProperty=nameWithType> предоставляют тригонометрических, логарифмических и иных общих математических функций.  
  
## <a name="remarks"></a>Примечания  
 В следующей таблице перечислены методы <xref:System.Math?displayProperty=nameWithType> класса. Их можно использовать в программе на Visual Basic.  
  
|Метод .NET|Описание|  
|---------------------------|-----------------|  
|<xref:System.Math.Abs%2A>|Возвращает абсолютное значение числа.|  
|<xref:System.Math.Acos%2A>|Возвращает угол, косинус которого равен указанному числу.|  
|<xref:System.Math.Asin%2A>|Возвращает угол, синус которого равен указанному числу.|  
|<xref:System.Math.Atan%2A>|Возвращает угол, тангенс которого равен указанному числу.|  
|<xref:System.Math.Atan2%2A>|Возвращает угол, тангенс которого равен отношению двух указанных чисел.|  
|<xref:System.Math.BigMul%2A>|Возвращает полное произведение двух 32-разрядных чисел.|  
|<xref:System.Math.Ceiling%2A>|Возвращает наименьшее целое число, которое больше или равно указанной `Decimal` или `Double`.|  
|<xref:System.Math.Cos%2A>|Возвращает косинус указанного угла.|  
|<xref:System.Math.Cosh%2A>|Возвращает гиперболический косинус указанного угла.|  
|<xref:System.Math.DivRem%2A>|Возвращает частное двух 32-разрядная или 64-разрядных целых чисел со знаком и возвращает остаток в выходном параметре.|  
|<xref:System.Math.Exp%2A>|Возвращает число e (основание натуральных логарифмов), возведенное в указанную степень.|  
|<xref:System.Math.Floor%2A>|Возвращает наибольшее целое число, которое меньше или равно указанному `Decimal` или `Double` номер.|  
|<xref:System.Math.IEEERemainder%2A>|Возвращает остаток от деления числа на другое указанное число.|  
|<xref:System.Math.Log%2A>|Возвращает натуральный (по основанию e) логарифм указанного числа или логарифм заданного числа с указанным основанием системы счисления.|  
|<xref:System.Math.Log10%2A>|Возвращает логарифм с основанием 10 указанного числа.|  
|<xref:System.Math.Max%2A>|Возвращает большее из двух чисел.|  
|<xref:System.Math.Min%2A>|Возвращает меньшее из двух чисел.|  
|<xref:System.Math.Pow%2A>|Возвращает указанное число, возведенное в указанную степень.|  
|<xref:System.Math.Round%2A>|Возвращает `Decimal` или `Double` значение округляется до ближайшего целого или указанного числа цифр дробной части.|  
|<xref:System.Math.Sign%2A>|Возвращает `Integer` значение, определяющее знак числа.|  
|<xref:System.Math.Sin%2A>|Возвращает синус указанного угла.|  
|<xref:System.Math.Sinh%2A>|Возвращает гиперболический синус указанного угла.|  
|<xref:System.Math.Sqrt%2A>|Возвращает квадратный корень из указанного числа.|  
|<xref:System.Math.Tan%2A>|Возвращает тангенс указанного угла.|  
|<xref:System.Math.Tanh%2A>|Возвращает гиперболический тангенс указанного угла.|  
|<xref:System.Math.Truncate%2A>|Вычисляет целую часть заданного `Decimal` или `Double` номер.|  
  
 Для использования этих функций без квалификации, импортировать <xref:System.Math?displayProperty=nameWithType> пространства имен в проекте, добавив следующий код в начало файла исходного кода:  
  
```vb
Imports System.Math  
```  
  
## <a name="example"></a>Пример  
 В этом примере используется <xref:System.Math.Abs%2A> метод <xref:System.Math> класса, чтобы вычислить абсолютное значение числа.  
  
```vb
' Returns 50.3.  
Dim MyNumber1 As Double = Math.Abs(50.3)  
' Returns 50.3.  
Dim MyNumber2 As Double = Math.Abs(-50.3)  
```  
  
## <a name="example"></a>Пример  
 В этом примере используется <xref:System.Math.Atan%2A> метод <xref:System.Math> класса для вычисления значения числа пи.  
  
```vb
Public Function GetPi() As Double  
    ' Calculate the value of pi.  
    Return 4.0 * Math.Atan(1.0)  
End Function  
```  
  
## <a name="example"></a>Пример  
 В этом примере используется <xref:System.Math.Cos%2A> метод <xref:System.Math> класса для возвращения косинус указанного угла.  
  
```vb
Public Function Sec(ByVal angle As Double) As Double  
    ' Calculate the secant of angle, in radians.  
    Return 1.0 / Math.Cos(angle)  
End Function  
```  
  
## <a name="example"></a>Пример  
 В этом примере используется <xref:System.Math.Exp%2A> метод <xref:System.Math> класса для возвращения e, возведенное в степень.  
  
```vb
Public Function Sinh(ByVal angle As Double) As Double  
    ' Calculate hyperbolic sine of an angle, in radians.  
    Return (Math.Exp(angle) - Math.Exp(-angle)) / 2.0  
End Function  
```  
  
## <a name="example"></a>Пример  
 В этом примере используется <xref:System.Math.Log%2A> метод <xref:System.Math> класса для возвращения натуральный логарифм числа.  
  
```vb
Public Function Asinh(ByVal value As Double) As Double  
    ' Calculate inverse hyperbolic sine, in radians.  
    Return Math.Log(value + Math.Sqrt(value * value + 1.0))  
End Function  
```  
  
## <a name="example"></a>Пример  
 В этом примере используется <xref:System.Math.Round%2A> метод <xref:System.Math> класса для округления до ближайшего целого числа.  
  
```vb
' Returns 3.  
Dim MyVar2 As Double = Math.Round(2.8)  
```  
  
## <a name="example"></a>Пример  
 В этом примере используется <xref:System.Math.Sign%2A> метод <xref:System.Math> класс, чтобы определить знак числа.  
  
```vb
' Returns 1.  
Dim MySign1 As Integer = Math.Sign(12)  
' Returns -1.  
Dim MySign2 As Integer = Math.Sign(-2.4)  
' Returns 0.  
Dim MySign3 As Integer = Math.Sign(0)  
```  
  
## <a name="example"></a>Пример  
 В этом примере используется <xref:System.Math.Sin%2A> метод <xref:System.Math> класса для возвращения синус угла.  
  
```vb
Public Function Csc(ByVal angle As Double) As Double  
    ' Calculate cosecant of an angle, in radians.  
    Return 1.0 / Math.Sin(angle)  
End Function  
```  
  
## <a name="example"></a>Пример  
 В этом примере используется <xref:System.Math.Sqrt%2A> метод <xref:System.Math> класса, для которого требуется вычислить квадратный корень числа.  
  
```vb
' Returns 2.  
Dim MySqr1 As Double = Math.Sqrt(4)  
' Returns 4.79583152331272.  
Dim MySqr2 As Double = Math.Sqrt(23)  
' Returns 0.  
Dim MySqr3 As Double = Math.Sqrt(0)  
' Returns NaN (not a number).  
Dim MySqr4 As Double = Math.Sqrt(-4)  
```  
  
## <a name="example"></a>Пример  
 В этом примере используется <xref:System.Math.Tan%2A> метод <xref:System.Math> класса для возвращения тангенс угла.  
  
```vb
Public Function Ctan(ByVal angle As Double) As Double  
    ' Calculate cotangent of an angle, in radians.  
    Return 1.0 / Math.Tan(angle)  
End Function  
```  
  
## <a name="requirements"></a>Требования  
 **Класс:** <xref:System.Math>  
  
 **Пространство имен:** <xref:System>  
  
 **Сборка:** mscorlib (в mscorlib.dll)  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.VBMath.Rnd%2A>
- <xref:Microsoft.VisualBasic.VBMath.Randomize%2A>
- <xref:System.Double.NaN>
- [Производные математические функции](../../../visual-basic/language-reference/keywords/derived-math-functions.md)
- [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
