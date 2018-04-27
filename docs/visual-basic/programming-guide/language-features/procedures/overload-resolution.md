---
title: Разрешение перегрузки (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- overload resolution
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedure overloading [Visual Basic], overload resolution
- signatures [Visual Basic], procedure
- overloads [Visual Basic], resolution
ms.assetid: 766115d1-4352-45fb-859f-6063e0de0ec0
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e62560d853c95bc4bba6ba829d8579ee4388858e
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="overload-resolution-visual-basic"></a><span data-ttu-id="c7408-102">Разрешение перегрузки (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7408-102">Overload Resolution (Visual Basic)</span></span>
<span data-ttu-id="c7408-103">Когда компилятор Visual Basic обнаруживает вызов процедуры, которая определена в нескольких перегруженных версиях, компилятор должен решить, какую из перегрузок метода для вызова.</span><span class="sxs-lookup"><span data-stu-id="c7408-103">When the Visual Basic compiler encounters a call to a procedure that is defined in several overloaded versions, the compiler must decide which of the overloads to call.</span></span> <span data-ttu-id="c7408-104">Это делается путем выполнения следующих шагов:</span><span class="sxs-lookup"><span data-stu-id="c7408-104">It does this by performing the following steps:</span></span>  
  
1.  <span data-ttu-id="c7408-105">**Специальные возможности.**</span><span class="sxs-lookup"><span data-stu-id="c7408-105">**Accessibility.**</span></span> <span data-ttu-id="c7408-106">Это устраняет ни одной перегрузке с уровнем доступа, который предотвращает его вызов вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="c7408-106">It eliminates any overload with an access level that prevents the calling code from calling it.</span></span>  
  
2.  <span data-ttu-id="c7408-107">**Число параметров.**</span><span class="sxs-lookup"><span data-stu-id="c7408-107">**Number of Parameters.**</span></span> <span data-ttu-id="c7408-108">Это устраняет все перегрузку, которая определяет разное число параметров, чем задано в вызове.</span><span class="sxs-lookup"><span data-stu-id="c7408-108">It eliminates any overload that defines a different number of parameters than are supplied in the call.</span></span>  
  
3.  <span data-ttu-id="c7408-109">**Типы данных параметров.**</span><span class="sxs-lookup"><span data-stu-id="c7408-109">**Parameter Data Types.**</span></span> <span data-ttu-id="c7408-110">Компилятор предпочтительнее использует методы экземпляра через методы расширения.</span><span class="sxs-lookup"><span data-stu-id="c7408-110">The compiler gives instance methods preference over extension methods.</span></span> <span data-ttu-id="c7408-111">Если метод экземпляра обнаруживается, что требует только расширяющие преобразования, чтобы сопоставить вызов процедуры, удаляются все методы расширения, и компилятор продолжает использовать только кандидаты метода экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c7408-111">If any instance method is found that requires only widening conversions to match the procedure call, all extension methods are dropped and the compiler continues with only the instance method candidates.</span></span> <span data-ttu-id="c7408-112">Если такой метод экземпляр не найден, он продолжает выполнение экземпляра и методы расширения.</span><span class="sxs-lookup"><span data-stu-id="c7408-112">If no such instance method is found, it continues with both instance and extension methods.</span></span>  
  
     <span data-ttu-id="c7408-113">На этом шаге она также аннулирует ни одной перегрузке, для которых типы данных аргументов вызова не может быть преобразованы в типы параметров, определенные в этой перегрузке.</span><span class="sxs-lookup"><span data-stu-id="c7408-113">In this step, it eliminates any overload for which the data types of the calling arguments cannot be converted to the parameter types defined in the overload.</span></span>  
  
4.  <span data-ttu-id="c7408-114">**Сужающие преобразования.**</span><span class="sxs-lookup"><span data-stu-id="c7408-114">**Narrowing Conversions.**</span></span> <span data-ttu-id="c7408-115">Это устраняет все перегрузка, которая требует сужающего преобразования от типов аргументов вызова в типы определенных параметров.</span><span class="sxs-lookup"><span data-stu-id="c7408-115">It eliminates any overload that requires a narrowing conversion from the calling argument types to the defined parameter types.</span></span> <span data-ttu-id="c7408-116">Это верно ли переключатель проверки типа ([оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) является `On` или `Off`.</span><span class="sxs-lookup"><span data-stu-id="c7408-116">This is true whether the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `On` or `Off`.</span></span>  
  
5.  <span data-ttu-id="c7408-117">**Наименьшее расширение.**</span><span class="sxs-lookup"><span data-stu-id="c7408-117">**Least Widening.**</span></span> <span data-ttu-id="c7408-118">Компилятор считает, что оставшиеся перегрузки парами.</span><span class="sxs-lookup"><span data-stu-id="c7408-118">The compiler considers the remaining overloads in pairs.</span></span> <span data-ttu-id="c7408-119">Для каждой пары он сравнивает типы данных определенных параметров.</span><span class="sxs-lookup"><span data-stu-id="c7408-119">For each pair, it compares the data types of the defined parameters.</span></span> <span data-ttu-id="c7408-120">Если в одну из перегрузок все типы расширяются до соответствующих типов в другой, компилятор исключает последнюю.</span><span class="sxs-lookup"><span data-stu-id="c7408-120">If the types in one of the overloads all widen to the corresponding types in the other, the compiler eliminates the latter.</span></span> <span data-ttu-id="c7408-121">Другими словами он остается перегрузка, которая требует наименьший объем расширения.</span><span class="sxs-lookup"><span data-stu-id="c7408-121">That is, it retains the overload that requires the least amount of widening.</span></span>  
  
6.  <span data-ttu-id="c7408-122">**Единственный вариант.**</span><span class="sxs-lookup"><span data-stu-id="c7408-122">**Single Candidate.**</span></span> <span data-ttu-id="c7408-123">Компилятор продолжает рассматривать перегрузки попарно до только одна перегрузка остается, и он разрешает вызов этой перегрузки.</span><span class="sxs-lookup"><span data-stu-id="c7408-123">It continues considering overloads in pairs until only one overload remains, and it resolves the call to that overload.</span></span> <span data-ttu-id="c7408-124">Если компилятор не может уменьшить перегрузки единственный вариант, он создает ошибку.</span><span class="sxs-lookup"><span data-stu-id="c7408-124">If the compiler cannot reduce the overloads to a single candidate, it generates an error.</span></span>  
  
 <span data-ttu-id="c7408-125">На следующем рисунке процесс, который определяет, какой набор перегруженных версий для вызова.</span><span class="sxs-lookup"><span data-stu-id="c7408-125">The following illustration shows the process that determines which of a set of overloaded versions to call.</span></span>  
  
 <span data-ttu-id="c7408-126">![Схема потока перегруженного процесса разрешения](./media/overloadres.gif "OverloadRes")</span><span class="sxs-lookup"><span data-stu-id="c7408-126">![Flow diagram of overload resolution process](./media/overloadres.gif "OverloadRes")</span></span>  
<span data-ttu-id="c7408-127">Для перегруженных версий, разрешение</span><span class="sxs-lookup"><span data-stu-id="c7408-127">Resolving among overloaded versions</span></span>  
  
 <span data-ttu-id="c7408-128">Следующий пример иллюстрирует этот процесс разрешения перегрузки.</span><span class="sxs-lookup"><span data-stu-id="c7408-128">The following example illustrates this overload resolution process.</span></span>  
  
 [!code-vb[VbVbcnProcedures#62](./codesnippet/VisualBasic/overload-resolution_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#63](./codesnippet/VisualBasic/overload-resolution_2.vb)]  
  
 <span data-ttu-id="c7408-129">В первом вызове компилятор устраняет первую перегрузку, так как тип первого аргумента (`Short`) сужается к типу соответствующего параметра (`Byte`).</span><span class="sxs-lookup"><span data-stu-id="c7408-129">In the first call, the compiler eliminates the first overload because the type of the first argument (`Short`) narrows to the type of the corresponding parameter (`Byte`).</span></span> <span data-ttu-id="c7408-130">Затем исключаются третья перегрузка, так как каждый тип аргумента во второй перегрузке (`Short` и `Single`) может быть расширен до соответствующего типа в третьей перегрузке (`Integer` и `Single`).</span><span class="sxs-lookup"><span data-stu-id="c7408-130">It then eliminates the third overload because each argument type in the second overload (`Short` and `Single`) widens to the corresponding type in the third overload (`Integer` and `Single`).</span></span> <span data-ttu-id="c7408-131">Вторая перегрузка требует меньшего расширения, поэтому компилятор использует его для вызова.</span><span class="sxs-lookup"><span data-stu-id="c7408-131">The second overload requires less widening, so the compiler uses it for the call.</span></span>  
  
 <span data-ttu-id="c7408-132">Во втором вызове компилятор не может устранить зависимости от сужения перегрузок.</span><span class="sxs-lookup"><span data-stu-id="c7408-132">In the second call, the compiler cannot eliminate any of the overloads on the basis of narrowing.</span></span> <span data-ttu-id="c7408-133">Она также аннулирует третьей перегрузке по той же причине, что и первый вызов, так как он может вызвать вторую перегрузку с меньшим расширением типов аргументов.</span><span class="sxs-lookup"><span data-stu-id="c7408-133">It eliminates the third overload for the same reason as in the first call, because it can call the second overload with less widening of the argument types.</span></span> <span data-ttu-id="c7408-134">Однако компилятор не может разрешить между первой и второй перегрузок.</span><span class="sxs-lookup"><span data-stu-id="c7408-134">However, the compiler cannot resolve between the first and second overloads.</span></span> <span data-ttu-id="c7408-135">Каждая имеет один определенный тип параметра, может быть расширен до соответствующего типа в другой (`Byte` для `Short`, но `Single` для `Double`).</span><span class="sxs-lookup"><span data-stu-id="c7408-135">Each has one defined parameter type that widens to the corresponding type in the other (`Byte` to `Short`, but `Single` to `Double`).</span></span> <span data-ttu-id="c7408-136">Поэтому компилятор создает ошибку разрешения перегрузки.</span><span class="sxs-lookup"><span data-stu-id="c7408-136">The compiler therefore generates an overload resolution error.</span></span>  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a><span data-ttu-id="c7408-137">Перегрузка необязательных аргументов и массива аргументов</span><span class="sxs-lookup"><span data-stu-id="c7408-137">Overloaded Optional and ParamArray Arguments</span></span>  
 <span data-ttu-id="c7408-138">Если две перегрузки процедуры имеют одинаковые сигнатуры, за исключением того, что последний параметр объявляется [необязательно](../../../../visual-basic/language-reference/modifiers/optional.md) в одном и [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) в другой, компилятор разрешает вызов процедуры, как выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c7408-138">If two overloads of a procedure have identical signatures except that the last parameter is declared [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) in one and [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) in the other, the compiler resolves a call to that procedure as follows:</span></span>  
  
|<span data-ttu-id="c7408-139">Если задан как последний аргумент при вызове</span><span class="sxs-lookup"><span data-stu-id="c7408-139">If the call supplies the last argument as</span></span>|<span data-ttu-id="c7408-140">Компилятор вызывает перегрузку, объявление аргумента в качестве последнего</span><span class="sxs-lookup"><span data-stu-id="c7408-140">The compiler resolves the call to the overload declaring the last argument as</span></span>|  
|---|---|  
|<span data-ttu-id="c7408-141">Нет значения (аргумент опущен)</span><span class="sxs-lookup"><span data-stu-id="c7408-141">No value (argument omitted)</span></span>|`Optional`|  
|<span data-ttu-id="c7408-142">Одно значение</span><span class="sxs-lookup"><span data-stu-id="c7408-142">A single value</span></span>|`Optional`|  
|<span data-ttu-id="c7408-143">Два или несколько значений в список с разделителями запятыми</span><span class="sxs-lookup"><span data-stu-id="c7408-143">Two or more values in a comma-separated list</span></span>|`ParamArray`|  
|<span data-ttu-id="c7408-144">Массив любой длины (включая пустой массив)</span><span class="sxs-lookup"><span data-stu-id="c7408-144">An array of any length (including an empty array)</span></span>|`ParamArray`|  
  
## <a name="see-also"></a><span data-ttu-id="c7408-145">См. также</span><span class="sxs-lookup"><span data-stu-id="c7408-145">See Also</span></span>  
 [<span data-ttu-id="c7408-146">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="c7408-146">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="c7408-147">Массивы параметров</span><span class="sxs-lookup"><span data-stu-id="c7408-147">Parameter Arrays</span></span>](./parameter-arrays.md)  
 [<span data-ttu-id="c7408-148">Перегрузка процедур</span><span class="sxs-lookup"><span data-stu-id="c7408-148">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="c7408-149">Рекомендации по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="c7408-149">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="c7408-150">Практическое руководство. Определение различных версий процедуры</span><span class="sxs-lookup"><span data-stu-id="c7408-150">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)  
 [<span data-ttu-id="c7408-151">Практическое руководство. Вызов перегруженной процедуры</span><span class="sxs-lookup"><span data-stu-id="c7408-151">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)  
 [<span data-ttu-id="c7408-152">Практическое руководство. Перегрузка процедуры, которая принимает один необязательный параметр</span><span class="sxs-lookup"><span data-stu-id="c7408-152">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [<span data-ttu-id="c7408-153">Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров</span><span class="sxs-lookup"><span data-stu-id="c7408-153">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [<span data-ttu-id="c7408-154">Вопросы, связанные с перегрузкой процедур</span><span class="sxs-lookup"><span data-stu-id="c7408-154">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)  
 [<span data-ttu-id="c7408-155">Перегрузки</span><span class="sxs-lookup"><span data-stu-id="c7408-155">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [<span data-ttu-id="c7408-156">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="c7408-156">Extension Methods</span></span>](./extension-methods.md)
