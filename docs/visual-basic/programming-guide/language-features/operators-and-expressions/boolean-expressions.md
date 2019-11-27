---
title: Логические выражения
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
ms.openlocfilehash: 1000ec6e4b35d0cb2c6232b50f9a9551cb0dfdcd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350812"
---
# <a name="boolean-expressions-visual-basic"></a>Логические выражения (Visual Basic)
*Логическое выражение* — это выражение, результатом вычисления которого является значение [логического типа данных](../../../../visual-basic/language-reference/data-types/boolean-data-type.md): `True` или `False`. `Boolean` выражения могут принимать несколько форм. Простейшим является прямое сравнение значения `Boolean` переменной с `Boolean`ным литералом, как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#87)]  
  
## <a name="two-meanings-of-the--operator"></a>Два значения оператора =  
 Обратите внимание, что оператор присваивания `newCustomer = True` выглядит так же, как выражение в предыдущем примере, но выполняет другую функцию и используется по-разному. В предыдущем примере выражение `newCustomer = True` представляет логическое значение, а `=` знак интерпретируется как оператор сравнения. В изолированном операторе `=` знак интерпретируется как оператор присваивания и присваивает значение справа переменной слева. Это показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#88](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#88)]  
  
 Дополнительные сведения см. в разделе [сравнения значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) и [инструкции](../../../../visual-basic/language-reference/statements/index.md).  
  
## <a name="comparison-operators"></a>Операторы сравнения  
 Операторы сравнения, такие как `=`, `<`, `>`, `<>`, `<=`и `>=`, создают логические выражения, сравнивая выражение с левой стороны оператора с выражением в правой части оператора и вычисляя результат как `True` или `False`. Это показано в следующем примере.  
  
 `42 < 81`  
  
 Поскольку 42 меньше 81, логическое выражение в предыдущем примере вычисляется как `True`. Дополнительные сведения об этом типе выражения см. в разделе [сравнения значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md).  
  
### <a name="comparison-operators-combined-with-logical-operators"></a>Операторы сравнения в сочетании с логическими операторами  
 Выражения сравнения можно комбинировать с помощью логических операторов для создания более сложных логических выражений. В следующем примере показано использование операторов сравнения в сочетании с логическим оператором.  
  
 `x > y And x < 1000`  
  
 В предыдущем примере значение общего выражения зависит от значений выражений на каждой стороне оператора `And`. Если оба выражения являются `True`, то общее выражение вычисляется как `True`. Если любое из выражений является `False`, то результатом вычисления всего выражения будет `False`.  
  
## <a name="short-circuiting-operators"></a>Операторы сокращенного вычисления  
 Логические операторы `AndAlso` и `OrElse` демонстрируют поведение, называемое *сокращенным вычислением*. Оператор сокращенного вычисления сначала вычисляет левый операнд. Если левый операнд определяет значение всего выражения, выполнение программы продолжается без вычисления правого выражения. Это показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#89)]  
  
 В предыдущем примере оператор вычисляет левое выражение `45 < 12`. Так как левое выражение принимает значение `False`, все логическое выражение должно иметь значение `False`. Таким результатом, выполнение программы пропускает выполнение кода в блоке `If` без вычисления правого выражения, `testFunction(3)`. Этот пример не вызывает `testFunction()`, так как левое выражение фалсифиес все выражение.  
  
 Аналогично, если левое выражение в логическом выражении, использующем `OrElse`, вычисляется как `True`, выполнение переходит к следующей строке кода без вычисления правого выражения, поскольку левое выражение уже проверило все выражение.  
  
### <a name="comparison-with-non-short-circuiting-operators"></a>Сравнение с операторами, не являющимися сокращенными  
 Напротив, обе стороны логического оператора оцениваются, когда используются логические операторы `And` и `Or`. Это показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#90](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#90)]  
  
 В предыдущем примере вызывается `testFunction()` несмотря на то, что левое выражение принимает значение `False`.  
  
## <a name="parenthetical-expressions"></a>Выражения в скобках  
 Можно использовать круглые скобки для управления порядком вычисления логических выражений. Выражения, заключенные в круглые скобки, сначала оцениваются. Для нескольких уровней вложенности приоритет предоставляется самым глубоким вложенным выражениям. В круглых скобках вычисление продолжается в соответствии с правилами приоритета операторов. Дополнительные сведения см. [в разделе приоритет операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## <a name="see-also"></a>См. также

- [Логические и побитовые операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [Сравнения значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Операторы](../../../../visual-basic/programming-guide/language-features/statements.md)
- [Операторы сравнения](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Эффективное сочетание операторов](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
- [Порядок применения операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Логический тип данных](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)
