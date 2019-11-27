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
# <a name="ifthenelse-statement-visual-basic"></a><span data-ttu-id="e67ba-102">Оператор If...Then...Else (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e67ba-102">If...Then...Else Statement (Visual Basic)</span></span>

<span data-ttu-id="e67ba-103">Выполняет ту или иную группу операторов в зависимости от значения выражения.</span><span class="sxs-lookup"><span data-stu-id="e67ba-103">Conditionally executes a group of statements, depending on the value of an expression.</span></span>

## <a name="syntax"></a><span data-ttu-id="e67ba-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e67ba-104">Syntax</span></span>

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

## <a name="quick-links-to-example-code"></a><span data-ttu-id="e67ba-105">Быстрые ссылки на примеры кода</span><span class="sxs-lookup"><span data-stu-id="e67ba-105">Quick links to example code</span></span>

<span data-ttu-id="e67ba-106">Эта статья содержит несколько примеров, демонстрирующих использование оператора `If`...`Then`...`Else`:</span><span class="sxs-lookup"><span data-stu-id="e67ba-106">This article includes several examples that illustrate uses of the `If`...`Then`...`Else` statement:</span></span>

- [<span data-ttu-id="e67ba-107">Пример многострочного синтаксиса</span><span class="sxs-lookup"><span data-stu-id="e67ba-107">Multiline syntax example</span></span>](#multi-line)
- [<span data-ttu-id="e67ba-108">Пример вложенного синтаксиса</span><span class="sxs-lookup"><span data-stu-id="e67ba-108">Nested syntax example</span></span>](#nested)
- [<span data-ttu-id="e67ba-109">Пример однострочного синтаксиса</span><span class="sxs-lookup"><span data-stu-id="e67ba-109">Single-line syntax example</span></span>](#single-line)

## <a name="parts"></a><span data-ttu-id="e67ba-110">Части</span><span class="sxs-lookup"><span data-stu-id="e67ba-110">Parts</span></span>

`condition` \
<span data-ttu-id="e67ba-111">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="e67ba-111">Required.</span></span> <span data-ttu-id="e67ba-112">Выражение.</span><span class="sxs-lookup"><span data-stu-id="e67ba-112">Expression.</span></span> <span data-ttu-id="e67ba-113">Необходимо вычислить значение `True` или `False`или тип данных, который может быть неявно преобразован в `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="e67ba-113">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

<span data-ttu-id="e67ba-114">Если выражение является [обнуляемым](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` переменной, результатом которой является [Nothing](../../../visual-basic/language-reference/nothing.md), условие обрабатывается так, как если бы выражение `False`, а блоки `ElseIf` вычисляются, если они существуют, или блок `Else` выполняется, если он существует.</span><span class="sxs-lookup"><span data-stu-id="e67ba-114">If the expression is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the condition is treated as if the expression is `False`, and the `ElseIf` blocks are evaluated if they exist, or the `Else` block is executed if it exists.</span></span>

`Then` \
<span data-ttu-id="e67ba-115">Требуется в однострочном синтаксисе; Необязательный в многострочном синтаксисе.</span><span class="sxs-lookup"><span data-stu-id="e67ba-115">Required in the single-line syntax; optional in the multiline syntax.</span></span>

`statements` \
<span data-ttu-id="e67ba-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e67ba-116">Optional.</span></span> <span data-ttu-id="e67ba-117">Один или несколько инструкций, следующих за `If`...`Then`, которые выполняются, если `condition` вычисляется как `True`.</span><span class="sxs-lookup"><span data-stu-id="e67ba-117">One or more statements following `If`...`Then` that are executed if `condition` evaluates to `True`.</span></span>

`elseifcondition` \
<span data-ttu-id="e67ba-118">Требуется при наличии `ElseIf`.</span><span class="sxs-lookup"><span data-stu-id="e67ba-118">Required if `ElseIf` is present.</span></span> <span data-ttu-id="e67ba-119">Выражение.</span><span class="sxs-lookup"><span data-stu-id="e67ba-119">Expression.</span></span> <span data-ttu-id="e67ba-120">Необходимо вычислить значение `True` или `False`или тип данных, который может быть неявно преобразован в `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="e67ba-120">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

`elseifstatements` \
<span data-ttu-id="e67ba-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e67ba-121">Optional.</span></span> <span data-ttu-id="e67ba-122">Один или несколько инструкций, следующих за `ElseIf`...`Then`, которые выполняются, если `elseifcondition` вычисляется как `True`.</span><span class="sxs-lookup"><span data-stu-id="e67ba-122">One or more statements following `ElseIf`...`Then` that are executed if `elseifcondition` evaluates to `True`.</span></span>

`elsestatements` \
<span data-ttu-id="e67ba-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e67ba-123">Optional.</span></span> <span data-ttu-id="e67ba-124">Одна или несколько инструкций, которые выполняются, если предыдущее `condition` или `elseifcondition` выражение не имеет значение `True`.</span><span class="sxs-lookup"><span data-stu-id="e67ba-124">One or more statements that are executed if no previous `condition` or `elseifcondition` expression evaluates to `True`.</span></span>

`End If` \
<span data-ttu-id="e67ba-125">Завершает многострочную версию блока `If`...`Then`...`Else`.</span><span class="sxs-lookup"><span data-stu-id="e67ba-125">Terminates the multiline version of `If`...`Then`...`Else` block.</span></span>

## <a name="remarks"></a><span data-ttu-id="e67ba-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="e67ba-126">Remarks</span></span>

### <a name="multiline-syntax"></a><span data-ttu-id="e67ba-127">Многострочный синтаксис</span><span class="sxs-lookup"><span data-stu-id="e67ba-127">Multiline syntax</span></span>

<span data-ttu-id="e67ba-128">При обнаружении оператора `If`...`Then`...`Else` проверяется `condition`.</span><span class="sxs-lookup"><span data-stu-id="e67ba-128">When an `If`...`Then`...`Else` statement is encountered, `condition` is tested.</span></span> <span data-ttu-id="e67ba-129">Если `condition` `True`, выполняются операторы, следующие `Then`.</span><span class="sxs-lookup"><span data-stu-id="e67ba-129">If `condition` is `True`, the statements following `Then` are executed.</span></span> <span data-ttu-id="e67ba-130">Если `condition` `False`, то каждый оператор `ElseIf` (если таковые имеются) вычисляется по порядку.</span><span class="sxs-lookup"><span data-stu-id="e67ba-130">If `condition` is `False`, each `ElseIf` statement (if there are any) is evaluated in order.</span></span> <span data-ttu-id="e67ba-131">При обнаружении `elseifcondition` `True` выполняются инструкции, следующие непосредственно за соответствующим `ElseIf`.</span><span class="sxs-lookup"><span data-stu-id="e67ba-131">When a `True` `elseifcondition` is found, the statements immediately following the associated `ElseIf` are executed.</span></span> <span data-ttu-id="e67ba-132">Если `elseifcondition` не принимает значение `True`или если нет инструкций `ElseIf`, выполняются операторы, следующие за `Else`.</span><span class="sxs-lookup"><span data-stu-id="e67ba-132">If no `elseifcondition` evaluates to `True`, or if there are no `ElseIf` statements, the statements following `Else` are executed.</span></span> <span data-ttu-id="e67ba-133">После выполнения инструкций, следующих за `Then`, `ElseIf`или `Else`, выполнение продолжится с оператора, следующего за `End If`.</span><span class="sxs-lookup"><span data-stu-id="e67ba-133">After executing the statements following `Then`, `ElseIf`, or `Else`, execution continues with the statement following `End If`.</span></span>

<span data-ttu-id="e67ba-134">Предложения `ElseIf` и `Else` являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="e67ba-134">The `ElseIf` and `Else` clauses are both optional.</span></span> <span data-ttu-id="e67ba-135">Можно использовать любое количество `ElseIf` предложений в `If`...`Then`...`Else`, но предложение `ElseIf` не может появляться после предложения `Else`.</span><span class="sxs-lookup"><span data-stu-id="e67ba-135">You can have as many `ElseIf` clauses as you want in an `If`...`Then`...`Else` statement, but no `ElseIf` clause can appear after an `Else` clause.</span></span> <span data-ttu-id="e67ba-136">операторы `If`...`Then`...`Else` могут быть вложены друг в друга.</span><span class="sxs-lookup"><span data-stu-id="e67ba-136">`If`...`Then`...`Else` statements can be nested within each other.</span></span>

<span data-ttu-id="e67ba-137">В многострочном синтаксисе оператор `If` должен быть единственным оператором в первой строке.</span><span class="sxs-lookup"><span data-stu-id="e67ba-137">In the multiline syntax, the `If` statement must be the only statement on the first line.</span></span> <span data-ttu-id="e67ba-138">Операторам `ElseIf`, `Else`и `End If` может предшествовать только метка строки.</span><span class="sxs-lookup"><span data-stu-id="e67ba-138">The `ElseIf`, `Else`, and `End If` statements can be preceded only by a line label.</span></span> <span data-ttu-id="e67ba-139">Блок `If`...`Then`...`Else` должен заканчиваться оператором `End If`.</span><span class="sxs-lookup"><span data-stu-id="e67ba-139">The `If`...`Then`...`Else` block must end with an `End If` statement.</span></span>

> [!TIP]
> <span data-ttu-id="e67ba-140">[Выберите... Оператор Case](../../../visual-basic/language-reference/statements/select-case-statement.md) может оказаться более полезным при вычислении одного выражения, имеющего несколько возможных значений.</span><span class="sxs-lookup"><span data-stu-id="e67ba-140">The [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) might be more useful when you evaluate a single expression that has several possible values.</span></span>

### <a name="single-line-syntax"></a><span data-ttu-id="e67ba-141">Однострочный синтаксис</span><span class="sxs-lookup"><span data-stu-id="e67ba-141">Single-Line syntax</span></span>

<span data-ttu-id="e67ba-142">Можно использовать однострочный синтаксис для одного условия с кодом для выполнения, если это так.</span><span class="sxs-lookup"><span data-stu-id="e67ba-142">You can use the single-line syntax for a single condition with code to execute if it's true.</span></span> <span data-ttu-id="e67ba-143">Однако многострочный синтаксис обеспечивает большую структуру и гибкость и проще в чтении, обслуживании и отладке.</span><span class="sxs-lookup"><span data-stu-id="e67ba-143">However, the multiple-line syntax provides more structure and flexibility and is easier to read, maintain, and debug.</span></span>

<span data-ttu-id="e67ba-144">Что следует за ключевым словом `Then`, проверяется, является ли оператор однострочным `If`.</span><span class="sxs-lookup"><span data-stu-id="e67ba-144">What follows the `Then` keyword is examined to determine whether a statement is a single-line `If`.</span></span> <span data-ttu-id="e67ba-145">Если после `Then` в той же строке отображается любое значение, кроме комментария, инструкция рассматривается как однострочная `If` инструкция.</span><span class="sxs-lookup"><span data-stu-id="e67ba-145">If anything other than a comment appears after `Then` on the same line, the statement is treated as a single-line `If` statement.</span></span> <span data-ttu-id="e67ba-146">Если `Then` отсутствует, он должен быть началом многострочного `If`...`Then`...`Else`.</span><span class="sxs-lookup"><span data-stu-id="e67ba-146">If `Then` is absent, it must be the start of a multiple-line `If`...`Then`...`Else`.</span></span>

<span data-ttu-id="e67ba-147">В однострочном синтаксисе можно использовать несколько инструкций, выполняемых в результате `If`...`Then` принятия решения.</span><span class="sxs-lookup"><span data-stu-id="e67ba-147">In the single-line syntax, you can have multiple statements executed as the result of an `If`...`Then` decision.</span></span> <span data-ttu-id="e67ba-148">Все операторы должны находиться в одной строке и быть разделены двоеточиями.</span><span class="sxs-lookup"><span data-stu-id="e67ba-148">All statements must be on the same line and be separated by colons.</span></span>

## <a name="multiline-syntax-example"></a><span data-ttu-id="e67ba-149">Пример многострочного синтаксиса</span><span class="sxs-lookup"><span data-stu-id="e67ba-149">Multiline syntax example</span></span>

<a name="multi-line"></a>

<span data-ttu-id="e67ba-150">В следующем примере показано использование многострочного синтаксиса инструкции `If`...`Then`...`Else`.</span><span class="sxs-lookup"><span data-stu-id="e67ba-150">The following example illustrates the use of the multiline syntax of the `If`...`Then`...`Else` statement.</span></span>

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a><span data-ttu-id="e67ba-151">Пример вложенного синтаксиса</span><span class="sxs-lookup"><span data-stu-id="e67ba-151">Nested syntax example</span></span>

<a name="nested"></a>

<span data-ttu-id="e67ba-152">В следующем примере содержатся вложенные операторы `If`...`Then`...`Else`.</span><span class="sxs-lookup"><span data-stu-id="e67ba-152">The following example contains nested `If`...`Then`...`Else` statements.</span></span>

[!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a><span data-ttu-id="e67ba-153">Пример однострочного синтаксиса</span><span class="sxs-lookup"><span data-stu-id="e67ba-153">Single-Line syntax example</span></span>

<a name="single-line"></a><span data-ttu-id="e67ba-154">В следующем примере показано использование однострочного синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="e67ba-154">The following example illustrates the use of the single-line syntax.</span></span>

[!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]

## <a name="see-also"></a><span data-ttu-id="e67ba-155">См. также</span><span class="sxs-lookup"><span data-stu-id="e67ba-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [<span data-ttu-id="e67ba-156">Директивы #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="e67ba-156">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="e67ba-157">Оператор Select...Case</span><span class="sxs-lookup"><span data-stu-id="e67ba-157">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="e67ba-158">Вложенные структуры управления</span><span class="sxs-lookup"><span data-stu-id="e67ba-158">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="e67ba-159">Структуры решений</span><span class="sxs-lookup"><span data-stu-id="e67ba-159">Decision Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="e67ba-160">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e67ba-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [<span data-ttu-id="e67ba-161">Оператор If</span><span class="sxs-lookup"><span data-stu-id="e67ba-161">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
