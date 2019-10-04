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
ms.openlocfilehash: 9c25653809c51662ea5b606ab97be6a9b50d5986
ms.sourcegitcommit: 7bfe1682d9368cf88d43e895d1e80ba2d88c3a99
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2019
ms.locfileid: "71956935"
---
# <a name="exit-statement-visual-basic"></a><span data-ttu-id="7b5d5-102">Оператор Exit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b5d5-102">Exit Statement (Visual Basic)</span></span>

<span data-ttu-id="7b5d5-103">Выходит из процедуры или блока и немедленно передает управление оператору после вызова процедуры или определения блока.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-103">Exits a procedure or block and transfers control immediately to the statement following the procedure call or the block definition.</span></span>

## <a name="syntax"></a><span data-ttu-id="7b5d5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7b5d5-104">Syntax</span></span>

```vb
Exit { Do | For | Function | Property | Select | Sub | Try | While }
```

## <a name="statements"></a><span data-ttu-id="7b5d5-105">Операторы</span><span class="sxs-lookup"><span data-stu-id="7b5d5-105">Statements</span></span>

 `Exit Do`  
 <span data-ttu-id="7b5d5-106">Немедленно завершает работу цикла `Do`, в котором он отображается.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-106">Immediately exits the `Do` loop in which it appears.</span></span> <span data-ttu-id="7b5d5-107">Выполнение продолжится с оператора, следующего за оператором `Loop`.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-107">Execution continues with the statement following the `Loop` statement.</span></span> <span data-ttu-id="7b5d5-108">`Exit Do` можно использовать только в цикле `Do`.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-108">`Exit Do` can be used only inside a `Do` loop.</span></span> <span data-ttu-id="7b5d5-109">При использовании внутри вложенных циклов `Do` `Exit Do` выходит из внутреннего цикла и передает управление следующему более высокому уровню вложенности.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-109">When used within nested `Do` loops, `Exit Do` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

 `Exit For`  
 <span data-ttu-id="7b5d5-110">Немедленно завершает работу цикла `For`, в котором он отображается.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-110">Immediately exits the `For` loop in which it appears.</span></span> <span data-ttu-id="7b5d5-111">Выполнение продолжится с оператора, следующего за оператором `Next`.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-111">Execution continues with the statement following the `Next` statement.</span></span> <span data-ttu-id="7b5d5-112">`Exit For` может использоваться только в цикле `For`... `Next` или `For Each`... `Next`.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-112">`Exit For` can be used only inside a `For`...`Next` or `For Each`...`Next` loop.</span></span> <span data-ttu-id="7b5d5-113">При использовании внутри вложенных циклов `For` `Exit For` выходит из внутреннего цикла и передает управление следующему более высокому уровню вложенности.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-113">When used within nested `For` loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

 `Exit Function`  
 <span data-ttu-id="7b5d5-114">Немедленно завершает работу процедуры `Function`, в которой она отображается.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-114">Immediately exits the `Function` procedure in which it appears.</span></span> <span data-ttu-id="7b5d5-115">Выполнение продолжится с оператора, следующего за инструкцией, вызвавшей процедуру `Function`.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-115">Execution continues with the statement following the statement that called the `Function` procedure.</span></span> <span data-ttu-id="7b5d5-116">`Exit Function` может использоваться только внутри процедуры `Function`.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-116">`Exit Function` can be used only inside a `Function` procedure.</span></span>

 <span data-ttu-id="7b5d5-117">Чтобы указать возвращаемое значение, можно присвоить значение имени функции в строке перед оператором `Exit Function`.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-117">To specify a return value, you can assign the value to the function name on a line before the `Exit Function` statement.</span></span> <span data-ttu-id="7b5d5-118">Чтобы присвоить возвращаемое значение и выйти из функции в одной инструкции, можно использовать [оператор return](return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7b5d5-118">To assign the return value and exit the function in one statement, you can instead use the [Return Statement](return-statement.md).</span></span>

 `Exit Property`  
 <span data-ttu-id="7b5d5-119">Немедленно завершает работу процедуры `Property`, в которой она отображается.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-119">Immediately exits the `Property` procedure in which it appears.</span></span> <span data-ttu-id="7b5d5-120">Выполнение продолжится с оператора, вызвавшего процедуру `Property`, то есть с инструкцией, запрашивающей или задавая значение свойства.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-120">Execution continues with the statement that called the `Property` procedure, that is, with the statement requesting or setting the property's value.</span></span> <span data-ttu-id="7b5d5-121">`Exit Property` может использоваться только внутри процедуры свойства `Get` или `Set`.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-121">`Exit Property` can be used only inside a property's `Get` or `Set` procedure.</span></span>

 <span data-ttu-id="7b5d5-122">Чтобы указать возвращаемое значение в процедуре `Get`, можно присвоить значение имени функции в строке перед оператором `Exit Property`.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-122">To specify a return value in a `Get` procedure, you can assign the value to the function name on a line before the `Exit Property` statement.</span></span> <span data-ttu-id="7b5d5-123">Чтобы присвоить возвращаемое значение и выйти из процедуры `Get` в одном операторе, можно использовать инструкцию `Return`.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-123">To assign the return value and exit the `Get` procedure in one statement, you can instead use the `Return` statement.</span></span>

 <span data-ttu-id="7b5d5-124">В процедуре `Set` Инструкция `Exit Property` эквивалентна инструкции `Return`.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-124">In a `Set` procedure, the `Exit Property` statement is equivalent to the `Return` statement.</span></span>

 `Exit Select`  
 <span data-ttu-id="7b5d5-125">Немедленно завершает работу блока `Select Case`, в котором он отображается.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-125">Immediately exits the `Select Case` block in which it appears.</span></span> <span data-ttu-id="7b5d5-126">Выполнение продолжится с оператора, следующего за оператором `End Select`.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-126">Execution continues with the statement following the `End Select` statement.</span></span> <span data-ttu-id="7b5d5-127">`Exit Select` может использоваться только внутри оператора `Select Case`.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-127">`Exit Select` can be used only inside a `Select Case` statement.</span></span>

 `Exit Sub`  
 <span data-ttu-id="7b5d5-128">Немедленно завершает работу процедуры `Sub`, в которой она отображается.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-128">Immediately exits the `Sub` procedure in which it appears.</span></span> <span data-ttu-id="7b5d5-129">Выполнение продолжится с оператора, следующего за инструкцией, вызвавшей процедуру `Sub`.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-129">Execution continues with the statement following the statement that called the `Sub` procedure.</span></span> <span data-ttu-id="7b5d5-130">`Exit Sub` может использоваться только внутри процедуры `Sub`.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-130">`Exit Sub` can be used only inside a `Sub` procedure.</span></span>

 <span data-ttu-id="7b5d5-131">В процедуре `Sub` Инструкция `Exit Sub` эквивалентна инструкции `Return`.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-131">In a `Sub` procedure, the `Exit Sub` statement is equivalent to the `Return` statement.</span></span>

 `Exit Try`  
 <span data-ttu-id="7b5d5-132">Немедленно завершает работу блока `Try` или `Catch`, в котором он отображается.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-132">Immediately exits the `Try` or `Catch` block in which it appears.</span></span> <span data-ttu-id="7b5d5-133">Выполнение продолжится с блока `Finally`, если таковой имеется, или с оператором, следующим за оператором `End Try` в противном случае.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-133">Execution continues with the `Finally` block if there is one, or with the statement following the `End Try` statement otherwise.</span></span> <span data-ttu-id="7b5d5-134">`Exit Try` можно использовать только в блоке `Try` или `Catch`, а не в блоке `Finally`.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-134">`Exit Try` can be used only inside a `Try` or `Catch` block, and not inside a `Finally` block.</span></span>

 `Exit While`  
 <span data-ttu-id="7b5d5-135">Немедленно завершает работу цикла `While`, в котором он отображается.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-135">Immediately exits the `While` loop in which it appears.</span></span> <span data-ttu-id="7b5d5-136">Выполнение продолжится с оператора, следующего за оператором `End While`.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-136">Execution continues with the statement following the `End While` statement.</span></span> <span data-ttu-id="7b5d5-137">`Exit While` можно использовать только в цикле `While`.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-137">`Exit While` can be used only inside a `While` loop.</span></span> <span data-ttu-id="7b5d5-138">При использовании внутри вложенных циклов `While` `Exit While` передает управление циклу, который является одним вложенным уровнем над циклом, где происходит `Exit While`.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-138">When used within nested `While` loops, `Exit While` transfers control to the loop that is one nested level above the loop where `Exit While` occurs.</span></span>

