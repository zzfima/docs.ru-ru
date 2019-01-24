---
title: Оператор OrElse (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- OrElse
- vb.OrElse
helpviewer_keywords:
- short-circuiting
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], disjunction
- short-circuit evaluation
- OrElse operator [Visual Basic]
ms.assetid: 253803d8-05b0-47d7-b213-abd222847779
ms.openlocfilehash: 70bbfef54d3f716e0e7463a39ee15e8480066695
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603018"
---
# <a name="orelse-operator-visual-basic"></a>Оператор OrElse (Visual Basic)
Выполняет сокращенное вычисление логического сложения двух выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательный. Произвольное выражение `Boolean` .  
  
 `expression1`  
 Обязательный. Произвольное выражение `Boolean` .  
  
 `expression2`  
 Обязательный. Произвольное выражение `Boolean` .  
  
## <a name="remarks"></a>Примечания  
 Логическая операция называется *сокращенного вычисления* Если скомпилированный код может пропустить вычисления одного выражения в зависимости от результата другого выражения. Если результат вычисления первого выражения определяет конечный результат операции, нет необходимости для вычисления второго выражения, так как он не может изменить результат. Сокращенное вычисление может повысить производительность, если пропущенное выражение является сложным или содержит вызовы процедур.  
  
 Если один или оба выражения `True`, `result` является `True`. В следующей таблице показано как `result` определяется.  
  
|Если `expression1` —|И `expression2` —|Значение `result` —|  
|-------------------------|--------------------------|------------------------------|  
|`True`|(не вычисленное)|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a>Типы данных  
 `OrElse` Оператор определен только для [логический тип данных](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Visual Basic преобразует каждый операнд при необходимости `Boolean` и выполняет операцию полностью в `Boolean`. Если результат назначается числовой тип, Visual Basic преобразует его из `Boolean` к этому типу. Это может привести к непредвиденному поведению. Например `5 OrElse 12` приводит `–1` при преобразовании `Integer`.  
  
## <a name="overloading"></a>Перегрузка  
 [Или оператор](../../../visual-basic/language-reference/operators/or-operator.md) и [Оператор IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md) может быть *перегружены*, что означает, что класс или структура может переопределить их поведение, если операнд имеет тип этого класса или структуры. Перегрузка `Or` и `IsTrue` операторы влияет на поведение `OrElse` оператор. Если код использует `OrElse` для класса или структуры, перегружающей `Or` и `IsTrue`, убедитесь, что их переопределенное. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `OrElse` оператор для выполнения логического сложения двух выражений. В результате `Boolean` значение, представляющее ли одно из выражений имеет значение true. Если первое выражение является `True`, второй не вычисляется.  
  
 [!code-vb[VbVbalrOperators#37](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/orelse-operator_1.vb)]  
  
 В предыдущем примере получался результат `True`, `True`, и `False` соответственно. В расчет `firstCheck`, второе выражение не вычисляется, так как первый уже `True`. Однако второе выражение оценивается в расчете `secondCheck`.  
  
## <a name="example"></a>Пример  
 В следующем примере показан `If`... `Then` инструкции, содержащей два вызова процедуры. Если первый вызов возвращает `True`, вторая процедура не вызывается. Это может привести к непредвиденным результатам, если вторая процедура выполняет важные задачи, которые всегда должны выполняться при запуске этот раздел кода.  
  
 [!code-vb[VbVbalrOperators#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/orelse-operator_2.vb)]  
  
## <a name="see-also"></a>См. также
- [Логические (побитовые) операторы (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Оператор Or](../../../visual-basic/language-reference/operators/or-operator.md)
- [Оператор IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [Логические и побитовые операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
