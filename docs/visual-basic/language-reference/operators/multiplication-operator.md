---
title: '* Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.*
helpviewer_keywords:
- arithmetic operators [Visual Basic], multiplication
- operators [Visual Basic], multiplication
- '* operator [Visual Basic]'
- multiplication operator [Visual Basic], syntax
- math operators [Visual Basic]
ms.assetid: 2b210382-99da-4195-89ba-b1d06f5e89ad
ms.openlocfilehash: 09b95585325b05c0b7925c4c1c9e123f45791e10
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58828957"
---
# <a name="-operator-visual-basic"></a>Оператор * (Visual Basic)
Выполняет умножение двух чисел.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
number1 * number2  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`number1`|Обязательный. Произвольное числовое выражение.|  
|`number2`|Обязательный. Произвольное числовое выражение.|  
  
## <a name="result"></a>Результат  
 Результатом является произведение `number1` и `number2`.  
  
## <a name="supported-types"></a>Поддерживаемые типы  
 Все числовые типы, включая типы без знака и с плавающей запятой и `Decimal`.  
  
## <a name="remarks"></a>Примечания  
 Тип данных результата зависит от типов операндов. Следующая таблица показывает, как определяется тип данных результата.  
  
|Типы данных операндов|Тип данных результата|  
|---|---|  
|Оба выражения имеют целочисленных типов данных ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [байтов](../../../visual-basic/language-reference/data-types/byte-data-type.md), [короткие](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [целое число](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))|Числовой тип данных для типов данных `number1` и `number2`. См. в таблицах «Целочисленных арифметических операций» [типы данных из результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).|  
|Оба выражения имеют [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|`Decimal`|  
|Оба выражения имеют [единый](../../../visual-basic/language-reference/data-types/single-data-type.md)|`Single`|  
|Любое из выражений имеет тип данных с плавающей запятой (`Single` или [двойные](../../../visual-basic/language-reference/data-types/double-data-type.md)), но не оба `Single` (Примечание `Decimal` не является типом данных с плавающей запятой)|`Double`|  
  
 Если выражение, результатом которого является [ничего не](../../../visual-basic/language-reference/nothing.md), он интерпретируется как ноль.  
  
## <a name="overloading"></a>Перегрузка  
 `*` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется `*` оператор для умножения двух чисел. Результатом является произведение двух операндов.  
  
 [!code-vb[VbVbalrOperators#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#4)]  
  
## <a name="see-also"></a>См. также

- [Оператор *=](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
