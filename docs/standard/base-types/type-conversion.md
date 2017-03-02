---
title: "Преобразование типов"
description: "Преобразование типов"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/22/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: c9a53222-89cb-47e5-983d-4f0f204e31ba
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 0a774a170b7703b900c2044708b07faeb4e51548
ms.lasthandoff: 03/02/2017

---

# <a name="type-conversion"></a>Преобразование типов

Каждое значение имеет соответствующий тип, который определяет атрибуты, такие как объем памяти, выделяемой значению, диапазон возможных значений и доступные элементы. Многие значения можно выразить несколькими типами. Например, число `4` можно выразить как целое число или как число с плавающей запятой. Преобразование типа создает значение нового типа, эквивалентное значению старого типа, но при этом не обязательно сохраняется идентичность (или точные значения) первоначального объекта.

Платформа .NET автоматически поддерживает указанные далее преобразования.

* Преобразование из производного класса в базовый класс. Это означает, например, что экземпляр любого класса или структуры может быть преобразован в экземпляр [Object](xref:System.Object). Для этого преобразования не требуется оператор приведения.

* Преобразование из базового класса обратно в исходный производный класс. В C# для этого преобразования требуется оператор приведения. В Visual Basic требуется оператор `CType`, если `Option Strict` включен. 

* Преобразование из типа, реализующего интерфейс, в объект интерфейса, представляющий этот интерфейс. Для этого преобразования не требуется оператор приведения.

* Преобразование из объекта интерфейса обратно в исходный тип, который реализует этот интерфейс. В C# для этого преобразования требуется оператор приведения. В Visual Basic требуется оператор `CType`, если `Option Strict` включен. 

Помимо этих автоматических преобразований в .NET предусмотрено несколько возможностей для поддержки преобразования пользовательского типа. В число этих требований входят следующие: 

