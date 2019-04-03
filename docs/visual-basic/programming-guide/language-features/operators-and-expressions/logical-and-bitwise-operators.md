---
title: Логические и побитовые операторы в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- operators [Visual Basic], logical
- AndAlso operator [Visual Basic]
- Not operator [Visual Basic], Boolean expressions
- Xor operator [Visual Basic], Boolean expressions
- And operator [Visual Basic], logical operators
- logical operators [Visual Basic]
- expressions [Visual Basic], Boolean
- Or operator [Visual Basic], logical operators
- Visual Basic code, operators
- short-circuiting [Visual Basic], logical operators
- logical operators [Visual Basic], short-circuiting
- Visual Basic code, expressions
- logical operators [Visual Basic], binary
- OrElse operator [Visual Basic]
- logical operators [Visual Basic], unary
ms.assetid: ca474e13-567d-4b1d-a18b-301433705e57
ms.openlocfilehash: ac47b6d7fa4861d18646a23f442caccc4062852f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819311"
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a>Логические и побитовые операторы в Visual Basic
Логические операторы сравнения `Boolean` выражения и возвращают `Boolean` результат. `And`, `Or`, `AndAlso`, `OrElse`, И `Xor` операторы *двоичных* так, как они принимают два операнда, тогда как `Not` оператор *унарный* так как он принимает один операнд. Некоторые из этих операторов можно также выполнять побитовые логические операции над целыми значениями.  
  
## <a name="unary-logical-operator"></a>Унарный логический оператор  
 [Оператор Not](../../../../visual-basic/language-reference/operators/not-operator.md) выполняет логические *отрицания* на `Boolean` выражение. Он возвращает логическое отрицание операнда. Если выражение, результатом которого является `True`, затем `Not` возвращает `False`; Если выражение, результатом которого является `False`, затем `Not` возвращает `True`. Это показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#77)]  
  
