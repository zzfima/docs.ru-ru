---
title: Оператор If (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.IfOperator
- IfOperator
helpviewer_keywords:
- ternary operators [Visual Basic]
- conditional execution
- If expressions [Visual Basic]
- conditional operator [Visual Basic]
- If Operator [Visual Basic]
ms.assetid: dd56c9df-7cd4-442c-9ba6-20c70ee44c8f
ms.openlocfilehash: 192309a7ca728feb300e867bf2340e669e9da16c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="if-operator-visual-basic"></a>Оператор If (Visual Basic)
Использует сокращенные вычисления, в условно возвращает одно из двух значений. `If` Оператор может вызываться с тремя или с двумя аргументами.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
If( [argument1,] argument2, argument3 )  
```  
  
## <a name="if-operator-called-with-three-arguments"></a>Оператор If с тремя аргументами  
 Когда `If` вызывается с тремя аргументами, первый аргумент должен иметь значение, может быть приведен как `Boolean`. Что `Boolean` значение будет определять, какой из двух других аргументов вычисляется и возвращается. Следующий список применяется, только если `If` оператор был вызван с помощью трех аргументов.  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`argument1`|Обязательно. `Boolean`. Определяет, какие другие аргументы для вычисления и возврата.|  
|`argument2`|Обязательно. `Object`. Если вычисленное и возвращаются в `argument1` равен `True`.|  
|`argument3`|Обязательно. `Object`. Если вычисленное и возвращаются в `argument1` равен `False` или если `argument1` — [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` переменной, результатом которого является [ничего не](../../../visual-basic/language-reference/nothing.md).|  
  
 `If` Оператор, который вызывается с тремя аргументами работает подобно `IIf` функции, за исключением того, что он использует сокращенные вычисления. `IIf` Функция всегда вычисляет все три аргументов, тогда как `If` с тремя аргументами вычисляет только два из них. Первый `If` аргумент вычисляется, и результат приводится к `Boolean` значение `True` или `False`. Если значение равно `True`, `argument2` — вычисляется и возвращается его значение, но `argument3` не вычисляется. Если значение `Boolean` выражение `False`, `argument3` — вычисляется и возвращается его значение, но `argument2` не вычисляется. Следующие примеры иллюстрируют использование `If` при использовании три аргумента:  
  
 [!code-vb[VbVbalrOperators#100](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/if-operator_1.vb)]  
  
 В следующем примере показано значение сокращенным вычислением. В примере показано две попытки деления переменной `number` переменной `divisor` только если `divisor` равно нулю. В этом случае должно быть возвращено значение 0, и не должен быть предпринята попытка выполнить деление потому, что приведет к ошибке во время выполнения. Поскольку `If` выражение использует сокращенные вычисления, оно вычисляет второй или третий аргумент, в зависимости от значения первого аргумента. Если первый аргумент имеет значение true, делитель не равна нулю и безопасно вычисления второго аргумента и деление. Если первый аргумент имеет значение false, только третий аргумент вычисляется и возвращается значение 0. Таким образом Если делитель равен 0, не будет предпринята попытка выполнить деление и не приведет к ошибке. Тем не менее поскольку `IIf` не использует сокращенные вычисления, второй аргумент вычисляется, даже в том случае, если первый аргумент имеет значение false. Это приводит к ошибке деления на ноль во время выполнения.  
  
 [!code-vb[VbVbalrOperators#101](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/if-operator_2.vb)]  
  
## <a name="if-operator-called-with-two-arguments"></a>Оператор If с двумя аргументами  
 Первый аргумент `If` можно опустить. Благодаря этому оператор вызываться с использованием только двух аргументов. Следующий список применяется, только если `If` оператор был вызван с двумя аргументами.  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`argument2`|Обязательно. `Object`. Должен быть ссылку или тип, допускающий значение NULL. Вычисляется и возвращается, если оно оценивается как-либо отличного от `Nothing`.|  
|`argument3`|Обязательно. `Object`. Если вычисленное и возвращаются в `argument2` равен `Nothing`.|  
  
 Когда `Boolean` аргумент опущен, первый аргумент должен быть ссылкой или типом nullable. Если первый аргумент принимает значение `Nothing`, возвращается значение второго аргумента. Во всех остальных случаях возвращается значение первого аргумента. В следующем примере показано, как работает это вычисление.  
  
 [!code-vb[VbVbalrOperators#102](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/if-operator_3.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Interaction.IIf%2A>  
 [Типы значений, допускающие значение NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [Nothing](../../../visual-basic/language-reference/nothing.md)
