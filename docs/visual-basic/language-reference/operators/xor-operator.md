---
title: Оператор Xor (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Xor
helpviewer_keywords:
- exclusive OR operator [Visual Basic]
- logical exclusion
- operators [Visual Basic], exclusive or
- exclusion operator [Visual Basic]
- operators [Visual Basic], bitwise
- bitwise operators [Visual Basic], XOR operator
- Xor operator [Visual Basic]
- Xor keyword [Visual Basic]
- bitwise comparison [Visual Basic]
ms.assetid: 036000a9-3934-4e7f-a9d0-a816de3d84a6
ms.openlocfilehash: af6589206232f01b572cd2b965ba1a0f36d462e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527124"
---
# <a name="xor-operator-visual-basic"></a>Оператор Xor (Visual Basic)
Выполняет логическое исключение над двумя `Boolean` выражений или побитовое Вычитание двух числовых выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательный. Любой `Boolean` или числовой переменной. Для логического сравнения `result` является логическое исключение (исключающая логическая дизъюнкция) из двух `Boolean` значения. Для битовых операций: `result` — это числовое значение, представляющее (поразрядной исключающей побитовое дизъюнкции) из двум битовым шаблонам чисел.  
  
 `expression1`  
 Обязательный. Любой `Boolean` или числовое выражение.  
  
 `expression2`  
 Обязательный. Любой `Boolean` или числовое выражение.  
  
## <a name="remarks"></a>Примечания  
 Логическое сравнение `result` — `True` , только если задан только один из `expression1` и `expression2` принимает значение `True`. То есть, только если `expression1` и `expression2` оценки на противоположном `Boolean` значения. В следующей таблице показано как `result` определяется.  
  
|Если `expression1` —|И `expression2` —|Значение `result` —|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  В логическое сравнение `Xor` оператор всегда вычисляет оба выражения, которые могут включать вызовы процедуры. Имеется не сокращенной обработки аналогом `Xor`, так как результат всегда зависит от обоих операндов. Для *сокращенного вычисления* логические операторы, см. в разделе [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) и [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).  
  
 Для битовых операций: `Xor` оператор выполняет побитовое сравнение одинаково расположенных битов в двух числовых выражений и устанавливает значение соответствующего бита в `result` согласно следующей таблице.  
  
|Если бит в `expression1` —|И бит в `expression2` —|Бит в `result` —|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|0|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
>  Поскольку логические и побитовые операторы имеют более низкий приоритет, чем другие арифметические и реляционные операторы, битовые операции следует заключать в круглые скобки, чтобы обеспечить правильное выполнение.  
  
 Например, 5 `Xor` 3 — 6. Чтобы узнать, почему это так, преобразуем 5 и 3 в двоичное представление, 101 и 011. Воспользуйтесь приведенной выше таблице, чтобы определить, что 101 Xor 011-110, являющееся двоичное представление десятичного числа 6.  
  
## <a name="data-types"></a>Типы данных  
 Если операнды состоять из одного `Boolean` выражение и одного числового выражения, Visual Basic преобразуют `Boolean` выражение в числовое значение (-1 для `True` и 0 для `False`) и выполняет побитовую операцию.  
  
 Для `Boolean` имеет тип данных результата сравнения, `Boolean`. Побитовое сравнение, тип данных результата является числовым типом, соответствующим типам данных `expression1` и `expression2`. См. в таблице «Реляционные и побитовое сравнение» в [типы данных из результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="overloading"></a>Перегрузка  
 `Xor` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Xor` оператор для выполнения логического исключения (исключающая логическая дизъюнкция) для двух выражений. В результате `Boolean` значение, которое указывает, находится ли ровно одно из выражений `True`.  
  
 [!code-vb[VbVbalrOperators#40](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xor-operator_1.vb)]  
  
 В предыдущем примере получаются результаты `False`, `True`, и `False`, соответственно.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Xor` оператор для выполнения логического исключения (исключающая логическая дизъюнкция) с отдельными битами двух числовых выражений. Бит в шаблоне результата устанавливается в том случае, если только один из соответствующих бита в операндов имеет значение 1.  
  
 [!code-vb[VbVbalrOperators#41](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xor-operator_2.vb)]  
  
 Предыдущий пример получаются результаты 2, 12 и 14, соответственно.  
  
## <a name="see-also"></a>См. также
- [Логические (побитовые) операторы (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Логические и побитовые операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
