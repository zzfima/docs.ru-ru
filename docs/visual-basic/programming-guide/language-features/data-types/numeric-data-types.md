---
title: "Числовые типы данных (Visual Basic) | Документы Microsoft"
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
- integral types, Visual Basic
- Short data type, numeric data types
- Double data type, numeric data types
- Long data type, Visual Basic numeric data types
- numbers, whole
- fractions
- numbers
- whole numbers
- integer numbers
- numbers, integer
- fractional data types
- mantissas, of fractional numbers
- mantissas
- data types [Visual Basic], numeric
- Integer data type, numeric data types
- exponent, of fractional numbers
- integers
- numeric data types, Visual Basic
- Single data type, numeric types
- Decimal data type, numeric data types
ms.assetid: a27bd4d0-7e14-43eb-9cc4-b42eaab323c9
caps.latest.revision: 25
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 3c3098370b8d9dcb6aafcb06dcfb8f4e144b899a
ms.lasthandoff: 03/13/2017

---
# <a name="numeric-data-types-visual-basic"></a>Числовые типы данных (Visual Basic)
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]предоставляет несколько *числовые типы данных* для обработки чисел в различном представлении. *Целочисленный* типы представляют собой только целые числа (положительные, отрицательные и ноль), и *нецелочисленным* — числа с целой и дробной частей.  
  
 Для таблицы, сравнение side-by-side [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] типы данных в разделе [типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## <a name="integral-numeric-types"></a>Целочисленные типы  
 *Целочисленные типы данных* представляют собой только числа без дробной части.  
  
 *Подписью* целые типы данных [тип данных SByte](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md) (8-разрядный), [тип данных Short](../../../../visual-basic/language-reference/data-types/short-data-type.md) (16-разрядная версия), [целочисленный тип данных](../../../../visual-basic/language-reference/data-types/integer-data-type.md) (32-разрядная версия), и [тип данных Long](../../../../visual-basic/language-reference/data-types/long-data-type.md) (64-разрядная версия). Если переменная всегда хранит целые числа, а не дробных чисел, объявите его в качестве одного из этих типов.  
  
 *Без знака* целочисленные типы имеют [тип данных Byte](../../../../visual-basic/language-reference/data-types/byte-data-type.md) (8-разрядный), [тип данных UShort](../../../../visual-basic/language-reference/data-types/ushort-data-type.md) (16-разрядная версия), [UInteger-тип данных](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md) (32-разрядная версия), и [тип данных ULong](../../../../visual-basic/language-reference/data-types/ulong-data-type.md) (64-разрядная версия). Если переменная содержит двоичные данные или данные неизвестной природы, следует объявите ее как один из этих типов.  
  
### <a name="performance"></a>Производительность  
 Арифметические операции выполняются быстрее с целыми типами, чем с другими типами данных. Они являются наиболее быстрым `Integer` и `UInteger` типы в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
### <a name="large-integers"></a>Больших целых чисел  
 Если необходимо хранить целое число больше, чем `Integer` может содержать тип данных, можно использовать `Long` тип данных. `Long`переменные могут содержать числа в диапазоне от -9223372036854775808 до 9223372036854775807. Операции с `Long` немного медленнее, чем с `Integer`.  
  
 Если требуется, чтобы еще больше значений, можно использовать [тип данных Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md). Можно хранить числа в диапазоне от -79,228,162,514,264,337,593,543,950,335 до 79,228,162,514,264,337,593,543,950,335 в `Decimal` переменной, если вы не используете десятичные разряды. Однако операции с `Decimal` номера выполняются значительно медленнее, чем с любым другим типом числовых данных.  
  
### <a name="small-integers"></a>Двухбайтовые целые числа  
 Если не требуется полный диапазон `Integer` тип данных, можно использовать `Short` тип данных, который может содержать целые числа от-32 768 до 32 767. Для диапазона наименьшее целое число `SByte` тип данных содержит целые числа от -128 до 127. Если имеется большое количество переменных, которые содержат двухбайтовые целые числа, общеязыковая среда выполнения, иногда можно хранить на `Short` и `SByte` переменные более эффективно и снизить потребление памяти. Однако операции с `Short` и `SByte` выполняются медленнее, чем с `Integer`.  
  
### <a name="unsigned-integers"></a>Целые числа без знака  
 Если вы знаете, что переменная никогда не должна содержать отрицательное число, можно использовать *беззнаковых типов*`Byte`, `UShort`, `UInteger`, и `ULong`. Каждый из этих типов данных может содержать положительное целое число два раза превосходящее его соответствующий знаковый тип (`SByte`, `Short`, `Integer`, и `Long`). С точки зрения производительности каждый тип без знака точно так же эффективно, как соответствующий тип со знаком. В частности `UInteger` совместно `Integer` являются наиболее эффективными из всех типов простейших числовых данных.  
  
## <a name="nonintegral-numeric-types"></a>Нецелочисленный числовые типы  
 *Типы данных нецелочисленный* представляют собой числа с целой и дробной частей.  
  
 Нецелочисленный числовыми типами данных являются `Decimal` (128 бит с фиксированной запятой), [одного типа данных](../../../../visual-basic/language-reference/data-types/single-data-type.md) (32-разрядных чисел с плавающей запятой), и [тип данных Double](../../../../visual-basic/language-reference/data-types/double-data-type.md) (64-разрядных чисел с плавающей запятой). Они являются все подписанные типами. Если переменная может содержать дробную часть, следует объявите ее как один из этих типов.  
  
 `Decimal`не является типом данных с плавающей запятой. `Decimal`числа имеют двоичное целое значение и масштабный коэффициент целых чисел, который определяет, какая часть значения является десятичной дробью.  
  
 Можно использовать `Decimal` переменные для денежных значений. Преимущество имеет точность значений. `Double` Тип данных выполняется быстрее и требует меньше памяти, но она подвержена ошибкам округления. `Decimal` Тип данных сохраняет полную точность до 28 десятичных разрядов.  
  
 С плавающей запятой (`Single` и `Double`) числа имеют большие диапазоны, чем `Decimal` числа, но могут возникать ошибки округления. Типы с плавающей запятой поддерживают меньшее количество значащих цифр, чем `Decimal` , но могут представлять значения большей величины.  
  
 Нецелочисленные значения могут быть выражены как mmmEeee, в которых mmm является *мантиссы* (значащими цифрами), а eee — *экспоненты* (степень 10). Максимальные положительные значения для нецелочисленных типов являются 7.9228162514264337593543950335E + 28 для `Decimal`, 3, 4028235E + 38 для `Single`и 1, 79769313486231570E + 308 для `Double`.  
  
### <a name="performance"></a>Производительность  
 `Double`является наиболее эффективным из дробных типов данных, поскольку процессоры на современных платформах выполняют операции с плавающей запятой с двойной точностью. Однако операции с `Double` не так же быстро, как и в случае целочисленные типы, такие как `Integer`.  
  
### <a name="small-magnitudes"></a>Малые величины  
 Для чисел с наименьшей возможной величиной (стремящейся к 0) `Double` переменные могут содержать числа, как - 4, 94065645841246544E-324 для отрицательных значений и 4, 94065645841246544E-324 для положительных значений.  
  
### <a name="small-fractional-numbers"></a>Малые дробные числа  
 Если не требуется полный диапазон `Double` тип данных, можно использовать `Single` тип данных, который может хранить числа с плавающей запятой от - 3, 4028235E + 38 до 3, 4028235E + 38. Минимальные значения `Single` переменные, - 1, 401298E-45 для отрицательных значений и 1, 401298E-45 для положительных значений. Если имеется большое количество переменных, которые содержат небольшие числа с плавающей запятой, общеязыковая среда выполнения, иногда можно хранить на `Single` переменные более эффективно и снизить потребление памяти.  
  
## <a name="see-also"></a>См. также  
 [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Символьные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)   
 [Прочие типы данных](../../../../visual-basic/programming-guide/language-features/data-types/miscellaneous-data-types.md)   
 [Устранение неполадок типы данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа](../../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
