---
title: Сравнение значений (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], comparing values
- Visual Basic code, operators
- Visual Basic code, expressions
- comparison operators [Visual Basic], comparing expressions
- numeric expressions
- operators [Visual Basic], comparison
- expressions [Visual Basic], comparing
ms.assetid: 60da0c76-9458-4afc-97e9-44a7939c064c
ms.openlocfilehash: 270b226d0a1aa7d08721e6f9ed36d68492685af3
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818609"
---
# <a name="value-comparisons-visual-basic"></a>Сравнение значений (Visual Basic)
Операторы сравнения можно использовать для создания выражений, которые сравнивают значения числовых переменных. Эти выражения возвращают `Boolean` значение, основанное на ли сравнение значение true или false. Ниже приведены примеры таких выражений.  
  
 `45 > 26`  
  
 `26 > 45`  
  
 Первое выражение, результатом которого является `True`, поскольку 45 больше 26. Во втором примере, результатом которого является `False`, поскольку 26 не превышает 45.  
  
 Вы также можете сравнить числовых выражений таким образом. Выражения могут быть сложными, как показано в следующем примере.  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 Сложное выражение содержит литералы, переменные и вызовы функций. Выражения с обеих сторон оператора сравнения вычисляются и результирующие значения сравниваются с помощью `>=` оператор сравнения. Если значение выражения в левой части больше или равно значению выражения в правой части, то весь выражение `True`; в противном случае он возвращает `False`.  
  
 Чаще всего используются в выражениях, которые сравнивают значения `If...Then` конструкции, как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#84)]  
  
 `=` Входа является оператором сравнения, а также оператор присваивания. При использовании в качестве оператора сравнения, она проверяет, является ли значение слева равно значению справа, как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#85)]  
  
 Можно также использовать выражения сравнения в любом `Boolean` значение, например, как показано на `If`, `While`, `Loop`, или `ElseIf` инструкции, или при назначении или передаче значения `Boolean` переменной. В следующем примере присваивается значение, возвращаемое выражением сравнения `Boolean` переменной.  
  
 [!code-vb[VbVbalrOperators#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#86)]  
  
## <a name="see-also"></a>См. также

- [Логические выражения](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [Операторы и выражения](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Операторы сравнения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Практическое руководство. Вычисление числовых значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)
- [Порядок применения операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)
