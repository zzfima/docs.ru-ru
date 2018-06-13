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
ms.openlocfilehash: 8fa88172c9914a071e1b24e959c9030e6d219a30
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654207"
---
# <a name="numeric-data-types-visual-basic"></a>Числовые типы данных (Visual Basic)
Visual Basic предоставляет несколько *числовых типов данных* для обработки чисел в различных представлениях. *Целочисленный* типам относятся только целые числа (положительные, отрицательные и ноль), и *нецелочисленным* — с целую и дробную части числа.  
  
 Таблица, показывающая сравнение типы данных Visual Basic, см. [типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## <a name="integral-numeric-types"></a>Целочисленные типы  
 *Целочисленные типы данных* представляют собой только числа без дробной части.  
  
 *Подписан* целые типы данных [тип данных SByte](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md) (8-разрядная версия), [тип данных Short](../../../../visual-basic/language-reference/data-types/short-data-type.md) (16-разрядная версия), [целочисленный тип данных](../../../../visual-basic/language-reference/data-types/integer-data-type.md) (32-разрядная версия) и [ Тип данных Long](../../../../visual-basic/language-reference/data-types/long-data-type.md) (64-разрядная версия). Если переменная всегда хранит целые числа, а не дробных чисел, объявите его как один из этих типов.  
  
 *Без знака* целочисленные типы имеют [типа данных Byte](../../../../visual-basic/language-reference/data-types/byte-data-type.md) (8-разрядная версия), [тип данных UShort](../../../../visual-basic/language-reference/data-types/ushort-data-type.md) (16-разрядная версия), [UInteger-тип данных](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md) (32-разрядная версия) и [ Тип данных ULong](../../../../visual-basic/language-reference/data-types/ulong-data-type.md) (64-разрядная версия). Если переменная содержит двоичные данные или данные неизвестной природы, объявите его как один из этих типов.  
  
### <a name="performance"></a>Производительность  
 Арифметические операции выполняются быстрее с целыми типами, чем с другими типами данных. Они являются наиболее быстрым `Integer` и `UInteger` типы в Visual Basic.  
  
### <a name="large-integers"></a>Больших целых чисел  
 Если необходимо хранить целое число больше, чем `Integer` может содержать тип данных, можно использовать `Long` типа данных. `Long` переменные могут содержать числа в диапазоне от -9223372036854775808 до 9223372036854775807. Операции с `Long` немного медленнее, чем с `Integer`.  
  
 Если необходимо, чтобы еще больше значения, можно использовать [тип данных Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md). Можно хранить числа в диапазоне от -79,228,162,514,264,337,593,543,950,335 до 79,228,162,514,264,337,593,543,950,335 в `Decimal` переменной, если вы не используете десятичные разряды. Тем не менее операции с `Decimal` номера — это значительно медленнее, чем с другими типами числовых данных.  
  
### <a name="small-integers"></a>Двухбайтовые целые числа  
 Если не требуется полный диапазон `Integer` тип данных, вы можете использовать `Short` тип данных, который может содержать целые числа от-32 768 до 32 767. Для диапазона наименьшее целое число `SByte` тип данных содержит целые числа от -128 до 127. Если имеется большое количество переменных, которые содержат двухбайтовые целые числа, среда, иногда можно хранить на `Short` и `SByte` переменные более эффективно и снизить потребление памяти. Тем не менее операции с `Short` и `SByte` выполняются медленнее, чем с `Integer`.  
  
### <a name="unsigned-integers"></a>Целые числа без знака  
 Если вы знаете, что переменная никогда не должна содержать отрицательное число, можно использовать *беззнаковых типов*`Byte`, `UShort`, `UInteger`, и `ULong`. Каждый из этих типов данных может содержать положительное целое число в два раза превышает как его соответствующий тип со знаком (`SByte`, `Short`, `Integer`, и `Long`). С точки зрения производительности каждый тип без знака — точно так же эффективно, как его соответствующий тип со знаком. В частности `UInteger` являются общими с `Integer` являются наиболее эффективными из всех типов простейших числовых данных.  
  
## <a name="nonintegral-numeric-types"></a>Нецелочисленный числовые типы  
 *Типы данных нецелочисленный* представляют собой целую и дробную части числа.  
  
 Нецелочисленный числовыми типами данных являются `Decimal` (128 бит с фиксированной запятой), [одного типа данных](../../../../visual-basic/language-reference/data-types/single-data-type.md) (32-разрядных чисел с плавающей запятой), и [тип данных Double](../../../../visual-basic/language-reference/data-types/double-data-type.md) (64-разрядных чисел с плавающей запятой). Они являются все подписанные типами. Если переменная может содержать дробную часть, объявите его как один из этих типов.  
  
 `Decimal` не является типом данных с плавающей запятой. `Decimal` номера имеют двоичное целое значение и масштабный коэффициент целое число, указывающее, какая часть значения является десятичной дробью.  
  
 Можно использовать `Decimal` переменные для денежных значений. Преимущество заключается в точности значений. `Double` Типа данных происходит быстрее и требует меньше памяти, однако он может быть ошибок округления. `Decimal` Тип данных сохраняет полную точность до 28 десятичных разрядов.  
  
 С плавающей запятой (`Single` и `Double`) номера имеют большие диапазоны, чем `Decimal` чисел, но может быть причиной ошибок округления. Типы с плавающей запятой поддерживают меньшее количество значащих цифр, чем `Decimal` , но могут представлять значения большей величины.  
  
 Нецелочисленные значения могут быть выражены как mmmEeee, в которых mmm является *мантиссы* (значащих цифр), а eee — *показатель степени* (степень числа 10). Максимальные положительные значения для нецелочисленных типов являются 7.9228162514264337593543950335E + 28 для `Decimal`, 3, 4028235E + 38 для `Single`и 1, 79769313486231570E + 308 для `Double`.  
  
### <a name="performance"></a>Производительность  
 `Double` является наиболее эффективным дробных типов данных, поскольку процессоры на современных платформах выполняют операции с плавающей запятой с двойной точностью. Тем не менее операции с `Double` не выполняются так же быстро, как и для целочисленных типов, таких как `Integer`.  
  
### <a name="small-magnitudes"></a>Малые величины  
 Для чисел с наименьшей возможной величиной (наиболее близкое к 0) `Double` переменных может содержать числа, как - 4, 94065645841246544E-324 для отрицательных значений и 4, 94065645841246544E-324 для положительных значений.  
  
### <a name="small-fractional-numbers"></a>Небольшой дробных чисел  
 Если не требуется полный диапазон `Double` тип данных, вы можете использовать `Single` тип данных, который может хранить числа с плавающей запятой от - 3, 4028235E + 38 до 3, 4028235E + 38. Минимальные значения `Single` переменные являются - 1, 401298E-45 для отрицательных значений и 1, 401298E-45 для положительных значений. Если имеется большое количество переменных, которые содержат небольшого числа с плавающей запятой, среда может хранить иногда вашей `Single` переменные более эффективно и снизить потребление памяти.  
  
## <a name="see-also"></a>См. также  
 [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Символьные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)  
 [Прочие типы данных](../../../../visual-basic/programming-guide/language-features/data-types/miscellaneous-data-types.md)  
 [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа](../../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
