---
title: "Оператор /= (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb./=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- /= operator [Visual Basic]
- operator /=
- compound assignment statements [Visual Basic]
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 94448856072a949582e64577287134c4b975bfec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a>Оператор /= (Visual Basic)
Делит значение переменной или свойства на значение выражения и присваивает результат с плавающей запятой переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
variableorproperty /= expression  
```  
  
## <a name="parts"></a>Части  
 `variableorproperty`  
 Обязательный. Числовая переменная или свойство.  
  
 `expression`  
 Обязательный. Произвольное числовое выражение.  
  
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
