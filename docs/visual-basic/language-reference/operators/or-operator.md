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
ms.openlocfilehash: 03decb4ad32e8ff2c03e3b64a272bce779282973
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701238"
---
# <a name="or-operator-visual-basic"></a>Оператор Or (Visual Basic)
Выполняет логическое сложение двух выражений `Boolean` или побитовое сложение двух числовых выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательный. Любое `Boolean` или числовое выражение. Для сравнения `Boolean` `result` является инклюзивным логическим соединением двух значений `Boolean`. Для побитовых операций `result` — это числовое значение, представляющее включающее побитовое сложение двух числовых битов.  
  
 `expression1`  
 Обязательный. Любое `Boolean` или числовое выражение.  
  
 `expression2`  
 Обязательный. Любое `Boolean` или числовое выражение.  
  
## <a name="remarks"></a>Примечания  
 Для сравнения `Boolean` `result` — `False`, только если оба `expression1` и `expression2` равны `False`. В следующей таблице показано, как определяется `result`.  
  
|Если `expression1` имеет значение|И `expression2` является|Значение `result` равно|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> В сравнении `Boolean` оператор `Or` всегда вычисляет оба выражения, которые могут включать вызовы процедур. [Оператор OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md) выполняет *сокращенное вычисление*, что означает, что если `expression1` имеет `True`, то `expression2` не вычисляется.  
  
 Для побитовых операций оператор `Or` выполняет побитовое сравнение одинаково позиционированных битов в двух числовых выражениях и устанавливает соответствующий бит в `result` в соответствии со следующей таблицей.  
  
|Если бит в `expression1` равен|И бит в `expression2` —|Бит в `result` является|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
> Так как логические и побитовые операторы имеют более низкий приоритет, чем другие арифметические и реляционные операторы, все битовые операции должны быть заключены в круглые скобки, чтобы обеспечить точное выполнение.  
  
## <a name="data-types"></a>Типы данных  
 Если операнды состоят из одного выражения `Boolean` и одного числового выражения, Visual Basic преобразует выражение `Boolean` в числовое значение (– 1 для `True` и 0 для `False`) и выполняет побитовую операцию.  
  
 Для сравнения `Boolean` тип данных результата `Boolean`. Для побитового сравнения тип данных результата является числовым типом, подходящим для типов данных `expression1` и `expression2`. См. таблицу "реляционные и побитовые сравнения" в разделе [типы данных результатов операторов](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="overloading"></a>Перегрузка  
 Оператор `Or` можно *перегрузить*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры. Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `Or` используется для выполнения включающего логического сложения двух выражений. Результатом является значение `Boolean`, которое показывает, является ли одно из двух выражений `True`.  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 В предыдущем примере создаются результаты `True`, `True` и `False` соответственно.  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `Or` используется для выполнения инклюзивного логического сложения по отдельным битам двух числовых выражений. Бит в результирующем шаблоне задается, если один из соответствующих битов операндов имеет значение 1.  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 В предыдущем примере выдается результат 10, 14 и 14 соответственно.  
  
## <a name="see-also"></a>См. также

- [Логические и битовые операторы (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Оператор OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md)
- [Логические и побитовые операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
