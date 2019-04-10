---
title: Практическое руководство. Создать лямбда-выражения (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: fc2b7ed2004b842116d051b393f00506428def61
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59344550"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a><span data-ttu-id="96dd5-102">Практическое руководство. Создать лямбда-выражения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96dd5-102">How to: Create a Lambda Expression (Visual Basic)</span></span>
<span data-ttu-id="96dd5-103">Объект *лямбда-выражение* функцию или подпрограмму, которая не имеет имени.</span><span class="sxs-lookup"><span data-stu-id="96dd5-103">A *lambda expression* is a function or subroutine that does not have a name.</span></span> <span data-ttu-id="96dd5-104">Лямбда-выражение может использоваться везде, где допустим тип делегата.</span><span class="sxs-lookup"><span data-stu-id="96dd5-104">A lambda expression can be used wherever a delegate type is valid.</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a><span data-ttu-id="96dd5-105">Чтобы создать функцию однострочное лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="96dd5-105">To create a single-line lambda expression function</span></span>  
  
1. <span data-ttu-id="96dd5-106">В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Function`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="96dd5-106">In any situation where a delegate type could be used, type the keyword `Function`, as in the following example:</span></span>  
  
     `Dim add1 =`   `Function`  
  
2. <span data-ttu-id="96dd5-107">В скобках сразу после `Function`, введите параметры функции.</span><span class="sxs-lookup"><span data-stu-id="96dd5-107">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="96dd5-108">Обратите внимание на то, что не нужно указывать имя после `Function`.</span><span class="sxs-lookup"><span data-stu-id="96dd5-108">Notice that you do not specify a name after `Function`.</span></span>  
  
     `Dim add1 = Function`   `(num As Integer)`  
  
3. <span data-ttu-id="96dd5-109">Список параметров введите одно выражение в теле функции.</span><span class="sxs-lookup"><span data-stu-id="96dd5-109">Following the parameter list, type a single expression as the body of the function.</span></span> <span data-ttu-id="96dd5-110">Выражение, результатом которого является значение является значением, возвращаемым функцией.</span><span class="sxs-lookup"><span data-stu-id="96dd5-110">The value that the expression evaluates to is the value returned by the function.</span></span> <span data-ttu-id="96dd5-111">Вы не используете `As` предложение, чтобы указать тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="96dd5-111">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
     <span data-ttu-id="96dd5-112">Лямбда-выражение вызывается путем передачи в целочисленный аргумент.</span><span class="sxs-lookup"><span data-stu-id="96dd5-112">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
4. <span data-ttu-id="96dd5-113">Кроме того в следующем примере выполняется тот же результат:</span><span class="sxs-lookup"><span data-stu-id="96dd5-113">Alternatively, the same result is accomplished by the following example:</span></span>  
  
     [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a><span data-ttu-id="96dd5-114">Создание подпрограммы однострочное лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="96dd5-114">To create a single-line lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="96dd5-115">В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Sub`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="96dd5-115">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example.</span></span>  
  
     `Dim add1 =`   `Sub`  
  
2. <span data-ttu-id="96dd5-116">В скобках сразу после `Sub`, введите параметры подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="96dd5-116">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="96dd5-117">Обратите внимание на то, что не нужно указывать имя после `Sub`.</span><span class="sxs-lookup"><span data-stu-id="96dd5-117">Notice that you do not specify a name after `Sub`.</span></span>  
  
     `Dim add1 = Sub`   `(msg As String)`  
  
3. <span data-ttu-id="96dd5-118">Список параметров введите одной инструкции в теле подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="96dd5-118">Following the parameter list, type a single statement as the body of the subroutine.</span></span>  
  
     [!code-vb[VbVbalrLambdas#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#17)]  
  
     <span data-ttu-id="96dd5-119">Лямбда-выражение вызывается путем передачи аргумента строки.</span><span class="sxs-lookup"><span data-stu-id="96dd5-119">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#18)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a><span data-ttu-id="96dd5-120">Для создания многострочных лямбда-выражение функции</span><span class="sxs-lookup"><span data-stu-id="96dd5-120">To create a multiline lambda expression function</span></span>  
  
1. <span data-ttu-id="96dd5-121">В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Function`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="96dd5-121">In any situation where a delegate type could be used, type the keyword `Function`, as shown in the following example.</span></span>  
  
     `Dim add1 =`   `Function`  
  
2. <span data-ttu-id="96dd5-122">В скобках сразу после `Function`, введите параметры функции.</span><span class="sxs-lookup"><span data-stu-id="96dd5-122">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="96dd5-123">Обратите внимание на то, что не нужно указывать имя после `Function`.</span><span class="sxs-lookup"><span data-stu-id="96dd5-123">Notice that you do not specify a name after `Function`.</span></span>  
  
     `Dim add1 = Function`   `(index As Integer)`  
  
3. <span data-ttu-id="96dd5-124">Нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="96dd5-124">Press ENTER.</span></span> <span data-ttu-id="96dd5-125">`End Function` Автоматически добавляется инструкция.</span><span class="sxs-lookup"><span data-stu-id="96dd5-125">The `End Function` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="96dd5-126">В теле функции добавьте следующий код, чтобы создать выражение и возвращают значение.</span><span class="sxs-lookup"><span data-stu-id="96dd5-126">Within the body of the function, add the following code to create an expression and return the value.</span></span> <span data-ttu-id="96dd5-127">Вы не используете `As` предложение, чтобы указать тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="96dd5-127">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#19)]  
  
     <span data-ttu-id="96dd5-128">Лямбда-выражение вызывается путем передачи в целочисленный аргумент.</span><span class="sxs-lookup"><span data-stu-id="96dd5-128">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#20)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a><span data-ttu-id="96dd5-129">Создание выражения подпрограммы многострочного лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="96dd5-129">To create a multiline lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="96dd5-130">В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Sub`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="96dd5-130">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example:</span></span>  
  
     `Dim add1 =`   `Sub`  
  
2. <span data-ttu-id="96dd5-131">В скобках сразу после `Sub`, введите параметры подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="96dd5-131">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="96dd5-132">Обратите внимание на то, что не нужно указывать имя после `Sub`.</span><span class="sxs-lookup"><span data-stu-id="96dd5-132">Notice that you do not specify a name after `Sub`.</span></span>  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3. <span data-ttu-id="96dd5-133">Нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="96dd5-133">Press ENTER.</span></span> <span data-ttu-id="96dd5-134">`End Sub` Автоматически добавляется инструкция.</span><span class="sxs-lookup"><span data-stu-id="96dd5-134">The `End Sub` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="96dd5-135">В теле функции добавьте следующий код для выполнения при вызове подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="96dd5-135">Within the body of the function, add the following code to execute when the subroutine is invoked.</span></span>  
  
     [!code-vb[VbVbalrLambdas#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#21)]  
  
     <span data-ttu-id="96dd5-136">Лямбда-выражение вызывается путем передачи аргумента строки.</span><span class="sxs-lookup"><span data-stu-id="96dd5-136">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="96dd5-137">Пример</span><span class="sxs-lookup"><span data-stu-id="96dd5-137">Example</span></span>  
 <span data-ttu-id="96dd5-138">Обычно лямбда-выражений используется для определения функции, который может передаваться в качестве аргумента для параметра, тип которого является `Delegate`.</span><span class="sxs-lookup"><span data-stu-id="96dd5-138">A common use of lambda expressions is to define a function that can be passed in as the argument for a parameter whose type is `Delegate`.</span></span> <span data-ttu-id="96dd5-139">В следующем примере <xref:System.Diagnostics.Process.GetProcesses%2A> метод возвращает массив процессов, запущенных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="96dd5-139">In the following example, the <xref:System.Diagnostics.Process.GetProcesses%2A> method returns an array of the processes running on the local computer.</span></span> <span data-ttu-id="96dd5-140"><xref:System.Linq.Enumerable.Where%2A> Метода из <xref:System.Linq.Enumerable> классу `Boolean` делегат в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="96dd5-140">The <xref:System.Linq.Enumerable.Where%2A> method from the <xref:System.Linq.Enumerable> class requires a `Boolean` delegate as its argument.</span></span> <span data-ttu-id="96dd5-141">Лямбда-выражение в примере используется для этой цели.</span><span class="sxs-lookup"><span data-stu-id="96dd5-141">The lambda expression in the example is used for that purpose.</span></span> <span data-ttu-id="96dd5-142">Он возвращает `True` каждого процесса, у которой есть только один поток, а те, выбранные в `filteredList`.</span><span class="sxs-lookup"><span data-stu-id="96dd5-142">It returns `True` for each process that has only one thread, and those are selected in `filteredList`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class4.vb#10)]  
  
 <span data-ttu-id="96dd5-143">Предыдущий пример эквивалентен следующий код, написанный на [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] синтаксис:</span><span class="sxs-lookup"><span data-stu-id="96dd5-143">The previous example is equivalent to the following code, which is written in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] syntax:</span></span>  
  
 [!code-vb[VbVbalrLambdas#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class5.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="96dd5-144">См. также</span><span class="sxs-lookup"><span data-stu-id="96dd5-144">See also</span></span>

- <xref:System.Linq.Enumerable>
- [<span data-ttu-id="96dd5-145">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="96dd5-145">Lambda Expressions</span></span>](./lambda-expressions.md)
- [<span data-ttu-id="96dd5-146">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="96dd5-146">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="96dd5-147">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="96dd5-147">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="96dd5-148">Делегаты</span><span class="sxs-lookup"><span data-stu-id="96dd5-148">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="96dd5-149">Практическое руководство. Передача процедур другой процедуре в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="96dd5-149">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="96dd5-150">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="96dd5-150">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="96dd5-151">Знакомство с LINQ в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="96dd5-151">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
