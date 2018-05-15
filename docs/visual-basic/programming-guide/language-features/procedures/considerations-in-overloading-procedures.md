---
title: Вопросы, связанные с перегрузкой процедур (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- signatures [Visual Basic], ParamArray arguments
- ParamArray keyword [Visual Basic], parameter arrays
- ParamArray keyword [Visual Basic], arguments and signatures
- function overloading [Visual Basic], implicit overloads for ParamArray
- ParamArray keyword [Visual Basic], signatures
- Visual Basic code, procedures
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], overloading
- parameters [Visual Basic], lists
- function overloading [Visual Basic], typeless programming
- typeless programming
- function overloading [Visual Basic], restrictions
- arguments [Visual Basic], optional
- optional arguments [Visual Basic], overloading
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- parameter arrays [Visual Basic], overloading arguments
- Visual Basic code, parameter lists
- procedure overloading [Visual Basic], considerations
- Option Explicit statement [Visual Basic]
- restrictions [Visual Basic], overloading procedures
- procedures [Visual Basic], parameter lists
ms.assetid: a2001248-10d0-42c5-b0ce-eeedc987319f
ms.openlocfilehash: e1768d0ac03cb6730c4337d7476ae163e75adfd3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a><span data-ttu-id="94a16-102">Вопросы, связанные с перегрузкой процедур (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="94a16-102">Considerations in Overloading Procedures (Visual Basic)</span></span>
<span data-ttu-id="94a16-103">При перегрузке процедур необходимо использовать другой *подписи* для каждой из перегруженных версий.</span><span class="sxs-lookup"><span data-stu-id="94a16-103">When you overload a procedure, you must use a different *signature* for each overloaded version.</span></span> <span data-ttu-id="94a16-104">Обычно это означает, что каждой версии необходимо указать другим списком параметров.</span><span class="sxs-lookup"><span data-stu-id="94a16-104">This usually means each version must specify a different parameter list.</span></span> <span data-ttu-id="94a16-105">Дополнительные сведения см. в разделе «Сигнатура» в [перегрузка процедур](./procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="94a16-105">For more information, see "Different Signature" in [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
 <span data-ttu-id="94a16-106">Можно перегрузить `Function` процедуру с `Sub` процедура и наоборот, если они имеют разные сигнатуры.</span><span class="sxs-lookup"><span data-stu-id="94a16-106">You can overload a `Function` procedure with a `Sub` procedure, and vice versa, provided they have different signatures.</span></span> <span data-ttu-id="94a16-107">Две перегрузки не отличаются только тем, что одна имеет возвращаемое значение, а другой — нет.</span><span class="sxs-lookup"><span data-stu-id="94a16-107">Two overloads cannot differ only in that one has a return value and the other does not.</span></span>  
  
 <span data-ttu-id="94a16-108">Свойство можно перегрузить перегрузка процедуры, так же, как и с тем же ограничениям.</span><span class="sxs-lookup"><span data-stu-id="94a16-108">You can overload a property the same way you overload a procedure, and with the same restrictions.</span></span> <span data-ttu-id="94a16-109">Однако нельзя перегрузить процедуру со свойством, или наоборот.</span><span class="sxs-lookup"><span data-stu-id="94a16-109">However, you cannot overload a procedure with a property, or vice versa.</span></span>  
  
## <a name="alternatives-to-overloaded-versions"></a><span data-ttu-id="94a16-110">Альтернативы перегруженных версий</span><span class="sxs-lookup"><span data-stu-id="94a16-110">Alternatives to Overloaded Versions</span></span>  
 <span data-ttu-id="94a16-111">Иногда имеют альтернативы перегруженных версий, особенно в том случае, если наличие аргументов является необязательным или их количество может меняться.</span><span class="sxs-lookup"><span data-stu-id="94a16-111">You sometimes have alternatives to overloaded versions, particularly when the presence of arguments is optional or their number is variable.</span></span>  
  
 <span data-ttu-id="94a16-112">Имейте в виду, что необязательные аргументы могут не поддерживаться все языки, а массивы параметров ограничены Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="94a16-112">Keep in mind that optional arguments are not necessarily supported by all languages, and parameter arrays are limited to Visual Basic.</span></span> <span data-ttu-id="94a16-113">При создании процедуры, который должен вызываться из кода, написанного на любом из нескольких различных языков, перегруженные версии предоставляют наибольшую гибкость.</span><span class="sxs-lookup"><span data-stu-id="94a16-113">If you are writing a procedure that is likely to be called from code written in any of several different languages, overloaded versions offer the greatest flexibility.</span></span>  
  
### <a name="overloads-and-optional-arguments"></a><span data-ttu-id="94a16-114">Перегрузки и необязательные аргументы</span><span class="sxs-lookup"><span data-stu-id="94a16-114">Overloads and Optional Arguments</span></span>  
 <span data-ttu-id="94a16-115">Если вызывающий код при необходимости можно указать или пропустить один или несколько аргументов, можно определить несколько перегруженных версий или использовать дополнительные параметры.</span><span class="sxs-lookup"><span data-stu-id="94a16-115">When the calling code can optionally supply or omit one or more arguments, you can define multiple overloaded versions or use optional parameters.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="94a16-116">Когда следует использовать перегруженные версии</span><span class="sxs-lookup"><span data-stu-id="94a16-116">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="94a16-117">Можно определить набор перегруженных версий в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="94a16-117">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
-   <span data-ttu-id="94a16-118">Логика в коде процедуры существенно отличается в зависимости от того, является ли вызывающий код предоставляет необязательный аргумент или нет.</span><span class="sxs-lookup"><span data-stu-id="94a16-118">The logic in the procedure code is significantly different depending on whether the calling code supplies an optional argument or not.</span></span>  
  
-   <span data-ttu-id="94a16-119">Код процедуры нельзя надежно проверить, является ли вызывающий код указанный необязательный аргумент.</span><span class="sxs-lookup"><span data-stu-id="94a16-119">The procedure code cannot reliably test whether the calling code has supplied an optional argument.</span></span> <span data-ttu-id="94a16-120">Это так, например, если нет ни одного кандидата для значение по умолчанию, которое вызывающий код не может предоставить.</span><span class="sxs-lookup"><span data-stu-id="94a16-120">This is the case, for example, if there is no possible candidate for a default value that the calling code could not be expected to supply.</span></span>  
  
#### <a name="when-to-use-optional-parameters"></a><span data-ttu-id="94a16-121">Когда следует использовать необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="94a16-121">When to Use Optional Parameters</span></span>  
 <span data-ttu-id="94a16-122">Можно использовать один или несколько необязательных параметрах в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="94a16-122">You might prefer one or more optional parameters in the following cases:</span></span>  
  
-   <span data-ttu-id="94a16-123">Установите для параметра значение по умолчанию является только требуемые действия, когда вызывающий код не предоставляет необязательный аргумент.</span><span class="sxs-lookup"><span data-stu-id="94a16-123">The only required action when the calling code does not supply an optional argument is to set the parameter to a default value.</span></span> <span data-ttu-id="94a16-124">В этом случае код процедуры может быть проще, если определить одну версию с одним или несколькими `Optional` параметров.</span><span class="sxs-lookup"><span data-stu-id="94a16-124">In such a case, the procedure code can be less complicated if you define a single version with one or more `Optional` parameters.</span></span>  
  
 <span data-ttu-id="94a16-125">Дополнительные сведения см. в разделе [необязательные параметры](./optional-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="94a16-125">For more information, see [Optional Parameters](./optional-parameters.md).</span></span>  
  
### <a name="overloads-and-paramarrays"></a><span data-ttu-id="94a16-126">Перегрузки и массивы параметров</span><span class="sxs-lookup"><span data-stu-id="94a16-126">Overloads and ParamArrays</span></span>  
 <span data-ttu-id="94a16-127">Если вызывающий код может передавать переменное число аргументов, можно определить несколько перегруженных версий или использовать массив параметров.</span><span class="sxs-lookup"><span data-stu-id="94a16-127">When the calling code can pass a variable number of arguments, you can define multiple overloaded versions or use a parameter array.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="94a16-128">Когда следует использовать перегруженные версии</span><span class="sxs-lookup"><span data-stu-id="94a16-128">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="94a16-129">Можно определить набор перегруженных версий в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="94a16-129">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
-   <span data-ttu-id="94a16-130">Вы знаете, что вызывающий код никогда не передается больше чем небольшое количество значений в массиве параметров.</span><span class="sxs-lookup"><span data-stu-id="94a16-130">You know that the calling code never passes more than a small number of values to the parameter array.</span></span>  
  
-   <span data-ttu-id="94a16-131">Логика в коде процедуры существенно отличается в зависимости от того, сколько значений, которые передает вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="94a16-131">The logic in the procedure code is significantly different depending on how many values the calling code passes.</span></span>  
  
-   <span data-ttu-id="94a16-132">Вызывающий код может передавать значения различных типов данных.</span><span class="sxs-lookup"><span data-stu-id="94a16-132">The calling code can pass values of different data types.</span></span>  
  
#### <a name="when-to-use-a-parameter-array"></a><span data-ttu-id="94a16-133">Когда следует использовать массив параметров</span><span class="sxs-lookup"><span data-stu-id="94a16-133">When to Use a Parameter Array</span></span>  
 <span data-ttu-id="94a16-134">Вам удобнее работать с `ParamArray` параметр в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="94a16-134">You are better served by a `ParamArray` parameter in the following cases:</span></span>  
  
-   <span data-ttu-id="94a16-135">Невозможно спрогнозировать количество значений, вызывающий код может передать массив параметров, и это может быть большое число.</span><span class="sxs-lookup"><span data-stu-id="94a16-135">You are not able to predict how many values the calling code can pass to the parameter array, and it could be a large number.</span></span>  
  
-   <span data-ttu-id="94a16-136">Логика процедуры пригоден для прохода по всем значениям, вызывающий код передает выполнение по сути одинаковые операции над каждым значением.</span><span class="sxs-lookup"><span data-stu-id="94a16-136">The procedure logic lends itself to iterating through all the values the calling code passes, performing essentially the same operations on every value.</span></span>  
  
 <span data-ttu-id="94a16-137">Дополнительные сведения см. в разделе [массивы параметров](./parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="94a16-137">For more information, see [Parameter Arrays](./parameter-arrays.md).</span></span>  
  
## <a name="implicit-overloads-for-optional-parameters"></a><span data-ttu-id="94a16-138">Неявные перегрузки для дополнительных параметров</span><span class="sxs-lookup"><span data-stu-id="94a16-138">Implicit Overloads for Optional Parameters</span></span>  
 <span data-ttu-id="94a16-139">Процедуры с [необязательно](../../../../visual-basic/language-reference/modifiers/optional.md) параметр эквивалентен двум перегруженным процедурам, с необязательным параметром, а другая — нет.</span><span class="sxs-lookup"><span data-stu-id="94a16-139">A procedure with an [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameter is equivalent to two overloaded procedures, one with the optional parameter and one without it.</span></span> <span data-ttu-id="94a16-140">Невозможно перегрузить такую процедуру со списком параметров, соответствующим любому из них.</span><span class="sxs-lookup"><span data-stu-id="94a16-140">You cannot overload such a procedure with a parameter list corresponding to either of these.</span></span> <span data-ttu-id="94a16-141">Это показано в следующих объявлениях.</span><span class="sxs-lookup"><span data-stu-id="94a16-141">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#58](./codesnippet/VisualBasic/considerations-in-overloading-procedures_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/considerations-in-overloading-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/considerations-in-overloading-procedures_3.vb)]  
  
 <span data-ttu-id="94a16-142">Для процедуры с более чем один необязательный параметр имеется набор неявных перегрузок, получающихся по той же схеме, в приведенном выше примере.</span><span class="sxs-lookup"><span data-stu-id="94a16-142">For a procedure with more than one optional parameter, there is a set of implicit overloads, arrived at by logic similar to that in the preceding example.</span></span>  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a><span data-ttu-id="94a16-143">Неявные перегрузки параметру ParamArray.</span><span class="sxs-lookup"><span data-stu-id="94a16-143">Implicit Overloads for a ParamArray Parameter</span></span>  
 <span data-ttu-id="94a16-144">Компилятор считает, что процедура с [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) параметру принимать бесконечное число перегрузок, отличающихся друг от друга в том, что вызывающий код передает массив параметров, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="94a16-144">The compiler considers a procedure with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter to have an infinite number of overloads, differing from each other in what the calling code passes to the parameter array, as follows:</span></span>  
  
-   <span data-ttu-id="94a16-145">Одна перегрузка, когда вызывающий код не передает аргумент `ParamArray`</span><span class="sxs-lookup"><span data-stu-id="94a16-145">One overload for when the calling code does not supply an argument to the `ParamArray`</span></span>  
  
-   <span data-ttu-id="94a16-146">Одна перегрузка, когда вызывающий код предоставляет одномерный массив `ParamArray` тип элемента</span><span class="sxs-lookup"><span data-stu-id="94a16-146">One overload for when the calling code supplies a one-dimensional array of the `ParamArray` element type</span></span>  
  
-   <span data-ttu-id="94a16-147">Одна перегрузка для каждого положительного целого числа, когда вызывающий код предоставляет количество аргументов, каждый из `ParamArray` тип элемента</span><span class="sxs-lookup"><span data-stu-id="94a16-147">For every positive integer, one overload for when the calling code supplies that number of arguments, each of the `ParamArray` element type</span></span>  
  
 <span data-ttu-id="94a16-148">Эти неявные перегрузки показывают следующие объявления.</span><span class="sxs-lookup"><span data-stu-id="94a16-148">The following declarations illustrate these implicit overloads.</span></span>  
  
 [!code-vb[VbVbcnProcedures#68](./codesnippet/VisualBasic/considerations-in-overloading-procedures_4.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/considerations-in-overloading-procedures_5.vb)]  
  
 <span data-ttu-id="94a16-149">Нельзя перегрузить процедуру со списком параметров, который принимает одномерный массив для массива параметров.</span><span class="sxs-lookup"><span data-stu-id="94a16-149">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="94a16-150">Тем не менее можно использовать подписи неявных перегрузок.</span><span class="sxs-lookup"><span data-stu-id="94a16-150">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="94a16-151">Это показано в следующих объявлениях.</span><span class="sxs-lookup"><span data-stu-id="94a16-151">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/considerations-in-overloading-procedures_6.vb)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a><span data-ttu-id="94a16-152">Программирование без типов как альтернатива перегрузке</span><span class="sxs-lookup"><span data-stu-id="94a16-152">Typeless Programming as an Alternative to Overloading</span></span>  
 <span data-ttu-id="94a16-153">Если вы хотите разрешить вызывающему коду для передачи различных типов данных в параметр, альтернативный подход — программирование.</span><span class="sxs-lookup"><span data-stu-id="94a16-153">If you want to allow the calling code to pass different data types to a parameter, an alternative approach is typeless programming.</span></span> <span data-ttu-id="94a16-154">Можно задать ключ для проверки типа `Off` либо [оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) или [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="94a16-154">You can set the type checking switch to `Off` with either the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) or the [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) compiler option.</span></span> <span data-ttu-id="94a16-155">Затем объявите тип данных параметра нет.</span><span class="sxs-lookup"><span data-stu-id="94a16-155">Then you do not have to declare the parameter's data type.</span></span> <span data-ttu-id="94a16-156">Однако такой подход имеет следующие недостатки по сравнению с перегрузкой:</span><span class="sxs-lookup"><span data-stu-id="94a16-156">However, this approach has the following disadvantages compared to overloading:</span></span>  
  
-   <span data-ttu-id="94a16-157">Программирование выводятся менее эффективный код выполнения.</span><span class="sxs-lookup"><span data-stu-id="94a16-157">Typeless programming produces less efficient execution code.</span></span>  
  
-   <span data-ttu-id="94a16-158">Процедура должна проверять каждый тип данных, которые можно предвидеть передан.</span><span class="sxs-lookup"><span data-stu-id="94a16-158">The procedure must test for every data type it anticipates being passed.</span></span>  
  
-   <span data-ttu-id="94a16-159">Компилятор не может сообщить об ошибке, если вызывающий код передает тип данных, процедура не поддерживает.</span><span class="sxs-lookup"><span data-stu-id="94a16-159">The compiler cannot signal an error if the calling code passes a data type that the procedure does not support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94a16-160">См. также</span><span class="sxs-lookup"><span data-stu-id="94a16-160">See Also</span></span>  
 [<span data-ttu-id="94a16-161">Процедуры</span><span class="sxs-lookup"><span data-stu-id="94a16-161">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="94a16-162">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="94a16-162">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="94a16-163">Рекомендации по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="94a16-163">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="94a16-164">Практическое руководство. Определение различных версий процедуры</span><span class="sxs-lookup"><span data-stu-id="94a16-164">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)  
 [<span data-ttu-id="94a16-165">Практическое руководство. Вызов перегруженной процедуры</span><span class="sxs-lookup"><span data-stu-id="94a16-165">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)  
 [<span data-ttu-id="94a16-166">Практическое руководство. Перегрузка процедуры, которая принимает один необязательный параметр</span><span class="sxs-lookup"><span data-stu-id="94a16-166">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [<span data-ttu-id="94a16-167">Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров</span><span class="sxs-lookup"><span data-stu-id="94a16-167">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [<span data-ttu-id="94a16-168">Разрешение перегрузки</span><span class="sxs-lookup"><span data-stu-id="94a16-168">Overload Resolution</span></span>](./overload-resolution.md)  
 [<span data-ttu-id="94a16-169">Перегрузки</span><span class="sxs-lookup"><span data-stu-id="94a16-169">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
