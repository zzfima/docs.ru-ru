---
title: Тип данных Double (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Double
helpviewer_keywords:
- 'identifier type characters [Visual Basic], #'
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- 0 characters [Visual Basic], trailing
- literal type characters [Visual Basic], R
- data types [Visual Basic], assigning
- Double data type [Visual Basic]
- '# identifier type character'
- double-precision numbers
- floating-point numbers [Visual Basic], Double data type
- R literal type character [Visual Basic]
- zeros, trailing
- Double data type
ms.assetid: 0c5670f7-fcb1-453a-bef1-374730cd38fd
ms.openlocfilehash: 5d2d84f298b9cf6138e84ef287f6ea9212da2960
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44180232"
---
# <a name="double-data-type-visual-basic"></a>Тип данных Double (Visual Basic)
Содержит знаком IEEE 64-разрядные (8-байтные) числа двойной точности с плавающей запятой числа, в диапазоне от - 1, 79769313486231570E + 308 до - 4, 94065645841246544E-324 для отрицательных значений и от 4.94065645841246544E-324 до 1, 79769313486231570E + 308 положительные значения. Числа двойной точности хранят приближенное значение вещественного числа.  
  
## <a name="remarks"></a>Примечания  
 `Double` Тип данных обеспечивает наибольшую и наименьшую возможные значения для нескольких.  
  
 Значение по умолчанию для типа `Double` — 0.  
  
## <a name="programming-tips"></a>Советы по программированию  
  
-   **Точность.** При работе с числами с плавающей запятой, помните, что они не всегда имеют точное представление в памяти. Это может привести к непредвиденным результатам определенных операций, таких как сравнения значений и `Mod` оператор. Дополнительные сведения см. в разделе [Устранение неполадок типы данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
-   **Замыкающие нули.** Типы данных с плавающей запятой не имеют внутреннего представления конечные нули. Например они не различают 4,2000 и 4.2. Следовательно конечные нули не отображаются при отображении или печати значений с плавающей запятой.  
  
-   **Символы типа.** При добавлении к литералу символа типа литерала `R` производится принудительное приведение литерала к типу данных `Double`. Например, если целочисленное значение сопровождается `R`, значение будет изменено на `Double`.  
  
    ```  
    ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:  
    Dim dub As Double = 4.0R  
    ```  
  
     При добавлении символа идентификатора типа `#` к любому идентификатору производится принудительное приведение этого идентификатора к типу `Double`. В следующем примере переменная `num` типизируется как `Double`:  
  
    ```  
    Dim num# = 3  
    ```  
  
-   **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.Double?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Double?displayProperty=nameWithType>  
 [Типы данных](../../../visual-basic/language-reference/data-types/index.md)  
 [Тип данных Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)  
 [Тип данных Single](../../../visual-basic/language-reference/data-types/single-data-type.md)  
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [Устранение неполадок, связанных с типами данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Знаки типов](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
