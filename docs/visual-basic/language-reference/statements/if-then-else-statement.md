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
ms.openlocfilehash: aeffdc842730a1be8160cd8db8e4c2aa849e94cc
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57201733"
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

Эта статья содержит несколько примеров, иллюстрирующих использование `If`... `Then`... `Else` инструкции:

* [Пример синтаксиса многострочный](#multi-line)
* [Пример вложенных синтаксиса](#nested)
* [Пример синтаксиса однострочный](#single-line)

## <a name="parts"></a>Части  
 `condition`  
 Обязательный. выражение. Должны иметь `True` или `False`, или тип данных, который неявно преобразуется к типу `Boolean`.  
  
 Если выражение является [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` переменной, результатом которого является [ничего не](../../../visual-basic/language-reference/nothing.md), условие рассматривается как выражение является `False` и `Else` выполняется блок.  
  
 `Then`  
 Требуется однострочный синтаксис; необязательно для многострочный синтаксис.  
  
 `statements`  
 Необязательный параметр. Один или несколько следующих инструкций `If`... `Then` , которые выполняются, если `condition` принимает значение `True`.  
  
 `elseifcondition`  
 Обязателен, если `ElseIf` присутствует. выражение. Должны иметь `True` или `False`, или тип данных, который неявно преобразуется к типу `Boolean`.  
  
 `elseifstatements`  
 Необязательный параметр. Один или несколько следующих инструкций `ElseIf`... `Then` , которые выполняются, если `elseifcondition` принимает значение `True`.  
  
 `elsestatements`  
 Необязательный параметр. Один или несколько инструкций, которые выполняются, если предыдущего `condition` или `elseifcondition` выражение, результатом которого является `True`.  
  
 `End If`  
 Завершает многострочном `If`... `Then`... `Else` блок.  
  
## <a name="remarks"></a>Примечания  
  
### <a name="multiline-syntax"></a>Многострочный синтаксис  
 Когда `If`... `Then`... `Else` встречается, `condition` тестируется. Если `condition` — `True`, инструкции, следующие за `Then` выполняются. Если `condition` — `False`, каждая `ElseIf` инструкция (если таковые имеются) оценивается по очереди. Когда `True` `elseifcondition` найден, операторы, следующие непосредственно связанный `ElseIf` выполняются. Если не `elseifcondition` принимает значение `True`, или если не `ElseIf` операторы, инструкции, следующие за `Else` выполняются. После выполнения следующей инструкции `Then`, `ElseIf`, или `Else`, выполнение продолжается с оператор, следующий `End If`.  
  
 `ElseIf` И `Else` являются оба необязательно. Может быть столько `ElseIf` предложения, как вы хотите `If`... `Then`... `Else` инструкции, но не `ElseIf` предложения может появляться после `Else` предложение. `If`... `Then`... `Else` операторы могут быть вложены друг с другом.  
  
 В многострочных синтаксисе `If` инструкция должна быть единственной инструкцией в первой строке. `ElseIf`, `Else`, И `End If` инструкций может стоять только метку строки. `If`... `Then`... `Else` блок должен завершаться `End If` инструкции.  
  
> [!TIP]
>  [Выберите... Оператор выбора](../../../visual-basic/language-reference/statements/select-case-statement.md) могут быть более полезными при оценке одно выражение, которое имеет несколько возможных значений.  
  
### <a name="single-line-syntax"></a>Однострочный синтаксис  
 Можно использовать синтаксис одну строку для отдельного условия с кодом для выполнения, если он имеет значение true. Однако многострочный синтаксис предоставляет большую структуру, гибкость и проще читать, обслуживать и отладки.  
  
 Ниже описано `Then` ключевое слово анализируется для определения, является ли оператор однострочный `If`. Если ничего, кроме комментарий появляется после `Then` в той же строке, инструкция обрабатывается как однострочный `If` инструкции. Если `Then` отсутствует, он должен быть начала многострочного `If`... `Then`... `Else`.  
  
 В синтаксисе одной строки, можно использовать несколько операторов, в результате выполнения `If`... `Then` принятия решений. Все операторы должны находиться в той же строке и быть разделены точкой с запятой.  

## <a name="multiline-syntax-example"></a>Пример синтаксиса многострочный

<a name="multi-line"></a>
 
 Следующий пример иллюстрирует использование многострочный синтаксис `If`... `Then`... `Else` инструкции.  
  
 [!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a>Пример вложенных синтаксиса

<a name="nested"></a>

 В следующем примере показаны вложенные `If`... `Then`... `Else` инструкций.  
  
 [!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a>Пример синтаксиса однострочный
  
<a name="single-line"></a> Следующий пример иллюстрирует использование синтаксиса одну строку.  
  
 [!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]
  
## <a name="see-also"></a>См. также
- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [Директивы #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Оператор Select...Case](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [Вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Структуры решений](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Логические и побитовые операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [Оператор If](../../../visual-basic/language-reference/operators/if-operator.md)
