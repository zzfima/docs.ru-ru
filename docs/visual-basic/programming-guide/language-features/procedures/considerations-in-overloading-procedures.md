---
title: Вопросы, связанные с перегрузкой процедур
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
ms.openlocfilehash: 4a0cfe176a59b3f90f5850ae8b4e34784c400c6b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351011"
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a><span data-ttu-id="9bfec-102">Вопросы, связанные с перегрузкой процедур (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9bfec-102">Considerations in Overloading Procedures (Visual Basic)</span></span>
<span data-ttu-id="9bfec-103">При перегрузке процедуры необходимо использовать другую *сигнатуру* для каждой перегруженной версии.</span><span class="sxs-lookup"><span data-stu-id="9bfec-103">When you overload a procedure, you must use a different *signature* for each overloaded version.</span></span> <span data-ttu-id="9bfec-104">Обычно это означает, что каждая версия должна указывать другой список параметров.</span><span class="sxs-lookup"><span data-stu-id="9bfec-104">This usually means each version must specify a different parameter list.</span></span> <span data-ttu-id="9bfec-105">Дополнительные сведения см. в разделе "другая сигнатура" в [перегрузке процедур](./procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="9bfec-105">For more information, see "Different Signature" in [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
 <span data-ttu-id="9bfec-106">Можно перегружать `Function` процедуру с помощью `Sub` процедуры, и наоборот, если они имеют разные сигнатуры.</span><span class="sxs-lookup"><span data-stu-id="9bfec-106">You can overload a `Function` procedure with a `Sub` procedure, and vice versa, provided they have different signatures.</span></span> <span data-ttu-id="9bfec-107">Две перегрузки не могут различаться только в том случае, если одна из них имеет возвращаемое значение, а другая — нет.</span><span class="sxs-lookup"><span data-stu-id="9bfec-107">Two overloads cannot differ only in that one has a return value and the other does not.</span></span>  
  
 <span data-ttu-id="9bfec-108">Свойство можно перегружать так же, как и при перегрузке процедуры, с теми же ограничениями.</span><span class="sxs-lookup"><span data-stu-id="9bfec-108">You can overload a property the same way you overload a procedure, and with the same restrictions.</span></span> <span data-ttu-id="9bfec-109">Однако нельзя перегружать процедуру со свойством или наоборот.</span><span class="sxs-lookup"><span data-stu-id="9bfec-109">However, you cannot overload a procedure with a property, or vice versa.</span></span>  
  
## <a name="alternatives-to-overloaded-versions"></a><span data-ttu-id="9bfec-110">Альтернативы перегруженным версиям</span><span class="sxs-lookup"><span data-stu-id="9bfec-110">Alternatives to Overloaded Versions</span></span>  
 <span data-ttu-id="9bfec-111">Иногда у вас есть альтернативы перегруженным версиям, особенно если присутствие аргументов является необязательным или их число является переменной.</span><span class="sxs-lookup"><span data-stu-id="9bfec-111">You sometimes have alternatives to overloaded versions, particularly when the presence of arguments is optional or their number is variable.</span></span>  
  
 <span data-ttu-id="9bfec-112">Помните, что необязательные аргументы не всегда поддерживаются всеми языками, а массивы параметров ограничены Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9bfec-112">Keep in mind that optional arguments are not necessarily supported by all languages, and parameter arrays are limited to Visual Basic.</span></span> <span data-ttu-id="9bfec-113">При написании процедуры, которая, скорее всего, будет вызываться из кода, написанного на любом из нескольких разных языков, перегруженные версии обеспечивают максимальную гибкость.</span><span class="sxs-lookup"><span data-stu-id="9bfec-113">If you are writing a procedure that is likely to be called from code written in any of several different languages, overloaded versions offer the greatest flexibility.</span></span>  
  
### <a name="overloads-and-optional-arguments"></a><span data-ttu-id="9bfec-114">Перегрузки и необязательные аргументы</span><span class="sxs-lookup"><span data-stu-id="9bfec-114">Overloads and Optional Arguments</span></span>  
 <span data-ttu-id="9bfec-115">Если вызывающий код может дополнительно указать или опустить один или несколько аргументов, можно определить несколько перегруженных версий или использовать необязательные параметры.</span><span class="sxs-lookup"><span data-stu-id="9bfec-115">When the calling code can optionally supply or omit one or more arguments, you can define multiple overloaded versions or use optional parameters.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="9bfec-116">Когда следует использовать перегруженные версии</span><span class="sxs-lookup"><span data-stu-id="9bfec-116">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="9bfec-117">Можно определить ряд перегруженных версий в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="9bfec-117">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
- <span data-ttu-id="9bfec-118">Логика в коде процедуры существенно различается в зависимости от того, предоставляет ли вызывающий код необязательный аргумент.</span><span class="sxs-lookup"><span data-stu-id="9bfec-118">The logic in the procedure code is significantly different depending on whether the calling code supplies an optional argument or not.</span></span>  
  
- <span data-ttu-id="9bfec-119">Код процедуры не может надежно проверить, предоставил ли вызывающий код необязательный аргумент.</span><span class="sxs-lookup"><span data-stu-id="9bfec-119">The procedure code cannot reliably test whether the calling code has supplied an optional argument.</span></span> <span data-ttu-id="9bfec-120">Это происходит, например, если нет возможных кандидатов для значения по умолчанию, которое вызывающий код не может ожидать.</span><span class="sxs-lookup"><span data-stu-id="9bfec-120">This is the case, for example, if there is no possible candidate for a default value that the calling code could not be expected to supply.</span></span>  
  
#### <a name="when-to-use-optional-parameters"></a><span data-ttu-id="9bfec-121">Когда следует использовать необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="9bfec-121">When to Use Optional Parameters</span></span>  
 <span data-ttu-id="9bfec-122">В следующих случаях можно предпочесть один или несколько необязательных параметров:</span><span class="sxs-lookup"><span data-stu-id="9bfec-122">You might prefer one or more optional parameters in the following cases:</span></span>  
  
- <span data-ttu-id="9bfec-123">Единственное необходимое действие, если вызывающий код не предоставляет необязательный аргумент, — установка для параметра значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9bfec-123">The only required action when the calling code does not supply an optional argument is to set the parameter to a default value.</span></span> <span data-ttu-id="9bfec-124">В этом случае код процедуры может быть менее сложным, если определить одну версию с одним или несколькими параметрами `Optional`.</span><span class="sxs-lookup"><span data-stu-id="9bfec-124">In such a case, the procedure code can be less complicated if you define a single version with one or more `Optional` parameters.</span></span>  
  
 <span data-ttu-id="9bfec-125">Дополнительные сведения см. в разделе [необязательные параметры](./optional-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="9bfec-125">For more information, see [Optional Parameters](./optional-parameters.md).</span></span>  
  
### <a name="overloads-and-paramarrays"></a><span data-ttu-id="9bfec-126">Перегрузки и Парамаррайс</span><span class="sxs-lookup"><span data-stu-id="9bfec-126">Overloads and ParamArrays</span></span>  
 <span data-ttu-id="9bfec-127">Когда вызывающий код может передать переменное число аргументов, можно определить несколько перегруженных версий или использовать массив параметров.</span><span class="sxs-lookup"><span data-stu-id="9bfec-127">When the calling code can pass a variable number of arguments, you can define multiple overloaded versions or use a parameter array.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="9bfec-128">Когда следует использовать перегруженные версии</span><span class="sxs-lookup"><span data-stu-id="9bfec-128">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="9bfec-129">Можно определить ряд перегруженных версий в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="9bfec-129">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
- <span data-ttu-id="9bfec-130">Известно, что вызывающий код никогда не передает больше чем небольшое число значений в массив параметров.</span><span class="sxs-lookup"><span data-stu-id="9bfec-130">You know that the calling code never passes more than a small number of values to the parameter array.</span></span>  
  
- <span data-ttu-id="9bfec-131">Логика в коде процедуры существенно различается в зависимости от количества значений, пройденных вызывающим кодом.</span><span class="sxs-lookup"><span data-stu-id="9bfec-131">The logic in the procedure code is significantly different depending on how many values the calling code passes.</span></span>  
  
- <span data-ttu-id="9bfec-132">Вызывающий код может передавать значения различных типов данных.</span><span class="sxs-lookup"><span data-stu-id="9bfec-132">The calling code can pass values of different data types.</span></span>  
  
#### <a name="when-to-use-a-parameter-array"></a><span data-ttu-id="9bfec-133">Когда следует использовать массив параметров</span><span class="sxs-lookup"><span data-stu-id="9bfec-133">When to Use a Parameter Array</span></span>  
 <span data-ttu-id="9bfec-134">Параметр `ParamArray` лучше обслуживать в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="9bfec-134">You are better served by a `ParamArray` parameter in the following cases:</span></span>  
  
- <span data-ttu-id="9bfec-135">Невозможно предсказать, сколько значений вызывающего кода можно передать в массив параметров, и это может быть большое число.</span><span class="sxs-lookup"><span data-stu-id="9bfec-135">You are not able to predict how many values the calling code can pass to the parameter array, and it could be a large number.</span></span>  
  
- <span data-ttu-id="9bfec-136">Логика процедуры позволяет выполнять итерацию всех значений, пройденных вызывающим кодом, выполняя фактически те же операции с каждым значением.</span><span class="sxs-lookup"><span data-stu-id="9bfec-136">The procedure logic lends itself to iterating through all the values the calling code passes, performing essentially the same operations on every value.</span></span>  
  
 <span data-ttu-id="9bfec-137">Дополнительные сведения см. в разделе [массивы параметров](./parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="9bfec-137">For more information, see [Parameter Arrays](./parameter-arrays.md).</span></span>  
  
## <a name="implicit-overloads-for-optional-parameters"></a><span data-ttu-id="9bfec-138">Неявные перегрузки для необязательных параметров</span><span class="sxs-lookup"><span data-stu-id="9bfec-138">Implicit Overloads for Optional Parameters</span></span>  
 <span data-ttu-id="9bfec-139">Процедура с [необязательным](../../../../visual-basic/language-reference/modifiers/optional.md) параметром эквивалентна двум перегруженным процедурам, одна с необязательным параметром, а другая — без нее.</span><span class="sxs-lookup"><span data-stu-id="9bfec-139">A procedure with an [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameter is equivalent to two overloaded procedures, one with the optional parameter and one without it.</span></span> <span data-ttu-id="9bfec-140">Невозможно перегрузить такую процедуру со списком параметров, соответствующим одному из них.</span><span class="sxs-lookup"><span data-stu-id="9bfec-140">You cannot overload such a procedure with a parameter list corresponding to either of these.</span></span> <span data-ttu-id="9bfec-141">Это показано в следующих объявлениях.</span><span class="sxs-lookup"><span data-stu-id="9bfec-141">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#58)]  
  
 [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
 [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
 <span data-ttu-id="9bfec-142">Для процедуры с более чем одним необязательным параметром существует набор неявных перегрузок, которые прибывают логикой, аналогичной той, которая описана в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="9bfec-142">For a procedure with more than one optional parameter, there is a set of implicit overloads, arrived at by logic similar to that in the preceding example.</span></span>  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a><span data-ttu-id="9bfec-143">Неявные перегрузки для параметра ParamArray</span><span class="sxs-lookup"><span data-stu-id="9bfec-143">Implicit Overloads for a ParamArray Parameter</span></span>  
 <span data-ttu-id="9bfec-144">Компилятор считает, что процедура с параметром [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) имеет бесконечное количество перегрузок, отличающихся друг от друга тем, что вызывающий код передает в массив параметров, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9bfec-144">The compiler considers a procedure with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter to have an infinite number of overloads, differing from each other in what the calling code passes to the parameter array, as follows:</span></span>  
  
- <span data-ttu-id="9bfec-145">Одна перегрузка для, когда вызывающий код не предоставляет аргумент в `ParamArray`</span><span class="sxs-lookup"><span data-stu-id="9bfec-145">One overload for when the calling code does not supply an argument to the `ParamArray`</span></span>  
  
- <span data-ttu-id="9bfec-146">Одна перегрузка для, когда вызывающий код предоставляет одномерный массив `ParamArray`ного типа элемента</span><span class="sxs-lookup"><span data-stu-id="9bfec-146">One overload for when the calling code supplies a one-dimensional array of the `ParamArray` element type</span></span>  
  
- <span data-ttu-id="9bfec-147">Для каждого положительного целого числа одна перегрузка для, когда вызывающий код предоставляет количество аргументов, каждый тип элемента `ParamArray`</span><span class="sxs-lookup"><span data-stu-id="9bfec-147">For every positive integer, one overload for when the calling code supplies that number of arguments, each of the `ParamArray` element type</span></span>  
  
 <span data-ttu-id="9bfec-148">Следующие объявления иллюстрируют эти Неявные перегрузки.</span><span class="sxs-lookup"><span data-stu-id="9bfec-148">The following declarations illustrate these implicit overloads.</span></span>  
  
 [!code-vb[VbVbcnProcedures#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#68)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 <span data-ttu-id="9bfec-149">Невозможно перегрузить такую процедуру со списком параметров, принимающим одномерный массив для массива параметров.</span><span class="sxs-lookup"><span data-stu-id="9bfec-149">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="9bfec-150">Однако можно использовать сигнатуры других неявных перегрузок.</span><span class="sxs-lookup"><span data-stu-id="9bfec-150">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="9bfec-151">Это показано в следующих объявлениях.</span><span class="sxs-lookup"><span data-stu-id="9bfec-151">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a><span data-ttu-id="9bfec-152">Нетипизированное программирование в качестве альтернативы перегрузке</span><span class="sxs-lookup"><span data-stu-id="9bfec-152">Typeless Programming as an Alternative to Overloading</span></span>  
 <span data-ttu-id="9bfec-153">Если вы хотите разрешить вызывающему коду передавать в параметр различные типы данных, альтернативным подходом является программирование без типа.</span><span class="sxs-lookup"><span data-stu-id="9bfec-153">If you want to allow the calling code to pass different data types to a parameter, an alternative approach is typeless programming.</span></span> <span data-ttu-id="9bfec-154">Параметр проверки типа можно установить в `Off` с помощью [оператора Option строго](../../../../visual-basic/language-reference/statements/option-strict-statement.md) или [-оптионстрикт](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) компилятора.</span><span class="sxs-lookup"><span data-stu-id="9bfec-154">You can set the type checking switch to `Off` with either the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) or the [-optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) compiler option.</span></span> <span data-ttu-id="9bfec-155">После этого не нужно объявлять тип данных параметра.</span><span class="sxs-lookup"><span data-stu-id="9bfec-155">Then you do not have to declare the parameter's data type.</span></span> <span data-ttu-id="9bfec-156">Однако этот подход имеет следующие недостатки по сравнению с перегрузкой:</span><span class="sxs-lookup"><span data-stu-id="9bfec-156">However, this approach has the following disadvantages compared to overloading:</span></span>  
  
- <span data-ttu-id="9bfec-157">Программирование без типов дает менее эффективный код выполнения.</span><span class="sxs-lookup"><span data-stu-id="9bfec-157">Typeless programming produces less efficient execution code.</span></span>  
  
- <span data-ttu-id="9bfec-158">Процедура должна тестироваться для каждого типа данных, который он ожидает передачи.</span><span class="sxs-lookup"><span data-stu-id="9bfec-158">The procedure must test for every data type it anticipates being passed.</span></span>  
  
- <span data-ttu-id="9bfec-159">Компилятор не может сообщить об ошибке, если вызывающий код передает тип данных, который не поддерживает процедура.</span><span class="sxs-lookup"><span data-stu-id="9bfec-159">The compiler cannot signal an error if the calling code passes a data type that the procedure does not support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bfec-160">См. также</span><span class="sxs-lookup"><span data-stu-id="9bfec-160">See also</span></span>

- [<span data-ttu-id="9bfec-161">Процедуры</span><span class="sxs-lookup"><span data-stu-id="9bfec-161">Procedures</span></span>](./index.md)
- [<span data-ttu-id="9bfec-162">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="9bfec-162">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="9bfec-163">Рекомендации по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="9bfec-163">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="9bfec-164">Практическое руководство. Определение различных версий процедуры</span><span class="sxs-lookup"><span data-stu-id="9bfec-164">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="9bfec-165">Практическое руководство. Вызов перегруженной процедуры</span><span class="sxs-lookup"><span data-stu-id="9bfec-165">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="9bfec-166">Практическое руководство. Перегрузка процедуры, которая принимает один необязательный параметр</span><span class="sxs-lookup"><span data-stu-id="9bfec-166">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="9bfec-167">Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров</span><span class="sxs-lookup"><span data-stu-id="9bfec-167">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="9bfec-168">Разрешение перегрузки</span><span class="sxs-lookup"><span data-stu-id="9bfec-168">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="9bfec-169">Overloads</span><span class="sxs-lookup"><span data-stu-id="9bfec-169">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
