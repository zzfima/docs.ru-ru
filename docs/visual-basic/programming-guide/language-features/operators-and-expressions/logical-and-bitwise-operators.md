---
title: Логические и побитовые операторы
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
ms.openlocfilehash: 55a246c0d56501a409ebbc7d0d0aa39ae9fa1770
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343590"
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a>Логические и побитовые операторы в Visual Basic
Логические операторы сравнивают `Boolean` выражения и возвращают `Boolean` результат. Операторы `And`, `Or`, `AndAlso`, `OrElse`и `Xor` являются *двоичными* , так как они принимают два операнда, а оператор `Not` — *унарный* , так как он принимает один операнд. Некоторые из этих операторов также могут выполнять побитовые логические операции над целочисленными значениями.  
  
## <a name="unary-logical-operator"></a>Унарный логический оператор  
 [Оператор not](../../../../visual-basic/language-reference/operators/not-operator.md) выполняет логическое *отрицание* в выражении `Boolean`. Он возвращает логическое противоположное значение операнда. Если выражение принимает значение `True`, `Not` возвращает `False`; Если выражение принимает значение `False`, `Not` возвращает `True`. Это показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#77)]  
  
## <a name="binary-logical-operators"></a>Бинарные логические операторы  
 [Оператор and](../../../../visual-basic/language-reference/operators/and-operator.md) выполняет логическое *умножение* двух выражений `Boolean`. Если оба выражения оцениваются как `True`, `And` возвращает `True`. Если хотя бы одно из выражений имеет значение `False`, `And` возвращает `False`.  
  
 [Оператор OR](../../../../visual-basic/language-reference/operators/or-operator.md) выполняет логическое *сложение* или *включение* в двух выражениях `Boolean`. Если любое из выражений принимает значение `True`или оба значения имеют значение `True`, то `Or` возвращает `True`. Если ни одно из выражений не имеет значение `True`, `Or` возвращает `False`.  
  
 [Оператор XOR](../../../../visual-basic/language-reference/operators/xor-operator.md) выполняет логическое *исключение* в двух выражениях `Boolean`. Если только одно выражение имеет значение `True`, но не оба, `Xor` возвращает `True`. Если оба выражения оцениваются как `True` или оба имеют `False`, `Xor` возвращает `False`.  
  
 В следующем примере показаны операторы `And`, `Or`и `Xor`.  
  
 [!code-vb[VbVbalrOperators#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#78)]  
  
## <a name="short-circuiting-logical-operations"></a>Сокращенное вычисление логических операций  
 [Оператор AndAlso](../../../../visual-basic/language-reference/operators/andalso-operator.md) очень похож на оператор `And` в том, что он также выполняет логическое умножение двух `Boolean`ных выражений. Основное различие между ними состоит в том, что `AndAlso` приводит к *сокращению* поведения. Если первое выражение в `AndAlso` выражении имеет значение `False`, второе выражение не вычисляется, так как оно не может изменить окончательный результат, а `AndAlso` возвращает `False`.  
  
 Аналогичным образом [оператор OrElse](../../../../visual-basic/language-reference/operators/orelse-operator.md) выполняет сокращенное логическое сложение двух `Boolean` выражений. Если первое выражение в `OrElse` выражении имеет значение `True`, второе выражение не вычисляется, так как оно не может изменить окончательный результат, а `OrElse` возвращает `True`.  
  
### <a name="short-circuiting-trade-offs"></a>Сокращенное вычисление компромиссов  
 Сокращенное вычисление может повысить производительность, не вычисляя выражение, которое не может изменить результат логической операции. Однако если это выражение выполняет дополнительные действия, сокращенное вычисление пропускает эти действия. Например, если выражение содержит вызов `Function` процедуры, эта процедура не вызывается, если выражение сокращено, и любой дополнительный код, содержащийся в `Function`, не выполняется. Таким образом, функция может выполняться только иногда и может быть некорректно проверена. Или логика программы может зависеть от кода в `Function`.  
  
 В следующем примере показана разница между `And`, `Or`и их сокращенными аналогами.  
  
 [!code-vb[VbVbalrOperators#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#81)]  
  
 [!code-vb[VbVbalrOperators#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#80)]  
  
 [!code-vb[VbVbalrOperators#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#79)]  
  
 Обратите внимание, что в предыдущем примере некоторый важный код в `checkIfValid()` не выполняется при сокращенном вызове. Первая инструкция `If` вызывает `checkIfValid()` несмотря на то, что `12 > 45` возвращает `False`, так как `And` не является сокращенной схемой. Вторая инструкция `If` не вызывает `checkIfValid()`, так как когда `12 > 45` возвращает `False`, `AndAlso` сокращенное значение второго выражения. Третья `If`ная инструкция вызывает `checkIfValid()` несмотря на то, что `12 < 45` возвращает `True`, так как `Or` не является сокращенной схемой. Четвертый оператор `If` не вызывает `checkIfValid()`, так как когда `12 < 45` возвращает `True`, `OrElse` сокращенное значение второго выражения.  
  
## <a name="bitwise-operations"></a>Битовые операции  
 Побитовые операции оценивают два целочисленных значения в форме binary (основание 2). Они сравнивают биты в соответствующих позициях и затем присваивают значения на основе сравнения. В следующем примере показан оператор `And`.  
  
 [!code-vb[VbVbalrConcepts#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#2)]  
  
 В предыдущем примере значение `x` задается равным 1. Это происходит по следующим причинам.  
  
- Значения рассматриваются как двоичные:  
  
     3 в двоичном формате = 011  
  
     5 в двоичном формате = 101  
  
- Оператор `And` сравнивает двоичные представления, по одной двоичной позиции (бит) за раз. Если оба бита в заданной позиции равны 1, то в результате в эту точку помещается 1. Если любой из битов равен 0, то в результат помещается 0. В предыдущем примере это работает следующим образом:  
  
     011 (3 в двоичной форме)  
  
     101 (5 в двоичной форме)  
  
     001 (результат в двоичной форме)  
  
- Результат считается десятичным. Значение 001 является двоичным представлением 1, поэтому `x` = 1.  
  
 Побитовая операция `Or` похожа на, за исключением того, что значение 1 назначается биту результата, если один или оба сравниваемых бита равны 1. `Xor` присваивает значение 1 результирующему биту, если ровно один из сравниваемых битов (не оба) равен 1. `Not` принимает один операнд и инвертирует все биты, включая бит знака, и присваивает это значение результату. Это означает, что для положительных чисел со знаком `Not` всегда возвращает отрицательное значение, а для отрицательных чисел `Not` всегда возвращает положительное или нулевое значение.  
  
 Операторы `AndAlso` и `OrElse` не поддерживают побитовые операции.  
  
> [!NOTE]
> Битовые операции могут выполняться только с целыми типами. Перед выполнением побитовой операции значения с плавающей запятой необходимо преобразовать в целочисленные типы.  
  
## <a name="see-also"></a>См. также

- [Логические и битовые операторы (Visual Basic)](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Логические выражения](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [Арифметические операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Операторы сравнения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Операторы объединения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [Эффективное сочетание операторов](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
