---
title: Тип данных Short
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
ms.openlocfilehash: 8dfdfb56de32e4b3a96729b09ccf46a6fee9a424
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343938"
---
# <a name="short-data-type-visual-basic"></a>Короткий тип данных (Visual Basic)

Содержит 16-битные (2-байтные) целые числа со знаком в диапазоне от-32 768 до 32 767.  
  
## <a name="remarks"></a>Примечания  

 Используйте тип данных `Short` для хранения целочисленных значений, не требующих полной ширины данных `Integer`. В некоторых случаях среда CLR может объединять переменные `Short` и экономить потребление памяти.  
  
 Значение по умолчанию для типа `Short` — 0.  
  
## <a name="literal-assignments"></a>Присваивания литералов

Можно объявить и инициализировать переменную `Short`, назначив ей десятичный литерал, шестнадцатеричный литерал, Восьмеричный литерал или (начиная с Visual Basic 2017) двоичный литерал. Если целочисленный литерал выходит за пределы диапазона `Short` (то есть, если он меньше <xref:System.Int16.MinValue?displayProperty=nameWithType> или больше <xref:System.Int16.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.

В следующем примере целые числа, равные 1 034, представленные в виде десятичного, шестнадцатеричного и двоичного литерала, неявно преобразуются из [целого числа](integer-data-type.md) в `Short` значения.

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> Префикс `&h` или `&H` можно использовать для обозначения шестнадцатеричного литерала, префикс `&b` или `&B` для обозначения двоичного литерала, а префикс `&o` или `&O` — для обозначения восьмеричного литерала. У десятичных литералов префиксов нет.

Начиная с Visual Basic 2017 можно также использовать символ подчеркивания `_`в качестве разделителя цифр для повышения удобочитаемости, как показано в следующем примере.

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

Начиная с Visual Basic 15,5 можно также использовать символ подчеркивания (`_`) в качестве начального разделителя между префиксом и шестнадцатеричными, двоичными или восьмеричными цифрами. Пример.

```vb
Dim number As Short = &H_3264
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Числовые литералы также могут включать [символ типа](../../programming-guide/language-features/data-types/type-characters.md) `S`, чтобы обозначить `Short` тип данных, как показано в следующем примере.

```vb
Dim number = &H_3264S
```

## <a name="programming-tips"></a>Советы по программированию

- **Расширяющие.** Тип данных `Short` расширяется до `Integer`, `Long`, `Decimal`, `Single`или `Double`. Это означает, что тип `Short` можно преобразовать в любой из этих типов без возникновения ошибки <xref:System.OverflowException?displayProperty=nameWithType>.  
  
- **Символы типа.** При добавлении к литералу символа типа литерала `S` производится принудительное приведение литерала к типу данных `Short`. `Short` не имеет символа типа идентификатора.  
  
- **Тип платформы.** В .NET Framework данный тип соответствует структуре <xref:System.Int16?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Int16?displayProperty=nameWithType>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Тип данных Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Тип данных Long](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
