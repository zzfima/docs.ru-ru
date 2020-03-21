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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401385"
---
# <a name="sbyte-data-type-visual-basic"></a>Тип данных SByte (Visual Basic)

Держит подписанные 8-битные (1-байт) целые столбы, которые варьируются в цене от -128 до 127.

## <a name="remarks"></a>Remarks

Используйте `SByte` тип данных, чтобы содержать целые значения, которые `Integer` не требуют полной `Short`ширины данных или даже половины ширины данных. В некоторых случаях время выполнения общего языка `SByte` может быть в состоянии упаковать переменные близко друг к другу и сохранить потребление памяти.

Значение по умолчанию для типа `SByte` — 0.

## <a name="literal-assignments"></a>Литературные задания

Вы можете объявить `SByte` и инициализировать переменную, назначив ей десятичную буквальную, гексадецичную буквальную, октальную буквальную или (начиная с Visual Basic 2017) двоичный буквальный.

В следующем примере значениям присваиваются `SByte` целые столбы, равные -102, которые представлены как десятичные, гексадецимальные и бинарные буквальные значения. Этот пример требует компиляции с коммутатором компилятора. `/removeintchecks`

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]

> [!NOTE]
> Вы используете `&h` приставку или `&H` для обозначения гексадецимального буквального, приставки `&b` или `&B` для `&o` `&O` обозначения двоичного буквального, и приставки или для обозначения октал буквального. У десятичных литералов префиксов нет.

Начиная с Visual Basic 2017, вы также `_`можете использовать символ подчеркивания, как цифровой сепаратор для повышения читаемости, как показано в следующем примере.

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]

Начиная с Visual Basic 15.5, вы также`_`можете использовать символ подчеркивателя ( ) в качестве ведущего сепаратора между приставкой и гексадецичными, бинарными или октальными цифрами. Пример:

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Если целочисленный литерал выходит за пределы диапазона `SByte` (то есть, если он меньше <xref:System.SByte.MinValue?displayProperty=nameWithType> или больше <xref:System.SByte.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции. Когда в буквальном смысле нет суффикса, выводит [integer.](integer-data-type.md) Если целый буквальный находится за пределами диапазона `Integer` типа, [Лонг](long-data-type.md) выводит. Это означает, что в предыдущих примерах, `0x9A` `0b10011010` числовы и интерпретируются как 32-битные подписанные целые числа со значением 156, что превышает <xref:System.SByte.MaxValue?displayProperty=nameWithType>. Для успешной компиляции кода, как это, что присваивает не-десятичной целый `SByte`ряд, вы можете сделать любой из следующих:

- Отключение рядовых границ проверяется путем `/removeintchecks` компиляции с компилятором.

- Используйте [символ типа,](../../programming-guide/language-features/data-types/type-characters.md) чтобы точно определить буквальное значение, `SByte`которое вы хотите присвоить . Следующий пример присваивает отрицательное буквальное `Short` значение . `SByte` Обратите внимание, что для отрицательных чисел необходимо установить бит высокого порядка слова в цифровом букве. В случае нашего примера, это бит 15 `Short` буквального значения.

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a>Советы по программированию

- **Соответствие требованиям CLS.** Тип `SByte` данных не является частью [спецификации общего языка](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), поэтому код, совместимый с CLS, не может потреблять компонент, который его использует.

- **Расширение.** Тип `SByte` данных расширяется `Integer` `Long`до `Decimal` `Short` `Single`, `Double`, , и . Это означает, `SByte` что вы можете преобразовать <xref:System.OverflowException?displayProperty=nameWithType> в любой из этих типов, не сталкиваясь с ошибкой.

- **Тип символов.** `SByte`не имеет буквального символа типа или символа типа идентификатора.

- **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.SByte?displayProperty=nameWithType>.

## <a name="see-also"></a>См. также раздел

- <xref:System.SByte?displayProperty=nameWithType>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Тип данных Short](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [Тип данных негров](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Тип данных Long](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
