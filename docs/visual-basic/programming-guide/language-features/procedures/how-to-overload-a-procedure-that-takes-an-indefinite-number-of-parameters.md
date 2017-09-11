---
title: "Практическое руководство: перегрузка процедуры, принимающей неопределенное число параметров (Visual Basic) | Документы Microsoft"
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
- procedures, parameters
- procedure overloading, indefinite number of parameters
- procedures, defining
- Visual Basic code, procedures
- procedure parameters
- procedures, overloading
- procedures, multiple versions
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
caps.latest.revision: 18
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
ms.openlocfilehash: 3e4ef81049f3b0d3ab1271fb709f07c37f274a88
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a><span data-ttu-id="2ae29-102">Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ae29-102">How to: Overload a Procedure that Takes an Indefinite Number of Parameters (Visual Basic)</span></span>
<span data-ttu-id="2ae29-103">Если процедура имеет [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) параметра, нельзя определить перегруженную версию, принимающую одномерный массив для массива параметров.</span><span class="sxs-lookup"><span data-stu-id="2ae29-103">If a procedure has a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, you cannot define an overloaded version taking a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="2ae29-104">Дополнительные сведения см. в разделе «Неявные перегрузки для параметра ParamArray» в [вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="2ae29-104">For more information, see "Implicit Overloads for a ParamArray Parameter" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a><span data-ttu-id="2ae29-105">Чтобы перегрузить процедуру, которая принимает переменное число параметров</span><span class="sxs-lookup"><span data-stu-id="2ae29-105">To overload a procedure that takes a variable number of parameters</span></span>  
  
1.  <span data-ttu-id="2ae29-106">Выяснить, что процедуры и вызов уместно перегруженных версий более чем из `ParamArray` параметр.</span><span class="sxs-lookup"><span data-stu-id="2ae29-106">Ascertain that the procedure and calling code logic benefits from overloaded versions more than from a `ParamArray` parameter.</span></span> <span data-ttu-id="2ae29-107">В разделе «Перегрузки и массивы параметров» [вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="2ae29-107">See "Overloads and ParamArrays" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
2.  <span data-ttu-id="2ae29-108">Определите, какое число предоставленных значений должна принимать процедура в переменной части списка параметров.</span><span class="sxs-lookup"><span data-stu-id="2ae29-108">Determine which numbers of supplied values the procedure should accept in the variable part of the parameter list.</span></span> <span data-ttu-id="2ae29-109">Это может включать случай отсутствия значений и может включать случай одномерного массива.</span><span class="sxs-lookup"><span data-stu-id="2ae29-109">This might include the case of no value, and it might include the case of a single one-dimensional array.</span></span>  
  
3.  <span data-ttu-id="2ae29-110">Для каждого допустимого числа предоставленных значений напишите `Sub` или `Function` инструкцию объявления, определяющую соответствующий список параметров.</span><span class="sxs-lookup"><span data-stu-id="2ae29-110">For each acceptable number of supplied values, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="2ae29-111">Не используйте в `Optional` или `ParamArray` ключевое слово в данной перегруженной версии.</span><span class="sxs-lookup"><span data-stu-id="2ae29-111">Do not use either the `Optional` or the `ParamArray` keyword in this overloaded version.</span></span>  
  
4.  <span data-ttu-id="2ae29-112">В каждом объявлении перед `Sub` или `Function` ключевого слова with [перегрузки](../../../../visual-basic/language-reference/modifiers/overloads.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="2ae29-112">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
5.  <span data-ttu-id="2ae29-113">После каждого объявления напишите код процедуры, который должен выполняться, когда вызывающий код предоставляет значения, соответствующие элементам списка параметров в объявлении.</span><span class="sxs-lookup"><span data-stu-id="2ae29-113">Following each declaration, write the procedure code that should execute when the calling code supplies values corresponding to that declaration's parameter list.</span></span>  
  
6.  <span data-ttu-id="2ae29-114">Завершите выполнение каждой процедуры с `End Sub` или `End Function` инструкцию соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="2ae29-114">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ae29-115">Пример</span><span class="sxs-lookup"><span data-stu-id="2ae29-115">Example</span></span>  
 <span data-ttu-id="2ae29-116">В следующем примере показано процедура, определенная с [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) параметр и эквивалентный набор перегруженных процедур.</span><span class="sxs-lookup"><span data-stu-id="2ae29-116">The following example shows a procedure defined with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, and then an equivalent set of overloaded procedures.</span></span>  
  
 <span data-ttu-id="2ae29-117">[!code-vb[VbVbcnProcedures&#69;](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2ae29-117">[!code-vb[VbVbcnProcedures#69](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_1.vb)]</span></span>  
  
 <span data-ttu-id="2ae29-118">[!code-vb[VbVbcnProcedures&#70;](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="2ae29-118">[!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_2.vb)]</span></span>  
  
 <span data-ttu-id="2ae29-119">Нельзя перегрузить процедуру со списком параметров, который принимает одномерный массив для массива параметров.</span><span class="sxs-lookup"><span data-stu-id="2ae29-119">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="2ae29-120">Тем не менее можно использовать подписи неявных перегрузок.</span><span class="sxs-lookup"><span data-stu-id="2ae29-120">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="2ae29-121">Показано в следующих объявлениях.</span><span class="sxs-lookup"><span data-stu-id="2ae29-121">The following declarations illustrate this.</span></span>  
  
 <span data-ttu-id="2ae29-122">[!code-vb[VbVbcnProcedures&#71;](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="2ae29-122">[!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_3.vb)]</span></span>  
  
 <span data-ttu-id="2ae29-123">Код перегруженных версий не имеет для проверки в вызывающем коде задано одно или несколько значений для `ParamArray` параметра, и если да, сколько.</span><span class="sxs-lookup"><span data-stu-id="2ae29-123">The code in the overloaded versions does not have to test whether the calling code supplied one or more values for the `ParamArray` parameter, or if so, how many.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="2ae29-124">передает управление версию, которая соответствует списку аргументов вызова.</span><span class="sxs-lookup"><span data-stu-id="2ae29-124"> passes control to the version matching the calling argument list.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2ae29-125">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="2ae29-125">Compiling the Code</span></span>  
 <span data-ttu-id="2ae29-126">Поскольку процедура с `ParamArray` эквивалентна набору перегруженных версий, нельзя перегрузить такую процедуру со списком параметров, соответствующим любому из этих неявных перегрузок.</span><span class="sxs-lookup"><span data-stu-id="2ae29-126">Because a procedure with a `ParamArray` parameter is equivalent to a set of overloaded versions, you cannot overload such a procedure with a parameter list corresponding to any of these implicit overloads.</span></span> <span data-ttu-id="2ae29-127">Дополнительные сведения см. в разделе [вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="2ae29-127">For more information, see [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="2ae29-128">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2ae29-128">.NET Framework Security</span></span>  
 <span data-ttu-id="2ae29-129">При работе с которой неограниченно большим массивом есть риск переполнения некоторой внутренней емкости приложения.</span><span class="sxs-lookup"><span data-stu-id="2ae29-129">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="2ae29-130">Принимается массив параметров, следует проверить его длину массива, вызывающий код передается и предпринять соответствующие действия, если она слишком велика для приложения.</span><span class="sxs-lookup"><span data-stu-id="2ae29-130">If you accept a parameter array, you should test for the length of the array the calling code passed to it, and take appropriate steps if it is too large for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ae29-131">См. также</span><span class="sxs-lookup"><span data-stu-id="2ae29-131">See Also</span></span>  
 <span data-ttu-id="2ae29-132">[Процедуры](./index.md) </span><span class="sxs-lookup"><span data-stu-id="2ae29-132">[Procedures](./index.md) </span></span>  
<span data-ttu-id="2ae29-133"> [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="2ae29-133"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="2ae29-134"> [Необязательные параметры](./optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="2ae29-134"> [Optional Parameters](./optional-parameters.md) </span></span>  
<span data-ttu-id="2ae29-135"> [Массивы параметров](./parameter-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="2ae29-135"> [Parameter Arrays](./parameter-arrays.md) </span></span>  
<span data-ttu-id="2ae29-136"> [Перегрузка процедур](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="2ae29-136"> [Procedure Overloading](./procedure-overloading.md) </span></span>  
<span data-ttu-id="2ae29-137"> [Рекомендации по устранению неполадок](./troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="2ae29-137"> [Troubleshooting Procedures](./troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="2ae29-138"> [Практическое руководство: определение различных версий процедуры](./how-to-define-multiple-versions-of-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="2ae29-138"> [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md) </span></span>  
<span data-ttu-id="2ae29-139"> [Практическое руководство: вызов перегруженной процедуры](./how-to-call-an-overloaded-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="2ae29-139"> [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md) </span></span>  
<span data-ttu-id="2ae29-140"> [Практическое руководство: перегрузка процедуры, которая принимает необязательные параметры](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="2ae29-140"> [How to: Overload a Procedure that Takes Optional Parameters](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span></span>  
<span data-ttu-id="2ae29-141"> [Разрешение перегрузки](./overload-resolution.md)</span><span class="sxs-lookup"><span data-stu-id="2ae29-141"> [Overload Resolution](./overload-resolution.md)</span></span>
