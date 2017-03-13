---
title: "Операторы и выражения в Visual Basic | Microsoft Docs"
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
  - "выражения [Visual Basic]"
  - "операнды"
  - "операнды, определение"
  - "операторы [Visual Basic]"
  - "операторы [Visual Basic], операнды"
  - "код Visual Basic, выражения"
  - "код Visual Basic, операторы"
ms.assetid: b86f3131-94ee-448f-96cd-79611e028b26
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Операторы и выражения в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

*Оператор* является элементом кода, выполняющим операцию с одним или несколькими элементами кода, которые содержат значения.  Элементы значений включают переменные, константы, литералы, свойства, возвращаемый значения `Function` и процедуры `Operator`, а также выражения.  
  
 *Выражение* представляет собой набор элементов значений в сочетании с операторами, который приводит к новому значению.  Операторы выполняют над элементами значений различные действия путем вычисления, сравнения и других операций.  
  
## Типы операторов  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] предоставляет следующие типы операторов:  
  
-   [Арифметические операторы](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) выполняют знакомые вычисления над числовыми значениями, включая сдвиг их битовых шаблонов.  
  
-   [Операторы сравнения](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) сравнивают два выражения и возвращают логическое значение \(`Boolean`\), представляющее результат сравнения.  
  
-   [Операторы объединения](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md) объединяют несколько строк в одну.  
  
-   [Логические и побитовые операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md) объединяют `Boolean` или числовые значения и возвращают результат того же типа данных, что и значения.  
  
 Элементы значения, объединенные с оператором, называются *операнды* этого оператора.  Операторы, объединенные с элементами значения, образуют выражения за исключением оператора назначения, который образует *инструкцию*.  Дополнительные сведения см. в разделе [Операторы](../../../../visual-basic/programming-guide/language-features/statements.md).  
  
## Расчет значений выражений  
 Конечный результат выражения представляет значение, которое обычно принадлежит знакомому типу данных, например, `Boolean`, `String` или числовому типу.  
  
 Ниже представлены примеры выражений:  
  
 `5 + 4`  
  
 `' The preceding expression evaluates to 9.`  
  
 `15 * System.Math.Sqrt(9) + x`  
  
 `' The preceding expression evaluates to 45 plus the value of x.`  
  
 `"Concat" & "ena" & "tion"`  
  
 `' The preceding expression evaluates to "Concatenation".`  
  
 `763 < 23`  
  
 `' The preceding expression evaluates to False.`  
  
 Несколько операторов могут выполнять действия в одном выражении или инструкции, как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#56](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/index_1.vb)]  
  
 В предыдущем примере [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] выполняет операции в выражении в правой части оператора присваивания \(`=`\) и присваивает полученное значение переменной `x` слева.  Нет практического ограничения количества операторов, которые могут быть объединены в одно выражение, но, чтобы получить ожидаемые результаты, необходимо понимание [Порядок применения операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
 Дополнительные сведения и примеры содержатся в [Перегрузка операторов в Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703).  
  
## См. также  
 [Операторы](../../../../visual-basic/language-reference/operators/index.md)   
 [Эффективное сочетание операторов](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)   
 [Операторы](../../../../visual-basic/language-reference/statements/index.md)