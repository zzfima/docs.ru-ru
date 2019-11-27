---
title: Явные и неявные преобразования
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [Visual Basic], type
- variables [Visual Basic], changing data type
- casting
- conversions [Visual Basic], data type
- type conversion [Visual Basic], implicit conversions
- CType function [Visual Basic], conversions
- casting, data types
- data type conversion [Visual Basic], explicit
- type conversion [Visual Basic], explicit conversions
- data types [Visual Basic], casting
- conversions [Visual Basic], implicit
- explicit data type conversions [Visual Basic]
- conversions [Visual Basic]
- changing data types [Visual Basic]
- conversions [Visual Basic], explicit
- data type conversion [Visual Basic], implicit
- implicit data type conversions [Visual Basic]
ms.assetid: 77de1659-af8a-492c-967e-e7ef60ccce66
ms.openlocfilehash: b7215933cec89b7023f08e8996a283b39b3a3c83
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346360"
---
# <a name="implicit-and-explicit-conversions-visual-basic"></a>Явные и неявные преобразования (Visual Basic)

*Неявное преобразование* не требует специального синтаксиса в исходном коде. В следующем примере Visual Basic неявно преобразует значение `k` в значение с плавающей запятой одиночной точности перед тем, как назначить его `q`.

```vb
Dim k As Integer
Dim q As Double
' Integer widens to Double, so you can do this with Option Strict On.
k = 432
q = k
```

При *явном преобразовании* используется ключевое слово преобразования типа. Visual Basic предоставляет несколько таких ключевых слов, которые применяют выражение в круглых скобках к требуемому типу данных. Эти ключевые слова действуют как функции, но компилятор создает встроенный код, поэтому выполнение выполняется немного быстрее, чем с помощью вызова функции.

В следующем расширении предыдущего примера ключевое слово `CInt` преобразует значение `q` обратно в целое число перед тем, как назначить его `k`.

```vb
' q had been assigned the value 432 from k.
q = Math.Sqrt(q)
k = CInt(q)
' k now has the value 21 (rounded square root of 432).
```

## <a name="conversion-keywords"></a>Ключевые слова преобразований

В следующей таблице приведены доступные ключевые слова для преобразования.

