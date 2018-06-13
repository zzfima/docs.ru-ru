---
title: Оператор /= (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb./=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- /= operator [Visual Basic]
- operator /=
- compound assignment statements [Visual Basic]
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
ms.openlocfilehash: 642307bc531e7d9ce21a932b112795b35e7b3182
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604098"
---
# <a name="-operator-visual-basic"></a>Оператор /= (Visual Basic)
Делит значение переменной или свойства на значение выражения и присваивает результат с плавающей запятой переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
variableorproperty /= expression  
```  
  
## <a name="parts"></a>Части  
 `variableorproperty`  
 Обязательно. Числовая переменная или свойство.  
  
 `expression`  
 Обязательно. Произвольное числовое выражение.  
  
## <a name="remarks"></a>Примечания  
 Элемент, на левой стороне `/=` оператор может быть простой скалярной переменной, свойством или элемент массива. Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 `/=` Оператор сначала делит значение переменной или свойства (в левой части оператора) значение выражения (в правой части оператора). Затем оператор присваивает результат этой операции с плавающей запятой переменной или свойству.  
  
 Эта инструкция присваивает `Double` значение переменной или свойству в левой части экрана. Если `Option Strict` — `On`, `variableorproperty` должен быть `Double`. Если `Option Strict` — `Off`, Visual Basic выполняет неявное преобразование, а затем присваивает результирующее значение `variableorproperty`, возможные ошибки во время выполнения. Дополнительные сведения см. в разделе [расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) и [оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
## <a name="overloading"></a>Перегрузка  
 [-Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) может быть *перегружены*, это означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Перегрузка `/` оператор влияет на поведение `/=` оператор. Если ваш код использует `/=` для класса или структуры, перегружающей `/`, убедитесь, что его переопределенное. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `/=` оператор деления для деления одного `Integer` переменных в секунду и назначить частное первой переменной.  
  
 [!code-vb[VbVbalrOperators#17](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [/ Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)  
 [\\= Оператор](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
