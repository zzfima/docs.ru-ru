---
title: '&gt;&gt;= Оператор (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.>>=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator >>= [Visual Basic]
- compound assignment statements [Visual Basic]
- '>>= operator [Visual Basic]'
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
ms.openlocfilehash: d0c0ea819741f80e30e55a960b1187699898a3bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="gtgt-operator-visual-basic"></a>&gt;&gt;= Оператор (Visual Basic)
Выполняет арифметический сдвиг вправо значения переменной или свойства и присваивает результат переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a>Части  
 `variableorproperty`  
 Обязательно. Переменная или свойство целого типа (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, или `ULong`).  
  
 `amount`  
 Обязательно. Числовое выражение типа данных, который расширяется до `Integer`.  
  
## <a name="remarks"></a>Примечания  
 Элемент, на левой стороне `>>=` оператор может быть простой скалярной переменной, свойством или элемент массива. Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 `>>=` Оператор сначала выполняет арифметический сдвиг вправо значения переменной или свойства. Затем оператор присваивает результат этой операции переменной или свойству.  
  
 Арифметический сдвиг не циклической, это означает, что биты, сдвигаемые результата, не подставляются с другой стороны. В арифметический сдвиг вправо биты, сдвигаемые дальше крайней правой позиции отбрасываются, а крайний левый бит передается в освободившиеся слева позиции битов. Это означает, что если `variableorproperty` имеет отрицательное значение, освобождаемые устанавливаются в единицу. Если `variableorproperty` положительно, или если его тип данных является тип без знака, освобождаемые принимают нулевое значение.  
  
## <a name="overloading"></a>Перегрузка  
 [>> Оператор](../../../visual-basic/language-reference/operators/right-shift-operator.md) может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Перегрузка `>>` оператор влияет на поведение `>>=` оператор. Если ваш код использует `>>=` для класса или структуры, перегружающей `>>`, убедитесь, что его переопределенное. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `>>=` оператор, на которое производится Сдвиг битового представления `Integer` переменной вправо на указанную величину и присвоить его результат переменной.  
  
 [!code-vb[VbVbalrOperators#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор >>](../../../visual-basic/language-reference/operators/right-shift-operator.md)  
 [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [Операторы сдвига битов](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
