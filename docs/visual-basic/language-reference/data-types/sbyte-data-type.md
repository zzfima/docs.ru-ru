---
title: Тип данных SByte
ms.date: 04/20/2017
f1_keywords:
- vb.sbyte
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- SByte data type
ms.assetid: 5c38374a-18a1-4cc2-b493-299e3dcaa60f
ms.openlocfilehash: 01a0a4a261213d7e6e2016bf49128092e5b22308
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343951"
---
# <a name="sbyte-data-type-visual-basic"></a>Тип данных SByte (Visual Basic)

Содержит 8-битные (1-байтные) целые числа со знаком в диапазоне от-128 до 127.

## <a name="remarks"></a>Примечания

Используйте тип данных `SByte` для хранения целочисленных значений, не требующих полной ширины данных `Integer` или даже половины ширины данных `Short`. В некоторых случаях среда CLR может одновременно упаковать переменные `SByte` и сэкономить потребление памяти.

Значение по умолчанию для типа `SByte` — 0.

## <a name="literal-assignments"></a>Присваивания литералов

Можно объявить и инициализировать переменную `SByte`, назначив ей десятичный литерал, шестнадцатеричный литерал, Восьмеричный литерал или (начиная с Visual Basic 2017) двоичный литерал.

В следующем примере целые числа, равные-102, представленные в виде десятичного, шестнадцатеричного и двоичного литерала, присваиваются `SByte` значениям. В этом примере требуется компиляция с параметром компилятора `/removeintchecks`.

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]

> [!NOTE]
> Префикс `&h` или `&H` можно использовать для обозначения шестнадцатеричного литерала, префикс `&b` или `&B` для обозначения двоичного литерала, а префикс `&o` или `&O` — для обозначения восьмеричного литерала. У десятичных литералов префиксов нет.

Начиная с Visual Basic 2017 можно также использовать символ подчеркивания `_`в качестве разделителя цифр для повышения удобочитаемости, как показано в следующем примере.

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]

Начиная с Visual Basic 15,5 можно также использовать символ подчеркивания (`_`) в качестве начального разделителя между префиксом и шестнадцатеричными, двоичными или восьмеричными цифрами. Пример.

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Если целочисленный литерал выходит за пределы диапазона `SByte` (то есть, если он меньше <xref:System.SByte.MinValue?displayProperty=nameWithType> или больше <xref:System.SByte.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции. Если у целочисленного литерала нет суффикса, выводится [целое число](integer-data-type.md) . Если целочисленный литерал находится вне диапазона `Integer` типа, выводится [Long](long-data-type.md) . Это означает, что в предыдущих примерах числовые литералы `0x9A` и `0b10011010` интерпретируется как 32-разрядные целые числа со знаком со значением 156, что превышает <xref:System.SByte.MaxValue?displayProperty=nameWithType>. Чтобы успешно скомпилировать код, подобный этому, который присваивает `SByte`недесятичное целое числом, можно выполнить одно из следующих действий.

- Отключает проверку целочисленных границ путем компиляции с параметром компилятора `/removeintchecks`.

- Используйте [символ типа](../../programming-guide/language-features/data-types/type-characters.md) , чтобы явно определить литеральное значение, которое необходимо назначить `SByte`. В следующем примере для `SByte`присваивается отрицательное литеральное значение `Short`. Обратите внимание, что для отрицательных чисел необходимо задать старшие разрядные слова в числовом литерале с высоким порядком. В нашем примере это бит 15 литерала `Short` value.

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a>Советы по программированию

- **Соответствие CLS.** Тип данных `SByte` не является частью [спецификации](https://www.ecma-international.org/publications/standards/Ecma-335.htm) CLS, поэтому CLS-совместимый код не может использовать компонент, который его использует.

- **Расширяющие.** Тип данных `SByte` расширяется до `Short`, `Integer`, `Long`, `Decimal`, `Single`и `Double`. Это означает, что можно преобразовать `SByte` в любой из этих типов без возникновения ошибки <xref:System.OverflowException?displayProperty=nameWithType>.

- **Символы типа.** `SByte` не имеет символа типа литерала или символа типа идентификатора.

- **Тип платформы.** В .NET Framework данный тип соответствует структуре <xref:System.SByte?displayProperty=nameWithType>.

## <a name="see-also"></a>См. также

- <xref:System.SByte?displayProperty=nameWithType>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Тип данных Short](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [Тип данных Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Тип данных Long](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
