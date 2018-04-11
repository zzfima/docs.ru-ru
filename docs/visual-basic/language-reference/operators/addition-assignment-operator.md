---
title: Оператор += (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.+=
helpviewer_keywords:
- += operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- += operator [Visual Basic], appending strings
- compound assignment statements [Visual Basic]
ms.assetid: d3e959f4-85d4-4e47-87c4-77b62335a5b3
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4ac8f5679aa90c50c15c33a957cfc75d9ccecde6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a>Оператор += (Visual Basic)
Добавляет значение числового выражения к значению числовой переменной или свойства и присваивает результат переменной или свойству. Можно также использовать для объединения `String` выражение `String` переменной или свойства и присвоить его результат переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
variableorproperty += expression  
```  
  
## <a name="parts"></a>Части  
 `variableorproperty`  
 Обязательный. Любые числовые или `String` переменной или свойству.  
  
 `expression`  
 Обязательный. Любые числовые или `String` выражение.  
  
## <a name="remarks"></a>Примечания  
 Элемент, на левой стороне `+=` оператор может быть простой скалярной переменной, свойством или элемент массива. Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 `+=` Оператор добавляет значение справа переменной или свойству слева от него и присваивает результат переменной или свойству слева от него. `+=` Оператор может также использоваться для сцепления `String` выражение справа для `String` переменную или свойство слева и назначить результат в переменную или свойство слева от него.  
  
> [!NOTE]
>  При использовании `+=` оператор не можно определить, произойдет ли объединение строк или сложение операция. Используйте `&=` для объединения оператор во избежание неоднозначности и выполнять код.  
  
 Этот оператор присваивания производит неявное не сужающие преобразования, если среда требует строгой семантики. Дополнительные сведения о подобных преобразованиях см. в разделе [расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md). Дополнительные сведения о строгой и см. в разделе [оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
 Если семантика разрешений разрешены, `+=` оператор неявно выполняет различные строковые и числовые преобразования, которые идентичны выполняемым `+` оператор. Дополнительные сведения об этих преобразований см. в разделе [оператор +](../../../visual-basic/language-reference/operators/addition-operator.md).  
  
## <a name="overloading"></a>Перегрузка  
 `+` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Перегрузка `+` оператор влияет на поведение `+=` оператор. Если ваш код использует `+=` для класса или структуры, перегружающей `+`, убедитесь, что его переопределенное. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `+=` оператор для объединения значения одной переменной с другой. Первая часть использует `+=` с числовыми переменными для добавления одного значения в другой. Вторая часть использует `+=` с `String` переменные для добавления одной строки к другой. В обоих случаях результат присваивается первой переменной.  
  
 [!code-vb[VbVbalrOperators#7](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-assignment-operator_1.vb)]  
  
 [!code-vb[VbVbalrOperators#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-assignment-operator_2.vb)]  
  
 Значение `num1` сейчас 13, а значение `str1` становится «103».  
  
## <a name="see-also"></a>См. также  
 [Оператор +](../../../visual-basic/language-reference/operators/addition-operator.md)  
 [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Операторы объединения](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
