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
ms.openlocfilehash: 1da5de4971928ca23a23c4dcfc5f338c4d7a3875
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54719577"
---
# <a name="sbyte-data-type-visual-basic"></a>Тип данных SByte (Visual Basic)

Содержит знаком 8-разрядных целых чисел (1-байтовое), которые могут меняться в диапазоне от -128 до 127.  
  
## <a name="remarks"></a>Примечания

Используйте `SByte` тип данных для хранения целых значений, которые не требуют полного размера `Integer` или даже половины данных ширину `Short`. В некоторых случаях среда CLR можно упаковать в `SByte` переменные в тесном контакте и снизить потребление памяти.

Значение по умолчанию для типа `SByte` — 0.

## <a name="literal-assignments"></a>Назначения литералов
  
Можно объявить и инициализировать `SByte` переменной, назначив ей десятичный литерал, шестнадцатеричный восьмеричный литерал, или (начиная с Visual Basic 2017) двоичный литерал.

В следующем примере целые числа, равные 102 представляются в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются `SByte` значения. В этом примере требуется компилировать с `/removeintchecks` параметр компилятора.

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]  

> [!NOTE] 
> Используйте префикс `&h` или `&H` для обозначения шестнадцатеричного литерала, префикс `&b` или `&B` для обозначения двоичного литерала, а также префикс `&o` или `&O` для обозначения восьмеричный литерал. У десятичных литералов префиксов нет.

Начиная с Visual Basic 2017, можно также использовать символ подчеркивания, `_`, в качестве разделителя разрядов для повышения удобства чтения, как в примере ниже показан.

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]  

Начиная с Visual Basic 15.5, можно также использовать символ подчеркивания (`_`) в качестве начального разделителя между префиксом и двоичное, шестнадцатеричное или восьмеричное цифры. Пример:

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Если целочисленный литерал выходит за пределы диапазона `SByte` (то есть, если он меньше <xref:System.SByte.MinValue?displayProperty=nameWithType> или больше <xref:System.SByte.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции. Если целочисленный литерал не имеет суффикса, [целое число](integer-data-type.md) выводится. Если целочисленный литерал выходит за пределы диапазона `Integer` типа, [Long](long-data-type.md) выводится. Это означает, что в предыдущих примерах, числовые литералы `0x9A` и `0b10011010` интерпретируются как 32-разрядных целых чисел со знаком с имеющие значение 156, превышающее <xref:System.SByte.MaxValue?displayProperty=nameWithType>. Для успешной компиляции кода, например, присваивает недесятичных целое число для `SByte`, можно выполнить одно из следующих:

- Отключение проверки границ для целочисленных значений при компиляции с `/removeintchecks` параметр компилятора.

- Используйте [символ типа](../../programming-guide/language-features/data-types/type-characters.md) для явного определения литеральное значение, которое вы хотите назначить `SByte`. В следующем примере присваивается отрицательное литерал `Short` значение `SByte`. Обратите внимание, что для отрицательных чисел, необходимо установить бит высокого порядка из старшего слова числового литерала. В нашем примере это бит 15 литерала `Short` значение.

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a>Советы по программированию
  
-   **CLS-совместимость.** `SByte` Тип данных не является частью [спецификация CLS](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), поэтому CLS-совместимого кода нельзя использовать компонент, который его использует.

-   **Расширяющие.** `SByte` Тип данных можно расширить до `Short`, `Integer`, `Long`, `Decimal`, `Single`, и `Double`. Это означает, что вы можете преобразовать `SByte` к любому из этих типов без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.
  
-   **Символы типа.** `SByte` не имеет знак типа литерала или знак типа идентификатора.  
  
-   **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.SByte?displayProperty=nameWithType>.
  
## <a name="see-also"></a>См. также

- <xref:System.SByte?displayProperty=nameWithType>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Тип данных Short](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [Тип данных Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Тип данных Long](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
