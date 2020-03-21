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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401343"
---
# <a name="short-data-type-visual-basic"></a>Короткий тип данных (Visual Basic)

Держит подписанные 16-битные (2-байт) целые столбы, которые варьируются в цене от -32,768 до 32,767.  
  
## <a name="remarks"></a>Remarks  

 Используйте `Short` тип данных для содержащих целые значения, которые `Integer`не требуют полной ширины данных. В некоторых случаях время выполнения общего `Short` языка может упаковать переменные близко друг к другу и сохранить потребление памяти.  
  
 Значение по умолчанию для типа `Short` — 0.  
  
## <a name="literal-assignments"></a>Литературные задания

Вы можете объявить `Short` и инициализировать переменную, назначив ей десятичную буквальную, гексадецичную буквальную, октальную буквальную или (начиная с Visual Basic 2017) двоичный буквальный. Если целочисленный литерал выходит за пределы диапазона `Short` (то есть, если он меньше <xref:System.Int16.MinValue?displayProperty=nameWithType> или больше <xref:System.Int16.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.

В следующем примере целые 1034, которые представлены как десятичные, гексадецимальные и бинарные буквальные, `Short` неявно преобразуются из [Integer](integer-data-type.md) в значения.

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> Вы используете `&h` приставку или `&H` для обозначения гексадецимального буквального, приставки `&b` или `&B` для `&o` `&O` обозначения двоичного буквального, и приставки или для обозначения октал буквального. У десятичных литералов префиксов нет.

Начиная с Visual Basic 2017, вы также `_`можете использовать символ подчеркивания, как цифровой сепаратор для повышения читаемости, как показано в следующем примере.

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

Начиная с Visual Basic 15.5, вы также`_`можете использовать символ подчеркивателя ( ) в качестве ведущего сепаратора между приставкой и гексадецичными, бинарными или октальными цифрами. Пример:

```vb
Dim number As Short = &H_3264
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Число в цифрах может `S` также включать [символ](../../programming-guide/language-features/data-types/type-characters.md) `Short` типа для обозначения типа данных, как показано в следующем примере.

```vb
Dim number = &H_3264S
```

## <a name="programming-tips"></a>Советы по программированию

- **Расширение.** Тип `Short` данных расширяется `Long` `Decimal`до `Single` `Integer`, `Double`, , или . Это означает, что тип `Short` можно преобразовать в любой из этих типов без возникновения ошибки <xref:System.OverflowException?displayProperty=nameWithType>.  
  
- **Тип символов.** При добавлении к литералу символа типа литерала `S` производится принудительное приведение литерала к типу данных `Short`. `Short`не имеет символа типа идентификатора.  
  
- **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.Int16?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Int16?displayProperty=nameWithType>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Тип данных негров](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Тип данных Long](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
