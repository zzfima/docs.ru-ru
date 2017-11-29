---
title: "Расширяющие и сужающие преобразования (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- widening conversions [Visual Basic]
- narrowing conversions [Visual Basic]
- conversions [Visual Basic], type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- conversions [Visual Basic], exceptions during conversion
- type conversion [Visual Basic], exceptions during conversion
- conversions [Visual Basic], data type
- conversions [Visual Basic], narrowing
- type conversion [Visual Basic], narrowing
- data type conversion [Visual Basic], widening
- data type conversion [Visual Basic], narrowing
- changing data types [Visual Basic]
- type conversion [Visual Basic], widening
- data type conversion [Visual Basic], exceptions during conversion
- conversions [Visual Basic], widening
ms.assetid: 058c3152-6c28-4268-af44-2209e774f0bd
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2cf1f8d956935a9a363211abf94b4f1c2f538074
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="widening-and-narrowing-conversions-visual-basic"></a>Расширяющие и сужающие преобразования (Visual Basic)
Важным аспектом при преобразовании типа является результат преобразования в пределах диапазона целевого типа данных.  
  
 Объект *расширяющее преобразование* изменяет значение в тип данных, можно разрешить для всех возможных значений исходных данных.  Расширяющие преобразования сохраняют исходное значение, но могут изменить его представление. Это происходит при преобразовании из целого типа в `Decimal`, или из `Char` для `String`.  
  
 *Преобразование сужения* изменяет тип данных значения на тип, который не сможет содержать некоторые возможные значения. Например, дробные значения округляются при преобразовании целого типа, а при преобразовании в числовой тип `Boolean` сокращается до либо `True` или `False`.  
  
## <a name="widening-conversions"></a>расширяющие преобразования  
 В следующей таблице показаны стандартные расширяющие преобразования.  
  
|Тип данных|Расширяется до типов данных <sup>1</sup>|  
|---|---|  
|[SByte](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[Byte](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[Short](../../../../visual-basic/language-reference/data-types/short-data-type.md)|`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[UShort](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[Integer](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|`Integer`, `Long`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[UInteger](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|`UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[Long](../../../../visual-basic/language-reference/data-types/long-data-type.md)|`Long`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[ULong](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|`ULong`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|`Decimal`, `Single`, `Double`<sup>2</sup>|  
|[Single](../../../../visual-basic/language-reference/data-types/single-data-type.md)|`Single`, `Double`|  
|[Double](../../../../visual-basic/language-reference/data-types/double-data-type.md)|`Double`|  
|Какой-либо перечисляемый тип ([перечисления](../../../../visual-basic/language-reference/statements/enum-statement.md))|Его основного целочисленного типа и любой тип, до которого может быть расширен базовый тип.|  
|[Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)|`Char`, `String`|  
|Массив `Char`|`Char`Массив,`String`|  
|Любой тип|[Объект](../../../../visual-basic/language-reference/data-types/object-data-type.md)|  
|Любой производный тип|Любой базовый тип, от которого он является производным <sup>3</sup>.|  
|Любой тип|Любой интерфейс, который его реализует.|  
|[Nothing](../../../../visual-basic/language-reference/nothing.md)|Тип данных или тип объекта.|  
  
 <sup>1</sup> по определению каждый тип данных может быть расширен до самого.  
  
 <sup>2</sup> преобразования из `Integer`, `UInteger`, `Long`, `ULong`, или `Decimal` для `Single` или `Double` может привести к потере точности, но никогда не потере величины. В этом смысле они не создают потери информации.  
  
 <sup>3</sup> может показаться странным, что преобразование из производного типа в один из его базовых типов является расширяющим. Объясняется это тем, что производный тип содержит все члены базового типа, поэтому он определяется как экземпляр базового типа. В обратном направлении базовый тип не содержит никакие новые члены, определенные производным типом.  
  
 Расширяющие преобразования всегда выполняться успешно во время выполнения и никогда не приводят к потере данных. Можно всегда выполнить их неявным образом, является ли [оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) задает ключ для проверки типа `On` или `Off`.  
  
## <a name="narrowing-conversions"></a>сужающие преобразования  
 Ниже приведены стандартные сужающие преобразования:  
  
-   Обратные направления расширяющих преобразований в предыдущем таблице (за исключением того, что каждый тип может быть расширен на себя)  
  
-   Преобразования в любом направлении между [логическое](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) и любым числовым типом.  
  
-   Преобразования любого числового типа в любой перечисляемый тип (`Enum`)  
  
-   Преобразования в любом направлении между [строка](../../../../visual-basic/language-reference/data-types/string-data-type.md) и любым числовым типом `Boolean`, или [даты](../../../../visual-basic/language-reference/data-types/date-data-type.md)  
  
-   Преобразования из типа данных или объект типа производный от него тип.  
  
 Сужающие преобразования не всегда успешны во время выполнения и может завершиться ошибкой или приводят к потере данных. Возникает ошибка, если целевой тип данных не может получить преобразованное значение. Например числовое преобразование может привести к переполнению. Компилятор не позволяет выполнять сужающие преобразования неявным образом, если не [оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) задает ключ для проверки типа `Off`.  
  
> [!NOTE]
>  Ошибка сужающего преобразования отбрасывается при преобразовании из элементов в `For Each…Next` коллекции для управляющей переменной цикла. Дополнительные сведения и примеры см. в подразделе «Сужающие преобразования» [For Each... Следующий оператор](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
### <a name="when-to-use-narrowing-conversions"></a>Когда следует использовать сужающие преобразования  
 Сужающее преобразование использовать, когда известно, что исходное значение может быть преобразовано в тип данных назначения без ошибок или потери данных. Например, если у вас есть `String` , вы знаете, содержит значение «True» или «False», можно использовать `CBool` ключевое слово для преобразования его в `Boolean`.  
  
## <a name="exceptions-during-conversion"></a>Исключения при преобразовании  
 Поскольку расширяющие преобразования всегда выполняются успешно, они не создают исключений. Сужающие преобразования, если они вызывают ошибку, наиболее часто вызывать следующие исключения:  
  
-   <xref:System.InvalidCastException>— Если не определено преобразование между двумя типами  
  
-   <xref:System.OverflowException>— (только для целых типов) если преобразованное значение слишком велико для типа целевого объекта  
  
 Если класс или структура определяет [функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md) в качестве оператора преобразования в или из этого класса или структуры, которая `CType` может вызвать исключение, которые она считает необходимыми. Кроме того, что `CType` может вызывать [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] функции или [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] методы, которые в свою очередь, могут вызвать ряд исключений.  
  
## <a name="changes-during-reference-type-conversions"></a>Изменения в ходе преобразования типа ссылки  
 Преобразование из *ссылочному типу* копирует только указатель на значение. Само значение не копируется и не изменяется. Единственное, что можно изменить имеет тип данных переменной, содержащей указатель. В следующем примере тип данных преобразуется из производного класса к базовому классу, но, теперь обе переменные наведите указатель на объект, не изменяется.  
  
```  
' Assume class cSquare inherits from class cShape.  
Dim shape As cShape  
Dim square As cSquare = New cSquare  
' The following statement performs a widening  
' conversion from a derived class to its base class.  
shape = square  
```  
  
## <a name="see-also"></a>См. также  
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Преобразования значений между строковыми и другими типами](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [Как: преобразование объекта к другому типу в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [Преобразования массивов](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
