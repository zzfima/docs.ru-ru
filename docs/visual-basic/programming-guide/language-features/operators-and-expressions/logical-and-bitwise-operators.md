---
title: "Логические и побитовые операторы в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "And - оператор [Visual Basic], логические операторы"
  - "AndAlso - оператор"
  - "логические выражения"
  - "выражения [Visual Basic], Логические"
  - "логические операторы"
  - "логические операторы, двоичные"
  - "логические операторы, логические выражения"
  - "логические операторы, сокращенные вычисления"
  - "логические операторы, унарные"
  - "Not - оператор [Visual Basic], логические выражения"
  - "операторы [Visual Basic], логический"
  - "Or - оператор, логические операторы"
  - "OrElse - оператор [Visual Basic]"
  - "сокращенные вычисления"
  - "сокращенные вычисления, логические операторы"
  - "код Visual Basic, выражения"
  - "код Visual Basic, операторы"
  - "Xor - оператор [Visual Basic], логические выражения"
ms.assetid: ca474e13-567d-4b1d-a18b-301433705e57
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Логические и побитовые операторы в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Логические операторы сравнивают `Boolean` выражения и возвращают `Boolean` результат.  Операторы `And`, `Or`, `AndAlso`, `OrElse` и `Xor` являются  *бинарными* , так как они принимают два операнда, а оператор `Not` является *унарным*, поскольку он принимает один операнд.  Некоторые из этих операторов могут также выполнять побитовые логические операции над целыми значениями.  
  
