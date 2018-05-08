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
ms.openlocfilehash: 34d317da5d85127e371c2df7229e0f0873972f50
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="xor-operator-visual-basic"></a>Оператор Xor (Visual Basic)
Выполняет логическое исключение над двумя `Boolean` выражений или побитовое Вычитание двух числовых выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательно. Любой `Boolean` или числовой переменной. Для логического сравнения `result` является логическим исключением (исключающая логическая дизъюнкция) из двух `Boolean` значения. Для битовых операций `result` является числовым значением, представляющим побитовое исключение (исключающая Побитовая дизъюнкция) из двух числовых битовых шаблонов.  
  
 `expression1`  
 Обязательно. Любой `Boolean` или числовое выражение.  
  
 `expression2`  
 Обязательно. Любой `Boolean` или числовое выражение.  
  
## <a name="remarks"></a>Примечания  
 Логическое сравнение `result` — `True` , только если один из `expression1` и `expression2` равен `True`. То есть, только если `expression1` и `expression2` оценки в обратном `Boolean` значения. В следующей таблице показано, как `result` определяется.  
  
|Если `expression1` является|И `expression2` —|Значение `result` —|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  В логическом сравнении `Xor` оператор всегда вычисляет оба выражения, которые могут включать вызовы процедур. Нет не сокращенной обработки аналогом `Xor`, поскольку результат всегда зависит от обоих операндов. Для *сокращенного вычисления* логические операторы в разделе [оператор AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md) и [оператор OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md).  
  
 Для битовых операций `Xor` оператор выполняет побитовое сравнение одинаково расположенных битов в двух числовых выражений и устанавливает значение соответствующего бита в `result` согласно следующей таблице.  
  
|Если бит в `expression1` —|И бита `expression2` —|Бит в `result` —|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|0|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
>  Поскольку логические и битовые операторы имеют более низкий приоритет, чем другие арифметических операторов и операторов отношения, побитовые операции следует заключать в круглые скобки, чтобы обеспечить правильное выполнение.  
  
 Например, 5 `Xor` 3-6. Чтобы убедиться в этом, преобразуйте 5 и 3 в двоичное представление, 101 и 011. Чтобы определить, что 101 Xor 011 110, который является двоичным представлением десятичного числа 6, воспользуйтесь приведенной выше таблице.  
  
## <a name="data-types"></a>Типы данных  
 Если операнды состоят из одного `Boolean` выражение и одного числового выражения, Visual Basic преобразует `Boolean` выражение в числовое значение (-1 для `True` и 0 для `False`) и выполняет побитовую операцию.  
  
 Для `Boolean` сравнения, тип данных результата является `Boolean`. Поразрядное сравнение, тип данных результата является числовым типом, соответствующим для типов данных `expression1` и `expression2`. См. в таблице «Реляционных и Побитовый оператор сравнения» [типы данных из результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="overloading"></a>Перегрузка  
 `Xor` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Xor` оператор для выполнения логического исключения (исключающая логическая дизъюнкция) для двух выражений. В результате `Boolean` значение, которое указывает, находится ли ровно одно из выражений `True`.  
  
 [!code-vb[VbVbalrOperators#40](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xor-operator_1.vb)]  
  
 В предыдущем примере получаются результаты `False`, `True`, и `False`соответственно.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Xor` оператор для выполнения логического исключения (исключающая логическая дизъюнкция) для отдельных битов двух числовых выражений. Бит в шаблоне результата устанавливается в том случае, если только один из соответствующих битов в операндах равен 1.  
  
 [!code-vb[VbVbalrOperators#41](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xor-operator_2.vb)]  
  
 В предыдущем примере получаются результаты 2, 12 и 14 соответственно.  
  
## <a name="see-also"></a>См. также  
 [Логические (побитовые) операторы (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Логические и побитовые операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
