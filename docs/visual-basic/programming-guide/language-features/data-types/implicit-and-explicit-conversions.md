---
title: "Явные и неявные преобразования (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "приведение"
  - "приведение, типы данных"
  - "изменение типов данных"
  - "преобразования"
  - "преобразования, тип данных"
  - "преобразования, явные"
  - "преобразования, неявные"
  - "преобразования, тип"
  - "CType - функция, преобразования"
  - "преобразование типов данных, явные"
  - "преобразование типов данных, неявные"
  - "типы данных [Visual Basic], приведение"
  - "явное преобразование типов данных"
  - "неявное преобразование типов данных"
  - "преобразование типов, явные преобразования"
  - "преобразование типов, неявные преобразования"
  - "переменные [Visual Basic], изменение типа данных"
ms.assetid: 77de1659-af8a-492c-967e-e7ef60ccce66
caps.latest.revision: 25
caps.handback.revision: 25
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Явные и неявные преобразования (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

*implicit conversion* не требует специального синтаксиса в исходном коде.  В следующем примере [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] неявно преобразует значение `k` в значение одинарной точности с плавающей запятой перед его присвоением `q`.  
  
```  
Dim k As Integer  
Dim q As Double  
' Integer widens to Double, so you can do this with Option Strict On.  
k = 432  
q = k  
```  
  
 При *явном преобразовании* используется ключевое слово преобразования типа.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] предоставляет несколько зарезервированных слов, которые приводят выражение в скобках к нужному типу данных.  Эти ключевые слова действуют аналогично функциям, но компилятор создает встроенный код, и поэтому его выполнение будет несколько быстрее, чем при вызове функции.  
  
 В следующем расширении предыдущего примера ключевое слово `CInt` преобразует значение `q` обратно в целое перед его присвоением `k`.  
  
```  
' q had been assigned the value 432 from k.  
q = Math.Sqrt(q)  
k = CInt(q)  
' k now has the value 21 (rounded square root of 432).  
```  
  
## Ключевые слова преобразований  
 В следующей таблице показаны допустимые зарезервированные слова преобразования.  
  
