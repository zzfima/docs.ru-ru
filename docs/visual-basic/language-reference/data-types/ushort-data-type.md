---
title: Тип данных UShort (Visual Basic)
ms.date: 01/31/2018
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
ms.openlocfilehash: 038aad2c41f655d0699dab33df276132a70e3ede
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2018
ms.locfileid: "46492724"
---
# <a name="ushort-data-type-visual-basic"></a>Тип данных UShort (Visual Basic)

Содержит 16-разрядное (2-байтовое) целых чисел без знака в диапазоне от 0 до 65 535.  
  
## <a name="remarks"></a>Примечания

 Используйте `UShort` тип данных для хранения двоичных данных, слишком велик для `Byte`.  
  
 Значение по умолчанию для типа `UShort` — 0.  

# <a name="literal-assignments"></a>Назначения литералов

Можно объявить и инициализировать `UShort` переменной, назначив ей десятичный литерал, шестнадцатеричный восьмеричный литерал, или (начиная с Visual Basic 2017) двоичный литерал. Если целочисленный литерал выходит за пределы диапазона `UShort` (то есть, если он меньше <xref:System.UInt16.MinValue?displayProperty=nameWithType> или больше <xref:System.UInt16.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.

В следующем примере целые числа, равные 65 034 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются `UShort` значения.
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> Используйте префикс `&h` или `&H` для обозначения шестнадцатеричного литерала, префикс `&b` или `&B` для обозначения двоичного литерала, а также префикс `&o` или `&O` для обозначения восьмеричный литерал. У десятичных литералов префиксов нет.

Начиная с Visual Basic 2017, можно также использовать символ подчеркивания, `_`, в качестве разделителя разрядов для повышения удобства чтения, как в примере ниже показан.

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

Начиная с Visual Basic 15.5, можно также использовать символ подчеркивания (`_`) в качестве начального разделителя между префиксом и двоичное, шестнадцатеричное или восьмеричное цифры. Пример:

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Числовые литералы могут содержать `US` или `us` [символ типа](../../programming-guide\language-features\data-types/type-characters.md) для обозначения `UShort` тип данных, как показано в следующем примере.

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a>Советы по программированию
  
-   **Отрицательные числа.** Так как `UShort` — это тип без знака, он не может представлять отрицательное число. При использовании унарного минуса (`-`) оператор на выражение, результатом вычисления которого введите `UShort`, Visual Basic преобразует выражение `Integer` первого.  
  
-   **CLS-совместимость.** `UShort` Тип данных не является частью [спецификация CLS](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), поэтому CLS-совместимого кода нельзя использовать компонент, который его использует.
  
-   **Расширяющие.** `UShort` Тип данных можно расширить до `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, и `Double`. Это означает, что вы можете преобразовать `UShort` к любому из этих типов без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.  
  
-   **Символы типа.** Добавление символы типа литерала `US` в литерал приводит к принудительному `UShort` тип данных. `UShort` не имеет тип символа идентификатора.  
  
-   **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.UInt16?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.UInt16>  
 [Типы данных](../../../visual-basic/language-reference/data-types/index.md)  
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
