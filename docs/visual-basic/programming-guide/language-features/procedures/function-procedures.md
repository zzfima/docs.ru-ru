---
title: Процедуры функций
ms.date: 07/20/2015
helpviewer_keywords:
- Function procedures
- return values [Visual Basic], function procedures
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], Function procedures
- syntax [Visual Basic], function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
ms.openlocfilehash: b62a730e8ade211821826afbb55fa8858ea311a3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74341091"
---
# <a name="function-procedures-visual-basic"></a><span data-ttu-id="62d01-102">Процедуры Function (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62d01-102">Function Procedures (Visual Basic)</span></span>
<span data-ttu-id="62d01-103">`Function` процедура — это последовательность Visual Basic инструкций, заключенных в операторы `Function` и `End Function`.</span><span class="sxs-lookup"><span data-stu-id="62d01-103">A `Function` procedure is a series of Visual Basic statements enclosed by the `Function` and `End Function` statements.</span></span> <span data-ttu-id="62d01-104">`Function` процедура выполняет задачу, а затем возвращает управление вызывающему коду.</span><span class="sxs-lookup"><span data-stu-id="62d01-104">The `Function` procedure performs a task and then returns control to the calling code.</span></span> <span data-ttu-id="62d01-105">Когда он возвращает управление, он также возвращает значение в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="62d01-105">When it returns control, it also returns a value to the calling code.</span></span>  
  
 <span data-ttu-id="62d01-106">При каждом вызове процедуры ее инструкции выполняются, начиная с первого исполняемого оператора после оператора `Function` и заканчивая первой инструкцией `End Function`, `Exit Function`или `Return`.</span><span class="sxs-lookup"><span data-stu-id="62d01-106">Each time the procedure is called, its statements run, starting with the first executable statement after the `Function` statement and ending with the first `End Function`, `Exit Function`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="62d01-107">Процедуру `Function` можно определить в модуле, классе или структуре.</span><span class="sxs-lookup"><span data-stu-id="62d01-107">You can define a `Function` procedure in a module, class, or structure.</span></span> <span data-ttu-id="62d01-108">Он `Public` по умолчанию, что означает, что его можно вызывать из любого места в приложении, которое имеет доступ к модулю, классу или структуре, в которой он определен.</span><span class="sxs-lookup"><span data-stu-id="62d01-108">It is `Public` by default, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span>  
  
 <span data-ttu-id="62d01-109">`Function` процедура может принимать аргументы, такие как константы, переменные или выражения, которые передаются в него вызывающим кодом.</span><span class="sxs-lookup"><span data-stu-id="62d01-109">A `Function` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="62d01-110">Синтаксис объявления</span><span class="sxs-lookup"><span data-stu-id="62d01-110">Declaration Syntax</span></span>  
 <span data-ttu-id="62d01-111">Синтаксис для объявления `Function` процедуры выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="62d01-111">The syntax for declaring a `Function` procedure is as follows:</span></span>  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 <span data-ttu-id="62d01-112">*Модификаторы* могут указывать уровень доступа и сведения о перегрузке, переопределении, совместном использовании и затенении.</span><span class="sxs-lookup"><span data-stu-id="62d01-112">The *modifiers* can specify access level and information regarding overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="62d01-113">Дополнительные сведения см. в разделе [оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="62d01-113">For more information, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="62d01-114">Каждый параметр объявляется так же, как и для [процедур подраздела](./sub-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="62d01-114">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="62d01-115">Тип данных</span><span class="sxs-lookup"><span data-stu-id="62d01-115">Data Type</span></span>  
 <span data-ttu-id="62d01-116">Каждая `Function` процедура имеет тип данных, точно так же, как и каждая переменная.</span><span class="sxs-lookup"><span data-stu-id="62d01-116">Every `Function` procedure has a data type, just as every variable does.</span></span> <span data-ttu-id="62d01-117">Этот тип данных указывается предложением `As` в инструкции `Function` и определяет тип данных значения, возвращаемого функцией в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="62d01-117">This data type is specified by the `As` clause in the `Function` statement, and it determines the data type of the value the function returns to the calling code.</span></span> <span data-ttu-id="62d01-118">Это показано в приведенных ниже примерах объявлений.</span><span class="sxs-lookup"><span data-stu-id="62d01-118">The following sample declarations illustrate this.</span></span>  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 <span data-ttu-id="62d01-119">Дополнительные сведения см. в разделе "части" в [операторе Function](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="62d01-119">For more information, see "Parts" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="returning-values"></a><span data-ttu-id="62d01-120">Возвращаемые значения</span><span class="sxs-lookup"><span data-stu-id="62d01-120">Returning Values</span></span>  
 <span data-ttu-id="62d01-121">Значение, `Function` процедура, отправляется обратно вызывающему коду, называется возвращаемым значением.</span><span class="sxs-lookup"><span data-stu-id="62d01-121">The value a `Function` procedure sends back to the calling code is called its return value.</span></span> <span data-ttu-id="62d01-122">Процедура возвращает это значение одним из двух способов:</span><span class="sxs-lookup"><span data-stu-id="62d01-122">The procedure returns this value in one of two ways:</span></span>  
  
- <span data-ttu-id="62d01-123">Он использует оператор `Return` для указания возвращаемого значения и немедленно возвращает управление вызывающей программе.</span><span class="sxs-lookup"><span data-stu-id="62d01-123">It uses the `Return` statement to specify the return value, and returns control immediately to the calling program.</span></span> <span data-ttu-id="62d01-124">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="62d01-124">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement immediately transfers control back  
    ' to the calling code and returns the value of Expression.  
    Return Expression  
End Function  
```  
  
- <span data-ttu-id="62d01-125">Он присваивает значение имени своей функции в одной или нескольких инструкциях процедуры.</span><span class="sxs-lookup"><span data-stu-id="62d01-125">It assigns a value to its own function name in one or more statements of the procedure.</span></span> <span data-ttu-id="62d01-126">Управление не возвращается вызывающей программе до тех пор, пока не будет выполнен оператор `Exit Function` или `End Function`.</span><span class="sxs-lookup"><span data-stu-id="62d01-126">Control does not return to the calling program until an `Exit Function` or `End Function` statement is executed.</span></span> <span data-ttu-id="62d01-127">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="62d01-127">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement does not transfer control back to the calling code.  
    FunctionName = Expression  
    ' When control returns to the calling code, Expression is the return value.  
End Function  
```  
  
 <span data-ttu-id="62d01-128">Преимуществом присвоения возвращаемого значения имени функции является то, что Управление не возвращается из процедуры до тех пор, пока не встретится оператор `Exit Function` или `End Function`.</span><span class="sxs-lookup"><span data-stu-id="62d01-128">The advantage of assigning the return value to the function name is that control does not return from the procedure until it encounters an `Exit Function` or `End Function` statement.</span></span> <span data-ttu-id="62d01-129">Это позволяет назначить предварительное значение и позже при необходимости изменить его.</span><span class="sxs-lookup"><span data-stu-id="62d01-129">This allows you to assign a preliminary value and adjust it later if necessary.</span></span>  
  
 <span data-ttu-id="62d01-130">Дополнительные сведения о возвращаемых значениях см. в разделе [оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="62d01-130">For more information about returning values, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="62d01-131">Дополнительные сведения о возврате массивов см. в разделе [массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="62d01-131">For information about returning arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="62d01-132">Синтаксис вызова</span><span class="sxs-lookup"><span data-stu-id="62d01-132">Calling Syntax</span></span>  
 <span data-ttu-id="62d01-133">Процедура `Function` вызывается путем включения ее имени и аргументов в правой части оператора присваивания или в выражении.</span><span class="sxs-lookup"><span data-stu-id="62d01-133">You invoke a `Function` procedure by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span> <span data-ttu-id="62d01-134">Необходимо указать значения для всех аргументов, которые не являются необязательными, и необходимо заключить список аргументов в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="62d01-134">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="62d01-135">Если аргументы не указаны, можно дополнительно опустить круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="62d01-135">If no arguments are supplied, you can optionally omit the parentheses.</span></span>  
  
 <span data-ttu-id="62d01-136">Синтаксис вызова `Function` процедуры выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="62d01-136">The syntax for a call to a `Function` procedure is as follows:</span></span>  
  
 <span data-ttu-id="62d01-137">*lvalue*`=`*functionname* `[(` *ArgumentList* `)]`</span><span class="sxs-lookup"><span data-stu-id="62d01-137">*lvalue*  `=`  *functionname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="62d01-138">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`*Expression* `) Then`</span><span class="sxs-lookup"><span data-stu-id="62d01-138">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`  *expression* `) Then`</span></span>  
  
 <span data-ttu-id="62d01-139">При вызове `Function` процедуры не нужно использовать ее возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="62d01-139">When you call a `Function` procedure, you do not have to use its return value.</span></span> <span data-ttu-id="62d01-140">В противном случае выполняются все действия функции, но возвращаемое значение игнорируется.</span><span class="sxs-lookup"><span data-stu-id="62d01-140">If you do not, all the actions of the function are performed, but the return value is ignored.</span></span> <span data-ttu-id="62d01-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> часто вызывается таким образом.</span><span class="sxs-lookup"><span data-stu-id="62d01-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> is often called in this manner.</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="62d01-142">Иллюстрация объявления и вызова</span><span class="sxs-lookup"><span data-stu-id="62d01-142">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="62d01-143">Следующая `Function` процедура вычисляет самую длинную сторону (гипотенузу) правого треугольника, учитывая значения двух других сторон.</span><span class="sxs-lookup"><span data-stu-id="62d01-143">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
 <span data-ttu-id="62d01-144">В следующем примере показан типичный вызов `hypotenuse`.</span><span class="sxs-lookup"><span data-stu-id="62d01-144">The following example shows a typical call to `hypotenuse`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="62d01-145">См. также</span><span class="sxs-lookup"><span data-stu-id="62d01-145">See also</span></span>

- [<span data-ttu-id="62d01-146">Процедуры</span><span class="sxs-lookup"><span data-stu-id="62d01-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="62d01-147">Подпрограммы</span><span class="sxs-lookup"><span data-stu-id="62d01-147">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="62d01-148">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="62d01-148">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="62d01-149">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="62d01-149">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="62d01-150">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="62d01-150">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="62d01-151">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="62d01-151">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="62d01-152">Практическое руководство. Создание процедуры, возвращающей значение</span><span class="sxs-lookup"><span data-stu-id="62d01-152">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="62d01-153">Практическое руководство. Возврат значения из процедуры</span><span class="sxs-lookup"><span data-stu-id="62d01-153">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="62d01-154">Практическое руководство. Вызов процедуры, возвращающей значение</span><span class="sxs-lookup"><span data-stu-id="62d01-154">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