||||  
|-|-|-|  
|Ключевое слово преобразования типа|Преобразует выражение в тип данных|Типы данных, разрешенные для преобразуемого выражения|  
|`CBool`|[Тип данных Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Любой числовой тип \(включая `Byte`, `SByte` и типы перечисления\) `String`, `Object`|  
|`CByte`|[Тип данных Byte](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|Любой числовой тип \(включая `SByte` и перечисляемые типы\), `Boolean`, `String`, `Object`|  
|`CChar`|[Тип данных Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)|`String`, `Object`|  
|`CDate`|[Тип данных Date](../../../../visual-basic/language-reference/data-types/date-data-type.md)|`String`, `Object`|  
|`CDbl`|[Тип данных Double](../../../../visual-basic/language-reference/data-types/double-data-type.md)|Любой числовой тип \(включая `Byte`, `SByte` и типы перечисления\), `Boolean`, `String`, `Object`|  
|`CDec`|[Тип данных Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|Любой числовой тип \(включая `Byte`, `SByte` и типы перечисления\), `Boolean`, `String`, `Object`|  
|`CInt`|[Тип данных Integer](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|Любой числовой тип \(включая `Byte`, `SByte` и типы перечисления\), `Boolean`, `String`, `Object`|  
|`CLng`|[Тип данных Long](../../../../visual-basic/language-reference/data-types/long-data-type.md)|Любой числовой тип \(включая `Byte`, `SByte` и типы перечисления\), `Boolean`, `String`, `Object`|  
|`CObj`|[Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)|Любой тип|  
|`CSByte`|[Тип данных SByte](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|Любой числовой тип \(включая `Byte` и типы перечисления\), `Boolean`, `String`, `Object`|  
|`CShort`|[Тип данных Short](../../../../visual-basic/language-reference/data-types/short-data-type.md)|Любой числовой тип \(включая `Byte`, `SByte` и типы перечисления\), `Boolean`, `String`, `Object`|  
|`CSng`|[Тип данных Single](../../../../visual-basic/language-reference/data-types/single-data-type.md)|Любой числовой тип \(включая `Byte`, `SByte` и типы перечисления\), `Boolean`, `String`, `Object`|  
|`CStr`|[Тип данных String](../../../../visual-basic/language-reference/data-types/string-data-type.md)|Любой числовой тип \(включая `Byte`, `SByte` и типы перечисления\), `Boolean`, `Char`, массив `Char`, `Date`, `Object`|  
|`CType`|Тип, заданный после запятой \(`,`\)|При преобразовании в *elementary data type* \(включая массив простейших типов\) — те же типы, которые разрешены для соответствующих зарезервированных слов преобразования.<br /><br /> При преобразовании в *composite data type* — реализующие их интерфейсы и классы от которых они наследуются<br /><br /> При преобразовании класса или структуры, в которой имеются перегруженные `CType`, класс или структура|  
|`CUInt`|[Тип данных UInteger](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|Любой числовой тип \(включая `Byte`, `SByte` и типы перечисления\), `Boolean`, `String`, `Object`|  
|`CULng`|[Тип данных ULong](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|Любой числовой тип \(включая `Byte`, `SByte` и типы перечисления\), `Boolean`, `String`, `Object`|  
|`CUShort`|[Тип данных UShort](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|Любой числовой тип \(включая `Byte`, `SByte` и типы перечисления\), `Boolean`, `String`, `Object`|  
  
## Функция CType  
 [Функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md) имеет два аргумента.  Первым является преобразуемое выражение, а вторым — конечный тип данных или класс объекта.  Обратите внимание, что первый аргумент должен быть выражением, а не типом.  
  
 `CType` является *inline function*, то есть скомпилированный код делает преобразование, часто без использования вызова функции.  Это повышает производительность.  
  
 Для сравнения `CType` с другими зарезервированными словами преобразования типов см. [Оператор DirectCast](../../../../visual-basic/language-reference/operators/directcast-operator.md) и [Оператор TryCast](../../../../visual-basic/language-reference/operators/trycast-operator.md).  
  
### Простые типы  
 Следующий пример демонстрирует использование `CType`.  
  
```  
k = CType(q, Integer)  
' The following statement coerces w to the specific object class Label.  
f = CType(w, Label)  
```  
  
### Составные типы  
 Зарезервированное слово `CType` используется для преобразования значений в составной тип данных точно так же, как и в простые типы.  Используется также для присвоения класса объекта типу одного из его интерфейсов, как в следующем примере:  
  
```  
' Assume class cZone implements interface iZone.  
Dim h As Object  
' The first argument to CType must be an expression, not a type.  
Dim cZ As cZone  
' The following statement coerces a cZone object to its interface iZone.  
h = CType(cZ, iZone)  
```  
  
### Типы массивов  
 `CType` преобразует также типы данных массивов, как в следующем примере:  
  
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
  
 Дополнительные сведения и примеры см. в разделе [Преобразования массивов](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md).  
  
### Определение типов CType  
 Можно определить `CType` для класса или структуры, определенной пользователем.  Это позволяет производить прямое и обратное преобразование значений в \(из\) типа класса или структуры.  Дополнительные сведения и примеры см. в разделе [Практическое руководство. Определение оператора преобразования](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
> [!NOTE]
>  Значения, используемые с зарезервированными словами преобразования, должны быть допустимы для конечных типов данных, в противном случае возникнет ошибка.  Например при преобразовании типа `Long` в `Integer` значение типа `Long` должно быть в пределах допустимого диапазона для типа данных `Integer`.  
  
> [!CAUTION]
>  Указание `CType` для преобразования из одного типа класса в другой вызовет ошибку во время выполнения, если тип источника не является производным от назначаемого типа.  Такой сбой вызовет исключение <xref:System.InvalidCastException>.  
  
 Однако, если один из типов является структурой или классом, который был определен пользователем, и если пользователь определил `CType` для структуры или класса, то преобразование может быть успешным, если оно удовлетворяет требованиям `CType`.  См. раздел [Практическое руководство. Определение оператора преобразования](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
 Выполнение явного преобразования известно также как *casting* типа выражения к определенному типу данных или классу объекта.  
  
## См. также  
 [Преобразование типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Преобразование значений между строковыми и другими типами](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)   
 [Практическое руководство. Преобразование объекта к другому типу в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)   
 [Структуры](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)