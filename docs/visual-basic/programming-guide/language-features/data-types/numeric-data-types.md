---
title: Числовые типы данных (Visual Basic)
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
ms.openlocfilehash: 75e60cb2a3a934956099ce6fc7d81bf6ecea4d11
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841645"
---
# <a name="numeric-data-types-visual-basic"></a>Числовые типы данных (Visual Basic)
Visual Basic предоставляет несколько *числовых типов данных* для обработки чисел в различные представления. *Целочисленный* типы представляют только целые числа (положительные, отрицательных и нулевых), и *нецелочисленным* — числа с целой и дробной частями.  
  
 Таблица, показывающая side-by-side сравнение типов данных Visual Basic, см. в разделе [типы данных](../../../../visual-basic/language-reference/data-types/index.md).  
  
## <a name="integral-numeric-types"></a>Целочисленные типы  
 *Целочисленных типов данных* представляют собой только числа без дробной части.  
  
 *Автоматический* целые типы данных [тип данных SByte](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md) (8-разрядная версия), [тип данных Short](../../../../visual-basic/language-reference/data-types/short-data-type.md) (16-разрядная версия), [целочисленный тип данных](../../../../visual-basic/language-reference/data-types/integer-data-type.md) (32-разрядная версия) и [ Тип данных Long](../../../../visual-basic/language-reference/data-types/long-data-type.md) (64-разрядная версия). Если переменная всегда хранит целые числа, а не дробных чисел, объявите его как один из этих типов.  
  
 *Без знака* целочисленные типы [тип данных Byte](../../../../visual-basic/language-reference/data-types/byte-data-type.md) (8-разрядная версия), [тип данных UShort](../../../../visual-basic/language-reference/data-types/ushort-data-type.md) (16-разрядная версия), [тип данных UInteger](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md) (32-разрядная версия) и [ Тип данных ULong](../../../../visual-basic/language-reference/data-types/ulong-data-type.md) (64-разрядная версия). Если переменная содержит двоичные данные или данные неизвестной природы, объявите его как один из этих типов.  
  
### <a name="performance"></a>Производительность  
 Арифметические операции выполняются быстрее с целочисленными типами, чем с другими типами данных. Они являются наиболее быстрым `Integer` и `UInteger` типы в Visual Basic.  
  
### <a name="large-integers"></a>Больших целых чисел  
 Если вам нужно хранить целое число больше, чем `Integer` может содержать тип данных, можно использовать `Long` вместо этого тип данных. `Long` переменные могут содержать числа в диапазоне от -9223372036854775808 до 9223372036854775807. Операции с `Long` обрабатываются немного медленнее, чем с `Integer`.  
  
 Если вам требуется еще больше значения, можно использовать [тип данных Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md). Вы можете хранить числа в диапазоне от -79,228,162,514,264,337,593,543,950,335 до 79,228,162,514,264,337,593,543,950,335 в `Decimal` переменной, если вы не используете десятичные разряды. Тем не менее операции с `Decimal` номера выполняются значительно медленнее, чем с другими типами числовых данных.  
  
### <a name="small-integers"></a>Двухбайтовые целые числа  
 Если не требуется полный спектр `Integer` тип данных, можно использовать `Short` тип данных, который может содержать целые числа от-32 768 до 32 767. Для диапазона наименьшее целое число `SByte` тип данных содержит целые числа от -128 до 127. Если у вас есть очень большое количество переменных, которые содержат двухбайтовые целые числа, среда CLR, иногда может хранить ваши `Short` и `SByte` переменные более эффективно и снизить потребление памяти. Тем не менее операции с `Short` и `SByte` выполняются медленнее, чем с `Integer`.  
  
### <a name="unsigned-integers"></a>Целые числа без знака  
 Если вы знаете, что переменная никогда не должна содержать отрицательное число, можно использовать *беззнаковых типов*`Byte`, `UShort`, `UInteger`, и `ULong`. Каждый из этих типов данных может содержать положительное целое число в два раза превышает как его соответствующий тип со знаком (`SByte`, `Short`, `Integer`, и `Long`). С точки зрения производительности каждый тип без знака точно так же эффективно, как его соответствующий тип со знаком. В частности `UInteger` предоставил `Integer` являются наиболее эффективный все простые числовые типы данных.  
  
## <a name="nonintegral-numeric-types"></a>Нецелочисленный числовые типы  
 *Типы данных нецелочисленный* представляют собой номера с целой и дробной частей.  
  
 Нецелочисленный числовыми типами данных являются `Decimal` (128-разрядный фиксированной запятой), [одного типа данных](../../../../visual-basic/language-reference/data-types/single-data-type.md) (32-разрядных с плавающей запятой), и [тип данных Double](../../../../visual-basic/language-reference/data-types/double-data-type.md) (64-разрядное число с плавающей запятой). Они являются все подписанные типами. Если переменная может содержать дробную часть, объявите его как один из этих типов.  
  
 `Decimal` не является типом данных с плавающей запятой. `Decimal` числа имеют двоичное целое значение и масштабный коэффициент целое число, указывающее, какая часть значения является десятичной дробью.  
  
 Можно использовать `Decimal` переменные для денежных значений. Преимущество заключается в точность значений. `Double` Тип данных выполняется быстрее и требует меньше памяти, но она доступна на условиях ошибок округления. `Decimal` Тип данных сохраняет полную точность до 28 десятичных разрядов.  
  
 С плавающей запятой (`Single` и `Double`) числа имеют большие диапазоны, чем `Decimal` чисел, но могут возникать ошибки округления. Типы с плавающей запятой поддерживают меньшее количество значащих цифр, чем `Decimal` , но могут представлять значения, превышающие.  
  
 Нецелочисленные значения могут быть выражены как mmmEeee, в которых mmm является *мантиссы* (значимых цифр), а eee — *показатель степени* (степень 10). Когда положительное находятся большие значения нецелочисленных типов 7.9228162514264337593543950335E + 28 для `Decimal`, 3, 4028235E + 38 для `Single`и 1, 79769313486231570E + 308 `Double`.  
  
### <a name="performance"></a>Производительность  
 `Double` наиболее эффективен для дробных типов данных, так как процессоры на современных платформах выполняют операции с плавающей запятой с двойной точностью. Тем не менее операции с `Double` не выполняются так же быстро, как и в случае с целочисленными типами, такие как `Integer`.  
  
### <a name="small-magnitudes"></a>Малые величины  
 Для чисел с наименьшей возможной величиной (наиболее близким к 0) `Double` переменных может содержать числа, как - 4, 94065645841246544E-324 для отрицательных значений и 4, 94065645841246544E-324 для положительных значений.  
  
### <a name="small-fractional-numbers"></a>Малые дробные числа  
 Если не требуется полный спектр `Double` тип данных, можно использовать `Single` тип данных, который может содержать числа с плавающей запятой от - 3, 4028235E + 38 до 3, 4028235E + 38. Минимальные значения `Single` переменные являются - 1, 401298E-45 для отрицательных значений и 1, 401298E-45 для положительных значений. Если у вас есть очень большое количество переменных, которые содержат небольшого числа с плавающей запятой, среда CLR, иногда может хранить ваши `Single` переменные более эффективно и снизить потребление памяти.  
  
## <a name="see-also"></a>См. также

- [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Символьные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)
- [Прочие типы данных](../../../../visual-basic/programming-guide/language-features/data-types/miscellaneous-data-types.md)
- [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа](../../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
