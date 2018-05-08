---
title: Логические выражения (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- expressions [Visual Basic], Boolean
- expression evaluation [Visual Basic], Boolean expressions
- operators [Visual Basic], short-circuiting
- Visual Basic code, operators
- short-circuit evaluation
- logical operators [Visual Basic], short-circuiting
- operators [Visual Basic], Boolean
- Visual Basic code, expressions
ms.assetid: d3d90406-55c8-4404-8143-50fd7f0d0d1a
ms.openlocfilehash: ff5843c815658468ac69fe5d62a9ea4cac2be830
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="boolean-expressions-visual-basic"></a>Логические выражения (Visual Basic)
Объект *логическое выражение* — это выражение, результатом которого является значение из [тип данных Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md): `True` или `False`. `Boolean` выражения могут принимать различные формы. Самым простым является прямое сравнение значения `Boolean` переменной `Boolean` литерал, как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#87](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_1.vb)]  
  
## <a name="two-meanings-of-the--operator"></a>Два значения =-оператор  
 Обратите внимание, что оператор присваивания `newCustomer = True` выглядит так же, как выражение в предыдущем примере, но она выполняет другую функцию и используется по-разному. В предыдущем примере выражение `newCustomer = True` представляет логическое значение и `=` входа интерпретируется как оператор сравнения. В инструкции автономный `=` входа интерпретируется как оператор присваивания и присваивает значение справа переменной слева. Это показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#88](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_2.vb)]  
  
 Дополнительные сведения см. в разделе [сравнение значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) и [инструкции](../../../../visual-basic/language-reference/statements/index.md).  
  
## <a name="comparison-operators"></a>Операторы сравнения  
 Операторы сравнения, такие как `=`, `<`, `>`, `<>`, `<=`, и `>=` создания логических выражений, сравнивая выражение в левой части оператора с выражением с правой стороны оператора и представляют результат в виде `True` или `False`. Это показано в следующем примере.  
  
 `42 < 81`  
  
 Поскольку 42 меньше 81, логическое выражение в предыдущем примере результатом которого является `True`. Дополнительные сведения о выражениях такого рода см. в разделе [сравнение значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md).  
  
### <a name="comparison-operators-combined-with-logical-operators"></a>Операторы сравнения в комбинации с логическими операторами  
 Выражения сравнения можно комбинировать с логическими операторами для создания более сложных выражений типа Boolean. В следующем примере показано использование операторов сравнения в сочетании с логическим оператором.  
  
 `x > y And x < 1000`  
  
 В предыдущем примере значение полного выражения зависит от значения выражения на каждой стороне `And` оператор. Если оба выражения имеют `True`, а затем полное выражение принимает значение `True`. Если одно из выражений имеет `False`, то все выражение, результатом которого является `False`.  
  
## <a name="short-circuiting-operators"></a>Сокращенные вычисления операторов  
 Логические операторы `AndAlso` и `OrElse` демонстрируют поведение, известный как *сокращенного вычисления*. Вычисляют сначала вычисляет левый операнд. Если левый операнд определяет значение всего выражения, выполнение программы продолжается без вычисления правого выражения. Это показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#89](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_3.vb)]  
  
 В предыдущем примере оператор вычисляет левое выражение `45 < 12`. Так как левое выражение, результатом которого является `False`, весь логическое выражение должно возвращать `False`. Таким образом, выполнение программы пропускает выполнение кода внутри `If` блок без вычисления правого выражения `testFunction(3)`. В этом примере не вызывает `testFunction()` поскольку левое выражение опровергает всего выражения.  
  
 Аналогичным образом если левое выражение в логическом выражении, использующем `OrElse` равен `True`, выполнение продолжается на следующую строку кода без вычисления правого выражения, поскольку левое выражение уже проверены всего выражение.  
  
### <a name="comparison-with-non-short-circuiting-operators"></a>Сравнение с операторами вычисление не Short  
 И наоборот, обе части логического оператора вычисляются при логические операторы `And` и `Or` используются. Это показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#90](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_4.vb)]  
  
 В предыдущем примере вызывается `testFunction()` даже если левое выражение, результатом которого является `False`.  
  
## <a name="parenthetical-expressions"></a>Выражения в скобках  
 Круглые скобки используются для управления порядком вычисления логических выражений. Заключено в скобки выражения вычисляются в первую очередь. Для нескольких уровней вложения приоритет предоставляется наиболее глубоко вложенных выражений. Между скобками вычисление выполняется согласно правилам приоритета операторов. Дополнительные сведения см. в разделе [операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## <a name="see-also"></a>См. также  
 [Логические и побитовые операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [Сравнения значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [Операторы](../../../../visual-basic/programming-guide/language-features/statements.md)  
 [Операторы сравнения](../../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [Эффективное сочетание операторов](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)  
 [Порядок применения операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Логический тип данных](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)
