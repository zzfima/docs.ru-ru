---
title: "Практическое руководство: создание лямбда-выражения (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: edd475490dce81ff9cca32b5f9a5090d99f4d80d
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a><span data-ttu-id="76043-102">Практическое руководство. Создание лямбда-выражения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="76043-102">How to: Create a Lambda Expression (Visual Basic)</span></span>
<span data-ttu-id="76043-103">Объект *лямбда-выражение* функцию или подпрограмму, которая не имеет имени.</span><span class="sxs-lookup"><span data-stu-id="76043-103">A *lambda expression* is a function or subroutine that does not have a name.</span></span> <span data-ttu-id="76043-104">Лямбда-выражение можно использовать везде, где допустим тип делегата.</span><span class="sxs-lookup"><span data-stu-id="76043-104">A lambda expression can be used wherever a delegate type is valid.</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a><span data-ttu-id="76043-105">Чтобы создать функцию Однострочные лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="76043-105">To create a single-line lambda expression function</span></span>  
  
1.  <span data-ttu-id="76043-106">В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Function`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="76043-106">In any situation where a delegate type could be used, type the keyword `Function`, as in the following example:</span></span>  
  
     <span data-ttu-id="76043-107">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="76043-107">`Dim add1 =`   `Function`</span></span>  
  
2.  <span data-ttu-id="76043-108">В скобках непосредственно после `Function`, введите параметры функции.</span><span class="sxs-lookup"><span data-stu-id="76043-108">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="76043-109">Обратите внимание, что не задано имя после `Function`.</span><span class="sxs-lookup"><span data-stu-id="76043-109">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="76043-110">`Dim add1 = Function`   `(num As Integer)`</span><span class="sxs-lookup"><span data-stu-id="76043-110">`Dim add1 = Function`   `(num As Integer)`</span></span>  
  
3.  <span data-ttu-id="76043-111">Вслед за списком параметров введите одно выражение как тело функции.</span><span class="sxs-lookup"><span data-stu-id="76043-111">Following the parameter list, type a single expression as the body of the function.</span></span> <span data-ttu-id="76043-112">Значение, выражение, результатом вычисления которого является значение, возвращаемое функцией.</span><span class="sxs-lookup"><span data-stu-id="76043-112">The value that the expression evaluates to is the value returned by the function.</span></span> <span data-ttu-id="76043-113">Не используйте `As` предложение, чтобы указать тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="76043-113">You do not use an `As` clause to specify the return type.</span></span>  
  
     <span data-ttu-id="76043-114">[!code-vb[VbVbalrLambdas&#1;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="76043-114">[!code-vb[VbVbalrLambdas#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_1.vb)]</span></span>  
  
     <span data-ttu-id="76043-115">Лямбда-выражение вызывается путем передачи ему целочисленного аргумента.</span><span class="sxs-lookup"><span data-stu-id="76043-115">You call the lambda expression by passing in an integer argument.</span></span>  
  
     <span data-ttu-id="76043-116">[!code-vb[VbVbalrLambdas&#2;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="76043-116">[!code-vb[VbVbalrLambdas#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_2.vb)]</span></span>  
  
4.  <span data-ttu-id="76043-117">Кроме того тот же результат достигается в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="76043-117">Alternatively, the same result is accomplished by the following example:</span></span>  
  
     <span data-ttu-id="76043-118">[!code-vb[VbVbalrLambdas&#3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="76043-118">[!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_3.vb)]</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a><span data-ttu-id="76043-119">Создание подпрограммы Однострочные лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="76043-119">To create a single-line lambda expression subroutine</span></span>  
  
1.  <span data-ttu-id="76043-120">В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Sub`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="76043-120">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="76043-121">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="76043-121">`Dim add1 =`   `Sub`</span></span>  
  
