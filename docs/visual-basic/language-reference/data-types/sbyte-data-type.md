---
title: Тип данных SByte (Visual Basic)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 20a5a9182da50345f97331e6f01e0e3665a2a61c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591425"
---
# <a name="sbyte-data-type-visual-basic"></a>Тип данных SByte (Visual Basic)

Содержит знаком 8-разрядное (1-байтовые) целые числа в диапазоне от -128 до 127.  
  
## <a name="remarks"></a>Примечания

Используйте `SByte` тип данных для хранения целых значений, которые не требуют полного размера `Integer` или даже половины данных ширина `Short`. В некоторых случаях среда можно упаковать вашей `SByte` переменные тесном контакте и снизить потребление памяти.

Значение по умолчанию для типа `SByte` — 0.

## <a name="literal-assignments"></a>Литерал назначения
  
Можно объявить и инициализировать `SByte` переменной, назначив его десятичное литералом, Шестнадцатеричный литерал восьмеричного литерала, или (начиная с Visual Basic 2017 г) двоичный литерал.

В следующем примере целых чисел, равные-102, представленное в десятичном, шестнадцатеричном виде, и двоичные литералы назначены `SByte` значения. Для этого примера требуются компиляции с параметром `/removeintchecks` переключатель компилятора.

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]  

> [!NOTE] 
> Используйте префикс `&h` или `&H` для обозначения Шестнадцатеричный литерал префиксом `&b` или `&B` для обозначения двоичный литерал и префикс `&o` или `&O` для обозначения восьмеричного литерала. У десятичных литералов префиксов нет.

Начиная с Visual Basic 2017 г., можно также использовать знак подчеркивания `_`, как разделитель для повышения удобства чтения, как в следующем примере показано.

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]  

Начиная с Visual Basic 15,5, можно также использовать символ подчеркивания (`_`) в качестве начальных разделителя между префиксом и двоичное, шестнадцатеричное или восьмеричное цифры. Пример:

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Если целочисленный литерал выходит за пределы диапазона `SByte` (то есть, если он меньше <xref:System.SByte.MinValue?displayProperty=nameWithType> или больше <xref:System.SByte.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции. Если целочисленный литерал не имеет суффикса, [целое](integer-data-type.md) выводится. Если целочисленный литерал находится за пределами диапазона `Integer` типа, [длинные](long-data-type.md) выводится. Это означает, что в предыдущих примерах, числовые литералы `0x9A` и `0b10011010` интерпретируются как 32-разрядных целых чисел со знаком со значением 156, что превышает <xref:System.SByte.MaxValue?displayProperty=nameWithType>. Для успешной компиляции кода, например, назначающий целое число без десятичного `SByte`, можно выполнить одно из следующих действий:

- Отключение проверки границ для целочисленных значений при компиляции с `/removeintchecks` переключатель компилятора.

- Используйте [символ типа](../../programming-guide\language-features\data-types/type-characters.md) явно задать литеральное значение, которое вы хотите назначить `SByte`. В следующем примере присваивается отрицательное литерал `Short` значение `SByte`. Обратите внимание, что для отрицательных чисел, необходимо задать старших битов высокого порядка слова числового литерала. В случае в нашем примере это имеет тип bit 15 литерала `Short` значение.

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a>Советы по программированию
  
-   **CLS-совместимости.** `SByte` Тип данных не является частью [спецификации CLS](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), поэтому CLS-совместимого кода нельзя использовать компонент, который его использует.

-   **Расширяющие.** `SByte` Тип данных может быть расширен до `Short`, `Integer`, `Long`, `Decimal`, `Single`, и `Double`. Это означает, что можно преобразовать `SByte` на любой из этих типов без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.
  
-   **Символы типов.** `SByte` не имеет знак типа литерала или знак типа идентификатора.  
  
-   **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.SByte?displayProperty=nameWithType>.
  
## <a name="see-also"></a>См. также

 <xref:System.SByte?displayProperty=nameWithType>  
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Тип данных Short](../../../visual-basic/language-reference/data-types/short-data-type.md)  
 [Тип данных Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [Тип данных Long](../../../visual-basic/language-reference/data-types/long-data-type.md)  
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
