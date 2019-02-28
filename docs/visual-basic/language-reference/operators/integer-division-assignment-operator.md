---
title: '\= Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- '\='
- vb.\=
helpviewer_keywords:
- '\= operator [Visual Basic]'
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator \= [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 6f39915d-e398-4045-afcc-da6885e57b9c
ms.openlocfilehash: 2b24cfe3357bfe5be213464facd9f9db0a5e27e0
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977997"
---
# <a name="-operator"></a>\\= Оператор
Делит значение переменной или свойства на значение выражения и присваивает целочисленный результат переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
variableorproperty \= expression  
```  
  
## <a name="parts"></a>Части  
 `variableorproperty`  
 Обязательный. Любой числовой переменной или свойства.  
  
 `expression`  
 Обязательный. Произвольное числовое выражение.  
  
## <a name="remarks"></a>Примечания  
 Элемент, на левой стороне `\=` оператор может быть простой скалярной переменной, свойства или элемента массива. Не может быть переменной или свойству [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 `\=` Оператор делит значение переменной или свойства слева от него значение справа и присваивает целочисленный результат переменной или свойству слева от него  
  
 Для получения дополнительных сведений при целочисленном делении см. в разделе [\ оператора (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).  
  
## <a name="overloading"></a>Перегрузка  
 `\` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Перегрузка `\` оператор влияет на поведение `\=` оператор. Если код использует `\=` для класса или структуры, перегружающей `\`, убедитесь, что его переопределенное. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `\=` оператор деления для деления одного `Integer` переменных в секунду и назначить результат целое число в первой переменной.  
  
 [!code-vb[VbVbalrOperators#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#19)]  
  
## <a name="see-also"></a>См. также
- [\ Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [/ =-Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
