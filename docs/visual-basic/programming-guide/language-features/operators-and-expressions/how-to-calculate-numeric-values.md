---
title: "Практическое руководство. Вычисление числовых значений (Visual Basic) | Microsoft Docs"
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
  - "вычисления, числовые выражения"
  - "выражения [Visual Basic], числовой"
  - "числовые выражения"
  - "приоритет операторов"
  - "операторы [Visual Basic]"
  - "приоритет, операторов"
  - "код Visual Basic, выражения"
  - "код Visual Basic, операторы"
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Практическое руководство. Вычисление числовых значений (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Числовые значения можно вычислить с помощью числовых выражений.  *Числовое выражение* — это выражение, которое содержит литералы, константы и переменные, представляющие числовые значения, а также операторы, действующие на эти значения.  
  
## Вычисление числовых значений  
  
#### Для вычисления числового значения  
  
-   Объедините один или несколько числовых литералов, констант и переменных в числовое выражение.  В следующем примере показаны некоторые допустимые числовые выражения.  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     В первых трех строках отображается литерал, константа и переменная.  Каждый сам по себе является формой допустимого числового выражения  Последняя строка показывает комбинацию переменной с двумя литералами.  
  
     Обратите внимание, что числовое выражение само по себе не образует завершенной инструкции [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  Необходимо использовать выражение как часть завершенной инструкции.  
  
#### Для хранения числовых значений  
  
-   Можно использовать оператор назначения для назначения числового выражения переменной, как показано в следующем примере.  
  
     [!code-vb[VbVbalrOperators#82](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_1.vb)]  
  
     В предыдущем примере значение выражения в правой части оператора равно \(`=`\) присваивается переменной `j` слева от оператора, поэтому `j` вычисляется как 276.  
  
     Дополнительные сведения см. в разделе [Операторы](../../../../visual-basic/language-reference/statements/index.md).  
  
## Несколько операторов  
 Если числовое выражение содержит более одного оператора, порядок их вычисления определяется правилами приоритета операторов.  Для переопределения правил приоритета операторов выражения заключаются в круглые скобки, как в предыдущем примере. Такие выражения вычисляются в первую очередь.  
  
#### Чтобы переопределить приоритет обычного оператора  
  
-   Используйте скобки для заключения в них операций, которые должны выполняться в первую очередь.  В следующем примере показано два разных результата с теми же операндами и операторами.  
  
     [!code-vb[VbVbalrOperators#83](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_2.vb)]  
  
     В предыдущем примере при вычислении `j` сперва выполняется дополнительный оператор\(`+`\), так как скобки `(67 + i)` переопределяют стандартный порядок действий. Переменной `j` присваивается значение 276 \(4 х 69\).  При вычислении `k` операторы выполняются в обычном порядке \(`*` перед `+`\). Переменной `k` присваивается значение 270 \(268 \+ 2\).  
  
     Дополнительные сведения см. в разделе [Порядок применения операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## См. также  
 [Операторы и выражения](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Сравнения значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)   
 [Операторы](../../../../visual-basic/language-reference/statements/index.md)   
 [Порядок применения операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Арифметические операторы](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Эффективное сочетание операторов](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)