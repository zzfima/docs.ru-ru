---
title: "Тип данных Single (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Single
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c91dbdf73ed1e26393518001ec8651557e5b780f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="single-data-type-visual-basic"></a>Тип данных Single (Visual Basic)
Содержит знаком IEEE 32 бита (4-байтовое) число одинарной точности числа с плавающей запятой в диапазоне от - 3, 4028235E + 38 до - 1, 401298E-45 для отрицательных значений и от 1, 401298E-45 до 3, 4028235E + 38 для положительных значений. Числа одинарной точности сохраняют приближенные значения вещественным числом.  
  
## <a name="remarks"></a>Примечания  
 Используйте `Single` тип данных для хранения значений с плавающей запятой, которые не требуют полного размера `Double`. В некоторых случаях среда можно упаковать вашей `Single` переменные тесном контакте и снизить потребление памяти.  
  
 Значение по умолчанию для типа `Single` — 0.  
  
## <a name="programming-tips"></a>Советы по программированию  
  
-   **Точность.** При работе с числами с плавающей запятой, имейте в виду, что они не всегда имеют точное представление в памяти. Это может привести к непредвиденным результатам определенных операций, таких как значение сравнения и `Mod` оператор. Дополнительные сведения см. в разделе [Устранение неполадок типы данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
-   **Расширяющие.** `Single` Тип данных может быть расширен до `Double`. Это означает, что можно преобразовать `Single` для `Double` без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.  
  
-   **Замыкающие нули.** Типы данных с плавающей запятой не имеют внутреннего представления символов конечных нулей. Например они не различают 4,2000 и 4,2. Следовательно символы 0 не появляются при отображении или печати значений с плавающей запятой.  
  
-   **Символы типов.** При добавлении к литералу символа типа литерала `F` производится принудительное приведение литерала к типу данных `Single`. При добавлении символа идентификатора типа `!` к любому идентификатору производится принудительное приведение этого идентификатора к типу `Single`.  
  
-   **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.Single?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Single?displayProperty=nameWithType>  
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Тип данных Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)  
 [Тип данных Double](../../../visual-basic/language-reference/data-types/double-data-type.md)  
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [Устранение неполадок, связанных с типами данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
