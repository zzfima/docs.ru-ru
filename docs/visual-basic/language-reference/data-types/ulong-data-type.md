---
title: Тип данных ULong (Visual Basic)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 214243f6a8a87f4e4cc15f31be23275fff00d07d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43465829"
---
# <a name="ulong-data-type-visual-basic"></a>Тип данных ULong (Visual Basic)

Содержит 64-разрядное (8-байтные) целых чисел без знака в диапазоне от 0 до 18446744073709551615 (1,84 раза более чем 10 ^ 19).  
  
## <a name="remarks"></a>Примечания

Используйте `ULong` тип данных для хранения двоичных данных, слишком велик для `UInteger`, или наибольшее возможное без знака целочисленных значений.  
  
Значение по умолчанию для типа `ULong` — 0.

## <a name="literal-assignments"></a>Назначения литералов

Можно объявить и инициализировать `ULong` переменной, назначив ей десятичный литерал, шестнадцатеричный восьмеричный литерал, или (начиная с Visual Basic 2017) двоичный литерал. Если целочисленный литерал выходит за пределы диапазона `ULong` (то есть, если он меньше <xref:System.UInt64.MinValue?displayProperty=nameWithType> или больше <xref:System.UInt64.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.

В следующем примере целые числа, равные 7 934 076 125 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `ULong`.
  
[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE] 
> Используйте префикс `&h` или `&H` для обозначения шестнадцатеричного литерала, префикс `&b` или `&B` для обозначения двоичного литерала, а также префикс `&o` или `&O` для обозначения восьмеричный литерал. У десятичных литералов префиксов нет.

Начиная с Visual Basic 2017, можно также использовать символ подчеркивания, `_`, в качестве разделителя разрядов для повышения удобства чтения, как в примере ниже показан.

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

Начиная с Visual Basic 15.5, можно также использовать символ подчеркивания (`_`) в качестве начального разделителя между префиксом и двоичное, шестнадцатеричное или восьмеричное цифры. Пример:

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Числовые литералы могут содержать `UL` или `ul` [символ типа](../../programming-guide\language-features\data-types/type-characters.md) для обозначения `ULong` тип данных, как показано в следующем примере.

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a>Советы по программированию
  
-   **Отрицательные числа.** Так как `ULong` — это тип без знака, он не может представлять отрицательное число. При использовании унарного минуса (`-`) оператор на выражение, результатом вычисления которого введите `ULong`, Visual Basic преобразует выражение `Decimal` первого.  
  
-   **CLS-совместимость.** `ULong` Тип данных не является частью [спецификация CLS](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), поэтому CLS-совместимого кода нельзя использовать компонент, который его использует.  
  
-   **Вопросы взаимодействия.** При взаимодействии с компонентами, которые не написаны для платформы .NET Framework, например, автоматизация или COM-объекты, имейте в виду, что типы, такие как `ulong` может иметь другой размер (32 бита) в других средах. Если вы передаете 32-разрядного аргумента такому компоненту, объявите его как `UInteger` вместо `ULong` в управляемом коде Visual Basic.  
  
     Кроме того службы автоматизации не поддерживает 64-разрядных целых чисел в Windows 95, Windows 98, Windows ME или Windows 2000. Невозможно передать Visual Basic `ULong` аргумент в компонент автоматизации на этих платформах.  
  
-   **Расширяющие.** `ULong` Тип данных можно расширить до `Decimal`, `Single`, и `Double`. Это означает, что вы можете преобразовать `ULong` к любому из этих типов без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.  
  
-   **Символы типа.** Добавление символы типа литерала `UL` в литерал приводит к принудительному `ULong` тип данных. `ULong` не имеет тип символа идентификатора.
  
-   **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.UInt64?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также

 <xref:System.UInt64>  
 [Типы данных](../../../visual-basic/language-reference/data-types/index.md)  
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
