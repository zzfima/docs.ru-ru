---
title: Явные и неявные преобразования (Visual Basic)
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
ms.openlocfilehash: 09d96b304ba3bcf2a9de2812ce37ae69dba73a41
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43396598"
---
# <a name="implicit-and-explicit-conversions-visual-basic"></a>Явные и неявные преобразования (Visual Basic)
*Неявное преобразование* не требует специального синтаксиса в исходном коде. В следующем примере Visual Basic неявно преобразует значение `k` значение с плавающей запятой одиночной точности, перед назначением его `q`.  
  
```  
Dim k As Integer  
Dim q As Double  
' Integer widens to Double, so you can do this with Option Strict On.  
k = 432  
q = k  
```  
  
 *Явное преобразование* используется ключевое слово преобразования типа. Visual Basic предоставляет несколько зарезервированных слов, которые приводят выражение в круглые скобки, чтобы в нужный тип данных. Эти ключевые слова действуют аналогично функциям, но компилятор создает встроенный код, поэтому выполнение будет немного быстрее, чем при вызове функции.  
  
 В следующее расширение в предыдущем примере `CInt` ключевое слово преобразует значение `q` обратно в целое число перед назначением его `k`.  
  
```  
' q had been assigned the value 432 from k.  
q = Math.Sqrt(q)  
k = CInt(q)  
' k now has the value 21 (rounded square root of 432).  
```  
  
## <a name="conversion-keywords"></a>Ключевые слова преобразований  
 В следующей таблице показаны ключевые слова преобразований.  
  
|Ключевое слово преобразования типа|Преобразует выражение в тип данных|Допустимые типы данных выражение для преобразования|  
|---|---|---|  
|`CBool`|[Логический тип данных](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `String`, `Object`|  
|`CByte`|[Тип данных Byte](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|Любой числовой тип (включая `SByte` и типы перечисления), `Boolean`, `String`, `Object`|  
|`CChar`|[Тип данных Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)|`String`, `Object`|  
|`CDate`|[Тип данных Date](../../../../visual-basic/language-reference/data-types/date-data-type.md)|`String`, `Object`|  
|`CDbl`|[Тип данных Double](../../../../visual-basic/language-reference/data-types/double-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`, `Object`|  
|`CDec`|[Тип данных Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`, `Object`|  
|`CInt`|[Тип данных Integer](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`, `Object`|  
|`CLng`|[Тип данных Long](../../../../visual-basic/language-reference/data-types/long-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`, `Object`|  
|`CObj`|[Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)|Любой тип|  
|`CSByte`|[Тип данных SByte](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|Любой числовой тип (включая `Byte` и типы перечисления), `Boolean`, `String`, `Object`|  
|`CShort`|[Тип данных Short](../../../../visual-basic/language-reference/data-types/short-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`, `Object`|  
|`CSng`|[Тип данных Single](../../../../visual-basic/language-reference/data-types/single-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`, `Object`|  
|`CStr`|[Тип данных String](../../../../visual-basic/language-reference/data-types/string-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `Char`, `Char` массива, `Date`, `Object`|  
|`CType`|Тип, заданный после запятой (`,`)|При преобразовании в *простой тип данных* типов (включая массив простейших типов), так же, как для соответствующих зарезервированных слов преобразования<br /><br /> При преобразовании в *составной тип данных*, он реализует интерфейсы и классы, от которых он наследует<br /><br /> При преобразовании в класс или структура, в которой имеются перегруженные `CType`, класса или структуры|  
|`CUInt`|[Тип данных UInteger](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`, `Object`|  
|`CULng`|[Тип данных ULong](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`, `Object`|  
|`CUShort`|[Тип данных UShort](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`, `Object`|  
  
## <a name="the-ctype-function"></a>Функция CType  
 [Функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md) имеет два аргумента. Первый — это выражение для преобразования, а вторым – класс типа или объект назначения данных. Обратите внимание на то, что первый аргумент должен быть выражением, а не типом.  
  
 `CType` — *встроенная функция*, то есть скомпилированный код делает преобразование, часто без формирования функцию вызвать. Это повышает производительность.  
  
 Сравнение `CType` с других ключевых слов преобразования типов, см. в разделе [оператор DirectCast](../../../../visual-basic/language-reference/operators/directcast-operator.md) и [оператор TryCast](../../../../visual-basic/language-reference/operators/trycast-operator.md).  
  
### <a name="elementary-types"></a>Простые типы  
 В следующем примере показано использование функции `CType`.  
  
```  
k = CType(q, Integer)  
' The following statement coerces w to the specific object class Label.  
f = CType(w, Label)  
```  
  
### <a name="composite-types"></a>Составные типы  
 Можно использовать `CType` для преобразования значений в составные типы данных также относительно простыми типами. Можно также используется для присвоения объекту класса тип одного из интерфейсов, как показано в следующем примере.  
  
```  
' Assume class cZone implements interface iZone.  
Dim h As Object  
' The first argument to CType must be an expression, not a type.  
Dim cZ As cZone  
' The following statement coerces a cZone object to its interface iZone.  
h = CType(cZ, iZone)  
```  
  
### <a name="array-types"></a>Типы массивов  
 `CType` также можно преобразовать типы данных массивов, как показано в следующем примере.  
  
```  
Dim v() As classV  
Dim obArray() As Object  
' Assume some object array has been assigned to obArray.  
' Check for run-time type compatibility.  
If TypeOf obArray Is classV()  
    ' obArray can be converted to classV.  
    v = CType(obArray, classV())  
End If  
```  
  
 Дополнительные сведения и пример см. в разделе [преобразования массивов](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md).  
  
### <a name="types-defining-ctype"></a>Типы, определение CType  
 Вы можете определить `CType` для класса или структуры, которые вы определили. Это позволяет преобразовывать значения из типа класса или структуры. Дополнительные сведения и пример см. в разделе [как: определение оператора преобразования](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
> [!NOTE]
>  Значения, используемые с ключевым словом преобразование должно быть допустимым для целевого типа данных, или произошла ошибка. Например, если при попытке преобразовать `Long` для `Integer`, значение `Long` должно быть в допустимом диапазоне для `Integer` тип данных.  
  
> [!CAUTION]
>  Указание `CType` для преобразования из одного типа класса в другой вызовет ошибку во время выполнения, если исходный тип не является производным от типа назначения. Такой сбой вызывает <xref:System.InvalidCastException> исключение.  
  
 Тем не менее если один из типов структуры или класса, вы определили, а также если вы определили `CType` для структуры или класса, преобразование может быть успешным, если он удовлетворяет требованиям вашего `CType`. См. в разделе [как: определение оператора преобразования](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
 Выполнение явного преобразования также называется *приведения* выражение к классу данных типа или объекта.  
  
## <a name="see-also"></a>См. также  
 [Преобразование типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Преобразования значений между строковыми и другими типами](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [Практическое: преобразование объекта в другой тип в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [Структуры](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Типы данных](../../../../visual-basic/language-reference/data-types/index.md)  
 [Функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
