---
title: "Расширяющие и сужающие преобразования (Visual Basic) | Документы Microsoft"
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
- widening conversions
- narrowing conversions
- conversions, type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- conversions, exceptions during conversion
- type conversion, exceptions during conversion
- conversions, data type
- conversions, narrowing
- type conversion, narrowing
- data type conversion, widening
- data type conversion, narrowing
- changing data types
- type conversion, widening
- data type conversion, exceptions during conversion
- conversions, widening
ms.assetid: 058c3152-6c28-4268-af44-2209e774f0bd
caps.latest.revision: 27
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
ms.openlocfilehash: 88c5db6e7e82a88ae8015b581e5a795ec389d003
ms.lasthandoff: 03/13/2017

---
# <a name="widening-and-narrowing-conversions-visual-basic"></a>Расширяющие и сужающие преобразования (Visual Basic)
Важным аспектом при преобразовании типа является результатом преобразования в пределах диапазона целевого типа данных.  
  
 Объект *расширяющее преобразование* изменяет значение на тип данных, который позволяет выполнять любое возможное значение исходных данных.  Расширяющие преобразования сохраняют исходное значение, но могут изменить его представление. Это происходит при преобразовании из целого типа в `Decimal`, или `Char` в `String`.  
  
 *Преобразование сужения* изменяет тип данных значения на тип, который не сможет содержать некоторые возможные значения. Например, дробные значения округляются при преобразовании целочисленного типа и числового типа, при преобразовании в `Boolean` уменьшается либо `True` или `False`.  
  
## <a name="widening-conversions"></a>Расширяющие преобразования  
 В следующей таблице показаны стандартные расширяющие преобразования.  
  
|Тип данных|Расширяется до типов данных <sup>1</sup>|  
|---|---|  
|[SByte](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[Byte](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[Короткий](../../../../visual-basic/language-reference/data-types/short-data-type.md)|`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[UShort](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[Целое число](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|`Integer`, `Long`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[UInteger](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|`UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[Длинное](../../../../visual-basic/language-reference/data-types/long-data-type.md)|`Long`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[ULong](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|`ULong`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|`Decimal`, `Single`, `Double`<sup>2</sup>|  
|[Single](../../../../visual-basic/language-reference/data-types/single-data-type.md)|`Single`, `Double`|  
|[Double](../../../../visual-basic/language-reference/data-types/double-data-type.md)|`Double`|  
|Какой-либо перечисляемый тип ([перечисления](../../../../visual-basic/language-reference/statements/enum-statement.md))|Его основного целочисленного типа и любой тип, до которого может быть расширен базовый тип.|  
|[Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)|`Char`, `String`|  
|Массив `Char`|`Char`Массив,`String`|  
|Любой тип|[Объект](../../../../visual-basic/language-reference/data-types/object-data-type.md)|  
|Любой производный тип|Любой базовый тип, из которого получается <sup>3</sup>.|  
|Любой тип|Любой интерфейс, который его реализует.|  
|[Nothing](../../../../visual-basic/language-reference/nothing.md)|Тип данных или тип объекта.|  
  
 <sup>1</sup> по определению каждый тип данных может быть расширен до самого.  
  
 <sup>2</sup> преобразования из `Integer`, `UInteger`, `Long`, `ULong`, или `Decimal` для `Single` или `Double` может привести к потере точности, но никогда не потере величины. В этом смысле они не создают потерю данных.  
  
 <sup>3</sup> может показаться странным, что преобразование из производного типа в один из его базовых типов является расширяющим. Объясняется это тем, что производный тип содержит все члены базового типа, поэтому он определяется как экземпляр базового типа. В обратном направлении базовый тип не содержит все новых членов, определенных производным типом.  
  
 Расширяющие преобразования всегда успешны во время выполнения и никогда не приводят к потере данных. Можно всегда выполнить их неявным образом, является ли [оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) задает ключ для проверки типа `On` или `Off`.  
  
## <a name="narrowing-conversions"></a>Сужающие преобразования  
 Стандартные сужающие преобразования включают следующие:  
  
-   Обратные направления расширяющих преобразований в предшествующей таблице (за исключением того, что каждый тип может быть расширен на себя)  
  
-   Преобразования в любом направлении между [логическое](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) и любым числовым типом.  
  
-   Преобразования любого числового типа в любой перечисляемый тип (`Enum`)  
  
-   Преобразования в любом направлении между [строка](../../../../visual-basic/language-reference/data-types/string-data-type.md) и любым числовым типом `Boolean`, или [даты](../../../../visual-basic/language-reference/data-types/date-data-type.md)  
  
-   Преобразования из типа данных или объект типа в тип, производный от него  
  
 Сужающие преобразования не всегда успешны во время выполнения и может завершиться ошибкой или приводят к потере данных. Ошибка возникает, если целевой тип данных не может получить преобразованное значение. Например числовое преобразование может привести к переполнению. Компилятор не дают возможность выполнения сужающего преобразования неявно, если не [оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) задает ключ для проверки типа `Off`.  
  
> [!NOTE]
>  Ошибка сужающего преобразования отбрасывается при преобразовании из элементов в `For Each…Next` коллекцию для переменной цикла. Дополнительные сведения и примеры см. в разделе «Сужающие преобразования» [For Each... Следующий оператор](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
### <a name="when-to-use-narrowing-conversions"></a>Когда следует использовать сужающие преобразования  
 Сужающее преобразование использовать, когда известно, что исходное значение может быть преобразовано в конечный тип данных без ошибки и потери данных. Например, если у вас есть `String` , вы знаете, содержит значение «True» или «False», можно использовать `CBool` ключевое слово для преобразования его в `Boolean`.  
  
## <a name="exceptions-during-conversion"></a>Исключения при преобразовании  
 Поскольку расширяющие преобразования всегда выполнена успешно, они не создают исключений. Сужающие преобразования, если они не часто создают следующие исключения:  
  
-   <xref:System.InvalidCastException>— Если не определено преобразование между двумя типами</xref:System.InvalidCastException>  
  
-   <xref:System.OverflowException>— (только для целых типов) если преобразованное значение слишком велико для целевого типа</xref:System.OverflowException>  
  
 Если класс или структура определяет [функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md) в качестве оператора преобразования в или из этого класса или структуры, которая `CType` можно вызывать любое исключение, которые она считает необходимыми. Кроме того, что `CType` может вызвать [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] функции или [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] методы, которые в свою очередь, могут вызвать ряд исключений.  
  
## <a name="changes-during-reference-type-conversions"></a>Изменения в ходе преобразования типа ссылки  
 Преобразование из *ссылочный тип* копирует только указатель на значение. Само значение не копируются и не изменяется. Единственное, что можно изменить является типом данных переменной, содержащей указатель. В следующем примере тип данных преобразуется из производного класса в его базовый класс, но объект, чтобы указывают обе переменные, не изменяется.  
  
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
 [Преобразование между строковыми и другими типами](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)   
 [Практическое руководство: преобразование объекта к другому типу в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)   
 [Преобразования массивов](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)   
 [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
