---
title: Практическое руководство. Создание лямбда-выражения (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: f437166bc5206b4145d6508aa2131ec94d6eca95
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/25/2018
ms.locfileid: "39244902"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a><span data-ttu-id="e4c8c-102">Практическое руководство. Создание лямбда-выражения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e4c8c-102">How to: Create a Lambda Expression (Visual Basic)</span></span>
<span data-ttu-id="e4c8c-103">Объект *лямбда-выражение* функцию или подпрограмму, которая не имеет имени.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-103">A *lambda expression* is a function or subroutine that does not have a name.</span></span> <span data-ttu-id="e4c8c-104">Лямбда-выражение может использоваться везде, где допустим тип делегата.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-104">A lambda expression can be used wherever a delegate type is valid.</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a><span data-ttu-id="e4c8c-105">Чтобы создать функцию однострочное лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="e4c8c-105">To create a single-line lambda expression function</span></span>  
  
1.  <span data-ttu-id="e4c8c-106">В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Function`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e4c8c-106">In any situation where a delegate type could be used, type the keyword `Function`, as in the following example:</span></span>  
  
     <span data-ttu-id="e4c8c-107">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="e4c8c-107">`Dim add1 =`   `Function`</span></span>  
  
2.  <span data-ttu-id="e4c8c-108">В скобках сразу после `Function`, введите параметры функции.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-108">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="e4c8c-109">Обратите внимание на то, что не нужно указывать имя после `Function`.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-109">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="e4c8c-110">`Dim add1 = Function`   `(num As Integer)`</span><span class="sxs-lookup"><span data-stu-id="e4c8c-110">`Dim add1 = Function`   `(num As Integer)`</span></span>  
  
3.  <span data-ttu-id="e4c8c-111">Список параметров введите одно выражение в теле функции.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-111">Following the parameter list, type a single expression as the body of the function.</span></span> <span data-ttu-id="e4c8c-112">Выражение, результатом которого является значение является значением, возвращаемым функцией.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-112">The value that the expression evaluates to is the value returned by the function.</span></span> <span data-ttu-id="e4c8c-113">Вы не используете `As` предложение, чтобы указать тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-113">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_1.vb)]  
  
     <span data-ttu-id="e4c8c-114">Лямбда-выражение вызывается путем передачи в целочисленный аргумент.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-114">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_2.vb)]  
  
4.  <span data-ttu-id="e4c8c-115">Кроме того в следующем примере выполняется тот же результат:</span><span class="sxs-lookup"><span data-stu-id="e4c8c-115">Alternatively, the same result is accomplished by the following example:</span></span>  
  
     [!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_3.vb)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a><span data-ttu-id="e4c8c-116">Создание подпрограммы однострочное лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="e4c8c-116">To create a single-line lambda expression subroutine</span></span>  
  
1.  <span data-ttu-id="e4c8c-117">В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Sub`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-117">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="e4c8c-118">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="e4c8c-118">`Dim add1 =`   `Sub`</span></span>  
  
2.  <span data-ttu-id="e4c8c-119">В скобках сразу после `Sub`, введите параметры подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-119">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="e4c8c-120">Обратите внимание на то, что не нужно указывать имя после `Sub`.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-120">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="e4c8c-121">`Dim add1 = Sub`   `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="e4c8c-121">`Dim add1 = Sub`   `(msg As String)`</span></span>  
  
3.  <span data-ttu-id="e4c8c-122">Список параметров введите одной инструкции в теле подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-122">Following the parameter list, type a single statement as the body of the subroutine.</span></span>  
  
     [!code-vb[VbVbalrLambdas#17](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_4.vb)]  
  
     <span data-ttu-id="e4c8c-123">Лямбда-выражение вызывается путем передачи аргумента строки.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-123">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#18](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_5.vb)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a><span data-ttu-id="e4c8c-124">Для создания многострочных лямбда-выражение функции</span><span class="sxs-lookup"><span data-stu-id="e4c8c-124">To create a multiline lambda expression function</span></span>  
  
1.  <span data-ttu-id="e4c8c-125">В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Function`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-125">In any situation where a delegate type could be used, type the keyword `Function`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="e4c8c-126">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="e4c8c-126">`Dim add1 =`   `Function`</span></span>  
  
2.  <span data-ttu-id="e4c8c-127">В скобках сразу после `Function`, введите параметры функции.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-127">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="e4c8c-128">Обратите внимание на то, что не нужно указывать имя после `Function`.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-128">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="e4c8c-129">`Dim add1 = Function`   `(index As Integer)`</span><span class="sxs-lookup"><span data-stu-id="e4c8c-129">`Dim add1 = Function`   `(index As Integer)`</span></span>  
  
3.  <span data-ttu-id="e4c8c-130">Нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-130">Press ENTER.</span></span> <span data-ttu-id="e4c8c-131">`End Function` Автоматически добавляется инструкция.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-131">The `End Function` statement is automatically added.</span></span>  
  
4.  <span data-ttu-id="e4c8c-132">В теле функции добавьте следующий код, чтобы создать выражение и возвращают значение.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-132">Within the body of the function, add the following code to create an expression and return the value.</span></span> <span data-ttu-id="e4c8c-133">Вы не используете `As` предложение, чтобы указать тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-133">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#19](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_6.vb)]  
  
     <span data-ttu-id="e4c8c-134">Лямбда-выражение вызывается путем передачи в целочисленный аргумент.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-134">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#20](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_7.vb)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a><span data-ttu-id="e4c8c-135">Создание выражения подпрограммы многострочного лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="e4c8c-135">To create a multiline lambda expression subroutine</span></span>  
  
1.  <span data-ttu-id="e4c8c-136">В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Sub`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e4c8c-136">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example:</span></span>  
  
     <span data-ttu-id="e4c8c-137">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="e4c8c-137">`Dim add1 =`   `Sub`</span></span>  
  
2.  <span data-ttu-id="e4c8c-138">В скобках сразу после `Sub`, введите параметры подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-138">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="e4c8c-139">Обратите внимание на то, что не нужно указывать имя после `Sub`.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-139">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="e4c8c-140">`Dim add1 = Sub`  `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="e4c8c-140">`Dim add1 = Sub`  `(msg As String)`</span></span>  
  
3.  <span data-ttu-id="e4c8c-141">Нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-141">Press ENTER.</span></span> <span data-ttu-id="e4c8c-142">`End Sub` Автоматически добавляется инструкция.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-142">The `End Sub` statement is automatically added.</span></span>  
  
4.  <span data-ttu-id="e4c8c-143">В теле функции добавьте следующий код для выполнения при вызове подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-143">Within the body of the function, add the following code to execute when the subroutine is invoked.</span></span>  
  
     [!code-vb[VbVbalrLambdas#21](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_8.vb)]  
  
     <span data-ttu-id="e4c8c-144">Лямбда-выражение вызывается путем передачи аргумента строки.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-144">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#22](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_9.vb)]  
  
## <a name="example"></a><span data-ttu-id="e4c8c-145">Пример</span><span class="sxs-lookup"><span data-stu-id="e4c8c-145">Example</span></span>  
 <span data-ttu-id="e4c8c-146">Обычно лямбда-выражений используется для определения функции, который может передаваться в качестве аргумента для параметра, тип которого является `Delegate`.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-146">A common use of lambda expressions is to define a function that can be passed in as the argument for a parameter whose type is `Delegate`.</span></span> <span data-ttu-id="e4c8c-147">В следующем примере <xref:System.Diagnostics.Process.GetProcesses%2A> метод возвращает массив процессов, запущенных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-147">In the following example, the <xref:System.Diagnostics.Process.GetProcesses%2A> method returns an array of the processes running on the local computer.</span></span> <span data-ttu-id="e4c8c-148"><xref:System.Linq.Enumerable.Where%2A> Метода из <xref:System.Linq.Enumerable> классу `Boolean` делегат в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-148">The <xref:System.Linq.Enumerable.Where%2A> method from the <xref:System.Linq.Enumerable> class requires a `Boolean` delegate as its argument.</span></span> <span data-ttu-id="e4c8c-149">Лямбда-выражение в примере используется для этой цели.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-149">The lambda expression in the example is used for that purpose.</span></span> <span data-ttu-id="e4c8c-150">Он возвращает `True` каждого процесса, у которой есть только один поток, а те, выбранные в `filteredList`.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-150">It returns `True` for each process that has only one thread, and those are selected in `filteredList`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#10](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_10.vb)]  
  
 <span data-ttu-id="e4c8c-151">Предыдущий пример эквивалентен следующий код, написанный на [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e4c8c-151">The previous example is equivalent to the following code, which is written in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] syntax:</span></span>  
  
 [!code-vb[VbVbalrLambdas#11](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_11.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e4c8c-152">См. также</span><span class="sxs-lookup"><span data-stu-id="e4c8c-152">See Also</span></span>  
 <xref:System.Linq.Enumerable>  
 [<span data-ttu-id="e4c8c-153">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="e4c8c-153">Lambda Expressions</span></span>](./lambda-expressions.md)  
 [<span data-ttu-id="e4c8c-154">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="e4c8c-154">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="e4c8c-155">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="e4c8c-155">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="e4c8c-156">Делегаты</span><span class="sxs-lookup"><span data-stu-id="e4c8c-156">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 <span data-ttu-id="e4c8c-157">[How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) (Практическое руководство. Передача процедур другой процедуре в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e4c8c-157">[How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)</span></span>  
 [<span data-ttu-id="e4c8c-158">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="e4c8c-158">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 <span data-ttu-id="e4c8c-159">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e4c8c-159">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
