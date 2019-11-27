---
title: Числовые типы данных
ms.date: 07/20/2015
helpviewer_keywords:
- integral types [Visual Basic], Visual Basic
- Short data type [Visual Basic], numeric data types
- Double data type [Visual Basic], numeric data types
- Long data type [Visual Basic], Visual Basic numeric data types
- numbers [Visual Basic], whole
- fractions
- numbers
- whole numbers
- integer numbers
- numbers [Visual Basic], integer
- fractional data types [Visual Basic]
- mantissas, of fractional numbers
- mantissas
- data types [Visual Basic], numeric
- Integer data type [Visual Basic], numeric data types
- exponent, of fractional numbers
- integers [Visual Basic]
- numeric data types [Visual Basic], Visual Basic
- Single data type [Visual Basic], numeric types
- Decimal data type [Visual Basic], numeric data types
ms.assetid: a27bd4d0-7e14-43eb-9cc4-b42eaab323c9
ms.openlocfilehash: dc8b630eebc48e5733344a00664b453360769c0b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346311"
---
# <a name="numeric-data-types-visual-basic"></a>Числовые типы данных (Visual Basic)
Visual Basic предоставляет несколько *числовых типов данных* для обработки чисел в различных представлениях. *Целочисленные* типы представляют только целые числа (положительные, отрицательные и нулевые), а *Нецелочисленные* типы — числа с целой и дробной частями.  
  
 Для таблицы, показывающей параллельное сравнение типов данных Visual Basic, см. в разделе [типы данных](../../../../visual-basic/language-reference/data-types/index.md).  
  
## <a name="integral-numeric-types"></a>Целочисленные типы  
 *Целочисленные типы данных* — это те, которые представляют только числа без дробных частей.  
  
 Целочисленные типы данных *со знаком* имеют [тип данных SByte](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md) (8-разрядный), [короткий тип данных](../../../../visual-basic/language-reference/data-types/short-data-type.md) (16-разрядный), [целочисленный тип данных](../../../../visual-basic/language-reference/data-types/integer-data-type.md) (32 бит) и [тип данных Long](../../../../visual-basic/language-reference/data-types/long-data-type.md) (64-бит). Если переменная всегда хранит целые числа, а не дробные числа, объявите ее как один из этих типов.  
  
 Целочисленные типы *без знака* имеют [тип данных Byte](../../../../visual-basic/language-reference/data-types/byte-data-type.md) (8-разрядный), [тип данных UShort](../../../../visual-basic/language-reference/data-types/ushort-data-type.md) (16-разрядный), [тип данных UInteger](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md) (32 бит) и [тип данных ULong](../../../../visual-basic/language-reference/data-types/ulong-data-type.md) (64-бит). Если переменная содержит двоичные данные или данные неизвестной природы, объявите ее как один из этих типов.  
  
### <a name="performance"></a>Производительность  
 Арифметические операции выполняются быстрее с целочисленными типами, чем с другими типами данных. Они работают быстрее с типами `Integer` и `UInteger` в Visual Basic.  
  
### <a name="large-integers"></a>Большие целые числа  
 Если необходимо хранить целое число, большее, чем `Integer` тип данных, можно использовать `Long` тип данных. `Long` переменные могут содержать числа от-9223372036854775808 до 9 223 372 036 854 775 807. Операции с `Long` немного медленнее, чем в `Integer`.  
  
 Если вам нужны еще большие значения, можно использовать [тип данных Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md). Можно хранить числа от-79,228,162,514,264,337,593,543,950,335 до 79,228,162,514,264,337,593,543,950,335 в переменной `Decimal`, если не используются десятичные разряды. Однако операции с числами `Decimal` значительно медленнее, чем с любым другим числовым типом данных.  
  
### <a name="small-integers"></a>Небольшие целые числа  
 Если не требуется полный диапазон `Integer` типа данных, можно использовать `Short` тип данных, который может содержать целые числа от-32 768 до 32 767. Для наименьшего диапазона целых чисел `SByte` тип данных содержит целые числа от-128 до 127. При наличии очень большого числа переменных, содержащих небольшие целые числа, среда CLR иногда может хранить `Short` и `SByte` переменные более эффективно и экономить потребление памяти. Однако операции с `Short` и `SByte` несколько медленнее, чем в `Integer`.  
  
