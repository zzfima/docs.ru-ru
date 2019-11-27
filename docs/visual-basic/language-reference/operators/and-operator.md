---
title: Оператор And
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
ms.openlocfilehash: 78a65843a449bd15d5615710e1685f40d94c37f7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350256"
---
# <a name="and-operator-visual-basic"></a>Оператор And (Visual Basic)
Выполняет логическое умножение двух выражений `Boolean` или побитовое умножение двух числовых выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
result = expression1 And expression2  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательно. Любое `Boolean` или числовое выражение. Для логического сравнения `result` — это логическое умножение двух `Boolean` значений. Для побитовых операций `result` является числовым значением, представляющим побитовое умножение двух числовых битов.  
  
 `expression1`  
 Обязательно. Любое `Boolean` или числовое выражение.  
  
 `expression2`  
 Обязательно. Любое `Boolean` или числовое выражение.  
  
## <a name="remarks"></a>Заметки  
 Для логического сравнения `result` `True` только в том случае, если оба `expression1` и `expression2` имеют значение `True`. В следующей таблице показано, как определяется `result`.  
  
|Если `expression1`|И `expression2`|Значение `result` равно|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> При логическом сравнении оператор `And` всегда вычисляет оба выражения, которые могут включать вызовы процедур. [Оператор AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md) выполняет *сокращенное вычисление*, что означает, что если `expression1` `False`, то `expression2` не вычисляется.  
  
 При применении к числовым значениям оператор `And` выполняет побитовое сравнение одинаково позиционированных битов в двух числовых выражениях и устанавливает соответствующий бит в `result` в соответствии со следующей таблицей.  
  
|Если бит в `expression1` имеет значение|И бит в `expression2` —|Бит в `result`|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|0|  
|0|1|0|  
|0|0|0|  
  
> [!NOTE]
> Так как логические и побитовые операторы имеют более низкий приоритет, чем другие арифметические и реляционные операторы, все битовые операции должны быть заключены в круглые скобки для обеспечения точных результатов.  
  
## <a name="data-types"></a>Типы данных  
 Если операнды состоят из одного `Boolean` выражения и одного числового выражения, Visual Basic преобразует выражение `Boolean` в числовое значение (– 1 для `True` и 0 для `False`) и выполняет побитовую операцию.  
  
 Для логического сравнения тип данных результата `Boolean`. Для побитового сравнения тип данных результата является числовым типом, подходящим для типов данных `expression1` и `expression2`. См. таблицу "реляционные и побитовые сравнения" в разделе [типы данных результатов операторов](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
> [!NOTE]
> Оператор `And` может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры. Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `And` используется для выполнения логического умножения двух выражений. Результатом является `Boolean` значение, которое показывает, `True`ли оба выражения.  
  
 [!code-vb[VbVbalrOperators#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#22)]  
  
 В предыдущем примере создаются результаты `True` и `False`соответственно.  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `And` используется для выполнения логического умножения отдельных битов двух числовых выражений. Бит в результирующем шаблоне задается, если для соответствующих битов в операндах задано значение 1.  
  
 [!code-vb[VbVbalrOperators#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#23)]  
  
 В предыдущем примере выдается результат 8, 2 и 0 соответственно.  
  
## <a name="see-also"></a>См. также

- [Логические и битовые операторы (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Оператор AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md)
- [Логические и побитовые операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
