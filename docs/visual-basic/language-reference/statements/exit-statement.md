---
title: Оператор Exit
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
ms.openlocfilehash: 1bfe81428fd3c50663fd8978e05c6a945cd47df8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345940"
---
# <a name="exit-statement-visual-basic"></a><span data-ttu-id="26b51-102">Оператор Exit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26b51-102">Exit Statement (Visual Basic)</span></span>

<span data-ttu-id="26b51-103">Выходит из процедуры или блока и немедленно передает управление оператору после вызова процедуры или определения блока.</span><span class="sxs-lookup"><span data-stu-id="26b51-103">Exits a procedure or block and transfers control immediately to the statement following the procedure call or the block definition.</span></span>

## <a name="syntax"></a><span data-ttu-id="26b51-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="26b51-104">Syntax</span></span>

```vb
Exit { Do | For | Function | Property | Select | Sub | Try | While }
```

## <a name="statements"></a><span data-ttu-id="26b51-105">Операторы</span><span class="sxs-lookup"><span data-stu-id="26b51-105">Statements</span></span>

 `Exit Do`  
 <span data-ttu-id="26b51-106">Немедленно выходит из цикла `Do`, в котором он отображается.</span><span class="sxs-lookup"><span data-stu-id="26b51-106">Immediately exits the `Do` loop in which it appears.</span></span> <span data-ttu-id="26b51-107">Выполнение продолжится с оператора, следующего за оператором `Loop`.</span><span class="sxs-lookup"><span data-stu-id="26b51-107">Execution continues with the statement following the `Loop` statement.</span></span> <span data-ttu-id="26b51-108">`Exit Do` можно использовать только в цикле `Do`.</span><span class="sxs-lookup"><span data-stu-id="26b51-108">`Exit Do` can be used only inside a `Do` loop.</span></span> <span data-ttu-id="26b51-109">При использовании внутри вложенных циклов `Do` `Exit Do` выходит из внутреннего цикла и передает управление следующему более высокому уровню вложенности.</span><span class="sxs-lookup"><span data-stu-id="26b51-109">When used within nested `Do` loops, `Exit Do` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

 `Exit For`  
 <span data-ttu-id="26b51-110">Немедленно выходит из цикла `For`, в котором он отображается.</span><span class="sxs-lookup"><span data-stu-id="26b51-110">Immediately exits the `For` loop in which it appears.</span></span> <span data-ttu-id="26b51-111">Выполнение продолжится с оператора, следующего за оператором `Next`.</span><span class="sxs-lookup"><span data-stu-id="26b51-111">Execution continues with the statement following the `Next` statement.</span></span> <span data-ttu-id="26b51-112">`Exit For` можно использовать только в цикле `For`...`Next` или `For Each`...`Next`.</span><span class="sxs-lookup"><span data-stu-id="26b51-112">`Exit For` can be used only inside a `For`...`Next` or `For Each`...`Next` loop.</span></span> <span data-ttu-id="26b51-113">При использовании внутри вложенных циклов `For` `Exit For` выходит из внутреннего цикла и передает управление следующему более высокому уровню вложенности.</span><span class="sxs-lookup"><span data-stu-id="26b51-113">When used within nested `For` loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

 `Exit Function`  
 <span data-ttu-id="26b51-114">Немедленно завершает работу `Function` процедуры, в которой она отображается.</span><span class="sxs-lookup"><span data-stu-id="26b51-114">Immediately exits the `Function` procedure in which it appears.</span></span> <span data-ttu-id="26b51-115">Выполнение продолжится с оператора, следующего за инструкцией, вызвавшей `Function` процедуру.</span><span class="sxs-lookup"><span data-stu-id="26b51-115">Execution continues with the statement following the statement that called the `Function` procedure.</span></span> <span data-ttu-id="26b51-116">`Exit Function` можно использовать только внутри процедуры `Function`.</span><span class="sxs-lookup"><span data-stu-id="26b51-116">`Exit Function` can be used only inside a `Function` procedure.</span></span>

 <span data-ttu-id="26b51-117">Чтобы указать возвращаемое значение, можно присвоить значение имени функции в строке перед оператором `Exit Function`.</span><span class="sxs-lookup"><span data-stu-id="26b51-117">To specify a return value, you can assign the value to the function name on a line before the `Exit Function` statement.</span></span> <span data-ttu-id="26b51-118">Чтобы присвоить возвращаемое значение и выйти из функции в одной инструкции, можно использовать [оператор return](return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="26b51-118">To assign the return value and exit the function in one statement, you can instead use the [Return Statement](return-statement.md).</span></span>

 `Exit Property`  
 <span data-ttu-id="26b51-119">Немедленно завершает работу `Property` процедуры, в которой она отображается.</span><span class="sxs-lookup"><span data-stu-id="26b51-119">Immediately exits the `Property` procedure in which it appears.</span></span> <span data-ttu-id="26b51-120">Выполнение продолжится с оператора, вызвавшего `Property` процедуру, то есть с инструкцией, запрашивающей или задавая значение свойства.</span><span class="sxs-lookup"><span data-stu-id="26b51-120">Execution continues with the statement that called the `Property` procedure, that is, with the statement requesting or setting the property's value.</span></span> <span data-ttu-id="26b51-121">`Exit Property` можно использовать только внутри `Get` или `Set` процедуры свойства.</span><span class="sxs-lookup"><span data-stu-id="26b51-121">`Exit Property` can be used only inside a property's `Get` or `Set` procedure.</span></span>

 <span data-ttu-id="26b51-122">Чтобы указать возвращаемое значение в `Get` процедуре, можно присвоить значение имени функции в строке перед инструкцией `Exit Property`.</span><span class="sxs-lookup"><span data-stu-id="26b51-122">To specify a return value in a `Get` procedure, you can assign the value to the function name on a line before the `Exit Property` statement.</span></span> <span data-ttu-id="26b51-123">Чтобы присвоить возвращаемое значение и выйти из процедуры `Get` в одном операторе, можно использовать инструкцию `Return`.</span><span class="sxs-lookup"><span data-stu-id="26b51-123">To assign the return value and exit the `Get` procedure in one statement, you can instead use the `Return` statement.</span></span>

 <span data-ttu-id="26b51-124">В `Set`ной процедуре инструкция `Exit Property` эквивалентна инструкции `Return`.</span><span class="sxs-lookup"><span data-stu-id="26b51-124">In a `Set` procedure, the `Exit Property` statement is equivalent to the `Return` statement.</span></span>

 `Exit Select`  
 <span data-ttu-id="26b51-125">Немедленно завершает работу блока `Select Case`, в котором он отображается.</span><span class="sxs-lookup"><span data-stu-id="26b51-125">Immediately exits the `Select Case` block in which it appears.</span></span> <span data-ttu-id="26b51-126">Выполнение продолжится с оператора, следующего за оператором `End Select`.</span><span class="sxs-lookup"><span data-stu-id="26b51-126">Execution continues with the statement following the `End Select` statement.</span></span> <span data-ttu-id="26b51-127">`Exit Select` можно использовать только внутри инструкции `Select Case`.</span><span class="sxs-lookup"><span data-stu-id="26b51-127">`Exit Select` can be used only inside a `Select Case` statement.</span></span>

 `Exit Sub`  
 <span data-ttu-id="26b51-128">Немедленно завершает работу `Sub` процедуры, в которой она отображается.</span><span class="sxs-lookup"><span data-stu-id="26b51-128">Immediately exits the `Sub` procedure in which it appears.</span></span> <span data-ttu-id="26b51-129">Выполнение продолжится с оператора, следующего за инструкцией, вызвавшей `Sub` процедуру.</span><span class="sxs-lookup"><span data-stu-id="26b51-129">Execution continues with the statement following the statement that called the `Sub` procedure.</span></span> <span data-ttu-id="26b51-130">`Exit Sub` можно использовать только внутри процедуры `Sub`.</span><span class="sxs-lookup"><span data-stu-id="26b51-130">`Exit Sub` can be used only inside a `Sub` procedure.</span></span>

 <span data-ttu-id="26b51-131">В `Sub`ной процедуре инструкция `Exit Sub` эквивалентна инструкции `Return`.</span><span class="sxs-lookup"><span data-stu-id="26b51-131">In a `Sub` procedure, the `Exit Sub` statement is equivalent to the `Return` statement.</span></span>

 `Exit Try`  
 <span data-ttu-id="26b51-132">Немедленно завершает работу `Try` или `Catch` блока, в котором он отображается.</span><span class="sxs-lookup"><span data-stu-id="26b51-132">Immediately exits the `Try` or `Catch` block in which it appears.</span></span> <span data-ttu-id="26b51-133">Выполнение продолжится в блоке `Finally`, если таковой имеется, или с оператором, который следует в противном случае с оператором `End Try`.</span><span class="sxs-lookup"><span data-stu-id="26b51-133">Execution continues with the `Finally` block if there is one, or with the statement following the `End Try` statement otherwise.</span></span> <span data-ttu-id="26b51-134">`Exit Try` можно использовать только в блоке `Try` или `Catch`, а не в блоке `Finally`.</span><span class="sxs-lookup"><span data-stu-id="26b51-134">`Exit Try` can be used only inside a `Try` or `Catch` block, and not inside a `Finally` block.</span></span>

 `Exit While`  
 <span data-ttu-id="26b51-135">Немедленно выходит из цикла `While`, в котором он отображается.</span><span class="sxs-lookup"><span data-stu-id="26b51-135">Immediately exits the `While` loop in which it appears.</span></span> <span data-ttu-id="26b51-136">Выполнение продолжится с оператора, следующего за оператором `End While`.</span><span class="sxs-lookup"><span data-stu-id="26b51-136">Execution continues with the statement following the `End While` statement.</span></span> <span data-ttu-id="26b51-137">`Exit While` можно использовать только в цикле `While`.</span><span class="sxs-lookup"><span data-stu-id="26b51-137">`Exit While` can be used only inside a `While` loop.</span></span> <span data-ttu-id="26b51-138">При использовании внутри вложенных циклов `While` `Exit While` передает управление циклу, который является одним вложенным уровнем над циклом, где происходит `Exit While`.</span><span class="sxs-lookup"><span data-stu-id="26b51-138">When used within nested `While` loops, `Exit While` transfers control to the loop that is one nested level above the loop where `Exit While` occurs.</span></span>

## <a name="remarks"></a><span data-ttu-id="26b51-139">Заметки</span><span class="sxs-lookup"><span data-stu-id="26b51-139">Remarks</span></span>

<span data-ttu-id="26b51-140">Не путайте `Exit` инструкции с операторами `End`.</span><span class="sxs-lookup"><span data-stu-id="26b51-140">Do not confuse `Exit` statements with `End` statements.</span></span> <span data-ttu-id="26b51-141">`Exit` не определяет конец инструкции.</span><span class="sxs-lookup"><span data-stu-id="26b51-141">`Exit` does not define the end of a statement.</span></span>

## <a name="example"></a><span data-ttu-id="26b51-142">Пример</span><span class="sxs-lookup"><span data-stu-id="26b51-142">Example</span></span>

<span data-ttu-id="26b51-143">В следующем примере условие цикла останавливает цикл, если `index`ая переменная больше 100.</span><span class="sxs-lookup"><span data-stu-id="26b51-143">In the following example, the loop condition stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="26b51-144">Однако оператор `If` в цикле приводит к тому, что инструкция `Exit Do` останавливает цикл, когда переменная индекса больше 10.</span><span class="sxs-lookup"><span data-stu-id="26b51-144">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>

[!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]

## <a name="example"></a><span data-ttu-id="26b51-145">Пример</span><span class="sxs-lookup"><span data-stu-id="26b51-145">Example</span></span>

<span data-ttu-id="26b51-146">В следующем примере возвращаемое значение присваивается имени функции `myFunction`, а затем для возврата из функции используется `Exit Function`.</span><span class="sxs-lookup"><span data-stu-id="26b51-146">The following example assigns the return value to the function name `myFunction`, and then uses `Exit Function` to return from the function:</span></span>

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

## <a name="example"></a><span data-ttu-id="26b51-147">Пример</span><span class="sxs-lookup"><span data-stu-id="26b51-147">Example</span></span>

<span data-ttu-id="26b51-148">В следующем примере [оператор return](return-statement.md) используется для назначения возвращаемого значения и выхода из функции:</span><span class="sxs-lookup"><span data-stu-id="26b51-148">The following example uses the [Return Statement](return-statement.md) to assign the return value and exit the function:</span></span>

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

## <a name="see-also"></a><span data-ttu-id="26b51-149">См. также</span><span class="sxs-lookup"><span data-stu-id="26b51-149">See also</span></span>

- [<span data-ttu-id="26b51-150">Оператор Continue</span><span class="sxs-lookup"><span data-stu-id="26b51-150">Continue Statement</span></span>](continue-statement.md)
- [<span data-ttu-id="26b51-151">Оператор Do...Loop</span><span class="sxs-lookup"><span data-stu-id="26b51-151">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="26b51-152">Оператор End</span><span class="sxs-lookup"><span data-stu-id="26b51-152">End Statement</span></span>](end-statement.md)
- [<span data-ttu-id="26b51-153">Оператор For Each...Next</span><span class="sxs-lookup"><span data-stu-id="26b51-153">For Each...Next Statement</span></span>](for-each-next-statement.md)
- [<span data-ttu-id="26b51-154">Оператор For...Next</span><span class="sxs-lookup"><span data-stu-id="26b51-154">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="26b51-155">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="26b51-155">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="26b51-156">Оператор Return</span><span class="sxs-lookup"><span data-stu-id="26b51-156">Return Statement</span></span>](return-statement.md)
- [<span data-ttu-id="26b51-157">Оператор Stop</span><span class="sxs-lookup"><span data-stu-id="26b51-157">Stop Statement</span></span>](stop-statement.md)
- [<span data-ttu-id="26b51-158">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="26b51-158">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="26b51-159">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="26b51-159">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
