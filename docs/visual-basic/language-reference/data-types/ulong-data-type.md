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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401319"
---
# <a name="ulong-data-type-visual-basic"></a>ULong тип данных (Visual Basic)

Держит неподписанные 64-разрядные (8-байт) бесых в диапазоне от 0 до 18 446 744 073 709 551 615 (более 1,84 раза 10 и 19).

## <a name="remarks"></a>Remarks

Используйте `ULong` тип данных для хранения `UInteger`двоичных данных слишком большой для, или максимально возможных неподписанных значения бесчисленности.

Значение по умолчанию для типа `ULong` — 0.

## <a name="literal-assignments"></a>Литературные задания

Вы можете объявить `ULong` и инициализировать переменную, назначив ей десятичную буквальную, гексадецичную буквальную, октальную буквальную или (начиная с Visual Basic 2017) двоичный буквальный. Если целочисленный литерал выходит за пределы диапазона `ULong` (то есть, если он меньше <xref:System.UInt64.MinValue?displayProperty=nameWithType> или больше <xref:System.UInt64.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.

В следующем примере целые числа, равные 7 934 076 125 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `ULong`.

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE]
> Вы используете `&h` приставку или `&H` для обозначения гексадецимального буквального, приставки `&b` или `&B` для `&o` `&O` обозначения двоичного буквального, и приставки или для обозначения октал буквального. У десятичных литералов префиксов нет.

Начиная с Visual Basic 2017, вы также `_`можете использовать символ подчеркивания, как цифровой сепаратор для повышения читаемости, как показано в следующем примере.

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

Начиная с Visual Basic 15.5, вы также`_`можете использовать символ подчеркивателя ( ) в качестве ведущего сепаратора между приставкой и гексадецичными, бинарными или октальными цифрами. Пример:

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Число в перечном виде `UL` `ul` может также включать `ULong` символ или [тип](../../programming-guide/language-features/data-types/type-characters.md) для обозначения типа данных, как показано в следующем примере.

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a>Советы по программированию

- **Отрицательные числа.** Поскольку `ULong` он является неподписанным типом, он не может представлять отрицательное число. Если вы используете необезыщаемый минус`-` `ULong`() оператора на выражение, которое оценивает вводить, Visual Basic преобразует выражение в `Decimal` первое.

- **Соответствие требованиям CLS.** Тип `ULong` данных не является частью [спецификации общего языка](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), поэтому код, совместимый с CLS, не может потреблять компонент, который его использует.

- **Вопросы взаимодействия.** Если вы взаимосвязаны с компонентами, не записанными для рамочного соглашения .NET, например объектами Automation или COM, имейте в виду, что такие типы, как, `ulong` могут иметь различную ширину данных (32 бита) в других средах. Если вы передаете 32-битный аргумент такому `UInteger` компоненту, объявите его, а не `ULong` в управляемом коде Visual Basic.

  Кроме того, Automation не поддерживает 64-разрядные пакеты на Windows 95, Windows 98, Windows ME или Windows 2000. На этих платформах `ULong` невозможно передать элемент Visual Basic компоненту автоматизации.

- **Расширение.** Тип `ULong` данных расширяется `Single`до `Double` `Decimal`, и . Это означает, `ULong` что вы можете преобразовать <xref:System.OverflowException?displayProperty=nameWithType> в любой из этих типов, не сталкиваясь с ошибкой.

- **Тип символов.** Придаток символов `UL` буквального типа к буквальному `ULong` заставляет его типа данных. `ULong`не имеет символа типа идентификатора.

- **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.UInt64?displayProperty=nameWithType>.

## <a name="see-also"></a>См. также раздел

- <xref:System.UInt64>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
