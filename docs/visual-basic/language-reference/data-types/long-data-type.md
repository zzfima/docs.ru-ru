---
title: "Тип данных Long (Visual Basic)"
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Long
helpviewer_keywords:
- identifier type characters [Visual Basic], &
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- '& identifier type character'
- integer numbers
- literal type characters [Visual Basic], L
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- L literal type character [Visual Basic]
- integers [Visual Basic], types
- Long keyword [Visual Basic]
- data types [Visual Basic], integral
- data types [Visual Basic], assigning
- Long data type
ms.assetid: b4770c34-1804-4f8c-b512-c10b0893e516
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1e21ed43ddc6efb018df0581faed1ebf270ab3ca
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="long-data-type-visual-basic"></a>Тип данных Long (Visual Basic)

Содержит 64-разрядные целые числа (8-байтные) в диапазоне от -9223372036854775808 до 9223372036854775807 знаком (9.2... E + 18).  
  
## <a name="remarks"></a>Примечания

 Используйте `Long` тип данных для хранения целых чисел, которые помещаются `Integer` тип данных.  
  
 Значение по умолчанию для типа `Long` — 0.

## <a name="literal-assignments"></a>Литерал назначения 

Можно объявить и инициализировать `Long` переменной, назначив его десятичное литералом, Шестнадцатеричный литерал восьмеричного литерала, или (начиная с Visual Basic 2017 г) двоичный литерал. Если целочисленный литерал выходит за пределы диапазона `Long` (то есть, если он меньше <xref:System.Int64.MinValue?displayProperty=nameWithType> или больше <xref:System.Int64.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.

В следующем примере целые числа, равные 4 294 967 296 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `Long`.
  
[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]  

> [!NOTE]
> Используйте префикс `&h` или `&H` для обозначения Шестнадцатеричный литерал префиксом `&b` или `&B` для обозначения двоичный литерал и префикс `&o` или `&O` для обозначения восьмеричного литерала. У десятичных литералов префиксов нет.

Начиная с Visual Basic 2017 г., можно также использовать знак подчеркивания `_`, как разделитель для повышения удобства чтения, как в следующем примере показано.

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

Можно также включать числовые литералы `L` [символ типа](../../programming-guide\language-features\data-types/type-characters.md) для обозначения `Long` тип данных, как показано в следующем примере.

```vb
Dim number = &H0FAC0326L
```

## <a name="programming-tips"></a>Советы по программированию

-   **Вопросы взаимодействия.** При взаимодействии с компонентами, которые не написаны для платформы .NET Framework, например, автоматизация или COM-объекты, следует помнить, что `Long` имеет другой размер (32 бита) в других средах. Если вы передаете 32-разрядного аргумента такому компоненту, объявите его как `Integer` вместо `Long` в новом коде Visual Basic.  
  
-   **Расширяющие.** `Long` Тип данных может быть расширен до `Decimal`, `Single`, или `Double`. Это означает, что тип `Long` можно преобразовать в любой из этих типов без возникновения ошибки <xref:System.OverflowException?displayProperty=nameWithType>.  
  
-   **Символы типов.** При добавлении к литералу символа типа литерала `L` производится принудительное приведение литерала к типу данных `Long`. При добавлении символа идентификатора типа `&` к любому идентификатору производится принудительное приведение этого идентификатора к типу `Long`.  
  
-   **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.Int64?displayProperty=nameWithType>.  

## <a name="see-also"></a>См. также

<xref:System.Int64>[Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
[Целочисленный тип данных](../../../visual-basic/language-reference/data-types/integer-data-type.md)   
[Short-тип данных](../../../visual-basic/language-reference/data-types/short-data-type.md)   
[Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
[Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
[Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
