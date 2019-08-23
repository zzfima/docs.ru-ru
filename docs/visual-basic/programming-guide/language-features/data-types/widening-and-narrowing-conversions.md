---
title: Расширяющие и сужающие преобразования (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 858b2b2e154b659470fa61b21f25ab61eabda012
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965657"
---
# <a name="widening-and-narrowing-conversions-visual-basic"></a>Расширяющие и сужающие преобразования (Visual Basic)
Важное замечание при преобразовании типов заключается в том, находится ли результат преобразования в диапазоне целевого типа данных.  
  
 *Расширяющее преобразование* изменяет значение на тип данных, который может допускать любое возможное значение исходных данных.  Расширяющие преобразования сохраняют исходное значение, но могут изменять его представление. Это происходит при преобразовании из целочисленного типа в `Decimal`или из `Char` в `String`.  
  
 *Преобразование сужения* изменяет тип данных значения на тип, который не сможет содержать некоторые возможные значения. Например, дробное значение округляется при преобразовании в целочисленный тип, а числовой тип, преобразуемый `Boolean` в, сокращается до `False`либо `True` .  
  
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
|Любой перечислимый тип ([enum](../../../../visual-basic/language-reference/statements/enum-statement.md))|Его базовый целочисленный тип и любой тип, к которому расширяется базовый тип.|  
|[Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)|`Char`, `String`|  
|Массив `Char`|`Char`inArray`String`|  
|Любой тип|[Объект](../../../../visual-basic/language-reference/data-types/object-data-type.md)|  
|Любой производный тип|Любой базовый тип, от которого он является производным <sup>3</sup>.|  
|Любой тип|Любой интерфейс, который он реализует.|  
|[Nothing](../../../../visual-basic/language-reference/nothing.md)|Любой тип данных или тип объекта.|  
  
 <sup>1</sup> по определению каждый тип данных расширяется до самого себя.  
  
 <sup>2</sup> преобразования из `Integer`, `UInteger` `Single` ,, илив`Decimal` или могут`Double` привести к утрате точности, но никогда не будут иметь потери. `Long` `ULong` В этом смысле они не приводят к утрате информации.  
  
 <sup>3</sup> может показаться удивительно, что преобразование из производного типа в один из его базовых типов является расширяющим. Обоснованием является то, что производный тип содержит все члены базового типа, поэтому он является экземпляром базового типа. В обратном направлении базовый тип не содержит новых элементов, определенных производным типом.  
  
 Расширяющие преобразования всегда выполняются в период выполнения и никогда не вызывают потери данных. Вы всегда можете выполнять их неявно, независимо от того, устанавливает ли [оператор Option строго](../../../../visual-basic/language-reference/statements/option-strict-statement.md) значение переключателя `On` проверки типа `Off`в значение или.  
  
## <a name="narrowing-conversions"></a>сужающие преобразования  
 К стандартным сужающим преобразованиям относятся следующие:  
  
- Обратные направления расширяющих преобразований в предыдущей таблице (за исключением того, что каждый тип расширяется до самого себя)  
  
- Преобразования в любом направлении между [логическим](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) и любым числовым типом  
  
- Преобразования любого числового типа в любой перечислимый тип (`Enum`)  
  
- Преобразования в любом направлении между [строкой](../../../../visual-basic/language-reference/data-types/string-data-type.md) и любым числовым `Boolean`типом, или [датой](../../../../visual-basic/language-reference/data-types/date-data-type.md)  
  
- Преобразование типа данных или типа объекта в производный от него тип  
  
 Сужающие преобразования не всегда выполняются успешно во время выполнения и могут привести к сбою или потери данных. Если целевой тип данных не может получить преобразуемое значение, возникает ошибка. Например, числовое преобразование может привести к переполнению. Компилятор не позволяет выполнять сужающие преобразования неявно, если только [оператор Option строго](../../../../visual-basic/language-reference/statements/option-strict-statement.md) задает для `Off`параметра проверки типа значение.  
  
> [!NOTE]
> Ошибка сужения преобразования подавляется для преобразований из элементов в `For Each…Next` коллекции в переменную управления циклом. Дополнительные сведения и примеры см. в подразделе «сужающие преобразования» раздела [For Each... Следующий оператор](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
### <a name="when-to-use-narrowing-conversions"></a>Когда следует использовать сужающие преобразования  
 Если известно, что исходное значение можно преобразовать в целевой тип данных без ошибок или потери данных, используется суженное преобразование. Например, если имеется объект `String` , который содержит значение true или false, можно `CBool` использовать ключевое слово, чтобы преобразовать его в `Boolean`.  
  
## <a name="exceptions-during-conversion"></a>Исключения во время преобразования  
 Поскольку расширяющие преобразования всегда выполняются, они не создают исключения. Сужающие преобразования, когда они завершаются сбоем, чаще всего вызывают следующие исключения:  
  
- <xref:System.InvalidCastException>— Если преобразование между двумя типами не определено  
  
- <xref:System.OverflowException>— (только целочисленные типы), если преобразованное значение слишком велико для целевого типа  
  
 Если класс или структура определяет [функцию CType](../../../../visual-basic/language-reference/functions/ctype-function.md) , которая будет служить оператором преобразования в этот класс или структуру или из этого класса или `CType` структуры, это может вызвать любое исключение, которое оно считается соответствующим. Кроме того, это `CType` может вызывать функции Visual Basic или методы .NET Framework, которые, в свою очередь, могут вызывать различные исключения.  
  
## <a name="changes-during-reference-type-conversions"></a>Изменения во время преобразования ссылочного типа  
 При преобразовании из *ссылочного типа* копируется только указатель на значение. Само значение не копируется и не изменяется каким-либо образом. Единственное, что может изменить, — это тип данных переменной, содержащей указатель. В следующем примере тип данных преобразуется из производного класса в его базовый класс, но объект, на который теперь указывают обе переменные, не изменяется.  
  
```  
' Assume class cSquare inherits from class cShape.  
Dim shape As cShape  
Dim square As cSquare = New cSquare  
' The following statement performs a widening  
' conversion from a derived class to its base class.  
shape = square  
```  
  
## <a name="see-also"></a>См. также

- [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Преобразования значений между строковыми и другими типами](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [Практическое руководство. Преобразование объекта в другой тип в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [Преобразования массивов](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [Типы данных](../../../../visual-basic/language-reference/data-types/index.md)
- [Функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
