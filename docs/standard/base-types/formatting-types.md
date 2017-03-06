---
title: "Типы форматирования"
description: "Типы форматирования"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: cf497639-9f91-45cb-836f-998d1cea2f43
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: dc0693c2e2c034c4c71b4270ef2812be4af72e72
ms.lasthandoff: 03/02/2017

---

# <a name="formatting-types"></a>Типы форматирования

Форматирование — это процесс преобразования экземпляра класса, структуры или значения перечисления в строковое представление. Результирующая строка затем демонстрируется пользователям или десериализуется для последующего восстановления значения с исходным типом данных. Преобразование может быть связано с рядом проблем:

* Внутреннее представление значений необязательно соответствует тому виду, в котором они должны быть представлены пользователям. Например, номер телефона может храниться в форме **8009999999**, которая не отличается удобством для пользователей. Вместо этого номер должен отображаться в следующем виде: **800-999-9999**. Пример подобного форматирования см. в разделе [Строки настраиваемого формата](#custom-format-strings). 

* Иногда порядок преобразования объекта в строковое представление неочевиден. Например, неясно, как должно выглядеть строковое представление объекта класса **Temperature**, представляющего температурные значения, или класса **Person**, представляющего данные о людях. Пример различного форматирования объекта **Temperature** см. в разделе [Строки стандартного формата](#standard-format-strings).

* Для некоторых значений может потребоваться форматирование, учитывающее язык и региональные параметры. Например, в приложении, где числа используются для обозначения денежных сумм, числовые строки должны включать символ текущей валюты, разделители групп (в большинстве случаев они совпадают с разделителями тысяч) и символ-разделитель целой и дробной частей. Пример см. в разделе [Форматирование с учетом языка и региональных параметров с помощью поставщиков формата и интерфейса IFormatProvider](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface). 

* Одно и то же значение может быть необходимо представить в приложении несколькими способами. Например, приложение может представлять элемент перечисления, отображая строковое представление его имени или его базовое значение. Пример различного форматирования члена перечисления [DayOfWeek](xref:System.DayOfWeek) см. в разделе [Строки стандартного формата](#standard-format-strings).

Платформа .NET обеспечивает обширную поддержку форматирования, позволяя разработчикам справиться с описанными проблемами. 

> [!NOTE]
> Форматирование приводит к преобразованию значения определенного типа в его строковое представление. Обратной по отношению к форматированию операцией является анализ. В ходе анализа на основании строкового представления создается экземпляр некоторого типа данных. Дополнительные сведения о преобразовании строк в другие типы данных см. в статье [Анализ строк](parsing-strings.md).

Обзор включает следующие разделы.

* [Форматирование в .NET](#formatting-in-net)

* [Форматирование по умолчанию при помощи метода ToString](#default-formatting-using-the-tostring-method)

* [Переопределение метода ToString](#overriding-the-tostring-method)

* [Метод ToString и строки формата](#the-tostring-method-and-format-strings)

    * [Строки стандартного формата](#standard-format-strings)
    
    * [Строки настраиваемого формата](#custom-format-strings)
    
    * [Строки форматов и типы .NET](#format-strings-and-net-types)
    
* [Форматирование с учетом языка и региональных параметров с помощью поставщиков формата и интерфейса IFormatProvider](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface)

    * [Форматирование числовых значений, зависящее от языка и региональных параметров](#culture-sensitive-formatting-of-numeric-values)
    
    * [Форматирование значений даты и времени, зависящее от языка и региональных параметров](#culture-sensitive-formatting-of-date-and-time-values)
    
* [Интерфейс IFormattable](#the-iformattable-interface)

* [Составное форматирование](#composite-formatting)

* [Настраиваемое форматирование с использованием интерфейса ICustomFormatter](#custom-formatting-with-icustomformatter)

* [Связанные статьи](#related-topics)

* [Ссылки](#reference)

## <a name="formatting-in-net"></a>Форматирование в .NET

Базовый механизм форматирования — это используемая по умолчанию реализация метода [Object.ToString](xref:System.Object.ToString), которая описана ниже в разделе [Форматирование по умолчанию при помощи метода ToString](#default-formatting-using-the-tostring-method). При этом платформа .NET предоставляет несколько способов изменения и расширения имеющихся по умолчанию возможностей форматирования. В число этих требований входят следующие:

* Переопределение метода [Object.ToString](xref:System.Object.ToString), позволяющее определить настраиваемое строковое представление значения объекта. Дополнительные сведения см. ниже в разделе [Переопределение метода ToString](#overriding-the-tostring-method).

* Определение описателей формата, позволяющих использовать несколько видов строкового представления значения объекта. Например, описатель формата "X" в следующем операторе позволяет преобразовать целое число в шестнадцатеричное строковое представление.

  ```csharp
  int integerValue = 60312;
  Console.WriteLine(integerValue.ToString("X"));   // Displays EB98.
  ```

  ```vb
  Dim integerValue As Integer = 60312
  Console.WriteLine(integerValue.ToString("X"))   ' Displays EB98.
  ```
  
  Дополнительные сведения об описателях форматов см. в разделе [Метод ToString и строки формата](#the-tostring-method-and-format-strings).
  
* Использование поставщиков форматирования, позволяющих воспользоваться преимуществами соглашений о форматировании, присущих конкретному языку и региональным параметрам. Например, следующий оператор выводит значение валюты с использованием соглашений о форматировании языка и региональных параметров "en-US". 

  ```csharp
  double cost = 1632.54; 
  Console.WriteLine(cost.ToString("C", 
                  new System.Globalization.CultureInfo("en-US")));   
  // The example displays the following output:
  //       $1,632.54
  ```

  ```vb
  Dim cost As Double = 1632.54
  Console.WriteLine(cost.ToString("C", New System.Globalization.CultureInfo("en-US")))
  ' The example displays the following output:
  '       $1,632.54
  ```
  
  Дополнительные сведения о форматировании при помощи поставщиков форматирования см. в разделе [Форматирование с учетом языка и региональных параметров с помощью поставщиков формата и интерфейса IFormatProvider](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface).  
  
* Реализация интерфейса [IFormattable](xref:System.IFormattable), позволяющая преобразовывать строки с помощью класса [Convert](xref:System.Convert) и использовать составное форматирование. Дополнительные сведения см. в разделе [Интерфейс IFormattable](#the-iformattable-interface).

* Использование составного форматирования, позволяющее внедрить строковую презентацию в состав более крупной строки. Дополнительные сведения см. в разделе [Составное форматирование](#composite-formatting).

* Реализация интерфейсов [ICustomFormatter](xref:System.ICustomFormatter) и [IFormatProvider](xref:System.IFormatProvider), позволяющая создать полноценное настраиваемое решение для форматирования. Дополнительные сведения см. в разделе [Настраиваемое форматирование с использованием интерфейса ICustomFormatter](#custom-formatting-with-icustomformatter).

В следующих подразделах перечисленные методы преобразования объектов в их строковые представления рассматриваются более подробно.

## <a name="default-formatting-using-the-tostring-method"></a>Форматирование по умолчанию при помощи метода ToString

Любой производный от [System.Object](xref:System.Object) тип автоматически наследует метод [ToString](xref:System.Object.ToString) без параметров, по умолчанию возвращающий имя типа. В следующем примере демонстрируется использование метода [ToString](xref:System.Object.ToString) по умолчанию. Здесь определен класс с именем `Automobile`, у которого нет реализации. При создании экземпляра этого класса и вызове его метода [ToString](xref:System.Object.ToString) отображается имя типа. Обратите внимание, что метод [ToString](xref:System.Object.ToString) не вызывается в примере явным образом. Метод [Console.WriteLine(Object)](xref:System.Console.WriteLine(System.Object)) неявно вызывает метод [ToString](xref:System.Object.ToString) объекта, переданного ему в качестве аргумента. 

```csharp
using System;

public class Automobile
{
   // No implementation. All members are inherited from Object.
}

public class Example
{
   public static void Main()
   {
      Automobile firstAuto = new Automobile();
      Console.WriteLine(firstAuto);
   }
}
// The example displays the following output:
//       Automobile
```

```vb 
Public Class Automobile
   ' No implementation. All members are inherited from Object.
End Class

Module Example
   Public Sub Main()
      Dim firstAuto As New Automobile()
      Console.WriteLine(firstAuto)
   End Sub
End Module
' The example displays the following output:
'       Automobile
```

Поскольку производными от [Object](xref:System.Object) являются все типы, кроме интерфейсов, данная функциональность автоматически присутствует в пользовательских классах и структурах. Тем не менее метод [ToString](xref:System.Object.ToString) по умолчанию обладает весьма ограниченной функциональностью: хотя метод позволяет определить имя типа, никаких сведений об экземпляре типа он не предоставляет. Для формирования строкового представления объекта, позволяющего получить сведения о конкретном объекте, следует переопределить метод [ToString](xref:System.Object.ToString).

> [!NOTE]
> Структуры наследуют от типа [ValueType](xref:System.ValueType), который также является производным от [Object](xref:System.Object). Хотя [ValueType](xref:System.ValueType) переопределяет [Object.ToString](xref:System.Object.ToString), его реализация идентична.

## <a name="overriding-the-tostring-method"></a>Переопределение метода ToString

Отображение имени типа зачастую малополезно и не позволяет пользователям типов отличить один экземпляр от другого. Однако метод [ToString](xref:System.Object.ToString) можно переопределить, чтобы он мог возвращать более функциональное представление значения объекта. В следующем примере определяется объект `Temperature`, метод [ToString](xref:System.Object.ToString) которого переопределен и отображает температуру в градусах Цельсия.

```csharp
using System;

public class Temperature
{
   private decimal temp;

   public Temperature(decimal temperature)
   {
      this.temp = temperature;   
   }

   public override string ToString()
   {
      return this.temp.ToString("N1") + "°C";
   }
}

public class Example
{
   public static void Main()
   {
      Temperature currentTemperature = new Temperature(23.6m);
      Console.WriteLine("The current temperature is " +
                        currentTemperature.ToString());
   }
}
// The example displays the following output:
//       The current temperature is 23.6°C.
```

```vb
Public Class Temperature
   Private temp As Decimal

   Public Sub New(temperature As Decimal)
      Me.temp = temperature
   End Sub

   Public Overrides Function ToString() As String
      Return Me.temp.ToString("N1") + "°C"   
   End Function
End Class

Module Example
   Public Sub Main()
      Dim currentTemperature As New Temperature(23.6d)
      Console.WriteLine("The current temperature is " +
                        currentTemperature.ToString())
   End Sub
End Module
' The example displays the following output:
'       The current temperature is 23.6°C.
```

В платформе .NET метод [ToString](xref:System.Object.ToString) переопределен у всех типов-примитивов значений: вместо имени он отображает значение объекта. В следующей таблице показаны переопределения для всех типов-примитивов. Обратите внимание, что большинство переопределенных методов вызывают другую перегрузку метода [ToString](xref:System.Object.ToString) и передают ей описатель формата "G", который задает общий формат типа, и объект [IFormatProvider](xref:System.IFormatProvider), представляющий текущий язык и региональные параметры.

Тип | Переопределение ToString
---- | -----------------
[Boolean](xref:System.Boolean) | Возвращает [Boolean.TrueString](xref:System.Boolean.TrueString) или [Boolean.FalseString](xref:System.Boolean.FalseString).
[Byte](xref:System.Byte) | Вызывает метод `Byte.ToString("G", NumberFormatInfo.CurrentInfo)`, чтобы отформатировать значение [Byte](xref:System.Byte) в соответствии с текущим языком и региональными параметрами.
[Char](xref:System.Char) | Возвращает символ в виде строки.
[DateTime](xref:System.DateTime) | Вызывает метод `DateTime.ToString("G", DatetimeFormatInfo.CurrentInfo)`, чтобы отформатировать значение даты и времени в соответствии с текущим языком и региональными параметрами. 
[Decimal](xref:System.Decimal) | Вызывает метод `Decimal.ToString("G", NumberFormatInfo.CurrentInfo)`, чтобы отформатировать значение [Decimal](xref:System.Decimal) в соответствии с текущим языком и региональными параметрами.
[Double](xref:System.Double) | Вызывает метод `Double.ToString("G", NumberFormatInfo.CurrentInfo)`, чтобы отформатировать значение [Double](xref:System.Double) в соответствии с текущим языком и региональными параметрами.
[Int16](xref:System.Int16) | Вызывает метод `Int16.ToString("G", NumberFormatInfo.CurrentInfo)`, чтобы отформатировать значение [Int16](xref:System.Int16) в соответствии с текущим языком и региональными параметрами.
[Int32](xref:System.Int32) | Вызывает метод `Int16.ToString("G", NumberFormatInfo.CurrentInfo)`, чтобы отформатировать значение [Int32](xref:System.Int32) в соответствии с текущим языком и региональными параметрами.
[Int64](xref:System.Int64) | Вызывает метод `Int16.ToString("G", NumberFormatInfo.CurrentInfo)`, чтобы отформатировать значение [Int64](xref:System.Int64) в соответствии с текущим языком и региональными параметрами.
[SByte](xref:System.SByte) | Вызывает метод `Int16.ToString("G", NumberFormatInfo.CurrentInfo)`, чтобы отформатировать значение [SByte](xref:System.SByte) | в соответствии с текущим языком и региональными параметрами.
[Single](xref:System.Single) | Вызывает метод `Int16.ToString("G", NumberFormatInfo.CurrentInfo)`, чтобы отформатировать значение [Single](xref:System.Single) в соответствии с текущим языком и региональными параметрами.
[UInt32](xref:System.UInt32) | Вызывает метод `Int16.ToString("G", NumberFormatInfo.CurrentInfo)`, чтобы отформатировать значение [UInt32](xref:System.UInt32) в соответствии с текущим языком и региональными параметрами.
[UInt32](xref:System.UInt32) | Вызывает метод `Int16.ToString("G", NumberFormatInfo.CurrentInfo)`, чтобы отформатировать значение [UInt32](xref:System.UInt32) в соответствии с текущим языком и региональными параметрами.
[UInt64](xref:System.UInt64) | Вызывает метод `Int16.ToString("G", NumberFormatInfo.CurrentInfo)`, чтобы отформатировать значение [UInt64](xref:System.UInt64) в соответствии с текущим языком и региональными параметрами.

## <a name="the-tostring-method-and-format-strings"></a>Метод ToString и строки формата

Использовать метод [ToString](xref:System.Object.ToString) по умолчанию или перегрузку [ToString](xref:System.Object.ToString) удобно, если у объекта имеется однозначное строковое представление. Тем не менее зачастую значение объекта может иметь несколько представлений. Например, температура может выражаться в градусах по шкале Фаренгейта, Цельсия или Кельвина. Аналогично, целое число 10 можно представить различными способами, включая 10, 10.0, 1.0e01 или $10.00.

Для реализации нескольких строковых представлений одного значения в платформе .NET используются строки формата. Строка формата содержит один или несколько предопределенных описателей формата, представляющих собой одиночные символы или группы символов, указывающие, как метод [ToString](xref:System.Object.ToString) должен форматировать вывод. Строка формата передается в качестве параметра методу [ToString](xref:System.Object.ToString) объекта и определяет, как должно выглядеть строковое представление его значения.

Все числовые типы, типы даты и времени, а также перечисления в составе платформы .NET поддерживают предопределенный набор описателей формата. Строки формата также можно использовать для определения разнообразных строковых представлений прикладных пользовательских типов данных.

### <a name="standard-format-strings"></a>Строки стандартного формата

Строка стандартного формата содержит один описатель формата. Это алфавитный символ, определяющий строковое представление объекта, к которому он применяется. Также строка формата может содержать необязательный описатель точности, определяющий, сколько цифр отображается в результирующей строке. Если описатель точности не указан или не поддерживается, описатель стандартного формата будет эквивалентен строке стандартного формата. 

В платформе .NET определяется набор описателей стандартного формата для всех числовых типов, типов даты и времени, а также для всех типов перечислений. Например, все эти категории поддерживают описатель стандартного формата "G", который определяет общее строковое представление значения соответствующего типа.

Строки стандартного формата для типов перечислений напрямую определяют строковое представление значения. От строки формата, переданной в метод [ToString](xref:System.Object.ToString) значения перечисления, зависит, будет ли оно представлено своим строковым именем (описатели формата "G" и "F"), базовым целочисленным значением (описатель формата "D") или шестнадцатеричным значением (описатель формата "X"). В следующем примере демонстрируется использование строк стандартного формата для форматирования значения перечисления [DayOfWeek](xref:System.DayOfWeek). 

```csharp
DayOfWeek thisDay = DayOfWeek.Monday;
string[] formatStrings = {"G", "F", "D", "X"};

foreach (string formatString in formatStrings)
   Console.WriteLine(thisDay.ToString(formatString));
// The example displays the following output:
//       Monday
//       Monday
//       1
//       00000001
```

```vb
Dim thisDay As DayOfWeek = DayOfWeek.Monday
Dim formatStrings() As String = {"G", "F", "D", "X"}

For Each formatString As String In formatStrings
   Console.WriteLine(thisDay.ToString(formatString))
Next
' The example displays the following output:
'       Monday
'       Monday
'       1
'       00000001
```

Информацию о строках форматов перечисления см. в статье [Строки форматов перечисления](enumeration-format.md).

Строки стандартного формата для числовых типов обычно задают результирующую строку, точный вид которой зависит от значения одного или нескольких свойств. Например, описатель формата "C" форматирует число в виде значения валюты. При вызове метода [ToString](xref:System.Object.ToString) с описателем формата "C" в качестве единственного параметра для определения строкового представления числового значения используются следующие свойства объекта [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) для текущего языка и региональных параметров:

* Свойство [CurrencySymbol](xref:System.Globalization.NumberFormatInfo.CurrencySymbol), определяющее обозначение денежной единицы для текущего языка и региональных параметров.

* Свойство [CurrencyNegativePattern](xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern) или [CurrencyPositivePattern](xref:System.Globalization.NumberFormatInfo.CurrencyPositivePattern), возвращающее целое число, от которого зависят указанные далее моменты. 

    * Положение символа валюты.
    
    * Обозначение отрицательных значений: отрицательный знак в начале, отрицательный знак в конце или круглые скобки.
    
    * Наличие пробела между числовым значением и символом валюты.
    
* Свойство [CurrencyDecimalDigits](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits), определяющее число цифр дробной части в результирующей строке.

* Свойство [CurrencyDecimalSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator), определяющее символ-разделитель целой и дробной частей в результирующей строке.

* Свойство [CurrencyGroupSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator), определяющее символ-разделитель групп.

* Свойство [CurrencyGroupSizes](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSizes), определяющее число цифр в каждой из групп слева от разделителя целой и дробной частей.

* Свойство [NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign), задающее отрицательный знак, который используется в случаях, если скобки не применяются для обозначения отрицательных значений в результирующей строке.

Кроме того, строки числового формата могут содержать описатель точности. Смысл этого описателя зависит от строки формата, в которой он используется, но обычно он задает общее число цифр в результирующей строке или число цифр в дробной части. В следующем примере используется строка стандартного числового формата с описателем точности ("X4"), что позволяет сформировать строковое значение из четырех шестидесятеричных цифр.

```csharp
byte[] byteValues = { 12, 163, 255 };
foreach (byte byteValue in byteValues)
   Console.WriteLine(byteValue.ToString("X4"));
// The example displays the following output:
//       000C
//       00A3
//       00FF
```

```vb
Dim byteValues() As Byte = { 12, 163, 255 }
For Each byteValue As Byte In byteValues
   Console.WriteLine(byteValue.ToString("X4"))
Next
' The example displays the following output:
'       000C
'       00A3
'       00FF
```

Подробности о строках стандартных числовых форматов см. в статье [Строки стандартных числовых форматов](standard-numeric.md). 

Строки стандартного формата для значений даты и времени — это псевдонимы строк настраиваемого формата, которые хранятся в конкретном свойстве [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo). Например, вызов метода [ToString](xref:System.Object.ToString) применительно к значению даты и времени с описателем формата "D" приведет к отображению даты и времени с помощью настраиваемой строки формата, хранящейся в свойстве [DateTimeFormatInfo.LongDatePattern](xref:System.Globalization.DateTimeFormatInfo.LongDatePattern) для текущего языка и региональных параметров. (Дополнительные сведения о строках настраиваемого формата см. в разделе [Строки настраиваемого формата](#custom-format-strings).) Данная связь показана в следующем примере.

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      DateTime date1 = new DateTime(2017, 6, 30);
      Console.WriteLine("D Format Specifier:     {0:D}", date1);
      string longPattern = CultureInfo.CurrentCulture.DateTimeFormat.LongDatePattern;
      Console.WriteLine("'{0}' custom format string:     {1}", 
                        longPattern, date1.ToString(longPattern));
   }
}
// The example displays the following output when run on a system whose
// current culture is en-US:
//    D Format Specifier:     Tuesday, June 30, 2017
//    'dddd, MMMM dd, yyyy' custom format string:     Tuesday, June 30, 2017
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim date1 As Date = #6/30/2009#
      Console.WriteLine("D Format Specifier:     {0:D}", date1)
      Dim longPattern As String = CultureInfo.CurrentCulture.DateTimeFormat.LongDatePattern
      Console.WriteLine("'{0}' custom format string:     {1}", _
                        longPattern, date1.ToString(longPattern))
   End Sub
End Module
' The example displays the following output when run on a system whose
' current culture is en-US:
'    D Format Specifier:     Tuesday, June 30, 2009
'    'dddd, MMMM dd, yyyy' custom format string:     Tuesday, June 30, 2009
```

Дополнительные сведения о строках стандартных форматов даты и времени см. в статье [Строки стандартных форматов даты и времени](standard-datetime.md).

Строки стандартного формата также можно использовать для определения строкового представления прикладного объекта, формируемого с помощью метода `ToString(String)` такого объекта. Можно определить конкретные описатели стандартного формата, поддерживаемые объектом, а также решить, будут ли они зависеть от регистра символов. Реализация метода `ToString(String)` должна отвечать следующим условиям:

* Должен поддерживаться описатель формата "G", отвечающий за представление обычного или общего формата объекта. Перегрузка метода `ToString` объекта, не имеющая параметров, должна вызывать его перегрузку `ToString(String)`, передавая ей строку стандартного формата "G".

* Должен поддерживаться описатель формата, равный пустой ссылке. Описатель формата, равный пустой ссылке, должен рассматриваться как эквивалент описателя формата "G".

Например, во внутреннем представлении класса `Temperature` температура может храниться в градусах Цельсия, а для представления значения объекта `Temperature` в градусах Цельсия, Фаренгейта или Кельвина могут использоваться различные описатели формата. Ниже приведен пример.

```csharp
using System;

public class Temperature
{
   private decimal m_Temp;

   public Temperature(decimal temperature)
   {
      this.m_Temp = temperature;
   }

   public decimal Celsius
   {
      get { return this.m_Temp; }
   }

   public decimal Kelvin
   {
      get { return this.m_Temp + 273.15m; }   
   }

   public decimal Fahrenheit
   {
      get { return Math.Round(((decimal) (this.m_Temp * 9 / 5 + 32)), 2); }
   }

   public override string ToString()
   {
      return this.ToString("C");
   }

   public string ToString(string format)
   {  
      // Handle null or empty string.
      if (String.IsNullOrEmpty(format)) format = "C";
      // Remove spaces and convert to uppercase.
      format = format.Trim().ToUpperInvariant();      

      // Convert temperature to Fahrenheit and return string.
      switch (format)
      {
         // Convert temperature to Fahrenheit and return string.
         case "F":
            return this.Fahrenheit.ToString("N2") + " °F";
         // Convert temperature to Kelvin and return string.
         case "K":
            return this.Kelvin.ToString("N2") + " K";
         // return temperature in Celsius.
         case "G":
         case "C":
            return this.Celsius.ToString("N2") + " °C";
         default:
            throw new FormatException(String.Format("The '{0}' format string is not supported.", format));
      }      
   }
}

public class Example
{
   public static void Main()
   {
      Temperature temp1 = new Temperature(0m);
      Console.WriteLine(temp1.ToString());
      Console.WriteLine(temp1.ToString("G"));
      Console.WriteLine(temp1.ToString("C"));
      Console.WriteLine(temp1.ToString("F"));
      Console.WriteLine(temp1.ToString("K"));

      Temperature temp2 = new Temperature(-40m);
      Console.WriteLine(temp2.ToString());
      Console.WriteLine(temp2.ToString("G"));
      Console.WriteLine(temp2.ToString("C"));
      Console.WriteLine(temp2.ToString("F"));
      Console.WriteLine(temp2.ToString("K"));

      Temperature temp3 = new Temperature(16m);
      Console.WriteLine(temp3.ToString());
      Console.WriteLine(temp3.ToString("G"));
      Console.WriteLine(temp3.ToString("C"));
      Console.WriteLine(temp3.ToString("F"));
      Console.WriteLine(temp3.ToString("K"));

      Console.WriteLine(String.Format("The temperature is now {0:F}.", temp3));
   }
}
// The example displays the following output:
//       0.00 °C
//       0.00 °C
//       0.00 °C
//       32.00 °F
//       273.15 K
//       -40.00 °C
//       -40.00 °C
//       -40.00 °C
//       -40.00 °F
//       233.15 K
//       16.00 °C
//       16.00 °C
//       16.00 °C
//       60.80 °F
//       289.15 K
//       The temperature is now 16.00 °C.
```

```vb
Public Class Temperature
   Private m_Temp As Decimal

   Public Sub New(temperature As Decimal)
      Me.m_Temp = temperature
   End Sub

   Public ReadOnly Property Celsius() As Decimal
      Get
         Return Me.m_Temp
      End Get   
   End Property

   Public ReadOnly Property Kelvin() As Decimal
      Get
         Return Me.m_Temp + 273.15d   
      End Get
   End Property

   Public ReadOnly Property Fahrenheit() As Decimal
      Get
         Return Math.Round(CDec(Me.m_Temp * 9 / 5 + 32), 2)
      End Get      
   End Property

   Public Overrides Function ToString() As String
      Return Me.ToString("C")
   End Function

   Public Overloads Function ToString(format As String) As String  
      ' Handle null or empty string.
      If String.IsNullOrEmpty(format) Then format = "C"
      ' Remove spaces and convert to uppercase.
      format = format.Trim().ToUpperInvariant()      

      Select Case format
         Case "F"
           ' Convert temperature to Fahrenheit and return string.
            Return Me.Fahrenheit.ToString("N2") & " °F"
         Case "K"
            ' Convert temperature to Kelvin and return string.
            Return Me.Kelvin.ToString("N2") & " K"
         Case "C", "G"
            ' Return temperature in Celsius.
            Return Me.Celsius.ToString("N2") & " °C"
         Case Else
            Throw New FormatException(String.Format("The '{0}' format string is not supported.", format))
      End Select      
   End Function
End Class

Public Module Example
   Public Sub Main()
      Dim temp1 As New Temperature(0d)
      Console.WriteLine(temp1.ToString())
      Console.WriteLine(temp1.ToString("G"))
      Console.WriteLine(temp1.ToString("C"))
      Console.WriteLine(temp1.ToString("F"))
      Console.WriteLine(temp1.ToString("K"))

      Dim temp2 As New Temperature(-40d)
      Console.WriteLine(temp2.ToString())
      Console.WriteLine(temp2.ToString("G"))
      Console.WriteLine(temp2.ToString("C"))
      Console.WriteLine(temp2.ToString("F"))
      Console.WriteLine(temp2.ToString("K"))

      Dim temp3 As New Temperature(16d)
      Console.WriteLine(temp3.ToString())
      Console.WriteLine(temp3.ToString("G"))
      Console.WriteLine(temp3.ToString("C"))
      Console.WriteLine(temp3.ToString("F"))
      Console.WriteLine(temp3.ToString("K"))

      Console.WriteLine(String.Format("The temperature is now {0:F}.", temp3))
   End Sub
End Module
' The example displays the following output:
'       0.00 °C
'       0.00 °C
'       0.00 °C
'       32.00 °F
'       273.15 K
'       -40.00 °C
'       -40.00 °C
'       -40.00 °C
'       -40.00 °F
'       233.15 K
'       16.00 °C
'       16.00 °C
'       16.00 °C
'       60.80 °F
'       289.15 K
'       The temperature is now 16.00 °C.
```

### <a name="custom-format-strings"></a>Строки настраиваемого формата

Помимо строк стандартного формата, в платформе .NET для числовых значений и значений даты и времени определяются строки настраиваемого формата. Строка настраиваемого формата состоит из одного или нескольких описателей настраиваемого формата, описывающих строковое представление значения. Например, строка настраиваемого формата даты и времени, заданная как "yyyy/mm/dd hh:mm:ss.ffff t zzz", преобразует дату в строковое представления вида "2008/11/15 07:45:00.0000 P -08:00" для языка и региональных параметров "en-US". Аналогично строка настраиваемого формата "0000" приведет к преобразованию целочисленного значения 12 в строку "0012". Полный список строк настраиваемых форматов см. в статьях [Строки настраиваемых форматов даты и времени](custom-datetime.md) и [Строки настраиваемых числовых форматов](custom-numeric.md).

Если строка формата состоит из одного описателя настраиваемого формата, то перед ним должен стоять символ процента (%), чтобы его можно было отличить от описателя стандартного формата. В следующем примере описатель настраиваемого формата "М" используется для вывода одно- или двухзначного числа месяца для определенной даты.

```csharp
DateTime date1 = new DateTime(2009, 9, 8);
Console.WriteLine(date1.ToString("%M"));       
// Displays 9
```

```vb
Dim date1 As Date = #09/08/2009#
Console.WriteLine(date1.ToString("%M"))      ' Displays 9
```

Многие строки стандартного формата для значений даты и времени являются псевдонимами для строк настраиваемого формата, определяемых свойствами объекта [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo). Строки настраиваемого формата также позволяют добиться значительной гибкости в реализации прикладного форматирования числовых значений или значений даты и времени. Можно определить собственные настраиваемые результирующие строки для числовых значений и значений даты и времени, объединив несколько описателей настраиваемого формата в одной строке настраиваемого формата. В следующем примере определяется строка настраиваемого формата, отображающая день недели в скобках после названия месяца, числа и года.

```csharp
string customFormat = "MMMM dd, yyyy (dddd)";
DateTime date1 = new DateTime(2009, 8, 28);
Console.WriteLine(date1.ToString(customFormat));   
// The example displays the following output if run on a system
// whose language is English:
//       August 28, 2009 (Friday) 
```

```vb
Dim customFormat As String = "MMMM dd, yyyy (dddd)"
Dim date1 As Date = #8/28/2009#
Console.WriteLine(date1.ToString(customFormat))   
' The example displays the following output if run on a system
' whose language is English:
'       August 28, 2009 (Friday) 
```

В следующем примере определяется строка настраиваемого формата, которая отображает значение [Int64](xref:System.Int64) как стандартный&7;-значный американский номер телефона вместе с кодом города. 

```csharp
using System;

public class Example
{
   public static void Main()
   {
      long number = 8009999999;
      string fmt = "000-000-0000";
      Console.WriteLine(number.ToString(fmt));
   }
}
// The example displays the following output:
//        800-999-9999
```

```vb
Module Example
   Public Sub Main()
      Dim number As Long = 8009999999
      Dim fmt As String = "000-000-0000"
      Console.WriteLine(number.ToString(fmt))
   End Sub
End Module
' The example displays the following output:

' The example displays the following output:
'       800-999-9999
```

Хотя строк стандартного формата обычно достаточно для выполнения большинства задач форматирования прикладных типов, для форматирования пользовательских типов также можно определять описатели настраиваемого формата. 

### <a name="format-strings-and-net-types"></a>Строки форматов и типы .NET

Все числовые типы (то есть [Byte](xref:System.Byte), [Decimal](xref:System.Decimal), [Double](xref:System.Double), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [Single](xref:System.Single), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), [UInt64](xref:System.UInt64) и [BigInteger](xref:System.Numerics.BigInteger)), а также [DateTime](xref:System.DateTime), [DateTimeOffset](xref:System.DateTimeOffset), [TimeSpan](xref:System.TimeSpan), [Guid](xref:System.Guid) и все типы перечислений поддерживают форматирование с помощью строк форматов. Сведения о конкретных строках форматов, поддерживаемых каждым типом, см. в следующих разделах. 

Заголовок | Определение
----- | ----------
[Строки стандартных числовых форматов](standard-numeric.md) | Описание строк стандартного формата, позволяющих создавать общеупотребимые строковые представления числовых значений. 
[Строки настраиваемых числовых форматов](custom-numeric.md) | Описание строк настраиваемого формата, позволяющих создавать прикладные строковые представления числовых значений.
[Строки стандартных форматов даты и времени](standard-datetime.md) | Описание строк стандартного формата, позволяющих создавать общеупотребимые строковые представления значений [DateTime](xref:System.DateTime).
[Строки настраиваемых форматов даты и времени](custom-datetime.md) | Описание строк настраиваемого формата, позволяющих создавать характерные для приложений форматы для значений [DateTime](xref:System.DateTime).
[Строки стандартного формата TimeSpan](standard-timespan.md) | Описание строк стандартного формата, позволяющих создавать общеупотребимые строковые представления интервалов времени.
[Строки настраиваемого формата TimeSpan](custom-timespan.md) | Описание строк настраиваемого формата, позволяющих создавать прикладные строковые представления интервалов времени.
[Строки форматов перечисления](enumeration-format.md) | Описание строк стандартного формата, используемых для создания строковых представлений значений перечислений.
[Guid.ToString(String)](xref:System.Guid.ToString(System.String)) | Описание строк стандартного формата для значений [Guid](xref:System.Guid).

## <a name="culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface"></a>Форматирование с учетом языка и региональных параметров с помощью поставщиков формата и интерфейса IFormatProvider

Хотя описатели формата позволяют настраивать форматирование объектов, для формирования осмысленного строкового представления объектов зачастую требуется дополнительная информация, связанная с форматированием. Например, при форматировании числового значения в формате валюты с помощью строки стандартного формата "C" или строки настраиваемого формата "$ #,#.00" для включения в отформатированную строку должен быть известен нужный символ валюты, разделитель групп, а также разделитель целой и дробной частей. В платформе .NET подобные дополнительные сведения предоставляются с помощью интерфейса [IFormatProvider](xref:System.IFormatProvider), передаваемого в качестве параметра одной или нескольких перегрузок метода `ToString` для числовых типов и типов даты и времени. Реализации [IFormatProvider](xref:System.IFormatProvider) используются в .NET для поддержки форматирования с учетом языка и региональных параметров. В следующем примере показано, как меняется строковое представление объекта при его форматировании с использованием трех разных объектов [IFormatProvider](xref:System.IFormatProvider), представляющих разные язык и региональные параметры.

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      decimal value = 1603.42m;
      Console.WriteLine(value.ToString("C3", new CultureInfo("en-US")));
      Console.WriteLine(value.ToString("C3", new CultureInfo("fr-FR")));
      Console.WriteLine(value.ToString("C3", new CultureInfo("de-DE")));
   }
}
// The example displays the following output:
//       $1,603.420
//       1 603,420 €
//       1.603,420 €
```

```vb
Imports System.Globalization

Public Module Example
   Public Sub Main()
      Dim value As Decimal = 1603.42d
      Console.WriteLine(value.ToString("C3", New CultureInfo("en-US")))
      Console.WriteLine(value.ToString("C3", New CultureInfo("fr-FR")))
      Console.WriteLine(value.ToString("C3", New CultureInfo("de-DE")))
   End Sub
End Module
' The example displays the following output:
'       $1,603.420
'       1 603,420 €
'       1.603,420 €
```

Интерфейс [IFormatProvider](xref:System.IFormatProvider) включает один метод [GetFormat(Type)](xref:System.IFormatProvider.GetFormat(System.Type)), имеющий один параметр, задающий тип объекта, который предоставляет сведения о форматировании. Если метод может предоставить объект указанного типа, то он его возвращает. В противном случае метод возвращает пустую ссылку.

[IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) — это метод обратного вызова. При вызове перегрузки метода `ToString`, имеющей параметр [IFormatProvider](xref:System.IFormatProvider), вызывается метод [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) соответствующего объекта [IFormatProvider](xref:System.IFormatProvider). Метод [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) должен вернуть в метод `ToString` объект, способный предоставить необходимые сведения о форматировании и соответствующий параметру *formatType*. 

Многие методы форматирования и преобразования строк имеют параметр типа [IFormatProvider](xref:System.IFormatProvider), но во многих случаях значение параметра игнорируется при вызове метода. В следующей таблице перечислены некоторые методы форматирования, использующие этот параметр. Для каждого метода также указывается тип объекта [Type](xref:System.Type), передаваемого в метод [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)). 

Метод | Тип параметра *formatType*
------ | ------------------------------
Метод `ToString` для числовых типов | [System.Globalization.NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)
Метод `ToString` для типов даты и времени | [System.Globalization.DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)
[String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) | [System.ICustomFormatter](xref:System.ICustomFormatter)
[StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)) | [System.ICustomFormatter](xref:System.ICustomFormatter)

В составе платформы .NET есть три класса, реализующих интерфейс [IFormatProvider](xref:System.IFormatProvider). 

* [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo): класс, предоставляющий сведения о форматировании значений даты и времени для конкретного языка и региональных параметров. Реализация метода [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) в этом классе возвращает его экземпляр.

* [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo): класс, предоставляющий сведения о форматировании числовых значений для конкретного языка и региональных параметров. Реализация метода [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) в этом классе возвращает его экземпляр.

* [CultureInfo](xref:System.Globalization.CultureInfo). Реализация метода [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) в этом классе возвращает объект [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), предоставляющий сведения о форматировании числовых значений, либо объект [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), предоставляющий сведения о форматировании значений даты и времени. 

Также можно реализовать пользовательский поставщик форматирования, позволяющий заменить любой из этих классов. При этом пользовательская реализация метода `GetFormat`, рассчитанная на предоставление сведений о форматировании для метода `ToString`, должна возвращать объект одного из типов, перечисленных в приведенной выше таблице.

### <a name="culture-sensitive-formatting-of-numeric-values"></a>Форматирование числовых значений, зависящее от языка и региональных параметров

По умолчанию форматирование числовых значений зависит от языка и региональных параметров. Если не указать язык и региональные параметры при вызове метода форматирования, используются соглашения о форматировании текущего языка и региональных параметров. Это продемонстрировано в следующем примере, который изменяет текущие язык и региональные параметры четыре раза, а затем вызывает метод [Decimal.ToString(String)](xref:System.Decimal.ToString(System.String)). В каждом случае результирующая строка отражает соглашения о форматировании текущих языка и региональных параметров. Это происходит потому, что методы `ToString` и `ToString(String)` создают оболочки для вызовов метода `ToString(String, IFormatProvider)` каждого числового типа. 

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string[] cultureNames = { "en-US", "fr-FR", "es-MX", "de-DE" };
      Decimal value = 1043.17m;

      foreach (var cultureName in cultureNames) {
         // Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName);
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name);
         Console.WriteLine(value.ToString("C2"));
         Console.WriteLine();
      }   
   }
}
// The example displays the following output:
//       The current culture is en-US
//       $1,043.17
//       
//       The current culture is fr-FR
//       1 043,17 €
//       
//       The current culture is es-MX
//       $1,043.17
//       
//       The current culture is de-DE
//       1.043,17 €
```

```vb
Imports System.Globalization
Imports System.Threading 

Module Example
   Public Sub Main()
      Dim cultureNames() As String = { "en-US", "fr-FR", "es-MX", "de-DE" }
      Dim value As Decimal = 1043.17d 

      For Each cultureName In cultureNames
         ' Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName)
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name)
         Console.WriteLine(value.ToString("C2"))
         Console.WriteLine()
      Next                  
   End Sub
End Module
' The example displays the following output:
'       The current culture is en-US
'       $1,043.17
'       
'       The current culture is fr-FR
'       1 043,17 €
'       
'       The current culture is es-MX
'       $1,043.17
'       
'       The current culture is de-DE
'       1.043,17 €
```

Отформатировать числовое значение для определенных языка и региональных параметров также можно путем вызова перегрузки метода `ToString`, которая имеет параметр *provider*, и передачи ей одного из следующих объектов: 

* Объекта [CultureInfo](xref:System.Globalization.CultureInfo), представляющего язык и региональные параметры, соглашения о форматировании которых требуется использовать. Его метод [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) возвращает значение свойства [CultureInfo.NumberFormat](xref:System.Globalization.CultureInfo.NumberFormat), которое является объектом [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), предоставляющим сведения о форматировании в соответствии с языком и региональными параметрами для числовых значений.

* Объекта [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), определяющего соглашения о форматировании для используемых языка и региональных параметров. Метод [GetFormat](xref:System.Globalization.NumberFormatInfo.GetFormat(System.Type)) этого класса возвращает экземпляр его самого.

В следующем примере объекты [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), представляющие "Английский (США)" и "Английский (Великобритания)" язык и региональные параметры, а также "Французский" и "Русский" нейтральные языки и региональные параметры, используются для форматирования числа с плавающей запятой.

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {                                                                                                    
      Double value = 1043.62957;
      string[] cultureNames = { "en-US", "en-GB", "ru", "fr" };

      foreach (var name in cultureNames) {
         NumberFormatInfo nfi = CultureInfo.CreateSpecificCulture(name).NumberFormat;
         Console.WriteLine("{0,-6} {1}", name + ":", value.ToString("N3", nfi));
      }   
   }
}
// The example displays the following output:
//       en-US: 1,043.630
//       en-GB: 1,043.630
//       ru:    1 043,630
//       fr:    1 043,630
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim value As Double = 1043.62957
      Dim cultureNames() As String = { "en-US", "en-GB", "ru", "fr" }

      For Each name In cultureNames
         Dim nfi As NumberFormatInfo = CultureInfo.CreateSpecificCulture(name).NumberFormat
         Console.WriteLine("{0,-6} {1}", name + ":", value.ToString("N3", nfi))
      Next   
   End Sub
End Module
' The example displays the following output:
'       en-US: 1,043.630
'       en-GB: 1,043.630
'       ru:    1 043,630
'       fr:    1 043,630
```

### <a name="culture-sensitive-formatting-of-date-and-time-values"></a>Форматирование значений даты и времени, зависящее от языка и региональных параметров

По умолчанию форматирование значений даты и времени зависит от языка и региональных параметров. Если не указать язык и региональные параметры при вызове метода форматирования, используются соглашения о форматировании текущего языка и региональных параметров. Это продемонстрировано в следующем примере, который изменяет текущие язык и региональные параметры четыре раза, а затем вызывает метод [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String)). В каждом случае результирующая строка отражает соглашения о форматировании текущих языка и региональных параметров. Это происходит потому, что методы [DateTime.ToString()](xref:System.DateTime.ToString), [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String)), [DateTimeOffset.ToString()](xref:System.DateTimeOffset.ToString(System.String)) и [DateTimeOffset.ToString(String)](xref:System.DateTimeOffset.ToString(System.String)) создают оболочки для вызовов методов [DateTime.ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) и [DateTimeOffset.ToString(String, IFormatProvider)](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)).

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string[] cultureNames = { "en-US", "fr-FR", "es-MX", "de-DE" };
      DateTime dateToFormat = new DateTime(2012, 5, 28, 11, 30, 0);

      foreach (var cultureName in cultureNames) {
         // Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName);
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name);
         Console.WriteLine(dateToFormat.ToString("F"));
         Console.WriteLine();
      }   
   }
}
// The example displays the following output:
//       The current culture is en-US
//       Monday, May 28, 2012 11:30:00 AM
//       
//       The current culture is fr-FR
//       lundi 28 mai 2012 11:30:00
//       
//       The current culture is es-MX
//       lunes, 28 de mayo de 2012 11:30:00 a.m.
//       
//       The current culture is de-DE
//       Montag, 28. Mai 2012 11:30:00
```

```vb
Imports System.Globalization
Imports System.Threading 

Module Example
   Public Sub Main()
      Dim cultureNames() As String = { "en-US", "fr-FR", "es-MX", "de-DE" }
      Dim dateToFormat As Date = #5/28/2012 11:30AM#

      For Each cultureName In cultureNames
         ' Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName)
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name)
         Console.WriteLine(dateToFormat.ToString("F"))
         Console.WriteLine()
      Next                  
   End Sub
End Module
' The example displays the following output:
'       The current culture is en-US
'       Monday, May 28, 2012 11:30:00 AM
'       
'       The current culture is fr-FR
'       lundi 28 mai 2012 11:30:00
'       
'       The current culture is es-MX
'       lunes, 28 de mayo de 2012 11:30:00 a.m.
'       
'       The current culture is de-DE
'       Montag, 28. Mai 2012 11:30:00
```

Форматировать значения даты и времени для определенных языка и региональных параметров также можно путем вызова перегрузки методов [DateTime.ToString](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) или [DateTimeOffset.ToString](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)), которая имеет параметр provider, и передачи ей одного из следующих объектов: 

* Объекта [CultureInfo](xref:System.Globalization.CultureInfo), представляющего язык и региональные параметры, соглашения о форматировании которых требуется использовать. Его метод [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) возвращает значение свойства [CultureInfo.NumberFormat](xref:System.Globalization.CultureInfo.NumberFormat), которое является объектом [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), предоставляющим сведения о форматировании в соответствии с языком и региональными параметрами для числовых значений.

* Объекта [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), определяющего соглашения о форматировании для используемых языка и региональных параметров. Метод [GetFormat](xref:System.Globalization.DateTimeFormatInfo.GetFormat(System.Type)) этого класса возвращает экземпляр его самого.

В следующем примере объекты [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), представляющие "Английский (США)" и "Английский (Великобритания)" язык и региональные параметры, а также "Французский" и "Русский" нейтральные языки и региональные параметры, используются для форматирования даты. 

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {                                                                                                    
      DateTime dat1 = new DateTime(2012, 5, 28, 11, 30, 0);
      string[] cultureNames = { "en-US", "en-GB", "ru", "fr" };

      foreach (var name in cultureNames) {
         DateTimeFormatInfo dtfi = CultureInfo.CreateSpecificCulture(name).DateTimeFormat;
         Console.WriteLine("{0}: {1}", name, dat1.ToString(dtfi));
      }   
   }
}
// The example displays the following output:
//       en-US: 5/28/2012 11:30:00 AM
//       en-GB: 28/05/2012 11:30:00
//       ru: 28.05.2012 11:30:00
//       fr: 28/05/2012 11:30:00
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim dat1 As Date = #5/28/2012 11:30AM#
      Dim cultureNames() As String = { "en-US", "en-GB", "ru", "fr" }

      For Each name In cultureNames
         Dim dtfi As DateTimeFormatInfo = CultureInfo.CreateSpecificCulture(name).DateTimeFormat
         Console.WriteLine("{0}: {1}", name, dat1.ToString(dtfi))
      Next   
   End Sub
End Module
' The example displays the following output:
'       en-US: 5/28/2012 11:30:00 AM
'       en-GB: 28/05/2012 11:30:00
'       ru: 28.05.2012 11:30:00
'       fr: 28/05/2012 11:30:00
```

## <a name="the-iformattable-interface"></a>Интерфейс IFormattable

Обычно типы, в которых имеется перегрузка метода `ToString`, использующая строку формата и параметр [IFormatProvider](xref:System.IFormatProvider), также реализуют интерфейс [IFormattable](xref:System.IFormattable). Единственный член этого интерфейса — метод [IFormattable.ToString(String, IFormatProvider)](xref:System.IFormattable.ToString(System.String,System.IFormatProvider)), параметрами которого являются строка формата и поставщик форматирования.

Реализация интерфейса [IFormattable](xref:System.IFormattable) в определяемых приложением классах позволяет получить два преимущества: 

* Поддержка строковых преобразований с помощью класса [Convert](xref:System.Convert). При вызове методов [Convert.ToString(Object)](xref:System.Convert.ToString(System.Object)) и [Convert.ToString(Object, IFormatProvider)](xref:System.Convert.ToString(System.Object,System.IFormatProvider)) автоматически вызывается пользовательская реализация [IFormattable](xref:System.IFormattable).

* Поддержка составного форматирования. Если для форматирования пользовательского типа используется элемент форматирования, включающий строку формата, то среда CLR автоматически вызывает пользовательскую реализацию [IFormattable](xref:System.IFormattable), передавая ей строку формата. Дополнительные сведения о составном форматировании при помощи таких методов, как `String.Format` или `Console.WriteLine`, см. в разделе [Составное форматирование](#composite-formatting).

В следующем примере определяется класс `Temperature`, реализующий интерфейс [IFormattable](xref:System.IFormattable). Он поддерживает описатели формата "C" и "G", позволяющие отобразить значение температуры в градусах Цельсия, описатель формата "F", позволяющий отобразить значение температуры в градусах Фаренгейта, и описатель формата "K", позволяющий отобразить значение температуры в градусах Кельвина.

```csharp
using System;
using System.Globalization;

public class Temperature : IFormattable
{
   private decimal m_Temp;

   public Temperature(decimal temperature)
   {
      this.m_Temp = temperature;
   }

   public decimal Celsius
   {
      get { return this.m_Temp; }
   }

   public decimal Kelvin
   {
      get { return this.m_Temp + 273.15m; }   
   }

   public decimal Fahrenheit
   {
      get { return Math.Round((decimal) this.m_Temp * 9 / 5 + 32, 2); }
   }

   public override string ToString()
   {
      return this.ToString("G", null);
   }

   public string ToString(string format)
   {
      return this.ToString(format, null);
   }

   public string ToString(string format, IFormatProvider provider)  
   {
      // Handle null or empty arguments.
      if (String.IsNullOrEmpty(format)) format = "G";
      // Remove any white space and convert to uppercase.
      format = format.Trim().ToUpperInvariant();

      if (provider == null) provider = NumberFormatInfo.CurrentInfo;

      switch (format)
      {
         // Convert temperature to Fahrenheit and return string.
         case "F":
            return this.Fahrenheit.ToString("N2", provider) + "°F";
         // Convert temperature to Kelvin and return string.
         case "K":
            return this.Kelvin.ToString("N2", provider) + "K";
         // Return temperature in Celsius.
         case "C":
         case "G":
            return this.Celsius.ToString("N2", provider) + "°C";
         default:
            throw new FormatException(String.Format("The '{0}' format string is not supported.", format));
      }      
   }
}
```

```vb
Imports System.Globalization

Public Class Temperature : Implements IFormattable
   Private m_Temp As Decimal

   Public Sub New(temperature As Decimal)
      Me.m_Temp = temperature
   End Sub

   Public ReadOnly Property Celsius() As Decimal
      Get
         Return Me.m_Temp
      End Get   
   End Property

   Public ReadOnly Property Kelvin() As Decimal
      Get
         Return Me.m_Temp + 273.15d   
      End Get
   End Property

   Public ReadOnly Property Fahrenheit() As Decimal
      Get
         Return Math.Round(CDec(Me.m_Temp * 9 / 5 + 32), 2)
      End Get      
   End Property

   Public Overrides Function ToString() As String
      Return Me.ToString("G", Nothing)
   End Function

   Public Overloads Function ToString(format As String) As String
      Return Me.ToString(format, Nothing)
   End Function

   Public Overloads Function ToString(format As String, provider As IFormatProvider) As String _  
      Implements IFormattable.ToString

      ' Handle null or empty arguments.
      If String.IsNullOrEmpty(format) Then format = "G"
      ' Remove any white space and convert to uppercase.
      format = format.Trim().ToUpperInvariant()

      If provider Is Nothing Then provider = NumberFormatInfo.CurrentInfo

      Select Case format
         ' Convert temperature to Fahrenheit and return string.
         Case "F"
            Return Me.Fahrenheit.ToString("N2", provider) & "°F"
         ' Convert temperature to Kelvin and return string.
         Case "K"
            Return Me.Kelvin.ToString("N2", provider) & "K"
         ' Return temperature in Celsius.
         Case "C", "G"
            Return Me.Celsius.ToString("N2", provider) & "°C"
         Case Else
            Throw New FormatException(String.Format("The '{0}' format string is not supported.", format))
      End Select      
   End Function
End Class
```

В следующем примере создается объект `Temperature`. Затем в нем вызывается метод [ToString](xref:System.Convert.ToString(System.Object,System.IFormatProvider)). Использование нескольких строк составного формата позволяет получить различные строковые представления объекта `Temperature`. В свою очередь каждый из этих вызовов метода вызывает реализацию [IFormattable](xref:System.IFormattable) класса `Temperature`.

```csharp
public class Example
{
   public static void Main()
   {
      Temperature temp1 = new Temperature(22m);
      Console.WriteLine(Convert.ToString(temp1, new CultureInfo("ja-JP")));
      Console.WriteLine("Temperature: {0:K}", temp1);
      Console.WriteLine("Temperature: {0:F}", temp1);
      Console.WriteLine(String.Format(new CultureInfo("fr-FR"), "Temperature: {0:F}", temp1));
   }
}
// The example displays the following output:
//       22.00°C
//       Temperature: 295.15°K
//       Temperature: 71.60°F
//       Temperature: 71,60°F
```

```vb
Public Module Example
   Public Sub Main()
      Dim temp1 As New Temperature(22d)
      Console.WriteLine(Convert.ToString(temp1, New CultureInfo("ja-JP")))
      Console.WriteLine("Temperature: {0:K}", temp1)
      Console.WriteLine("Temperature: {0:F}", temp1)
      Console.WriteLine(String.Format(New CultureInfo("fr-FR"), "Temperature: {0:F}", temp1)) 
   End Sub
End Module
' The example displays the following output:
'       22.00°C
'       Temperature: 295.15°K
'       Temperature: 71.60°F
'       Temperature: 71,60°F
```

## <a name="composite-formatting"></a>Составное форматирование

Некоторые методы, например `String.Format` и `StringBuilder.AppendFormat`, поддерживают составное форматирование. Строка составного формата — это некий шаблон, возвращающий единую строку, включающую строковое представление нулевого, единичного или другого числа объектов. Каждый объект представляется в строке составного формата индексированным элементом форматирования. Индекс элемента форматирования соответствует положению представляющего его объекта в списке параметров метода. Индексы отсчитываются от нуля. Например, в вызове метода `String.Format` первый элемент форматирования, `{0:D}`, замещается строковым представлением `thatDate`; второй элемент форматирования, `{1}`, замещается строковым представлением `item1`; а третий элемент форматирования, `{2:C2}`, замещается строковым представлением `item1.Value`.

```csharp
result = String.Format("On {0:d}, the inventory of {1} was worth {2:C2}.", 
                       thatDate, item1, item1.Value);
Console.WriteLine(result);                            
// The example displays output like the following if run on a system
// whose current culture is en-US:
//       On 5/1/2009, the inventory of WidgetA was worth $107.44.
```

```vb
result = String.Format("On {0:d}, the inventory of {1} was worth {2:C2}.", _
                       thatDate, item1, item1.Value)
Console.WriteLine(result)                            
' The example displays output like the following if run on a system
' whose current culture is en-US:
'       On 5/1/2009, the inventory of WidgetA was worth $107.44.
```

Помимо замены элементов форматирования строковыми представлениями соответствующего объекта, элементы форматирования также позволяют управлять перечисленными ниже аспектами. 

* Вы можете указать конкретный способ представления объекта в виде строки, если объект реализует интерфейс [IFormattable](xref:System.IFormattable) и поддерживает строки формата. Для этого после индекса элемента форматирования необходимо ввести ":" (двоеточие), а за ним — допустимую строку формата. В предыдущем примере для этого выполнялось форматирование значения даты с помощью строки формата "d" (шаблон короткого формата даты, например `{0:d}`) и форматирование числового значения с помощью строки формата "C2" (например, `{2:C2}` для представления числа в виде значения валюты с двумя цифрами дробной части). 

* Вы можете задать ширину поля, содержащего строковое представление объекта, и выравнивание строкового представления в этом поле. Для этого после индекса элемента форматирования необходимо ввести "," (запятую), а за ней — значение ширины поля. Строка выравнивается по правому краю поля, если ширина поля — положительное значение, и по левому краю, если ширина поля — отрицательное значение. В примере ниже значения даты выравниваются по левому краю поля из 20 символов, а десятичные значения с одной цифрой дробной части — по правом краю поля из 11 символов. 

```csharp
DateTime startDate = new DateTime(2015, 8, 28, 6, 0, 0);
decimal[] temps = { 73.452m, 68.98m, 72.6m, 69.24563m,
                   74.1m, 72.156m, 72.228m };
Console.WriteLine("{0,-20} {1,11}\n", "Date", "Temperature");
for (int ctr = 0; ctr < temps.Length; ctr++)
   Console.WriteLine("{0,-20:g} {1,11:N1}", startDate.AddDays(ctr), temps[ctr]);

// The example displays the following output:
//       Date                 Temperature
//
//       8/28/2015 6:00 AM           73.5
//       8/29/2015 6:00 AM           69.0
//       8/30/2015 6:00 AM           72.6
//       8/31/2015 6:00 AM           69.2
//       9/1/2015 6:00 AM            74.1
//       9/2/2015 6:00 AM            72.2
//       9/3/2015 6:00 AM            72.2
```

```vb
Dim startDate As New Date(2015, 8, 28, 6, 0, 0)
Dim temps() As Decimal = { 73.452, 68.98, 72.6, 69.24563,
                           74.1, 72.156, 72.228 }
Console.WriteLine("{0,-20} {1,11}", "Date", "Temperature")
Console.WriteLine()
For ctr As Integer = 0 To temps.Length - 1
   Console.WriteLine("{0,-20:g} {1,11:N1}", startDate.AddDays(ctr), temps(ctr))
Next
' The example displays the following output:
'       Date                 Temperature
'
'       8/28/2015 6:00 AM           73.5
'       8/29/2015 6:00 AM           69.0
'       8/30/2015 6:00 AM           72.6
'       8/31/2015 6:00 AM           69.2
'       9/1/2015 6:00 AM            74.1
'       9/2/2015 6:00 AM            72.2
'       9/3/2015 6:00 AM            72.2
```

Обратите внимание на то, что если присутствует и компонент выравнивания строки, и компонент строки формата, первый из них предшествует последнему (например, `{0,-20:g}`). 

Подробности о составном форматировании см. в разделе [Составное форматирование](composite-format.md).

## <a name="custom-formatting-with-icustomformatter"></a>Настраиваемое форматирование с использованием интерфейса ICustomFormatter

У двух методов составного форматирования [String.Format(IFormatProvider, String, Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object[])) и [StringBuilder.AppendFormat(IFormatProvider, String, Object[])](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)) также имеется параметр, задающий поставщик форматирования, поддерживающий настраиваемое форматирование. При вызове какого-либо из этих методов форматирования объект [Type](xref:System.Type), представляющий интерфейс [ICustomFormatter](xref:System.ICustomFormatter), передается методу `GetFormat` поставщика форматирования. Метод `GetFormat` должен вернуть реализацию [ICustomFormatter](xref:System.ICustomFormatter), поддерживающую настраиваемое форматирование.

Единственный метод интерфейса [ICustomFormatter](xref:System.ICustomFormatter), который называется [Format(String, Object, IFormatProvider)](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)), автоматически вызывается методом составного форматирования по одному разу для каждого элемента форматирования в строке составного формата. У метода [Format(String, Object, IFormatProvider)](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) есть три параметра: строка формата, представляющая аргумент *formatString* в элементе форматирования, сам форматируемый объект и объект [IFormatProvider](xref:System.IFormatProvider), предоставляющий услуги форматирования. Обычно класс, реализующий интерфейс [ICustomFormatter](xref:System.ICustomFormatter), также реализует интерфейс [IFormatProvider](xref:System.IFormatProvider), поэтому в таком случае последний параметр будет ссылкой на сам класс настраиваемого форматирования. Метод возвращает настраиваемое строковое представление объекта, который нужно было отформатировать. Если методу не удается отформатировать объект, он должен вернуть пустую ссылку.

В следующем примере приведена реализация [ICustomFormatter](xref:System.ICustomFormatter) с именем `ByteByByteFormatter`, отображающая целочисленные значения в виде последовательности пар шестнадцатеричных цифр, разделенных пробелами.

```csharp
public class ByteByByteFormatter : IFormatProvider, ICustomFormatter
{
   public object GetFormat(Type formatType)
   { 
      if (formatType == typeof(ICustomFormatter))
         return this;
      else
         return null;
   }

   public string Format(string format, object arg, 
                          IFormatProvider formatProvider)
   {   
      if (! formatProvider.Equals(this)) return null;

      // Handle only hexadecimal format string.
      if (! format.StartsWith("X")) return null;

      byte[] bytes;
      string output = null;

      // Handle only integral types.
      if (arg is Byte) 
         bytes = BitConverter.GetBytes((Byte) arg);
      else if (arg is Int16)
         bytes = BitConverter.GetBytes((Int16) arg);
      else if (arg is Int32)
         bytes = BitConverter.GetBytes((Int32) arg);
      else if (arg is Int64)   
         bytes = BitConverter.GetBytes((Int64) arg);
      else if (arg is SByte)
         bytes = BitConverter.GetBytes((SByte) arg);
      else if (arg is UInt16)
         bytes = BitConverter.GetBytes((UInt16) arg);
      else if (arg is UInt32)
         bytes = BitConverter.GetBytes((UInt32) arg);
      else if (arg is UInt64)
         bytes = BitConverter.GetBytes((UInt64) arg);
      else
         return null;

      for (int ctr = bytes.Length - 1; ctr >= 0; ctr--)
         output += String.Format("{0:X2} ", bytes[ctr]);   

      return output.Trim();
   }
}
```

```vb
Public Class ByteByByteFormatter : Implements IFormatProvider, ICustomFormatter
   Public Function GetFormat(formatType As Type) As Object _
                   Implements IFormatProvider.GetFormat
      If formatType Is GetType(ICustomFormatter) Then
         Return Me
      Else
         Return Nothing
      End If
   End Function

   Public Function Format(fmt As String, arg As Object, 
                          formatProvider As IFormatProvider) As String _
                          Implements ICustomFormatter.Format

      If Not formatProvider.Equals(Me) Then Return Nothing

      ' Handle only hexadecimal format string.
      If Not fmt.StartsWith("X") Then 
            Return Nothing
      End If

      ' Handle only integral types.
      If Not typeof arg Is Byte AndAlso
         Not typeof arg Is Int16 AndAlso
         Not typeof arg Is Int32 AndAlso
         Not typeof arg Is Int64 AndAlso
         Not typeof arg Is SByte AndAlso
         Not typeof arg Is UInt16 AndAlso
         Not typeof arg Is UInt32 AndAlso
         Not typeof arg Is UInt64 Then _
            Return Nothing

      Dim bytes() As Byte = BitConverter.GetBytes(arg)
      Dim output As String = Nothing

      For ctr As Integer = bytes.Length - 1 To 0 Step -1
         output += String.Format("{0:X2} ", bytes(ctr))   
      Next

      Return output.Trim()
   End Function
End Class
```

В следующем примере класс `ByteByByteFormatter` используется для форматирования целочисленных значений. Обратите внимание, что метод [ICustomFormatter.Format](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) вызывается во втором вызове метода [String.Format(IFormatProvider, String, Object[])](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) несколько раз и что в третьем вызове метода используется поставщик [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) по умолчанию, поскольку метод `.ByteByByteFormatter.Format` не распознает строку формата "N0" и возвращает пустую ссылку.

```csharp
public class Example
{
   public static void Main()
   {
      long value = 3210662321; 
      byte value1 = 214;
      byte value2 = 19;

      Console.WriteLine(String.Format(new ByteByByteFormatter(), "{0:X}", value));
      Console.WriteLine(String.Format(new ByteByByteFormatter(), "{0:X} And {1:X} = {2:X} ({2:000})", 
                                      value1, value2, value1 & value2));                                
      Console.WriteLine(String.Format(new ByteByByteFormatter(), "{0,10:N0}", value));
   }
}
// The example displays the following output:
//       00 00 00 00 BF 5E D1 B1
//       00 D6 And 00 13 = 00 12 (018)
//       3,210,662,321
```

```vb
Public Module Example
   Public Sub Main()
      Dim value As Long = 3210662321 
      Dim value1 As Byte = 214
      Dim value2 As Byte = 19

      Console.WriteLine((String.Format(New ByteByByteFormatter(), "{0:X}", value)))
      Console.WriteLine((String.Format(New ByteByByteFormatter(), "{0:X} And {1:X} = {2:X} ({2:000})", 
                                      value1, value2, value1 And value2)))                                
      Console.WriteLine(String.Format(New ByteByByteFormatter(), "{0,10:N0}", value))
   End Sub
End Module
' The example displays the following output:
'       00 00 00 00 BF 5E D1 B1
'       00 D6 And 00 13 = 00 12 (018)
'       3,210,662,321
```

## <a name="related-topics"></a>См. также

Заголовок | Определение
----- | ----------
[Строки стандартных числовых форматов](standard-numeric.md) | Описание строк стандартного формата, позволяющих создавать общеупотребимые строковые представления числовых значений. 
[Строки настраиваемых числовых форматов](custom-numeric.md) | Описание строк настраиваемого формата, позволяющих создавать прикладные строковые представления числовых значений.
[Строки стандартных форматов даты и времени](standard-datetime.md) |  Описание строк стандартного формата, позволяющих создавать общеупотребимые строковые представления значений [DateTime](xref:System.DateTime).
[Строки настраиваемых форматов даты и времени](custom-datetime.md) | Описание строк настраиваемого формата, позволяющих создавать характерные для приложений форматы для значений [DateTime](xref:System.DateTime).
[Строки стандартного формата TimeSpan](standard-timespan.md) | Описание строк стандартного формата, позволяющих создавать общеупотребимые строковые представления интервалов времени.
[Строки настраиваемого формата TimeSpan](custom-timespan.md) | Описание строк настраиваемого формата, позволяющих создавать прикладные строковые представления интервалов времени.
[Строки форматов перечисления](enumeration-format.md) | Описание строк стандартного формата, используемых для создания строковых представлений значений перечислений.
[Составное форматирование](composite-format.md) | Описание способа совмещения нескольких форматируемых значений в строке. Строка может быть последовательно отображена в консоли или выведена в поток.
[Выполнение операций форматирования](performing-formatting-operations.md) | Перечень разделов, содержащих пошаговые инструкции для выполнения конкретных операций форматирования.
[Анализ строк](parsing-strings.md) | Описание способов инициализации объектов со значениями, описанными строковыми представлениями этих объектов. Разбор является операцией, обратной форматированию.

## <a name="reference"></a>Ссылка

[System.IFormattable](xref:System.IFormattable)

[System.IFormatProvider](xref:System.IFormatProvider)

[System.ICustomFormatter](xref:System.ICustomFormatter)

