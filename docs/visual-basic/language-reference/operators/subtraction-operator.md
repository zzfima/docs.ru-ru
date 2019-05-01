---
title: '- Operator (Visual Basic)'
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
ms.openlocfilehash: 1a5c47a2f1bc8a8b9e1b0263b90006a0e58e17bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013482"
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
 Обязательный. Произвольное числовое выражение.  
  
 `expression2`  
 Требуется, если `–` оператор вычисляет отрицательное значение. Произвольное числовое выражение.  
  
## <a name="result"></a>Результат  
 Результат отличается от `expression1` и `expression2`, или отрицательное значение `expression1`.  
  
 Тип данных результата является числовым типом, соответствующим типам данных `expression1` и `expression2`. См. в таблицах «Целочисленных арифметических операций» [типы данных из результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="supported-types"></a>Поддерживаемые типы  
 все числовые типы. Сюда входят типы без знака и с плавающей запятой и `Decimal`.  
  
## <a name="remarks"></a>Примечания  
 При первом использовании показано в приведенном примере `–` оператор *двоичных* оператор арифметического вычитания для разницы между двумя числовыми выражениями.  
  
 При использовании второго в синтаксис, показанный ранее `–` оператор *унарный* оператор отрицания отрицательного значения выражения. В этом смысле отрицание представляет собой замену знака `expression1` , чтобы результат будет положительным Если `expression1` является отрицательным.  
  
 Если любое из выражений, результатом которого является [ничего не](../../../visual-basic/language-reference/nothing.md), `–` оператор воспринимает его как ноль.  
  
> [!NOTE]
>  `–` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что переопределенное его. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `–` оператор вычисляет и возвращает разность двух чисел, а затем меняет знак числа.  
  
 [!code-vb[VbVbalrOperators#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#10)]  
  
 После выполнения этих инструкций `binaryResult` содержит значение 124,45 и `unaryResult` содержит значение – 334,90.  
  
## <a name="see-also"></a>См. также

- [-= Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
