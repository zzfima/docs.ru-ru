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
ms.openlocfilehash: 8ced464cb0cc8e1bec3c3449dccb827575599905
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="efficient-combination-of-operators-visual-basic"></a>Эффективное сочетание операторов (Visual Basic)
Сложные выражения могут содержать большое количество различных операторов. Это показано в следующем примере.  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 Создание сложных выражений, таких как в предыдущем примере требуется глубокого понимания правил приоритета операторов. Дополнительные сведения см. в разделе [операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## <a name="parenthetical-expressions"></a>Выражения в скобках  
 Часто возникает необходимость выполнения операций в порядке, отличном от, определяемый приоритетом операторов. Рассмотрим следующий пример.  
  
 `x = z * y + 4`  
  
 Предыдущий пример умножает `z` по `y`, затем результат добавляется `4`. Однако если вы хотите добавить `y` и `4` перед умножением на `z`, можно переопределить очередность выполнения с помощью скобок. Выражение заключено в круглые скобки, принудительно выражения быть вычисленной первой, независимо от приоритета операторов. Чтобы принудительно в предыдущем примере сначала выполнить сложение, нужно переписать его как в следующем примере.  
  
 `x = z * (y + 4)`  
  
 В предыдущем примере добавляется `y` и `4`, затем сумма умножается на `z`.  
  
### <a name="nested-parenthetical-expressions"></a>Вложенные выражения в скобках  
 Можно вкладывать выражения в скобки для дальнейшего переопределения приоритетов разных уровней. Самый глубокий уровень вложенности в скобках вычисляются во-первых, за ним самый глубокий уровень вложенности, и т. д бы большим уровнем вложенности, и наконец выражения за пределами скобок. Это показано в следующем примере.  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 В приведенном выше примере `z + 2` является оценивается первым, то другие выражения в скобках. Возведения в степень, который обычно имеет более высокий приоритет, чем сложения и умножения, вычисляется в этом примере последнего, поскольку другие выражения заключены в круглые скобки.  
  
## <a name="see-also"></a>См. также  
 [Арифметические операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [Операторы сравнения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Логические и побитовые операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [Логические (побитовые) операторы (Visual Basic)](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Логические выражения](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [Сравнения значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [Практическое руководство. Вычисление числовых значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)  
 [Порядок применения операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)
