---
title: Оператор Exit (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Exit
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- Exit statement [Visual Basic]
- program termination
- execution [Visual Basic], stopping
ms.assetid: 760bfb32-5c3f-4bdb-a432-9a6001c92db7
ms.openlocfilehash: 1f386694bd7425ee530b9305ab684b730f9b73c8
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832636"
---
# <a name="exit-statement-visual-basic"></a><span data-ttu-id="3733d-102">Оператор Exit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3733d-102">Exit Statement (Visual Basic)</span></span>
<span data-ttu-id="3733d-103">Выходит из процедуры или блока и немедленно передает управление оператору после вызова процедуры или определения блока.</span><span class="sxs-lookup"><span data-stu-id="3733d-103">Exits a procedure or block and transfers control immediately to the statement following the procedure call or the block definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3733d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3733d-104">Syntax</span></span>  
  
```  
Exit { Do | For | Function | Property | Select | Sub | Try | While }  
```  
  
## <a name="statements"></a><span data-ttu-id="3733d-105">Операторы</span><span class="sxs-lookup"><span data-stu-id="3733d-105">Statements</span></span>  
 `Exit Do`  
 <span data-ttu-id="3733d-106">Немедленно завершает работу `Do` цикл, в котором он содержится.</span><span class="sxs-lookup"><span data-stu-id="3733d-106">Immediately exits the `Do` loop in which it appears.</span></span> <span data-ttu-id="3733d-107">Выполнение продолжается с оператор, следующий `Loop` инструкции.</span><span class="sxs-lookup"><span data-stu-id="3733d-107">Execution continues with the statement following the `Loop` statement.</span></span> <span data-ttu-id="3733d-108">`Exit Do` можно использовать только внутри `Do` цикла.</span><span class="sxs-lookup"><span data-stu-id="3733d-108">`Exit Do` can be used only inside a `Do` loop.</span></span> <span data-ttu-id="3733d-109">При использовании внутри вложенной `Do` циклы, `Exit Do` выходит из самого внутреннего цикла и передает управление повысить уровень вложенности.</span><span class="sxs-lookup"><span data-stu-id="3733d-109">When used within nested `Do` loops, `Exit Do` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>  
  
 `Exit For`  
 <span data-ttu-id="3733d-110">Немедленно завершает работу `For` цикл, в котором он содержится.</span><span class="sxs-lookup"><span data-stu-id="3733d-110">Immediately exits the `For` loop in which it appears.</span></span> <span data-ttu-id="3733d-111">Выполнение продолжается с оператор, следующий `Next` инструкции.</span><span class="sxs-lookup"><span data-stu-id="3733d-111">Execution continues with the statement following the `Next` statement.</span></span> <span data-ttu-id="3733d-112">`Exit For` можно использовать только внутри `For`... `Next` или `For Each`... `Next` цикла.</span><span class="sxs-lookup"><span data-stu-id="3733d-112">`Exit For` can be used only inside a `For`...`Next` or `For Each`...`Next` loop.</span></span> <span data-ttu-id="3733d-113">При использовании внутри вложенной `For` циклы, `Exit For` выходит из самого внутреннего цикла и передает управление повысить уровень вложенности.</span><span class="sxs-lookup"><span data-stu-id="3733d-113">When used within nested `For` loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>  
  
 `Exit Function`  
 <span data-ttu-id="3733d-114">Немедленно завершает работу `Function` процедуры, в котором он находится.</span><span class="sxs-lookup"><span data-stu-id="3733d-114">Immediately exits the `Function` procedure in which it appears.</span></span> <span data-ttu-id="3733d-115">Выполнение продолжается с оператора, следующего за оператором, вызвавшим `Function` процедуры.</span><span class="sxs-lookup"><span data-stu-id="3733d-115">Execution continues with the statement following the statement that called the `Function` procedure.</span></span> <span data-ttu-id="3733d-116">`Exit Function` можно использовать только внутри `Function` процедуры.</span><span class="sxs-lookup"><span data-stu-id="3733d-116">`Exit Function` can be used only inside a `Function` procedure.</span></span>  
  
 <span data-ttu-id="3733d-117">Чтобы задать возвращаемое значение, можно присвоить значение имени функции в строке перед `Exit Function` инструкции.</span><span class="sxs-lookup"><span data-stu-id="3733d-117">To specify a return value, you can assign the value to the function name on a line before the `Exit Function` statement.</span></span> <span data-ttu-id="3733d-118">Чтобы назначить возвращаемое значение и выхода из функции в одной инструкции, можно использовать [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3733d-118">To assign the return value and exit the function in one statement, you can instead use the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 `Exit Property`  
 <span data-ttu-id="3733d-119">Немедленно завершает работу `Property` процедуры, в котором он находится.</span><span class="sxs-lookup"><span data-stu-id="3733d-119">Immediately exits the `Property` procedure in which it appears.</span></span> <span data-ttu-id="3733d-120">Выполнение продолжается с оператора, который вызывается `Property` процедуры, то есть с помощью инструкции запроса и установки значения свойства.</span><span class="sxs-lookup"><span data-stu-id="3733d-120">Execution continues with the statement that called the `Property` procedure, that is, with the statement requesting or setting the property's value.</span></span> <span data-ttu-id="3733d-121">`Exit Property` можно использовать только внутри свойства `Get` или `Set` процедуры.</span><span class="sxs-lookup"><span data-stu-id="3733d-121">`Exit Property` can be used only inside a property's `Get` or `Set` procedure.</span></span>  
  
 <span data-ttu-id="3733d-122">Чтобы указать возвращаемое значение в `Get` процедуры, можно присвоить значение имени функции в строке перед `Exit Property` инструкции.</span><span class="sxs-lookup"><span data-stu-id="3733d-122">To specify a return value in a `Get` procedure, you can assign the value to the function name on a line before the `Exit Property` statement.</span></span> <span data-ttu-id="3733d-123">Чтобы назначить возвращаемое значение и выхода `Get` процедуры в одной инструкции, можно вместо этого использовать `Return` инструкции.</span><span class="sxs-lookup"><span data-stu-id="3733d-123">To assign the return value and exit the `Get` procedure in one statement, you can instead use the `Return` statement.</span></span>  
  
 <span data-ttu-id="3733d-124">В `Set` процедуре `Exit Property` оператор эквивалентен `Return` инструкции.</span><span class="sxs-lookup"><span data-stu-id="3733d-124">In a `Set` procedure, the `Exit Property` statement is equivalent to the `Return` statement.</span></span>  
  
 `Exit Select`  
 <span data-ttu-id="3733d-125">Немедленно завершает работу `Select Case` блока, в котором находится этот элемент.</span><span class="sxs-lookup"><span data-stu-id="3733d-125">Immediately exits the `Select Case` block in which it appears.</span></span> <span data-ttu-id="3733d-126">Выполнение продолжается с оператор, следующий `End Select` инструкции.</span><span class="sxs-lookup"><span data-stu-id="3733d-126">Execution continues with the statement following the `End Select` statement.</span></span> <span data-ttu-id="3733d-127">`Exit Select` можно использовать только внутри `Select Case` инструкции.</span><span class="sxs-lookup"><span data-stu-id="3733d-127">`Exit Select` can be used only inside a `Select Case` statement.</span></span>  
  
 `Exit Sub`  
 <span data-ttu-id="3733d-128">Немедленно завершает работу `Sub` процедуры, в котором он находится.</span><span class="sxs-lookup"><span data-stu-id="3733d-128">Immediately exits the `Sub` procedure in which it appears.</span></span> <span data-ttu-id="3733d-129">Выполнение продолжается с оператора, следующего за оператором, вызвавшим `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="3733d-129">Execution continues with the statement following the statement that called the `Sub` procedure.</span></span> <span data-ttu-id="3733d-130">`Exit Sub` можно использовать только внутри `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="3733d-130">`Exit Sub` can be used only inside a `Sub` procedure.</span></span>  
  
 <span data-ttu-id="3733d-131">В `Sub` процедуре `Exit Sub` оператор эквивалентен `Return` инструкции.</span><span class="sxs-lookup"><span data-stu-id="3733d-131">In a `Sub` procedure, the `Exit Sub` statement is equivalent to the `Return` statement.</span></span>  
  
 `Exit Try`  
 <span data-ttu-id="3733d-132">Немедленно завершает работу `Try` или `Catch` блока, в котором находится этот элемент.</span><span class="sxs-lookup"><span data-stu-id="3733d-132">Immediately exits the `Try` or `Catch` block in which it appears.</span></span> <span data-ttu-id="3733d-133">Выполнение продолжается с `Finally` блокировать, если таковой имеется, или оператор, следующий `End Try` инструкции, которые в противном случае.</span><span class="sxs-lookup"><span data-stu-id="3733d-133">Execution continues with the `Finally` block if there is one, or with the statement following the `End Try` statement otherwise.</span></span> <span data-ttu-id="3733d-134">`Exit Try` можно использовать только внутри `Try` или `Catch` блока, а не внутри `Finally` блока.</span><span class="sxs-lookup"><span data-stu-id="3733d-134">`Exit Try` can be used only inside a `Try` or `Catch` block, and not inside a `Finally` block.</span></span>  
  
 `Exit While`  
 <span data-ttu-id="3733d-135">Немедленно завершает работу `While` цикл, в котором он содержится.</span><span class="sxs-lookup"><span data-stu-id="3733d-135">Immediately exits the `While` loop in which it appears.</span></span> <span data-ttu-id="3733d-136">Выполнение продолжается с оператор, следующий `End While` инструкции.</span><span class="sxs-lookup"><span data-stu-id="3733d-136">Execution continues with the statement following the `End While` statement.</span></span> <span data-ttu-id="3733d-137">`Exit While` можно использовать только внутри `While` цикла.</span><span class="sxs-lookup"><span data-stu-id="3733d-137">`Exit While` can be used only inside a `While` loop.</span></span> <span data-ttu-id="3733d-138">При использовании внутри вложенной `While` циклы, `Exit While` передает управление в цикл, находящийся на один уровень выше цикла где `Exit While` происходит.</span><span class="sxs-lookup"><span data-stu-id="3733d-138">When used within nested `While` loops, `Exit While` transfers control to the loop that is one nested level above the loop where `Exit While` occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3733d-139">Примечания</span><span class="sxs-lookup"><span data-stu-id="3733d-139">Remarks</span></span>  
 <span data-ttu-id="3733d-140">Не следует путать `Exit` инструкции с `End` инструкций.</span><span class="sxs-lookup"><span data-stu-id="3733d-140">Do not confuse `Exit` statements with `End` statements.</span></span> <span data-ttu-id="3733d-141">`Exit` не определяет конец оператора.</span><span class="sxs-lookup"><span data-stu-id="3733d-141">`Exit` does not define the end of a statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3733d-142">Пример</span><span class="sxs-lookup"><span data-stu-id="3733d-142">Example</span></span>  
 <span data-ttu-id="3733d-143">В следующем примере, останавливающее цикл в условие цикла при `index` переменной превышает 100.</span><span class="sxs-lookup"><span data-stu-id="3733d-143">In the following example, the loop condition stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="3733d-144">`If` Оператора цикла, однако вызывает `Exit Do` инструкции для остановки цикла, когда переменная индекса превышает 10.</span><span class="sxs-lookup"><span data-stu-id="3733d-144">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a><span data-ttu-id="3733d-145">Пример</span><span class="sxs-lookup"><span data-stu-id="3733d-145">Example</span></span>  
 <span data-ttu-id="3733d-146">В следующем примере присваивается значение имени функции `myFunction`, а затем использует `Exit Function` для возврата из функции.</span><span class="sxs-lookup"><span data-stu-id="3733d-146">The following example assigns the return value to the function name `myFunction`, and then uses `Exit Function` to return from the function.</span></span>  
  
 [!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]  
  
## <a name="example"></a><span data-ttu-id="3733d-147">Пример</span><span class="sxs-lookup"><span data-stu-id="3733d-147">Example</span></span>  
 <span data-ttu-id="3733d-148">В следующем примере используется [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md) присвойте возвращаемое значение и выхода из функции.</span><span class="sxs-lookup"><span data-stu-id="3733d-148">The following example uses the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) to assign the return value and exit the function.</span></span>  
  
 [!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]  
  
## <a name="see-also"></a><span data-ttu-id="3733d-149">См. также</span><span class="sxs-lookup"><span data-stu-id="3733d-149">See also</span></span>

- [<span data-ttu-id="3733d-150">Оператор Continue</span><span class="sxs-lookup"><span data-stu-id="3733d-150">Continue Statement</span></span>](../../../visual-basic/language-reference/statements/continue-statement.md)
- [<span data-ttu-id="3733d-151">Оператор Do...Loop</span><span class="sxs-lookup"><span data-stu-id="3733d-151">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="3733d-152">Оператор End</span><span class="sxs-lookup"><span data-stu-id="3733d-152">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
- [<span data-ttu-id="3733d-153">Оператор For Each...Next</span><span class="sxs-lookup"><span data-stu-id="3733d-153">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="3733d-154">Оператор For...Next</span><span class="sxs-lookup"><span data-stu-id="3733d-154">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="3733d-155">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="3733d-155">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="3733d-156">Оператор Return</span><span class="sxs-lookup"><span data-stu-id="3733d-156">Return Statement</span></span>](../../../visual-basic/language-reference/statements/return-statement.md)
- [<span data-ttu-id="3733d-157">Оператор Stop</span><span class="sxs-lookup"><span data-stu-id="3733d-157">Stop Statement</span></span>](../../../visual-basic/language-reference/statements/stop-statement.md)
- [<span data-ttu-id="3733d-158">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="3733d-158">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="3733d-159">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="3733d-159">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
