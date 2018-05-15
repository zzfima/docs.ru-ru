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
ms.openlocfilehash: 887c930cb757b012542c97d64a57a62882a2eed3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="function-procedures-visual-basic"></a><span data-ttu-id="bbe89-102">Процедуры Function (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bbe89-102">Function Procedures (Visual Basic)</span></span>
<span data-ttu-id="bbe89-103">Объект `Function` процедура — это последовательность операторов Visual Basic, заключенным в `Function` и `End Function` инструкции.</span><span class="sxs-lookup"><span data-stu-id="bbe89-103">A `Function` procedure is a series of Visual Basic statements enclosed by the `Function` and `End Function` statements.</span></span> <span data-ttu-id="bbe89-104">`Function` Процедура выполняет задачу и возвращает управление вызывающему коду.</span><span class="sxs-lookup"><span data-stu-id="bbe89-104">The `Function` procedure performs a task and then returns control to the calling code.</span></span> <span data-ttu-id="bbe89-105">При возвращении элемента управления также возвращает значение вызывающему коду.</span><span class="sxs-lookup"><span data-stu-id="bbe89-105">When it returns control, it also returns a value to the calling code.</span></span>  
  
 <span data-ttu-id="bbe89-106">При каждом вызове процедуры ее инструкции выполняются, начиная с первого исполняемого оператора после `Function` инструкции и заканчивая первым `End Function`, `Exit Function`, или `Return` обнаружен оператор.</span><span class="sxs-lookup"><span data-stu-id="bbe89-106">Each time the procedure is called, its statements run, starting with the first executable statement after the `Function` statement and ending with the first `End Function`, `Exit Function`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="bbe89-107">Можно определить `Function` процедуру в модуля, класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="bbe89-107">You can define a `Function` procedure in a module, class, or structure.</span></span> <span data-ttu-id="bbe89-108">Это `Public` по умолчанию, означающее, который можно вызвать из любого места в приложении, которое имеет доступ к модуля, класса или структуры, в котором она определена.</span><span class="sxs-lookup"><span data-stu-id="bbe89-108">It is `Public` by default, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span>  
  
 <span data-ttu-id="bbe89-109">Объект `Function` процедура может принимать аргументы, например константы, переменные или выражения, которые передаются вызывающим кодом.</span><span class="sxs-lookup"><span data-stu-id="bbe89-109">A `Function` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="bbe89-110">Синтаксис объявления</span><span class="sxs-lookup"><span data-stu-id="bbe89-110">Declaration Syntax</span></span>  
 <span data-ttu-id="bbe89-111">Синтаксис объявления `Function` процедура является следующим образом:</span><span class="sxs-lookup"><span data-stu-id="bbe89-111">The syntax for declaring a `Function` procedure is as follows:</span></span>  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 <span data-ttu-id="bbe89-112">*Модификаторы* можно указать уровень доступа и сведения о перегрузке, переопределении, общем доступе и затенение.</span><span class="sxs-lookup"><span data-stu-id="bbe89-112">The *modifiers* can specify access level and information regarding overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="bbe89-113">Дополнительные сведения см. в разделе [Function, инструкция](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="bbe89-113">For more information, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="bbe89-114">Каждый параметр объявляется так же, как для [Sub-процедуры](./sub-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="bbe89-114">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="bbe89-115">Тип данных</span><span class="sxs-lookup"><span data-stu-id="bbe89-115">Data Type</span></span>  
 <span data-ttu-id="bbe89-116">Каждый `Function` процедуры имеет тип данных, просто любой переменной.</span><span class="sxs-lookup"><span data-stu-id="bbe89-116">Every `Function` procedure has a data type, just as every variable does.</span></span> <span data-ttu-id="bbe89-117">Этот тип данных определяется `As` предложения в `Function` оператор, который определяет тип данных значения, функция возвращает в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="bbe89-117">This data type is specified by the `As` clause in the `Function` statement, and it determines the data type of the value the function returns to the calling code.</span></span> <span data-ttu-id="bbe89-118">Следующий пример демонстрирует объявление проиллюстрировать это.</span><span class="sxs-lookup"><span data-stu-id="bbe89-118">The following sample declarations illustrate this.</span></span>  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 <span data-ttu-id="bbe89-119">Дополнительные сведения см. в разделе «Компоненты» в [Function, инструкция](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="bbe89-119">For more information, see "Parts" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="returning-values"></a><span data-ttu-id="bbe89-120">Получение возвращаемых значений</span><span class="sxs-lookup"><span data-stu-id="bbe89-120">Returning Values</span></span>  
 <span data-ttu-id="bbe89-121">Значение `Function` процедура отправляет обратно в вызывающий код вызывается возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="bbe89-121">The value a `Function` procedure sends back to the calling code is called its return value.</span></span> <span data-ttu-id="bbe89-122">Процедура возвращает это значение в одном из двух способов:</span><span class="sxs-lookup"><span data-stu-id="bbe89-122">The procedure returns this value in one of two ways:</span></span>  
  
-   <span data-ttu-id="bbe89-123">Она использует `Return` инструкцию, чтобы задать возвращаемое значение и возвращает управление немедленно вызываемой программе.</span><span class="sxs-lookup"><span data-stu-id="bbe89-123">It uses the `Return` statement to specify the return value, and returns control immediately to the calling program.</span></span> <span data-ttu-id="bbe89-124">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="bbe89-124">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement immediately transfers control back  
    ' to the calling code and returns the value of Expression.  
    Return Expression  
End Function  
```  
  
-   <span data-ttu-id="bbe89-125">Значение присваивается собственному имени функции в одной или нескольких инструкций процедуры.</span><span class="sxs-lookup"><span data-stu-id="bbe89-125">It assigns a value to its own function name in one or more statements of the procedure.</span></span> <span data-ttu-id="bbe89-126">Управление не возвращается вызывающей программе до `Exit Function` или `End Function` выполняется инструкция.</span><span class="sxs-lookup"><span data-stu-id="bbe89-126">Control does not return to the calling program until an `Exit Function` or `End Function` statement is executed.</span></span> <span data-ttu-id="bbe89-127">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="bbe89-127">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement does not transfer control back to the calling code.  
    FunctionName = Expression  
    ' When control returns to the calling code, Expression is the return value.  
End Function  
```  
  
 <span data-ttu-id="bbe89-128">Преимуществом присвоение имени функции возвращаемое значение является, управление не возвращается из процедуры, пока встретится `Exit Function` или `End Function` инструкции.</span><span class="sxs-lookup"><span data-stu-id="bbe89-128">The advantage of assigning the return value to the function name is that control does not return from the procedure until it encounters an `Exit Function` or `End Function` statement.</span></span> <span data-ttu-id="bbe89-129">Это позволяет определить предварительное значение и изменять его впоследствии при необходимости.</span><span class="sxs-lookup"><span data-stu-id="bbe89-129">This allows you to assign a preliminary value and adjust it later if necessary.</span></span>  
  
 <span data-ttu-id="bbe89-130">Дополнительные сведения о возврате значения см. в разделе [Function, инструкция](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="bbe89-130">For more information about returning values, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="bbe89-131">Сведения о возврате массивов см. в разделе [массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="bbe89-131">For information about returning arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="bbe89-132">Синтаксис вызова</span><span class="sxs-lookup"><span data-stu-id="bbe89-132">Calling Syntax</span></span>  
 <span data-ttu-id="bbe89-133">Вызвать `Function` процедуры, включая ее имя и аргументы справа от оператора присваивания или в составе выражения.</span><span class="sxs-lookup"><span data-stu-id="bbe89-133">You invoke a `Function` procedure by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span> <span data-ttu-id="bbe89-134">Необходимо указать значения для всех аргументов, которые не являются необязательными, и список аргумент должен быть заключен в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="bbe89-134">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="bbe89-135">Если не указано никаких аргументов, скобки можно опустить.</span><span class="sxs-lookup"><span data-stu-id="bbe89-135">If no arguments are supplied, you can optionally omit the parentheses.</span></span>  
  
 <span data-ttu-id="bbe89-136">Синтаксис для вызова `Function` процедура является следующим образом:</span><span class="sxs-lookup"><span data-stu-id="bbe89-136">The syntax for a call to a `Function` procedure is as follows:</span></span>  
  
 <span data-ttu-id="bbe89-137">*lvalue*`=`*functionname* `[(` *argumentlist*  `)]`</span><span class="sxs-lookup"><span data-stu-id="bbe89-137">*lvalue*  `=`  *functionname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="bbe89-138">`If ((` *FunctionName* `[(` *argumentlist* `)] / 3) <=` *выражение*  `) Then`</span><span class="sxs-lookup"><span data-stu-id="bbe89-138">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`  *expression* `) Then`</span></span>  
  
 <span data-ttu-id="bbe89-139">При вызове `Function` процедуры, не нужно использовать ее возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="bbe89-139">When you call a `Function` procedure, you do not have to use its return value.</span></span> <span data-ttu-id="bbe89-140">Если этого не сделать, выполняются все действия функции, но возвращаемое значение игнорируется.</span><span class="sxs-lookup"><span data-stu-id="bbe89-140">If you do not, all the actions of the function are performed, but the return value is ignored.</span></span> <span data-ttu-id="bbe89-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> часто называют таким образом.</span><span class="sxs-lookup"><span data-stu-id="bbe89-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> is often called in this manner.</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="bbe89-142">Пример объявления и вызова</span><span class="sxs-lookup"><span data-stu-id="bbe89-142">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="bbe89-143">Следующие `Function` процедуры рассчитывается длинной стороны, гипотенуза прямоугольного треугольника, заданы значения для двух других сторон.</span><span class="sxs-lookup"><span data-stu-id="bbe89-143">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
 [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/function-procedures_1.vb)]  
  
 <span data-ttu-id="bbe89-144">В примере показан типичный вызов `hypotenuse`.</span><span class="sxs-lookup"><span data-stu-id="bbe89-144">The following example shows a typical call to `hypotenuse`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/function-procedures_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="bbe89-145">См. также</span><span class="sxs-lookup"><span data-stu-id="bbe89-145">See Also</span></span>  
 [<span data-ttu-id="bbe89-146">Процедуры</span><span class="sxs-lookup"><span data-stu-id="bbe89-146">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="bbe89-147">Подпрограммы</span><span class="sxs-lookup"><span data-stu-id="bbe89-147">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="bbe89-148">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="bbe89-148">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="bbe89-149">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="bbe89-149">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="bbe89-150">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="bbe89-150">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="bbe89-151">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="bbe89-151">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="bbe89-152">Практическое руководство. Создание процедуры, возвращающей значение</span><span class="sxs-lookup"><span data-stu-id="bbe89-152">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)  
 [<span data-ttu-id="bbe89-153">Практическое руководство. Возврат значения из процедуры</span><span class="sxs-lookup"><span data-stu-id="bbe89-153">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)  
 [<span data-ttu-id="bbe89-154">Практическое руководство. Вызов процедуры, возвращающей значение</span><span class="sxs-lookup"><span data-stu-id="bbe89-154">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