2.  <span data-ttu-id="76043-122">В скобках непосредственно после `Sub`, введите параметры подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="76043-122">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="76043-123">Обратите внимание, что не задано имя после `Sub`.</span><span class="sxs-lookup"><span data-stu-id="76043-123">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="76043-124">`Dim add1 = Sub`   `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="76043-124">`Dim add1 = Sub`   `(msg As String)`</span></span>  
  
3.  <span data-ttu-id="76043-125">Вслед за списком параметров введите один оператор как тело подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="76043-125">Following the parameter list, type a single statement as the body of the subroutine.</span></span>  
  
     <span data-ttu-id="76043-126">[!code-vb[VbVbalrLambdas&17;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="76043-126">[!code-vb[VbVbalrLambdas#17](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_4.vb)]</span></span>  
  
     <span data-ttu-id="76043-127">Лямбда-выражение вызывается передачи строкового аргумента.</span><span class="sxs-lookup"><span data-stu-id="76043-127">You call the lambda expression by passing in a string argument.</span></span>  
  
     <span data-ttu-id="76043-128">[!code-vb[VbVbalrLambdas&18;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="76043-128">[!code-vb[VbVbalrLambdas#18](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_5.vb)]</span></span>  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a><span data-ttu-id="76043-129">Для создания многострочных лямбда-функцией, выражение</span><span class="sxs-lookup"><span data-stu-id="76043-129">To create a multiline lambda expression function</span></span>  
  
1.  <span data-ttu-id="76043-130">В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Function`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="76043-130">In any situation where a delegate type could be used, type the keyword `Function`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="76043-131">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="76043-131">`Dim add1 =`   `Function`</span></span>  
  
2.  <span data-ttu-id="76043-132">В скобках непосредственно после `Function`, введите параметры функции.</span><span class="sxs-lookup"><span data-stu-id="76043-132">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="76043-133">Обратите внимание, что не задано имя после `Function`.</span><span class="sxs-lookup"><span data-stu-id="76043-133">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="76043-134">`Dim add1 = Function`   `(index As Integer)`</span><span class="sxs-lookup"><span data-stu-id="76043-134">`Dim add1 = Function`   `(index As Integer)`</span></span>  
  
3.  <span data-ttu-id="76043-135">Нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="76043-135">Press ENTER.</span></span> <span data-ttu-id="76043-136">`End Function` Автоматически добавляется инструкция.</span><span class="sxs-lookup"><span data-stu-id="76043-136">The `End Function` statement is automatically added.</span></span>  
  
