---
title: '- Оператор (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.Negate
- vb.-
helpviewer_keywords:
- operator [Visual Basic]
- operators [Visual Basic], subtraction
- operators [Visual Basic], difference
- negation operator [Visual Basic]
- operators [Visual Basic], arithmetic
- subtraction operator [Visual Basic], syntax
- arithmetic operators [Visual Basic], subtraction
- difference operator [Visual Basic]
- math operators [Visual Basic]
- operators [Visual Basic], negation
- minus operator [Visual Basic]
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
ms.openlocfilehash: 4df8eb3844ed20fd24ca375f77cea46b9c6cee37
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604319"
---
# <a name="--operator-visual-basic"></a>Оператор - (Visual Basic)
Возвращает разность двух числовых выражений или отрицательное значение числового выражения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## <a name="parts"></a>Части  
 `expression1`  
 Обязательно. Произвольное числовое выражение.  
  
 `expression2`  
 Требуется, если `–` оператор вычисляет отрицательное значение. Произвольное числовое выражение.  
  
## <a name="result"></a>Результат  
 Результат отличается от `expression1` и `expression2`, или инвертированное значение `expression1`.  
  
 Тип данных результата является числовым типом, соответствующим для типов данных `expression1` и `expression2`. В таблице «Целочисленных арифметических операций» в [типы данных из результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="supported-types"></a>Поддерживаемые типы  
 Все числовые типы. Сюда входят типы без знака и с плавающей запятой и `Decimal`.  
  
## <a name="remarks"></a>Примечания  
 При первом использовании показано в приведенном примере `–` оператор *двоичных* оператор арифметического вычитания для нахождения разности двух числовых выражений.  
  
 При втором использовании показано в приведенном примере `–` оператор *унарный* оператор отрицания отрицательного значения выражения. В этом смысле отрицание представляет собой замену знака `expression1` , чтобы результат будет положительным Если `expression1` является отрицательным значением.  
  
 Если какое-нибудь выражение, результатом которого является [ничего](../../../visual-basic/language-reference/nothing.md), `–` оператор воспринимает его как ноль.  
  
> [!NOTE]
>  `–` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что переопределенное его. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `–` оператор вычисляет и возвращает разность двух чисел, а затем меняет знак числа.  
  
 [!code-vb[VbVbalrOperators#10](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/subtraction-operator_1.vb)]  
  
 После выполнения этих инструкций `binaryResult` содержит значение 124,45 и `unaryResult` содержит значение – 334,90.  
  
## <a name="see-also"></a>См. также  
 [-= Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md) [арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
