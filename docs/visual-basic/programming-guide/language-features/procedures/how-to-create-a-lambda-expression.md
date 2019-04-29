---
title: Практическое руководство. Создать лямбда-выражения (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: fc2b7ed2004b842116d051b393f00506428def61
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61665940"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a><span data-ttu-id="1fe5b-102">Практическое руководство. Создать лямбда-выражения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1fe5b-102">How to: Create a Lambda Expression (Visual Basic)</span></span>
<span data-ttu-id="1fe5b-103">Объект *лямбда-выражение* функцию или подпрограмму, которая не имеет имени.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-103">A *lambda expression* is a function or subroutine that does not have a name.</span></span> <span data-ttu-id="1fe5b-104">Лямбда-выражение может использоваться везде, где допустим тип делегата.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-104">A lambda expression can be used wherever a delegate type is valid.</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a><span data-ttu-id="1fe5b-105">Чтобы создать функцию однострочное лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="1fe5b-105">To create a single-line lambda expression function</span></span>  
  
1. <span data-ttu-id="1fe5b-106">В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Function`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="1fe5b-106">In any situation where a delegate type could be used, type the keyword `Function`, as in the following example:</span></span>  
  
     <span data-ttu-id="1fe5b-107">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="1fe5b-107">`Dim add1 =`   `Function`</span></span>  
  
2. <span data-ttu-id="1fe5b-108">В скобках сразу после `Function`, введите параметры функции.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-108">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="1fe5b-109">Обратите внимание на то, что не нужно указывать имя после `Function`.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-109">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="1fe5b-110">`Dim add1 = Function`   `(num As Integer)`</span><span class="sxs-lookup"><span data-stu-id="1fe5b-110">`Dim add1 = Function`   `(num As Integer)`</span></span>  
  
3. <span data-ttu-id="1fe5b-111">Список параметров введите одно выражение в теле функции.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-111">Following the parameter list, type a single expression as the body of the function.</span></span> <span data-ttu-id="1fe5b-112">Выражение, результатом которого является значение является значением, возвращаемым функцией.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-112">The value that the expression evaluates to is the value returned by the function.</span></span> <span data-ttu-id="1fe5b-113">Вы не используете `As` предложение, чтобы указать тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-113">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
     <span data-ttu-id="1fe5b-114">Лямбда-выражение вызывается путем передачи в целочисленный аргумент.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-114">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
4. <span data-ttu-id="1fe5b-115">Кроме того в следующем примере выполняется тот же результат:</span><span class="sxs-lookup"><span data-stu-id="1fe5b-115">Alternatively, the same result is accomplished by the following example:</span></span>  
  
     [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a><span data-ttu-id="1fe5b-116">Создание подпрограммы однострочное лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="1fe5b-116">To create a single-line lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="1fe5b-117">В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Sub`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-117">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="1fe5b-118">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="1fe5b-118">`Dim add1 =`   `Sub`</span></span>  
  
2. <span data-ttu-id="1fe5b-119">В скобках сразу после `Sub`, введите параметры подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-119">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="1fe5b-120">Обратите внимание на то, что не нужно указывать имя после `Sub`.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-120">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="1fe5b-121">`Dim add1 = Sub`   `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="1fe5b-121">`Dim add1 = Sub`   `(msg As String)`</span></span>  
  
3. <span data-ttu-id="1fe5b-122">Список параметров введите одной инструкции в теле подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-122">Following the parameter list, type a single statement as the body of the subroutine.</span></span>  
  
     [!code-vb[VbVbalrLambdas#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#17)]  
  
     <span data-ttu-id="1fe5b-123">Лямбда-выражение вызывается путем передачи аргумента строки.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-123">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#18)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a><span data-ttu-id="1fe5b-124">Для создания многострочных лямбда-выражение функции</span><span class="sxs-lookup"><span data-stu-id="1fe5b-124">To create a multiline lambda expression function</span></span>  
  
1. <span data-ttu-id="1fe5b-125">В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Function`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-125">In any situation where a delegate type could be used, type the keyword `Function`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="1fe5b-126">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="1fe5b-126">`Dim add1 =`   `Function`</span></span>  
  
2. <span data-ttu-id="1fe5b-127">В скобках сразу после `Function`, введите параметры функции.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-127">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="1fe5b-128">Обратите внимание на то, что не нужно указывать имя после `Function`.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-128">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="1fe5b-129">`Dim add1 = Function`   `(index As Integer)`</span><span class="sxs-lookup"><span data-stu-id="1fe5b-129">`Dim add1 = Function`   `(index As Integer)`</span></span>  
  
3. <span data-ttu-id="1fe5b-130">Нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-130">Press ENTER.</span></span> <span data-ttu-id="1fe5b-131">`End Function` Автоматически добавляется инструкция.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-131">The `End Function` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="1fe5b-132">В теле функции добавьте следующий код, чтобы создать выражение и возвращают значение.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-132">Within the body of the function, add the following code to create an expression and return the value.</span></span> <span data-ttu-id="1fe5b-133">Вы не используете `As` предложение, чтобы указать тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-133">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#19)]  
  
     <span data-ttu-id="1fe5b-134">Лямбда-выражение вызывается путем передачи в целочисленный аргумент.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-134">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#20)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a><span data-ttu-id="1fe5b-135">Создание выражения подпрограммы многострочного лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="1fe5b-135">To create a multiline lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="1fe5b-136">В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Sub`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="1fe5b-136">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example:</span></span>  
  
     <span data-ttu-id="1fe5b-137">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="1fe5b-137">`Dim add1 =`   `Sub`</span></span>  
  
2. <span data-ttu-id="1fe5b-138">В скобках сразу после `Sub`, введите параметры подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-138">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="1fe5b-139">Обратите внимание на то, что не нужно указывать имя после `Sub`.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-139">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="1fe5b-140">`Dim add1 = Sub`  `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="1fe5b-140">`Dim add1 = Sub`  `(msg As String)`</span></span>  
  
3. <span data-ttu-id="1fe5b-141">Нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-141">Press ENTER.</span></span> <span data-ttu-id="1fe5b-142">`End Sub` Автоматически добавляется инструкция.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-142">The `End Sub` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="1fe5b-143">В теле функции добавьте следующий код для выполнения при вызове подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-143">Within the body of the function, add the following code to execute when the subroutine is invoked.</span></span>  
  
     [!code-vb[VbVbalrLambdas#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#21)]  
  
     <span data-ttu-id="1fe5b-144">Лямбда-выражение вызывается путем передачи аргумента строки.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-144">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="1fe5b-145">Пример</span><span class="sxs-lookup"><span data-stu-id="1fe5b-145">Example</span></span>  
 <span data-ttu-id="1fe5b-146">Обычно лямбда-выражений используется для определения функции, который может передаваться в качестве аргумента для параметра, тип которого является `Delegate`.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-146">A common use of lambda expressions is to define a function that can be passed in as the argument for a parameter whose type is `Delegate`.</span></span> <span data-ttu-id="1fe5b-147">В следующем примере <xref:System.Diagnostics.Process.GetProcesses%2A> метод возвращает массив процессов, запущенных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-147">In the following example, the <xref:System.Diagnostics.Process.GetProcesses%2A> method returns an array of the processes running on the local computer.</span></span> <span data-ttu-id="1fe5b-148"><xref:System.Linq.Enumerable.Where%2A> Метода из <xref:System.Linq.Enumerable> классу `Boolean` делегат в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-148">The <xref:System.Linq.Enumerable.Where%2A> method from the <xref:System.Linq.Enumerable> class requires a `Boolean` delegate as its argument.</span></span> <span data-ttu-id="1fe5b-149">Лямбда-выражение в примере используется для этой цели.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-149">The lambda expression in the example is used for that purpose.</span></span> <span data-ttu-id="1fe5b-150">Он возвращает `True` каждого процесса, у которой есть только один поток, а те, выбранные в `filteredList`.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-150">It returns `True` for each process that has only one thread, and those are selected in `filteredList`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class4.vb#10)]  
  
 <span data-ttu-id="1fe5b-151">Предыдущий пример эквивалентен следующий код, написанный на [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] синтаксис:</span><span class="sxs-lookup"><span data-stu-id="1fe5b-151">The previous example is equivalent to the following code, which is written in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] syntax:</span></span>  
  
 [!code-vb[VbVbalrLambdas#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class5.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="1fe5b-152">См. также</span><span class="sxs-lookup"><span data-stu-id="1fe5b-152">See also</span></span>

- <xref:System.Linq.Enumerable>
- [<span data-ttu-id="1fe5b-153">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="1fe5b-153">Lambda Expressions</span></span>](./lambda-expressions.md)
- [<span data-ttu-id="1fe5b-154">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="1fe5b-154">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="1fe5b-155">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="1fe5b-155">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="1fe5b-156">Делегаты</span><span class="sxs-lookup"><span data-stu-id="1fe5b-156">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="1fe5b-157">Практическое руководство. Передача процедур другой процедуре в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1fe5b-157">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="1fe5b-158">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="1fe5b-158">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- <span data-ttu-id="1fe5b-159">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1fe5b-159">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
