---
title: Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], indefinite number of parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
ms.openlocfilehash: 3cf75fc6221364704379eb23d308481c34e6c0d6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61955745"
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a><span data-ttu-id="a459f-102">Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a459f-102">How to: Overload a Procedure that Takes an Indefinite Number of Parameters (Visual Basic)</span></span>
<span data-ttu-id="a459f-103">Если процедура имеет [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) параметр, не может определить перегруженную версию, принимающую одномерный массив для массива параметров.</span><span class="sxs-lookup"><span data-stu-id="a459f-103">If a procedure has a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, you cannot define an overloaded version taking a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="a459f-104">Дополнительные сведения см. в разделе «Неявные перегрузки для параметра ParamArray» в [вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="a459f-104">For more information, see "Implicit Overloads for a ParamArray Parameter" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a><span data-ttu-id="a459f-105">Перегрузка процедуры, которая принимает переменное количество параметров</span><span class="sxs-lookup"><span data-stu-id="a459f-105">To overload a procedure that takes a variable number of parameters</span></span>  
  
1. <span data-ttu-id="a459f-106">Выяснить, что процедура и вызов уместно перегруженные версии, более чем из `ParamArray` параметра.</span><span class="sxs-lookup"><span data-stu-id="a459f-106">Ascertain that the procedure and calling code logic benefits from overloaded versions more than from a `ParamArray` parameter.</span></span> <span data-ttu-id="a459f-107">См. в разделе «Перегрузки и массивы параметров» в [вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="a459f-107">See "Overloads and ParamArrays" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
2. <span data-ttu-id="a459f-108">Определите, какое число предоставленных значений должна принимать процедура в переменной части списка параметров.</span><span class="sxs-lookup"><span data-stu-id="a459f-108">Determine which numbers of supplied values the procedure should accept in the variable part of the parameter list.</span></span> <span data-ttu-id="a459f-109">Это может включать случай отсутствия значений и может включать в случае одномерного массива.</span><span class="sxs-lookup"><span data-stu-id="a459f-109">This might include the case of no value, and it might include the case of a single one-dimensional array.</span></span>  
  
3. <span data-ttu-id="a459f-110">Напишите для каждого допустимого числа предоставленных значений `Sub` или `Function` оператора объявления, который определяет соответствующий список параметров.</span><span class="sxs-lookup"><span data-stu-id="a459f-110">For each acceptable number of supplied values, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="a459f-111">Не используйте в `Optional` или `ParamArray` ключевое слово в данной перегруженной версии.</span><span class="sxs-lookup"><span data-stu-id="a459f-111">Do not use either the `Optional` or the `ParamArray` keyword in this overloaded version.</span></span>  
  
4. <span data-ttu-id="a459f-112">В каждое объявление перед `Sub` или `Function` ключевого слова with [перегружает](../../../../visual-basic/language-reference/modifiers/overloads.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="a459f-112">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
5. <span data-ttu-id="a459f-113">После каждого объявления напишите код процедуры, который должен выполняться, когда вызывающий код предоставляет значения, соответствующие списка параметров в объявлении.</span><span class="sxs-lookup"><span data-stu-id="a459f-113">Following each declaration, write the procedure code that should execute when the calling code supplies values corresponding to that declaration's parameter list.</span></span>  
  
6. <span data-ttu-id="a459f-114">Завершите выполнение каждой процедуры с `End Sub` или `End Function` инструкцию соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="a459f-114">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a459f-115">Пример</span><span class="sxs-lookup"><span data-stu-id="a459f-115">Example</span></span>  
 <span data-ttu-id="a459f-116">В следующем примере показано процедура, определенная с помощью [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) параметра, а затем эквивалентным набором перегруженные процедуры.</span><span class="sxs-lookup"><span data-stu-id="a459f-116">The following example shows a procedure defined with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, and then an equivalent set of overloaded procedures.</span></span>  
  
 [!code-vb[VbVbcnProcedures#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#69)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 <span data-ttu-id="a459f-117">Не могут перегружать процедуру со списком параметров, который принимает одномерный массив для массива параметров.</span><span class="sxs-lookup"><span data-stu-id="a459f-117">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="a459f-118">Тем не менее можно использовать подписи других неявных перегрузок.</span><span class="sxs-lookup"><span data-stu-id="a459f-118">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="a459f-119">Следующие объявления, иллюстрируют это.</span><span class="sxs-lookup"><span data-stu-id="a459f-119">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
 <span data-ttu-id="a459f-120">Код в перегруженных версий не имеет для проверки в вызывающем коде указано одно или несколько значений для `ParamArray` параметра, или если да, сколько.</span><span class="sxs-lookup"><span data-stu-id="a459f-120">The code in the overloaded versions does not have to test whether the calling code supplied one or more values for the `ParamArray` parameter, or if so, how many.</span></span> <span data-ttu-id="a459f-121">Visual Basic передает управление версию, которая соответствует списку аргументов вызова.</span><span class="sxs-lookup"><span data-stu-id="a459f-121">Visual Basic passes control to the version matching the calling argument list.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a459f-122">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="a459f-122">Compiling the Code</span></span>  
 <span data-ttu-id="a459f-123">Так как процедура с `ParamArray` эквивалентны набор перегруженных версий, нельзя перегрузить такую процедуру со списком параметров, соответствующим любому из этих неявных перегрузок.</span><span class="sxs-lookup"><span data-stu-id="a459f-123">Because a procedure with a `ParamArray` parameter is equivalent to a set of overloaded versions, you cannot overload such a procedure with a parameter list corresponding to any of these implicit overloads.</span></span> <span data-ttu-id="a459f-124">Дополнительные сведения см. в разделе [вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="a459f-124">For more information, see [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="a459f-125">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a459f-125">.NET Framework Security</span></span>  
 <span data-ttu-id="a459f-126">Каждый раз, когда вы имеете дело с массив, который может быть неограниченно большим, есть риск переполнения некоторой внутренней емкости приложения.</span><span class="sxs-lookup"><span data-stu-id="a459f-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="a459f-127">Если вы принимаете массив параметров, следует проверить длину массива, переданного ему вызывающий код и предпринять соответствующие действия, если она слишком велика для приложения.</span><span class="sxs-lookup"><span data-stu-id="a459f-127">If you accept a parameter array, you should test for the length of the array the calling code passed to it, and take appropriate steps if it is too large for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a459f-128">См. также</span><span class="sxs-lookup"><span data-stu-id="a459f-128">See also</span></span>

- [<span data-ttu-id="a459f-129">Процедуры</span><span class="sxs-lookup"><span data-stu-id="a459f-129">Procedures</span></span>](./index.md)
- [<span data-ttu-id="a459f-130">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="a459f-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="a459f-131">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="a459f-131">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="a459f-132">Массивы параметров</span><span class="sxs-lookup"><span data-stu-id="a459f-132">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="a459f-133">Перегрузка процедур</span><span class="sxs-lookup"><span data-stu-id="a459f-133">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="a459f-134">Рекомендации по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="a459f-134">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="a459f-135">Практическое руководство. Определение различных версий процедуры</span><span class="sxs-lookup"><span data-stu-id="a459f-135">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="a459f-136">Практическое руководство. Вызов перегруженной процедуры</span><span class="sxs-lookup"><span data-stu-id="a459f-136">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="a459f-137">Практическое руководство. Перегрузка процедуры, которая принимает один необязательный параметр</span><span class="sxs-lookup"><span data-stu-id="a459f-137">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="a459f-138">Разрешение перегрузки</span><span class="sxs-lookup"><span data-stu-id="a459f-138">Overload Resolution</span></span>](./overload-resolution.md)
