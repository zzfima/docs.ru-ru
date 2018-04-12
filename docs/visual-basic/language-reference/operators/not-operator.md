---
title: Оператор Not (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Not
helpviewer_keywords:
- Boolean expressions, negating
- operators [Visual Basic], bitwise
- negation operator [Visual Basic]
- inverse bit values in variables [Visual Basic]
- bitwise operators [Visual Basic], NOT operator
- bitwise comparison [Visual Basic]
- Not operator [Visual Basic]
- logical negation
- operators [Visual Basic], negation
ms.assetid: 8f2ea83c-d2ed-480a-a474-3042a1cad9b5
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ac160aef7b7dc8acb8bf0211b403599692f2373c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="not-operator-visual-basic"></a>Оператор Not (Visual Basic)
Выполняет логическое отрицание `Boolean` выражения или побитовое отрицание в числовом выражении.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
result = Not expression  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательный. Любой `Boolean` или числовое выражение.  
  
 `expression`  
 Обязательный. Любой `Boolean` или числовое выражение.  
  
## <a name="remarks"></a>Примечания  
 Для `Boolean` выражения, в следующей таблице показано как `result` определяется.  
  
|Если `expression` является|Значение `result` —|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 Для числовых выражений `Not` оператор инвертирует значения битов числового выражения и задает соответствующий бит в `result` согласно следующей таблице.  
  
|Если бит в `expression` —|Бит в `result` —|  
|-------------------------------|----------------------------|  
|1|0|  
|0|1|  
  
> [!NOTE]
>  Поскольку логические и битовые операторы имеют более низкий приоритет, чем другие арифметических операторов и операторов отношения, побитовые операции следует заключать в круглые скобки, чтобы обеспечить правильное выполнение.  
  
## <a name="data-types"></a>Типы данных  
 Для логического отрицания тип данных результата является `Boolean`. Для поразрядного отрицания, тип данных результата относится так же, как `expression`. Тем не менее если выражение является `Decimal`, в результате `Long`.  
  
## <a name="overloading"></a>Перегрузка  
 `Not` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если его операнд имеет тип этого класса или структуры. Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Not` оператор логического отрицания `Boolean` выражение. В результате `Boolean` значение, представляющее обратное значение выражения.  
  
 [!code-vb[VbVbalrOperators#33](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_1.vb)]  
  
 В предыдущем примере получаются результаты `False` и `True`соответственно.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Not` оператор для выполнения логического отрицания отдельных битов числового выражения. Бит в шаблоне результат присваивается обратное соответствующий бит в шаблоне операнда, включая бит знака.  
  
 [!code-vb[VbVbalrOperators#34](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_2.vb)]  
  
 В предыдущем примере получаются результаты – 11, – 9 и – 7 соответственно.  
  
## <a name="see-also"></a>См. также  
 [Логические (побитовые) операторы (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Логические и побитовые операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
