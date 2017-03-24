---
title: "Явные и неявные преобразования (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- conversions, type
- variables [Visual Basic], changing data type
- casting
- conversions, data type
- type conversion, implicit conversions
- CType function, conversions
- casting, data types
- data type conversion, explicit
- type conversion, explicit conversions
- data types [Visual Basic], casting
- conversions, implicit
- explicit data type conversions
- conversions
- changing data types
- conversions, explicit
- data type conversion, implicit
- implicit data type conversions
ms.assetid: 77de1659-af8a-492c-967e-e7ef60ccce66
caps.latest.revision: 25
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 24c434df4be480c290b3e4e36bd9f294d12b99ef
ms.lasthandoff: 03/13/2017

---
# <a name="implicit-and-explicit-conversions-visual-basic"></a>Явные и неявные преобразования (Visual Basic)
*Неявное преобразование* не требуют специального синтаксиса в исходном коде. В следующем примере [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] неявно преобразует значение `k` в значение с плавающей запятой одиночной точности, перед назначением их `q`.  
  
```  
Dim k As Integer  
Dim q As Double  
' Integer widens to Double, so you can do this with Option Strict On.  
k = 432  
q = k  
```  
  
 *Явное преобразование* используется ключевое слово преобразования типа. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]предоставляет несколько зарезервированных слов, которые приводят выражение в скобках для нужного типа данных. Эти ключевые слова действуют аналогично функциям, но компилятор создает встроенный код, поэтому выполнение будет несколько быстрее, чем при вызове функции.  
  
 В следующем расширении предыдущего примера `CInt` ключевое слово преобразует значение `q` обратно в целое перед его присвоением `k`.  
  
```  
' q had been assigned the value 432 from k.  
q = Math.Sqrt(q)  
k = CInt(q)  
' k now has the value 21 (rounded square root of 432).  
```  
  
## <a name="conversion-keywords"></a>Ключевые слова преобразований  
 В следующей таблице показаны допустимые зарезервированные слова преобразования.  
  
|Ключевое слово преобразования типа|Преобразует выражение в тип данных|Допустимые типы данных преобразуемого выражения|  
|---|---|---|  
|`CBool`|[Логический тип данных](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `String`,`Object`|  
|`CByte`|[Тип данных Byte](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|Любой числовой тип (включая `SByte` и типы перечисления), `Boolean`, `String`,`Object`|  
|`CChar`|[Тип данных Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)|`String`, `Object`|  
|`CDate`|[Тип данных Date](../../../../visual-basic/language-reference/data-types/date-data-type.md)|`String`, `Object`|  
|`CDbl`|[Тип данных Double](../../../../visual-basic/language-reference/data-types/double-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`,`Object`|  
|`CDec`|[Тип данных Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`,`Object`|  
|`CInt`|[Тип данных Integer](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`,`Object`|  
|`CLng`|[Тип данных Long](../../../../visual-basic/language-reference/data-types/long-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`,`Object`|  
|`CObj`|[Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)|Любой тип|  
|`CSByte`|[Тип данных SByte](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|Любой числовой тип (включая `Byte` и типы перечисления), `Boolean`, `String`,`Object`|  
|`CShort`|[Тип данных Short](../../../../visual-basic/language-reference/data-types/short-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`,`Object`|  
|`CSng`|[Тип данных Single](../../../../visual-basic/language-reference/data-types/single-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`,`Object`|  
|`CStr`|[Тип данных String](../../../../visual-basic/language-reference/data-types/string-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `Char`, `Char` массива, `Date`,`Object`|  
|`CType`|Тип, заданный после запятой (`,`)|При преобразовании в *простой тип данных* (включая массив простейших типов), же типы, которые разрешены для соответствующих зарезервированных слов преобразования<br /><br /> При преобразовании в *составного типа*, он реализует интерфейсы и классы, от которых они наследуются<br /><br /> При преобразовании класса или структуры, в которой имеются перегруженные `CType`, класса или структуры|  
|`CUInt`|[Тип данных UInteger](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`,`Object`|  
|`CULng`|[Тип данных ULong](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`,`Object`|  
|`CUShort`|[Тип данных UShort](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|Любой числовой тип (включая `Byte`, `SByte`и типы перечисления), `Boolean`, `String`,`Object`|  
  
## <a name="the-ctype-function"></a>Функция CType  
 [Функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md) имеет два аргумента. Во-первых, преобразуемое выражение, а второй — класс тип или объект назначения данных. Обратите внимание, что первый аргумент должен быть выражением, а не тип.  
  
 `CType`— *встроенная функция*, то есть скомпилированный код делает преобразование, часто без создания функции вызова. Это повышает производительность.  
  
 Сравнение `CType` с другим типом зарезервированных слов преобразования, в разделе [оператор DirectCast](../../../../visual-basic/language-reference/operators/directcast-operator.md) и [оператор TryCast](../../../../visual-basic/language-reference/operators/trycast-operator.md).  
  
### <a name="elementary-types"></a>Простые типы  
 В следующем примере показано использование функции `CType`.  
  
```  
k = CType(q, Integer)  
' The following statement coerces w to the specific object class Label.  
f = CType(w, Label)  
```  
  
### <a name="composite-types"></a>Составные типы  
 Можно использовать `CType` для преобразования значений в составной данных типов, а также простые типы. Его также можно использовать для присвоения класса объекта типу одного из его интерфейсов, как показано в следующем примере.  
  
```  
' Assume class cZone implements interface iZone.  
Dim h As Object  
' The first argument to CType must be an expression, not a type.  
Dim cZ As cZone  
' The following statement coerces a cZone object to its interface iZone.  
h = CType(cZ, iZone)  
```  
  
### <a name="array-types"></a>Типы массивов  
 `CType`также можно преобразовать типы данных массивов, как показано в следующем примере.  
  
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
  
 Дополнительные сведения и пример см. в разделе [преобразования массива](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md).  
  
### <a name="types-defining-ctype"></a>Типы, определение CType  
 Можно определить `CType` в классе или структуре, определенных вами. Это дает возможность преобразования значений из типа класса или структуры. Дополнительные сведения и пример см. в разделе [Практическое руководство: определение оператора преобразования](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
> [!NOTE]
>  Значения, используемые с ключевым словом преобразования должен быть допустимым для целевого типа данных, или произошла ошибка. Например, если при попытке преобразовать `Long` для `Integer`, значение `Long` должно быть в пределах допустимого диапазона для `Integer` тип данных.  
  
> [!CAUTION]
>  Указание `CType` для преобразования из одного типа класса в другой вызовет ошибку во время выполнения, если тип источника не является производным от конечного типа. Такой сбой вызовет исключение <xref:System.InvalidCastException>исключение.</xref:System.InvalidCastException>  
  
 Тем не менее если один из типов является структурой или определения класса, а определены `CType` для структуры или класса, преобразование может быть успешным, если оно удовлетворяет требованиям вашего `CType`. В разделе [Практическое руководство: определение оператора преобразования](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
 Выполнение явного преобразования называется также *приведение* выражение для данных типа или объект класса.  
  
## <a name="see-also"></a>См. также  
 [Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Преобразование между строковыми и другими типами](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)   
 [Практическое руководство: преобразование объекта к другому типу в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)   
 [Структуры](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
