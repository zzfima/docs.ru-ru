---
title: Оператор *= (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.*=
helpviewer_keywords:
- operator *=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '*= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
ms.openlocfilehash: 7c009a6b3acfe1528a2c34ed1e10735ac86507e6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032144"
---
# <a name="-operator-visual-basic"></a>Оператор *= (Visual Basic)
Умножает значение переменной или свойства на значение выражения и присваивает результат переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
variableorproperty *= expression  
```  
  
## <a name="parts"></a>Части  
 `variableorproperty`  
 Обязательный. Любой числовой переменной или свойства.  
  
 `expression`  
 Обязательный. Произвольное числовое выражение.  
  
## <a name="remarks"></a>Примечания  
 Элемент, на левой стороне `*=` оператор может быть простой скалярной переменной, свойства или элемента массива. Не может быть переменной или свойству [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 `*=` Оператор сначала Умножает значение выражения (в области справа от оператора) на значение переменной или свойства (в левой части оператора). Оператор затем присваивает результат этой операции переменной или свойству.  
  
## <a name="overloading"></a>Перегрузка  
 [* Оператор](../../../visual-basic/language-reference/operators/multiplication-operator.md) может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Перегрузка `*` оператор влияет на поведение `*=` оператор. Если код использует `*=` для класса или структуры, перегружающей `*`, убедитесь, что его переопределенное. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `*=` чтобы перемножить один `Integer` переменных в секунду и назначает полученное значение первой переменной.  
  
 [!code-vb[VbVbalrOperators#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#5)]  
  
## <a name="see-also"></a>См. также

- [Оператор *](../../../visual-basic/language-reference/operators/multiplication-operator.md)
- [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
