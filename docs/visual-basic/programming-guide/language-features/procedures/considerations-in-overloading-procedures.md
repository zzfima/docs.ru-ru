---
title: "Вопросы, связанные с перегрузкой процедур (Visual Basic) | Документы Microsoft"
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
- signatures, ParamArray arguments
- ParamArray keyword, parameter arrays
- ParamArray keyword, arguments and signatures
- function overloading, implicit overloads for ParamArray
- ParamArray keyword, signatures
- Visual Basic code, procedures
- arguments [Visual Basic], parameter arrays
- procedures, overloading
- parameters, lists
- function overloading, typeless programming
- typeless programming
- function overloading, restrictions
- arguments [Visual Basic], optional
- optional arguments, overloading
- signatures, procedure
- parameter lists
- parameter arrays, overloading arguments
- Visual Basic code, parameter lists
- procedure overloading, considerations
- Option Explicit statement
- restrictions, overloading procedures
- procedures, parameter lists
ms.assetid: a2001248-10d0-42c5-b0ce-eeedc987319f
caps.latest.revision: 26
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
ms.openlocfilehash: 486e6c08fe6284cc9b5856fb848f7307a5651120
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="considerations-in-overloading-procedures-visual-basic"></a><span data-ttu-id="08991-102">Вопросы, связанные с перегрузкой процедур (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08991-102">Considerations in Overloading Procedures (Visual Basic)</span></span>
<span data-ttu-id="08991-103">При перегрузке процедур необходимо использовать другой *подписи* для каждой из перегруженных версий.</span><span class="sxs-lookup"><span data-stu-id="08991-103">When you overload a procedure, you must use a different *signature* for each overloaded version.</span></span> <span data-ttu-id="08991-104">Это обычно означает, что каждая версия необходимо указать другой список параметров.</span><span class="sxs-lookup"><span data-stu-id="08991-104">This usually means each version must specify a different parameter list.</span></span> <span data-ttu-id="08991-105">Дополнительные сведения см. в разделе «Другую подпись» в [перегрузка процедур](./procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="08991-105">For more information, see "Different Signature" in [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
 <span data-ttu-id="08991-106">Можно перегрузить `Function` процедуры с `Sub` процедура и наоборот, если они имеют разные сигнатуры.</span><span class="sxs-lookup"><span data-stu-id="08991-106">You can overload a `Function` procedure with a `Sub` procedure, and vice versa, provided they have different signatures.</span></span> <span data-ttu-id="08991-107">Две перегрузки не отличаются только тем, что одна имеет возвращаемое значение, а другой — нет.</span><span class="sxs-lookup"><span data-stu-id="08991-107">Two overloads cannot differ only in that one has a return value and the other does not.</span></span>  
  
 <span data-ttu-id="08991-108">Свойство можно перегрузить перегрузка процедуры, так же, как и с тем же ограничениями.</span><span class="sxs-lookup"><span data-stu-id="08991-108">You can overload a property the same way you overload a procedure, and with the same restrictions.</span></span> <span data-ttu-id="08991-109">Однако нельзя перегрузить процедуру со свойством или наоборот.</span><span class="sxs-lookup"><span data-stu-id="08991-109">However, you cannot overload a procedure with a property, or vice versa.</span></span>  
  
## <a name="alternatives-to-overloaded-versions"></a><span data-ttu-id="08991-110">Альтернативы перегруженных версий</span><span class="sxs-lookup"><span data-stu-id="08991-110">Alternatives to Overloaded Versions</span></span>  
 <span data-ttu-id="08991-111">Иногда существуют альтернативы перегруженных версий, особенно если наличие аргументов является необязательным или их количество может меняться.</span><span class="sxs-lookup"><span data-stu-id="08991-111">You sometimes have alternatives to overloaded versions, particularly when the presence of arguments is optional or their number is variable.</span></span>  
  
 <span data-ttu-id="08991-112">Имейте в виду, что необязательные аргументы могут не поддерживаться все языки, а массивы параметров ограничены [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="08991-112">Keep in mind that optional arguments are not necessarily supported by all languages, and parameter arrays are limited to [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="08991-113">При создании процедуры, который должен вызываться из кода, написанного на любом из нескольких различных языков, перегруженные версии предоставляют наибольшую гибкость.</span><span class="sxs-lookup"><span data-stu-id="08991-113">If you are writing a procedure that is likely to be called from code written in any of several different languages, overloaded versions offer the greatest flexibility.</span></span>  
  
### <a name="overloads-and-optional-arguments"></a><span data-ttu-id="08991-114">Перегрузки и необязательные аргументы</span><span class="sxs-lookup"><span data-stu-id="08991-114">Overloads and Optional Arguments</span></span>  
 <span data-ttu-id="08991-115">Если вызывающий код может при необходимости предоставить или пропустить один или несколько аргументов, можно определить несколько перегруженных версий или использовать дополнительные параметры.</span><span class="sxs-lookup"><span data-stu-id="08991-115">When the calling code can optionally supply or omit one or more arguments, you can define multiple overloaded versions or use optional parameters.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="08991-116">Когда следует использовать перегруженные версии</span><span class="sxs-lookup"><span data-stu-id="08991-116">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="08991-117">Можно определять наборы перегруженных версий в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="08991-117">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
-   <span data-ttu-id="08991-118">Логика в коде процедуры существенно отличается в зависимости от того, является ли вызывающий код предоставляет необязательный аргумент или нет.</span><span class="sxs-lookup"><span data-stu-id="08991-118">The logic in the procedure code is significantly different depending on whether the calling code supplies an optional argument or not.</span></span>  
  
-   <span data-ttu-id="08991-119">Код процедуры нельзя надежно проверить, является ли вызывающий код имеет указанный необязательный аргумент.</span><span class="sxs-lookup"><span data-stu-id="08991-119">The procedure code cannot reliably test whether the calling code has supplied an optional argument.</span></span> <span data-ttu-id="08991-120">Это происходит, например, если нет ни одного кандидата для значение по умолчанию, которое вызывающий код не может предоставить.</span><span class="sxs-lookup"><span data-stu-id="08991-120">This is the case, for example, if there is no possible candidate for a default value that the calling code could not be expected to supply.</span></span>  
  
#### <a name="when-to-use-optional-parameters"></a><span data-ttu-id="08991-121">Когда следует использовать дополнительные параметры</span><span class="sxs-lookup"><span data-stu-id="08991-121">When to Use Optional Parameters</span></span>  
 <span data-ttu-id="08991-122">Может потребоваться один или несколько необязательных параметров в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="08991-122">You might prefer one or more optional parameters in the following cases:</span></span>  
  
-   <span data-ttu-id="08991-123">Присвойте параметру значение по умолчанию является только требуемое действие, когда вызывающий код не предоставляет необязательный аргумент.</span><span class="sxs-lookup"><span data-stu-id="08991-123">The only required action when the calling code does not supply an optional argument is to set the parameter to a default value.</span></span> <span data-ttu-id="08991-124">В таком случае код процедуры можно упростить, если определить одну версию с одним или несколькими `Optional` параметров.</span><span class="sxs-lookup"><span data-stu-id="08991-124">In such a case, the procedure code can be less complicated if you define a single version with one or more `Optional` parameters.</span></span>  
  
 <span data-ttu-id="08991-125">Дополнительные сведения см. в разделе [необязательные параметры](./optional-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="08991-125">For more information, see [Optional Parameters](./optional-parameters.md).</span></span>  
  
### <a name="overloads-and-paramarrays"></a><span data-ttu-id="08991-126">Перегрузки и массивы параметров</span><span class="sxs-lookup"><span data-stu-id="08991-126">Overloads and ParamArrays</span></span>  
 <span data-ttu-id="08991-127">Если вызывающий код может передавать переменное число аргументов, можно определить несколько перегруженных версий или использовать массив параметров.</span><span class="sxs-lookup"><span data-stu-id="08991-127">When the calling code can pass a variable number of arguments, you can define multiple overloaded versions or use a parameter array.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="08991-128">Когда следует использовать перегруженные версии</span><span class="sxs-lookup"><span data-stu-id="08991-128">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="08991-129">Можно определять наборы перегруженных версий в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="08991-129">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
-   <span data-ttu-id="08991-130">Вы знаете, что вызывающий код передает в более чем небольшое количество значений в массиве параметров.</span><span class="sxs-lookup"><span data-stu-id="08991-130">You know that the calling code never passes more than a small number of values to the parameter array.</span></span>  
  
-   <span data-ttu-id="08991-131">Логика в коде процедуры существенно отличается в зависимости от количества значений, которые передает вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="08991-131">The logic in the procedure code is significantly different depending on how many values the calling code passes.</span></span>  
  
-   <span data-ttu-id="08991-132">Вызывающий код может передавать значения различных типов данных.</span><span class="sxs-lookup"><span data-stu-id="08991-132">The calling code can pass values of different data types.</span></span>  
  
#### <a name="when-to-use-a-parameter-array"></a><span data-ttu-id="08991-133">Когда следует использовать массив параметров</span><span class="sxs-lookup"><span data-stu-id="08991-133">When to Use a Parameter Array</span></span>  
 <span data-ttu-id="08991-134">Вам удобнее работать с `ParamArray` параметр в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="08991-134">You are better served by a `ParamArray` parameter in the following cases:</span></span>  
  
-   <span data-ttu-id="08991-135">Невозможно предсказать количество значений, вызывающий код может передать в массив параметров, и он может быть большим числом.</span><span class="sxs-lookup"><span data-stu-id="08991-135">You are not able to predict how many values the calling code can pass to the parameter array, and it could be a large number.</span></span>  
  
-   <span data-ttu-id="08991-136">Логика процедуры пригоден для прохода по всем значениям, которые передает вызывающий код выполняет по сути одинаковые операции над каждым значением.</span><span class="sxs-lookup"><span data-stu-id="08991-136">The procedure logic lends itself to iterating through all the values the calling code passes, performing essentially the same operations on every value.</span></span>  
  
 <span data-ttu-id="08991-137">Дополнительные сведения см. в разделе [массивы параметров](./parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="08991-137">For more information, see [Parameter Arrays](./parameter-arrays.md).</span></span>  
  
## <a name="implicit-overloads-for-optional-parameters"></a><span data-ttu-id="08991-138">Неявные перегрузки для дополнительных параметров</span><span class="sxs-lookup"><span data-stu-id="08991-138">Implicit Overloads for Optional Parameters</span></span>  
 <span data-ttu-id="08991-139">Процедуры с [необязательно](../../../../visual-basic/language-reference/modifiers/optional.md) эквивалентна двум перегруженным процедурам, с необязательным параметром, а другая — нет.</span><span class="sxs-lookup"><span data-stu-id="08991-139">A procedure with an [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameter is equivalent to two overloaded procedures, one with the optional parameter and one without it.</span></span> <span data-ttu-id="08991-140">Невозможно перегрузить такую процедуру со списком параметров, соответствующего любой из них.</span><span class="sxs-lookup"><span data-stu-id="08991-140">You cannot overload such a procedure with a parameter list corresponding to either of these.</span></span> <span data-ttu-id="08991-141">Показано в следующих объявлениях.</span><span class="sxs-lookup"><span data-stu-id="08991-141">The following declarations illustrate this.</span></span>  
  
 <span data-ttu-id="08991-142">[!code-vb[VbVbcnProcedures&#58;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="08991-142">[!code-vb[VbVbcnProcedures#58](./codesnippet/VisualBasic/considerations-in-overloading-procedures_1.vb)]</span></span>  
  
 <span data-ttu-id="08991-143">[!code-vb[VbVbcnProcedures&#60;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="08991-143">[!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/considerations-in-overloading-procedures_2.vb)]</span></span>  
  
 <span data-ttu-id="08991-144">[!code-vb[VbVbcnProcedures&#61;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="08991-144">[!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/considerations-in-overloading-procedures_3.vb)]</span></span>  
  
 <span data-ttu-id="08991-145">Для процедуры с более чем один необязательный параметр существует набор неявных перегрузок, получающихся логикой, подобного приведенному в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="08991-145">For a procedure with more than one optional parameter, there is a set of implicit overloads, arrived at by logic similar to that in the preceding example.</span></span>  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a><span data-ttu-id="08991-146">Неявные перегрузки для параметра ParamArray</span><span class="sxs-lookup"><span data-stu-id="08991-146">Implicit Overloads for a ParamArray Parameter</span></span>  
 <span data-ttu-id="08991-147">Компилятор считает, что процедуры с [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) параметра бесконечным числом перегрузок, отличающихся друг от друга, в то, что вызывающий код передает в массив параметров следующим образом:</span><span class="sxs-lookup"><span data-stu-id="08991-147">The compiler considers a procedure with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter to have an infinite number of overloads, differing from each other in what the calling code passes to the parameter array, as follows:</span></span>  
  
-   <span data-ttu-id="08991-148">Одна перегрузка, когда вызывающий код не передает аргумент`ParamArray`</span><span class="sxs-lookup"><span data-stu-id="08991-148">One overload for when the calling code does not supply an argument to the `ParamArray`</span></span>  
  
-   <span data-ttu-id="08991-149">Одна перегрузка, когда вызывающий код предоставляет одномерный массив `ParamArray` тип элемента</span><span class="sxs-lookup"><span data-stu-id="08991-149">One overload for when the calling code supplies a one-dimensional array of the `ParamArray` element type</span></span>  
  
-   <span data-ttu-id="08991-150">Одна перегрузка для каждого положительного целого числа, когда вызывающий код предоставляет количество аргументов, каждый из `ParamArray` тип элемента</span><span class="sxs-lookup"><span data-stu-id="08991-150">For every positive integer, one overload for when the calling code supplies that number of arguments, each of the `ParamArray` element type</span></span>  
  
 <span data-ttu-id="08991-151">Эти неявные перегрузки показывают следующие объявления.</span><span class="sxs-lookup"><span data-stu-id="08991-151">The following declarations illustrate these implicit overloads.</span></span>  
  
 <span data-ttu-id="08991-152">[!code-vb[VbVbcnProcedures&#68;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="08991-152">[!code-vb[VbVbcnProcedures#68](./codesnippet/VisualBasic/considerations-in-overloading-procedures_4.vb)]</span></span>  
  
 <span data-ttu-id="08991-153">[!code-vb[VbVbcnProcedures&#70;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="08991-153">[!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/considerations-in-overloading-procedures_5.vb)]</span></span>  
  
 <span data-ttu-id="08991-154">Нельзя перегрузить процедуру со списком параметров, который принимает одномерный массив для массива параметров.</span><span class="sxs-lookup"><span data-stu-id="08991-154">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="08991-155">Тем не менее можно использовать подписи неявных перегрузок.</span><span class="sxs-lookup"><span data-stu-id="08991-155">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="08991-156">Показано в следующих объявлениях.</span><span class="sxs-lookup"><span data-stu-id="08991-156">The following declarations illustrate this.</span></span>  
  
 <span data-ttu-id="08991-157">[!code-vb[VbVbcnProcedures&#71;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="08991-157">[!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/considerations-in-overloading-procedures_6.vb)]</span></span>  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a><span data-ttu-id="08991-158">Программирование без типов как альтернатива перегрузке</span><span class="sxs-lookup"><span data-stu-id="08991-158">Typeless Programming as an Alternative to Overloading</span></span>  
 <span data-ttu-id="08991-159">Если требуется разрешить вызывающему коду передачу различных типов данных в параметр альтернативный подход — программирование.</span><span class="sxs-lookup"><span data-stu-id="08991-159">If you want to allow the calling code to pass different data types to a parameter, an alternative approach is typeless programming.</span></span> <span data-ttu-id="08991-160">Можно задать ключ для проверки типа `Off` с помощью [оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) или [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="08991-160">You can set the type checking switch to `Off` with either the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) or the [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) compiler option.</span></span> <span data-ttu-id="08991-161">Затем у вас объявить тип данных параметра.</span><span class="sxs-lookup"><span data-stu-id="08991-161">Then you do not have to declare the parameter's data type.</span></span> <span data-ttu-id="08991-162">Однако такой подход имеет следующие недостатки по сравнению с перегрузкой:</span><span class="sxs-lookup"><span data-stu-id="08991-162">However, this approach has the following disadvantages compared to overloading:</span></span>  
  
-   <span data-ttu-id="08991-163">Программирование выводятся менее эффективного выполнения кода.</span><span class="sxs-lookup"><span data-stu-id="08991-163">Typeless programming produces less efficient execution code.</span></span>  
  
-   <span data-ttu-id="08991-164">Процедура должна проверять каждый тип данных, который может передан.</span><span class="sxs-lookup"><span data-stu-id="08991-164">The procedure must test for every data type it anticipates being passed.</span></span>  
  
-   <span data-ttu-id="08991-165">Компилятор не может сообщить об ошибке, если вызывающий код передает тип данных, процедура не поддерживает.</span><span class="sxs-lookup"><span data-stu-id="08991-165">The compiler cannot signal an error if the calling code passes a data type that the procedure does not support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08991-166">См. также</span><span class="sxs-lookup"><span data-stu-id="08991-166">See Also</span></span>  
 <span data-ttu-id="08991-167">[Процедуры](./index.md) </span><span class="sxs-lookup"><span data-stu-id="08991-167">[Procedures](./index.md) </span></span>  
<span data-ttu-id="08991-168"> [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="08991-168"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="08991-169"> [Рекомендации по устранению неполадок](./troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="08991-169"> [Troubleshooting Procedures](./troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="08991-170"> [Практическое руководство: определение различных версий процедуры](./how-to-define-multiple-versions-of-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="08991-170"> [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md) </span></span>  
<span data-ttu-id="08991-171"> [Практическое руководство: вызов перегруженной процедуры](./how-to-call-an-overloaded-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="08991-171"> [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md) </span></span>  
<span data-ttu-id="08991-172"> [Практическое руководство: перегрузка процедуры, которая принимает необязательные параметры](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="08991-172"> [How to: Overload a Procedure that Takes Optional Parameters](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span></span>  
<span data-ttu-id="08991-173"> [Практическое руководство: перегрузка процедуры, принимающей неопределенное число параметров](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="08991-173"> [How to: Overload a Procedure that Takes an Indefinite Number of Parameters](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span></span>  
<span data-ttu-id="08991-174"> [Разрешение перегрузки](./overload-resolution.md) </span><span class="sxs-lookup"><span data-stu-id="08991-174"> [Overload Resolution](./overload-resolution.md) </span></span>  
<span data-ttu-id="08991-175"> [Перегрузки](../../../../visual-basic/language-reference/modifiers/overloads.md)</span><span class="sxs-lookup"><span data-stu-id="08991-175"> [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)</span></span>