### <a name="unsigned-integers"></a>Целые числа без знака  
 Если известно, что переменная никогда не должна содержать отрицательное число, можно использовать *неподписанные типы*`Byte`, `UShort`, `UInteger`и `ULong`. Каждый из этих типов данных может содержать положительное целое число в два раза больше, чем соответствующий знаковый тип (`SByte`, `Short`, `Integer`и `Long`). С точки зрения производительности каждый тип без знака является точно таким же эффективным, как и соответствующий тип со знаком. В частности, `UInteger` предоставляет общий доступ к `Integer` отличие наиболее эффективного из всех простейших числовых типов данных.  
  
## <a name="nonintegral-numeric-types"></a>Нецелочисленные числовые типы  
 *Нецелочисленные типы данных* — это значения, представляющие числа с целой и дробной частями.  
  
 Нецелочисленные числовые типы данных `Decimal` (128-разрядная Фиксированная точка), [один тип данных](../../../../visual-basic/language-reference/data-types/single-data-type.md) (32-разрядная с плавающей запятой) и [тип данных Double](../../../../visual-basic/language-reference/data-types/double-data-type.md) (64-разрядный с плавающей запятой). Все типы со знаком. Если переменная может содержать дробную часть, объявите ее как один из этих типов.  
  
 `Decimal` не является типом данных с плавающей запятой. `Decimal` числа имеют двоичное целочисленное значение и целочисленный коэффициент масштабирования, указывающий, какая часть значения является десятичной дробью.  
  
 Для денежных значений можно использовать `Decimal` переменные. Преимущество — точность значений. Тип данных `Double` является более быстрым и требует меньше памяти, но он подвергается ошибкам округления. Тип данных `Decimal` сохраняет полную точность до 28 десятичных разрядов.  
  
 Числа с плавающей запятой (`Single` и `Double`) имеют большие диапазоны, чем `Decimal` числа, но могут подвергаться ошибкам округления. Типы с плавающей запятой поддерживают меньше значащих цифр, чем `Decimal`, но могут представлять значения большей величины.  
  
 Нецелочисленные числовые значения можно выразить как Мммии, в котором MMM является *мантиссаом* (значащими цифрами), а ие — *экспонентой* (степенью 10). Наибольшие положительные значения нецелочисленных типов — 7.9228162514264337593543950335 E + 28 для `Decimal`, 4028235E E + 38 для `Single`и 1.79769313486231570 E + 308 для `Double`.  
  
### <a name="performance"></a>Производительность  
 `Double` является наиболее эффективным из типов данных дробной части, так как процессоры на текущих платформах выполняют операции с плавающей запятой с двойной точностью. Однако операции с `Double` не так быстро, как с целочисленными типами, такими как `Integer`.  
  
### <a name="small-magnitudes"></a>Небольшие величины  
 Для чисел с наименьшей возможной величиной (ближайшее к 0) `Double` переменные могут содержать числа в виде мелких, например, 4.94065645841246544 E-324 для отрицательных значений и 4.94065645841246544 E-324 для положительных значений.  
  
### <a name="small-fractional-numbers"></a>Небольшие дробные числа  
 Если не требуется полный диапазон `Double` типа данных, можно использовать `Single` тип данных, который может содержать числа с плавающей запятой в диапазоне от-4028235E E + 38 до 4028235E E + 38. Наименьшими значениями для `Single` переменных являются-1.401298 E-45 для отрицательных значений и 1.401298 E-45 для положительных значений. При наличии очень большого числа переменных, содержащих небольшие числа с плавающей запятой, среда CLR может иногда сохранять `Single` переменные более эффективно и экономить потребление памяти.  
  
## <a name="see-also"></a>См. также

- [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Символьные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)
- [Прочие типы данных](../../../../visual-basic/programming-guide/language-features/data-types/miscellaneous-data-types.md)
- [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа](../../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