* Оператор `Implicit`, определяющий доступные расширяющие преобразования между типами. Дополнительные сведения см. в разделе [Неявные преобразования с помощью оператора Implicit](#implicit-conversion-with-the-implicit-operator).

* Оператор `Explicit`, определяющий доступные сужающие преобразования между типами. Дополнительные сведения см. в разделе [Явные преобразования с помощью оператора Explicit](#explicit-conversion-with-the-explicit-operator).

* Интерфейс [IConvertible](xref:System.IConvertible), определяющий преобразования в каждый из базовых типов данных платформы .NET. Дополнительные сведения см. в разделе [Интерфейс IConvertible](#the-iconvertible-interface).

* Класс [Convert](xref:System.Convert), предоставляющий набор методов, реализующих методы интерфейса `IConvertible`. Дополнительные сведения см. в разделе [Класс Convert](#the-convert-class).

* Класс [TypeConverter](xref:System.ComponentModel.TypeConverter), являющийся базовым классом, который может быть расширен для поддержки преобразования указанного типа в любой другой тип. Дополнительные сведения см. в разделе [Класс TypeConverter](#the-typeconverter-class).

## <a name="implicit-conversion-with-the-implicit-operator"></a>Неявное преобразование с помощью оператора Implicit

Расширяющие преобразования предполагают создание нового значения из значения существующего типа, имеющего более ограничивающий диапазон или более ограниченный список членов, чем целевой тип. Расширяющие преобразования не могут привести к потере данных (хотя способны дать в результате меньшую точность). Поскольку потеря данных исключена, компиляторы могут обрабатывать преобразование неявно или прозрачно без необходимости использования метода явного преобразования или оператора приведения.

> [!NOTE]
> Хотя код, используемый для неявного преобразования, может вызывать метод преобразования или использовать оператор приведения, применение таких методов компиляторами, поддерживающими неявные преобразования, не требуется.

Например, тип [Decimal](xref:System.Decimal) поддерживает неявные преобразования значений из типов [Byte](xref:System.Byte), [Char](xref:System.Char), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32) и [UInt64](xref:System.UInt64). В следующем примере демонстрируются некоторые неявные преобразования при присвоении значений переменной `Decimal`.

```csharp
byte byteValue = 16;
short shortValue = -1024;
int intValue = -1034000;
long longValue = 1152921504606846976;
ulong ulongValue = UInt64.MaxValue;

decimal decimalValue;

decimalValue = byteValue;
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.", 
                  byteValue.GetType().Name, decimalValue); 

decimalValue = shortValue;
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.", 
                  shortValue.GetType().Name, decimalValue); 

decimalValue = intValue;
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.", 
                  intValue.GetType().Name, decimalValue); 

decimalValue = longValue;
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.", 
                  longValue.GetType().Name, decimalValue); 

decimalValue = ulongValue;
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.", 
                  longValue.GetType().Name, decimalValue); 
// The example displays the following output:
//    After assigning a Byte value, the Decimal value is 16.
//    After assigning a Int16 value, the Decimal value is -1024.
//    After assigning a Int32 value, the Decimal value is -1034000.
//    After assigning a Int64 value, the Decimal value is 1152921504606846976.
//    After assigning a Int64 value, the Decimal value is 18446744073709551615.
```

```vb
Dim byteValue As Byte = 16
Dim shortValue As Short = -1024
Dim intValue As Integer = -1034000
Dim longValue As Long = CLng(1024^6)
Dim ulongValue As ULong = ULong.MaxValue

Dim decimalValue As Decimal

decimalValue = byteValue
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.",
                  byteValue.GetType().Name, decimalValue) 

decimalValue = shortValue
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.",
                  shortValue.GetType().Name, decimalValue) 

decimalValue = intValue
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.",
                  intValue.GetType().Name, decimalValue) 

decimalValue = longValue
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.",
                  longValue.GetType().Name, decimalValue) 

decimalValue = ulongValue
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.",
                  longValue.GetType().Name, decimalValue) 
' The example displays the following output:
'    After assigning a Byte value, the Decimal value is 16.
'    After assigning a Int16 value, the Decimal value is -1024.
'    After assigning a Int32 value, the Decimal value is -1034000.
'    After assigning a Int64 value, the Decimal value is 1152921504606846976.
'    After assigning a Int64 value, the Decimal value is 18446744073709551615.
```

Если компилятор конкретного языка поддерживает настраиваемые операторы, можно также определить неявные преобразования в собственных настраиваемых типах. В следующем примере показана частичная реализация знакового типа данных byte с именем `ByteWithSign`, использующего представление знака и величины. Он поддерживает неявное преобразование значений [Byte](xref:System.Byte) и [SByte](xref:System.SByte) в значения `ByteWithSign`.

```csharp
public struct ByteWithSign
{
   private SByte signValue; 
   private Byte value;

   public static implicit operator ByteWithSign(SByte value) 
   {
      ByteWithSign newValue;
      newValue.signValue = (SByte) Math.Sign(value);
      newValue.value = (byte) Math.Abs(value);
      return newValue;
   }  

   public static implicit operator ByteWithSign(Byte value)
   {
      ByteWithSign  newValue;
      newValue.signValue = 1;
      newValue.value = value;
      return newValue;
   }

   public override string ToString()
   { 
      return (signValue * value).ToString();
   }
}
```

```vb
Public Structure ByteWithSign
   Private signValue As SByte 
   Private value As Byte

   Public Overloads Shared Widening Operator CType(value As SByte) As ByteWithSign
      Dim newValue As ByteWithSign
      newValue.signValue = CSByte(Math.Sign(value))
      newValue.value = CByte(Math.Abs(value))
      Return newValue
   End Operator  

   Public Overloads Shared Widening Operator CType(value As Byte) As ByteWithSign
      Dim NewValue As ByteWithSign
      newValue.signValue = 1
      newValue.value = value
      Return newValue
   End Operator

   Public Overrides Function ToString() As String 
      Return (signValue * value).ToString()
   End Function
End Structure
```

В клиентском коде затем можно объявить переменную `ByteWithSign` и присвоить ей значения [Byte](xref:System.Byte) и [SByte](xref:System.SByte), не выполняя явные преобразования и не используя операторы приведения, как показано в следующем примере.

```csharp
SByte sbyteValue = -120;
ByteWithSign value = sbyteValue;
Console.WriteLine(value);
value = Byte.MaxValue;
Console.WriteLine(value);
// The example displays the following output:
//       -120
//       255
```

```vb
Dim sbyteValue As SByte = -120
Dim value As ByteWithSign = sbyteValue
Console.WriteLine(value.ToString()) 
value = Byte.MaxValue
Console.WriteLine(value.ToString()) 
' The example displays the following output:
'       -120
'       255
```

## <a name="explicit-conversion-with-the-explicit-operator"></a>Явное преобразование с помощью оператора Explicit

Сужающие преобразования предполагают создание нового значения из значения существующего типа, имеющего более широкий диапазон или список членов, чем у целевого типа. Поскольку сужающее преобразование может привести к потере данных, компиляторы, как правило, требуют выполнять преобразование явно посредством вызова метода преобразования или оператора приведения. Это означает, что преобразование должно обрабатываться явно в коде разработчика. 

> [!NOTE]
> Основная цель требования явного использования метода преобразования или оператора приведения заключается в информировании разработчика о возможной потере данных или исключении [OverflowException](xref:System.OverflowException), чтобы это можно было учесть в коде. При этом некоторые компиляторы могут опускать это требование. Например, в Visual Basic, если параметр `Option Strict` выключен (по умолчанию), компилятор Visual Basic предпринимает попытку выполнения сужающего преобразования неявно.

Например, типы данных [UInt32](xref:System.UInt32), [Int64](xref:System.Int64) и [UInt64](xref:System.UInt64) имеют диапазоны, покрывающие диапазон типа данных [Int32](xref:System.Int32), как показано в таблице ниже.

Тип | Сравнение с диапазоном Int32
---- | ------------------------------
[Int64](xref:System.Int64) | [Int64.MaxValue](xref:System.Int64.MaxValue) больше, чем [Int32.MaxValue](xref:System.Int32#System_Int32_MaxValue), а [Int64.MinValue](xref:System.Int64.MinValue) меньше (имеет больший отрицательный диапазон), чем [Int32.MinValue](xref:System.Int32#System_Int32_MinValue).
[UInt32](xref:System.UInt32) | [UInt32.MaxValue](xref:System.UInt32.MaxValue) больше, чем [Int32.MaxValue](xref:System.Int32.MaxValue).
[UInt64](xref:System.UInt64) | [UInt64.MaxValue](xref:System.UInt64.MaxValue) больше, чем [Int32.MaxValue](xref:System.Int32.MaxValue).

Для обработки таких сужающих преобразований .NET позволяет типам определять оператор `Explicit`. Компиляторы отдельных языков могут реализовывать этот оператор, используя свой собственный синтаксис или вызывая член класса [Convert](xref:System.Convert) для выполнения преобразования. (Дополнительные сведения о классе `Convert` см. в подразделе [Класс Convert](#the-convert-class) далее в этом разделе.) В следующем примере показано использование функций языка для обработки явного преобразования этих потенциально выходящих за пределы диапазона целочисленных значений в значения [Int32](xref:System.Int32). 

```csharp
long number1 = int.MaxValue + 20L;
uint number2 = int.MaxValue - 1000;
ulong number3 = int.MaxValue;

int intNumber;

try {
   intNumber = checked((int) number1);
   Console.WriteLine("After assigning a {0} value, the Integer value is {1}.", 
                     number1.GetType().Name, intNumber); 
}
catch (OverflowException) {
   if (number1 > int.MaxValue)
      Console.WriteLine("Conversion failed: {0} exceeds {1}.", 
                        number1, int.MaxValue);
   else
      Console.WriteLine("Conversion failed: {0} is less than {1}.", 
                        number1, int.MinValue);
}

try {
   intNumber = checked((int) number2);
   Console.WriteLine("After assigning a {0} value, the Integer value is {1}.", 
                     number2.GetType().Name, intNumber); 
}
catch (OverflowException) {
   Console.WriteLine("Conversion failed: {0} exceeds {1}.", 
                     number2, int.MaxValue);
}

try {
   intNumber = checked((int) number3);
   Console.WriteLine("After assigning a {0} value, the Integer value is {1}.", 
                     number3.GetType().Name, intNumber); 
}
catch (OverflowException) {
   Console.WriteLine("Conversion failed: {0} exceeds {1}.", 
                     number1, int.MaxValue);
}

// The example displays the following output:
//    Conversion failed: 2147483667 exceeds 2147483647.
//    After assigning a UInt32 value, the Integer value is 2147482647.
//    After assigning a UInt64 value, the Integer value is 2147483647.
```

```vb
Dim number1 As Long = Integer.MaxValue + 20L
Dim number2 As UInteger = Integer.MaxValue - 1000
Dim number3 As ULong = Integer.MaxValue

Dim intNumber As Integer

Try
   intNumber = CInt(number1)
   Console.WriteLine("After assigning a {0} value, the Integer value is {1}.", 
                       number1.GetType().Name, intNumber)
Catch e As OverflowException
   If number1 > Integer.MaxValue Then
      Console.WriteLine("Conversion failed: {0} exceeds {1}.", 
                                        number1, Integer.MaxValue)
   Else
      Console.WriteLine("Conversion failed: {0} is less than {1}.\n", 
                                        number1, Integer.MinValue)
   End If
End Try

Try
   intNumber = CInt(number2)
   Console.WriteLine("After assigning a {0} value, the Integer value is {1}.", 
                       number2.GetType().Name, intNumber)
Catch e As OverflowException
   Console.WriteLine("Conversion failed: {0} exceeds {1}.", 
                                     number2, Integer.MaxValue)
End Try

Try
   intNumber = CInt(number3)
   Console.WriteLine("After assigning a {0} value, the Integer value is {1}.", 
                       number3.GetType().Name, intNumber)
Catch e As OverflowException
   Console.WriteLine("Conversion failed: {0} exceeds {1}.",
                                     number1, Integer.MaxValue)
End Try
' The example displays the following output:
'    Conversion failed: 2147483667 exceeds 2147483647.
'    After assigning a UInt32 value, the Integer value is 2147482647.
'    After assigning a UInt64 value, the Integer value is 2147483647.
```

Результаты явного преобразования в разных языках могут быть различными. Кроме того, эти результаты могут отличаться от значений, возвращаемых соответствующим методом [Convert](xref:System.Convert). Например, если значение типа [Double](xref:System.Double), равное **12.63251**, преобразуется в [Int32](xref:System.Int32), метод Visual Basic `CInt` и метод платформы .NET [Convert.ToInt32(Double)](xref:System.Convert.ToInt32(System.Double)) округляют [Double](xref:System.Double), возвращая значение **13**, а оператор C# `(int)` усекает значение [Double](xref:System.Double), возвращая значение **12**. Аналогично оператор C# `(int)` не поддерживает преобразование логических значений в целочисленные, а метод Visual Basic `CInt` преобразует значение `true` в **-1**. С другой стороны, метод [Convert.ToInt32(Boolean)](xref:System.Convert.ToInt32(System.Boolean)) преобразует значение `true` в **1**.

Большинство компиляторов допускают явное преобразование как с проверкой, так и без проверки. Если при выполнении преобразования с проверкой преобразуемое значение находится вне диапазона допустимых значений конечного типа, создается исключение [OverflowException](xref:System.OverflowException). Если в такой же ситуации выполнять преобразование без проверки, то исключение может не быть создано, но результат преобразования в данном случае неизвестен, и на выходе может быть получено неверное значение.

> [!NOTE]
> В C# для преобразования с проверкой используется ключевое слово `checked`, добавляемое к оператору приведения, или параметр компилятора `/checked+`. Для преобразования без проверки используется ключевое слово `unchecked`, добавляемое к оператору приведения, или параметр компилятора `/checked-`. По умолчанию явное преобразование выполняется без проверки. В Visual Basic для преобразования с проверкой используется параметр компилятора `/removeintchecks-`. И наоборот, для преобразования без проверки используется параметр компилятора `/removeintchecks+`. По умолчанию явное преобразование выполняется с проверкой.

В следующем примере на C# используются ключевые слова `checked` и `unchecked` для демонстрации разницы поведения при преобразовании выходящего за пределы диапазона значения [Byte](xref:System.Byte) в `Byte`. При выполнении преобразования с проверкой создается исключение, а при выполнении преобразования без проверки значение [Byte.MaxValue](xref:System.Byte.MaxValue) присваивается переменой `Byte`.

```csharp
int largeValue = Int32.MaxValue;
byte newValue;

try {
   newValue = unchecked((byte) largeValue);
   Console.WriteLine("Converted the {0} value {1} to the {2} value {3}.", 
                     largeValue.GetType().Name, largeValue,
                     newValue.GetType().Name, newValue);
}
catch (OverflowException) {
   Console.WriteLine("{0} is outside the range of the Byte data type.", 
                     largeValue);
}

try {
   newValue = checked((byte) largeValue);
   Console.WriteLine("Converted the {0} value {1} to the {2} value {3}.", 
                     largeValue.GetType().Name, largeValue,
                     newValue.GetType().Name, newValue);
}
catch (OverflowException) {
   Console.WriteLine("{0} is outside the range of the Byte data type.", 
                     largeValue);
}
// The example displays the following output:
//    Converted the Int32 value 2147483647 to the Byte value 255.
//    2147483647 is outside the range of the Byte data type.
```

Если компилятор конкретного языка поддерживает настраиваемые перегруженные операторы, можно также определить явные преобразования в собственных настраиваемых типах. В следующем примере показана частичная реализация знакового типа данных byte с именем `ByteWithSign`, использующего представление знака и величины. Он поддерживает явное преобразование значений [Int32](xref:System.Int32) и [UInt32](xref:System.UInt32) в значения `ByteWithSign`.

```csharp
public struct ByteWithSign
{
   private SByte signValue; 
   private Byte value;

   private const byte MaxValue = byte.MaxValue;
   private const int MinValue = -1 * byte.MaxValue;

   public static explicit operator ByteWithSign(int value) 
   {
      // Check for overflow.
      if (value > ByteWithSign.MaxValue || value < ByteWithSign.MinValue)
         throw new OverflowException(String.Format("'{0}' is out of range of the ByteWithSign 
                                                   data type.", 
                                                   value));

      ByteWithSign newValue;
      newValue.signValue = (SByte) Math.Sign(value);
      newValue.value = (byte) Math.Abs(value);
      return newValue;
   }  

   public static explicit operator ByteWithSign(uint value)
   {
      if (value > ByteWithSign.MaxValue) 
         throw new OverflowException(String.Format("'{0}' is out of range of the ByteWithSign 
                                                   data type.", 
                                                   value));

      ByteWithSign newValue;
      newValue.signValue = 1;
      newValue.value = (byte) value;
      return newValue;
   }

   public override string ToString()
   { 
      return (signValue * value).ToString();
   }
}
```

```vb
Public Structure ByteWithSign
   Private signValue As SByte 
   Private value As Byte

   Private Const MaxValue As Byte = Byte.MaxValue
   Private Const MinValue As Integer = -1 * Byte.MaxValue

   Public Overloads Shared Narrowing Operator CType(value As Integer) As ByteWithSign
      ' Check for overflow.
      If value > ByteWithSign.MaxValue Or value < ByteWithSign.MinValue Then
         Throw New OverflowException(String.Format("'{0}' is out of range of the ByteWithSign 
                                                   data type.", value))
      End If

      Dim newValue As ByteWithSign

      newValue.signValue = CSByte(Math.Sign(value))
      newValue.value = CByte(Math.Abs(value))
      Return newValue
   End Operator

   Public Overloads Shared Narrowing Operator CType(value As UInteger) As ByteWithSign
      If value > ByteWithSign.MaxValue Then 
         Throw New OverflowException(String.Format("'{0}' is out of range of the ByteWithSign 
                                                   data type.", value))
      End If

      Dim NewValue As ByteWithSign

      newValue.signValue = 1
      newValue.value = CByte(value)
      Return newValue
   End Operator

   Public Overrides Function ToString() As String 
      Return (signValue * value).ToString()
   End Function
End Structure
```

Если присваивание включает оператор приведения, как показано в следующем примере, в клиентском коде можно объявить переменную `ByteWithSign` и присвоить ей значения [Int32](xref:System.Int32) и [UInt32](xref:System.UInt32).

```csharp
ByteWithSign value;

try {
   int intValue = -120;
   value = (ByteWithSign) intValue;
   Console.WriteLine(value);
}
catch (OverflowException e) {
   Console.WriteLine(e.Message);
}

try {
   uint uintValue = 1024;
   value = (ByteWithSign) uintValue;
   Console.WriteLine(value);
}
catch (OverflowException e) {
    Console.WriteLine(e.Message);
}
// The example displays the following output:
//       -120
//       '1024' is out of range of the ByteWithSign data type.
```

```vb
Dim value As ByteWithSign

Try  
   Dim intValue As Integer = -120
   value = CType(intValue, ByteWithSign)
   Console.WriteLine(value) 
Catch e As OverflowException
   Console.WriteLine(e.Message)
End Try

Try
   Dim uintValue As UInteger = 1024
   value = CType(uintValue, ByteWithSign)
   Console.WriteLine(value) 
Catch e As OverflowException
   Console.WriteLine(e.Message)
End Try
' The example displays the following output:
'       -120
'       '1024' is out of range of the ByteWithSign data type.
```

## <a name="the-iconvertible-interface"></a>Интерфейс IConvertible

Для поддержки преобразования любого типа в базовый тип среды CLR .NET предоставляет интерфейс [IConvertible](xref:System.IConvertible). Реализующий тип должен предоставить следующее:

* Метод, возвращающий объект [TypeCode](xref:System.TypeCode) реализующего типа.

* Метод для преобразования реализующего типа в каждый из базовых типов среды CLR ([Boolean](xref:System.Boolean), [Byte](xref:System.Byte), [DateTime](xref:System.DateTime), [Decimal](xref:System.Decimal), [Double](xref:System.Double) и т. д.).

* Универсальный метод преобразования экземпляра реализующего типа в другой заданный тип. Неподдерживаемые преобразования должны порождать исключение [InvalidCastException](xref:System.InvalidCastException).

Все базовые типы среды CLR (т. е. [Boolean](xref:System.Boolean), [Byte](xref:System.Byte), [Char](xref:System.Char), [DateTime](xref:System.DateTime), [Decimal](xref:System.Decimal), [Double](xref:System.Double), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [Single](xref:System.Single), [String](xref:System.String), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32) и [UInt64](xref:System.UInt64), а также типы [DBNull](xref:System.DBNull) и [Enum](xref:System.Enum) реализуют интерфейс [IConvertible](xref:System.IConvertible). Тем не менее это явные реализации интерфейса; метод преобразования можно вызвать только посредством переменной интерфейса [IConvertible](xref:System.IConvertible), как показано в следующем примере. В этом примере показано преобразование значения [Int32](xref:System.Int32) в эквивалентное значение [Char](xref:System.Char).

```csharp
int codePoint = 1067;
IConvertible iConv = codePoint;
char ch = iConv.ToChar(null);
Console.WriteLine("Converted {0} to {1}.", codePoint, ch);
```

```vb
Dim codePoint As Integer = 1067
Dim iConv As IConvertible = codePoint
Dim ch As Char = iConv.ToChar(Nothing)
Console.WriteLine("Converted {0} to {1}.", codePoint, ch)
```

Требование вызова метода преобразования для интерфейса, а не для реализующего типа, делает явные реализации интерфейса относительно требовательными к ресурсам. Вместо этого для выполнения преобразования между базовыми типами среды CLR рекомендуется вызывать соответствующий член класса [Convert](xref:System.Convert). Дополнительные сведения см. в следующем разделе: [Класс Convert](#the-convert-class). 

> [!NOTE]
> В дополнение к интерфейсу [IConvertible](xref:System.IConvertible) и классу [Convert](xref:System.Convert), предоставленным в .NET, отдельные языки могут также предоставлять различные способы выполнения преобразования. Например, в C# используются операторы приведения типов. В Visual Basic используются функции преобразования, реализованные в компиляторе, такие как `CType` `CInt` и `DirectCast`.

Интерфейс [IConvertible](xref:System.IConvertible) по большей части предназначен для поддержки преобразований между базовыми типами в .NET. При этом данный интерфейс также можно реализовать и в пользовательском типе, чтобы обеспечить поддержку преобразования этого типа в другой пользовательский тип. Дополнительные сведения см. в разделе [Настраиваемые преобразования с использованием метода ChangeType](#custom-conversions-with-the-changetype-method) ниже.

## <a name="the-convert-class"></a>Класс Convert

Хотя каждая реализация интерфейса [IConvertible](xref:System.IConvertible) базового типа может быть вызвана для выполнения преобразования типа, вызов методов класса [System.Convert](xref:System.Convert) является рекомендуемым и не зависящим от языка способом преобразования одного базового типа в другой. Кроме этого, метод [Convert.ChangeType(Object, Type, IFormatProvider)](xref:System.Convert.ChangeType(System.Object,System.Type,System.IFormatProvider)) может использоваться для преобразования указанного настраиваемого типа в другой тип. 

### <a name="conversions-between-base-types"></a>Преобразования между базовыми типами

Класс [Convert](xref:System.Convert) обеспечивает не зависящий от языка способ выполнения преобразований между базовыми типами и доступен во всех языках, предназначенных для среды CLR. Он предоставляет набор методов для расширяющих и сужающих преобразований и создает исключение [InvalidCastException](xref:System.InvalidCastException) для преобразований, которые не поддерживаются (например, для преобразования значения [DateTime](xref:System.DateTime) в целочисленное значение). Сужающие преобразования выполняются в проверяемом контексте, а если преобразование завершается неудачей, порождается исключение [OverflowException](xref:System.OverflowException).

> [!IMPORTANT]
> Поскольку класс [Convert](xref:System.Convert) включает методы преобразования для каждого базового типа, он исключает необходимость вызова явной реализации интерфейса [IConvertible](xref:System.IConvertible) каждого из базовых классов.

В следующем примере показано применение класса [System.Convert](xref:System.Convert) для выполнения нескольких расширяющих и сужающих преобразований между базовыми типами платформы .NET.

```csharp
// Convert an Int32 value to a Decimal (a widening conversion).
int integralValue = 12534;
decimal decimalValue = Convert.ToDecimal(integralValue);
Console.WriteLine("Converted the {0} value {1} to " +  
                                  "the {2} value {3:N2}.", 
                                  integralValue.GetType().Name, 
                                  integralValue, 
                                  decimalValue.GetType().Name, 
                                  decimalValue);
// Convert a Byte value to an Int32 value (a widening conversion).
byte byteValue = Byte.MaxValue;
int integralValue2 = Convert.ToInt32(byteValue);                                  
Console.WriteLine("Converted the {0} value {1} to " +  
                                  "the {2} value {3:G}.", 
                                  byteValue.GetType().Name, 
                                  byteValue, 
                                  integralValue2.GetType().Name, 
                                  integralValue2);

// Convert a Double value to an Int32 value (a narrowing conversion).
double doubleValue = 16.32513e12;
try {
   long longValue = Convert.ToInt64(doubleValue);
   Console.WriteLine("Converted the {0} value {1:E} to " +  
                                     "the {2} value {3:N0}.", 
                                     doubleValue.GetType().Name, 
                                     doubleValue, 
                                     longValue.GetType().Name, 
                                     longValue);
}
catch (OverflowException) {
   Console.WriteLine("Unable to convert the {0:E} value {1}.", 
                                     doubleValue.GetType().Name, doubleValue);
}

// Convert a signed byte to a byte (a narrowing conversion).     
sbyte sbyteValue = -16;
try {
   byte byteValue2 = Convert.ToByte(sbyteValue);
   Console.WriteLine("Converted the {0} value {1} to " +  
                                     "the {2} value {3:G}.", 
                                     sbyteValue.GetType().Name, 
                                     sbyteValue, 
                                     byteValue2.GetType().Name, 
                                     byteValue2);
}
catch (OverflowException) {
   Console.WriteLine("Unable to convert the {0} value {1}.", 
                                     sbyteValue.GetType().Name, sbyteValue);
}                                         
// The example displays the following output:
//       Converted the Int32 value 12534 to the Decimal value 12,534.00.
//       Converted the Byte value 255 to the Int32 value 255.
//       Converted the Double value 1.632513E+013 to the Int64 value 16,325,130,000,000.
//       Unable to convert the SByte value -16.
```

```vb
' Convert an Int32 value to a Decimal (a widening conversion).
Dim integralValue As Integer = 12534
Dim decimalValue As Decimal = Convert.ToDecimal(integralValue)
Console.WriteLine("Converted the {0} value {1} to the {2} value {3:N2}.", 
                  integralValue.GetType().Name,
                  integralValue,
                  decimalValue.GetType().Name,
                  decimalValue)

' Convert a Byte value to an Int32 value (a widening conversion).
Dim byteValue As Byte = Byte.MaxValue
Dim integralValue2 As Integer = Convert.ToInt32(byteValue)                                  
Console.WriteLine("Converted the {0} value {1} to " + 
                                  "the {2} value {3:G}.",
                                  byteValue.GetType().Name,
                                  byteValue,
                                  integralValue2.GetType().Name,
                                  integralValue2)

' Convert a Double value to an Int32 value (a narrowing conversion).
Dim doubleValue As Double = 16.32513e12
Try
   Dim longValue As Long = Convert.ToInt64(doubleValue)
   Console.WriteLine("Converted the {0} value {1:E} to " + 
                                     "the {2} value {3:N0}.",
                                     doubleValue.GetType().Name,
                                     doubleValue,
                                     longValue.GetType().Name,
                                     longValue)
Catch e As OverflowException
   Console.WriteLine("Unable to convert the {0:E} value {1}.",
                                     doubleValue.GetType().Name, doubleValue)
End Try                                                             

' Convert a signed byte to a byte (a narrowing conversion).     
Dim sbyteValue As SByte = -16
Try
   Dim byteValue2 As Byte = Convert.ToByte(sbyteValue)
   Console.WriteLine("Converted the {0} value {1} to " + 
                                     "the {2} value {3:G}.",
                                     sbyteValue.GetType().Name,
                                     sbyteValue,
                                     byteValue2.GetType().Name,
                                     byteValue2)
Catch e As OverflowException
   Console.WriteLine("Unable to convert the {0} value {1}.",
                                     sbyteValue.GetType().Name, sbyteValue)
End Try 
' The example displays the following output:
'       Converted the Int32 value 12534 to the Decimal value 12,534.00.
'       Converted the Byte value 255 to the Int32 value 255.
'       Converted the Double value 1.632513E+013 to the Int64 value 16,325,130,000,000.
'       Unable to convert the SByte value -16.
```

В некоторых случаях, особенно при преобразовании значений с плавающей запятой, преобразование может предполагать потерю точности, даже если исключение [OverflowException](xref:System.OverflowException) не создается. В следующем примере показана потеря точности. В этом случае значение [Decimal](xref:System.Decimal) после преобразования в [Double](xref:System.Double) имеет меньшую точность (меньше значимых цифр). Во втором случае при преобразовании значения [Double](xref:System.Double) оно округляется с **42,72** до **43**, чтобы было выполнено преобразование.

```csharp
double doubleValue; 

// Convert a Double to a Decimal.
decimal decimalValue = 13956810.96702888123451471211m;
doubleValue = Convert.ToDouble(decimalValue);
Console.WriteLine("{0} converted to {1}.", decimalValue, doubleValue);

doubleValue = 42.72;
try {
   int integerValue = Convert.ToInt32(doubleValue);
   Console.WriteLine("{0} converted to {1}.", 
                                     doubleValue, integerValue);
}
catch (OverflowException) {      
   Console.WriteLine("Unable to convert {0} to an integer.", 
                                     doubleValue);
}   
// The example displays the following output:
//       13956810.96702888123451471211 converted to 13956810.9670289.
//       42.72 converted to 43.
```

```vb
Dim doubleValue As Double 

' Convert a Double to a Decimal.
Dim decimalValue As Decimal = 13956810.96702888123451471211d
doubleValue = Convert.ToDouble(decimalValue)
Console.WriteLine("{0} converted to {1}.", decimalValue, doubleValue)

doubleValue = 42.72
Try
   Dim integerValue As Integer = Convert.ToInt32(doubleValue)
   Console.WriteLine("{0} converted to {1}.",
                                     doubleValue, integerValue)
Catch e As OverflowException
   Console.WriteLine("Unable to convert {0} to an integer.",
                                     doubleValue)
End Try   
' The example displays the following output:
'       13956810.96702888123451471211 converted to 13956810.9670289.
'       42.72 converted to 43.
```

Таблица, в которой перечислены расширяющие и сужающие преобразования, поддерживаемые классом [Convert](xref:System.Convert), представлена в разделе [Таблица преобразования типов](conversion-tables.md).

### <a name="custom-conversions-with-the-changetype-method"></a>Настраиваемые преобразования, использующие метод ChangeType

В дополнение к поддержке преобразований в каждый из базовых типов класс [Convert](xref:System.Convert) может использоваться для преобразования настраиваемых типов в один или несколько предопределенных типов. Это преобразование выполняется методом [Convert.ChangeType(Object, Type, IFormatProvider)](xref:System.Convert.ChangeType(System.Object,System.Type,System.IFormatProvider)), который, в свою очередь, служит оболочкой для вызова метода [IConvertible.ToType](xref:System.IConvertible.ToType(System.Type,System.IFormatProvider)) параметра значения. Это означает, что объект, представленный параметром значения, должен предоставить реализацию интерфейса [IConvertible](xref:System.IConvertible).

> [!NOTE]
> Поскольку методы [Convert.ChangeType(Object, Type)](xref:System.Convert.ChangeType(System.Object,System.Type)) и [Convert.ChangeType(Object, Type, IFormatProvider)](xref:System.Convert.ChangeType(System.Object,System.Type,System.IFormatProvider)) используют объект [Type](xref:System.Type) для указания типа целевого объекта, в который преобразуется значение, их можно использовать для выполнения динамического преобразования в объект, тип которого неизвестен во время компиляции. Однако обратите внимание, что реализация [IConvertible](xref:System.IConvertible) значения все равно должна поддерживать данное преобразование. 

В следующем примере показана возможная реализация интерфейса [IConvertible](xref:System.IConvertible), позволяющая преобразовать объект `TemperatureCelsius` в `TemperatureFahrenheit` или наоборот. В примере определяется базовый класс, `Temperature`, который реализует интерфейс [IConvertible](xref:System.IConvertible) и переопределяет метод [Object.ToString](xref:System.Object.ToString). Производные классы `TemperatureCelsius` и `TemperatureFahrenheit` переопределяют методы `ToType` и `ToString` базового класса. 

```csharp
using System;

public abstract class Temperature : IConvertible
{
   protected decimal temp;

   public Temperature(decimal temperature)
   {
      this.temp = temperature;
   }

   public decimal Value
   { 
      get { return this.temp; } 
      set { this.temp = Value; }        
   }

   public override string ToString()
   {
      return temp.ToString(null as IFormatProvider) + "º";
   }

   // IConvertible implementations.
   public TypeCode GetTypeCode() { 
      return TypeCode.Object;
   }   

   public bool ToBoolean(IFormatProvider provider) {
      throw new InvalidCastException(String.Format("Temperature-to-Boolean conversion is not supported."));
   }

   public byte ToByte(IFormatProvider provider) {
      if (temp < Byte.MinValue || temp > Byte.MaxValue)
         throw new OverflowException(String.Format("{0} is out of range of the Byte data type.", temp));
      else
         return (byte) temp;
   }

   public char ToChar(IFormatProvider provider) {
      throw new InvalidCastException("Temperature-to-Char conversion is not supported.");
   }

   public DateTime ToDateTime(IFormatProvider provider) {
      throw new InvalidCastException("Temperature-to-DateTime conversion is not supported.");
   }

   public decimal ToDecimal(IFormatProvider provider) {
      return temp;
   }

   public double ToDouble(IFormatProvider provider) {
      return (double) temp;
   }

   public short ToInt16(IFormatProvider provider) {
      if (temp < Int16.MinValue || temp > Int16.MaxValue)
         throw new OverflowException(String.Format("{0} is out of range of the Int16 data type.", temp));
      else
         return (short) Math.Round(temp);
   }

   public int ToInt32(IFormatProvider provider) {
      if (temp < Int32.MinValue || temp > Int32.MaxValue)
         throw new OverflowException(String.Format("{0} is out of range of the Int32 data type.", temp));
      else
         return (int) Math.Round(temp);
   }

   public long ToInt64(IFormatProvider provider) {
      if (temp < Int64.MinValue || temp > Int64.MaxValue)
         throw new OverflowException(String.Format("{0} is out of range of the Int64 data type.", temp));
      else
         return (long) Math.Round(temp);
   }

   public sbyte ToSByte(IFormatProvider provider) {
      if (temp < SByte.MinValue || temp > SByte.MaxValue)
         throw new OverflowException(String.Format("{0} is out of range of the SByte data type.", temp));
      else
         return (sbyte) temp;
   }

   public float ToSingle(IFormatProvider provider) {
      return (float) temp;
   }

   public virtual string ToString(IFormatProvider provider) {
      return temp.ToString(provider) + "°";
   }

   // If conversionType is implemented by another IConvertible method, call it.
   public virtual object ToType(Type conversionType, IFormatProvider provider) {
      switch (Type.GetTypeCode(conversionType))
      {
         case TypeCode.Boolean:
            return this.ToBoolean(provider);
         case TypeCode.Byte:
            return this.ToByte(provider);
         case TypeCode.Char:
            return this.ToChar(provider);
         case TypeCode.DateTime:
            return this.ToDateTime(provider);
         case TypeCode.Decimal:
            return this.ToDecimal(provider);
         case TypeCode.Double:
            return this.ToDouble(provider);
         case TypeCode.Empty:
            throw new NullReferenceException("The target type is null.");
         case TypeCode.Int16:
            return this.ToInt16(provider);
         case TypeCode.Int32:
            return this.ToInt32(provider);
         case TypeCode.Int64:
            return this.ToInt64(provider);
         case TypeCode.Object:
            // Leave conversion of non-base types to derived classes.
            throw new InvalidCastException(String.Format("Cannot convert from Temperature to {0}.", 
                                           conversionType.Name));
         case TypeCode.SByte:
            return this.ToSByte(provider);
         case TypeCode.Single:
            return this.ToSingle(provider);
         case TypeCode.String:
            IConvertible iconv = this;
            return iconv.ToString(provider);
         case TypeCode.UInt16:
            return this.ToUInt16(provider);
         case TypeCode.UInt32:
            return this.ToUInt32(provider);
         case TypeCode.UInt64:
            return this.ToUInt64(provider);
         default:
            throw new InvalidCastException("Conversion not supported.");
      }
   }

   public ushort ToUInt16(IFormatProvider provider) {
      if (temp < UInt16.MinValue || temp > UInt16.MaxValue)
         throw new OverflowException(String.Format("{0} is out of range of the UInt16 data type.", temp));
      else
         return (ushort) Math.Round(temp);
   }

   public uint ToUInt32(IFormatProvider provider) {
      if (temp < UInt32.MinValue || temp > UInt32.MaxValue)
         throw new OverflowException(String.Format("{0} is out of range of the UInt32 data type.", temp));
      else
         return (uint) Math.Round(temp);
   }

   public ulong ToUInt64(IFormatProvider provider) {
      if (temp < UInt64.MinValue || temp > UInt64.MaxValue)
         throw new OverflowException(String.Format("{0} is out of range of the UInt64 data type.", temp));
      else
         return (ulong) Math.Round(temp);
   }
}

public class TemperatureCelsius : Temperature, IConvertible
{
   public TemperatureCelsius(decimal value) : base(value)
   {
   }

   // Override ToString methods.
   public override string ToString()
   {
      return this.ToString(null);
   }

   public override string ToString(IFormatProvider provider)
   {
      return temp.ToString(provider) + "°C"; 
   }

   // If conversionType is a implemented by another IConvertible method, call it.
   public override object ToType(Type conversionType, IFormatProvider provider) {
      // For non-objects, call base method.
      if (Type.GetTypeCode(conversionType) != TypeCode.Object) {
         return base.ToType(conversionType, provider);
      }   
      else
      {   
         if (conversionType.Equals(typeof(TemperatureCelsius)))
            return this;
         else if (conversionType.Equals(typeof(TemperatureFahrenheit)))
            return new TemperatureFahrenheit((decimal) this.temp * 9 / 5 + 32);
         else
            throw new InvalidCastException(String.Format("Cannot convert from Temperature to {0}.", 
                                           conversionType.Name));
      }
   }
}

public class TemperatureFahrenheit : Temperature, IConvertible 
{
   public TemperatureFahrenheit(decimal value) : base(value)
   {
   }

   // Override ToString methods.
   public override string ToString()
   {
      return this.ToString(null);
   }

   public override string ToString(IFormatProvider provider)
   {
      return temp.ToString(provider) + "°F"; 
   }

   public override object ToType(Type conversionType, IFormatProvider provider)
   { 
      // For non-objects, call base methood.
      if (Type.GetTypeCode(conversionType) != TypeCode.Object) {
         return base.ToType(conversionType, provider);
      }   
      else
      {   
         // Handle conversion between derived classes.
         if (conversionType.Equals(typeof(TemperatureFahrenheit))) 
            return this;
         else if (conversionType.Equals(typeof(TemperatureCelsius)))
            return new TemperatureCelsius((decimal) (this.temp - 32) * 5 / 9);
         // Unspecified object type: throw an InvalidCastException.
         else
            throw new InvalidCastException(String.Format("Cannot convert from Temperature to {0}.", 
                                           conversionType.Name));
      }                                 
   }
}
```

```vb
Public MustInherit Class Temperature
   Implements IConvertible

   Protected temp As Decimal

   Public Sub New(temperature As Decimal)
      Me.temp = temperature
   End Sub

   Public Property Value As Decimal
      Get 
         Return Me.temp
      End Get
      Set
         Me.temp = Value
      End Set   
   End Property

   Public Overrides Function ToString() As String
      Return temp.ToString() & "º"
   End Function

   ' IConvertible implementations.
   Public Function GetTypeCode() As TypeCode Implements IConvertible.GetTypeCode
      Return TypeCode.Object
   End Function   

   Public Function ToBoolean(provider As IFormatProvider) As Boolean Implements IConvertible.ToBoolean
      Throw New InvalidCastException(String.Format("Temperature-to-Boolean conversion is not supported."))
   End Function

   Public Function ToByte(provider As IFormatProvider) As Byte Implements IConvertible.ToByte
      If temp < Byte.MinValue Or temp > Byte.MaxValue Then
         Throw New OverflowException(String.Format("{0} is out of range of the Byte data type.", temp))
      Else
         Return CByte(temp)
      End If    
   End Function

   Public Function ToChar(provider As IFormatProvider) As Char Implements IConvertible.ToChar
      Throw New InvalidCastException("Temperature-to-Char conversion is not supported.")
   End Function

   Public Function ToDateTime(provider As IFormatProvider) As DateTime Implements IConvertible.ToDateTime
      Throw New InvalidCastException("Temperature-to-DateTime conversion is not supported.")
   End Function

   Public Function ToDecimal(provider As IFormatProvider) As Decimal Implements IConvertible.ToDecimal
      Return temp
   End Function

   Public Function ToDouble(provider As IFormatProvider) As Double Implements IConvertible.ToDouble
      Return CDbl(temp)
   End Function

   Public Function ToInt16(provider As IFormatProvider) As Int16 Implements IConvertible.ToInt16
      If temp < Int16.MinValue Or temp > Int16.MaxValue Then
         Throw New OverflowException(String.Format("{0} is out of range of the Int16 data type.", temp))
      End If
      Return CShort(Math.Round(temp))
   End Function

   Public Function ToInt32(provider As IFormatProvider) As Int32 Implements IConvertible.ToInt32
      If temp < Int32.MinValue Or temp > Int32.MaxValue Then
         Throw New OverflowException(String.Format("{0} is out of range of the Int32 data type.", temp))
      End If
      Return CInt(Math.Round(temp))
   End Function

   Public Function ToInt64(provider As IFormatProvider) As Int64 Implements IConvertible.ToInt64
      If temp < Int64.MinValue Or temp > Int64.MaxValue Then
         Throw New OverflowException(String.Format("{0} is out of range of the Int64 data type.", temp))
      End If
      Return CLng(Math.Round(temp))
   End Function

   Public Function ToSByte(provider As IFormatProvider) As SByte Implements IConvertible.ToSByte
      If temp < SByte.MinValue Or temp > SByte.MaxValue Then
         Throw New OverflowException(String.Format("{0} is out of range of the SByte data type.", temp))
      Else
         Return CSByte(temp)
      End If    
   End Function

   Public Function ToSingle(provider As IFormatProvider) As Single Implements IConvertible.ToSingle
      Return CSng(temp)
   End Function

   Public Overridable Overloads Function ToString(provider As IFormatProvider) As String Implements IConvertible.ToString
      Return temp.ToString(provider) & " °C"
   End Function

   ' If conversionType is a implemented by another IConvertible method, call it.
   Public Overridable Function ToType(conversionType As Type, provider As IFormatProvider) As Object Implements IConvertible.ToType
      Select Case Type.GetTypeCode(conversionType)
         Case TypeCode.Boolean
            Return Me.ToBoolean(provider)
         Case TypeCode.Byte
            Return Me.ToByte(provider)
         Case TypeCode.Char
            Return Me.ToChar(provider)   
         Case TypeCode.DateTime
            Return Me.ToDateTime(provider)
         Case TypeCode.Decimal
            Return Me.ToDecimal(provider)
         Case TypeCode.Double
            Return Me.ToDouble(provider)
         Case TypeCode.Empty
            Throw New NullReferenceException("The target type is null.")
         Case TypeCode.Int16
            Return Me.ToInt16(provider)
         Case TypeCode.Int32
            Return Me.ToInt32(provider)
         Case TypeCode.Int64
            Return Me.ToInt64(provider)
         Case TypeCode.Object
            ' Leave conversion of non-base types to derived classes.
            Throw New InvalidCastException(String.Format("Cannot convert from Temperature to {0}.", _
                                           conversionType.Name))
         Case TypeCode.SByte
            Return Me.ToSByte(provider)
         Case TypeCode.Single
            Return Me.ToSingle(provider)
         Case TypeCode.String
            Return Me.ToString(provider)
         Case TypeCode.UInt16
            Return Me.ToUInt16(provider)
         Case TypeCode.UInt32
            Return Me.ToUInt32(provider)
         Case TypeCode.UInt64
            Return Me.ToUInt64(provider)
         Case Else
            Throw New InvalidCastException("Conversion not supported.")   
      End Select
   End Function

   Public Function ToUInt16(provider As IFormatProvider) As UInt16 Implements IConvertible.ToUInt16
      If temp < UInt16.MinValue Or temp > UInt16.MaxValue Then
         Throw New OverflowException(String.Format("{0} is out of range of the UInt16 data type.", temp))
      End If
      Return CUShort(Math.Round(temp))
   End Function

   Public Function ToUInt32(provider As IFormatProvider) As UInt32 Implements IConvertible.ToUInt32
      If temp < UInt32.MinValue Or temp > UInt32.MaxValue Then
         Throw New OverflowException(String.Format("{0} is out of range of the UInt32 data type.", temp))
      End If
      Return CUInt(Math.Round(temp))
   End Function

   Public Function ToUInt64(provider As IFormatProvider) As UInt64 Implements IConvertible.ToUInt64
      If temp < UInt64.MinValue Or temp > UInt64.MaxValue Then
         Throw New OverflowException(String.Format("{0} is out of range of the UInt64 data type.", temp))
      End If
      Return CULng(Math.Round(temp))
   End Function
End Class

Public Class TemperatureCelsius : Inherits Temperature : Implements IConvertible
   Public Sub New(value As Decimal)
      MyBase.New(value)
   End Sub

   ' Override ToString methods.
   Public Overrides Function ToString() As String
      Return Me.ToString(Nothing)
   End Function

   Public Overrides Function ToString(provider As IFormatProvider ) As String
      Return temp.ToString(provider) + "°C" 
   End Function

  ' If conversionType is a implemented by another IConvertible method, call it.
   Public Overrides Function ToType(conversionType As Type, provider As IFormatProvider) As Object
      ' For non-objects, call base method.
      If Type.GetTypeCode(conversionType) <> TypeCode.Object Then
         Return MyBase.ToType(conversionType, provider)
      Else   
         If conversionType.Equals(GetType(TemperatureCelsius)) Then
            Return Me
         ElseIf conversionType.Equals(GetType(TemperatureFahrenheit))
            Return New TemperatureFahrenheit(CDec(Me.temp * 9 / 5 + 32))
         ' Unspecified object type: throw an InvalidCastException.
         Else
            Throw New InvalidCastException(String.Format("Cannot convert from Temperature to {0}.", _ 
                                           conversionType.Name))
         End If
      End If                                  
   End Function
End Class

Public Class TemperatureFahrenheit : Inherits Temperature : Implements IConvertible
   Public Sub New(value As Decimal)
      MyBase.New(value)
   End Sub

   ' Override ToString methods.
   Public Overrides Function ToString() As String
      Return Me.ToString(Nothing)
   End Function

   Public Overrides Function ToString(provider As IFormatProvider ) As String
      Return temp.ToString(provider) + "°F" 
   End Function

   Public Overrides Function ToType(conversionType As Type, provider As IFormatProvider) As Object
      ' For non-objects, call base methood.
      If Type.GetTypeCode(conversionType) <> TypeCode.Object Then
         Return MyBase.ToType(conversionType, provider)
      Else   
         ' Handle conversion between derived classes.
         If conversionType.Equals(GetType(TemperatureFahrenheit)) Then 
            Return Me
         ElseIf conversionType.Equals(GetType(TemperatureCelsius))
            Return New TemperatureCelsius(CDec((MyBase.temp - 32) * 5 / 9))
         ' Unspecified object type: throw an InvalidCastException.
         Else
            Throw New InvalidCastException(String.Format("Cannot convert from Temperature to {0}.", _
                                           conversionType.Name))
         End If
      End If                                  
   End Function
End Class
```

В следующем примере показано несколько вызовов реализаций интерфейса [IConvertible](xref:System.IConvertible) для преобразования объектов `TemperatureCelsius` в объекты `TemperatureFahrenheit` и наоборот.

```csharp
TemperatureCelsius tempC1 = new TemperatureCelsius(0);
TemperatureFahrenheit tempF1 = (TemperatureFahrenheit) Convert.ChangeType(tempC1, typeof(TemperatureFahrenheit), null);
Console.WriteLine("{0} equals {1}.", tempC1, tempF1);
TemperatureCelsius tempC2 = (TemperatureCelsius) Convert.ChangeType(tempC1, typeof(TemperatureCelsius), null);
Console.WriteLine("{0} equals {1}.", tempC1, tempC2);
TemperatureFahrenheit tempF2 = new TemperatureFahrenheit(212);
TemperatureCelsius tempC3 = (TemperatureCelsius) Convert.ChangeType(tempF2, typeof(TemperatureCelsius), null);
Console.WriteLine("{0} equals {1}.", tempF2, tempC3);
TemperatureFahrenheit tempF3 = (TemperatureFahrenheit) Convert.ChangeType(tempF2, typeof(TemperatureFahrenheit), null);
Console.WriteLine("{0} equals {1}.", tempF2, tempF3);
// The example displays the following output:
//       0°C equals 32°F.
//       0°C equals 0°C.
//       212°F equals 100°C.
//       212°F equals 212°F.
```

```vb
Dim tempC1 As New TemperatureCelsius(0)
Dim tempF1 As TemperatureFahrenheit = CType(Convert.ChangeType(tempC1, GetType(TemperatureFahrenheit), Nothing), TemperatureFahrenheit)
Console.WriteLine("{0} equals {1}.", tempC1, tempF1) 
Dim tempC2 As TemperatureCelsius = CType(Convert.ChangeType(tempC1, GetType(TemperatureCelsius), Nothing), TemperatureCelsius)
Console.WriteLine("{0} equals {1}.", tempC1, tempC2) 
Dim tempF2 As New TemperatureFahrenheit(212)
Dim tempC3 As TEmperatureCelsius = CType(Convert.ChangeType(tempF2, GEtType(TemperatureCelsius), Nothing), TemperatureCelsius)
Console.WriteLine("{0} equals {1}.", tempF2, tempC3) 
Dim tempF3 As TemperatureFahrenheit = CType(Convert.ChangeType(tempF2, GetType(TemperatureFahrenheit), Nothing), TemperatureFahrenheit)
Console.WriteLine("{0} equals {1}.", tempF2, tempF3)
' The example displays the following output:
'       0°C equals 32°F.
'       0°C equals 0°C.
'       212°F equals 100°C.
'       212°F equals 212°F.
```

## <a name="the-typeconverter-class"></a>Класс TypeConverter

Платформа .NET также позволяет определить преобразователь типов для пользовательского типа путем расширения класса [System.ComponentModel.TypeConverter](xref:System.ComponentModel.TypeConverter) и сопоставления преобразователя с типом через атрибут [System.ComponentModel.TypeConverterAttribute](xref:System.ComponentModel.TypeConverterAttribute). В следующей таблице выделены различия между этим подходом и реализацией интерфейса [IConvertible](xref:System.IConvertible) для настраиваемого типа.

> [!NOTE]
> Поддержка во время разработки может быть предоставлена для настраиваемого типа лишь при условии, что для него определен преобразователь типа.

Преобразование с использованием TypeConverter | Преобразование с использованием IConvertible
------------------------------ | -----------------------------
Реализуется для настраиваемого типа посредством создания отдельного класса-наследника [TypeConverter](xref:System.ComponentModel.TypeConverter). Производный класс связывается с настраиваемым типом посредством атрибута [TypeConverterAttribute](xref:System.ComponentModel.TypeConverterAttribute). | Реализуется настраиваемым типом для выполнения преобразования. Пользователь типа вызывает метод преобразования [IConvertible](xref:System.IConvertible) для типа.
Может использоваться как во время разработки, так и во время выполнения. | Может использоваться только во время выполнения.
Использует отражение, поэтому выполняется медленнее, чем преобразование, использующее [IConvertible](xref:System.IConvertible). | Не использует отражения.
Обеспечивает двустороннее преобразование настраиваемого типа в другие типы данных и наоборот. Например, тип [TypeConverter](xref:System.ComponentModel.TypeConverter), определенный для `MyType`, позволяет выполнять преобразования из `MyType` в [String](xref:System.String) и из [String](xref:System.String) в `MyType`. | Обеспечивает преобразование из настраиваемого типа в другие типы данных, но не наоборот.

Дополнительные сведения о выполнении преобразований с помощью преобразователей типов см. в разделе [System.ComponentModel.TypeConverter](xref:System.ComponentModel.TypeConverter).

## <a name="see-also"></a>См. также

[System.Convert](xref:System.Convert)

[IConvertible](xref:System.IConvertible)

[Таблицы преобразования типов](conversion-tables.md)
