---
title: Сравнения значений
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
ms.openlocfilehash: f766eaaada486a0f70838bafb754d25070ff4174
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346290"
---
# <a name="value-comparisons-visual-basic"></a>Сравнение значений (Visual Basic)
Операторы сравнения можно использовать для создания выражений, которые сравнивают значения числовых переменных. Эти выражения возвращают `Boolean` значение в зависимости от того, имеет ли сравнение значение true или false. Ниже приведены примеры таких выражений.  
  
 `45 > 26`  
  
 `26 > 45`  
  
 Первое выражение принимает значение `True`, поскольку 45 больше 26. Второй пример принимает значение `False`, так как 26 не превышает 45.  
  
 Таким образом можно также сравнить числовые выражения. Сравниваемые выражения могут быть сложными выражениями, как показано в следующем примере.  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 Предыдущее сложное выражение включает литералы, переменные и вызовы функций. Выражения на обеих сторонах оператора сравнения оцениваются, а результирующие значения сравниваются с помощью оператора сравнения `>=`. Если значение выражения в левой части больше или равно значению выражения справа, результатом вычисления всего выражения будет `True`. в противном случае он принимает значение `False`.  
  
 Выражения, которые сравнивают значения, чаще всего используются в `If...Then`ных конструкциях, как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#84)]  
  
 Знак `=` является оператором сравнения, а также оператором присваивания. При использовании в качестве оператора сравнения он вычисляет, равно ли значение слева значению справа, как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#85)]  
  
 Можно также использовать выражение сравнения в любом месте, где требуется `Boolean` значение, например в `If`, `While`, `Loop`или `ElseIf`, а также при назначении или передаче значения в переменную `Boolean`. В следующем примере значение, возвращаемое выражением сравнения, присваивается переменной `Boolean`.  
  
 [!code-vb[VbVbalrOperators#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#86)]  
  
## <a name="see-also"></a>См. также

- [Логические выражения](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [Операторы и выражения](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Операторы сравнения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Практическое руководство. Вычисление числовых значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)
- [Порядок применения операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)
