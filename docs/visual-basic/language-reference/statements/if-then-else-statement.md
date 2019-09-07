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
ms.openlocfilehash: db81a1c41809b563d5f9d0777c3feb064c5e540b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400710"
---
# <a name="ifthenelse-statement-visual-basic"></a><span data-ttu-id="82531-102">Оператор If...Then...Else (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="82531-102">If...Then...Else Statement (Visual Basic)</span></span>

<span data-ttu-id="82531-103">Выполняет ту или иную группу операторов в зависимости от значения выражения.</span><span class="sxs-lookup"><span data-stu-id="82531-103">Conditionally executes a group of statements, depending on the value of an expression.</span></span>

## <a name="syntax"></a><span data-ttu-id="82531-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82531-104">Syntax</span></span>

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

## <a name="quick-links-to-example-code"></a><span data-ttu-id="82531-105">Быстрые ссылки на примеры кода</span><span class="sxs-lookup"><span data-stu-id="82531-105">Quick links to example code</span></span>

<span data-ttu-id="82531-106">Эта статья содержит несколько примеров, демонстрирующих использование `If`... `Then`... `Else` Инструкция:</span><span class="sxs-lookup"><span data-stu-id="82531-106">This article includes several examples that illustrate uses of the `If`...`Then`...`Else` statement:</span></span>

