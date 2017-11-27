---
title: "Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], indefinite number of parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 37d5b47f06bad1c2a8871168c5642663aedcccf2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a><span data-ttu-id="03f1f-102">Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="03f1f-102">How to: Overload a Procedure that Takes an Indefinite Number of Parameters (Visual Basic)</span></span>
<span data-ttu-id="03f1f-103">Если процедура имеет [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) параметра, нельзя определить перегруженную версию, принимающую одномерный массив для массива параметров.</span><span class="sxs-lookup"><span data-stu-id="03f1f-103">If a procedure has a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, you cannot define an overloaded version taking a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="03f1f-104">Дополнительные сведения см. в разделе «Неявные перегрузки для параметра ParamArray» в [вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="03f1f-104">For more information, see "Implicit Overloads for a ParamArray Parameter" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a><span data-ttu-id="03f1f-105">Перегрузка процедуры, которая принимает переменное число параметров</span><span class="sxs-lookup"><span data-stu-id="03f1f-105">To overload a procedure that takes a variable number of parameters</span></span>  
  
1.  <span data-ttu-id="03f1f-106">Выяснить, что процедура и вызов уместно перегруженные версии, более чем из `ParamArray` параметра.</span><span class="sxs-lookup"><span data-stu-id="03f1f-106">Ascertain that the procedure and calling code logic benefits from overloaded versions more than from a `ParamArray` parameter.</span></span> <span data-ttu-id="03f1f-107">В разделе «Перегрузки и массивы параметров» в [вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="03f1f-107">See "Overloads and ParamArrays" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
2.  <span data-ttu-id="03f1f-108">Определите, какое число предоставленных значений должна принимать процедура в переменной части списка параметров.</span><span class="sxs-lookup"><span data-stu-id="03f1f-108">Determine which numbers of supplied values the procedure should accept in the variable part of the parameter list.</span></span> <span data-ttu-id="03f1f-109">Это может включать случай отсутствия значений и может включать в случае одномерного массива.</span><span class="sxs-lookup"><span data-stu-id="03f1f-109">This might include the case of no value, and it might include the case of a single one-dimensional array.</span></span>  
  
3.  <span data-ttu-id="03f1f-110">Для каждого допустимого числа предоставленных значений напишите `Sub` или `Function` инструкцию объявления, определяющую соответствующий список параметров.</span><span class="sxs-lookup"><span data-stu-id="03f1f-110">For each acceptable number of supplied values, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="03f1f-111">Не используйте в `Optional` или `ParamArray` ключевое слово в данной перегруженной версии.</span><span class="sxs-lookup"><span data-stu-id="03f1f-111">Do not use either the `Optional` or the `ParamArray` keyword in this overloaded version.</span></span>  
  
4.  <span data-ttu-id="03f1f-112">В каждое объявление перед `Sub` или `Function` ключевого слова with [перегрузки](../../../../visual-basic/language-reference/modifiers/overloads.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="03f1f-112">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
5.  <span data-ttu-id="03f1f-113">После каждого объявления напишите код процедуры, который должен выполняться, когда вызывающий код не предоставляет значения, соответствующие списка параметров в объявлении.</span><span class="sxs-lookup"><span data-stu-id="03f1f-113">Following each declaration, write the procedure code that should execute when the calling code supplies values corresponding to that declaration's parameter list.</span></span>  
  
6.  <span data-ttu-id="03f1f-114">Завершите выполнение каждой процедуры с `End Sub` или `End Function` инструкцию соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="03f1f-114">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03f1f-115">Пример</span><span class="sxs-lookup"><span data-stu-id="03f1f-115">Example</span></span>  
 <span data-ttu-id="03f1f-116">В следующем примере показано процедура, определенная с [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) параметра, а затем аналогичный набор перегруженных процедур.</span><span class="sxs-lookup"><span data-stu-id="03f1f-116">The following example shows a procedure defined with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, and then an equivalent set of overloaded procedures.</span></span>  
  
 [!code-vb[VbVbcnProcedures#69](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_2.vb)]  
  
 <span data-ttu-id="03f1f-117">Нельзя перегрузить процедуру со списком параметров, который принимает одномерный массив для массива параметров.</span><span class="sxs-lookup"><span data-stu-id="03f1f-117">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="03f1f-118">Тем не менее можно использовать подписи неявных перегрузок.</span><span class="sxs-lookup"><span data-stu-id="03f1f-118">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="03f1f-119">Это показано в следующих объявлениях.</span><span class="sxs-lookup"><span data-stu-id="03f1f-119">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_3.vb)]  
  
 <span data-ttu-id="03f1f-120">Код перегруженных версий не имеет для проверки в вызывающем коде задано одно или несколько значений для `ParamArray` параметра, и если да, сколько.</span><span class="sxs-lookup"><span data-stu-id="03f1f-120">The code in the overloaded versions does not have to test whether the calling code supplied one or more values for the `ParamArray` parameter, or if so, how many.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="03f1f-121">передает управление версию, которая соответствует списку аргументов вызова.</span><span class="sxs-lookup"><span data-stu-id="03f1f-121"> passes control to the version matching the calling argument list.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="03f1f-122">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="03f1f-122">Compiling the Code</span></span>  
 <span data-ttu-id="03f1f-123">Поскольку процедура с `ParamArray` параметр эквивалентен набор перегруженных версий, нельзя перегрузить такую процедуру со списком параметров, соответствующим любому из этих неявных перегрузок.</span><span class="sxs-lookup"><span data-stu-id="03f1f-123">Because a procedure with a `ParamArray` parameter is equivalent to a set of overloaded versions, you cannot overload such a procedure with a parameter list corresponding to any of these implicit overloads.</span></span> <span data-ttu-id="03f1f-124">Дополнительные сведения см. в разделе [вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="03f1f-124">For more information, see [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="03f1f-125">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="03f1f-125">.NET Framework Security</span></span>  
 <span data-ttu-id="03f1f-126">При работе с которой неограниченно большим массивом есть риск переполнения некоторой внутренней емкости приложения.</span><span class="sxs-lookup"><span data-stu-id="03f1f-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="03f1f-127">Если вы принимаете массив параметров, следует проверить его длину массива, вызывающий код передается и предпринять соответствующие действия, если она слишком велика для приложения.</span><span class="sxs-lookup"><span data-stu-id="03f1f-127">If you accept a parameter array, you should test for the length of the array the calling code passed to it, and take appropriate steps if it is too large for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03f1f-128">См. также</span><span class="sxs-lookup"><span data-stu-id="03f1f-128">See Also</span></span>  
 [<span data-ttu-id="03f1f-129">Процедуры</span><span class="sxs-lookup"><span data-stu-id="03f1f-129">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="03f1f-130">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="03f1f-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="03f1f-131">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="03f1f-131">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="03f1f-132">Массивы параметров</span><span class="sxs-lookup"><span data-stu-id="03f1f-132">Parameter Arrays</span></span>](./parameter-arrays.md)  
 [<span data-ttu-id="03f1f-133">Перегрузка процедур</span><span class="sxs-lookup"><span data-stu-id="03f1f-133">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="03f1f-134">Рекомендации по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="03f1f-134">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="03f1f-135">Практическое руководство. Определение различных версий процедуры</span><span class="sxs-lookup"><span data-stu-id="03f1f-135">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)  
 [<span data-ttu-id="03f1f-136">Практическое руководство. Вызов перегруженной процедуры</span><span class="sxs-lookup"><span data-stu-id="03f1f-136">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)  
 [<span data-ttu-id="03f1f-137">Практическое руководство. Перегрузка процедуры, которая принимает один необязательный параметр</span><span class="sxs-lookup"><span data-stu-id="03f1f-137">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [<span data-ttu-id="03f1f-138">Разрешение перегрузки</span><span class="sxs-lookup"><span data-stu-id="03f1f-138">Overload Resolution</span></span>](./overload-resolution.md)
