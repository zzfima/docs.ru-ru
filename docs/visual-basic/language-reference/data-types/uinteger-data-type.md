---
title: Тип данных UInteger
ms.date: 01/31/2018
f1_keywords:
- vb.uinteger
helpviewer_keywords:
- numbers [Visual Basic], whole
- UInteger data type
- literal type characters [Visual Basic], UI
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- UI literal type characters [Visual Basic]
- data types [Visual Basic], integral
ms.assetid: db7ddd34-4f23-46f5-84dd-8b0f83bb8729
ms.openlocfilehash: ccff61608aed797734cb4f5ca0571d7ed73ba98b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343889"
---
# <a name="uinteger-data-type"></a>UInteger - тип данных

Содержит 32-разрядные (4-байтные) целые числа без знака, имеющие значение от 0 до 4 294 967 295.

## <a name="remarks"></a>Примечания

Тип данных `UInteger` предоставляет наибольшее значение без знака в наиболее эффективной ширине данных.

Значение по умолчанию для типа `UInteger` — 0.

## <a name="literal-assignments"></a>Присваивания литералов

Можно объявить и инициализировать переменную `UInteger`, назначив ей десятичный литерал, шестнадцатеричный литерал, Восьмеричный литерал или (начиная с Visual Basic 2017) двоичный литерал. Если целочисленный литерал выходит за пределы диапазона `UInteger` (то есть, если он меньше <xref:System.UInt32.MinValue?displayProperty=nameWithType> или больше <xref:System.UInt32.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.

В следующем примере целые числа, равные 3 000 000 000 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `UInteger`.

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]

> [!NOTE]
> Префикс `&h` или `&H` можно использовать для обозначения шестнадцатеричного литерала, префикс `&b` или `&B` для обозначения двоичного литерала, а префикс `&o` или `&O` — для обозначения восьмеричного литерала. У десятичных литералов префиксов нет.

Начиная с Visual Basic 2017 можно также использовать символ подчеркивания `_`в качестве разделителя цифр для повышения удобочитаемости, как показано в следующем примере.

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]

Начиная с Visual Basic 15,5 можно также использовать символ подчеркивания (`_`) в качестве начального разделителя между префиксом и шестнадцатеричными, двоичными или восьмеричными цифрами. Пример.

```vb
Dim number As UInteger = &H_0F8C_0326
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Числовые литералы могут также включать [символ](../../programming-guide/language-features/data-types/type-characters.md) `UI` или `ui`, чтобы обозначить тип данных `UInteger`, как показано в следующем примере.

```vb
Dim number = &H_0FAC_14D7ui
```

## <a name="programming-tips"></a>Советы по программированию

Типы данных `UInteger` и `Integer` обеспечивают оптимальную производительность на 32-разрядном процессоре, поскольку меньшие целочисленные типы (`UShort`, `Short`, `Byte`и `SByte`), даже если они используют меньшее количество бит, занимают больше времени на загрузку, хранение и выборку.

- **Отрицательные числа.** Поскольку `UInteger` является неподписанным типом, он не может представлять отрицательное число. При использовании оператора унарного минуса (`-`) в выражении, результатом которого является тип `UInteger`, Visual Basic сначала преобразует выражение в `Long`.

- **Соответствие CLS.** Тип данных `UInteger` не является частью [спецификации](https://www.ecma-international.org/publications/standards/Ecma-335.htm) CLS, поэтому CLS-совместимый код не может использовать компонент, который его использует.

- **Вопросы взаимодействия.** Если вы взаимодействуете с компонентами, которые не написаны для .NET Framework, например автоматизации или COM-объекты, помните, что такие типы, как `uint`, могут иметь разную ширину данных (16 бит) в других средах. При передаче 16-разрядного аргумента в такой компонент объявите его как `UShort` вместо `UInteger` в управляемом коде Visual Basic.

- **Расширяющие.** Тип данных `UInteger` расширяется до `Long`, `ULong`, `Decimal`, `Single`и `Double`. Это означает, что можно преобразовать `UInteger` в любой из этих типов без возникновения ошибки <xref:System.OverflowException?displayProperty=nameWithType>.

- **Символы типа.** Добавление символов типа литерала `UI` литерала к типу данных `UInteger`. `UInteger` не имеет символа типа идентификатора.

- **Тип платформы.** В .NET Framework данный тип соответствует структуре <xref:System.UInt32?displayProperty=nameWithType>.

## <a name="see-also"></a>См. также

- <xref:System.UInt32>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
