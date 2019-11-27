---
title: Практическое руководство. Создание лямбда-выражения
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: bb0bdb3c10a7df2ca954fbdb9382a25bf805068d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349745"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a><span data-ttu-id="493e2-102">Практическое руководство. Создание лямбда-выражения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="493e2-102">How to: Create a Lambda Expression (Visual Basic)</span></span>
<span data-ttu-id="493e2-103">*Лямбда-выражение* — это функция или подпрограммы, у которой нет имени.</span><span class="sxs-lookup"><span data-stu-id="493e2-103">A *lambda expression* is a function or subroutine that does not have a name.</span></span> <span data-ttu-id="493e2-104">Лямбда-выражение может использоваться везде, где допустим тип делегата.</span><span class="sxs-lookup"><span data-stu-id="493e2-104">A lambda expression can be used wherever a delegate type is valid.</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a><span data-ttu-id="493e2-105">Создание однострочной функции лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="493e2-105">To create a single-line lambda expression function</span></span>  
  
1. <span data-ttu-id="493e2-106">В любой ситуации, где можно использовать тип делегата, введите ключевое слово `Function`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="493e2-106">In any situation where a delegate type could be used, type the keyword `Function`, as in the following example:</span></span>  
  
     <span data-ttu-id="493e2-107">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="493e2-107">`Dim add1 =`   `Function`</span></span>  
  
2. <span data-ttu-id="493e2-108">В скобках сразу после `Function`введите параметры функции.</span><span class="sxs-lookup"><span data-stu-id="493e2-108">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="493e2-109">Обратите внимание, что имя не указывается после `Function`.</span><span class="sxs-lookup"><span data-stu-id="493e2-109">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="493e2-110">`Dim add1 = Function`   `(num As Integer)`</span><span class="sxs-lookup"><span data-stu-id="493e2-110">`Dim add1 = Function`   `(num As Integer)`</span></span>  
  
3. <span data-ttu-id="493e2-111">После списка параметров введите одно выражение в качестве текста функции.</span><span class="sxs-lookup"><span data-stu-id="493e2-111">Following the parameter list, type a single expression as the body of the function.</span></span> <span data-ttu-id="493e2-112">Значение, которое вычисляется выражением, — это значение, возвращаемое функцией.</span><span class="sxs-lookup"><span data-stu-id="493e2-112">The value that the expression evaluates to is the value returned by the function.</span></span> <span data-ttu-id="493e2-113">Не используйте предложение `As`, чтобы указать тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="493e2-113">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
     <span data-ttu-id="493e2-114">Лямбда-выражение вызывается путем передачи целочисленного аргумента.</span><span class="sxs-lookup"><span data-stu-id="493e2-114">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
