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
ms.openlocfilehash: 3ff3d67f38f510b798da3e470de066cff1e98f29
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58826045"
---
# <a name="doloop-statement-visual-basic"></a><span data-ttu-id="beecb-102">Оператор Do...Loop (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="beecb-102">Do...Loop Statement (Visual Basic)</span></span>
<span data-ttu-id="beecb-103">Повторяет блок операторов, пока `Boolean` условие `True` или пока условие не станет `True`.</span><span class="sxs-lookup"><span data-stu-id="beecb-103">Repeats a block of statements while a `Boolean` condition is `True` or until the condition becomes `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="beecb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="beecb-104">Syntax</span></span>  
  
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
  
## <a name="parts"></a><span data-ttu-id="beecb-105">Части</span><span class="sxs-lookup"><span data-stu-id="beecb-105">Parts</span></span>  
  
|<span data-ttu-id="beecb-106">Термин</span><span class="sxs-lookup"><span data-stu-id="beecb-106">Term</span></span>|<span data-ttu-id="beecb-107">Определение</span><span class="sxs-lookup"><span data-stu-id="beecb-107">Definition</span></span>|  
|---|---|  
|`Do`|<span data-ttu-id="beecb-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="beecb-108">Required.</span></span> <span data-ttu-id="beecb-109">Начинается определение `Do` цикла.</span><span class="sxs-lookup"><span data-stu-id="beecb-109">Starts the definition of the `Do` loop.</span></span>|  
|`While`|<span data-ttu-id="beecb-110">Является обязательным, если используется параметр `Until`.</span><span class="sxs-lookup"><span data-stu-id="beecb-110">Required unless `Until` is used.</span></span> <span data-ttu-id="beecb-111">Повторите цикл до `condition` является `False`.</span><span class="sxs-lookup"><span data-stu-id="beecb-111">Repeat the loop until `condition` is `False`.</span></span>|  
|`Until`|<span data-ttu-id="beecb-112">Является обязательным, если используется параметр `While`.</span><span class="sxs-lookup"><span data-stu-id="beecb-112">Required unless `While` is used.</span></span> <span data-ttu-id="beecb-113">Повторите цикл до `condition` является `True`.</span><span class="sxs-lookup"><span data-stu-id="beecb-113">Repeat the loop until `condition` is `True`.</span></span>|  
|`condition`|<span data-ttu-id="beecb-114">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="beecb-114">Optional.</span></span> <span data-ttu-id="beecb-115">`Boolean` выражение.</span><span class="sxs-lookup"><span data-stu-id="beecb-115">`Boolean` expression.</span></span> <span data-ttu-id="beecb-116">Если `condition` — `Nothing`, Visual Basic рассматривает его как `False`.</span><span class="sxs-lookup"><span data-stu-id="beecb-116">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="beecb-117">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="beecb-117">Optional.</span></span> <span data-ttu-id="beecb-118">Один или несколько операторов, которые повторяются во время или до, `condition` является `True`.</span><span class="sxs-lookup"><span data-stu-id="beecb-118">One or more statements that are repeated while, or until, `condition` is `True`.</span></span>|  
|`Continue Do`|<span data-ttu-id="beecb-119">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="beecb-119">Optional.</span></span> <span data-ttu-id="beecb-120">Передает управление следующей итерации `Do` цикла.</span><span class="sxs-lookup"><span data-stu-id="beecb-120">Transfers control to the next iteration of the `Do` loop.</span></span>|  
|`Exit Do`|<span data-ttu-id="beecb-121">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="beecb-121">Optional.</span></span> <span data-ttu-id="beecb-122">Передает управление из `Do` цикла.</span><span class="sxs-lookup"><span data-stu-id="beecb-122">Transfers control out of the `Do` loop.</span></span>|  
|`Loop`|<span data-ttu-id="beecb-123">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="beecb-123">Required.</span></span> <span data-ttu-id="beecb-124">Завершает определение `Do` цикла.</span><span class="sxs-lookup"><span data-stu-id="beecb-124">Terminates the definition of the `Do` loop.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="beecb-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="beecb-125">Remarks</span></span>  
 <span data-ttu-id="beecb-126">Используйте `Do...Loop` структуры повторения набор инструкций неограниченное число раз, пока условие выполняется.</span><span class="sxs-lookup"><span data-stu-id="beecb-126">Use a `Do...Loop` structure when you want to repeat a set of statements an indefinite number of times, until a condition is satisfied.</span></span> <span data-ttu-id="beecb-127">Если вы хотите повторить инструкцию set несколько раз, [для... Следующий оператор](../../../visual-basic/language-reference/statements/for-next-statement.md) обычно является лучшим выбором.</span><span class="sxs-lookup"><span data-stu-id="beecb-127">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
 <span data-ttu-id="beecb-128">Можно использовать либо `While` или `Until` для указания `condition`, но не оба.</span><span class="sxs-lookup"><span data-stu-id="beecb-128">You can use either `While` or `Until` to specify `condition`, but not both.</span></span>  
  
 <span data-ttu-id="beecb-129">Вы можете протестировать `condition` только один раз, в начале или конце цикла.</span><span class="sxs-lookup"><span data-stu-id="beecb-129">You can test `condition` only one time, at either the start or the end of the loop.</span></span> <span data-ttu-id="beecb-130">Если вы проверяете `condition` в начале цикла (в `Do` инструкции), цикл не может запустить еще один раз.</span><span class="sxs-lookup"><span data-stu-id="beecb-130">If you test `condition` at the start of the loop (in the `Do` statement), the loop might not run even one time.</span></span> <span data-ttu-id="beecb-131">Если вы тестируете в конце цикла (в `Loop` инструкции), цикл всегда выполняется по крайней мере один раз.</span><span class="sxs-lookup"><span data-stu-id="beecb-131">If you test at the end of the loop (in the `Loop` statement), the loop always runs at least one time.</span></span>  
  
 <span data-ttu-id="beecb-132">Условие обычно является результатом сравнения двух значений, но он может быть любое выражение, результатом которого является [логический тип данных](../../../visual-basic/language-reference/data-types/boolean-data-type.md) значение (`True` или `False`).</span><span class="sxs-lookup"><span data-stu-id="beecb-132">The condition usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="beecb-133">Сюда входят значения других типов данных, например числовых типов, которые были преобразованы в `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="beecb-133">This includes values of other data types, such as numeric types, that have been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="beecb-134">Можно вложить `Do` циклы, поместив в одном цикле в другую.</span><span class="sxs-lookup"><span data-stu-id="beecb-134">You can nest `Do` loops by putting one loop within another.</span></span> <span data-ttu-id="beecb-135">Можно также вложить разные виды структур управления друг с другом.</span><span class="sxs-lookup"><span data-stu-id="beecb-135">You can also nest different kinds of control structures within each other.</span></span> <span data-ttu-id="beecb-136">Дополнительные сведения см. в разделе [вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="beecb-136">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="beecb-137">`Do...Loop` Структура дает большую гибкость, чем [хотя... Оператор End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md) так, как это дает возможность решить, следует ли завершить цикл при `condition` перестает быть `True` или когда сначала становится `True`.</span><span class="sxs-lookup"><span data-stu-id="beecb-137">The `Do...Loop` structure gives you more flexibility than the [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md) because it enables you to decide whether to end the loop when `condition` stops being `True` or when it first becomes `True`.</span></span> <span data-ttu-id="beecb-138">Он также позволяет тестировать `condition` в начале или конце цикла.</span><span class="sxs-lookup"><span data-stu-id="beecb-138">It also enables you to test `condition` at either the start or the end of the loop.</span></span>  
  
## <a name="exit-do"></a><span data-ttu-id="beecb-139">Exit</span><span class="sxs-lookup"><span data-stu-id="beecb-139">Exit Do</span></span>  
 <span data-ttu-id="beecb-140">[Выйти из сделать](../../../visual-basic/language-reference/statements/exit-statement.md) оператор может предоставить альтернативный способ выхода из `Do…Loop`.</span><span class="sxs-lookup"><span data-stu-id="beecb-140">The [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide an alternative way to exit a `Do…Loop`.</span></span> <span data-ttu-id="beecb-141">`Exit Do` Управление передается оператору, который расположен `Loop` инструкции.</span><span class="sxs-lookup"><span data-stu-id="beecb-141">`Exit Do` transfers control immediately to the statement that follows the `Loop` statement.</span></span>  
  
 <span data-ttu-id="beecb-142">`Exit Do` часто используется после вычисления некоторого условия, например в `If...Then...Else` структуры.</span><span class="sxs-lookup"><span data-stu-id="beecb-142">`Exit Do` is often used after some condition is evaluated, for example in an `If...Then...Else` structure.</span></span> <span data-ttu-id="beecb-143">Может потребоваться выйти из цикла, если определяет условие, которое делает бесполезным или невозможным продолжение итераций, например ошибочное значение или запрос на завершение.</span><span class="sxs-lookup"><span data-stu-id="beecb-143">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="beecb-144">Один из способов использования `Exit Do` — проверить условие, которое может привести к *бесконечный цикл*, который является цикл, который может запустить большое или возможно, бесконечное число раз.</span><span class="sxs-lookup"><span data-stu-id="beecb-144">One use of `Exit Do` is to test for a condition that could cause an *endless loop*, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="beecb-145">Можно использовать `Exit Do` для выхода из цикла.</span><span class="sxs-lookup"><span data-stu-id="beecb-145">You can use `Exit Do` to escape the loop.</span></span>  
  
 <span data-ttu-id="beecb-146">Можно включить любое число `Exit Do` инструкций в любом месте в `Do…Loop`.</span><span class="sxs-lookup"><span data-stu-id="beecb-146">You can include any number of `Exit Do` statements anywhere in a `Do…Loop`.</span></span>  
  
 <span data-ttu-id="beecb-147">При использовании внутри вложенной `Do` циклы, `Exit Do` передает управление из самого внутреннего цикла и поместить в следующий уровень вложенности.</span><span class="sxs-lookup"><span data-stu-id="beecb-147">When used within nested `Do` loops, `Exit Do` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="beecb-148">Пример</span><span class="sxs-lookup"><span data-stu-id="beecb-148">Example</span></span>  
 <span data-ttu-id="beecb-149">В следующем примере операторы в цикле продолжать выполняться до `index` переменной превышает 10.</span><span class="sxs-lookup"><span data-stu-id="beecb-149">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span> <span data-ttu-id="beecb-150">`Until` Предложение находится в конце цикла.</span><span class="sxs-lookup"><span data-stu-id="beecb-150">The `Until` clause is at the end of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#131](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#131)]  
  
## <a name="example"></a><span data-ttu-id="beecb-151">Пример</span><span class="sxs-lookup"><span data-stu-id="beecb-151">Example</span></span>  
 <span data-ttu-id="beecb-152">В следующем примере используется `While` предложение вместо `Until` предложение, и `condition` тестируется в начале цикла, а не в конце.</span><span class="sxs-lookup"><span data-stu-id="beecb-152">The following example uses a `While` clause instead of an `Until` clause, and `condition` is tested at the start of the loop instead of at the end.</span></span>  
  
 [!code-vb[VbVbalrStatements#132](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#132)]  
  
## <a name="example"></a><span data-ttu-id="beecb-153">Пример</span><span class="sxs-lookup"><span data-stu-id="beecb-153">Example</span></span>  
 <span data-ttu-id="beecb-154">В следующем примере `condition` останавливающее цикл при `index` переменной превышает 100.</span><span class="sxs-lookup"><span data-stu-id="beecb-154">In the following example, `condition` stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="beecb-155">`If` Оператора цикла, однако вызывает `Exit Do` инструкции для остановки цикла, когда переменная индекса превышает 10.</span><span class="sxs-lookup"><span data-stu-id="beecb-155">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a><span data-ttu-id="beecb-156">Пример</span><span class="sxs-lookup"><span data-stu-id="beecb-156">Example</span></span>  
 <span data-ttu-id="beecb-157">В следующем примере считываются все строки в текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="beecb-157">The following example reads all lines in a text file.</span></span> <span data-ttu-id="beecb-158"><xref:System.IO.File.OpenText%2A> Метод открывает файл и возвращает <xref:System.IO.StreamReader> , считывает символы.</span><span class="sxs-lookup"><span data-stu-id="beecb-158">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="beecb-159">В `Do...Loop` условие, <xref:System.IO.StreamReader.Peek%2A> метод `StreamReader` определяет, существуют ли все дополнительные символы.</span><span class="sxs-lookup"><span data-stu-id="beecb-159">In the `Do...Loop` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether there are any additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#134](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#134)]  
  
## <a name="see-also"></a><span data-ttu-id="beecb-160">См. также</span><span class="sxs-lookup"><span data-stu-id="beecb-160">See also</span></span>

- [<span data-ttu-id="beecb-161">Циклические структуры</span><span class="sxs-lookup"><span data-stu-id="beecb-161">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="beecb-162">Оператор For...Next</span><span class="sxs-lookup"><span data-stu-id="beecb-162">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="beecb-163">Логический тип данных</span><span class="sxs-lookup"><span data-stu-id="beecb-163">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="beecb-164">Вложенные структуры управления</span><span class="sxs-lookup"><span data-stu-id="beecb-164">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="beecb-165">Оператор Exit</span><span class="sxs-lookup"><span data-stu-id="beecb-165">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="beecb-166">Оператор While...End While</span><span class="sxs-lookup"><span data-stu-id="beecb-166">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
