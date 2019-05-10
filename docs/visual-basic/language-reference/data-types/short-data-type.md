---
title: Тип данных Short (Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.Short
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- S literal type character [Visual Basic]
- Short data type
- literal type characters [Visual Basic], S
ms.assetid: 65fcbcf3-a841-400e-885e-301497729a8b
ms.openlocfilehash: eedc2804652fb6f2f73e7288d6db830a6f4bd98a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647012"
---
# <a name="short-data-type-visual-basic"></a>Тип данных Short (Visual Basic)
Содержит знаком 16-разрядных целых чисел (2-байтовое), которые могут меняться в диапазоне от-32 768 до 32 767.  
  
## <a name="remarks"></a>Примечания  
 Используйте `Short` тип данных для хранения целых значений, которые не требуют полного размера `Integer`. В некоторых случаях среда CLR может с пакетом обновления вашей `Short` переменные в тесном контакте и снизить потребление памяти.  
  
 Значение по умолчанию для типа `Short` — 0.  
  
## <a name="literal-assignments"></a>Назначения литералов

Можно объявить и инициализировать `Short` переменной, назначив ей десятичный литерал, шестнадцатеричный восьмеричный литерал, или (начиная с Visual Basic 2017) двоичный литерал. Если целочисленный литерал выходит за пределы диапазона `Short` (то есть, если он меньше <xref:System.Int16.MinValue?displayProperty=nameWithType> или больше <xref:System.Int16.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.

В следующем примере целые числа, равные 1034 представляются в виде десятичного, шестнадцатеричного и двоичного литерала, неявно преобразуются из [целое число](integer-data-type.md) для `Short` значения.

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> Используйте префикс `&h` или `&H` для обозначения шестнадцатеричного литерала, префикс `&b` или `&B` для обозначения двоичного литерала, а также префикс `&o` или `&O` для обозначения восьмеричный литерал. У десятичных литералов префиксов нет.

Начиная с Visual Basic 2017, можно также использовать символ подчеркивания, `_`, в качестве разделителя разрядов для повышения удобства чтения, как в примере ниже показан.

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

Начиная с Visual Basic 15.5, можно также использовать символ подчеркивания (`_`) в качестве начального разделителя между префиксом и двоичное, шестнадцатеричное или восьмеричное цифры. Пример:

```vb
Dim number As Short = &H_3264
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Числовые литералы могут содержать `S` [символ типа](../../programming-guide/language-features/data-types/type-characters.md) для обозначения `Short` тип данных, как показано в следующем примере.

```vb
Dim number = &H_3264S
```

## <a name="programming-tips"></a>Советы по программированию

- **Расширяющие.** `Short` Тип данных можно расширить до `Integer`, `Long`, `Decimal`, `Single`, или `Double`. Это означает, что тип `Short` можно преобразовать в любой из этих типов без возникновения ошибки <xref:System.OverflowException?displayProperty=nameWithType>.  
  
- **Символы типа.** При добавлении к литералу символа типа литерала `S` производится принудительное приведение литерала к типу данных `Short`. `Short` не имеет тип символа идентификатора.  
  
- **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.Int16?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Int16?displayProperty=nameWithType>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Тип данных Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Тип данных Long](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
