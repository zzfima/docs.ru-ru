---
title: Оператор While... End While (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.While
- vb.While...EndWhile
helpviewer_keywords:
- While statement [Visual Basic], While...End While
- While statement [Visual Basic]
- While...End While statements [Visual Basic]
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
ms.openlocfilehash: 9f46a6ec65faef4448bdd25e30a6cc0c605cd0f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="whileend-while-statement-visual-basic"></a><span data-ttu-id="4d343-102">Оператор While... End While (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d343-102">While...End While Statement (Visual Basic)</span></span>
<span data-ttu-id="4d343-103">Выполняет последовательность операторов, пока заданное условие является `True`.</span><span class="sxs-lookup"><span data-stu-id="4d343-103">Runs a series of statements as long as a given condition is `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d343-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4d343-104">Syntax</span></span>  
  
```  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a><span data-ttu-id="4d343-105">Части</span><span class="sxs-lookup"><span data-stu-id="4d343-105">Parts</span></span>  
  
|<span data-ttu-id="4d343-106">Термин</span><span class="sxs-lookup"><span data-stu-id="4d343-106">Term</span></span>|<span data-ttu-id="4d343-107">Определение</span><span class="sxs-lookup"><span data-stu-id="4d343-107">Definition</span></span>|  
|---|---|  
|`condition`|<span data-ttu-id="4d343-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="4d343-108">Required.</span></span> <span data-ttu-id="4d343-109">`Boolean` Выражение.</span><span class="sxs-lookup"><span data-stu-id="4d343-109">`Boolean` expression.</span></span> <span data-ttu-id="4d343-110">Если `condition` — `Nothing`, Visual Basic рассматривает его как `False`.</span><span class="sxs-lookup"><span data-stu-id="4d343-110">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="4d343-111">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="4d343-111">Optional.</span></span> <span data-ttu-id="4d343-112">Один или несколько следующих инструкций `While`, который запускаться при каждом `condition` — `True`.</span><span class="sxs-lookup"><span data-stu-id="4d343-112">One or more statements following `While`, which run every time `condition` is `True`.</span></span>|  
|`Continue While`|<span data-ttu-id="4d343-113">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="4d343-113">Optional.</span></span> <span data-ttu-id="4d343-114">Передает управление следующей итерации цикла `While` блока.</span><span class="sxs-lookup"><span data-stu-id="4d343-114">Transfers control to the next iteration of the `While` block.</span></span>|  
|`Exit While`|<span data-ttu-id="4d343-115">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="4d343-115">Optional.</span></span> <span data-ttu-id="4d343-116">Передает управление из `While` блока.</span><span class="sxs-lookup"><span data-stu-id="4d343-116">Transfers control out of the `While` block.</span></span>|  
|`End While`|<span data-ttu-id="4d343-117">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="4d343-117">Required.</span></span> <span data-ttu-id="4d343-118">Завершает определение блока `While`.</span><span class="sxs-lookup"><span data-stu-id="4d343-118">Terminates the definition of the `While` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d343-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="4d343-119">Remarks</span></span>  
 <span data-ttu-id="4d343-120">Используйте `While...End While` структуры, если вы хотите повторить набор инструкций на неопределенное количество раз, до тех пор, пока условие остается `True`.</span><span class="sxs-lookup"><span data-stu-id="4d343-120">Use a `While...End While` structure when you want to repeat a set of statements an indefinite number of times, as long as a condition remains `True`.</span></span> <span data-ttu-id="4d343-121">Если требуется больше гибкости, с которой проверки того, что или результат можно проверить его, может потребоваться [сделать... Цикл инструкции](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4d343-121">If you want more flexibility with where you test the condition or what result you test it for, you might prefer the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span> <span data-ttu-id="4d343-122">Если вы хотите повторить инструкцию set несколько раз, [для... Следующий оператор](../../../visual-basic/language-reference/statements/for-next-statement.md) обычно является лучшим выбором.</span><span class="sxs-lookup"><span data-stu-id="4d343-122">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d343-123">`While` Также используется ключевое слово в [сделать... Цикл инструкции](../../../visual-basic/language-reference/statements/do-loop-statement.md), [предложение Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md) и [предложение Take While](../../../visual-basic/language-reference/queries/take-while-clause.md).</span><span class="sxs-lookup"><span data-stu-id="4d343-123">The `While` keyword is also used in the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md), the [Skip While Clause](../../../visual-basic/language-reference/queries/skip-while-clause.md) and the [Take While Clause](../../../visual-basic/language-reference/queries/take-while-clause.md).</span></span>  
  
 <span data-ttu-id="4d343-124">Если `condition` — `True`, все из `statements` выполнения до `End While` инструкции.</span><span class="sxs-lookup"><span data-stu-id="4d343-124">If `condition` is `True`, all of the `statements` run until the `End While` statement is encountered.</span></span> <span data-ttu-id="4d343-125">Затем возвращается на управления `While` инструкции и `condition` проверяется заново.</span><span class="sxs-lookup"><span data-stu-id="4d343-125">Control then returns to the `While` statement, and `condition` is again checked.</span></span> <span data-ttu-id="4d343-126">Если `condition` по-прежнему `True`, процесс повторяется.</span><span class="sxs-lookup"><span data-stu-id="4d343-126">If `condition` is still `True`, the process is repeated.</span></span> <span data-ttu-id="4d343-127">Если у него есть `False`, управление передается оператору, следующему `End While` инструкции.</span><span class="sxs-lookup"><span data-stu-id="4d343-127">If it’s `False`, control passes to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="4d343-128">`While` Оператор всегда проверяет условие перед началом цикла.</span><span class="sxs-lookup"><span data-stu-id="4d343-128">The `While` statement always checks the condition before it starts the loop.</span></span> <span data-ttu-id="4d343-129">Выполнение цикла продолжается, пока значение условия равно `True`.</span><span class="sxs-lookup"><span data-stu-id="4d343-129">Looping continues while the condition remains `True`.</span></span> <span data-ttu-id="4d343-130">Если `condition` — `False` при первом входе цикла, он не запускается даже один раз.</span><span class="sxs-lookup"><span data-stu-id="4d343-130">If `condition` is `False` when you first enter the loop, it doesn’t run even once.</span></span>  
  
 <span data-ttu-id="4d343-131">`condition` Обычно результатом сравнения двух значений, но может быть любое выражение, результатом которого является [тип данных Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md) значение (`True` или `False`).</span><span class="sxs-lookup"><span data-stu-id="4d343-131">The `condition` usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="4d343-132">Это выражение может включать значение другого типа данных, например числовой тип, который был преобразован в `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="4d343-132">This expression can include a value of another data type, such as a numeric type, that has been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="4d343-133">Можно вложить `While` циклы, поместив один в другой.</span><span class="sxs-lookup"><span data-stu-id="4d343-133">You can nest `While` loops by placing one loop within another.</span></span> <span data-ttu-id="4d343-134">Также можно вложить различные виды структур управления друг в друга.</span><span class="sxs-lookup"><span data-stu-id="4d343-134">You can also nest different kinds of control structures within one another.</span></span> <span data-ttu-id="4d343-135">Дополнительные сведения см. в разделе [вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="4d343-135">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
## <a name="exit-while"></a><span data-ttu-id="4d343-136">Выход при</span><span class="sxs-lookup"><span data-stu-id="4d343-136">Exit While</span></span>  
 <span data-ttu-id="4d343-137">[Выхода во время](../../../visual-basic/language-reference/statements/exit-statement.md) инструкции можно предоставить другим способом, чтобы выйти из `While` цикла.</span><span class="sxs-lookup"><span data-stu-id="4d343-137">The [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide another way to exit a `While` loop.</span></span> <span data-ttu-id="4d343-138">`Exit While` немедленно передает управление оператору, следующему `End While` инструкции.</span><span class="sxs-lookup"><span data-stu-id="4d343-138">`Exit While` immediately transfers control to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="4d343-139">Как правило, используется `Exit While` после вычисления некоторого условия (например, в `If...Then...Else` структуры).</span><span class="sxs-lookup"><span data-stu-id="4d343-139">You typically use `Exit While` after some condition is evaluated (for example, in an `If...Then...Else` structure).</span></span> <span data-ttu-id="4d343-140">Может потребоваться выйти из цикла при обнаружении условия, которое делает бесполезным или невозможным продолжение итераций, например ошибочное значение или запрос на завершение.</span><span class="sxs-lookup"><span data-stu-id="4d343-140">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="4d343-141">Можно использовать `Exit While` при проверке условия, которое может привести к *бесконечный цикл*, который является цикл, который может запустить слишком большой или возможно, бесконечное число раз.</span><span class="sxs-lookup"><span data-stu-id="4d343-141">You can use `Exit While` when you test for a condition that could cause an *endless loop*, which is a loop that could run an extremely large or even infinite number of times.</span></span> <span data-ttu-id="4d343-142">Затем можно использовать `Exit While` для выхода из цикла.</span><span class="sxs-lookup"><span data-stu-id="4d343-142">You can then use `Exit While` to escape the loop.</span></span>  
  
 <span data-ttu-id="4d343-143">Можно установить любое число `Exit While` инструкций в любом месте в `While` цикла.</span><span class="sxs-lookup"><span data-stu-id="4d343-143">You can place any number of `Exit While` statements anywhere in the `While` loop.</span></span>  
  
 <span data-ttu-id="4d343-144">При использовании внутри вложенной `While` циклы, `Exit While` передает управление из самого внутреннего цикла и отправляются верхнего уровня вложенности.</span><span class="sxs-lookup"><span data-stu-id="4d343-144">When used within nested `While` loops, `Exit While` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
 <span data-ttu-id="4d343-145">`Continue While` Инструкция немедленно передает управление следующей итерации цикла.</span><span class="sxs-lookup"><span data-stu-id="4d343-145">The `Continue While` statement immediately transfers control to the next iteration of the loop.</span></span> <span data-ttu-id="4d343-146">Дополнительные сведения см. в разделе [оператор Continue](../../../visual-basic/language-reference/statements/continue-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4d343-146">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d343-147">Пример</span><span class="sxs-lookup"><span data-stu-id="4d343-147">Example</span></span>  
 <span data-ttu-id="4d343-148">В следующем примере инструкции в цикле по-прежнему выполняются, пока `index` переменной больше 10.</span><span class="sxs-lookup"><span data-stu-id="4d343-148">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#171](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="4d343-149">Пример</span><span class="sxs-lookup"><span data-stu-id="4d343-149">Example</span></span>  
 <span data-ttu-id="4d343-150">Следующий пример иллюстрирует использование `Continue While` и `Exit While` инструкции.</span><span class="sxs-lookup"><span data-stu-id="4d343-150">The following example illustrates the use of the `Continue While` and `Exit While` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#172](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="4d343-151">Пример</span><span class="sxs-lookup"><span data-stu-id="4d343-151">Example</span></span>  
 <span data-ttu-id="4d343-152">Следующий пример считывает все строки в текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="4d343-152">The following example reads all lines in a text file.</span></span> <span data-ttu-id="4d343-153"><xref:System.IO.File.OpenText%2A> Метод открывает файл и возвращает <xref:System.IO.StreamReader> , считывает символы.</span><span class="sxs-lookup"><span data-stu-id="4d343-153">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="4d343-154">В `While` условие, <xref:System.IO.StreamReader.Peek%2A> метод `StreamReader` определяет, содержит ли файл дополнительных символов.</span><span class="sxs-lookup"><span data-stu-id="4d343-154">In the `While` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether the file contains additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#173](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4d343-155">См. также</span><span class="sxs-lookup"><span data-stu-id="4d343-155">See Also</span></span>  
 [<span data-ttu-id="4d343-156">Циклические структуры</span><span class="sxs-lookup"><span data-stu-id="4d343-156">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="4d343-157">Оператор Do...Loop</span><span class="sxs-lookup"><span data-stu-id="4d343-157">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [<span data-ttu-id="4d343-158">Оператор For...Next</span><span class="sxs-lookup"><span data-stu-id="4d343-158">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="4d343-159">Логический тип данных</span><span class="sxs-lookup"><span data-stu-id="4d343-159">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)  
 [<span data-ttu-id="4d343-160">Вложенные структуры управления</span><span class="sxs-lookup"><span data-stu-id="4d343-160">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="4d343-161">Оператор Exit</span><span class="sxs-lookup"><span data-stu-id="4d343-161">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [<span data-ttu-id="4d343-162">Оператор Continue</span><span class="sxs-lookup"><span data-stu-id="4d343-162">Continue Statement</span></span>](../../../visual-basic/language-reference/statements/continue-statement.md)
