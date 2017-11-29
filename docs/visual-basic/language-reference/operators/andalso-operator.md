---
title: "Оператор AndAlso (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.AndAlso
- AndAlso
helpviewer_keywords:
- short-circuiting
- AndAlso operator [Visual Basic]
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], conjunction
- short-circuit evaluation
ms.assetid: bbc15191-b374-495b-9b8f-7b8c2f4388eb
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5f92f4ed226c2923c3d95a7b80db3872b7ac33dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="andalso-operator-visual-basic"></a>Оператор AndAlso (Visual Basic)
Выполняет сокращенное вычисление логического умножения двух выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`result`|Обязательный. Произвольное выражение `Boolean`. В результате `Boolean` результат сравнения двух выражений.|  
|`expression1`|Обязательный. Произвольное выражение `Boolean`.|  
|`expression2`|Обязательный. Произвольное выражение `Boolean`.|  
  
## <a name="remarks"></a>Примечания  
 Логическая операция называется *сокращенного вычисления* Если скомпилированный код может пропустить оценку одного выражения в зависимости от результата другого выражения. Если результат вычисления первого выражения определяет конечный результат операции, нет необходимости для вычисления второго выражения, так как он не может изменить результат. Сокращенные вычисления могут повысить производительность, если пропущенное выражение является сложным или содержит вызовы процедур.  
  
 Если оба выражения `True`, `result` — `True`. В следующей таблице показано, как `result` определяется.  
  
|Если `expression1` является|И `expression2` —|Значение `result` —|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|(не вычисленное)|`False`|  
  
## <a name="data-types"></a>Типы данных  
 `AndAlso` Оператор определен только для [тип данных Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Visual Basic каждый операнд при необходимости преобразуется к `Boolean` и выполняет операцию полностью в `Boolean`. Если назначить результат в числовой тип, Visual Basic преобразует его из `Boolean` к этому типу. Это может привести к непредвиденному поведению. Например `5 AndAlso 12` приводит к `–1` при преобразовании `Integer`.  
  
## <a name="overloading"></a>Перегрузка  
 [И оператор](../../../visual-basic/language-reference/operators/and-operator.md) и [оператор IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md) может быть *перегружены*, что означает, что класс или структура может переопределить их поведение, если операнд имеет тип, класс или структура. Перегрузка `And` и `IsFalse` операторы влияет на поведение `AndAlso` оператор. Если ваш код использует `AndAlso` для класса или структуры, перегружающей `And` и `IsFalse`, убедитесь, что их переопределенное. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `AndAlso` оператор для выполнения логического умножения двух выражений. В результате `Boolean` значение, которое показывает, что объединенное всего выражения имеет значение true. Если первое выражение является `False`, второй не вычисляется.  
  
 [!code-vb[VbVbalrOperators#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_1.vb)]  
  
 В предыдущем примере получаются результаты `True`, `False`, и `False`соответственно. При расчете `secondCheck`, второе выражение не вычисляется, поскольку первый уже `False`. Однако второе выражение вычисляется при расчете `thirdCheck`.  
  
## <a name="example"></a>Пример  
 В следующем примере показан `Function` процедуру, которая выполняет поиск заданного значения среди элементов массива. Если массив пуст или превышает длину массива `While` инструкции не проверяет элементы массива на значение поиска.  
  
 [!code-vb[VbVbalrOperators#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_2.vb)]  
  
## <a name="see-also"></a>См. также  
 [Логические (побитовые) операторы (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Оператор And](../../../visual-basic/language-reference/operators/and-operator.md)  
 [Оператор IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [Логические и побитовые операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
