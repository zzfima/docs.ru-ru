---
title: Практическое руководство. Вычисление числовых значений (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 33184d9be275f5e777ffd79c6dd4e3182d865de7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58825759"
---
# <a name="how-to-calculate-numeric-values-visual-basic"></a>Практическое руководство. Вычисление числовых значений (Visual Basic)
Вы можете вычислить числовые значения с помощью числовых выражений. Объект *числовое выражение* является выражение, которое содержит литералы, константы и переменные, представляющие числовых значений и операторов, работать с этими значениями.  
  
## <a name="calculating-numeric-values"></a>Вычисление числовых значений  
  
#### <a name="to-calculate-a-numeric-value"></a>Для вычисления числовое значение  
  
-   Объединить один или несколько числовых литералов, констант и переменных в числовое выражение. В следующем примере некоторые допустимые числовые выражения.  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     Первые три строки отображения литерал, константы и переменной. Каждый из них forms допустимое числовое выражение, сам по себе. Последняя строка показывает комбинацию переменной с двумя литералами.  
  
     Обратите внимание, что числовое выражение не образует является законченным оператором Visual Basic сам по себе. Необходимо использовать выражение как часть является законченным оператором.  
  
#### <a name="to-store-a-numeric-value"></a>Для хранения числовое значение  
  
-   Чтобы назначить значение, представленное числового выражения, переменной, как показано в следующем примере, можно использовать оператор присваивания.  
  
     [!code-vb[VbVbalrOperators#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#82)]  
  
     В предыдущем примере, значение выражения в правой части оператора равно (`=`) присваивается переменной `j` слева от оператора, поэтому `j` вычисляется как 276.  
  
     Дополнительные сведения см. в разделе [Выписки](../../../../visual-basic/language-reference/statements/index.md).  
  
## <a name="multiple-operators"></a>Несколько операторов  
 Если числовое выражение содержит несколько операторов, порядок, в котором они вычисляются определяется правилами приоритета операторов. Для переопределения правил приоритета операторов, выражения заключать в круглые скобки, как показано в примере выше; выражения вычисляются первыми.  
  
#### <a name="to-override-normal-operator-precedence"></a>Чтобы переопределить обычный приоритет операторов  
  
-   Используйте круглые скобки, чтобы включить операции, которые вы хотите сначала необходимо выполнить. В следующем примере показано два разных результата с теми же операндов и операторов.  
  
     [!code-vb[VbVbalrOperators#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#83)]  
  
     В предыдущем примере, расчет `j` выполняет оператор сложения (`+`) первый так как скобки вокруг `(67 + i)` переопределить обычный приоритет и значение, присваиваемое `j` является 276 (4 раза 69). Расчет `k` операторы выполняются в обычном порядке (`*` перед `+`) и значение, присваиваемое `k` является 270 (268 плюс 2).  
  
     Дополнительные сведения см. в разделе [порядок применения операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## <a name="see-also"></a>См. также

- [Операторы и выражения](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Сравнения значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Операторы](../../../../visual-basic/language-reference/statements/index.md)
- [Порядок применения операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Арифметические операторы](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Эффективное сочетание операторов](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
