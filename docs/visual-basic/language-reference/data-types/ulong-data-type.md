---
title: Тип данных ULong
ms.date: 01/31/2018
f1_keywords:
- vb.ulong
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- literal type characters [Visual Basic], UL
- ULong data type
- UL literal type characters [Visual Basic]
ms.assetid: 017e0702-774e-44ae-bedc-786b424ca84e
ms.openlocfilehash: 3c6cd4086e08b808c158948756b4806f098196b9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343886"
---
# <a name="ulong-data-type-visual-basic"></a>Тип данных ULong (Visual Basic)

Содержит 64-разрядные (8-байтные) целые числа без знака в диапазоне от 0 до 18446744073709551615 (более 1,84 раза больше 10 ^ 19).

## <a name="remarks"></a>Примечания

Используйте `ULong` тип данных для хранения двоичных данных, которые слишком велики для `UInteger`, или максимальных возможных целочисленных значений без знака.

Значение по умолчанию для типа `ULong` — 0.

## <a name="literal-assignments"></a>Присваивания литералов

Можно объявить и инициализировать переменную `ULong`, назначив ей десятичный литерал, шестнадцатеричный литерал, Восьмеричный литерал или (начиная с Visual Basic 2017) двоичный литерал. Если целочисленный литерал выходит за пределы диапазона `ULong` (то есть, если он меньше <xref:System.UInt64.MinValue?displayProperty=nameWithType> или больше <xref:System.UInt64.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.

В следующем примере целые числа, равные 7 934 076 125 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `ULong`.

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE]
> Префикс `&h` или `&H` можно использовать для обозначения шестнадцатеричного литерала, префикс `&b` или `&B` для обозначения двоичного литерала, а префикс `&o` или `&O` — для обозначения восьмеричного литерала. У десятичных литералов префиксов нет.

Начиная с Visual Basic 2017 можно также использовать символ подчеркивания `_`в качестве разделителя цифр для повышения удобочитаемости, как показано в следующем примере.

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

Начиная с Visual Basic 15,5 можно также использовать символ подчеркивания (`_`) в качестве начального разделителя между префиксом и шестнадцатеричными, двоичными или восьмеричными цифрами. Пример.

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Числовые литералы могут также включать [символ](../../programming-guide/language-features/data-types/type-characters.md) `UL` или `ul`, чтобы обозначить тип данных `ULong`, как показано в следующем примере.

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a>Советы по программированию

- **Отрицательные числа.** Поскольку `ULong` является неподписанным типом, он не может представлять отрицательное число. При использовании оператора унарного минуса (`-`) в выражении, результатом которого является тип `ULong`, Visual Basic сначала преобразует выражение в `Decimal`.

- **Соответствие CLS.** Тип данных `ULong` не является частью [спецификации](https://www.ecma-international.org/publications/standards/Ecma-335.htm) CLS, поэтому CLS-совместимый код не может использовать компонент, который его использует.

- **Вопросы взаимодействия.** Если вы взаимодействуете с компонентами, которые не написаны для .NET Framework, например автоматизации или COM-объекты, помните, что такие типы, как `ulong`, могут иметь разную ширину данных (32 бит) в других средах. При передаче аргумента 32-bit в такой компонент объявите его как `UInteger`, а не `ULong` в управляемом коде Visual Basic.

  Более того, Автоматизация не поддерживает 64-разрядные целые числа в Windows 95, Windows 98, Windows ME или Windows 2000. Невозможно передать аргумент Visual Basic `ULong` в компонент автоматизации на этих платформах.

- **Расширяющие.** Тип данных `ULong` расширяется до `Decimal`, `Single`и `Double`. Это означает, что можно преобразовать `ULong` в любой из этих типов без возникновения ошибки <xref:System.OverflowException?displayProperty=nameWithType>.

- **Символы типа.** Добавление символов типа литерала `UL` литерала к типу данных `ULong`. `ULong` не имеет символа типа идентификатора.

- **Тип платформы.** В .NET Framework данный тип соответствует структуре <xref:System.UInt64?displayProperty=nameWithType>.

## <a name="see-also"></a>См. также

- <xref:System.UInt64>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
