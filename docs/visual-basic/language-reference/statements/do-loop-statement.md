---
title: Оператор Do...Loop (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Do
- vb.Loop
- vb.Until
helpviewer_keywords:
- conditional statements [Visual Basic], Do�Loop
- while statement [Visual Basic], Do...Loop
- execution [Visual Basic], conditional
- Do loops
- Until keyword [Visual Basic], Do...Loop statement
- Do...Loop statement
- instructions, repeating
- Do statement [Visual Basic]
- Exit statement [Visual Basic], in Do...Loop statements
- loop structures [Visual Basic], Do�Loop statements
- do-while statements [Visual Basic]
- loops, exiting
- Loop keyword [Visual Basic], Do...Loop statement
ms.assetid: 892f9096-b3e2-4aee-834d-83bc4e2c379d
ms.openlocfilehash: e12cdc1ae405b877d4d27d1947c98dcb51938ba7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="doloop-statement-visual-basic"></a><span data-ttu-id="c3b86-102">Оператор Do...Loop (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c3b86-102">Do...Loop Statement (Visual Basic)</span></span>
<span data-ttu-id="c3b86-103">Повторяет блок операторов, пока `Boolean` условие `True` или пока условия не станет `True`.</span><span class="sxs-lookup"><span data-stu-id="c3b86-103">Repeats a block of statements while a `Boolean` condition is `True` or until the condition becomes `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3b86-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c3b86-104">Syntax</span></span>  
  
```  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
-or-  
Do  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop { While | Until } condition  
```  
  
## <a name="parts"></a><span data-ttu-id="c3b86-105">Части</span><span class="sxs-lookup"><span data-stu-id="c3b86-105">Parts</span></span>  
  
|<span data-ttu-id="c3b86-106">Термин</span><span class="sxs-lookup"><span data-stu-id="c3b86-106">Term</span></span>|<span data-ttu-id="c3b86-107">Определение</span><span class="sxs-lookup"><span data-stu-id="c3b86-107">Definition</span></span>|  
|---|---|  
|`Do`|<span data-ttu-id="c3b86-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="c3b86-108">Required.</span></span> <span data-ttu-id="c3b86-109">Начинается определение `Do` цикла.</span><span class="sxs-lookup"><span data-stu-id="c3b86-109">Starts the definition of the `Do` loop.</span></span>|  
|`While`|<span data-ttu-id="c3b86-110">Является обязательным, если используется параметр `Until`.</span><span class="sxs-lookup"><span data-stu-id="c3b86-110">Required unless `Until` is used.</span></span> <span data-ttu-id="c3b86-111">Повторите цикл до `condition` — `False`.</span><span class="sxs-lookup"><span data-stu-id="c3b86-111">Repeat the loop until `condition` is `False`.</span></span>|  
|`Until`|<span data-ttu-id="c3b86-112">Является обязательным, если используется параметр `While`.</span><span class="sxs-lookup"><span data-stu-id="c3b86-112">Required unless `While` is used.</span></span> <span data-ttu-id="c3b86-113">Повторите цикл до `condition` — `True`.</span><span class="sxs-lookup"><span data-stu-id="c3b86-113">Repeat the loop until `condition` is `True`.</span></span>|  
|`condition`|<span data-ttu-id="c3b86-114">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="c3b86-114">Optional.</span></span> <span data-ttu-id="c3b86-115">`Boolean` Выражение.</span><span class="sxs-lookup"><span data-stu-id="c3b86-115">`Boolean` expression.</span></span> <span data-ttu-id="c3b86-116">Если `condition` — `Nothing`, Visual Basic рассматривает его как `False`.</span><span class="sxs-lookup"><span data-stu-id="c3b86-116">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="c3b86-117">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="c3b86-117">Optional.</span></span> <span data-ttu-id="c3b86-118">Один или несколько операторов, которые повторяются во время или до, `condition` — `True`.</span><span class="sxs-lookup"><span data-stu-id="c3b86-118">One or more statements that are repeated while, or until, `condition` is `True`.</span></span>|  
|`Continue Do`|<span data-ttu-id="c3b86-119">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="c3b86-119">Optional.</span></span> <span data-ttu-id="c3b86-120">Передает управление следующей итерации цикла `Do` цикла.</span><span class="sxs-lookup"><span data-stu-id="c3b86-120">Transfers control to the next iteration of the `Do` loop.</span></span>|  
|`Exit Do`|<span data-ttu-id="c3b86-121">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="c3b86-121">Optional.</span></span> <span data-ttu-id="c3b86-122">Передает управление из `Do` цикла.</span><span class="sxs-lookup"><span data-stu-id="c3b86-122">Transfers control out of the `Do` loop.</span></span>|  
|`Loop`|<span data-ttu-id="c3b86-123">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="c3b86-123">Required.</span></span> <span data-ttu-id="c3b86-124">Завершает определение `Do` цикла.</span><span class="sxs-lookup"><span data-stu-id="c3b86-124">Terminates the definition of the `Do` loop.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3b86-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="c3b86-125">Remarks</span></span>  
 <span data-ttu-id="c3b86-126">Используйте `Do...Loop` структуры, если вы хотите повторить набор инструкций на неопределенное количество раз, пока условие выполняется.</span><span class="sxs-lookup"><span data-stu-id="c3b86-126">Use a `Do...Loop` structure when you want to repeat a set of statements an indefinite number of times, until a condition is satisfied.</span></span> <span data-ttu-id="c3b86-127">Если вы хотите повторить инструкцию set несколько раз, [для... Следующий оператор](../../../visual-basic/language-reference/statements/for-next-statement.md) обычно является лучшим выбором.</span><span class="sxs-lookup"><span data-stu-id="c3b86-127">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
 <span data-ttu-id="c3b86-128">Можно использовать любой `While` или `Until` для указания `condition`, но не оба.</span><span class="sxs-lookup"><span data-stu-id="c3b86-128">You can use either `While` or `Until` to specify `condition`, but not both.</span></span>  
  
 <span data-ttu-id="c3b86-129">Можно проверить `condition` только один раз в начале или конце цикла.</span><span class="sxs-lookup"><span data-stu-id="c3b86-129">You can test `condition` only one time, at either the start or the end of the loop.</span></span> <span data-ttu-id="c3b86-130">Если вы тестируете `condition` в начале цикла (в `Do` инструкции), цикл не может запускаться хотя бы один раз.</span><span class="sxs-lookup"><span data-stu-id="c3b86-130">If you test `condition` at the start of the loop (in the `Do` statement), the loop might not run even one time.</span></span> <span data-ttu-id="c3b86-131">Если вы тестируете в конце цикла (в `Loop` инструкции), цикл всегда выполняется по крайней мере один раз.</span><span class="sxs-lookup"><span data-stu-id="c3b86-131">If you test at the end of the loop (in the `Loop` statement), the loop always runs at least one time.</span></span>  
  
 <span data-ttu-id="c3b86-132">Условие обычно является результатом сравнения двух значений, но он может быть любое выражение, результатом которого является [тип данных Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md) значение (`True` или `False`).</span><span class="sxs-lookup"><span data-stu-id="c3b86-132">The condition usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="c3b86-133">Сюда входят значения других типов данных, таких как числовые типы, которые были преобразованы в `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="c3b86-133">This includes values of other data types, such as numeric types, that have been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="c3b86-134">Можно вложить `Do` циклы, поместив цикл один в другой.</span><span class="sxs-lookup"><span data-stu-id="c3b86-134">You can nest `Do` loops by putting one loop within another.</span></span> <span data-ttu-id="c3b86-135">Также можно вложить различные виды управляющих структур друг с другом.</span><span class="sxs-lookup"><span data-stu-id="c3b86-135">You can also nest different kinds of control structures within each other.</span></span> <span data-ttu-id="c3b86-136">Дополнительные сведения см. в разделе [вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="c3b86-136">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c3b86-137">`Do...Loop` Структура обеспечивает большую гибкость, чем [во время... Оператор End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md) , так как она позволяет решить, следует ли завершить цикл при `condition` перестает быть `True` или когда сначала становится `True`.</span><span class="sxs-lookup"><span data-stu-id="c3b86-137">The `Do...Loop` structure gives you more flexibility than the [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md) because it enables you to decide whether to end the loop when `condition` stops being `True` or when it first becomes `True`.</span></span> <span data-ttu-id="c3b86-138">Он также позволяет тестировать `condition` в начале или конце цикла.</span><span class="sxs-lookup"><span data-stu-id="c3b86-138">It also enables you to test `condition` at either the start or the end of the loop.</span></span>  
  
## <a name="exit-do"></a><span data-ttu-id="c3b86-139">Exit</span><span class="sxs-lookup"><span data-stu-id="c3b86-139">Exit Do</span></span>  
 <span data-ttu-id="c3b86-140">[Выхода выполните](../../../visual-basic/language-reference/statements/exit-statement.md) инструкции можно предоставить альтернативный способ выйти из `Do…Loop`.</span><span class="sxs-lookup"><span data-stu-id="c3b86-140">The [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide an alternative way to exit a `Do…Loop`.</span></span> <span data-ttu-id="c3b86-141">`Exit Do` Управление передается оператору, следующему `Loop` инструкции.</span><span class="sxs-lookup"><span data-stu-id="c3b86-141">`Exit Do` transfers control immediately to the statement that follows the `Loop` statement.</span></span>  
  
 <span data-ttu-id="c3b86-142">`Exit Do` часто используется после оценки некоторого условия, например в `If...Then...Else` структуры.</span><span class="sxs-lookup"><span data-stu-id="c3b86-142">`Exit Do` is often used after some condition is evaluated, for example in an `If...Then...Else` structure.</span></span> <span data-ttu-id="c3b86-143">Может потребоваться выйти из цикла при обнаружении условия, которое делает бесполезным или невозможным продолжение итераций, например ошибочное значение или запрос на завершение.</span><span class="sxs-lookup"><span data-stu-id="c3b86-143">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="c3b86-144">Один из способов использования `Exit Do` используется для проверки условия, которое может вызвать *бесконечный цикл*, который является цикл, который может запустить большое или возможно, бесконечное число раз.</span><span class="sxs-lookup"><span data-stu-id="c3b86-144">One use of `Exit Do` is to test for a condition that could cause an *endless loop*, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="c3b86-145">Можно использовать `Exit Do` для выхода из цикла.</span><span class="sxs-lookup"><span data-stu-id="c3b86-145">You can use `Exit Do` to escape the loop.</span></span>  
  
 <span data-ttu-id="c3b86-146">Можно включить любое количество `Exit Do` инструкций в любом месте в `Do…Loop`.</span><span class="sxs-lookup"><span data-stu-id="c3b86-146">You can include any number of `Exit Do` statements anywhere in a `Do…Loop`.</span></span>  
  
 <span data-ttu-id="c3b86-147">При использовании внутри вложенной `Do` циклы, `Exit Do` передает управление из самого внутреннего цикла и отправляются верхнего уровня вложенности.</span><span class="sxs-lookup"><span data-stu-id="c3b86-147">When used within nested `Do` loops, `Exit Do` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3b86-148">Пример</span><span class="sxs-lookup"><span data-stu-id="c3b86-148">Example</span></span>  
 <span data-ttu-id="c3b86-149">В следующем примере инструкции в цикле по-прежнему выполняются, пока `index` переменной больше 10.</span><span class="sxs-lookup"><span data-stu-id="c3b86-149">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span> <span data-ttu-id="c3b86-150">`Until` Предложения — в конце цикла.</span><span class="sxs-lookup"><span data-stu-id="c3b86-150">The `Until` clause is at the end of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#131](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="c3b86-151">Пример</span><span class="sxs-lookup"><span data-stu-id="c3b86-151">Example</span></span>  
 <span data-ttu-id="c3b86-152">В следующем примере используется `While` предложение вместо `Until` предложения, и `condition` проверяется в начале цикла, а не в конце.</span><span class="sxs-lookup"><span data-stu-id="c3b86-152">The following example uses a `While` clause instead of an `Until` clause, and `condition` is tested at the start of the loop instead of at the end.</span></span>  
  
 [!code-vb[VbVbalrStatements#132](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="c3b86-153">Пример</span><span class="sxs-lookup"><span data-stu-id="c3b86-153">Example</span></span>  
 <span data-ttu-id="c3b86-154">В следующем примере `condition` останавливающее цикл при `index` переменной больше 100.</span><span class="sxs-lookup"><span data-stu-id="c3b86-154">In the following example, `condition` stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="c3b86-155">`If` Инструкции в цикле, однако вызывает `Exit Do` инструкции для остановки цикла, когда переменная индекса превышает 10.</span><span class="sxs-lookup"><span data-stu-id="c3b86-155">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#133](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="c3b86-156">Пример</span><span class="sxs-lookup"><span data-stu-id="c3b86-156">Example</span></span>  
 <span data-ttu-id="c3b86-157">Следующий пример считывает все строки в текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="c3b86-157">The following example reads all lines in a text file.</span></span> <span data-ttu-id="c3b86-158"><xref:System.IO.File.OpenText%2A> Метод открывает файл и возвращает <xref:System.IO.StreamReader> , считывает символы.</span><span class="sxs-lookup"><span data-stu-id="c3b86-158">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="c3b86-159">В `Do...Loop` условие, <xref:System.IO.StreamReader.Peek%2A> метод `StreamReader` определяет, являются ли все дополнительные символы.</span><span class="sxs-lookup"><span data-stu-id="c3b86-159">In the `Do...Loop` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether there are any additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#134](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c3b86-160">См. также</span><span class="sxs-lookup"><span data-stu-id="c3b86-160">See Also</span></span>  
 [<span data-ttu-id="c3b86-161">Циклические структуры</span><span class="sxs-lookup"><span data-stu-id="c3b86-161">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="c3b86-162">Оператор For...Next</span><span class="sxs-lookup"><span data-stu-id="c3b86-162">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="c3b86-163">Логический тип данных</span><span class="sxs-lookup"><span data-stu-id="c3b86-163">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)  
 [<span data-ttu-id="c3b86-164">Вложенные структуры управления</span><span class="sxs-lookup"><span data-stu-id="c3b86-164">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="c3b86-165">Оператор Exit</span><span class="sxs-lookup"><span data-stu-id="c3b86-165">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [<span data-ttu-id="c3b86-166">Оператор While...End While</span><span class="sxs-lookup"><span data-stu-id="c3b86-166">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
