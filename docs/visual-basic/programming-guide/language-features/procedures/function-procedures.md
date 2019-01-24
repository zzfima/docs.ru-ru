---
title: Процедуры Function (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function procedures
- return values [Visual Basic], function procedures
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], Function procedures
- syntax [Visual Basic], function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
ms.openlocfilehash: 8b67a6953e7788827ef1ec268f54bddf2f1392c3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662261"
---
# <a name="function-procedures-visual-basic"></a><span data-ttu-id="3a38e-102">Процедуры Function (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a38e-102">Function Procedures (Visual Basic)</span></span>
<span data-ttu-id="3a38e-103">Объект `Function` процедура — это последовательность операторов Visual Basic, заключенным `Function` и `End Function` инструкций.</span><span class="sxs-lookup"><span data-stu-id="3a38e-103">A `Function` procedure is a series of Visual Basic statements enclosed by the `Function` and `End Function` statements.</span></span> <span data-ttu-id="3a38e-104">`Function` Процедура выполняет задачи и возвращает управление вызывающему коду.</span><span class="sxs-lookup"><span data-stu-id="3a38e-104">The `Function` procedure performs a task and then returns control to the calling code.</span></span> <span data-ttu-id="3a38e-105">При возвращении управления также возвращает значение вызывающему коду.</span><span class="sxs-lookup"><span data-stu-id="3a38e-105">When it returns control, it also returns a value to the calling code.</span></span>  
  
 <span data-ttu-id="3a38e-106">Каждый раз при вызове процедуры, его операторы выполнения, начиная с первого выполняемого оператора после `Function` инструкции и заканчивая первым `End Function`, `Exit Function`, или `Return` обнаружен оператор.</span><span class="sxs-lookup"><span data-stu-id="3a38e-106">Each time the procedure is called, its statements run, starting with the first executable statement after the `Function` statement and ending with the first `End Function`, `Exit Function`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="3a38e-107">Вы можете определить `Function` процедуры в модуля, класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="3a38e-107">You can define a `Function` procedure in a module, class, or structure.</span></span> <span data-ttu-id="3a38e-108">Это `Public` по умолчанию, означающее, его можно вызвать из любого места в приложении, которое имеет доступ к модуля, класса или структуры, в котором она определена.</span><span class="sxs-lookup"><span data-stu-id="3a38e-108">It is `Public` by default, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span>  
  
 <span data-ttu-id="3a38e-109">Объект `Function` процедура может принимать аргументы, такие как константы, переменные или выражения, которые передаются в него в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="3a38e-109">A `Function` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="3a38e-110">Синтаксис объявления</span><span class="sxs-lookup"><span data-stu-id="3a38e-110">Declaration Syntax</span></span>  
 <span data-ttu-id="3a38e-111">Синтаксис объявления `Function` процедура выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3a38e-111">The syntax for declaring a `Function` procedure is as follows:</span></span>  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 <span data-ttu-id="3a38e-112">*Модификаторы* можно указать уровень доступа и сведения о перегрузка, переопределение, совместного использования и затенении.</span><span class="sxs-lookup"><span data-stu-id="3a38e-112">The *modifiers* can specify access level and information regarding overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="3a38e-113">Дополнительные сведения см. в разделе [инструкции Function](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3a38e-113">For more information, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="3a38e-114">Каждый параметр объявляется так же, как и для [подпрограммы](./sub-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="3a38e-114">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="3a38e-115">Тип данных</span><span class="sxs-lookup"><span data-stu-id="3a38e-115">Data Type</span></span>  
 <span data-ttu-id="3a38e-116">Каждый `Function` процедуры имеет тип данных, так же, как любой переменной.</span><span class="sxs-lookup"><span data-stu-id="3a38e-116">Every `Function` procedure has a data type, just as every variable does.</span></span> <span data-ttu-id="3a38e-117">Этот тип данных определяется `As` предложение в `Function` инструкции и определяет тип данных значения, функция возвращает в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="3a38e-117">This data type is specified by the `As` clause in the `Function` statement, and it determines the data type of the value the function returns to the calling code.</span></span> <span data-ttu-id="3a38e-118">Следующий пример демонстрирует объявление, иллюстрируют это.</span><span class="sxs-lookup"><span data-stu-id="3a38e-118">The following sample declarations illustrate this.</span></span>  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 <span data-ttu-id="3a38e-119">Дополнительные сведения см. в разделе «Компоненты» в [инструкции Function](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3a38e-119">For more information, see "Parts" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="returning-values"></a><span data-ttu-id="3a38e-120">Получение возвращаемых значений</span><span class="sxs-lookup"><span data-stu-id="3a38e-120">Returning Values</span></span>  
 <span data-ttu-id="3a38e-121">Значение `Function` процедура отправляет обратно в вызывающий код вызывается его возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="3a38e-121">The value a `Function` procedure sends back to the calling code is called its return value.</span></span> <span data-ttu-id="3a38e-122">Процедура возвращает это значение в одном из двух способов:</span><span class="sxs-lookup"><span data-stu-id="3a38e-122">The procedure returns this value in one of two ways:</span></span>  
  
-   <span data-ttu-id="3a38e-123">Она использует `Return` инструкцию, чтобы указать возвращаемое значение и возвращает управление вызывающей программе немедленно.</span><span class="sxs-lookup"><span data-stu-id="3a38e-123">It uses the `Return` statement to specify the return value, and returns control immediately to the calling program.</span></span> <span data-ttu-id="3a38e-124">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="3a38e-124">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement immediately transfers control back  
    ' to the calling code and returns the value of Expression.  
    Return Expression  
End Function  
```  
  
-   <span data-ttu-id="3a38e-125">Он присваивает значение собственное имя функции в одной или нескольких инструкций процедуры.</span><span class="sxs-lookup"><span data-stu-id="3a38e-125">It assigns a value to its own function name in one or more statements of the procedure.</span></span> <span data-ttu-id="3a38e-126">Управление не возвращается вызывающей программе до `Exit Function` или `End Function` выполняется инструкция.</span><span class="sxs-lookup"><span data-stu-id="3a38e-126">Control does not return to the calling program until an `Exit Function` or `End Function` statement is executed.</span></span> <span data-ttu-id="3a38e-127">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="3a38e-127">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement does not transfer control back to the calling code.  
    FunctionName = Expression  
    ' When control returns to the calling code, Expression is the return value.  
End Function  
```  
  
 <span data-ttu-id="3a38e-128">Присвоение имени функции возвращаемое значение удобен, управление не возвращается из процедуры, пока встретится `Exit Function` или `End Function` инструкции.</span><span class="sxs-lookup"><span data-stu-id="3a38e-128">The advantage of assigning the return value to the function name is that control does not return from the procedure until it encounters an `Exit Function` or `End Function` statement.</span></span> <span data-ttu-id="3a38e-129">Это позволяет назначить предварительное значение и изменить позже при необходимости.</span><span class="sxs-lookup"><span data-stu-id="3a38e-129">This allows you to assign a preliminary value and adjust it later if necessary.</span></span>  
  
 <span data-ttu-id="3a38e-130">Дополнительные сведения о возврате значения см. в разделе [инструкции Function](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3a38e-130">For more information about returning values, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="3a38e-131">Сведения о возврате массивов см. в разделе [массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="3a38e-131">For information about returning arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="3a38e-132">Синтаксис вызова</span><span class="sxs-lookup"><span data-stu-id="3a38e-132">Calling Syntax</span></span>  
 <span data-ttu-id="3a38e-133">Вы вызываете `Function` процедуры, включая ее имя и аргументы в правой части оператора присваивания или в выражении.</span><span class="sxs-lookup"><span data-stu-id="3a38e-133">You invoke a `Function` procedure by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span> <span data-ttu-id="3a38e-134">Необходимо указать значения для всех аргументов, которые не являются необязательными, и список аргументов необходимо заключить в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="3a38e-134">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="3a38e-135">Если не указано никаких аргументов, скобки можно опустить.</span><span class="sxs-lookup"><span data-stu-id="3a38e-135">If no arguments are supplied, you can optionally omit the parentheses.</span></span>  
  
 <span data-ttu-id="3a38e-136">Синтаксис для вызова `Function` процедура выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3a38e-136">The syntax for a call to a `Function` procedure is as follows:</span></span>  
  
 <span data-ttu-id="3a38e-137">*lvalue*`=`*functionname* `[(` *argumentlist*  `)]`</span><span class="sxs-lookup"><span data-stu-id="3a38e-137">*lvalue*  `=`  *functionname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="3a38e-138">`If ((` *FunctionName* `[(` *argumentlist* `)] / 3) <=` *выражение*  `) Then`</span><span class="sxs-lookup"><span data-stu-id="3a38e-138">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`  *expression* `) Then`</span></span>  
  
 <span data-ttu-id="3a38e-139">При вызове `Function` процедуры, не нужно использовать ее возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="3a38e-139">When you call a `Function` procedure, you do not have to use its return value.</span></span> <span data-ttu-id="3a38e-140">Если этого не сделать, выполняются все действия, функции, но возвращаемое значение игнорируется.</span><span class="sxs-lookup"><span data-stu-id="3a38e-140">If you do not, all the actions of the function are performed, but the return value is ignored.</span></span> <span data-ttu-id="3a38e-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> часто называется таким образом.</span><span class="sxs-lookup"><span data-stu-id="3a38e-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> is often called in this manner.</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="3a38e-142">Пример объявления и вызова</span><span class="sxs-lookup"><span data-stu-id="3a38e-142">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="3a38e-143">Следующие `Function` процедура вычисляет самая длинная сторона гипотенузы прямоугольного треугольника, значения для двух других сторон.</span><span class="sxs-lookup"><span data-stu-id="3a38e-143">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
 [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/function-procedures_1.vb)]  
  
 <span data-ttu-id="3a38e-144">В следующем примере показано типичный вызов `hypotenuse`.</span><span class="sxs-lookup"><span data-stu-id="3a38e-144">The following example shows a typical call to `hypotenuse`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/function-procedures_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3a38e-145">См. также</span><span class="sxs-lookup"><span data-stu-id="3a38e-145">See also</span></span>
- [<span data-ttu-id="3a38e-146">Процедуры</span><span class="sxs-lookup"><span data-stu-id="3a38e-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="3a38e-147">Подпрограммы</span><span class="sxs-lookup"><span data-stu-id="3a38e-147">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="3a38e-148">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="3a38e-148">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="3a38e-149">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="3a38e-149">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="3a38e-150">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="3a38e-150">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="3a38e-151">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="3a38e-151">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="3a38e-152">Практическое руководство. Создание процедуры, возвращающей значение</span><span class="sxs-lookup"><span data-stu-id="3a38e-152">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="3a38e-153">Практическое руководство. Возвращение значения из процедуры</span><span class="sxs-lookup"><span data-stu-id="3a38e-153">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="3a38e-154">Практическое руководство. Вызов процедуры, возвращающей значение</span><span class="sxs-lookup"><span data-stu-id="3a38e-154">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
