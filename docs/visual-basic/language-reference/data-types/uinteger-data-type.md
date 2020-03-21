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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401379"
---
# <a name="uinteger-data-type"></a>UInteger - тип данных

Держит неподписанные 32-битные (4-байт) многоразовые значения от 0 до 4 294 967 295.

## <a name="remarks"></a>Remarks

Тип `UInteger` данных обеспечивает наибольшее неподписанное значение в наиболее эффективной ширине данных.

Значение по умолчанию для типа `UInteger` — 0.

## <a name="literal-assignments"></a>Литературные задания

Вы можете объявить `UInteger` и инициализировать переменную, назначив ей десятичную буквальную, гексадецичную буквальную, октальную буквальную или (начиная с Visual Basic 2017) двоичный буквальный. Если целочисленный литерал выходит за пределы диапазона `UInteger` (то есть, если он меньше <xref:System.UInt32.MinValue?displayProperty=nameWithType> или больше <xref:System.UInt32.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.

В следующем примере целые числа, равные 3 000 000 000 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `UInteger`.

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]

> [!NOTE]
> Вы используете `&h` приставку или `&H` для обозначения гексадецимального буквального, приставки `&b` или `&B` для `&o` `&O` обозначения двоичного буквального, и приставки или для обозначения октал буквального. У десятичных литералов префиксов нет.

Начиная с Visual Basic 2017, вы также `_`можете использовать символ подчеркивания, как цифровой сепаратор для повышения читаемости, как показано в следующем примере.

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]

Начиная с Visual Basic 15.5, вы также`_`можете использовать символ подчеркивателя ( ) в качестве ведущего сепаратора между приставкой и гексадецичными, бинарными или октальными цифрами. Пример:

```vb
Dim number As UInteger = &H_0F8C_0326
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Число в перечном виде `UI` `ui` может также включать `UInteger` символ или [тип](../../programming-guide/language-features/data-types/type-characters.md) для обозначения типа данных, как показано в следующем примере.

```vb
Dim number = &H_0FAC_14D7ui
```

## <a name="programming-tips"></a>Советы по программированию

`UInteger` Типы `Integer` данных обеспечивают оптимальную производительность на 32-битном процессоре, потому что меньшие типы рядов`UShort`(, `Short` `Byte`и), `SByte`даже если они используют меньше битов, потребуется больше времени для загрузки, хранения и извлечения.

- **Отрицательные числа.** Поскольку `UInteger` он является неподписанным типом, он не может представлять отрицательное число. Если вы используете необезыщаемый минус`-` `UInteger`() оператора на выражение, которое оценивает вводить, Visual Basic преобразует выражение в `Long` первое.

- **Соответствие требованиям CLS.** Тип `UInteger` данных не является частью [спецификации общего языка](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), поэтому код, совместимый с CLS, не может потреблять компонент, который его использует.

- **Вопросы взаимодействия.** Если вы взаимосвязаны с компонентами, не записанными для рамочного соглашения .NET, например объектами Automation или COM, имейте в виду, что такие типы, как, `uint` могут иметь различную ширину данных (16 бит) в других средах. Если вы передаете 16-битный аргумент такому `UShort` компоненту, объявите его, а не `UInteger` в управляемом базовом коде Visual.

- **Расширение.** Тип `UInteger` данных расширяется `ULong` `Decimal`до `Single` `Long`, `Double`, , и . Это означает, `UInteger` что вы можете преобразовать <xref:System.OverflowException?displayProperty=nameWithType> в любой из этих типов, не сталкиваясь с ошибкой.

- **Тип символов.** Придаток символов `UI` буквального типа к буквальному `UInteger` заставляет его типа данных. `UInteger`не имеет символа типа идентификатора.

- **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.UInt32?displayProperty=nameWithType>.

## <a name="see-also"></a>См. также раздел

- <xref:System.UInt32>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
