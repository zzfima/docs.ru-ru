---
title: '&amp;= Оператор (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.&=
helpviewer_keywords:
- operator &=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '&= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
ms.openlocfilehash: c3db2d4095600f32af92d1a4ce1f806a3f032af0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="amp-operator-visual-basic"></a>&amp;= Оператор (Visual Basic)
Сцепляет `String` выражение `String` переменной или свойства и присваивает результат переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
variableorproperty &= expression  
```  
  
## <a name="parts"></a>Части  
 `variableorproperty`  
 Обязательно. Любой `String` переменной или свойству.  
  
 `expression`  
 Обязательно. Произвольное выражение `String`.  
  
## <a name="remarks"></a>Примечания  
 Элемент, на левой стороне `&=` оператор может быть простой скалярной переменной, свойством или элемент массива. Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md). `&=` Оператор объединяет `String` выражение справа для `String` переменной или свойству слева от него и присваивает результат переменной или свойству слева от него.  
  
## <a name="overloading"></a>Перегрузка  
 [& Оператор](../../../visual-basic/language-reference/operators/concatenation-operator.md) может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Перегрузка `&` оператор влияет на поведение `&=` оператор. Если ваш код использует `&=` для класса или структуры, перегружающей `&`, убедитесь, что его переопределенное. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `&=` оператор для сцепления двух `String` переменные и назначить результат первой переменной.  
  
 [!code-vb[VbVbalrOperators#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор &](../../../visual-basic/language-reference/operators/concatenation-operator.md)  
 [Оператор +=](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
 [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [Операторы объединения](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
