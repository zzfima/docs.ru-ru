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
ms.openlocfilehash: a1802d3a7018b1b6190ff5601eba055e16e62371
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913168"
---
# <a name="and-operator-visual-basic"></a>Оператор And (Visual Basic)
Выполняет логическое умножение двух `Boolean` выражений или побитовое умножение двух числовых выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
result = expression1 And expression2  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательный. Любое `Boolean` или числовое выражение. Для логического сравнения `result` — это логическое умножение двух `Boolean` значений. Для битовых операций `result` — это числовое значение, представляющее побитовое умножение двух числовых битов.  
  
 `expression1`  
 Обязательный. Любое `Boolean` или числовое выражение.  
  
 `expression2`  
 Обязательный. Любое `Boolean` или числовое выражение.  
  
## <a name="remarks"></a>Примечания  
 `result` Для логического сравнения параметр имеет `True` значение, только если оба `expression1` значения `expression2` и имеют `True`значение. В следующей таблице показано, `result` как определяется.  
  
|Если `expression1` имеет значение|И `expression2` является|Значение `result` равно|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> При логическом сравнении `And` оператор всегда вычисляет оба выражения, которые могут включать вызовы процедур. [Оператор AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md) выполняет *сокращенное вычисление*, означающее, что если `expression1` имеет `False`значение, `expression2` то не вычисляется.  
  
 При применении к числовым значениям `And` оператор выполняет побитовое сравнение одинаково позиционированных битов в двух числовых выражениях и устанавливает соответствующий бит в `result` соответствии со следующей таблицей.  
  
|Если бит в `expression1` имеет значение|И bit в `expression2` имеет|Бит в `result` имеет значение|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|0|  
|0|1|0|  
|0|0|0|  
  
> [!NOTE]
> Так как логические и побитовые операторы имеют более низкий приоритет, чем другие арифметические и реляционные операторы, все битовые операции должны быть заключены в круглые скобки для обеспечения точных результатов.  
  
## <a name="data-types"></a>Типы данных  
 `Boolean` Если операнды состоят из одного выражения и одного числового выражения, Visual Basic `Boolean` преобразует выражение в числовое значение (– 1 для `True` и 0 для `False`) и выполняет побитовую операцию.  
  
 Для логического сравнения тип данных результата — `Boolean`. Для побитового сравнения тип данных результата является числовым типом, подходящим для типов `expression1` данных и. `expression2` См. таблицу "реляционные и побитовые сравнения" в разделе [типы данных результатов операторов](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
> [!NOTE]
> Оператор можно перегрузить, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры. `And` Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере `And` оператор используется для выполнения логического умножения двух выражений. Результатом является `Boolean` значение, которое показывает, равны `True`ли оба выражения.  
  
 [!code-vb[VbVbalrOperators#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#22)]  
  
 В предыдущем примере создаются результаты `True` и `False`соответственно.  
  
## <a name="example"></a>Пример  
 В следующем примере `And` оператор используется для выполнения логического умножения отдельных битов двух числовых выражений. Бит в результирующем шаблоне задается, если для соответствующих битов в операндах задано значение 1.  
  
 [!code-vb[VbVbalrOperators#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#23)]  
  
 В предыдущем примере выдается результат 8, 2 и 0 соответственно.  
  
## <a name="see-also"></a>См. также

- [Логические и битовые операторы (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Оператор AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md)
- [Логические и побитовые операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