## <a name="binary-logical-operators"></a>Двоичный логические операторы  
 [И оператором](../../../../visual-basic/language-reference/operators/and-operator.md) выполняет логические *совместно* двух `Boolean` выражения. Если оба выражения имеют значение `True`, затем `And` возвращает `True`. Если по крайней мере одно из выражений имеет значение `False`, затем `And` возвращает `False`.  
  
 [Или оператор](../../../../visual-basic/language-reference/operators/or-operator.md) выполняет логические *дизъюнкция* или *включения* двух `Boolean` выражения. Если любое из выражений, результатом которого является `True`, или оба `True`, затем `Or` возвращает `True`. Если ни одно из выражений, результатом которого является `True`, `Or` возвращает `False`.  
  
 [Оператор Xor](../../../../visual-basic/language-reference/operators/xor-operator.md) выполняет логические *исключения* двух `Boolean` выражения. Если только одно выражение, результатом которого является `True`, но не оба `Xor` возвращает `True`. Если оба выражения имеют значение `True` или оба `False`, `Xor` возвращает `False`.  
  
 В следующем примере показано `And`, `Or`, и `Xor` операторы.  
  
 [!code-vb[VbVbalrOperators#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#78)]  
  
## <a name="short-circuiting-logical-operations"></a>Логические операторы сокращенного вычисления  
 [AndAlso Operator](../../../../visual-basic/language-reference/operators/andalso-operator.md) очень похожа на `And` оператор, в том, что он также выполняет логическое умножение двух `Boolean` выражения. Это ключевое различие между этими двумя `AndAlso` характеризуется *сокращенного вычисления* поведение. Если первое выражение в `AndAlso` выражение, результатом которого является `False`, то второе выражение не вычисляется, так как его невозможно изменить конечный результат и `AndAlso` возвращает `False`.  
  
 Аналогичным образом [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md) выполняет сокращенное вычисление логического сложения двух `Boolean` выражения. Если первое выражение в `OrElse` выражение, результатом которого является `True`, то второе выражение не вычисляется, так как его невозможно изменить конечный результат и `OrElse` возвращает `True`.  
  
### <a name="short-circuiting-trade-offs"></a>Сокращенных  
 Сокращенное вычисление можно повысить производительность, не вычисления выражений, которые невозможно изменить результат логической операции. Тем не менее если выражение выполняет дополнительные действия, сокращенного вычисления пропускает эти действия. Например, если выражение включает вызов `Function` процедуры, что процедура не вызывается, если выражение является выполнение этого кода отключено, и любой дополнительный код, содержащийся в `Function` не выполняется. Таким образом функция может выполняться лишь время от времени и не может быть проверен должным образом. Или логику программы могут опираться на код в `Function`.  
  
 В следующем примере показано различие между `And`, `Or`и их сокращенными аналогами.  
  
 [!code-vb[VbVbalrOperators#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#81)]  
  
 [!code-vb[VbVbalrOperators#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#80)]  
  
 [!code-vb[VbVbalrOperators#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#79)]  
  
 В предыдущем примере обратите внимание, что некоторые важные коды внутри `checkIfValid()` не выполняется при сокращенном вызов. Первый `If` инструкция вызывает `checkIfValid()` несмотря на то что `12 > 45` возвращает `False`, так как `And` сокращенный. Второй `If` инструкция не вызывает `checkIfValid()`, так как при `12 > 45` возвращает `False`, `AndAlso` игнорирует второе выражение. Третий `If` инструкция вызывает `checkIfValid()` несмотря на то что `12 < 45` возвращает `True`, так как `Or` сокращенный. Четвертый `If` инструкция не вызывает `checkIfValid()`, так как при `12 < 45` возвращает `True`, `OrElse` игнорирует второе выражение.  
  
## <a name="bitwise-operations"></a>Поразрядные операции  
 Побитовые операции оценки двух целочисленных значений в виде двоичного файла (по основанию 2). Они сравнения биты в соответствующих позициях, а затем назначьте на основе сравнения значений. В следующем примере показано `And` оператор.  
  
 [!code-vb[VbVbalrConcepts#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#2)]  
  
 Предыдущий пример задает значение `x` 1. Это происходит по следующим причинам:  
  
-   Значения обрабатываются как двоичные:  
  
     3 в двоичной форме = 011  
  
     5 в двоичной форме = 101  
  
-   `And` Оператор сравнивает двоичное представление, один двоичный позиции (бит) за раз. Если оба бита в заданной позиции равны 1, 1 помещается в этой позиции, в результате. Если оба бита равны 0, 0 помещается в этой позиции, в результате. В приведенном выше примере это происходит следующим образом:  
  
     011 (3 в двоичной форме)  
  
     101 (5 в двоичной форме)  
  
     001 (результат в двоичной форме)  
  
-   Результат рассматривается как десятичное число. Значение 001 является двоичным представлением 1, поэтому `x` = 1.  
  
 Побитовое `Or` операции аналогичен предыдущему, за исключением того, что бит результата присваивается значение 1, если оба сравниваемых бита равны 1. `Xor` назначает 1 бит результата, если только один из сравниваемых битов (а не оба) равен 1. `Not` принимает один операнд и инвертирует все биты, включая бит знака и присваивает это значение к результату. Это означает, что для положительных чисел со знаком, `Not` всегда возвращает отрицательное значение, а также для отрицательных чисел `Not` всегда возвращает положительное или нулевое значение.  
  
 `AndAlso` И `OrElse` операторы не поддерживают побитовых операций.  
  
> [!NOTE]
>  Побитовые операции могут выполняться только над целыми типами. Значения с плавающей запятой должны преобразовываться в целочисленные типы, прежде чем будет продолжена побитовой операции.  
  
## <a name="see-also"></a>См. также

- [Логические (побитовые) операторы (Visual Basic)](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Логические выражения](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [Арифметические операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Операторы сравнения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Операторы объединения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [Эффективное сочетание операторов](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