4.  <span data-ttu-id="76043-137">В теле функции добавьте следующий код, чтобы создать выражение и вернуть значение.</span><span class="sxs-lookup"><span data-stu-id="76043-137">Within the body of the function, add the following code to create an expression and return the value.</span></span> <span data-ttu-id="76043-138">Не используйте `As` предложение, чтобы указать тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="76043-138">You do not use an `As` clause to specify the return type.</span></span>  
  
     <span data-ttu-id="76043-139">[!code-vb[VbVbalrLambdas&19;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="76043-139">[!code-vb[VbVbalrLambdas#19](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_6.vb)]</span></span>  
  
     <span data-ttu-id="76043-140">Лямбда-выражение вызывается путем передачи ему целочисленного аргумента.</span><span class="sxs-lookup"><span data-stu-id="76043-140">You call the lambda expression by passing in an integer argument.</span></span>  
  
     <span data-ttu-id="76043-141">[!code-vb[VbVbalrLambdas&20;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="76043-141">[!code-vb[VbVbalrLambdas#20](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_7.vb)]</span></span>  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a><span data-ttu-id="76043-142">Создание выражения подпрограммы многострочных лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="76043-142">To create a multiline lambda expression subroutine</span></span>  
  
1.  <span data-ttu-id="76043-143">В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Sub`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="76043-143">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example:</span></span>  
  
     <span data-ttu-id="76043-144">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="76043-144">`Dim add1 =`   `Sub`</span></span>  
  
2.  <span data-ttu-id="76043-145">В скобках непосредственно после `Sub`, введите параметры подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="76043-145">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="76043-146">Обратите внимание, что не задано имя после `Sub`.</span><span class="sxs-lookup"><span data-stu-id="76043-146">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="76043-147">`Dim add1 = Sub`  `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="76043-147">`Dim add1 = Sub`  `(msg As String)`</span></span>  
  
3.  <span data-ttu-id="76043-148">Нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="76043-148">Press ENTER.</span></span> <span data-ttu-id="76043-149">`End Sub` Автоматически добавляется инструкция.</span><span class="sxs-lookup"><span data-stu-id="76043-149">The `End Sub` statement is automatically added.</span></span>  
  
4.  <span data-ttu-id="76043-150">В теле функции добавьте следующий код для выполнения при вызове подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="76043-150">Within the body of the function, add the following code to execute when the subroutine is invoked.</span></span>  
  
     <span data-ttu-id="76043-151">[!code-vb[VbVbalrLambdas&#21;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="76043-151">[!code-vb[VbVbalrLambdas#21](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_8.vb)]</span></span>  
  
     <span data-ttu-id="76043-152">Лямбда-выражение вызывается передачи строкового аргумента.</span><span class="sxs-lookup"><span data-stu-id="76043-152">You call the lambda expression by passing in a string argument.</span></span>  
  
     <span data-ttu-id="76043-153">[!code-vb[VbVbalrLambdas&#22;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="76043-153">[!code-vb[VbVbalrLambdas#22](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_9.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="76043-154">Пример</span><span class="sxs-lookup"><span data-stu-id="76043-154">Example</span></span>  
 <span data-ttu-id="76043-155">Обычно лямбда-выражений используется для определения функции, который можно передать в качестве аргумента для параметра, тип которого является `Delegate`.</span><span class="sxs-lookup"><span data-stu-id="76043-155">A common use of lambda expressions is to define a function that can be passed in as the argument for a parameter whose type is `Delegate`.</span></span> <span data-ttu-id="76043-156">В следующем примере <xref:System.Diagnostics.Process.GetProcesses%2A>метод возвращает массив процессов, запущенных на локальном компьютере.</xref:System.Diagnostics.Process.GetProcesses%2A></span><span class="sxs-lookup"><span data-stu-id="76043-156">In the following example, the <xref:System.Diagnostics.Process.GetProcesses%2A> method returns an array of the processes running on the local computer.</span></span> <span data-ttu-id="76043-157"><xref:System.Linq.Enumerable.Where%2A>Метод <xref:System.Linq.Enumerable>класса требуется `Boolean` делегат в качестве аргумента.</xref:System.Linq.Enumerable> </xref:System.Linq.Enumerable.Where%2A></span><span class="sxs-lookup"><span data-stu-id="76043-157">The <xref:System.Linq.Enumerable.Where%2A> method from the <xref:System.Linq.Enumerable> class requires a `Boolean` delegate as its argument.</span></span> <span data-ttu-id="76043-158">Лямбда-выражение в примере используется для этой цели.</span><span class="sxs-lookup"><span data-stu-id="76043-158">The lambda expression in the example is used for that purpose.</span></span> <span data-ttu-id="76043-159">Он возвращает `True` для каждого процесса, имеет только один поток, а те, выбранные в `filteredList`.</span><span class="sxs-lookup"><span data-stu-id="76043-159">It returns `True` for each process that has only one thread, and those are selected in `filteredList`.</span></span>  
  
 <span data-ttu-id="76043-160">[!code-vb[VbVbalrLambdas&#10;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="76043-160">[!code-vb[VbVbalrLambdas#10](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_10.vb)]</span></span>  
  
 <span data-ttu-id="76043-161">Предыдущий пример эквивалентен следующий код, который записывается в [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] синтаксис:</span><span class="sxs-lookup"><span data-stu-id="76043-161">The previous example is equivalent to the following code, which is written in [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] syntax:</span></span>  
  
 <span data-ttu-id="76043-162">[!code-vb[VbVbalrLambdas&11;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_11.vb)]</span><span class="sxs-lookup"><span data-stu-id="76043-162">[!code-vb[VbVbalrLambdas#11](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_11.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76043-163">См. также</span><span class="sxs-lookup"><span data-stu-id="76043-163">See Also</span></span>  
 <span data-ttu-id="76043-164"><xref:System.Linq.Enumerable></xref:System.Linq.Enumerable></span><span class="sxs-lookup"><span data-stu-id="76043-164"><xref:System.Linq.Enumerable></span></span>   
<span data-ttu-id="76043-165"> [Лямбда-выражения](./lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="76043-165"> [Lambda Expressions](./lambda-expressions.md) </span></span>  
<span data-ttu-id="76043-166"> [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="76043-166"> [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="76043-167"> [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="76043-167"> [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="76043-168"> [Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="76043-168"> [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="76043-169"> [Практическое руководство: передача процедур другой процедуре в Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="76043-169"> [How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) </span></span>  
<span data-ttu-id="76043-170"> [Оператор Delegate](../../../../visual-basic/language-reference/statements/delegate-statement.md) </span><span class="sxs-lookup"><span data-stu-id="76043-170"> [Delegate Statement](../../../../visual-basic/language-reference/statements/delegate-statement.md) </span></span>  
<span data-ttu-id="76043-171"> [Введение в LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span><span class="sxs-lookup"><span data-stu-id="76043-171"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