4. <span data-ttu-id="493e2-115">Кроме того, тот же результат достигается в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="493e2-115">Alternatively, the same result is accomplished by the following example:</span></span>  
  
     [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a><span data-ttu-id="493e2-116">Создание однострочной подпрограммы лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="493e2-116">To create a single-line lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="493e2-117">В любой ситуации, где можно использовать тип делегата, введите ключевое слово `Sub`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="493e2-117">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="493e2-118">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="493e2-118">`Dim add1 =`   `Sub`</span></span>  
  
2. <span data-ttu-id="493e2-119">В скобках сразу после `Sub`введите параметры подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="493e2-119">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="493e2-120">Обратите внимание, что имя не указывается после `Sub`.</span><span class="sxs-lookup"><span data-stu-id="493e2-120">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="493e2-121">`Dim add1 = Sub`   `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="493e2-121">`Dim add1 = Sub`   `(msg As String)`</span></span>  
  
3. <span data-ttu-id="493e2-122">После списка параметров введите один оператор в качестве текста подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="493e2-122">Following the parameter list, type a single statement as the body of the subroutine.</span></span>  
  
     [!code-vb[VbVbalrLambdas#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#17)]  
  
     <span data-ttu-id="493e2-123">Лямбда-выражение вызывается путем передачи строкового аргумента.</span><span class="sxs-lookup"><span data-stu-id="493e2-123">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#18)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a><span data-ttu-id="493e2-124">Создание многострочной функции лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="493e2-124">To create a multiline lambda expression function</span></span>  
  
1. <span data-ttu-id="493e2-125">В любой ситуации, где можно использовать тип делегата, введите ключевое слово `Function`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="493e2-125">In any situation where a delegate type could be used, type the keyword `Function`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="493e2-126">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="493e2-126">`Dim add1 =`   `Function`</span></span>  
  
2. <span data-ttu-id="493e2-127">В скобках сразу после `Function`введите параметры функции.</span><span class="sxs-lookup"><span data-stu-id="493e2-127">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="493e2-128">Обратите внимание, что имя не указывается после `Function`.</span><span class="sxs-lookup"><span data-stu-id="493e2-128">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="493e2-129">`Dim add1 = Function`   `(index As Integer)`</span><span class="sxs-lookup"><span data-stu-id="493e2-129">`Dim add1 = Function`   `(index As Integer)`</span></span>  
  
3. <span data-ttu-id="493e2-130">Нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="493e2-130">Press ENTER.</span></span> <span data-ttu-id="493e2-131">Инструкция `End Function` добавляется автоматически.</span><span class="sxs-lookup"><span data-stu-id="493e2-131">The `End Function` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="493e2-132">В теле функции добавьте следующий код, чтобы создать выражение и вернуть значение.</span><span class="sxs-lookup"><span data-stu-id="493e2-132">Within the body of the function, add the following code to create an expression and return the value.</span></span> <span data-ttu-id="493e2-133">Не используйте предложение `As`, чтобы указать тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="493e2-133">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#19)]  
  
     <span data-ttu-id="493e2-134">Лямбда-выражение вызывается путем передачи целочисленного аргумента.</span><span class="sxs-lookup"><span data-stu-id="493e2-134">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#20)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a><span data-ttu-id="493e2-135">Создание многострочной подпрограммы лямбда-выражений</span><span class="sxs-lookup"><span data-stu-id="493e2-135">To create a multiline lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="493e2-136">В любой ситуации, где можно использовать тип делегата, введите ключевое слово `Sub`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="493e2-136">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example:</span></span>  
  
     <span data-ttu-id="493e2-137">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="493e2-137">`Dim add1 =`   `Sub`</span></span>  
  
2. <span data-ttu-id="493e2-138">В скобках сразу после `Sub`введите параметры подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="493e2-138">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="493e2-139">Обратите внимание, что имя не указывается после `Sub`.</span><span class="sxs-lookup"><span data-stu-id="493e2-139">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="493e2-140">`Dim add1 = Sub`  `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="493e2-140">`Dim add1 = Sub`  `(msg As String)`</span></span>  
  
3. <span data-ttu-id="493e2-141">Нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="493e2-141">Press ENTER.</span></span> <span data-ttu-id="493e2-142">Инструкция `End Sub` добавляется автоматически.</span><span class="sxs-lookup"><span data-stu-id="493e2-142">The `End Sub` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="493e2-143">В теле функции добавьте следующий код для выполнения при вызове подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="493e2-143">Within the body of the function, add the following code to execute when the subroutine is invoked.</span></span>  
  
     [!code-vb[VbVbalrLambdas#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#21)]  
  
     <span data-ttu-id="493e2-144">Лямбда-выражение вызывается путем передачи строкового аргумента.</span><span class="sxs-lookup"><span data-stu-id="493e2-144">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="493e2-145">Пример</span><span class="sxs-lookup"><span data-stu-id="493e2-145">Example</span></span>  
 <span data-ttu-id="493e2-146">Обычно лямбда-выражения используются для определения функции, которую можно передать в качестве аргумента для параметра, тип которого `Delegate`.</span><span class="sxs-lookup"><span data-stu-id="493e2-146">A common use of lambda expressions is to define a function that can be passed in as the argument for a parameter whose type is `Delegate`.</span></span> <span data-ttu-id="493e2-147">В следующем примере метод <xref:System.Diagnostics.Process.GetProcesses%2A> возвращает массив процессов, запущенных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="493e2-147">In the following example, the <xref:System.Diagnostics.Process.GetProcesses%2A> method returns an array of the processes running on the local computer.</span></span> <span data-ttu-id="493e2-148">Для метода <xref:System.Linq.Enumerable.Where%2A> из класса <xref:System.Linq.Enumerable> требуется `Boolean` делегат в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="493e2-148">The <xref:System.Linq.Enumerable.Where%2A> method from the <xref:System.Linq.Enumerable> class requires a `Boolean` delegate as its argument.</span></span> <span data-ttu-id="493e2-149">Лямбда-выражение в примере используется для этой цели.</span><span class="sxs-lookup"><span data-stu-id="493e2-149">The lambda expression in the example is used for that purpose.</span></span> <span data-ttu-id="493e2-150">Он возвращает `True` для каждого процесса, который имеет только один поток, и выбранные в `filteredList`.</span><span class="sxs-lookup"><span data-stu-id="493e2-150">It returns `True` for each process that has only one thread, and those are selected in `filteredList`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class4.vb#10)]  
  
 <span data-ttu-id="493e2-151">Предыдущий пример эквивалентен следующему коду, написанному на [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] синтаксисе:</span><span class="sxs-lookup"><span data-stu-id="493e2-151">The previous example is equivalent to the following code, which is written in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] syntax:</span></span>  
  
 [!code-vb[VbVbalrLambdas#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class5.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="493e2-152">См. также</span><span class="sxs-lookup"><span data-stu-id="493e2-152">See also</span></span>

- <xref:System.Linq.Enumerable>
- [<span data-ttu-id="493e2-153">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="493e2-153">Lambda Expressions</span></span>](./lambda-expressions.md)
- [<span data-ttu-id="493e2-154">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="493e2-154">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="493e2-155">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="493e2-155">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="493e2-156">Делегаты</span><span class="sxs-lookup"><span data-stu-id="493e2-156">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- <span data-ttu-id="493e2-157">[How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) (Практическое руководство. Передача процедур другой процедуре в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="493e2-157">[How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)</span></span>
- [<span data-ttu-id="493e2-158">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="493e2-158">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- <span data-ttu-id="493e2-159">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="493e2-159">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
