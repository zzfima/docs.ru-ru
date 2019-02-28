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
ms.openlocfilehash: 065df7d6217dd6f817dee1d11dd0fd4a68b6323c
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965544"
---
# <a name="boolean-expressions-visual-basic"></a>Логические выражения (Visual Basic)
Объект *логическое выражение* представляет собой выражение, результатом которого является значение из [логический тип данных](../../../../visual-basic/language-reference/data-types/boolean-data-type.md): `True` или `False`. `Boolean` выражения могут принимать различные формы. Самым простым является прямое сравнение значения `Boolean` переменной `Boolean` литерал, как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#87)]  
  
## <a name="two-meanings-of-the--operator"></a>Два значения =-оператор  
 Обратите внимание, что оператор присваивания `newCustomer = True` выглядит так же, как выражение в предыдущем примере, но она выполняет другую функцию и используется по-разному. В предыдущем примере выражение `newCustomer = True` представляет логическое значение и `=` входа интерпретируется как оператор сравнения. В автономной инструкции `=` входа интерпретируется как оператор присваивания и присваивает значение справа переменной слева. Это показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#88](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#88)]  
  
 Для получения дополнительных сведений см. в разделе [сравнений значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) и [инструкций](../../../../visual-basic/language-reference/statements/index.md).  
  
## <a name="comparison-operators"></a>Операторы сравнения  
 Операторы сравнения, такие как `=`, `<`, `>`, `<>`, `<=`, и `>=` создания логических выражений, сравнивая выражение слева от оператора в выражение справа от оператора оператора и представляют результат в виде `True` или `False`. Это показано в следующем примере.  
  
 `42 < 81`  
  
 Поскольку 42 меньше 81, в предыдущем примере логическое выражение принимает значение `True`. Дополнительные сведения о выражениях такого рода, см. в разделе [сравнений значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md).  
  
### <a name="comparison-operators-combined-with-logical-operators"></a>Сравнение операторов в сочетании с логическими операторами  
 Выражения сравнения можно комбинировать с логическими операторами для создания более сложных логических выражений. Следующий пример демонстрирует использование операторов сравнения в сочетании с логическим оператором.  
  
 `x > y And x < 1000`  
  
 В предыдущем примере значение полного выражения зависит от значения выражения на каждой стороне `And` оператор. Если оба выражения имеют `True`, то общее выражение, результатом которого является `True`. Если любое из выражений `False`, то все выражение, результатом которого является `False`.  
  
## <a name="short-circuiting-operators"></a>Сокращенное вычисление операторы  
 Логические операторы `AndAlso` и `OrElse` демонстрируют поведение, известный как *сокращенного вычисления*. Вычисляют сначала вычисляет левый операнд. Если левый операнд определяет значение всего выражения, выполнение программы продолжается без вычисления правого выражения. Это показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#89)]  
  
 В приведенном выше примере оператор вычисляет левое выражение `45 < 12`. Так как левое выражение, результатом которого является `False`, всего логическое выражение должно возвращать `False`. Таким образом, выполнение программы пропускает выполнение кода внутри `If` блок без вычисления правого выражения `testFunction(3)`. В этом примере не вызывает `testFunction()` так как левое выражение опровергает всего выражения.  
  
 Аналогичным образом если левое выражение в логическом выражении, использующем `OrElse` принимает значение `True`, выполнение переходит на следующую строку кода без вычисления правого выражения, поскольку левое выражение уже проверила всего выражение.  
  
### <a name="comparison-with-non-short-circuiting-operators"></a>Сравнение с не--сокращенного операторы  
 Напротив, обе части логического оператора вычисляются при логические операторы `And` и `Or` используются. Это показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#90](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#90)]  
  
 В предыдущем примере вызывается `testFunction()` несмотря на то, что левое выражение, результатом которого является `False`.  
  
## <a name="parenthetical-expressions"></a>Выражения в скобках  
 Круглые скобки используются для управления порядком вычисления логических выражений. Сначала оценить выражения, заключенные в круглые скобки. Для нескольких уровней вложения приоритет предоставляется наиболее глубоко вложенных выражений. Внутри скобок процесс оценки переходит в соответствии с правилами приоритета операторов. Дополнительные сведения см. в разделе [порядок применения операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## <a name="see-also"></a>См. также
- [Логические и побитовые операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [Сравнения значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Операторы](../../../../visual-basic/programming-guide/language-features/statements.md)
- [Операторы сравнения](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Эффективное сочетание операторов](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
- [Порядок применения операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Логический тип данных](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)
