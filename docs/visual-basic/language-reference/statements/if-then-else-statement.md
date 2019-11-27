---
title: Оператор If...Then...Else
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
ms.openlocfilehash: f505755caeb9cc3cfeeb1ba83b6de15f48314103
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351164"
---
# <a name="ifthenelse-statement-visual-basic"></a>Оператор If...Then...Else (Visual Basic)

Выполняет ту или иную группу операторов в зависимости от значения выражения.

## <a name="syntax"></a>Синтаксис

```vb
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

Эта статья содержит несколько примеров, демонстрирующих использование оператора `If`...`Then`...`Else`:

- [Пример многострочного синтаксиса](#multi-line)
- [Пример вложенного синтаксиса](#nested)
- [Пример однострочного синтаксиса](#single-line)

## <a name="parts"></a>Части

`condition` \
Обязательно. Выражение. Необходимо вычислить значение `True` или `False`или тип данных, который может быть неявно преобразован в `Boolean`.

Если выражение является [обнуляемым](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` переменной, результатом которой является [Nothing](../../../visual-basic/language-reference/nothing.md), условие обрабатывается так, как если бы выражение `False`, а блоки `ElseIf` вычисляются, если они существуют, или блок `Else` выполняется, если он существует.

`Then` \
Требуется в однострочном синтаксисе; Необязательный в многострочном синтаксисе.

`statements` \
Необязательный элемент. Один или несколько инструкций, следующих за `If`...`Then`, которые выполняются, если `condition` вычисляется как `True`.

`elseifcondition` \
Требуется при наличии `ElseIf`. Выражение. Необходимо вычислить значение `True` или `False`или тип данных, который может быть неявно преобразован в `Boolean`.

`elseifstatements` \
Необязательный элемент. Один или несколько инструкций, следующих за `ElseIf`...`Then`, которые выполняются, если `elseifcondition` вычисляется как `True`.

`elsestatements` \
Необязательный элемент. Одна или несколько инструкций, которые выполняются, если предыдущее `condition` или `elseifcondition` выражение не имеет значение `True`.

`End If` \
Завершает многострочную версию блока `If`...`Then`...`Else`.

## <a name="remarks"></a>Примечания

### <a name="multiline-syntax"></a>Многострочный синтаксис

При обнаружении оператора `If`...`Then`...`Else` проверяется `condition`. Если `condition` `True`, выполняются операторы, следующие `Then`. Если `condition` `False`, то каждый оператор `ElseIf` (если таковые имеются) вычисляется по порядку. При обнаружении `elseifcondition` `True` выполняются инструкции, следующие непосредственно за соответствующим `ElseIf`. Если `elseifcondition` не принимает значение `True`или если нет инструкций `ElseIf`, выполняются операторы, следующие за `Else`. После выполнения инструкций, следующих за `Then`, `ElseIf`или `Else`, выполнение продолжится с оператора, следующего за `End If`.

Предложения `ElseIf` и `Else` являются необязательными. Можно использовать любое количество `ElseIf` предложений в `If`...`Then`...`Else`, но предложение `ElseIf` не может появляться после предложения `Else`. операторы `If`...`Then`...`Else` могут быть вложены друг в друга.

В многострочном синтаксисе оператор `If` должен быть единственным оператором в первой строке. Операторам `ElseIf`, `Else`и `End If` может предшествовать только метка строки. Блок `If`...`Then`...`Else` должен заканчиваться оператором `End If`.

> [!TIP]
> [Выберите... Оператор Case](../../../visual-basic/language-reference/statements/select-case-statement.md) может оказаться более полезным при вычислении одного выражения, имеющего несколько возможных значений.

### <a name="single-line-syntax"></a>Однострочный синтаксис

Можно использовать однострочный синтаксис для одного условия с кодом для выполнения, если это так. Однако многострочный синтаксис обеспечивает большую структуру и гибкость и проще в чтении, обслуживании и отладке.

Что следует за ключевым словом `Then`, проверяется, является ли оператор однострочным `If`. Если после `Then` в той же строке отображается любое значение, кроме комментария, инструкция рассматривается как однострочная `If` инструкция. Если `Then` отсутствует, он должен быть началом многострочного `If`...`Then`...`Else`.

В однострочном синтаксисе можно использовать несколько инструкций, выполняемых в результате `If`...`Then` принятия решения. Все операторы должны находиться в одной строке и быть разделены двоеточиями.

## <a name="multiline-syntax-example"></a>Пример многострочного синтаксиса

<a name="multi-line"></a>

В следующем примере показано использование многострочного синтаксиса инструкции `If`...`Then`...`Else`.

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a>Пример вложенного синтаксиса

<a name="nested"></a>

В следующем примере содержатся вложенные операторы `If`...`Then`...`Else`.

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
