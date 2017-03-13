---
title: "Логические выражения (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "логические выражения"
  - "вычисление выражений, логические выражения"
  - "выражения [Visual Basic], Логические"
  - "логические операторы, логические выражения"
  - "логические операторы, сокращенные вычисления"
  - "операторы [Visual Basic], Логические"
  - "операторы [Visual Basic], сокращенные вычисления"
  - "сокращенные вычисления"
  - "сокращенные вычисления"
  - "код Visual Basic, выражения"
  - "код Visual Basic, операторы"
ms.assetid: d3d90406-55c8-4404-8143-50fd7f0d0d1a
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Логические выражения (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

*Логическое выражение* — это выражение, результатом вычисления которого является значение [логического типа данных](../../../../visual-basic/language-reference/data-types/boolean-data-type.md): `True` или `False`.  Выражения `Boolean` могут принимать различные формы.  Самой простой является прямое сравнение значения переменной `Boolean` с литералом `Boolean`, например:  
  
 [!code-vb[VbVbalrOperators#87](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_1.vb)]  
  
## Два значения оператора \=  
 Необходимо отметить, что инструкция присваивания `newCustomer = True` выглядит так же, как выражение из предыдущего примера, но она выполняет другую функцию и используется по\-другому.  В предыдущем примере выражение `newCustomer = True` представляет значение Boolean, а знак `=` интерпретируется как оператор сравнения.  В автономной инструкции символ `=` интерпретируется как оператор присваивания и присваивает вычисленное значение переменной слева.  Это показано в приведенном ниже примере.  
  
 [!code-vb[VbVbalrOperators#88](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_2.vb)]  
  
 Дополнительные сведения см. в разделе [Сравнения значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) и [Операторы](../../../../visual-basic/language-reference/statements/index.md).  
  
## Операторы сравнения  
 Операторы сравнения `=`, `<`, `>`, `<>`, `<=` и `>=` сравнивают выражения в левой части оператора с выражением в правой части оператора и представляют результат в виде логического значения `True` или `False`.  Это показано в приведенном ниже примере.  
  
 `42 < 81`  
  
 Поскольку 42 меньше 81, в предыдущем примере выражение Boolean принимает значение `True`.  Дополнительные сведения о выражениях такого рода содержатся в разделе [Сравнения значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md).  
  
### Операторы сравнения в комбинации с логическими операторами  
 Выражения сравнения можно комбинировать с логическими операторами для создания более сложных логических Boolean выражений.  В следующем примере показано использование операторов сравнения в сочетании с логическим оператором.  
  
 `x > y And x < 1000`  
  
 В данном примере значение полного выражения зависит от значений выражений в каждой части оператора `And`.  Если оба выражения `True`, то полное выражение принимает значение `True`.  Если любая из частей выражения `False`, то полное выражение принимает значение `False`.  
  
## Операторы, допускающие сокращенные вычисления  
 Логические операторы `AndAlso` и `OrElse` представляют обработку, называемую *сокращенной*.  Эти операторы сначала вычисляют выражение, расположенное слева.  Если левый операнд определяет значение всего выражения, то выполнение программы продолжается без вычисления правого выражения.  Это показано в приведенном ниже примере.  
  
 [!code-vb[VbVbalrOperators#89](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_3.vb)]  
  
 В предыдущем примере оператор вычисляет левое выражение `45 < 12`.  Так как левое выражение `False`, всё логическое выражение должно возвращать `False`.  Таким образом, выполнение программы пропускает выполнение кода в блоке `If` без вычисления правого выражения `testFunction(3)`.  В этом примере `testFunction()` не вызывается, поскольку левое выражение опровергает всё выражение.  
  
 Аналогично, если для левой части в логическом выражении, использующем `OrElse`, вычисляется `True`, то выражение переходит к следующей строке кода без вычисления правого выражения, поскольку левое выражение уже определило результат полного выражения.  
  
### Сравнение с обычными операторами  
 И наоборот, обе части логического оператора вычисляются, если используются логические операторы `And` и `Or`.  Это показано в приведенном ниже примере.  
  
 [!code-vb[VbVbalrOperators#90](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_4.vb)]  
  
 В предыдущем примере вызывается `testFunction()`, даже если левое выражение становится равным `False`.  
  
## Выражения в скобках  
 Круглые скобки используются для управления порядком вычисления выражений Boolean.  Выражения, заключенные в круглые скобки, вычисляются в первую очередь.  Для нескольких уровней вложения приоритет предоставляется самым глубоко вложенным \(внутренним\) выражениям.  В круглых скобках вычисление выполняется в соответствии с правилами приоритета операторов.  Дополнительные сведения см. в разделе [Порядок применения операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## См. также  
 [Логические и побитовые операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)   
 [Сравнения значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)   
 [Операторы](../../../../visual-basic/programming-guide/language-features/statements.md)   
 [Операторы сравнения](../../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [Эффективное сочетание операторов](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)   
 [Порядок применения операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Тип данных Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)