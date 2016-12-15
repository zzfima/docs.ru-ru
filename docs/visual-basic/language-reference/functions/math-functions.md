---
title: "Математические функции (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "математические функции, Visual Basic"
  - "арифметические операции, математические функции"
  - "математические подпрограммы"
  - "Atn - функция"
ms.assetid: 4d2d82e7-6924-42fe-a4a7-b4dd5bebbd0c
caps.latest.revision: 23
caps.handback.revision: 23
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Математические функции (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Методы класса <xref:System.Math?displayProperty=fullName> предоставляют тригонометрические, логарифмические и других общих математические функции.  
  
## Заметки  
 В следующей таблице перечислены методы класса <xref:System.Math?displayProperty=fullName>.  Можно использовать их в программе Visual Basic.  
  
|Метод .NET Framework|Описание|  
|--------------------------|--------------|  
|<xref:System.Math.Abs%2A>|Возвращает абсолютное значение числа.|  
|<xref:System.Math.Acos%2A>|Возвращает угол, косинус которого равен указанному числу.|  
|<xref:System.Math.Asin%2A>|Возвращает угол, синус которого равен указанному числу.|  
|<xref:System.Math.Atan%2A>|Возвращает угол, тангенс которого равен указанному числу.|  
|<xref:System.Math.Atan2%2A>|Возвращает угол, тангенс которого равен отношению двух указанных чисел.|  
|<xref:System.Math.BigMul%2A>|Возвращает полный продукт 2 32 разрядных чисел.|  
|<xref:System.Math.Ceiling%2A>|Возвращает наименьшее целое значение, которое меньше или равно указанному `Decimal` или `Double`.|  
|<xref:System.Math.Cos%2A>|Возвращает косинус указанного угла.|  
|<xref:System.Math.Cosh%2A>|Возвращает гиперболический косинус указанного угла.|  
|<xref:System.Math.DivRem%2A>|Возвращает частное 2 32 или 64 разрядного разрядных знаковых целых чисел, а также возвращает остаток в параметре вывода.|  
|<xref:System.Math.Exp%2A>|Возвращает e \(основание натуральных логарифмов\), возведенное в заданную степень.|  
|<xref:System.Math.Floor%2A>|Возвращает наибольшее целое число, которое меньше или равно числу указанного типа `Decimal` или `Double`.|  
|<xref:System.Math.IEEERemainder%2A>|Возвращает остаток от деления, результаты из указанного числа другим указанным количеством.|  
|<xref:System.Math.Log%2A>|Возвращает естественный \( e\) базового логарифм заданного числа или логарифм заданного числа в определенной базе.|  
|<xref:System.Math.Log10%2A>|Возвращает логарифм с основанием 10 указанного числа.|  
|<xref:System.Math.Max%2A>|Возвращает большее 2 чисел.|  
|<xref:System.Math.Min%2A>|Возвращает меньшее из двух чисел.|  
|<xref:System.Math.Pow%2A>|Возвращает указанное число, возведенное в указанную степень.|  
|<xref:System.Math.Round%2A>|Возвращает значение `Decimal` или значение `Double`, округленное до разным значений или с указанным количеством цифр.|  
|<xref:System.Math.Sign%2A>|Возвращает значение типа `Integer`, показывающее знак числа.|  
|<xref:System.Math.Sin%2A>|Возвращает синус указанного угла.|  
|<xref:System.Math.Sinh%2A>|Возвращает гиперболический синус указанного угла.|  
|<xref:System.Math.Sqrt%2A>|Возвращает квадратный корень из указанного числа.|  
|<xref:System.Math.Tan%2A>|Возвращает тангенс указанного угла.|  
|<xref:System.Math.Tanh%2A>|Возвращает гиперболический тангенс указанного угла.|  
|<xref:System.Math.Truncate%2A>|Вычисляет неотъемлемую часть номера, определенных в `Decimal` или `Double`.|  
  
 Для использования этих функций без уточнения импортировать пространство имен <xref:System.Math?displayProperty=fullName> в проект, добавив следующий код в начало файла источника:  
  
```  
Imports System.Math  
```  
  
## Пример  
 В этом примере метод <xref:System.Math.Abs%2A> класса <xref:System.Math> используется для вычисления абсолютного значения числа.  
  
```  
' Returns 50.3.  
Dim MyNumber1 As Double = Math.Abs(50.3)  
' Returns 50.3.  
Dim MyNumber2 As Double = Math.Abs(-50.3)  
```  
  
## Пример  
 В этом примере метод <xref:System.Math.Atan%2A> класса <xref:System.Math> используется для вычисления значения числа пи.  
  
```  
Public Function GetPi() As Double  
    ' Calculate the value of pi.  
    Return 4.0 * Math.Atan(1.0)  
End Function  
```  
  
## Пример  
 В этом примере метод <xref:System.Math.Cos%2A> класса <xref:System.Math> используется для возврата косинуса угла.  
  
```  
Public Function Sec(ByVal angle As Double) As Double  
    ' Calculate the secant of angle, in radians.  
    Return 1.0 / Math.Cos(angle)  
End Function  
```  
  
## Пример  
 В этом примере метод <xref:System.Math.Exp%2A> класса <xref:System.Math> используется для возврата числа e, возведенного в степень.  
  
```  
Public Function Sinh(ByVal angle As Double) As Double  
    ' Calculate hyperbolic sine of an angle, in radians.  
    Return (Math.Exp(angle) - Math.Exp(-angle)) / 2.0  
End Function  
```  
  
## Пример  
 В этом примере метод <xref:System.Math.Log%2A> класса <xref:System.Math> используется для возврата натурального логарифма числа.  
  
```  
Public Function Asinh(ByVal value As Double) As Double  
    ' Calculate inverse hyperbolic sine, in radians.  
    Return Math.Log(value + Math.Sqrt(value * value + 1.0))  
End Function  
```  
  
## Пример  
 В этом примере метод <xref:System.Math.Round%2A> класса <xref:System.Math> используется для округления числа до ближайшего целого числа.  
  
```  
' Returns 3.  
Dim MyVar2 As Double = Math.Round(2.8)  
```  
  
## Пример  
 В этом примере метод <xref:System.Math.Sign%2A> класса <xref:System.Math> используется для определения знака числа.  
  
```  
' Returns 1.  
Dim MySign1 As Integer = Math.Sign(12)  
' Returns -1.  
Dim MySign2 As Integer = Math.Sign(-2.4)  
' Returns 0.  
Dim MySign3 As Integer = Math.Sign(0)  
```  
  
## Пример  
 В этом примере метод <xref:System.Math.Sin%2A> класса <xref:System.Math> используется для возврата синуса угла.  
  
```  
Public Function Csc(ByVal angle As Double) As Double  
    ' Calculate cosecant of an angle, in radians.  
    Return 1.0 / Math.Sin(angle)  
End Function  
```  
  
## Пример  
 В этом примере метод <xref:System.Math.Sqrt%2A> класса <xref:System.Math> используется для вычисления квадратного корня числа.  
  
```  
' Returns 2.  
Dim MySqr1 As Double = Math.Sqrt(4)  
' Returns 4.79583152331272.  
Dim MySqr2 As Double = Math.Sqrt(23)  
' Returns 0.  
Dim MySqr3 As Double = Math.Sqrt(0)  
' Returns NaN (not a number).  
Dim MySqr4 As Double = Math.Sqrt(-4)  
```  
  
## Пример  
 В этом примере метод <xref:System.Math.Tan%2A> класса <xref:System.Math> используется для возврата тангенса угла.  
  
```  
Public Function Ctan(ByVal angle As Double) As Double  
    ' Calculate cotangent of an angle, in radians.  
    Return 1.0 / Math.Tan(angle)  
End Function  
```  
  
## Требования  
 **Класс:** <xref:System.Math>  
  
 **Пространство имен:** <xref:System>  
  
 **Сборка:** mscorlib \(в mscorlib.dll\)  
  
## См. также  
 <xref:Microsoft.VisualBasic.VBMath.Rnd%2A>   
 <xref:Microsoft.VisualBasic.VBMath.Randomize%2A>   
 <xref:System.Double.NaN>   
 [Производные математические функции](../../../visual-basic/language-reference/keywords/derived-math-functions.md)   
 [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)