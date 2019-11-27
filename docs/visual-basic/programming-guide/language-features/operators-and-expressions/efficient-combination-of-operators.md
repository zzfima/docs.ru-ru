---
title: Эффективное сочетание операторов
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
ms.openlocfilehash: 83ad53e4c75490a75eba0f80a6bf0f078aa4d426
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348992"
---
# <a name="efficient-combination-of-operators-visual-basic"></a>Эффективное сочетание операторов (Visual Basic)
Сложные выражения могут содержать множество различных операторов. Это показано в следующем примере.  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 Создание сложных выражений, например, в предыдущем примере, требует тщательного понимания правил приоритета операторов. Дополнительные сведения см. [в разделе приоритет операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## <a name="parenthetical-expressions"></a>Выражения в скобках  
 Часто требуется, чтобы операции продвигается в порядке, отличном от того, который определяется приоритетом операторов. Рассмотрим следующий пример.  
  
 `x = z * y + 4`  
  
 Предыдущий пример умножает `z` на `y`, а затем добавляет результат в `4`. Но если вы хотите добавить `y` и `4` до умножения результата `z`, можно переопределить приоритет обычного оператора с помощью круглых скобок. Заключив выражение в круглые скобки, вы принудительно выдаете выражение первым, независимо от приоритета операторов. Чтобы выполнить предыдущий пример для первого добавления, можно переписать его, как показано в следующем примере.  
  
 `x = z * (y + 4)`  
  
 В предыдущем примере добавляется `y` и `4`, затем сумма умножается на `z`.  
  
### <a name="nested-parenthetical-expressions"></a>Вложенные выражения в скобках  
 Можно вкладывать выражения на нескольких уровнях круглых скобок для более детального переопределения приоритета. Выражения, наиболее глубоко вложенные в круглые скобки, сначала оцениваются, за которыми следуют более глубокий уровень вложенности, и так далее, и, наконец, выражения за пределами круглых скобок. Это показано в следующем примере.  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 В предыдущем примере `z + 2` вычисляется первым, а затем другими выражениями в скобках. Возведение в степень, которое обычно имеет более высокий приоритет, чем сложение или умножение, в этом примере вычисляется последним, так как другие выражения заключаются в круглые скобки.  
  
## <a name="see-also"></a>См. также

- [Арифметические операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Операторы сравнения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Логические и побитовые операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [Логические и битовые операторы (Visual Basic)](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Логические выражения](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [Сравнения значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Практическое руководство. Вычисление числовых значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)
- [Порядок применения операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)
