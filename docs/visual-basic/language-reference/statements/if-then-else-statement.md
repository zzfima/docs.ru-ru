---
title: Оператор If...Then...Else (Visual Basic)
ms.date: 04/16/2018
f1_keywords:
- vb.ElseIf
- vb.Then
- vb.If
- vb.EndIf
helpviewer_keywords:
- ElseIf statement [Visual Basic], If...Then...Else
- Then statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], branching
- execution [Visual Basic], conditional
- TypeOf...Is expression, and If...Then...Else statements
- If...Then...Else statements
- If statement [Visual Basic], If...Then...Else
- If statement [Visual Basic]
- Is operator [Visual Basic], in If...Then...Else statements
- If Operator [Visual Basic]
- branching [Visual Basic], conditional
- If function [Visual Basic], and If...Then...Else statements
- Else statement [Visual Basic]
ms.assetid: 790068a2-1307-4e28-8a72-be5ebda099e9
ms.openlocfilehash: 08d51326ee0c9f91eec02467ebcb116354b5033f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ifthenelse-statement-visual-basic"></a>Оператор If...Then...Else (Visual Basic)
Выполняет ту или иную группу операторов в зависимости от значения выражения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
' Multiline syntax:  
If condition [ Then ]  
    [ statements ]  
[ ElseIf elseifcondition [ Then ]  
    [ elseifstatements ] ]  
[ Else  
    [ elsestatements ] ]  
End If  
  
' Single-line syntax:  
If condition Then [ statements ] [ Else [ elsestatements ] ]  
```  

## <a name="quick-links-to-example-code"></a>Быстрые ссылки на пример кода

Здесь приведено несколько примеров, иллюстрирующих использование `If`... `Then`... `Else` инструкции:

* [Пример синтаксиса многострочный](#multi-line)
* [Пример вложенной синтаксиса](#nested)
* [Пример синтаксиса для одной строки](#single-line)

## <a name="parts"></a>Части  
 `condition`  
 Обязательно. Выражение. Должны иметь `True` или `False`, или тип данных, который неявно преобразуется в `Boolean`.  
  
 Если выражение является [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` переменной, результатом которого является [ничего](../../../visual-basic/language-reference/nothing.md), условие рассматривается как выражение `False` и `Else` выполняется блок.  
  
 `Then`  
 Требуется однострочный синтаксис; Необязательный параметр, в многострочной синтаксис.  
  
 `statements`  
 Необязательный. Один или несколько следующих инструкций `If`... `Then` , которые выполняются, если `condition` равен `True`.  
  
 `elseifcondition`  
 Обязателен, если `ElseIf` присутствует. Выражение. Должны иметь `True` или `False`, или тип данных, который неявно преобразуется в `Boolean`.  
  
 `elseifstatements`  
 Необязательный. Один или несколько следующих инструкций `ElseIf`... `Then` , которые выполняются, если `elseifcondition` равен `True`.  
  
 `elsestatements`  
 Необязательный. Один или несколько инструкций, которые выполняются, если предыдущие `condition` или `elseifcondition` выражение, результатом которого является `True`.  
  
 `End If`  
 Завершает многострочном `If`... `Then`... `Else` блок.  
  
## <a name="remarks"></a>Примечания  
  
### <a name="multiline-syntax"></a>Многострочный синтаксис  
 Когда `If`... `Then`... `Else` обнаружил инструкции, `condition` проверяется. Если `condition` — `True`, инструкции, следующие за `Then` выполняются. Если `condition` — `False`, каждая `ElseIf` инструкция (если таковые имеются) вычисляется в порядке. Когда `True` `elseifcondition` находится сразу за соответствующим операторы `ElseIf` выполняются. Если не `elseifcondition` равен `True`, или при наличии не `ElseIf` инструкций, инструкции, следующие за `Else` выполняются. После выполнения следующей инструкции `Then`, `ElseIf`, или `Else`, выполнение продолжается с оператору, следующему `End If`.  
  
 `ElseIf` И `Else` предложения имеют одновременно необязательно. Можно использовать столько `ElseIf` предложений, что и у вас должны быть в `If`... `Then`... `Else` инструкции, но это не `ElseIf` предложение может следовать за `Else` предложения. `If`... `Then`... `Else` операторы могут быть вложены друг с другом.  
  
 В синтаксисе многострочных `If` инструкция должна быть единственной инструкцией в первой строке. `ElseIf`, `Else`, И `End If` инструкций может стоять только метку строки. `If`... `Then`... `Else` блок должен завершаться `End If` инструкции.  
  
> [!TIP]
>  [Выберите... Оператор выбора](../../../visual-basic/language-reference/statements/select-case-statement.md) могут быть более полезными при оценке единственное выражение, которое имеет несколько возможных значений.  
  
### <a name="single-line-syntax"></a>Однострочный синтаксис  
 Однострочный синтаксис для одного условия с кодом можно использовать для выполнения, если он имеет значение true. Однако многострочный синтаксис предоставляет большую структуру, гибкость и удобнее для чтения, обслуживания и отладки.  
  
 Какие следующим `Then` ключевое слово проверяется, чтобы определить, является ли инструкция однострочный `If`. Если ничего, кроме комментарий после `Then` в той же строке, инструкция обрабатывается как однострочный `If` инструкции. Если `Then` не существует, он должен быть начала многострочного `If`... `Then`... `Else`.  
  
 В синтаксисе однострочный может иметь несколько инструкций, в результате выполнения `If`... `Then` принятия решений. Все операторы должны находиться в той же строке и быть разделены точкой с запятой.  

## <a name="multiline-syntax-example"></a>Пример синтаксиса многострочный

<a name="multi-line"></a>
 
 В следующем примере показано использование многострочный синтаксис `If`... `Then`... `Else` инструкции.  
  
 [!code-vb[VbVbalrStatements#101](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_1.vb?highlight=11,14,17,19)]

## <a name="nested-syntax-example"></a>Пример вложенной синтаксиса

<a name="nested"></a>

 В следующем примере показаны вложенные `If`... `Then`... `Else` инструкции.  
  
 [!code-vb[VbVbalrStatements#102](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_2.vb?highlight=14,15,17,19,20,21,23,25,26,28)]

## <a name="single-line-syntax-example"></a>Пример синтаксиса для одной строки
  
<a name="single-line"></a> Следующий пример иллюстрирует использование синтаксиса одну строку.  
  
 [!code-vb[VbVbalrStatements#103](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_3.vb?highlight=18)]
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>  
 <xref:Microsoft.VisualBasic.Interaction.Switch%2A>  
 [Директивы #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [Оператор Select...Case](../../../visual-basic/language-reference/statements/select-case-statement.md)  
 [Вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Структуры решений](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [Логические и побитовые операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [Оператор If](../../../visual-basic/language-reference/operators/if-operator.md)
