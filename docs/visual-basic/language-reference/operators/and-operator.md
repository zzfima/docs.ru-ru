---
title: Оператор And (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 83e1f9df11152f88ef0db24a794026d6f5888a2e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="and-operator-visual-basic"></a>Оператор And (Visual Basic)
Выполняет логическое умножение двух `Boolean` выражений или побитовое логическое умножение двух числовых выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
result = expression1 And expression2  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательный. Любой `Boolean` или числовое выражение. Для логического сравнения `result` — логическое умножение двух `Boolean` значения. Для битовых операций `result` — это числовое значение, представляющее побитовое логическое умножение двух числовых битовых шаблонов.  
  
 `expression1`  
 Обязательный. Любой `Boolean` или числовое выражение.  
  
 `expression2`  
 Обязательный. Любой `Boolean` или числовое выражение.  
  
## <a name="remarks"></a>Примечания  
 Логическое сравнение `result` — `True` Если и только если оба `expression1` и `expression2` равен `True`. В следующей таблице показано, как `result` определяется.  
  
|Если `expression1` является|И `expression2` —|Значение `result` —|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  В логическом сравнении `And` оператор всегда вычисляет оба выражения, которые могут включать вызовы процедур. [Оператор AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md) выполняет *сокращенного вычисления*, т.е. Если `expression1` — `False`, затем `expression2` не вычисляется.  
  
 При применении к числовым значениям, `And` оператор выполняет побитовое сравнение одинаково расположенных битов в двух числовых выражений и устанавливает значение соответствующего бита в `result` согласно следующей таблице.  
  
|Если бит в `expression1` —|И бита `expression2` —|Бит в `result` —|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|0|  
|0|1|0|  
|0|0|0|  
  
> [!NOTE]
>  Поскольку логические и битовые операторы имеют более низкий приоритет, чем другие арифметических операторов и операторов отношения, побитовые операции следует заключать в круглые скобки, чтобы обеспечить точность результатов.  
  
## <a name="data-types"></a>Типы данных  
 Если операнды состоят из одного `Boolean` выражение и одного числового выражения, Visual Basic преобразует `Boolean` выражение в числовое значение (-1 для `True` и 0 для `False`) и выполняет побитовую операцию.  
  
 Для логического сравнения, тип данных результата является `Boolean`. Поразрядное сравнение, тип данных результата является числовым типом, соответствующим для типов данных `expression1` и `expression2`. См. в таблице «Реляционных и Побитовый оператор сравнения» [типы данных из результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
> [!NOTE]
>  `And` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `And` оператор для выполнения логического умножения двух выражений. В результате `Boolean` значение, которое показывает, что оба выражения являются `True`.  
  
 [!code-vb[VbVbalrOperators#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-operator_1.vb)]  
  
 В предыдущем примере получаются результаты `True` и `False`соответственно.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `And` оператор для выполнения логического умножения отдельных битов двух числовых выражений. Бит в шаблоне результата устанавливается в том случае, если соответствующие биты в операндах устанавливаются в 1.  
  
 [!code-vb[VbVbalrOperators#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-operator_2.vb)]  
  
 В предыдущем примере получаются результаты 8, 2 и 0, соответственно.  
  
## <a name="see-also"></a>См. также  
 [Логические (побитовые) операторы (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Оператор AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md)  
 [Логические и побитовые операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
