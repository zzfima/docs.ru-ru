---
title: "Тип данных ULong (Visual Basic)"
ms.date: 01/31/2018
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
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
ms.openlocfilehash: 606e0ef87b209bb2e75e28223f27d081713c1b7e
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2018
---
# <a name="ulong-data-type-visual-basic"></a>Тип данных ULong (Visual Basic)

Содержит 64-разрядные (8-байтные) целых чисел без знака в диапазоне от 0 до 18446744073709551615 (1,84 раза больше чем 10 ^ 19).  
  
## <a name="remarks"></a>Примечания

Используйте `ULong` тип данных для хранения двоичных данных, слишком велик для `UInteger`, или наибольшее возможное без знака целочисленных значений.  
  
Значение по умолчанию для типа `ULong` — 0.

## <a name="literal-assignments"></a>Литерал назначения

Можно объявить и инициализировать `ULong` переменной, назначив его десятичное литералом, Шестнадцатеричный литерал восьмеричного литерала, или (начиная с Visual Basic 2017 г) двоичный литерал. Если целочисленный литерал выходит за пределы диапазона `ULong` (то есть, если он меньше <xref:System.UInt64.MinValue?displayProperty=nameWithType> или больше <xref:System.UInt64.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.

В следующем примере целые числа, равные 7 934 076 125 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `ULong`.
  
[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE] 
> Используйте префикс `&h` или `&H` для обозначения Шестнадцатеричный литерал префиксом `&b` или `&B` для обозначения двоичный литерал и префикс `&o` или `&O` для обозначения восьмеричного литерала. У десятичных литералов префиксов нет.

Начиная с Visual Basic 2017 г., можно также использовать знак подчеркивания `_`, как разделитель для повышения удобства чтения, как в следующем примере показано.

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

Начиная с Visual Basic 15,5, можно также использовать символ подчеркивания (`_`) в качестве начальных разделителя между префиксом и двоичное, шестнадцатеричное или восьмеричное цифры. Пример:

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Можно также включать числовые литералы `UL` или `ul` [символ типа](../../programming-guide\language-features\data-types/type-characters.md) для обозначения `ULong` тип данных, как показано в следующем примере.

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a>Советы по программированию
  
-   **Отрицательные числа.** Поскольку `ULong` является тип без знака, он не может представлять отрицательное число. Если вы используете унарного минуса (`-`) оператор в выражении, вычисляется как тип `ULong`, Visual Basic преобразует выражение, `Decimal` первой.  
  
-   **CLS-совместимости.** `ULong` Тип данных не является частью [спецификации CLS](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), поэтому CLS-совместимого кода нельзя использовать компонент, который его использует.  
  
-   **Вопросы взаимодействия.** При взаимодействии с компонентами, которые не написаны для платформы .NET Framework, например, автоматизация или COM-объекты, имейте в виду, что типы, такие как `ulong` может иметь другой размер (32 бита) в других средах. Если вы передаете 32-разрядного аргумента такому компоненту, объявите его как `UInteger` вместо `ULong` в управляемом коде Visual Basic.  
  
     Кроме того Automation не поддерживает 64-битовых целых чисел в Windows 95, Windows 98, Windows ME или Windows 2000. Невозможно передать Visual Basic `ULong` аргумент компоненту автоматизации на этих платформах.  
  
-   **Расширяющие.** `ULong` Тип данных может быть расширен до `Decimal`, `Single`, и `Double`. Это означает, что можно преобразовать `ULong` на любой из этих типов без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.  
  
-   **Символы типов.** Символы типа литерала добавления `UL` с литералом приводит к принудительному `ULong` тип данных. `ULong`не имеет типа символа идентификатора.
  
-   **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.UInt64?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также

 <xref:System.UInt64>  
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
