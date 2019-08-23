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
ms.openlocfilehash: 59f27b92996e1506be5967de88c22fb88e06f5b7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965846"
---
# <a name="xor-operator-visual-basic"></a>Оператор Xor (Visual Basic)
Выполняет логическое исключение для двух `Boolean` выражений или побитовое исключение для двух числовых выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательный. Любая `Boolean` или числовая переменная. Для логического сравнения `result` — это логическое исключение (исключающее логическое сложение) двух `Boolean` значений. Для битовых операций `result` — это числовое значение, представляющее побитовое исключение (исключающее побитовое сложение) двух числовых битов.  
  
 `expression1`  
 Обязательный. Любое `Boolean` или числовое выражение.  
  
 `expression2`  
 Обязательный. Любое `Boolean` или числовое выражение.  
  
## <a name="remarks"></a>Примечания  
 Для логического сравнения `result` параметр имеет `True` значение, только `expression2` если в `True`точности один `expression1` из значений равен. То есть, если и только если `expression1` и `expression2` имеют противоположные `Boolean` значения. В следующей таблице показано, `result` как определяется.  
  
|Если `expression1` имеет значение|И `expression2` является|Значение `result` равно|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> При логическом сравнении `Xor` оператор всегда вычисляет оба выражения, которые могут включать вызовы процедур. Не существует аналога `Xor`сокращенного выражения, поскольку результат всегда зависит от обоих операндов. Дополнительные операторы для сокращенного вычисления логических операторов см. в разделе [оператор AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md) и [оператор OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md).  
  
 Для побитовых операций `Xor` оператор выполняет побитовое сравнение одинаково позиционированных битов в двух числовых выражениях и устанавливает соответствующий бит в `result` соответствии со следующей таблицей.  
  
|Если бит в `expression1` имеет значение|И bit в `expression2` имеет|Бит в `result` имеет значение|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|0|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
> Так как логические и побитовые операторы имеют более низкий приоритет, чем другие арифметические и реляционные операторы, все битовые операции должны быть заключены в круглые скобки, чтобы обеспечить точное выполнение.  
  
 Например, 5 `Xor` 3 — 6. Чтобы узнать, почему это так, преобразуйте значения 5 и 3 в двоичные представления, 101 и 011. Затем используйте предыдущую таблицу, чтобы определить, что 101 Xor 011 имеет значение 110, которое является двоичным представлением десятичного числа 6.  
  
## <a name="data-types"></a>Типы данных  
 `Boolean` Если операнды состоят из одного выражения и одного числового выражения, Visual Basic `Boolean` преобразует выражение в числовое значение (– 1 для `True` и 0 для `False`) и выполняет побитовую операцию.  
  
 Для сравнения тип данных результата — `Boolean`. `Boolean` Для побитового сравнения тип данных результата является числовым типом, подходящим для типов `expression1` данных и. `expression2` См. таблицу "реляционные и побитовые сравнения" в разделе [типы данных результатов операторов](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="overloading"></a>Перегрузка  
 Оператор можно перегрузить, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры. `Xor` Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере `Xor` оператор используется для выполнения логического исключения (исключающее логическое сложение) в двух выражениях. Результатом является `Boolean` значение, указывающее, имеет `True`ли только одно из выражений.  
  
 [!code-vb[VbVbalrOperators#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#40)]  
  
 В предыдущем примере создаются результаты `False`, `True`и `False`соответственно.  
  
## <a name="example"></a>Пример  
 В следующем примере `Xor` оператор используется для выполнения логического исключения (исключающее логическое сложение) для отдельных битов двух числовых выражений. Бит в результирующем шаблоне устанавливается, если только один из соответствующих битов операндов имеет значение 1.  
  
 [!code-vb[VbVbalrOperators#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#41)]  
  
 В предыдущем примере выдается результат 2, 12 и 14 соответственно.  
  
## <a name="see-also"></a>См. также

- [Логические и битовые операторы (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Логические и побитовые операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