## Унарный логический оператор  
 [Оператор Not](../../../../visual-basic/language-reference/operators/not-operator.md) выполняет логическое *отрицание* выражения `Boolean`.  Он возвращает логическую противоположность своего операнда.  Если выражение `True`, то `Not` возвращает `False`; если выражение `False`, то `Not` возвращает `True`.  Это показано в приведенном ниже примере.  
  
 [!code-vb[VbVbalrOperators#77](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_1.vb)]  
  
## Бинарные логические операторы  
 [Оператор And](../../../../visual-basic/language-reference/operators/and-operator.md) выполняет логическое *умножение* двух `Boolean` выражений.  Если оба выражения `True`, то `And` возвращает `True`.  Если хотя бы одно из выражений `False`, то `And` возвращает `False`.  
  
 [Оператор Or](../../../../visual-basic/language-reference/operators/or-operator.md) выполняет логическое *сложение* или *импликацию* двух `Boolean` выражений.  Если выражение `True` или оба выражения `True`, то `Or` возвращает `True`.  Если ни одно выражение не `True`, то `Or` возвращает `False`.  
  
 [Оператор Xor](../../../../visual-basic/language-reference/operators/xor-operator.md) выполняет логическое *исключение* двух `Boolean` выражений.  Если точно одно выражение `True`, но не оба, то `Xor` возвращает `True`.  Если оба выражения `True` или оба `False`, то `Xor` возвращает `False`.  
  
 В следующем примере показано использование операторов `And`, `Or` и `Xor`.  
  
 [!code-vb[VbVbalrOperators#78](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_2.vb)]  
  
## Логические операторы сокращенного вычисления  
 [Оператор AndAlso](../../../../visual-basic/language-reference/operators/andalso-operator.md) похож на оператор `And` в том, что он также выполняет логическое умножение двух `Boolean` выражений.  Ключевое различие между ними состоит в том, что `AndAlso` выполняет *сокращенную* обработку.  Если первое выражение `AndAlso` равно `False`, то второе выражение не вычисляется, поскольку оно не повлияет на конечный результат, и `AndAlso` возвращает `False`.  
  
 Подобным образом [Оператор OrElse](../../../../visual-basic/language-reference/operators/orelse-operator.md) выполняет сокращенное логическое сложение для двух `Boolean` выражений.  Если первое выражение `OrElse` равно `True`, то второе выражение не вычисляется, поскольку оно не повлияет на конечный результат, и `OrElse` возвращает `True`.  
  
### Соглашения сокращенных вычислений  
 Сокращенные вычисления могут повысить производительность за счет не вычисления выражений, которые не влияют на результаты логической операции.  Однако, если выражение выполняет дополнительные действия, то сокращенные вычисления пропускают эти действия.  Например, если выражение содержит вызов процедуры `Function`, то эта процедура не вызывается при сокращенном вычислении, и любой дополнительный код, содержащийся в `Function`, не выполняется.  Следовательно, функция может выполняться только иногда и правильно тестировать ее невозможно,  или же логика программы может зависеть от кода в `Function`.  
  
 Следующий пример иллюстрирует разницу между `And`, `Or` и их сокращенными аналогами.  
  
 [!code-vb[VbVbalrOperators#81](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_3.vb)]  
  
 [!code-vb[VbVbalrOperators#80](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_4.vb)]  
  
 [!code-vb[VbVbalrOperators#79](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_5.vb)]  
  
 В предыдущем примере следует отметить, что некоторые важные коды внутри `checkIfValid()` не выполняются при сокращенном вызове.  Первая инструкция `If` вызывает `checkIfValid()`, хотя `12 > 45` принимает значение `False`, так как используется не сокращенный оператор `And`.  Вторая инструкция `If` не вызывает `checkIfValid()`, так как `12 > 45` принимает значение `False`, и `AndAlso` игнорирует второе выражение.  Третья инструкция `If` вызывает `checkIfValid()`, хотя `12 < 45` принимает значение `True`, так как используется не сокращенный оператор `Or`.  Четвертая инструкция `If` не вызывает `checkIfValid()`, так как `12 < 45` возвращает значение `True`, и `OrElse` игнорирует второе выражение.  
  
## Поразрядные операции  
 При поразрядных операциях используются два целых значения в двоичной форме \(по основанию 2\).  Они вычисляются по битам в соответствующих позициях, и значение базируется на сравнении.  В следующем примере демонстрируется оператор `And`.  
  
 [!code-vb[VbVbalrConcepts#2](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/codesnippet/VisualBasic/logical-and-bitwise-operators_6.vb)]  
  
 В предыдущем примере для свойства `x` задается значение 1.  Это связано со следующими причинами:  
  
-   Значения рассматриваются как двоичные:  
  
     3 в двоичной форме \= 011  
  
     5 в двоичной форме \= 101  
  
-   Оператор `And` вычисляет двоичное представление, используя одну двоичную позицию \(бит\) один раз.  Если оба бита данной позиции равны 1, то в результат помещается 1 на эту позицию.  Если любой из разрядов равен 0, то в результат помещается 0 на эту позицию.  В предыдущем примере это происходит следующим образом:  
  
     011 в двоичной форме \= 3  
  
     101 в двоичной форме \= 5  
  
     001 \(Результат в двоичной форме\)  
  
-   Результат рассматривается как десятичное число.  Значение 001 является двоичным представлением 1, поэтому `x` \= 1.  
  
 Операция побитового `Or` аналогична за тем исключением, что результирующему биту присваивается 1, если оба сравниваемых бита равны 1.  При выполнении операции `Xor` результирующему биту присваивается 1, только если ровно один из сравниваемых битов \(а не оба\) равен 1.  `Not` принимает один операнд и инвертирует все биты, включая знаковый бит, и присваивает это значение результату.  Это означает, что для положительных чисел со знаком `Not` всегда возвращает отрицательное значение, а для отрицательных чисел `Not` всегда возвращает положительное или нулевое значение.  
  
 Операторы `AndAlso` и `OrElse` не поддерживают побитовые операции.  
  
> [!NOTE]
>  Поразрядные операции выполняются только над целыми типами.  Значения с плавающей запятой необходимо преобразовать в целые типы перед переходом к поразрядной операции.  
  
## См. также  
 [Логические \(побитовые\) операторы](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)   
 [Логические выражения](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)   
 [Арифметические операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Операторы сравнения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Операторы объединения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)   
 [Эффективное сочетание операторов](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)