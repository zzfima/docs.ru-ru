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
ms.openlocfilehash: d82018a3018e2cf4362b9904ed127c20f56f6f0c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701269"
---
# <a name="xor-operator-visual-basic"></a>Оператор Xor (Visual Basic)
Выполняет логическое исключение в двух выражениях `Boolean` или побитовое исключение для двух числовых выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательный. Любая переменная `Boolean` или numeric. Для логического сравнения `result` является логическим исключением (исключающее логическое сложение) двух значений `Boolean`. Для побитовых операций `result` — это числовое значение, представляющее побитовое исключение (исключающее побитовое сложение) двух числовых битов.  
  
 `expression1`  
 Обязательный. Любое `Boolean` или числовое выражение.  
  
 `expression2`  
 Обязательный. Любое `Boolean` или числовое выражение.  
  
## <a name="remarks"></a>Примечания  
 Для логического сравнения `result` — `True`, только если в точности один из `expression1` и `expression2` равен `True`. То есть только в случае, если `expression1` и `expression2` имеют противоположные значения `Boolean`. В следующей таблице показано, как определяется `result`.  
  
|Если `expression1` имеет значение|И `expression2` является|Значение `result` равно|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> При логическом сравнении оператор `Xor` всегда вычисляет оба выражения, которые могут включать вызовы процедур. Нет аналогового аналога для `Xor`, так как результат всегда зависит от обоих операндов. Дополнительные операторы для *сокращенного* вычисления логических операторов см. в разделе [оператор AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md) и [оператор OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md).  
  
 Для побитовых операций оператор `Xor` выполняет побитовое сравнение одинаково позиционированных битов в двух числовых выражениях и устанавливает соответствующий бит в `result` в соответствии со следующей таблицей.  
  
|Если бит в `expression1` равен|И бит в `expression2` —|Бит в `result` является|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|0|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
> Так как логические и побитовые операторы имеют более низкий приоритет, чем другие арифметические и реляционные операторы, все битовые операции должны быть заключены в круглые скобки, чтобы обеспечить точное выполнение.  
  
 Например, 5 `Xor` 3 — 6. Чтобы узнать, почему это так, преобразуйте значения 5 и 3 в двоичные представления, 101 и 011. Затем используйте предыдущую таблицу, чтобы определить, что 101 Xor 011 имеет значение 110, которое является двоичным представлением десятичного числа 6.  
  
## <a name="data-types"></a>Типы данных  
 Если операнды состоят из одного выражения `Boolean` и одного числового выражения, Visual Basic преобразует выражение `Boolean` в числовое значение (– 1 для `True` и 0 для `False`) и выполняет побитовую операцию.  
  
 Для сравнения `Boolean` тип данных результата `Boolean`. Для побитового сравнения тип данных результата является числовым типом, подходящим для типов данных `expression1` и `expression2`. См. таблицу "реляционные и побитовые сравнения" в разделе [типы данных результатов операторов](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="overloading"></a>Перегрузка  
 Оператор `Xor` можно *перегрузить*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры. Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `Xor` используется для выполнения логического исключения (исключающее логическое сложение) в двух выражениях. Результатом является значение `Boolean`, которое показывает, является ли ровно одно из выражений `True`.  
  
 [!code-vb[VbVbalrOperators#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#40)]  
  
 В предыдущем примере получены результаты `False`, `True` и `False` соответственно.  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `Xor` используется для выполнения логического исключения (исключающее логическое сложение) для отдельных битов двух числовых выражений. Бит в результирующем шаблоне устанавливается, если только один из соответствующих битов операндов имеет значение 1.  
  
 [!code-vb[VbVbalrOperators#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#41)]  
  
 В предыдущем примере выдается результат 2, 12 и 14 соответственно.  
  
## <a name="see-also"></a>См. также

- [Логические и битовые операторы (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Логические и побитовые операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
