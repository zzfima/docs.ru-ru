---
title: Оператор And (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.And
helpviewer_keywords:
- operators [Visual Basic], bitwise
- logical conjunction
- bitwise AND operator [Visual Basic]
- conjunction operator [Visual Basic]
- And operator [Visual Basic]
- bitwise operators [Visual Basic], AND operator
- operators [Visual Basic], conjunction
- bitwise comparison [Visual Basic]
ms.assetid: 2ea711f3-439a-4c7c-9e3a-1ffe3b0d6046
ms.openlocfilehash: 2cdc272c07f3b30f61716f0c5ae72f0655c3f46b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597324"
---
# <a name="and-operator-visual-basic"></a>Оператор And (Visual Basic)
Выполняет логическое умножение двух `Boolean` выражений или побитовое логическое умножение двух числовых выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
result = expression1 And expression2  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательный. Любой `Boolean` или числовое выражение. Для логического сравнения `result` — логическое умножение двух `Boolean` значения. Для битовых операций: `result` числовое значение, представляющее побитовое логическое умножение двум битовым шаблонам чисел.  
  
 `expression1`  
 Обязательный. Любой `Boolean` или числовое выражение.  
  
 `expression2`  
 Обязательный. Любой `Boolean` или числовое выражение.  
  
## <a name="remarks"></a>Примечания  
 Для логического сравнения `result` — `True` Если и только если оба `expression1` и `expression2` иметь `True`. В следующей таблице показано как `result` определяется.  
  
|Если `expression1` —|И `expression2` —|Значение `result` —|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  В логическое сравнение `And` оператор всегда вычисляет оба выражения, которые могут включать вызовы процедуры. [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) выполняет *сокращенного вычисления*, т.е. Если `expression1` — `False`, затем `expression2` не вычисляется.  
  
 При применении в числовые значения `And` оператор выполняет побитовое сравнение одинаково расположенных битов в двух числовых выражений и устанавливает значение соответствующего бита в `result` согласно следующей таблице.  
  
|Если бит в `expression1` —|И бит в `expression2` —|Бит в `result` —|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|0|  
|0|1|0|  
|0|0|0|  
  
> [!NOTE]
>  Поскольку логические и побитовые операторы имеют более низкий приоритет, чем другие арифметические и реляционные операторы, битовые операции следует заключать в круглые скобки, чтобы обеспечить точные результаты.  
  
## <a name="data-types"></a>Типы данных  
 Если операнды состоять из одного `Boolean` выражение и одного числового выражения, Visual Basic преобразуют `Boolean` выражение в числовое значение (-1 для `True` и 0 для `False`) и выполняет побитовую операцию.  
  
 Для логического сравнения, тип данных результата — `Boolean`. Побитовое сравнение, тип данных результата является числовым типом, соответствующим типам данных `expression1` и `expression2`. См. в таблице «Реляционные и побитовое сравнение» в [типы данных из результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
> [!NOTE]
>  `And` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `And` оператору выполнять логическое умножение двух выражений. В результате `Boolean` значение, которое показывает, что оба выражения являются `True`.  
  
 [!code-vb[VbVbalrOperators#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-operator_1.vb)]  
  
 В предыдущем примере получался результат `True` и `False`, соответственно.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `And` оператор для выполнения логического умножения отдельных битов двух числовых выражений. Бит в шаблоне результата устанавливается в том случае, если соответствующие биты в операндах являются равными 1.  
  
 [!code-vb[VbVbalrOperators#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-operator_2.vb)]  
  
 В предыдущем примере получался результаты 8, 2 и 0, соответственно.  
  
## <a name="see-also"></a>См. также
- [Логические (побитовые) операторы (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Оператор AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md)
- [Логические и побитовые операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
