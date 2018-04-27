---
title: Практическое руководство. Вычисление числовых значений (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- operator precedence
- operators [Visual Basic]
- expressions [Visual Basic], numeric
- calculations [Visual Basic], numeric expressions
- precedence [Visual Basic], of operators
- Visual Basic code, operators
- Visual Basic code, expressions
- numeric expressions
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 322e2c9fe7f668e08a42cd707c5d81090aca627c
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-calculate-numeric-values-visual-basic"></a>Практическое руководство. Вычисление числовых значений (Visual Basic)
Можно вычислить числовые значения с помощью числовых выражений. Объект *числовое выражение* является выражение, которое содержит литералы, константы и переменные, представляющие числовые значения и операторы, выполняющие действия с этими значениями.  
  
## <a name="calculating-numeric-values"></a>Вычисление числовых значений  
  
#### <a name="to-calculate-a-numeric-value"></a>Для вычисления числового значения  
  
-   Объединить один или несколько числовых литералов, констант и переменных в числовое выражение. В следующем примере показано некоторые допустимые числовые выражения.  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     Первые три строки отображение литерал, константы и переменной. Каждый из них образует допустимое числовое выражение само по себе. Последняя строка показывает комбинацию переменной с двумя литералами.  
  
     Обратите внимание, что числовое выражение не образуют полную инструкцию Visual Basic сам по себе. Необходимо использовать выражение как часть является законченным оператором.  
  
#### <a name="to-store-a-numeric-value"></a>Для получения числового значения  
  
-   Чтобы назначить значение, представленное числовое выражение переменной, как показано в следующем примере, можно использовать оператор присваивания.  
  
     [!code-vb[VbVbalrOperators#82](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_1.vb)]  
  
     В предыдущем примере значение выражения в правой части оператора равно (`=`) присваивается переменной `j` слева от оператора, поэтому `j` вычисляется как 276.  
  
     Дополнительные сведения см. в разделе [Выписки](../../../../visual-basic/language-reference/statements/index.md).  
  
## <a name="multiple-operators"></a>Несколько операторов  
 Если числовое выражение содержит несколько операторов, порядок, в котором они вычисляются определяется правилами приоритета операторов. Для переопределения правил приоритета операторов, выражения заключаются в круглые скобки, как показано в приведенном выше примере; такие выражения вычисляются первыми.  
  
#### <a name="to-override-normal-operator-precedence"></a>Чтобы переопределить обычный приоритет операторов  
  
-   Используйте скобки для заключения операции, которые вы хотите сначала необходимо выполнить. В следующем примере показано два разных результата с теми же операндами и операторы.  
  
     [!code-vb[VbVbalrOperators#83](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_2.vb)]  
  
     В предыдущем примере, то вычисление для `j` выполняет оператор сложения (`+`) первый так как скобки вокруг `(67 + i)` переопределить обычный приоритет и значение, присваиваемое `j` равно 276 (4 раза 69). Расчет `k` операторы выполняются в обычном порядке (`*` перед `+`) и значение, присваиваемое `k` равно 270 (268 плюс 2).  
  
     Дополнительные сведения см. в разделе [операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## <a name="see-also"></a>См. также  
 [Операторы и выражения](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Сравнения значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [Операторы](../../../../visual-basic/language-reference/statements/index.md)  
 [Порядок применения операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Арифметические операторы](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Эффективное сочетание операторов](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
