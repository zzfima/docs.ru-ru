---
title: Тип данных Long
ms.date: 01/31/2018
f1_keywords:
- vb.Long
helpviewer_keywords:
- identifier type characters [Visual Basic], &
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- '& identifier type character'
- integer numbers
- literal type characters [Visual Basic], L
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- L literal type character [Visual Basic]
- integers [Visual Basic], types
- Long keyword [Visual Basic]
- data types [Visual Basic], integral
- data types [Visual Basic], assigning
- Long data type
ms.assetid: b4770c34-1804-4f8c-b512-c10b0893e516
ms.openlocfilehash: 16d7409c802e97b1f33474d810134db4d9f0ad6c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343978"
---
# <a name="long-data-type-visual-basic"></a>Тип данных Long (Visual Basic)

Содержит 64-битные (8-байтные) целые числа со знаком в диапазоне от-9223372036854775808 до 9 223 372 036 854 775 807 (1 – 7... E + 18).

## <a name="remarks"></a>Заметки

Используйте тип данных `Long` для хранения целочисленных чисел, которые слишком велики для `Integer` типа данных.

Значение по умолчанию для типа `Long` — 0.

## <a name="literal-assignments"></a>Присваивания литералов

Можно объявить и инициализировать переменную `Long`, назначив ей десятичный литерал, шестнадцатеричный литерал, Восьмеричный литерал или (начиная с Visual Basic 2017) двоичный литерал. Если целочисленный литерал выходит за пределы диапазона `Long` (то есть, если он меньше <xref:System.Int64.MinValue?displayProperty=nameWithType> или больше <xref:System.Int64.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.

В следующем примере целые числа, равные 4 294 967 296 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `Long`.

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]

> [!NOTE]
> Префикс `&h` или `&H` можно использовать для обозначения шестнадцатеричного литерала, префикс `&b` или `&B` для обозначения двоичного литерала, а префикс `&o` или `&O` — для обозначения восьмеричного литерала. У десятичных литералов префиксов нет.

Начиная с Visual Basic 2017 можно также использовать символ подчеркивания `_`в качестве разделителя цифр для повышения удобочитаемости, как показано в следующем примере.

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

Начиная с Visual Basic 15,5 можно также использовать символ подчеркивания (`_`) в качестве начального разделителя между префиксом и шестнадцатеричными, двоичными или восьмеричными цифрами. Пример.

```vb
Dim number As Long = &H_0FAC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Числовые литералы также могут включать [символ типа](../../programming-guide/language-features/data-types/type-characters.md) `L`, чтобы обозначить `Long` тип данных, как показано в следующем примере.

```vb
Dim number = &H_0FAC_0326_1489_D68CL
```

## <a name="programming-tips"></a>Советы по программированию

- **Вопросы взаимодействия.** Если вы взаимодействуете с компонентами, которые не написаны для .NET Framework, например автоматизации или COM-объекты, помните, что `Long` имеет разную ширину данных (32 бит) в других средах. При передаче аргумента 32-bit в такой компонент объявите его как `Integer` вместо `Long` в новом коде Visual Basic.

- **Расширяющие.** Тип данных `Long` расширяется до `Decimal`, `Single`или `Double`. Это означает, что тип `Long` можно преобразовать в любой из этих типов без возникновения ошибки <xref:System.OverflowException?displayProperty=nameWithType>.

- **Символы типа.** При добавлении к литералу символа типа литерала `L` производится принудительное приведение литерала к типу данных `Long`. При добавлении символа идентификатора типа `&` к любому идентификатору производится принудительное приведение этого идентификатора к типу `Long`.

- **Тип платформы.** В .NET Framework данный тип соответствует структуре <xref:System.Int64?displayProperty=nameWithType>.

## <a name="see-also"></a>См. также

- <xref:System.Int64>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Тип данных Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Тип данных Short](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
