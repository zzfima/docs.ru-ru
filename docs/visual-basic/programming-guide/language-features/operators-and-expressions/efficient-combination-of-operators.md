---
title: Эффективное сочетание операторов (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- expressions [Visual Basic], parentheses
- operators [Visual Basic], associativity
- expressions [Visual Basic], operators
- operators [Visual Basic], precedence
- Visual Basic code, operators
- Visual Basic code, expressions
- operators [Visual Basic], complex expressions
- expressions [Visual Basic], complex
- parentheses [Visual Basic], complex expressions
- numeric expressions
ms.assetid: bd22340e-b5be-458b-8772-3916c02309a4
ms.openlocfilehash: 8f5dd6c56b3e4576b9d798e0e5e10b2996f558dc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864658"
---
# <a name="efficient-combination-of-operators-visual-basic"></a>Эффективное сочетание операторов (Visual Basic)
Сложные выражения могут содержать большое количество различных операторов. Это показано в следующем примере.  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 Создание сложных выражений, подобное показанному в предыдущем примере требует глубокого понимания правил приоритета операторов. Дополнительные сведения см. в разделе [порядок применения операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## <a name="parenthetical-expressions"></a>Выражения в скобках  
 Часто возникает необходимость выполнения операций в порядке, отличающемся от определенного приоритетом операторов. Рассмотрим следующий пример.  
  
 `x = z * y + 4`  
  
 Предыдущий пример умножает `z` по `y`, затем результат прибавляется к `4`. Но если вы хотите добавить `y` и `4` перед умножением на `z`, обычный порядок применения операторов можно переопределить с помощью скобок. Выражение заключено в круглые скобки, принудительно это выражение, вычисляемое во-первых, вне зависимости от приоритета операторов. Чтобы принудительно в предыдущем примере сначала выполнить сложение, нужно переписать его как в следующем примере.  
  
 `x = z * (y + 4)`  
  
 В предыдущем примере добавляется `y` и `4`, затем сумма умножается на `z`.  
  
### <a name="nested-parenthetical-expressions"></a>Вложенные выражения в скобках  
 Можно осуществлять вложение выражений в нескольких уровней круглых скобок для дальнейшего переопределения приоритетов. Самую глубокую вложенную в скобках вычисляются во-первых, следуют следующей самую глубокую вложенную, и т. д бы глубоко вложенных и наконец выражения за пределами скобок. Это показано в следующем примере.  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 В приведенном выше примере `z + 2` сначала вычисляется, то другие выражения в скобках. Возведение в степень, который обычно имеет более высокий приоритет, чем сложение или умножение, вычисляется последним в этом примере, поскольку другие выражения заключены в круглые скобки.  
  
## <a name="see-also"></a>См. также

- [Арифметические операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Операторы сравнения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Логические и побитовые операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [Логические (побитовые) операторы (Visual Basic)](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Логические выражения](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [Сравнения значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Практическое руководство. Вычисление числовых значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)
- [Порядок применения операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)
