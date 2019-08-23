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
ms.openlocfilehash: 1d11a6d009f6ecfea9fb1a86b00c67b87d5555dc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955843"
---
# <a name="or-operator-visual-basic"></a>Оператор Or (Visual Basic)
Выполняет логическое сложение двух `Boolean` выражений или побитовое сложение двух числовых выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательный. Любое `Boolean` или числовое выражение. Для `Boolean` `Boolean` сравнения —этовключающеелогическоесложениедвухзначений.`result` Для битовых операций `result` — это числовое значение, представляющее включающее побитовое сложение двух числовых битов.  
  
 `expression1`  
 Обязательный. Любое `Boolean` или числовое выражение.  
  
 `expression2`  
 Обязательный. Любое `Boolean` или числовое выражение.  
  
## <a name="remarks"></a>Примечания  
 Для `Boolean` сравнения параметр `result` имеет `False` значение, только если оба `expression1` значения `expression2` и имеют `False`значение. В следующей таблице показано, `result` как определяется.  
  
|Если `expression1` имеет значение|И `expression2` является|Значение `result` равно|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> В сравнении `Or` оператор всегда вычисляет оба выражения, которые могут включать вызовы процедур. `Boolean` [Оператор OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md) выполняет сокращенное *Вычисление*, означающее, что `expression1` если имеет значение `True`, то `expression2` не вычисляется.  
  
 Для побитовых операций `Or` оператор выполняет побитовое сравнение одинаково позиционированных битов в двух числовых выражениях и устанавливает соответствующий бит в `result` соответствии со следующей таблицей.  
  
|Если бит в `expression1` имеет значение|И bit в `expression2` имеет|Бит в `result` имеет значение|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
> Так как логические и побитовые операторы имеют более низкий приоритет, чем другие арифметические и реляционные операторы, все битовые операции должны быть заключены в круглые скобки, чтобы обеспечить точное выполнение.  
  
## <a name="data-types"></a>Типы данных  
 `Boolean` Если операнды состоят из одного выражения и одного числового выражения, Visual Basic `Boolean` преобразует выражение в числовое значение (– 1 для `True` и 0 для `False`) и выполняет побитовую операцию.  
  
 Для сравнения тип данных результата — `Boolean`. `Boolean` Для побитового сравнения тип данных результата является числовым типом, подходящим для типов `expression1` данных и. `expression2` См. таблицу "реляционные и побитовые сравнения" в разделе [типы данных результатов операторов](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="overloading"></a>Перегрузка  
 Оператор можно перегрузить, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры. `Or` Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере `Or` оператор используется для выполнения включающего логического сложения двух выражений. Результатом является `Boolean` значение, которое представляет, является `True`ли одно из двух выражений.  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 В предыдущем примере создаются результаты `True`, `True`и `False`соответственно.  
  
## <a name="example"></a>Пример  
 В следующем примере `Or` оператор используется для выполнения инклюзивного логического сложения по отдельным битам двух числовых выражений. Бит в результирующем шаблоне задается, если один из соответствующих битов операндов имеет значение 1.  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 В предыдущем примере выдается результат 10, 14 и 14 соответственно.  
  
## <a name="see-also"></a>См. также

- [Логические и битовые операторы (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Оператор OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md)
- [Логические и побитовые операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