|Ключевое слово преобразования типа|Преобразует выражение в тип данных|Допустимые типы данных выражения для преобразования|
|---|---|---|
|`CBool`|[Логический тип данных](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и перечислимые типы), `String``Object`|
|`CByte`|[Тип данных Byte](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|Любой числовой тип (включая `SByte` и перечисляемые типы), `Boolean`, `String`, `Object`|
|`CChar`|[Тип данных Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)|`String`, `Object`|
|`CDate`|[Тип данных Date](../../../../visual-basic/language-reference/data-types/date-data-type.md)|`String`, `Object`|
|`CDbl`|[Тип данных Double](../../../../visual-basic/language-reference/data-types/double-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и перечислимые типы), `Boolean`, `String`, `Object`|
|`CDec`|[Тип данных Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и перечислимые типы), `Boolean`, `String`, `Object`|
|`CInt`|[Тип данных Integer](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и перечислимые типы), `Boolean`, `String`, `Object`|
|`CLng`|[Тип данных Long](../../../../visual-basic/language-reference/data-types/long-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и перечислимые типы), `Boolean`, `String`, `Object`|
|`CObj`|[Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)|Любой тип|
|`CSByte`|[Тип данных SByte](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|Любой числовой тип (включая `Byte` и перечисляемые типы), `Boolean`, `String`, `Object`|
|`CShort`|[Тип данных Short](../../../../visual-basic/language-reference/data-types/short-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и перечислимые типы), `Boolean`, `String`, `Object`|
|`CSng`|[Тип данных Single](../../../../visual-basic/language-reference/data-types/single-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и перечислимые типы), `Boolean`, `String`, `Object`|
|`CStr`|[Тип данных String](../../../../visual-basic/language-reference/data-types/string-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и перечисляемые типы), `Boolean`, `Char`, `Char` Array, `Date`, `Object`|
|`CType`|Тип, указанный после запятой (`,`)|При преобразовании в *простейший тип данных* (включая массив простейшего типа) типы, допустимые для соответствующего ключевого слова преобразования<br /><br /> При преобразовании в *составной тип данных*интерфейсы, которые он реализует, и классы, от которых он наследует<br /><br /> При преобразовании в класс или структуру, в которой имеется перегруженный `CType`, этот класс или структура|
|`CUInt`|[Тип данных UInteger](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и перечислимые типы), `Boolean`, `String`, `Object`|
|`CULng`|[Тип данных ULong](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и перечислимые типы), `Boolean`, `String`, `Object`|
|`CUShort`|[Тип данных UShort](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и перечислимые типы), `Boolean`, `String`, `Object`|

## <a name="the-ctype-function"></a>Функция CType

[Функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md) работает с двумя аргументами. Первое — выражение, которое необходимо преобразовать, а второе — целевой тип данных или класс объекта. Обратите внимание, что первый аргумент должен быть выражением, а не типом.

`CType` является *встроенной функцией*, то есть скомпилированный код выполняет преобразование, часто без создания вызова функции. Это повышает производительность.

Сравнение `CType` с другими ключевыми словами преобразования типов см. в разделе Оператор [DirectCast](../../../../visual-basic/language-reference/operators/directcast-operator.md) и [Оператор TryCast](../../../../visual-basic/language-reference/operators/trycast-operator.md).

### <a name="elementary-types"></a>Простые типы

В следующем примере показано использование функции `CType`.

```vb
k = CType(q, Integer)
' The following statement coerces w to the specific object class Label.
f = CType(w, Label)
```

### <a name="composite-types"></a>Составные типы

`CType` можно использовать для преобразования значений в составные типы данных, а также в простые типы. Его также можно использовать для приведения класса объекта к типу одного из его интерфейсов, как показано в следующем примере.

```vb
' Assume class cZone implements interface iZone.
Dim h As Object
' The first argument to CType must be an expression, not a type.
Dim cZ As cZone
' The following statement coerces a cZone object to its interface iZone.
h = CType(cZ, iZone)
```

### <a name="array-types"></a>Типы массивов

`CType` также могут преобразовываться типы данных массива, как показано в следующем примере.

```vb
Dim v() As classV
Dim obArray() As Object
' Assume some object array has been assigned to obArray.
' Check for run-time type compatibility.
If TypeOf obArray Is classV()
    ' obArray can be converted to classV.
    v = CType(obArray, classV())
End If
```

Дополнительные сведения и пример см. в разделе [Преобразование массивов](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md).

### <a name="types-defining-ctype"></a>Типы, определяющие CType

`CType` можно определить для класса или структуры, которые вы определили. Это позволяет преобразовать значения в тип класса или структуры и из него. Дополнительные сведения и пример см. в разделе [инструкции. Определение оператора преобразования](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).

> [!NOTE]
> Значения, используемые с ключевым словом преобразования, должны быть допустимыми для целевого типа данных, иначе возникает ошибка. Например, при попытке преобразовать `Long` в `Integer`значение `Long` должно находиться в пределах допустимого диапазона для `Integer`ного типа данных.

> [!CAUTION]
> Указание `CType` для преобразования из одного типа класса в другой завершается ошибкой во время выполнения, если исходный тип не является производным от целевого типа. Такой сбой вызывает исключение <xref:System.InvalidCastException>.

Однако если один из типов является определенной структурой или классом, и если вы определили `CType` в этой структуре или классе, то преобразование может быть выполнено успешно, если оно удовлетворяет требованиям `CType`. См. раздел [как определить оператор преобразования](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).

Выполнение явного преобразования также называется *приведением* выражения к заданному типу данных или классу объекта.

## <a name="see-also"></a>См. также

- [Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Преобразования значений между строковыми и другими типами](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [Как преобразовать объект в другой тип в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [Структуры](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Типы данных](../../../../visual-basic/language-reference/data-types/index.md)
- [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
