---
title: Оператор If...Then...Else (Visual Basic)
ms.date: 04/16/2018
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: conceptual
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
caps.latest.revision: 29
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1080a17cfcc493175c1e2f3527837030b4254bc2
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="ifthenelse-statement-visual-basic"></a><span data-ttu-id="a0b5f-102">Оператор If...Then...Else (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a0b5f-102">If...Then...Else Statement (Visual Basic)</span></span>
<span data-ttu-id="a0b5f-103">Выполняет ту или иную группу операторов в зависимости от значения выражения.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-103">Conditionally executes a group of statements, depending on the value of an expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0b5f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0b5f-104">Syntax</span></span>  
  
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

## <a name="quick-links-to-example-code"></a><span data-ttu-id="a0b5f-105">Быстрые ссылки на пример кода</span><span class="sxs-lookup"><span data-stu-id="a0b5f-105">Quick links to example code</span></span>

<span data-ttu-id="a0b5f-106">Здесь приведено несколько примеров, иллюстрирующих использование `If`... `Then`... `Else` инструкции:</span><span class="sxs-lookup"><span data-stu-id="a0b5f-106">This article includes several examples that illustrate uses of the `If`...`Then`...`Else` statement:</span></span>

* [<span data-ttu-id="a0b5f-107">Пример синтаксиса многострочный</span><span class="sxs-lookup"><span data-stu-id="a0b5f-107">Multiline syntax example</span></span>](#multi-line)
* [<span data-ttu-id="a0b5f-108">Пример вложенной синтаксиса</span><span class="sxs-lookup"><span data-stu-id="a0b5f-108">Nested syntax example</span></span>](#nested)
* [<span data-ttu-id="a0b5f-109">Пример синтаксиса для одной строки</span><span class="sxs-lookup"><span data-stu-id="a0b5f-109">Single-line syntax example</span></span>](#single-line)

## <a name="parts"></a><span data-ttu-id="a0b5f-110">Части</span><span class="sxs-lookup"><span data-stu-id="a0b5f-110">Parts</span></span>  
 `condition`  
 <span data-ttu-id="a0b5f-111">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-111">Required.</span></span> <span data-ttu-id="a0b5f-112">Выражение.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-112">Expression.</span></span> <span data-ttu-id="a0b5f-113">Должны иметь `True` или `False`, или тип данных, который неявно преобразуется в `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-113">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>  
  
 <span data-ttu-id="a0b5f-114">Если выражение является [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` переменной, результатом которого является [ничего](../../../visual-basic/language-reference/nothing.md), условие рассматривается как выражение `False` и `Else` выполняется блок.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-114">If the expression is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the condition is treated as if the expression is `False` and the `Else` block is executed.</span></span>  
  
 `Then`  
 <span data-ttu-id="a0b5f-115">Требуется однострочный синтаксис; Необязательный параметр, в многострочной синтаксис.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-115">Required in the single-line syntax; optional in the multiline syntax.</span></span>  
  
 `statements`  
 <span data-ttu-id="a0b5f-116">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-116">Optional.</span></span> <span data-ttu-id="a0b5f-117">Один или несколько следующих инструкций `If`... `Then` , которые выполняются, если `condition` равен `True`.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-117">One or more statements following `If`...`Then` that are executed if `condition` evaluates to `True`.</span></span>  
  
 `elseifcondition`  
 <span data-ttu-id="a0b5f-118">Обязателен, если `ElseIf` присутствует.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-118">Required if `ElseIf` is present.</span></span> <span data-ttu-id="a0b5f-119">Выражение.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-119">Expression.</span></span> <span data-ttu-id="a0b5f-120">Должны иметь `True` или `False`, или тип данных, который неявно преобразуется в `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-120">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>  
  
 `elseifstatements`  
 <span data-ttu-id="a0b5f-121">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-121">Optional.</span></span> <span data-ttu-id="a0b5f-122">Один или несколько следующих инструкций `ElseIf`... `Then` , которые выполняются, если `elseifcondition` равен `True`.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-122">One or more statements following `ElseIf`...`Then` that are executed if `elseifcondition` evaluates to `True`.</span></span>  
  
 `elsestatements`  
 <span data-ttu-id="a0b5f-123">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-123">Optional.</span></span> <span data-ttu-id="a0b5f-124">Один или несколько инструкций, которые выполняются, если предыдущие `condition` или `elseifcondition` выражение, результатом которого является `True`.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-124">One or more statements that are executed if no previous `condition` or `elseifcondition` expression evaluates to `True`.</span></span>  
  
 `End If`  
 <span data-ttu-id="a0b5f-125">Завершает многострочном `If`... `Then`... `Else` блок.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-125">Terminates the multiline version of `If`...`Then`...`Else` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0b5f-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0b5f-126">Remarks</span></span>  
  
### <a name="multiline-syntax"></a><span data-ttu-id="a0b5f-127">Многострочный синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0b5f-127">Multiline syntax</span></span>  
 <span data-ttu-id="a0b5f-128">Когда `If`... `Then`... `Else` обнаружил инструкции, `condition` проверяется.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-128">When an `If`...`Then`...`Else` statement is encountered, `condition` is tested.</span></span> <span data-ttu-id="a0b5f-129">Если `condition` — `True`, инструкции, следующие за `Then` выполняются.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-129">If `condition` is `True`, the statements following `Then` are executed.</span></span> <span data-ttu-id="a0b5f-130">Если `condition` — `False`, каждая `ElseIf` инструкция (если таковые имеются) вычисляется в порядке.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-130">If `condition` is `False`, each `ElseIf` statement (if there are any) is evaluated in order.</span></span> <span data-ttu-id="a0b5f-131">Когда `True` `elseifcondition` находится сразу за соответствующим операторы `ElseIf` выполняются.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-131">When a `True` `elseifcondition` is found, the statements immediately following the associated `ElseIf` are executed.</span></span> <span data-ttu-id="a0b5f-132">Если не `elseifcondition` равен `True`, или при наличии не `ElseIf` инструкций, инструкции, следующие за `Else` выполняются.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-132">If no `elseifcondition` evaluates to `True`, or if there are no `ElseIf` statements, the statements following `Else` are executed.</span></span> <span data-ttu-id="a0b5f-133">После выполнения следующей инструкции `Then`, `ElseIf`, или `Else`, выполнение продолжается с оператору, следующему `End If`.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-133">After executing the statements following `Then`, `ElseIf`, or `Else`, execution continues with the statement following `End If`.</span></span>  
  
 <span data-ttu-id="a0b5f-134">`ElseIf` И `Else` предложения имеют одновременно необязательно.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-134">The `ElseIf` and `Else` clauses are both optional.</span></span> <span data-ttu-id="a0b5f-135">Можно использовать столько `ElseIf` предложений, что и у вас должны быть в `If`... `Then`... `Else` инструкции, но это не `ElseIf` предложение может следовать за `Else` предложения.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-135">You can have as many `ElseIf` clauses as you want in an `If`...`Then`...`Else` statement, but no `ElseIf` clause can appear after an `Else` clause.</span></span> <span data-ttu-id="a0b5f-136">`If`... `Then`... `Else` операторы могут быть вложены друг с другом.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-136">`If`...`Then`...`Else` statements can be nested within each other.</span></span>  
  
 <span data-ttu-id="a0b5f-137">В синтаксисе многострочных `If` инструкция должна быть единственной инструкцией в первой строке.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-137">In the multiline syntax, the `If` statement must be the only statement on the first line.</span></span> <span data-ttu-id="a0b5f-138">`ElseIf`, `Else`, И `End If` инструкций может стоять только метку строки.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-138">The `ElseIf`, `Else`, and `End If` statements can be preceded only by a line label.</span></span> <span data-ttu-id="a0b5f-139">`If`... `Then`... `Else` блок должен завершаться `End If` инструкции.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-139">The `If`...`Then`...`Else` block must end with an `End If` statement.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="a0b5f-140">[Выберите... Оператор выбора](../../../visual-basic/language-reference/statements/select-case-statement.md) могут быть более полезными при оценке единственное выражение, которое имеет несколько возможных значений.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-140">The [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) might be more useful when you evaluate a single expression that has several possible values.</span></span>  
  
### <a name="single-line-syntax"></a><span data-ttu-id="a0b5f-141">Однострочный синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0b5f-141">Single-Line syntax</span></span>  
 <span data-ttu-id="a0b5f-142">Однострочный синтаксис для одного условия с кодом можно использовать для выполнения, если он имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-142">You can use the single-line syntax for a single condition with code to execute if it's true.</span></span> <span data-ttu-id="a0b5f-143">Однако многострочный синтаксис предоставляет большую структуру, гибкость и удобнее для чтения, обслуживания и отладки.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-143">However, the multiple-line syntax provides more structure and flexibility and is easier to read, maintain, and debug.</span></span>  
  
 <span data-ttu-id="a0b5f-144">Какие следующим `Then` ключевое слово проверяется, чтобы определить, является ли инструкция однострочный `If`.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-144">What follows the `Then` keyword is examined to determine whether a statement is a single-line `If`.</span></span> <span data-ttu-id="a0b5f-145">Если ничего, кроме комментарий после `Then` в той же строке, инструкция обрабатывается как однострочный `If` инструкции.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-145">If anything other than a comment appears after `Then` on the same line, the statement is treated as a single-line `If` statement.</span></span> <span data-ttu-id="a0b5f-146">Если `Then` не существует, он должен быть начала многострочного `If`... `Then`... `Else`.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-146">If `Then` is absent, it must be the start of a multiple-line `If`...`Then`...`Else`.</span></span>  
  
 <span data-ttu-id="a0b5f-147">В синтаксисе однострочный может иметь несколько инструкций, в результате выполнения `If`... `Then` принятия решений.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-147">In the single-line syntax, you can have multiple statements executed as the result of an `If`...`Then` decision.</span></span> <span data-ttu-id="a0b5f-148">Все операторы должны находиться в той же строке и быть разделены точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-148">All statements must be on the same line and be separated by colons.</span></span>  

## <a name="multiline-syntax-example"></a><span data-ttu-id="a0b5f-149">Пример синтаксиса многострочный</span><span class="sxs-lookup"><span data-stu-id="a0b5f-149">Multiline syntax example</span></span>

<a name="multi-line"></a>
 
 <span data-ttu-id="a0b5f-150">В следующем примере показано использование многострочный синтаксис `If`... `Then`... `Else` инструкции.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-150">The following example illustrates the use of the multiline syntax of the `If`...`Then`...`Else` statement.</span></span>  
  
 [!code-vb[VbVbalrStatements#101](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_1.vb?highlight=11,14,17,19)]

## <a name="nested-syntax-example"></a><span data-ttu-id="a0b5f-151">Пример вложенной синтаксиса</span><span class="sxs-lookup"><span data-stu-id="a0b5f-151">Nested syntax example</span></span>

<a name="nested"></a>

 <span data-ttu-id="a0b5f-152">В следующем примере показаны вложенные `If`... `Then`... `Else` инструкции.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-152">The following example contains nested `If`...`Then`...`Else` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#102](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_2.vb?highlight=14,15,17,19,20,21,23,25,26,28)]

## <a name="single-line-syntax-example"></a><span data-ttu-id="a0b5f-153">Пример синтаксиса для одной строки</span><span class="sxs-lookup"><span data-stu-id="a0b5f-153">Single-Line syntax example</span></span>
  
<a name="single-line"></a> <span data-ttu-id="a0b5f-154">Следующий пример иллюстрирует использование синтаксиса одну строку.</span><span class="sxs-lookup"><span data-stu-id="a0b5f-154">The following example illustrates the use of the single-line syntax.</span></span>  
  
 [!code-vb[VbVbalrStatements#103](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_3.vb?highlight=18)]
  
## <a name="see-also"></a><span data-ttu-id="a0b5f-155">См. также</span><span class="sxs-lookup"><span data-stu-id="a0b5f-155">See also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>  
 <xref:Microsoft.VisualBasic.Interaction.Switch%2A>  
 [<span data-ttu-id="a0b5f-156">Директивы #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="a0b5f-156">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="a0b5f-157">Оператор Select...Case</span><span class="sxs-lookup"><span data-stu-id="a0b5f-157">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)  
 [<span data-ttu-id="a0b5f-158">Вложенные структуры управления</span><span class="sxs-lookup"><span data-stu-id="a0b5f-158">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="a0b5f-159">Структуры решений</span><span class="sxs-lookup"><span data-stu-id="a0b5f-159">Decision Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="a0b5f-160">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a0b5f-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [<span data-ttu-id="a0b5f-161">Оператор If</span><span class="sxs-lookup"><span data-stu-id="a0b5f-161">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
