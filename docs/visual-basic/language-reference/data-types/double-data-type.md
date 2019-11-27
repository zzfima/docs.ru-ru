---
title: Тип данных Double
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
ms.openlocfilehash: 347b5c7b7af4c4aafec0f91aca46a8cf640236b9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344014"
---
# <a name="double-data-type-visual-basic"></a>Тип данных Double (Visual Basic)

Содержит подписанные 64-разрядные (8-байтные) числа с плавающей запятой двойной точности, которые находятся в диапазоне от-1.79769313486231570 E + 308 до-4.94065645841246544 E-324 для отрицательных значений и от 4.94065645841246544 E-324 до 1.79769313486231570 E + 308 для положительные значения. Числа двойной точности хранят приближение вещественного числа.

## <a name="remarks"></a>Заметки

Тип данных `Double` предоставляет самые большие и наименьшие возможные величины числа.

Значение по умолчанию для типа `Double` — 0.

## <a name="programming-tips"></a>Советы по программированию

- **Обеспечивают.** При работе с числами с плавающей запятой Помните, что они не всегда имеют точное представление в памяти. Это может привести к непредвиденным результатам некоторых операций, таких как сравнение значений и оператор `Mod`. Дополнительные сведения см. в разделе [Устранение неполадок типов данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).

- **Нули в конце.** Типы данных с плавающей запятой не имеют внутреннего представления конечных нулей. Например, они не различаются между 4,2000 и 4,2. Следовательно, конечные нули не отображаются при отображении или печати значений с плавающей запятой.

- **Символы типа.** При добавлении к литералу символа типа литерала `R` производится принудительное приведение литерала к типу данных `Double`. Например, если за целочисленным значением следует `R`, значение изменяется на `Double`.

  ```vb
  ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:
  Dim dub As Double = 4.0R
  ```

  При добавлении символа идентификатора типа `#` к любому идентификатору производится принудительное приведение этого идентификатора к типу `Double`. В следующем примере переменная `num` типизирована как `Double`:

  ```vb
  Dim num# = 3
  ```

- **Тип платформы.** В .NET Framework данный тип соответствует структуре <xref:System.Double?displayProperty=nameWithType>.

## <a name="see-also"></a>См. также

- <xref:System.Double?displayProperty=nameWithType>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Тип данных Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)
- [Тип данных Single](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Устранение неполадок, связанных с типами данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Знаки типов](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
