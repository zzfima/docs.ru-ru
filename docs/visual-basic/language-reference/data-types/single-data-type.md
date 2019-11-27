---
title: Тип данных Single
ms.date: 07/20/2015
f1_keywords:
- vb.Single
helpviewer_keywords:
- Single data type
- F literal type character [Visual Basic]
- trailing zeros
- real numbers
- literal type characters [Visual Basic], F
- trailing 0 characters [Visual Basic]
- identifier type characters [Visual Basic], !
- single-precision numbers
- '! identifier type character'
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- floating-point numbers [Visual Basic], Single data type
- numbers [Visual Basic], real
- zeros, trailing
- numbers [Visual Basic], floating point
ms.assetid: 224a2795-4cd5-496c-8f7a-a4f05a06d45d
ms.openlocfilehash: 60a688c510f6e36dca5809566b37a388429e18c7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343920"
---
# <a name="single-data-type-visual-basic"></a>Тип данных Single (Visual Basic)

Содержит подписанные 32-разрядные (4-байтовые) числа с плавающей запятой с одиночной точностью в диапазоне от-4028235E E + 38 до-1.401298 E-45 для отрицательных значений и от 1.401298 E-45 до 4028235E E + 38 для положительных значений. Числа с одиночной точностью хранят приближение вещественного числа.  
  
## <a name="remarks"></a>Примечания  

 Используйте `Single` тип данных, чтобы содержать значения с плавающей запятой, не требующие полной ширины данных `Double`. В некоторых случаях среда CLR может объединять переменные `Single` и экономить потребление памяти.  
  
 Значение по умолчанию для типа `Single` — 0.  
  
## <a name="programming-tips"></a>Советы по программированию  
  
- **Обеспечивают.** При работе с числами с плавающей запятой следует помнить, что они не всегда имеют точное представление в памяти. Это может привести к непредвиденным результатам некоторых операций, таких как сравнение значений и оператор `Mod`. Дополнительные сведения см. в разделе [Устранение неполадок типов данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
- **Расширяющие.** Тип данных `Single` расширяется до `Double`. Это означает, что можно преобразовать `Single` в `Double` без возникновения ошибки <xref:System.OverflowException?displayProperty=nameWithType>.  
  
- **Нули в конце.** Типы данных с плавающей запятой не имеют внутреннего представления конечных знаков 0. Например, они не различаются между 4,2000 и 4,2. Следовательно, замыкающие символы (0) не отображаются при отображении или печати значений с плавающей запятой.  
  
- **Символы типа.** При добавлении к литералу символа типа литерала `F` производится принудительное приведение литерала к типу данных `Single`. При добавлении символа идентификатора типа `!` к любому идентификатору производится принудительное приведение этого идентификатора к типу `Single`.  
  
- **Тип платформы.** В .NET Framework данный тип соответствует структуре <xref:System.Single?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Single?displayProperty=nameWithType>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Тип данных Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)
- [Тип данных Double](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Устранение неполадок, связанных с типами данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
