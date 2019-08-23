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
ms.openlocfilehash: 40076b2ad6606b4c565bcd39dbeea9e55da47211
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963314"
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a>Логические и побитовые операторы в Visual Basic
Логические операторы сравнивают `Boolean` выражения и `Boolean` возвращают результат. `And`Операторы, `Not` , ,и`AndAlso`являются двоичными, поскольку они принимают два операнда, а оператор является унарным, так как он принимает один операнд. `Or` `OrElse` `Xor` Некоторые из этих операторов также могут выполнять побитовые логические операции над целочисленными значениями.  
  
## <a name="unary-logical-operator"></a>Унарный логический оператор  
 [Оператор not](../../../../visual-basic/language-reference/operators/not-operator.md) выполняет логическое *отрицание* в `Boolean` выражении. Он возвращает логическое противоположное значение операнда. Если результатом вычисления `True`выражения является `Not` , возвращается `False`значение; `Not` если результат вычисления выражения равен `False`, возвращается `True`значение. Это показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#77)]  
  
## <a name="binary-logical-operators"></a>Бинарные логические операторы  
 [Оператор and](../../../../visual-basic/language-reference/operators/and-operator.md) выполняет логическое *умножение* двух `Boolean` выражений. Если оба выражения имеют значение `True` `And` , возвращается `True`значение. Если хотя бы одно из выражений имеет значение `False` `And` , возвращается `False`значение.  
  
 [Оператор OR](../../../../visual-basic/language-reference/operators/or-operator.md) выполняет логическое *сложение* или *Включение* двух `Boolean` выражений. Если любое из выражений `True`принимает значение, или оба `True`значения имеют значение, `Or` возвращается `True`значение. Если ни одно из выражений не `True`имеет `Or` значение `False`, возвращает.  
  
 [Оператор XOR](../../../../visual-basic/language-reference/operators/xor-operator.md) выполняет логическое *исключение* для двух `Boolean` выражений. Если только одно выражение имеет `True`значение, но не оба, `Xor` возвращает `True`. Если `True` оба выражения имеют значение или `False`, `Xor` возвращает `False`.  
  
 В следующем примере показаны `And`операторы, `Or`и. `Xor`  
  
 [!code-vb[VbVbalrOperators#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#78)]  
  
## <a name="short-circuiting-logical-operations"></a>Сокращенное вычисление логических операций  
 [Оператор AndAlso](../../../../visual-basic/language-reference/operators/andalso-operator.md) очень похож на `And` оператор, в котором он также выполняет логическое умножение двух `Boolean` выражений. Основное различие между ними состоит в том, `AndAlso` что приводит к *сокращению* поведения. Если `AndAlso` первое выражение в выражении имеет `False`значение, второе выражение не вычисляется, так как не может изменить окончательный результат и `AndAlso` возвращает `False`.  
  
 Аналогично [оператор OrElse](../../../../visual-basic/language-reference/operators/orelse-operator.md) выполняет сокращенное вычисление логического сложения двух `Boolean` выражений. Если `OrElse` первое выражение в выражении имеет `True`значение, второе выражение не вычисляется, так как не может изменить окончательный результат и `OrElse` возвращает `True`.  
  
### <a name="short-circuiting-trade-offs"></a>Сокращенное вычисление компромиссов  
 Сокращенное вычисление может повысить производительность, не вычисляя выражение, которое не может изменить результат логической операции. Однако если это выражение выполняет дополнительные действия, сокращенное вычисление пропускает эти действия. Например, если выражение содержит вызов `Function` процедуры, эта процедура не вызывается, если выражение сокращено, а любой дополнительный код, содержащийся в, `Function` не выполняется. Таким образом, функция может выполняться только иногда и может быть некорректно проверена. Или логика программы может зависеть от кода в `Function`.  
  
 В следующем примере показана разница между `And`, `Or`и их сокращенными аналогами.  
  
 [!code-vb[VbVbalrOperators#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#81)]  
  
 [!code-vb[VbVbalrOperators#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#80)]  
  
 [!code-vb[VbVbalrOperators#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#79)]  
  
 Обратите внимание, что в предыдущем примере некоторый важный код `checkIfValid()` внутри не выполняется при сокращенном вызове. `If` Первый оператор вызывает `checkIfValid()` , хотя `12 > 45` `And` возвращает `False`, так как не выполняет сокращенное вычисление. Вторая `If` инструкция не вызывает метод `checkIfValid()` `12 > 45` ,поскольку`False`при возврате происходит сокращенноезначениевтороговыражения.`AndAlso` Третья `If` инструкция вызывает `checkIfValid()` , даже если `12 < 45` возвращает `True`, так `Or` как не выполняет сокращенное вычисление. Четвертый `If` оператор не вызывает метод `checkIfValid()` `12 < 45` ,поскольку`True`при возврате происходит сокращенноезначениевтороговыражения.`OrElse`  
  
## <a name="bitwise-operations"></a>Битовые операции  
 Побитовые операции оценивают два целочисленных значения в форме binary (основание 2). Они сравнивают биты в соответствующих позициях и затем присваивают значения на основе сравнения. В следующем примере показан `And` оператор.  
  
 [!code-vb[VbVbalrConcepts#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#2)]  
  
 В предыдущем примере задается значение `x` 1. Это происходит по следующим причинам.  
  
- Значения рассматриваются как двоичные:  
  
     3 в двоичном формате = 011  
  
     5 в двоичном формате = 101  
  
- `And` Оператор сравнивает двоичные представления, по одной двоичной позиции (бит) за раз. Если оба бита в заданной позиции равны 1, то в результате в эту точку помещается 1. Если любой из битов равен 0, то в результат помещается 0. В предыдущем примере это работает следующим образом:  
  
     011 (3 в двоичной форме)  
  
     101 (5 в двоичной форме)  
  
     001 (результат в двоичной форме)  
  
- Результат считается десятичным. Значение 001 является двоичным представлением 1, то есть `x` = 1.  
  
 Побитовая `Or` операция аналогична, за исключением того, что 1 назначается биту результата, если один или оба сравниваемых бита равны 1. `Xor`присваивает значение 1 результирующему биту, если ровно один из сравниваемых битов (не оба) равен 1. `Not`принимает один операнд и инвертирует все биты, включая бит знака, и присваивает это значение результату. Это означает, что для положительных чисел `Not` со знаком всегда возвращает отрицательное значение, а для отрицательных `Not` чисел всегда возвращает положительное или нулевое значение.  
  
 Операторы `AndAlso` и`OrElse` не поддерживают побитовые операции.  
  
> [!NOTE]
> Битовые операции могут выполняться только с целыми типами. Перед выполнением побитовой операции значения с плавающей запятой необходимо преобразовать в целочисленные типы.  
  
## <a name="see-also"></a>См. также

- [Логические и битовые операторы (Visual Basic)](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Логические выражения](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [Арифметические операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Операторы сравнения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Операторы объединения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [Эффективное сочетание операторов](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
