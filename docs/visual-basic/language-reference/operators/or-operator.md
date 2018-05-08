---
title: Оператор Or (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Or
helpviewer_keywords:
- Or operator [Visual Basic]
- operators [Visual Basic], bitwise
- inclusive Or operator [Visual Basic]
- bitwise operators [Visual Basic], OR operator
- Or keyword [Visual Basic]
- operators [Visual Basic], inclusive or
- operators [Visual Basic], disjunction
- bitwise comparison [Visual Basic]
- logical disjunction
- disjunction operator [Visual Basic]
ms.assetid: 41ed6905-bf3d-468a-9e3b-03c10d461891
ms.openlocfilehash: 9e02f619a81ee3c15321dfd44963c1a7d29843ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="or-operator-visual-basic"></a>Оператор Or (Visual Basic)
Выполняет логическое сложение двух `Boolean` выражений или побитовое логическое сложение двух числовых выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательно. Любой `Boolean` или числовое выражение. Для `Boolean` сравнения, `result` является включающее логическое сложение двух `Boolean` значения. Для битовых операций `result` — это числовое значение, представляющее включающую побитовую дизъюнкцию двух числовых битовых шаблонов.  
  
 `expression1`  
 Обязательно. Любой `Boolean` или числовое выражение.  
  
 `expression2`  
 Обязательно. Любой `Boolean` или числовое выражение.  
  
## <a name="remarks"></a>Примечания  
 Для `Boolean` сравнения, `result` — `False` Если и только если оба `expression1` и `expression2` равен `False`. В следующей таблице показано, как `result` определяется.  
  
|Если `expression1` является|И `expression2` —|Значение `result` —|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  В `Boolean` сравнения, `Or` оператор всегда вычисляет оба выражения, которые могут включать вызовы процедур. [Оператор OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md) выполняет *сокращенного вычисления*, т.е. Если `expression1` — `True`, затем `expression2` не вычисляется.  
  
 Для битовых операций `Or` оператор выполняет побитовое сравнение одинаково расположенных битов в двух числовых выражений и устанавливает значение соответствующего бита в `result` согласно следующей таблице.  
  
|Если бит в `expression1` —|И бита `expression2` —|Бит в `result` —|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
>  Поскольку логические и битовые операторы имеют более низкий приоритет, чем другие арифметических операторов и операторов отношения, побитовые операции следует заключать в круглые скобки, чтобы обеспечить правильное выполнение.  
  
## <a name="data-types"></a>Типы данных  
 Если операнды состоят из одного `Boolean` выражение и одного числового выражения, Visual Basic преобразует `Boolean` выражение в числовое значение (-1 для `True` и 0 для `False`) и выполняет побитовую операцию.  
  
 Для `Boolean` сравнения, тип данных результата является `Boolean`. Поразрядное сравнение, тип данных результата является числовым типом, соответствующим для типов данных `expression1` и `expression2`. См. в таблице «Реляционных и Побитовый оператор сравнения» [типы данных из результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="overloading"></a>Перегрузка  
 `Or` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Or` оператор для выполнения логическое сложение двух выражений. В результате `Boolean` значение, представляющее ли два выражения являются `True`.  
  
 [!code-vb[VbVbalrOperators#35](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_1.vb)]  
  
 В предыдущем примере получаются результаты `True`, `True`, и `False`соответственно.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Or` оператор, чтобы выполнить включающее логическое сложение отдельных битов двух числовых выражений. Бит в шаблоне результата устанавливается в том случае, если любой из соответствующих бита в операндах равен 1.  
  
 [!code-vb[VbVbalrOperators#36](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_2.vb)]  
  
 В предыдущем примере получаются результаты 10, 14 и 14 соответственно.  
  
## <a name="see-also"></a>См. также  
 [Логические (побитовые) операторы (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Оператор OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md)  
 [Логические и побитовые операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
