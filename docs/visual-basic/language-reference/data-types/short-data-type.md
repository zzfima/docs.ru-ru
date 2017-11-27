---
title: "Тип данных Short (Visual Basic)"
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
author: rpetrusha
ms.author: ronpet
f1_keywords: vb.Short
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
ms.openlocfilehash: fef948debed69cf9fb7b0e6bb65eb0ddbe497a92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="short-data-type-visual-basic"></a>Тип данных Short (Visual Basic)
Содержит знаком 16-разрядное (2-байтовые) целые числа в диапазоне от-32 768 до 32 767.  
  
## <a name="remarks"></a>Примечания  
 Используйте `Short` тип данных для хранения целых значений, которые не требуют полного размера `Integer`. В некоторых случаях можно упаковать общеязыковая среда выполнения вашей `Short` переменные тесном контакте и снизить потребление памяти.  
  
 Значение по умолчанию для типа `Short` — 0.  
  
## <a name="literal-assignments"></a>Литерал назначения

Можно объявить и инициализировать `Short` переменной, назначив его десятичное литералом, Шестнадцатеричный литерал восьмеричного литерала, или (начиная с Visual Basic 2017 г) двоичный литерал. Если целочисленный литерал выходит за пределы диапазона `Short` (то есть, если он меньше <xref:System.Int16.MinValue?displayProperty=nameWithType> или больше <xref:System.Int16.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.

В следующем примере целых чисел, равные 1,034, представленное в десятичном, шестнадцатеричном виде, и двоичные литералы производится неявное преобразование из [целое](integer-data-type.md) для `Short` значения.

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> Используйте префикс `&h` или `&H` для обозначения Шестнадцатеричный литерал префиксом `&b` или `&B` для обозначения двоичный литерал и префикс `&o` или `&O` для обозначения восьмеричного литерала. У десятичных литералов префиксов нет.

Начиная с Visual Basic 2017 г., можно также использовать знак подчеркивания `_`, как разделитель для повышения удобства чтения, как в следующем примере показано.

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

Можно также включать числовые литералы `S` [символ типа](../../programming-guide\language-features\data-types/type-characters.md) для обозначения `Short` тип данных, как показано в следующем примере.

```vb
Dim number = &H0326S
```

## <a name="programming-tips"></a>Советы по программированию

-   **Расширяющие.** `Short` Тип данных может быть расширен до `Integer`, `Long`, `Decimal`, `Single`, или `Double`. Это означает, что тип `Short` можно преобразовать в любой из этих типов без возникновения ошибки <xref:System.OverflowException?displayProperty=nameWithType>.  
  
-   **Символы типов.** При добавлении к литералу символа типа литерала `S` производится принудительное приведение литерала к типу данных `Short`. `Short`не имеет типа символа идентификатора.  
  
-   **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.Int16?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также

 <xref:System.Int16?displayProperty=nameWithType>  
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Тип данных Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [Тип данных Long](../../../visual-basic/language-reference/data-types/long-data-type.md)  
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
