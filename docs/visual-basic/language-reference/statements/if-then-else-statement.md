---
title: "Оператор If...Then...Else (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "29"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 898b72055345e88ca35f805de211c0c57cd74200
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ifthenelse-statement-visual-basic"></a><span data-ttu-id="7e436-102">Оператор If...Then...Else (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7e436-102">If...Then...Else Statement (Visual Basic)</span></span>
<span data-ttu-id="7e436-103">Выполняет ту или иную группу операторов в зависимости от значения выражения.</span><span class="sxs-lookup"><span data-stu-id="7e436-103">Conditionally executes a group of statements, depending on the value of an expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e436-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e436-104">Syntax</span></span>  
  
```  
' Multiple-line syntax:  
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
  
## <a name="parts"></a><span data-ttu-id="7e436-105">Части</span><span class="sxs-lookup"><span data-stu-id="7e436-105">Parts</span></span>  
 `condition`  
 <span data-ttu-id="7e436-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="7e436-106">Required.</span></span> <span data-ttu-id="7e436-107">Выражение.</span><span class="sxs-lookup"><span data-stu-id="7e436-107">Expression.</span></span> <span data-ttu-id="7e436-108">Должны иметь `True` или `False`, или тип данных, который неявно преобразуется в `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="7e436-108">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>  
  
 <span data-ttu-id="7e436-109">Если выражение является [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` переменной, результатом которого является [ничего](../../../visual-basic/language-reference/nothing.md), условие рассматривается как недопустимое выражение `True`и `Else` блок выполнена.</span><span class="sxs-lookup"><span data-stu-id="7e436-109">If the expression is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)`Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the condition is treated as if the expression is not `True`, and the `Else` block is executed.</span></span>  
  
 `Then`  
 <span data-ttu-id="7e436-110">Требуется однострочный синтаксис; Необязательный параметр в синтаксисе несколько строк.</span><span class="sxs-lookup"><span data-stu-id="7e436-110">Required in the single-line syntax; optional in the multiple-line syntax.</span></span>  
  
 `statements`  
 <span data-ttu-id="7e436-111">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="7e436-111">Optional.</span></span> <span data-ttu-id="7e436-112">Один или несколько следующих инструкций `If`... `Then` , которые выполняются, если `condition` равен `True`.</span><span class="sxs-lookup"><span data-stu-id="7e436-112">One or more statements following `If`...`Then` that are executed if `condition` evaluates to `True`.</span></span>  
  
 `elseifcondition`  
 <span data-ttu-id="7e436-113">Обязателен, если `ElseIf` присутствует.</span><span class="sxs-lookup"><span data-stu-id="7e436-113">Required if `ElseIf` is present.</span></span> <span data-ttu-id="7e436-114">Выражение.</span><span class="sxs-lookup"><span data-stu-id="7e436-114">Expression.</span></span> <span data-ttu-id="7e436-115">Должны иметь `True` или `False`, или тип данных, который неявно преобразуется в `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="7e436-115">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>  
  
 `elseifstatements`  
 <span data-ttu-id="7e436-116">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="7e436-116">Optional.</span></span> <span data-ttu-id="7e436-117">Один или несколько следующих инструкций `ElseIf`... `Then` , которые выполняются, если `elseifcondition` равен `True`.</span><span class="sxs-lookup"><span data-stu-id="7e436-117">One or more statements following `ElseIf`...`Then` that are executed if `elseifcondition` evaluates to `True`.</span></span>  
  
 `elsestatements`  
 <span data-ttu-id="7e436-118">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="7e436-118">Optional.</span></span> <span data-ttu-id="7e436-119">Один или несколько инструкций, которые выполняются, если предыдущие `condition` или `elseifcondition` выражение, результатом которого является `True`.</span><span class="sxs-lookup"><span data-stu-id="7e436-119">One or more statements that are executed if no previous `condition` or `elseifcondition` expression evaluates to `True`.</span></span>  
  
 `End If`  
 <span data-ttu-id="7e436-120">Завершает `If`... `Then`... `Else` блок.</span><span class="sxs-lookup"><span data-stu-id="7e436-120">Terminates the `If`...`Then`...`Else` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e436-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="7e436-121">Remarks</span></span>  
  
## <a name="multiple-line-syntax"></a><span data-ttu-id="7e436-122">Многострочный синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e436-122">Multiple-Line Syntax</span></span>  
 <span data-ttu-id="7e436-123">Когда `If`... `Then`... `Else` обнаружил инструкции, `condition` проверяется.</span><span class="sxs-lookup"><span data-stu-id="7e436-123">When an `If`...`Then`...`Else` statement is encountered, `condition` is tested.</span></span> <span data-ttu-id="7e436-124">Если `condition` — `True`, инструкции, следующие за `Then` выполняются.</span><span class="sxs-lookup"><span data-stu-id="7e436-124">If `condition` is `True`, the statements following `Then` are executed.</span></span> <span data-ttu-id="7e436-125">Если `condition` — `False`, каждая `ElseIf` инструкция (если таковые имеются) вычисляется в порядке.</span><span class="sxs-lookup"><span data-stu-id="7e436-125">If `condition` is `False`, each `ElseIf` statement (if there are any) is evaluated in order.</span></span> <span data-ttu-id="7e436-126">Когда `True``elseifcondition` находится сразу за соответствующим операторы `ElseIf` выполняются.</span><span class="sxs-lookup"><span data-stu-id="7e436-126">When a `True``elseifcondition` is found, the statements immediately following the associated `ElseIf` are executed.</span></span> <span data-ttu-id="7e436-127">Если не `elseifcondition` равен `True`, или при наличии не `ElseIf` инструкций, инструкции, следующие за `Else` выполняются.</span><span class="sxs-lookup"><span data-stu-id="7e436-127">If no `elseifcondition` evaluates to `True`, or if there are no `ElseIf` statements, the statements following `Else` are executed.</span></span> <span data-ttu-id="7e436-128">После выполнения следующей инструкции `Then`, `ElseIf`, или `Else`, выполнение продолжается с оператору, следующему `End If`.</span><span class="sxs-lookup"><span data-stu-id="7e436-128">After executing the statements following `Then`, `ElseIf`, or `Else`, execution continues with the statement following `End If`.</span></span>  
  
 <span data-ttu-id="7e436-129">`ElseIf` И `Else` предложения имеют одновременно необязательно.</span><span class="sxs-lookup"><span data-stu-id="7e436-129">The `ElseIf` and `Else` clauses are both optional.</span></span> <span data-ttu-id="7e436-130">Можно использовать столько `ElseIf` предложений, что и у вас должны быть в `If`... `Then`... `Else` инструкции, но это не `ElseIf` предложение может следовать за `Else` предложения.</span><span class="sxs-lookup"><span data-stu-id="7e436-130">You can have as many `ElseIf` clauses as you want in an `If`...`Then`...`Else` statement, but no `ElseIf` clause can appear after an `Else` clause.</span></span> <span data-ttu-id="7e436-131">`If`... `Then`... `Else` операторы могут быть вложены друг с другом.</span><span class="sxs-lookup"><span data-stu-id="7e436-131">`If`...`Then`...`Else` statements can be nested within each other.</span></span>  
  
 <span data-ttu-id="7e436-132">В синтаксисе многострочных `If` инструкция должна быть единственной инструкцией в первой строке.</span><span class="sxs-lookup"><span data-stu-id="7e436-132">In the multiple-line syntax, the `If` statement must be the only statement on the first line.</span></span> <span data-ttu-id="7e436-133">`ElseIf`, `Else`, И `End If` инструкций может стоять только метку строки.</span><span class="sxs-lookup"><span data-stu-id="7e436-133">The `ElseIf`, `Else`, and `End If` statements can be preceded only by a line label.</span></span> <span data-ttu-id="7e436-134">`If`... `Then`... `Else` блок должен завершаться `End If` инструкции.</span><span class="sxs-lookup"><span data-stu-id="7e436-134">The `If`...`Then`...`Else` block must end with an `End If` statement.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="7e436-135">[Выберите... Оператор выбора](../../../visual-basic/language-reference/statements/select-case-statement.md) могут быть более полезными при оценке единственное выражение, которое имеет несколько возможных значений.</span><span class="sxs-lookup"><span data-stu-id="7e436-135">The [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) might be more useful when you evaluate a single expression that has several possible values.</span></span>  
  
## <a name="single-line-syntax"></a><span data-ttu-id="7e436-136">Однострочный синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e436-136">Single-Line Syntax</span></span>  
 <span data-ttu-id="7e436-137">Однострочный синтаксис можно использовать для коротких, простых проверок.</span><span class="sxs-lookup"><span data-stu-id="7e436-137">You can use the single-line syntax for short, simple tests.</span></span> <span data-ttu-id="7e436-138">Однако многострочный синтаксис предоставляет большую структуру, гибкость и обычно удобнее для чтения, обслуживать и отладки.</span><span class="sxs-lookup"><span data-stu-id="7e436-138">However, the multiple-line syntax provides more structure and flexibility and is usually easier to read, maintain, and debug.</span></span>  
  
 <span data-ttu-id="7e436-139">Какие следующим `Then` ключевое слово проверяется, чтобы определить, является ли инструкция однострочный `If`.</span><span class="sxs-lookup"><span data-stu-id="7e436-139">What follows the `Then` keyword is examined to determine whether a statement is a single-line `If`.</span></span> <span data-ttu-id="7e436-140">Если ничего, кроме комментарий после `Then` в той же строке, инструкция обрабатывается как однострочный `If` инструкции.</span><span class="sxs-lookup"><span data-stu-id="7e436-140">If anything other than a comment appears after `Then` on the same line, the statement is treated as a single-line `If` statement.</span></span> <span data-ttu-id="7e436-141">Если `Then` не существует, он должен быть начала многострочного `If`... `Then`... `Else`.</span><span class="sxs-lookup"><span data-stu-id="7e436-141">If `Then` is absent, it must be the start of a multiple-line `If`...`Then`...`Else`.</span></span>  
  
 <span data-ttu-id="7e436-142">В синтаксисе однострочный может иметь несколько инструкций, в результате выполнения `If`... `Then` принятия решений.</span><span class="sxs-lookup"><span data-stu-id="7e436-142">In the single-line syntax, you can have multiple statements executed as the result of an `If`...`Then` decision.</span></span> <span data-ttu-id="7e436-143">Все операторы должны находиться в той же строке и быть разделены точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="7e436-143">All statements must be on the same line and be separated by colons.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e436-144">Пример</span><span class="sxs-lookup"><span data-stu-id="7e436-144">Example</span></span>  
 <span data-ttu-id="7e436-145">Следующий пример иллюстрирует использование синтаксиса несколько строк `If`... `Then`... `Else` инструкции.</span><span class="sxs-lookup"><span data-stu-id="7e436-145">The following example illustrates the use of the multiple-line syntax of the `If`...`Then`...`Else` statement.</span></span>  
  
 [!code-vb[VbVbalrStatements#101](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="7e436-146">Пример</span><span class="sxs-lookup"><span data-stu-id="7e436-146">Example</span></span>  
 <span data-ttu-id="7e436-147">В следующем примере показаны вложенные `If`... `Then`... `Else` инструкции.</span><span class="sxs-lookup"><span data-stu-id="7e436-147">The following example contains nested `If`...`Then`...`Else` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#102](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="7e436-148">Пример</span><span class="sxs-lookup"><span data-stu-id="7e436-148">Example</span></span>  
 <span data-ttu-id="7e436-149">Следующий пример иллюстрирует использование синтаксиса одну строку.</span><span class="sxs-lookup"><span data-stu-id="7e436-149">The following example illustrates the use of the single-line syntax.</span></span>  
  
 [!code-vb[VbVbalrStatements#103](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7e436-150">См. также</span><span class="sxs-lookup"><span data-stu-id="7e436-150">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>  
 <xref:Microsoft.VisualBasic.Interaction.Switch%2A>  
 [<span data-ttu-id="7e436-151">Директивы #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="7e436-151">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="7e436-152">Оператор Select...Case</span><span class="sxs-lookup"><span data-stu-id="7e436-152">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)  
 [<span data-ttu-id="7e436-153">Вложенные структуры управления</span><span class="sxs-lookup"><span data-stu-id="7e436-153">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="7e436-154">Структуры решений</span><span class="sxs-lookup"><span data-stu-id="7e436-154">Decision Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="7e436-155">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7e436-155">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [<span data-ttu-id="7e436-156">Оператор If</span><span class="sxs-lookup"><span data-stu-id="7e436-156">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
