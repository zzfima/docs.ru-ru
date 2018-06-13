---
title: Оператор ^= (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
ms.openlocfilehash: 571ef26eb188d9044ec8f6c8e6e4b490780f17a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603500"
---
# <a name="-operator-visual-basic"></a>Оператор ^= (Visual Basic)
Возводит значение переменной или свойства в степень выражения и присваивает результат переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a>Части  
 `variableorproperty`  
 Обязательно. Числовая переменная или свойство.  
  
 `expression`  
 Обязательно. Произвольное числовое выражение.  
  
## <a name="remarks"></a>Примечания  
 Элемент, на левой стороне `^=` оператор может быть простой скалярной переменной, свойством или элемент массива. Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 `^=` Оператор сначала вызывает значение переменной или свойства (в левой части оператора) в степень значение выражения (справа от оператора). Затем оператор присваивает результат этой операции переменной или свойству.  
  
 Visual Basic всегда выполняет возведение в степень, в [тип данных Double](../../../visual-basic/language-reference/data-types/double-data-type.md). Операнды любого другого типа преобразуются в `Double`, и результат всегда является `Double`.  
  
 Значение `expression` может быть дробным, отрицательным или оба.  
  
## <a name="overloading"></a>Перегрузка  
 [^ Оператор](../../../visual-basic/language-reference/operators/exponentiation-operator.md) может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Перегрузка `^` оператор влияет на поведение `^=` оператор. Если ваш код использует `^=` для класса или структуры, перегружающей `^`, убедитесь, что его переопределенное. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `^=` оператор для вызова одного `Integer` переменной в степень второй переменной и назначить результат первой переменной.  
  
 [!code-vb[VbVbalrOperators#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/exponentiation-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор ^](../../../visual-basic/language-reference/operators/exponentiation-operator.md)  
 [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
