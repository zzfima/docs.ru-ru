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
ms.openlocfilehash: 6e1eda09784814d139ef94b6720b538aef30e5e7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="value-comparisons-visual-basic"></a>Сравнение значений (Visual Basic)
Операторы сравнения можно использовать для создания выражений, которые сравнивают значения числовых переменных. Эти выражения возвращают `Boolean` значение на основании результат сравнения-ИСТИНА или ЛОЖЬ. Ниже приводятся примеры таких выражений.  
  
 `45 > 26`  
  
 `26 > 45`  
  
 Первое выражение, результатом которого является `True`, поскольку 45 больше 26. Во втором примере вычисляется `False`, поскольку 26 не больше 45.  
  
 Вы также можете сравнить числовых выражений таким образом. Выражения могут быть сложными, как в следующем примере.  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 Сложное выражение содержит литералы, переменные и вызовы функций. Вычисляются выражения с обеих сторон оператора сравнения, а полученные значения сравниваются с помощью `>=` оператор сравнения. Если значение выражения в левой части больше или равно значению выражения справа, все выражение принимает значение `True`; в противном случае он возвращает `False`.  
  
 Выражения, сравнивающие значения чаще всего используются в `If...Then` конструкциях, как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#84](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_1.vb)]  
  
 `=` Входа является оператором сравнения, а также оператор присваивания. При использовании в качестве оператора сравнения, он определяет, является ли значение слева равно значению справа, как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#85](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_2.vb)]  
  
 Можно также использовать выражения сравнения в любом `Boolean` значение, например, как и в `If`, `While`, `Loop`, или `ElseIf` инструкции, или при назначении или передачи значения `Boolean` переменной. В следующем примере присваивается значение, возвращаемое выражением сравнения `Boolean` переменной.  
  
 [!code-vb[VbVbalrOperators#86](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_3.vb)]  
  
## <a name="see-also"></a>См. также  
 [Логические выражения](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [Операторы и выражения](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Операторы сравнения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Практическое руководство. Вычисление числовых значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)  
 [Порядок применения операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)
