---
title: "Тип данных UShort (Visual Basic)"
ms.date: 01/31/2018
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ushort
helpviewer_keywords:
- numbers [Visual Basic], whole
- literal type characters [Visual Basic], US
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- UShort data type
- US literal type characters [Visual Basic]
ms.assetid: 138db892-665d-4ba8-9cae-d8d91c4a8f39
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 958c7c74822d3b5cb311d22977b1b1f8bda04cd7
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2018
---
# <a name="ushort-data-type-visual-basic"></a>Тип данных UShort (Visual Basic)

Содержит 16-разрядное (2-байтовые) целых чисел без знака в диапазоне от 0 до 65 535.  
  
## <a name="remarks"></a>Примечания

 Используйте `UShort` тип данных для хранения двоичных данных, слишком велик для `Byte`.  
  
 Значение по умолчанию для типа `UShort` — 0.  

# <a name="literal-assignments"></a>Литерал назначения

Можно объявить и инициализировать `UShort` переменной, назначив его десятичное литералом, Шестнадцатеричный литерал восьмеричного литерала, или (начиная с Visual Basic 2017 г) двоичный литерал. Если целочисленный литерал выходит за пределы диапазона `UShort` (то есть, если он меньше <xref:System.UInt16.MinValue?displayProperty=nameWithType> или больше <xref:System.UInt16.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.

В следующем примере целых чисел, равные 65,034, представленное в десятичном, шестнадцатеричном виде, и двоичные литералы назначены `UShort` значения.
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> Используйте префикс `&h` или `&H` для обозначения Шестнадцатеричный литерал префиксом `&b` или `&B` для обозначения двоичный литерал и префикс `&o` или `&O` для обозначения восьмеричного литерала. У десятичных литералов префиксов нет.

Начиная с Visual Basic 2017 г., можно также использовать знак подчеркивания `_`, как разделитель для повышения удобства чтения, как в следующем примере показано.

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

Начиная с Visual Basic 15,5, можно также использовать символ подчеркивания (`_`) в качестве начальных разделителя между префиксом и двоичное, шестнадцатеричное или восьмеричное цифры. Пример:

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Можно также включать числовые литералы `US` или `us` [символ типа](../../programming-guide\language-features\data-types/type-characters.md) для обозначения `UShort` тип данных, как показано в следующем примере.

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a>Советы по программированию
  
-   **Отрицательные числа.** Поскольку `UShort` является тип без знака, он не может представлять отрицательное число. Если вы используете унарного минуса (`-`) оператор в выражении, вычисляется как тип `UShort`, Visual Basic преобразует выражение, `Integer` первой.  
  
-   **CLS-совместимости.** `UShort` Тип данных не является частью [спецификации CLS](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), поэтому CLS-совместимого кода нельзя использовать компонент, который его использует.
  
-   **Расширяющие.** `UShort` Тип данных может быть расширен до `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, и `Double`. Это означает, что можно преобразовать `UShort` на любой из этих типов без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.  
  
-   **Символы типов.** Символы типа литерала добавления `US` с литералом приводит к принудительному `UShort` тип данных. `UShort`не имеет типа символа идентификатора.  
  
-   **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.UInt16?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.UInt16>  
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
