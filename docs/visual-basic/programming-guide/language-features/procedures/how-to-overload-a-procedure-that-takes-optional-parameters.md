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
ms.openlocfilehash: 52e31ba2f9d2f5cf87a5597a3c8d639816a75535
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56972668"
---
# <a name="how-to-overload-a-procedure-that-takes-optional-parameters-visual-basic"></a><span data-ttu-id="d6d29-102">Практическое руководство. Перегрузка процедуры, которая принимает один необязательный параметр (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6d29-102">How to: Overload a Procedure that Takes Optional Parameters (Visual Basic)</span></span>
<span data-ttu-id="d6d29-103">Если процедура имеет один или несколько [необязательно](../../../../visual-basic/language-reference/modifiers/optional.md) параметров, нельзя определить перегруженную версию, соответствующую любой из ее неявных перегрузок.</span><span class="sxs-lookup"><span data-stu-id="d6d29-103">If a procedure has one or more [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameters, you cannot define an overloaded version matching any of its implicit overloads.</span></span> <span data-ttu-id="d6d29-104">Дополнительные сведения см. в разделе «Неявные перегрузки для необязательные параметры» в [вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="d6d29-104">For more information, see "Implicit Overloads for Optional Parameters" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="one-optional-parameter"></a><span data-ttu-id="d6d29-105">Один необязательный параметр</span><span class="sxs-lookup"><span data-stu-id="d6d29-105">One Optional Parameter</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-one-optional-parameter"></a><span data-ttu-id="d6d29-106">Перегрузка процедуры, которая принимает один необязательный параметр</span><span class="sxs-lookup"><span data-stu-id="d6d29-106">To overload a procedure that takes one optional parameter</span></span>  
  
1.  <span data-ttu-id="d6d29-107">Запись `Sub` или `Function` оператора объявления, которая включает необязательный параметр в списке параметров.</span><span class="sxs-lookup"><span data-stu-id="d6d29-107">Write a `Sub` or `Function` declaration statement that includes the optional parameter in the parameter list.</span></span> <span data-ttu-id="d6d29-108">Не используйте `Optional` ключевое слово в данной перегруженной версии.</span><span class="sxs-lookup"><span data-stu-id="d6d29-108">Do not use the `Optional` keyword in this overloaded version.</span></span>  
  
2.  <span data-ttu-id="d6d29-109">Перед `Sub` или `Function` ключевого слова with [перегружает](../../../../visual-basic/language-reference/modifiers/overloads.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="d6d29-109">Precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
3.  <span data-ttu-id="d6d29-110">Напишите код процедуры, который должен выполняться, когда вызывающий код предоставляет необязательный аргумент.</span><span class="sxs-lookup"><span data-stu-id="d6d29-110">Write the procedure code that should execute when the calling code supplies the optional argument.</span></span>  
  
4.  <span data-ttu-id="d6d29-111">Завершите процедуру `End Sub` или `End Function` инструкцию соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="d6d29-111">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
5.  <span data-ttu-id="d6d29-112">Напишите вторую инструкцию объявления, идентичный первому объявлению, за исключением того, чтобы он включал необязательного параметра в списке параметров.</span><span class="sxs-lookup"><span data-stu-id="d6d29-112">Write a second declaration statement that is identical to the first declaration except that it does not include the optional parameter in the parameter list.</span></span>  
  
6.  <span data-ttu-id="d6d29-113">Напишите код процедуры, который должен выполняться, когда вызывающий код не предоставляет необязательный аргумент.</span><span class="sxs-lookup"><span data-stu-id="d6d29-113">Write the procedure code that should execute when the calling code does not supply the optional argument.</span></span> <span data-ttu-id="d6d29-114">Завершите процедуру `End Sub` или `End Function` инструкцию соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="d6d29-114">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
     <span data-ttu-id="d6d29-115">В следующем примере показана процедура, определенная с необязательным параметром, аналогичный набор две перегруженные процедуры и, наконец, примеры недопустимых и допустимых перегруженных версий.</span><span class="sxs-lookup"><span data-stu-id="d6d29-115">The following example shows a procedure defined with an optional parameter,  an equivalent set of two overloaded procedures, and finally examples of both invalid and valid overloaded versions.</span></span>  
  
     [!code-vb[VbVbcnProcedures#59](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#59)]  
  
     [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
     [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
## <a name="multiple-optional-parameters"></a><span data-ttu-id="d6d29-116">Несколько необязательных параметров</span><span class="sxs-lookup"><span data-stu-id="d6d29-116">Multiple Optional Parameters</span></span>  
 <span data-ttu-id="d6d29-117">Для процедуры с более чем один необязательный параметр обычно необходимо более двух перегруженных версий.</span><span class="sxs-lookup"><span data-stu-id="d6d29-117">For a procedure with more than one optional parameter, you normally need more than two overloaded versions.</span></span> <span data-ttu-id="d6d29-118">Например если существуют два необязательных параметра, а вызывающий код может использовать или опустить каждый из них независимо от другого, требуется четыре перегруженные версии, по одному для каждого из возможных сочетаний предоставленных аргументов.</span><span class="sxs-lookup"><span data-stu-id="d6d29-118">For example, if there are two optional parameters, and the calling code can supply or omit each one independently of the other, you need four overloaded versions, one for each possible combination of supplied arguments.</span></span>  
  
 <span data-ttu-id="d6d29-119">С увеличением числа необязательных параметров, повышает сложность перегрузки.</span><span class="sxs-lookup"><span data-stu-id="d6d29-119">As the number of optional parameters increases, the complexity of the overloading increases.</span></span> <span data-ttu-id="d6d29-120">Если некоторые сочетания указанные аргументы недопустимы, для N необязательных параметров требуется 2 ^ N перегруженных версий.</span><span class="sxs-lookup"><span data-stu-id="d6d29-120">Unless some combinations of supplied arguments are not acceptable, for N optional parameters you need 2 ^ N overloaded versions.</span></span> <span data-ttu-id="d6d29-121">В зависимости от природы процедуры может оказаться, что ясности логики по правому краю лишние усилия для определения всех перегруженных версий.</span><span class="sxs-lookup"><span data-stu-id="d6d29-121">Depending on the nature of the procedure, you might find that the clarity of logic justifies the extra effort of defining all the overloaded versions.</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-more-than-one-optional-parameter"></a><span data-ttu-id="d6d29-122">Перегрузка процедуры, которая принимает более чем один необязательный параметр</span><span class="sxs-lookup"><span data-stu-id="d6d29-122">To overload a procedure that takes more than one optional parameter</span></span>  
  
1.  <span data-ttu-id="d6d29-123">Определите, какие комбинации предоставленных аргументов необязательно являются допустимыми в логику процедуры.</span><span class="sxs-lookup"><span data-stu-id="d6d29-123">Determine which combinations of supplied optional arguments are acceptable to the logic of the procedure.</span></span> <span data-ttu-id="d6d29-124">Недопустимое сочетание может возникнуть, если один необязательный параметр зависит от другого.</span><span class="sxs-lookup"><span data-stu-id="d6d29-124">An unacceptable combination might arise if one optional parameter depends on another.</span></span> <span data-ttu-id="d6d29-125">Например если один параметр принимает имя супруга, а другой принимает возраст супруга, сочетание аргументов возраста, но при пропуске названия неприемлем.</span><span class="sxs-lookup"><span data-stu-id="d6d29-125">For example, if one parameter accepts a spouse's name and another accepts the spouse's age, a combination of arguments supplying the age but omitting the name is unacceptable.</span></span>  
  
2.  <span data-ttu-id="d6d29-126">Для каждой допустимой комбинации предоставленных аргументов необязательно писать `Sub` или `Function` оператора объявления, который определяет соответствующий список параметров.</span><span class="sxs-lookup"><span data-stu-id="d6d29-126">For each acceptable combination of supplied optional arguments, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="d6d29-127">Не используйте `Optional` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="d6d29-127">Do not use the `Optional` keyword.</span></span>  
  
3.  <span data-ttu-id="d6d29-128">В каждое объявление перед `Sub` или `Function` ключевого слова with [перегружает](../../../../visual-basic/language-reference/modifiers/overloads.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="d6d29-128">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
4.  <span data-ttu-id="d6d29-129">После каждого объявления напишите код процедуры, который должен выполняться, когда вызывающий код предоставляет список аргументов, соответствующий списку параметров в объявлении.</span><span class="sxs-lookup"><span data-stu-id="d6d29-129">Following each declaration, write the procedure code that should execute when the calling code supplies an argument list corresponding to that declaration's parameter list.</span></span>  
  
5.  <span data-ttu-id="d6d29-130">Завершите выполнение каждой процедуры с `End Sub` или `End Function` инструкцию соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="d6d29-130">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6d29-131">См. также</span><span class="sxs-lookup"><span data-stu-id="d6d29-131">See also</span></span>
- [<span data-ttu-id="d6d29-132">Процедуры</span><span class="sxs-lookup"><span data-stu-id="d6d29-132">Procedures</span></span>](./index.md)
- [<span data-ttu-id="d6d29-133">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="d6d29-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="d6d29-134">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="d6d29-134">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="d6d29-135">Массивы параметров</span><span class="sxs-lookup"><span data-stu-id="d6d29-135">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="d6d29-136">Перегрузка процедур</span><span class="sxs-lookup"><span data-stu-id="d6d29-136">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="d6d29-137">Рекомендации по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="d6d29-137">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="d6d29-138">Практическое руководство. Определение различных версий процедуры</span><span class="sxs-lookup"><span data-stu-id="d6d29-138">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="d6d29-139">Практическое руководство. Вызов перегруженной процедуры</span><span class="sxs-lookup"><span data-stu-id="d6d29-139">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="d6d29-140">Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров</span><span class="sxs-lookup"><span data-stu-id="d6d29-140">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="d6d29-141">Разрешение перегрузки</span><span class="sxs-lookup"><span data-stu-id="d6d29-141">Overload Resolution</span></span>](./overload-resolution.md)