## <a name="remarks"></a><span data-ttu-id="7b5d5-139">Примечания</span><span class="sxs-lookup"><span data-stu-id="7b5d5-139">Remarks</span></span>

<span data-ttu-id="7b5d5-140">Не путайте операторы `Exit` с операторами `End`.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-140">Do not confuse `Exit` statements with `End` statements.</span></span> <span data-ttu-id="7b5d5-141">`Exit` не определяет конец инструкции.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-141">`Exit` does not define the end of a statement.</span></span>

## <a name="example"></a><span data-ttu-id="7b5d5-142">Пример</span><span class="sxs-lookup"><span data-stu-id="7b5d5-142">Example</span></span>

<span data-ttu-id="7b5d5-143">В следующем примере условие цикла останавливает цикл, если переменная `index` больше 100.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-143">In the following example, the loop condition stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="7b5d5-144">Однако оператор `If` в цикле приводит к тому, что оператор `Exit Do` останавливает цикл, если переменная индекса больше 10.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-144">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>

[!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]

## <a name="example"></a><span data-ttu-id="7b5d5-145">Пример</span><span class="sxs-lookup"><span data-stu-id="7b5d5-145">Example</span></span>

<span data-ttu-id="7b5d5-146">В следующем примере возвращаемое значение присваивается имени функции `myFunction`, а затем для возврата из функции используется `Exit Function`.</span><span class="sxs-lookup"><span data-stu-id="7b5d5-146">The following example assigns the return value to the function name `myFunction`, and then uses `Exit Function` to return from the function:</span></span>

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

