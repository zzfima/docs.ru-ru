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
ms.openlocfilehash: d91a913d515f36a6b974850bc30079b000a919b4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58842698"
---
# <a name="ifthenelse-statement-visual-basic"></a><span data-ttu-id="5cca1-102">Оператор If...Then...Else (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5cca1-102">If...Then...Else Statement (Visual Basic)</span></span>
<span data-ttu-id="5cca1-103">Выполняет ту или иную группу операторов в зависимости от значения выражения.</span><span class="sxs-lookup"><span data-stu-id="5cca1-103">Conditionally executes a group of statements, depending on the value of an expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cca1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5cca1-104">Syntax</span></span>  
  
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

## <a name="quick-links-to-example-code"></a><span data-ttu-id="5cca1-105">Быстрые ссылки на пример кода</span><span class="sxs-lookup"><span data-stu-id="5cca1-105">Quick links to example code</span></span>

<span data-ttu-id="5cca1-106">Эта статья содержит несколько примеров, иллюстрирующих использование `If`... `Then`... `Else` инструкции:</span><span class="sxs-lookup"><span data-stu-id="5cca1-106">This article includes several examples that illustrate uses of the `If`...`Then`...`Else` statement:</span></span>

* [<span data-ttu-id="5cca1-107">Пример синтаксиса многострочный</span><span class="sxs-lookup"><span data-stu-id="5cca1-107">Multiline syntax example</span></span>](#multi-line)
* [<span data-ttu-id="5cca1-108">Пример вложенных синтаксиса</span><span class="sxs-lookup"><span data-stu-id="5cca1-108">Nested syntax example</span></span>](#nested)
* [<span data-ttu-id="5cca1-109">Пример синтаксиса однострочный</span><span class="sxs-lookup"><span data-stu-id="5cca1-109">Single-line syntax example</span></span>](#single-line)

## <a name="parts"></a><span data-ttu-id="5cca1-110">Части</span><span class="sxs-lookup"><span data-stu-id="5cca1-110">Parts</span></span>  
 `condition`  
 <span data-ttu-id="5cca1-111">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="5cca1-111">Required.</span></span> <span data-ttu-id="5cca1-112">выражение.</span><span class="sxs-lookup"><span data-stu-id="5cca1-112">Expression.</span></span> <span data-ttu-id="5cca1-113">Должны иметь `True` или `False`, или тип данных, который неявно преобразуется к типу `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="5cca1-113">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>  
  
 <span data-ttu-id="5cca1-114">Если выражение является [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` переменной, результатом которого является [ничего не](../../../visual-basic/language-reference/nothing.md), условие рассматривается как выражение является `False` и `Else` выполняется блок.</span><span class="sxs-lookup"><span data-stu-id="5cca1-114">If the expression is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the condition is treated as if the expression is `False` and the `Else` block is executed.</span></span>  
  
 `Then`  
 <span data-ttu-id="5cca1-115">Требуется однострочный синтаксис; необязательно для многострочный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="5cca1-115">Required in the single-line syntax; optional in the multiline syntax.</span></span>  
  
 `statements`  
 <span data-ttu-id="5cca1-116">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="5cca1-116">Optional.</span></span> <span data-ttu-id="5cca1-117">Один или несколько следующих инструкций `If`... `Then` , которые выполняются, если `condition` принимает значение `True`.</span><span class="sxs-lookup"><span data-stu-id="5cca1-117">One or more statements following `If`...`Then` that are executed if `condition` evaluates to `True`.</span></span>  
  
 `elseifcondition`  
 <span data-ttu-id="5cca1-118">Обязателен, если `ElseIf` присутствует.</span><span class="sxs-lookup"><span data-stu-id="5cca1-118">Required if `ElseIf` is present.</span></span> <span data-ttu-id="5cca1-119">выражение.</span><span class="sxs-lookup"><span data-stu-id="5cca1-119">Expression.</span></span> <span data-ttu-id="5cca1-120">Должны иметь `True` или `False`, или тип данных, который неявно преобразуется к типу `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="5cca1-120">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>  
  
 `elseifstatements`  
 <span data-ttu-id="5cca1-121">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="5cca1-121">Optional.</span></span> <span data-ttu-id="5cca1-122">Один или несколько следующих инструкций `ElseIf`... `Then` , которые выполняются, если `elseifcondition` принимает значение `True`.</span><span class="sxs-lookup"><span data-stu-id="5cca1-122">One or more statements following `ElseIf`...`Then` that are executed if `elseifcondition` evaluates to `True`.</span></span>  
  
 `elsestatements`  
 <span data-ttu-id="5cca1-123">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="5cca1-123">Optional.</span></span> <span data-ttu-id="5cca1-124">Один или несколько инструкций, которые выполняются, если предыдущего `condition` или `elseifcondition` выражение, результатом которого является `True`.</span><span class="sxs-lookup"><span data-stu-id="5cca1-124">One or more statements that are executed if no previous `condition` or `elseifcondition` expression evaluates to `True`.</span></span>  
  
 `End If`  
 <span data-ttu-id="5cca1-125">Завершает многострочном `If`... `Then`... `Else` блок.</span><span class="sxs-lookup"><span data-stu-id="5cca1-125">Terminates the multiline version of `If`...`Then`...`Else` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5cca1-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="5cca1-126">Remarks</span></span>  
  
### <a name="multiline-syntax"></a><span data-ttu-id="5cca1-127">Многострочный синтаксис</span><span class="sxs-lookup"><span data-stu-id="5cca1-127">Multiline syntax</span></span>  
 <span data-ttu-id="5cca1-128">Когда `If`... `Then`... `Else` встречается, `condition` тестируется.</span><span class="sxs-lookup"><span data-stu-id="5cca1-128">When an `If`...`Then`...`Else` statement is encountered, `condition` is tested.</span></span> <span data-ttu-id="5cca1-129">Если `condition` — `True`, инструкции, следующие за `Then` выполняются.</span><span class="sxs-lookup"><span data-stu-id="5cca1-129">If `condition` is `True`, the statements following `Then` are executed.</span></span> <span data-ttu-id="5cca1-130">Если `condition` — `False`, каждая `ElseIf` инструкция (если таковые имеются) оценивается по очереди.</span><span class="sxs-lookup"><span data-stu-id="5cca1-130">If `condition` is `False`, each `ElseIf` statement (if there are any) is evaluated in order.</span></span> <span data-ttu-id="5cca1-131">Когда `True` `elseifcondition` найден, операторы, следующие непосредственно связанный `ElseIf` выполняются.</span><span class="sxs-lookup"><span data-stu-id="5cca1-131">When a `True` `elseifcondition` is found, the statements immediately following the associated `ElseIf` are executed.</span></span> <span data-ttu-id="5cca1-132">Если не `elseifcondition` принимает значение `True`, или если не `ElseIf` операторы, инструкции, следующие за `Else` выполняются.</span><span class="sxs-lookup"><span data-stu-id="5cca1-132">If no `elseifcondition` evaluates to `True`, or if there are no `ElseIf` statements, the statements following `Else` are executed.</span></span> <span data-ttu-id="5cca1-133">После выполнения следующей инструкции `Then`, `ElseIf`, или `Else`, выполнение продолжается с оператор, следующий `End If`.</span><span class="sxs-lookup"><span data-stu-id="5cca1-133">After executing the statements following `Then`, `ElseIf`, or `Else`, execution continues with the statement following `End If`.</span></span>  
  
 <span data-ttu-id="5cca1-134">`ElseIf` И `Else` являются оба необязательно.</span><span class="sxs-lookup"><span data-stu-id="5cca1-134">The `ElseIf` and `Else` clauses are both optional.</span></span> <span data-ttu-id="5cca1-135">Может быть столько `ElseIf` предложения, как вы хотите `If`... `Then`... `Else` инструкции, но не `ElseIf` предложения может появляться после `Else` предложение.</span><span class="sxs-lookup"><span data-stu-id="5cca1-135">You can have as many `ElseIf` clauses as you want in an `If`...`Then`...`Else` statement, but no `ElseIf` clause can appear after an `Else` clause.</span></span> <span data-ttu-id="5cca1-136">`If`... `Then`... `Else` операторы могут быть вложены друг с другом.</span><span class="sxs-lookup"><span data-stu-id="5cca1-136">`If`...`Then`...`Else` statements can be nested within each other.</span></span>  
  
 <span data-ttu-id="5cca1-137">В многострочных синтаксисе `If` инструкция должна быть единственной инструкцией в первой строке.</span><span class="sxs-lookup"><span data-stu-id="5cca1-137">In the multiline syntax, the `If` statement must be the only statement on the first line.</span></span> <span data-ttu-id="5cca1-138">`ElseIf`, `Else`, И `End If` инструкций может стоять только метку строки.</span><span class="sxs-lookup"><span data-stu-id="5cca1-138">The `ElseIf`, `Else`, and `End If` statements can be preceded only by a line label.</span></span> <span data-ttu-id="5cca1-139">`If`... `Then`... `Else` блок должен завершаться `End If` инструкции.</span><span class="sxs-lookup"><span data-stu-id="5cca1-139">The `If`...`Then`...`Else` block must end with an `End If` statement.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="5cca1-140">[Выберите... Оператор выбора](../../../visual-basic/language-reference/statements/select-case-statement.md) могут быть более полезными при оценке одно выражение, которое имеет несколько возможных значений.</span><span class="sxs-lookup"><span data-stu-id="5cca1-140">The [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) might be more useful when you evaluate a single expression that has several possible values.</span></span>  
  
### <a name="single-line-syntax"></a><span data-ttu-id="5cca1-141">Однострочный синтаксис</span><span class="sxs-lookup"><span data-stu-id="5cca1-141">Single-Line syntax</span></span>  
 <span data-ttu-id="5cca1-142">Можно использовать синтаксис одну строку для отдельного условия с кодом для выполнения, если он имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="5cca1-142">You can use the single-line syntax for a single condition with code to execute if it's true.</span></span> <span data-ttu-id="5cca1-143">Однако многострочный синтаксис предоставляет большую структуру, гибкость и проще читать, обслуживать и отладки.</span><span class="sxs-lookup"><span data-stu-id="5cca1-143">However, the multiple-line syntax provides more structure and flexibility and is easier to read, maintain, and debug.</span></span>  
  
 <span data-ttu-id="5cca1-144">Ниже описано `Then` ключевое слово анализируется для определения, является ли оператор однострочный `If`.</span><span class="sxs-lookup"><span data-stu-id="5cca1-144">What follows the `Then` keyword is examined to determine whether a statement is a single-line `If`.</span></span> <span data-ttu-id="5cca1-145">Если ничего, кроме комментарий появляется после `Then` в той же строке, инструкция обрабатывается как однострочный `If` инструкции.</span><span class="sxs-lookup"><span data-stu-id="5cca1-145">If anything other than a comment appears after `Then` on the same line, the statement is treated as a single-line `If` statement.</span></span> <span data-ttu-id="5cca1-146">Если `Then` отсутствует, он должен быть начала многострочного `If`... `Then`... `Else`.</span><span class="sxs-lookup"><span data-stu-id="5cca1-146">If `Then` is absent, it must be the start of a multiple-line `If`...`Then`...`Else`.</span></span>  
  
 <span data-ttu-id="5cca1-147">В синтаксисе одной строки, можно использовать несколько операторов, в результате выполнения `If`... `Then` принятия решений.</span><span class="sxs-lookup"><span data-stu-id="5cca1-147">In the single-line syntax, you can have multiple statements executed as the result of an `If`...`Then` decision.</span></span> <span data-ttu-id="5cca1-148">Все операторы должны находиться в той же строке и быть разделены точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="5cca1-148">All statements must be on the same line and be separated by colons.</span></span>  

## <a name="multiline-syntax-example"></a><span data-ttu-id="5cca1-149">Пример синтаксиса многострочный</span><span class="sxs-lookup"><span data-stu-id="5cca1-149">Multiline syntax example</span></span>

<a name="multi-line"></a>
 
 <span data-ttu-id="5cca1-150">Следующий пример иллюстрирует использование многострочный синтаксис `If`... `Then`... `Else` инструкции.</span><span class="sxs-lookup"><span data-stu-id="5cca1-150">The following example illustrates the use of the multiline syntax of the `If`...`Then`...`Else` statement.</span></span>  
  
 [!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a><span data-ttu-id="5cca1-151">Пример вложенных синтаксиса</span><span class="sxs-lookup"><span data-stu-id="5cca1-151">Nested syntax example</span></span>

<a name="nested"></a>

 <span data-ttu-id="5cca1-152">В следующем примере показаны вложенные `If`... `Then`... `Else` инструкций.</span><span class="sxs-lookup"><span data-stu-id="5cca1-152">The following example contains nested `If`...`Then`...`Else` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a><span data-ttu-id="5cca1-153">Пример синтаксиса однострочный</span><span class="sxs-lookup"><span data-stu-id="5cca1-153">Single-Line syntax example</span></span>
  
<a name="single-line"></a> <span data-ttu-id="5cca1-154">Следующий пример иллюстрирует использование синтаксиса одну строку.</span><span class="sxs-lookup"><span data-stu-id="5cca1-154">The following example illustrates the use of the single-line syntax.</span></span>  
  
 [!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]
  
## <a name="see-also"></a><span data-ttu-id="5cca1-155">См. также</span><span class="sxs-lookup"><span data-stu-id="5cca1-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [<span data-ttu-id="5cca1-156">Директивы #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="5cca1-156">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="5cca1-157">Оператор Select...Case</span><span class="sxs-lookup"><span data-stu-id="5cca1-157">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="5cca1-158">Вложенные структуры управления</span><span class="sxs-lookup"><span data-stu-id="5cca1-158">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="5cca1-159">Структуры решений</span><span class="sxs-lookup"><span data-stu-id="5cca1-159">Decision Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="5cca1-160">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5cca1-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [<span data-ttu-id="5cca1-161">Оператор If</span><span class="sxs-lookup"><span data-stu-id="5cca1-161">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
