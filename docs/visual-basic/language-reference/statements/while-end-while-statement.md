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
ms.openlocfilehash: 00ca0ad24231128b25a988921386d6bd3265e9a0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934230"
---
# <a name="whileend-while-statement-visual-basic"></a><span data-ttu-id="09ef4-102">Оператор While... End While (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09ef4-102">While...End While Statement (Visual Basic)</span></span>
<span data-ttu-id="09ef4-103">Выполняет ряд инструкций до тех пор, пока заданное условие является `True`.</span><span class="sxs-lookup"><span data-stu-id="09ef4-103">Runs a series of statements as long as a given condition is `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09ef4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="09ef4-104">Syntax</span></span>  
  
```  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a><span data-ttu-id="09ef4-105">Части</span><span class="sxs-lookup"><span data-stu-id="09ef4-105">Parts</span></span>  
  
|<span data-ttu-id="09ef4-106">Термин</span><span class="sxs-lookup"><span data-stu-id="09ef4-106">Term</span></span>|<span data-ttu-id="09ef4-107">Определение</span><span class="sxs-lookup"><span data-stu-id="09ef4-107">Definition</span></span>|  
|---|---|  
|`condition`|<span data-ttu-id="09ef4-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="09ef4-108">Required.</span></span> <span data-ttu-id="09ef4-109">`Boolean` выражение.</span><span class="sxs-lookup"><span data-stu-id="09ef4-109">`Boolean` expression.</span></span> <span data-ttu-id="09ef4-110">Если `condition` — `Nothing`, Visual Basic рассматривает его как `False`.</span><span class="sxs-lookup"><span data-stu-id="09ef4-110">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="09ef4-111">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="09ef4-111">Optional.</span></span> <span data-ttu-id="09ef4-112">Один или несколько следующих инструкций `While`, который запускаться при каждом `condition` является `True`.</span><span class="sxs-lookup"><span data-stu-id="09ef4-112">One or more statements following `While`, which run every time `condition` is `True`.</span></span>|  
|`Continue While`|<span data-ttu-id="09ef4-113">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="09ef4-113">Optional.</span></span> <span data-ttu-id="09ef4-114">Передает управление следующей итерации `While` блока.</span><span class="sxs-lookup"><span data-stu-id="09ef4-114">Transfers control to the next iteration of the `While` block.</span></span>|  
|`Exit While`|<span data-ttu-id="09ef4-115">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="09ef4-115">Optional.</span></span> <span data-ttu-id="09ef4-116">Передает управление из `While` блока.</span><span class="sxs-lookup"><span data-stu-id="09ef4-116">Transfers control out of the `While` block.</span></span>|  
|`End While`|<span data-ttu-id="09ef4-117">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="09ef4-117">Required.</span></span> <span data-ttu-id="09ef4-118">Завершает определение блока `While`.</span><span class="sxs-lookup"><span data-stu-id="09ef4-118">Terminates the definition of the `While` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09ef4-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="09ef4-119">Remarks</span></span>  
 <span data-ttu-id="09ef4-120">Используйте `While...End While` структуры, когда нужно повторить набор инструкций неограниченное число раз, до тех пор, пока условие остается `True`.</span><span class="sxs-lookup"><span data-stu-id="09ef4-120">Use a `While...End While` structure when you want to repeat a set of statements an indefinite number of times, as long as a condition remains `True`.</span></span> <span data-ttu-id="09ef4-121">Если требуется более гибкое и где проверить условие или результат можно проверить его, может потребоваться [сделать... Цикл инструкции](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="09ef4-121">If you want more flexibility with where you test the condition or what result you test it for, you might prefer the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span> <span data-ttu-id="09ef4-122">Если вы хотите повторить инструкцию set несколько раз, [для... Следующий оператор](../../../visual-basic/language-reference/statements/for-next-statement.md) обычно является лучшим выбором.</span><span class="sxs-lookup"><span data-stu-id="09ef4-122">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09ef4-123">`While` Ключевое слово также используется в [сделать... Цикл инструкции](../../../visual-basic/language-reference/statements/do-loop-statement.md), [предложение Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md) и [предложение Take While](../../../visual-basic/language-reference/queries/take-while-clause.md).</span><span class="sxs-lookup"><span data-stu-id="09ef4-123">The `While` keyword is also used in the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md), the [Skip While Clause](../../../visual-basic/language-reference/queries/skip-while-clause.md) and the [Take While Clause](../../../visual-basic/language-reference/queries/take-while-clause.md).</span></span>  
  
 <span data-ttu-id="09ef4-124">Если `condition` — `True`, все из `statements` выполнения до `End While` встречается.</span><span class="sxs-lookup"><span data-stu-id="09ef4-124">If `condition` is `True`, all of the `statements` run until the `End While` statement is encountered.</span></span> <span data-ttu-id="09ef4-125">Элемент управления затем возвращается на `While` инструкции и `condition` проверяется заново.</span><span class="sxs-lookup"><span data-stu-id="09ef4-125">Control then returns to the `While` statement, and `condition` is again checked.</span></span> <span data-ttu-id="09ef4-126">Если `condition` по-прежнему `True`, этот процесс повторяется.</span><span class="sxs-lookup"><span data-stu-id="09ef4-126">If `condition` is still `True`, the process is repeated.</span></span> <span data-ttu-id="09ef4-127">Если у него есть `False`, управление передается оператору, который расположен `End While` инструкции.</span><span class="sxs-lookup"><span data-stu-id="09ef4-127">If it’s `False`, control passes to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="09ef4-128">`While` Оператор всегда проверяет условие перед началом цикла.</span><span class="sxs-lookup"><span data-stu-id="09ef4-128">The `While` statement always checks the condition before it starts the loop.</span></span> <span data-ttu-id="09ef4-129">Выполнение цикла продолжается, пока значение условия равно `True`.</span><span class="sxs-lookup"><span data-stu-id="09ef4-129">Looping continues while the condition remains `True`.</span></span> <span data-ttu-id="09ef4-130">Если `condition` является `False` при первом входе в цикл, оно вообще не запускается.</span><span class="sxs-lookup"><span data-stu-id="09ef4-130">If `condition` is `False` when you first enter the loop, it doesn’t run even once.</span></span>  
  
 <span data-ttu-id="09ef4-131">`condition` Обычно результаты из сравнения двух значений, но он может быть любое выражение, результатом которого является [логический тип данных](../../../visual-basic/language-reference/data-types/boolean-data-type.md) значение (`True` или `False`).</span><span class="sxs-lookup"><span data-stu-id="09ef4-131">The `condition` usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="09ef4-132">Это выражение может включать значение другого типа данных, таких как числовой тип, который был преобразован в `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="09ef4-132">This expression can include a value of another data type, such as a numeric type, that has been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="09ef4-133">Можно вложить `While` циклы, поместив один внутри другого.</span><span class="sxs-lookup"><span data-stu-id="09ef4-133">You can nest `While` loops by placing one loop within another.</span></span> <span data-ttu-id="09ef4-134">Можно также вложить разные виды структур управления друг с другом.</span><span class="sxs-lookup"><span data-stu-id="09ef4-134">You can also nest different kinds of control structures within one another.</span></span> <span data-ttu-id="09ef4-135">Дополнительные сведения см. в разделе [вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="09ef4-135">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
## <a name="exit-while"></a><span data-ttu-id="09ef4-136">Выход при</span><span class="sxs-lookup"><span data-stu-id="09ef4-136">Exit While</span></span>  
 <span data-ttu-id="09ef4-137">[Выйти из во время](../../../visual-basic/language-reference/statements/exit-statement.md) инструкции можно найти другой способ выхода из `While` цикла.</span><span class="sxs-lookup"><span data-stu-id="09ef4-137">The [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide another way to exit a `While` loop.</span></span> <span data-ttu-id="09ef4-138">`Exit While` немедленно передает управление оператору, который расположен `End While` инструкции.</span><span class="sxs-lookup"><span data-stu-id="09ef4-138">`Exit While` immediately transfers control to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="09ef4-139">Как правило, используется `Exit While` после вычисления некоторого условия (например, в `If...Then...Else` структуры).</span><span class="sxs-lookup"><span data-stu-id="09ef4-139">You typically use `Exit While` after some condition is evaluated (for example, in an `If...Then...Else` structure).</span></span> <span data-ttu-id="09ef4-140">Может потребоваться выйти из цикла, если определяет условие, которое делает бесполезным или невозможным продолжение итераций, например ошибочное значение или запрос на завершение.</span><span class="sxs-lookup"><span data-stu-id="09ef4-140">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="09ef4-141">Можно использовать `Exit While` при проверке условия, которое может привести к *бесконечный цикл*, который является цикл, который может запустить слишком большой или возможно, бесконечное число раз.</span><span class="sxs-lookup"><span data-stu-id="09ef4-141">You can use `Exit While` when you test for a condition that could cause an *endless loop*, which is a loop that could run an extremely large or even infinite number of times.</span></span> <span data-ttu-id="09ef4-142">Затем можно использовать `Exit While` для выхода из цикла.</span><span class="sxs-lookup"><span data-stu-id="09ef4-142">You can then use `Exit While` to escape the loop.</span></span>  
  
 <span data-ttu-id="09ef4-143">Можно установить любое число `Exit While` инструкций в любом месте в `While` цикла.</span><span class="sxs-lookup"><span data-stu-id="09ef4-143">You can place any number of `Exit While` statements anywhere in the `While` loop.</span></span>  
  
 <span data-ttu-id="09ef4-144">При использовании внутри вложенной `While` циклы, `Exit While` передает управление из самого внутреннего цикла и поместить в следующий уровень вложенности.</span><span class="sxs-lookup"><span data-stu-id="09ef4-144">When used within nested `While` loops, `Exit While` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
 <span data-ttu-id="09ef4-145">`Continue While` Оператор сразу же передает управление следующей итерации цикла.</span><span class="sxs-lookup"><span data-stu-id="09ef4-145">The `Continue While` statement immediately transfers control to the next iteration of the loop.</span></span> <span data-ttu-id="09ef4-146">Дополнительные сведения см. в разделе [оператор Continue](../../../visual-basic/language-reference/statements/continue-statement.md).</span><span class="sxs-lookup"><span data-stu-id="09ef4-146">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="09ef4-147">Пример</span><span class="sxs-lookup"><span data-stu-id="09ef4-147">Example</span></span>  
 <span data-ttu-id="09ef4-148">В следующем примере операторы в цикле продолжать выполняться до `index` переменной превышает 10.</span><span class="sxs-lookup"><span data-stu-id="09ef4-148">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a><span data-ttu-id="09ef4-149">Пример</span><span class="sxs-lookup"><span data-stu-id="09ef4-149">Example</span></span>  
 <span data-ttu-id="09ef4-150">Следующий пример иллюстрирует использование `Continue While` и `Exit While` инструкций.</span><span class="sxs-lookup"><span data-stu-id="09ef4-150">The following example illustrates the use of the `Continue While` and `Exit While` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a><span data-ttu-id="09ef4-151">Пример</span><span class="sxs-lookup"><span data-stu-id="09ef4-151">Example</span></span>  
 <span data-ttu-id="09ef4-152">В следующем примере считываются все строки в текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="09ef4-152">The following example reads all lines in a text file.</span></span> <span data-ttu-id="09ef4-153"><xref:System.IO.File.OpenText%2A> Метод открывает файл и возвращает <xref:System.IO.StreamReader> , считывает символы.</span><span class="sxs-lookup"><span data-stu-id="09ef4-153">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="09ef4-154">В `While` условие, <xref:System.IO.StreamReader.Peek%2A> метод `StreamReader` определяет, содержит ли файл, дополнительные символы.</span><span class="sxs-lookup"><span data-stu-id="09ef4-154">In the `While` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether the file contains additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a><span data-ttu-id="09ef4-155">См. также</span><span class="sxs-lookup"><span data-stu-id="09ef4-155">See also</span></span>

- [<span data-ttu-id="09ef4-156">Циклические структуры</span><span class="sxs-lookup"><span data-stu-id="09ef4-156">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="09ef4-157">Оператор Do...Loop</span><span class="sxs-lookup"><span data-stu-id="09ef4-157">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="09ef4-158">Оператор For...Next</span><span class="sxs-lookup"><span data-stu-id="09ef4-158">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="09ef4-159">Логический тип данных</span><span class="sxs-lookup"><span data-stu-id="09ef4-159">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="09ef4-160">Вложенные структуры управления</span><span class="sxs-lookup"><span data-stu-id="09ef4-160">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="09ef4-161">Оператор Exit</span><span class="sxs-lookup"><span data-stu-id="09ef4-161">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="09ef4-162">Оператор Continue</span><span class="sxs-lookup"><span data-stu-id="09ef4-162">Continue Statement</span></span>](../../../visual-basic/language-reference/statements/continue-statement.md)
