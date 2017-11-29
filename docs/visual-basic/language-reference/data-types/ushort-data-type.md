---
title: "Тип данных UShort (Visual Basic)"
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.ushort
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
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 513e8ce4694788d33c5aa14e34b95e88b6d37ff1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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

Можно также включать числовые литералы `US` или `us` [символ типа](../../programming-guide\language-features\data-types/type-characters.md) для обозначения `UShort` тип данных, как показано в следующем примере.

```vb
Dim number = &H035826us
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
