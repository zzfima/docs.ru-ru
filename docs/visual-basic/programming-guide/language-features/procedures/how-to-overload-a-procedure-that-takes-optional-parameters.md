---
title: Практическое руководство. Перегрузка процедуры, которая принимает один необязательный параметр (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], optional parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: 825f9d56-4cde-43fd-993a-b9171717e2eb
ms.openlocfilehash: 1da1d67726a9669477721aabc0aace0119aa7e56
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652900"
---
# <a name="how-to-overload-a-procedure-that-takes-optional-parameters-visual-basic"></a><span data-ttu-id="91d05-102">Практическое руководство. Перегрузка процедуры, которая принимает один необязательный параметр (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="91d05-102">How to: Overload a Procedure that Takes Optional Parameters (Visual Basic)</span></span>
<span data-ttu-id="91d05-103">Если процедура имеет один или несколько [необязательно](../../../../visual-basic/language-reference/modifiers/optional.md) параметров, нельзя определить перегруженную версию, соответствующую любой из ее неявных перегрузок.</span><span class="sxs-lookup"><span data-stu-id="91d05-103">If a procedure has one or more [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameters, you cannot define an overloaded version matching any of its implicit overloads.</span></span> <span data-ttu-id="91d05-104">Дополнительные сведения см. в разделе «Неявные перегрузки для необязательные параметры» в [вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="91d05-104">For more information, see "Implicit Overloads for Optional Parameters" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="one-optional-parameter"></a><span data-ttu-id="91d05-105">Один необязательный параметр</span><span class="sxs-lookup"><span data-stu-id="91d05-105">One Optional Parameter</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-one-optional-parameter"></a><span data-ttu-id="91d05-106">Перегрузка процедуры, которая принимает один необязательный параметр</span><span class="sxs-lookup"><span data-stu-id="91d05-106">To overload a procedure that takes one optional parameter</span></span>  
  
1.  <span data-ttu-id="91d05-107">Запись `Sub` или `Function` оператора объявления, который содержит дополнительный параметр в списке параметров.</span><span class="sxs-lookup"><span data-stu-id="91d05-107">Write a `Sub` or `Function` declaration statement that includes the optional parameter in the parameter list.</span></span> <span data-ttu-id="91d05-108">Не используйте `Optional` ключевое слово в данной перегруженной версии.</span><span class="sxs-lookup"><span data-stu-id="91d05-108">Do not use the `Optional` keyword in this overloaded version.</span></span>  
  
2.  <span data-ttu-id="91d05-109">Перед `Sub` или `Function` ключевого слова with [перегрузки](../../../../visual-basic/language-reference/modifiers/overloads.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="91d05-109">Precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
3.  <span data-ttu-id="91d05-110">Напишите код процедуры, который должен выполняться, когда вызывающий код не предоставляет необязательный аргумент.</span><span class="sxs-lookup"><span data-stu-id="91d05-110">Write the procedure code that should execute when the calling code supplies the optional argument.</span></span>  
  
4.  <span data-ttu-id="91d05-111">Завершите процедуру `End Sub` или `End Function` инструкцию соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="91d05-111">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
5.  <span data-ttu-id="91d05-112">Напишите второй оператор объявления, идентичный первому объявлению, за исключением того, что он не включает необязательный параметр в списке параметров.</span><span class="sxs-lookup"><span data-stu-id="91d05-112">Write a second declaration statement that is identical to the first declaration except that it does not include the optional parameter in the parameter list.</span></span>  
  
6.  <span data-ttu-id="91d05-113">Напишите код процедуры, который должен выполняться, когда вызывающий код не предоставляет необязательный аргумент.</span><span class="sxs-lookup"><span data-stu-id="91d05-113">Write the procedure code that should execute when the calling code does not supply the optional argument.</span></span> <span data-ttu-id="91d05-114">Завершите процедуру `End Sub` или `End Function` инструкцию соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="91d05-114">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
     <span data-ttu-id="91d05-115">В следующем примере показано процедура, определенная с необязательным параметром, аналогичный набор из двух перегруженных процедур и, наконец, примеры и недопустимых перегруженных версий.</span><span class="sxs-lookup"><span data-stu-id="91d05-115">The following example shows a procedure defined with an optional parameter,  an equivalent set of two overloaded procedures, and finally examples of both invalid and valid overloaded versions.</span></span>  
  
     [!code-vb[VbVbcnProcedures#59](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_1.vb)]  
  
     [!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_2.vb)]  
  
     [!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_3.vb)]  
  
## <a name="multiple-optional-parameters"></a><span data-ttu-id="91d05-116">Несколько необязательных параметров</span><span class="sxs-lookup"><span data-stu-id="91d05-116">Multiple Optional Parameters</span></span>  
 <span data-ttu-id="91d05-117">Для процедуры с более чем один необязательный параметр обычно необходимо более двух перегруженных версий.</span><span class="sxs-lookup"><span data-stu-id="91d05-117">For a procedure with more than one optional parameter, you normally need more than two overloaded versions.</span></span> <span data-ttu-id="91d05-118">Например если имеются два необязательных параметра, а вызывающий код может использовать или опустить каждый из них независимо от другого, необходимо четыре перегруженных версий, один для каждой возможной комбинации предоставленных аргументов.</span><span class="sxs-lookup"><span data-stu-id="91d05-118">For example, if there are two optional parameters, and the calling code can supply or omit each one independently of the other, you need four overloaded versions, one for each possible combination of supplied arguments.</span></span>  
  
 <span data-ttu-id="91d05-119">С увеличением числа необязательных параметров увеличивает сложность перегрузки.</span><span class="sxs-lookup"><span data-stu-id="91d05-119">As the number of optional parameters increases, the complexity of the overloading increases.</span></span> <span data-ttu-id="91d05-120">Если некоторые сочетания предоставленных аргументов неприемлемы, для необязательных параметров N требуется 2 ^ N перегруженных версий.</span><span class="sxs-lookup"><span data-stu-id="91d05-120">Unless some combinations of supplied arguments are not acceptable, for N optional parameters you need 2 ^ N overloaded versions.</span></span> <span data-ttu-id="91d05-121">В зависимости от процедуры может оказаться, что ясности логики, японской и корейской лишние усилия для определения всех перегруженных версий.</span><span class="sxs-lookup"><span data-stu-id="91d05-121">Depending on the nature of the procedure, you might find that the clarity of logic justifies the extra effort of defining all the overloaded versions.</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-more-than-one-optional-parameter"></a><span data-ttu-id="91d05-122">Перегрузка процедуры, которая принимает более чем один необязательный параметр</span><span class="sxs-lookup"><span data-stu-id="91d05-122">To overload a procedure that takes more than one optional parameter</span></span>  
  
1.  <span data-ttu-id="91d05-123">Определите, какие комбинации предоставленных необязательные аргументы, приемлемы для логику процедуры.</span><span class="sxs-lookup"><span data-stu-id="91d05-123">Determine which combinations of supplied optional arguments are acceptable to the logic of the procedure.</span></span> <span data-ttu-id="91d05-124">Недопустимое сочетание может возникнуть, если один необязательный параметр зависит от другого.</span><span class="sxs-lookup"><span data-stu-id="91d05-124">An unacceptable combination might arise if one optional parameter depends on another.</span></span> <span data-ttu-id="91d05-125">Например если один параметр принимает имя супруга, а другой принимает возраст супруга, учитывать аргументы возраста, но опустить имя недопустима.</span><span class="sxs-lookup"><span data-stu-id="91d05-125">For example, if one parameter accepts a spouse's name and another accepts the spouse's age, a combination of arguments supplying the age but omitting the name is unacceptable.</span></span>  
  
2.  <span data-ttu-id="91d05-126">Для каждой допустимой комбинации предоставленных необязательных аргументов напишите `Sub` или `Function` инструкцию объявления, определяющую соответствующий список параметров.</span><span class="sxs-lookup"><span data-stu-id="91d05-126">For each acceptable combination of supplied optional arguments, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="91d05-127">Не используйте `Optional` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="91d05-127">Do not use the `Optional` keyword.</span></span>  
  
3.  <span data-ttu-id="91d05-128">В каждое объявление перед `Sub` или `Function` ключевого слова with [перегрузки](../../../../visual-basic/language-reference/modifiers/overloads.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="91d05-128">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
4.  <span data-ttu-id="91d05-129">После каждого объявления напишите код процедуры, который должен выполняться, когда вызывающий код передает список аргументов, соответствующий списку параметров в объявлении.</span><span class="sxs-lookup"><span data-stu-id="91d05-129">Following each declaration, write the procedure code that should execute when the calling code supplies an argument list corresponding to that declaration's parameter list.</span></span>  
  
5.  <span data-ttu-id="91d05-130">Завершите выполнение каждой процедуры с `End Sub` или `End Function` инструкцию соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="91d05-130">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91d05-131">См. также</span><span class="sxs-lookup"><span data-stu-id="91d05-131">See Also</span></span>  
 [<span data-ttu-id="91d05-132">Процедуры</span><span class="sxs-lookup"><span data-stu-id="91d05-132">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="91d05-133">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="91d05-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="91d05-134">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="91d05-134">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="91d05-135">Массивы параметров</span><span class="sxs-lookup"><span data-stu-id="91d05-135">Parameter Arrays</span></span>](./parameter-arrays.md)  
 [<span data-ttu-id="91d05-136">Перегрузка процедур</span><span class="sxs-lookup"><span data-stu-id="91d05-136">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="91d05-137">Рекомендации по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="91d05-137">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="91d05-138">Практическое руководство. Определение различных версий процедуры</span><span class="sxs-lookup"><span data-stu-id="91d05-138">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)  
 [<span data-ttu-id="91d05-139">Практическое руководство. Вызов перегруженной процедуры</span><span class="sxs-lookup"><span data-stu-id="91d05-139">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)  
 [<span data-ttu-id="91d05-140">Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров</span><span class="sxs-lookup"><span data-stu-id="91d05-140">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [<span data-ttu-id="91d05-141">Разрешение перегрузки</span><span class="sxs-lookup"><span data-stu-id="91d05-141">Overload Resolution</span></span>](./overload-resolution.md)
