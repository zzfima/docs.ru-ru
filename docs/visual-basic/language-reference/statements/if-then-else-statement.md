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
ms.openlocfilehash: 97ac8c82df14eb5ddc5e26fdaddf61cc774a0476
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046574"
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

## <a name="quick-links-to-example-code"></a>Быстрые ссылки на примеры кода

Эта статья содержит несколько примеров, демонстрирующих использование `If`... `Then`... `Else` Инструкция:

* [Пример многострочного синтаксиса](#multi-line)
* [Пример вложенного синтаксиса](#nested)
* [Пример однострочного синтаксиса](#single-line)

## <a name="parts"></a>Части

`condition` \
Обязательный. Выражение. Должен иметь значение `True` или `False`, или, или к типу данных, который неявно преобразуется `Boolean`в.

Если выражение является переменной, [допускающей значение NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` , которая возвращает значение [Nothing](../../../visual-basic/language-reference/nothing.md), условие обрабатывается так, как `False` `Else` если бы выражение было, а блок выполняется.

`Then` \
Требуется в однострочном синтаксисе; Необязательный в многострочном синтаксисе.

`statements` \
Необязательный параметр. Один или несколько инструкций, `If`следующих за... , которые выполняются, `condition` если имеет значение `True`. `Then`

`elseifcondition` \
Требуется, `ElseIf` если имеется. Выражение. Должен иметь значение `True` или `False`, или, или к типу данных, который неявно преобразуется `Boolean`в.

`elseifstatements` \
Необязательный параметр. Один или несколько инструкций, `ElseIf`следующих за... , которые выполняются, `elseifcondition` если имеет значение `True`. `Then`

`elsestatements` \
Необязательный параметр. Одна или несколько инструкций, выполняемых, если ни `condition` Предыдущая `elseifcondition` , ни выражение `True`не имеет значение.

`End If` \
Завершает многострочную версию `If`... `Then`... `Else` блокировать.

## <a name="remarks"></a>Примечания

### <a name="multiline-syntax"></a>Многострочный синтаксис

`If`Когда... `Then`... `Else` ,`condition` проверяется. Если `condition` имеет `True`значение, выполняются следующие `Then` операторы. Если `condition` имеет `False`значение, `ElseIf` то каждый оператор (если таковые имеются) вычисляется по порядку. Когда обнаруживается, выполняются операторы, непосредственно следующие за ними `ElseIf`. `True` `elseifcondition` Если значение `elseifcondition` не равно `True` `Else` или если нет `ElseIf` инструкций, выполняются следующие операторы. После выполнения инструкций, указанных `Then`после `ElseIf`, или `Else`, выполнение переходит к следующей `End If`инструкции.

Предложения `ElseIf` и`Else` являются необязательными. Можно использовать любое количество `ElseIf` предложений `If`в... `Then`... , но после предложения `ElseIf` предложение не может быть указано `Else`. `Else` `If`... `Then`... `Else` операторы могут быть вложенными друг в друга.

В многострочном синтаксисе `If` оператор должен быть единственным оператором в первой строке. Операторам `Else` ,и`End If` может предшествовать только метка строки. `ElseIf` `If`... `Then`... блок должен заканчиваться `End If`оператором. `Else`

> [!TIP]
> [Выберите... Оператор Case](../../../visual-basic/language-reference/statements/select-case-statement.md) может оказаться более полезным при вычислении одного выражения, имеющего несколько возможных значений.

### <a name="single-line-syntax"></a>Однострочный синтаксис

Можно использовать однострочный синтаксис для одного условия с кодом для выполнения, если это так. Однако многострочный синтаксис обеспечивает большую структуру и гибкость и проще в чтении, обслуживании и отладке.

Что следует за `Then` ключевым словом, проверяется, является ли оператор однострочным. `If` Если после `Then` на той же строке появляется нечто, кроме комментария, инструкция рассматривается как однострочный `If` оператор. Если `Then` параметр отсутствует, он должен быть началом многострочного `If`... `Then`... `Else`.

В однострочном синтаксисе можно использовать несколько инструкций, выполняемых в результате `If`выполнения... `Then` решение. Все операторы должны находиться в одной строке и быть разделены двоеточиями.

## <a name="multiline-syntax-example"></a>Пример многострочного синтаксиса

<a name="multi-line"></a>

В следующем примере показано использование многострочного синтаксиса `If`... `Then`... `Else` оператор.

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a>Пример вложенного синтаксиса

<a name="nested"></a>

Следующий пример содержит вложенные `If`... `Then`... `Else` операторы.

[!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a>Пример однострочного синтаксиса

<a name="single-line"></a>В следующем примере показано использование однострочного синтаксиса.

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