- [<span data-ttu-id="82531-107">Пример многострочного синтаксиса</span><span class="sxs-lookup"><span data-stu-id="82531-107">Multiline syntax example</span></span>](#multi-line)
- [<span data-ttu-id="82531-108">Пример вложенного синтаксиса</span><span class="sxs-lookup"><span data-stu-id="82531-108">Nested syntax example</span></span>](#nested)
- [<span data-ttu-id="82531-109">Пример однострочного синтаксиса</span><span class="sxs-lookup"><span data-stu-id="82531-109">Single-line syntax example</span></span>](#single-line)

## <a name="parts"></a><span data-ttu-id="82531-110">Части</span><span class="sxs-lookup"><span data-stu-id="82531-110">Parts</span></span>

`condition` \
<span data-ttu-id="82531-111">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="82531-111">Required.</span></span> <span data-ttu-id="82531-112">Выражение.</span><span class="sxs-lookup"><span data-stu-id="82531-112">Expression.</span></span> <span data-ttu-id="82531-113">Должен иметь значение `True` или `False`, или, или к типу данных, который неявно преобразуется `Boolean`в.</span><span class="sxs-lookup"><span data-stu-id="82531-113">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

<span data-ttu-id="82531-114">Если выражение является переменной, [допускающей значение NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` , значением которого является [Nothing](../../../visual-basic/language-reference/nothing.md), условие обрабатывается так, как если `False`бы выражение было `ElseIf` , а блоки оцениваются, если они существуют `Else` , или блоком является выполняется, если он существует.</span><span class="sxs-lookup"><span data-stu-id="82531-114">If the expression is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the condition is treated as if the expression is `False`, and the `ElseIf` blocks are evaluated if they exist, or the `Else` block is executed if it exists.</span></span>

`Then` \
<span data-ttu-id="82531-115">Требуется в однострочном синтаксисе; Необязательный в многострочном синтаксисе.</span><span class="sxs-lookup"><span data-stu-id="82531-115">Required in the single-line syntax; optional in the multiline syntax.</span></span>

`statements` \
<span data-ttu-id="82531-116">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="82531-116">Optional.</span></span> <span data-ttu-id="82531-117">Один или несколько инструкций, `If`следующих за... , которые выполняются, `condition` если имеет значение `True`. `Then`</span><span class="sxs-lookup"><span data-stu-id="82531-117">One or more statements following `If`...`Then` that are executed if `condition` evaluates to `True`.</span></span>

`elseifcondition` \
<span data-ttu-id="82531-118">Требуется, `ElseIf` если имеется.</span><span class="sxs-lookup"><span data-stu-id="82531-118">Required if `ElseIf` is present.</span></span> <span data-ttu-id="82531-119">Выражение.</span><span class="sxs-lookup"><span data-stu-id="82531-119">Expression.</span></span> <span data-ttu-id="82531-120">Должен иметь значение `True` или `False`, или, или к типу данных, который неявно преобразуется `Boolean`в.</span><span class="sxs-lookup"><span data-stu-id="82531-120">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

`elseifstatements` \
<span data-ttu-id="82531-121">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="82531-121">Optional.</span></span> <span data-ttu-id="82531-122">Один или несколько инструкций, `ElseIf`следующих за... , которые выполняются, `elseifcondition` если имеет значение `True`. `Then`</span><span class="sxs-lookup"><span data-stu-id="82531-122">One or more statements following `ElseIf`...`Then` that are executed if `elseifcondition` evaluates to `True`.</span></span>

`elsestatements` \
<span data-ttu-id="82531-123">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="82531-123">Optional.</span></span> <span data-ttu-id="82531-124">Одна или несколько инструкций, выполняемых, если ни `condition` Предыдущая `elseifcondition` , ни выражение `True`не имеет значение.</span><span class="sxs-lookup"><span data-stu-id="82531-124">One or more statements that are executed if no previous `condition` or `elseifcondition` expression evaluates to `True`.</span></span>

`End If` \
<span data-ttu-id="82531-125">Завершает многострочную версию `If`... `Then`... `Else` блокировать.</span><span class="sxs-lookup"><span data-stu-id="82531-125">Terminates the multiline version of `If`...`Then`...`Else` block.</span></span>

## <a name="remarks"></a><span data-ttu-id="82531-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="82531-126">Remarks</span></span>

### <a name="multiline-syntax"></a><span data-ttu-id="82531-127">Многострочный синтаксис</span><span class="sxs-lookup"><span data-stu-id="82531-127">Multiline syntax</span></span>

<span data-ttu-id="82531-128">`If`Когда... `Then`... `Else` ,`condition` проверяется.</span><span class="sxs-lookup"><span data-stu-id="82531-128">When an `If`...`Then`...`Else` statement is encountered, `condition` is tested.</span></span> <span data-ttu-id="82531-129">Если `condition` имеет `True`значение, выполняются следующие `Then` операторы.</span><span class="sxs-lookup"><span data-stu-id="82531-129">If `condition` is `True`, the statements following `Then` are executed.</span></span> <span data-ttu-id="82531-130">Если `condition` имеет `False`значение, `ElseIf` то каждый оператор (если таковые имеются) вычисляется по порядку.</span><span class="sxs-lookup"><span data-stu-id="82531-130">If `condition` is `False`, each `ElseIf` statement (if there are any) is evaluated in order.</span></span> <span data-ttu-id="82531-131">Когда обнаруживается, выполняются операторы, непосредственно следующие за ними `ElseIf`. `True` `elseifcondition`</span><span class="sxs-lookup"><span data-stu-id="82531-131">When a `True` `elseifcondition` is found, the statements immediately following the associated `ElseIf` are executed.</span></span> <span data-ttu-id="82531-132">Если значение `elseifcondition` не равно `True` `Else` или если нет `ElseIf` инструкций, выполняются следующие операторы.</span><span class="sxs-lookup"><span data-stu-id="82531-132">If no `elseifcondition` evaluates to `True`, or if there are no `ElseIf` statements, the statements following `Else` are executed.</span></span> <span data-ttu-id="82531-133">После выполнения инструкций, указанных `Then`после `ElseIf`, или `Else`, выполнение переходит к следующей `End If`инструкции.</span><span class="sxs-lookup"><span data-stu-id="82531-133">After executing the statements following `Then`, `ElseIf`, or `Else`, execution continues with the statement following `End If`.</span></span>

<span data-ttu-id="82531-134">Предложения `ElseIf` и`Else` являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="82531-134">The `ElseIf` and `Else` clauses are both optional.</span></span> <span data-ttu-id="82531-135">Можно использовать любое количество `ElseIf` предложений `If`в... `Then`... , но после предложения `ElseIf` предложение не может быть указано `Else`. `Else`</span><span class="sxs-lookup"><span data-stu-id="82531-135">You can have as many `ElseIf` clauses as you want in an `If`...`Then`...`Else` statement, but no `ElseIf` clause can appear after an `Else` clause.</span></span> <span data-ttu-id="82531-136">`If`... `Then`... `Else` операторы могут быть вложенными друг в друга.</span><span class="sxs-lookup"><span data-stu-id="82531-136">`If`...`Then`...`Else` statements can be nested within each other.</span></span>

<span data-ttu-id="82531-137">В многострочном синтаксисе `If` оператор должен быть единственным оператором в первой строке.</span><span class="sxs-lookup"><span data-stu-id="82531-137">In the multiline syntax, the `If` statement must be the only statement on the first line.</span></span> <span data-ttu-id="82531-138">Операторам `Else` ,и`End If` может предшествовать только метка строки. `ElseIf`</span><span class="sxs-lookup"><span data-stu-id="82531-138">The `ElseIf`, `Else`, and `End If` statements can be preceded only by a line label.</span></span> <span data-ttu-id="82531-139">`If`... `Then`... блок должен заканчиваться `End If`оператором. `Else`</span><span class="sxs-lookup"><span data-stu-id="82531-139">The `If`...`Then`...`Else` block must end with an `End If` statement.</span></span>

> [!TIP]
> <span data-ttu-id="82531-140">[Выберите... Оператор Case](../../../visual-basic/language-reference/statements/select-case-statement.md) может оказаться более полезным при вычислении одного выражения, имеющего несколько возможных значений.</span><span class="sxs-lookup"><span data-stu-id="82531-140">The [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) might be more useful when you evaluate a single expression that has several possible values.</span></span>

### <a name="single-line-syntax"></a><span data-ttu-id="82531-141">Однострочный синтаксис</span><span class="sxs-lookup"><span data-stu-id="82531-141">Single-Line syntax</span></span>

<span data-ttu-id="82531-142">Можно использовать однострочный синтаксис для одного условия с кодом для выполнения, если это так.</span><span class="sxs-lookup"><span data-stu-id="82531-142">You can use the single-line syntax for a single condition with code to execute if it's true.</span></span> <span data-ttu-id="82531-143">Однако многострочный синтаксис обеспечивает большую структуру и гибкость и проще в чтении, обслуживании и отладке.</span><span class="sxs-lookup"><span data-stu-id="82531-143">However, the multiple-line syntax provides more structure and flexibility and is easier to read, maintain, and debug.</span></span>

<span data-ttu-id="82531-144">Что следует за `Then` ключевым словом, проверяется, является ли оператор однострочным. `If`</span><span class="sxs-lookup"><span data-stu-id="82531-144">What follows the `Then` keyword is examined to determine whether a statement is a single-line `If`.</span></span> <span data-ttu-id="82531-145">Если после `Then` на той же строке появляется нечто, кроме комментария, инструкция рассматривается как однострочный `If` оператор.</span><span class="sxs-lookup"><span data-stu-id="82531-145">If anything other than a comment appears after `Then` on the same line, the statement is treated as a single-line `If` statement.</span></span> <span data-ttu-id="82531-146">Если `Then` параметр отсутствует, он должен быть началом многострочного `If`... `Then`... `Else`.</span><span class="sxs-lookup"><span data-stu-id="82531-146">If `Then` is absent, it must be the start of a multiple-line `If`...`Then`...`Else`.</span></span>

<span data-ttu-id="82531-147">В однострочном синтаксисе можно использовать несколько инструкций, выполняемых в результате `If`выполнения... `Then` решение.</span><span class="sxs-lookup"><span data-stu-id="82531-147">In the single-line syntax, you can have multiple statements executed as the result of an `If`...`Then` decision.</span></span> <span data-ttu-id="82531-148">Все операторы должны находиться в одной строке и быть разделены двоеточиями.</span><span class="sxs-lookup"><span data-stu-id="82531-148">All statements must be on the same line and be separated by colons.</span></span>

## <a name="multiline-syntax-example"></a><span data-ttu-id="82531-149">Пример многострочного синтаксиса</span><span class="sxs-lookup"><span data-stu-id="82531-149">Multiline syntax example</span></span>

<a name="multi-line"></a>

<span data-ttu-id="82531-150">В следующем примере показано использование многострочного синтаксиса `If`... `Then`... `Else` оператор.</span><span class="sxs-lookup"><span data-stu-id="82531-150">The following example illustrates the use of the multiline syntax of the `If`...`Then`...`Else` statement.</span></span>

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a><span data-ttu-id="82531-151">Пример вложенного синтаксиса</span><span class="sxs-lookup"><span data-stu-id="82531-151">Nested syntax example</span></span>

<a name="nested"></a>

<span data-ttu-id="82531-152">Следующий пример содержит вложенные `If`... `Then`... `Else` операторы.</span><span class="sxs-lookup"><span data-stu-id="82531-152">The following example contains nested `If`...`Then`...`Else` statements.</span></span>

[!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a><span data-ttu-id="82531-153">Пример однострочного синтаксиса</span><span class="sxs-lookup"><span data-stu-id="82531-153">Single-Line syntax example</span></span>

<a name="single-line"></a><span data-ttu-id="82531-154">В следующем примере показано использование однострочного синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="82531-154">The following example illustrates the use of the single-line syntax.</span></span>

[!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]

## <a name="see-also"></a><span data-ttu-id="82531-155">См. также</span><span class="sxs-lookup"><span data-stu-id="82531-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [<span data-ttu-id="82531-156">Директивы #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="82531-156">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="82531-157">Оператор Select...Case</span><span class="sxs-lookup"><span data-stu-id="82531-157">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="82531-158">Вложенные структуры управления</span><span class="sxs-lookup"><span data-stu-id="82531-158">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="82531-159">Структуры решений</span><span class="sxs-lookup"><span data-stu-id="82531-159">Decision Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="82531-160">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="82531-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [<span data-ttu-id="82531-161">Оператор If</span><span class="sxs-lookup"><span data-stu-id="82531-161">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