## <a name="example"></a><span data-ttu-id="7b5d5-147">Пример</span><span class="sxs-lookup"><span data-stu-id="7b5d5-147">Example</span></span>

<span data-ttu-id="7b5d5-148">В следующем примере [оператор return](return-statement.md) используется для назначения возвращаемого значения и выхода из функции:</span><span class="sxs-lookup"><span data-stu-id="7b5d5-148">The following example uses the [Return Statement](return-statement.md) to assign the return value and exit the function:</span></span>

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

## <a name="see-also"></a><span data-ttu-id="7b5d5-149">См. также</span><span class="sxs-lookup"><span data-stu-id="7b5d5-149">See also</span></span>

- [<span data-ttu-id="7b5d5-150">Оператор Continue</span><span class="sxs-lookup"><span data-stu-id="7b5d5-150">Continue Statement</span></span>](continue-statement.md)
- [<span data-ttu-id="7b5d5-151">Оператор Do...Loop</span><span class="sxs-lookup"><span data-stu-id="7b5d5-151">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="7b5d5-152">Оператор End</span><span class="sxs-lookup"><span data-stu-id="7b5d5-152">End Statement</span></span>](end-statement.md)
- [<span data-ttu-id="7b5d5-153">Оператор For Each...Next</span><span class="sxs-lookup"><span data-stu-id="7b5d5-153">For Each...Next Statement</span></span>](for-each-next-statement.md)
- [<span data-ttu-id="7b5d5-154">Оператор For...Next</span><span class="sxs-lookup"><span data-stu-id="7b5d5-154">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="7b5d5-155">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="7b5d5-155">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="7b5d5-156">Оператор Return</span><span class="sxs-lookup"><span data-stu-id="7b5d5-156">Return Statement</span></span>](return-statement.md)
- [<span data-ttu-id="7b5d5-157">Оператор Stop</span><span class="sxs-lookup"><span data-stu-id="7b5d5-157">Stop Statement</span></span>](stop-statement.md)
- [<span data-ttu-id="7b5d5-158">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="7b5d5-158">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="7b5d5-159">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="7b5d5-159">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
