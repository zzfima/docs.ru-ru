---
title: "Практическое руководство: вычисление числовых значений (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- operator precedence
- operators [Visual Basic]
- expressions [Visual Basic], numeric
- calculations, numeric expressions
- precedence, of operators
- Visual Basic code, operators
- Visual Basic code, expressions
- numeric expressions
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d844e2af3892d897125e21d3fd7047a8b295d10a
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-calculate-numeric-values-visual-basic"></a>Практическое руководство. Вычисление числовых значений (Visual Basic)
Можно вычислить числовых значений с помощью числовых выражений. Объект *числовое выражение* является выражение, которое содержит литералы, константы и переменные, представляющие числовые значения, а также операторы, действующие на эти значения.  
  
## <a name="calculating-numeric-values"></a>Вычисление числовых значений  
  
#### <a name="to-calculate-a-numeric-value"></a>Для вычисления числового значения  
  
-   Объединение числовых литералов, констант и переменных в числовое выражение. В следующем примере показано некоторые допустимые числовые выражения.  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     Первые три строки показывают литерал, константа и переменная. Каждая из форм допустимое числовое выражение само по себе. Последняя строка показывает комбинацию переменной с двумя литералами.  
  
     Обратите внимание, что числовое выражение не образуют полный [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] инструкции сама по себе. Необходимо использовать выражение как часть полной инструкции.  
  
#### <a name="to-store-a-numeric-value"></a>Для хранения числовых значений  
  
-   Оператор присваивания можно использовать для назначения значения, представленного числового выражения переменной, как показано в следующем примере.  
  
     [!code-vb[VbVbalrOperators&#82;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_1.vb)]  
  
     В предыдущем примере значение выражения в правой части оператора равно (`=`) назначается переменной `j` слева от оператора, поэтому `j` вычисляется как 276.  
  
     Дополнительные сведения см. в разделе [инструкции](../../../../visual-basic/language-reference/statements/index.md).  
  
## <a name="multiple-operators"></a>Несколько операторов  
 Если числовое выражение содержит несколько операторов, порядок, в котором они вычисляются определяется правилами приоритета операторов. Для переопределения правил приоритета операторов выражения заключаются в круглые скобки, как показано в предыдущем примере. такие выражения вычисляются первыми.  
  
#### <a name="to-override-normal-operator-precedence"></a>Чтобы переопределить обычный приоритет операторов  
  
-   Использование скобок для заключения операции, которые вы хотите сначала необходимо выполнить. В следующем примере показано два разных результата с теми же операндов и операторов.  
  
     [!code-vb[VbVbalrOperators&#83;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_2.vb)]  
  
     В предыдущем примере, то вычисление для `j` выполняет оператор сложения (`+`) первого из-за скобки вокруг `(67 + i)` переопределить обычный приоритет и значение, присваиваемое `j` равно 276 (4 раза по 69). Расчет `k` операторы выполняются в обычном порядке (`*` перед `+`) и значение, присваиваемое `k` равно 270 (268 плюс 2).  
  
     Дополнительные сведения см. в разделе [операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## <a name="see-also"></a>См. также  
 [Операторы и выражения](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Сравнение значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)   
 [Инструкции](../../../../visual-basic/language-reference/statements/index.md)   
 [Приоритет операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Арифметические операторы](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Эффективное сочетание операторов](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
