---
title: Массивы параметров (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- parameter arrays [Visual Basic], about parameter arrays
- ParamArray keyword [Visual Basic], parameter arrays
- Visual Basic code, procedures
- parameters [Visual Basic], parameter arrays
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], indefinite number of argument values
- arrays [Visual Basic], parameter arrays
ms.assetid: c43edfae-9114-4096-9ebc-8c5c957a1067
ms.openlocfilehash: a91da0d9e16ff11fdd4980588fee64b3e4a603c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="parameter-arrays-visual-basic"></a><span data-ttu-id="faa75-102">Массивы параметров (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="faa75-102">Parameter Arrays (Visual Basic)</span></span>
<span data-ttu-id="faa75-103">Как правило не может вызвать процедуру с большим числом аргументов, чем в объявлении процедуры указано.</span><span class="sxs-lookup"><span data-stu-id="faa75-103">Usually, you cannot call a procedure with more arguments than the procedure declaration specifies.</span></span> <span data-ttu-id="faa75-104">Если неопределенное число аргументов, можно объявить *массив параметров*, который позволяет процедуре принять массив значений для параметра.</span><span class="sxs-lookup"><span data-stu-id="faa75-104">When you need an indefinite number of arguments, you can declare a *parameter array*, which allows a procedure to accept an array of values for a parameter.</span></span> <span data-ttu-id="faa75-105">Необходимо знать количество элементов в массиве параметров, при определении процедуры.</span><span class="sxs-lookup"><span data-stu-id="faa75-105">You do not have to know the number of elements in the parameter array when you define the procedure.</span></span> <span data-ttu-id="faa75-106">Размер массива определяется отдельно при каждом вызове процедуры.</span><span class="sxs-lookup"><span data-stu-id="faa75-106">The array size is determined individually by each call to the procedure.</span></span>  
  
## <a name="declaring-a-paramarray"></a><span data-ttu-id="faa75-107">Объявление ParamArray</span><span class="sxs-lookup"><span data-stu-id="faa75-107">Declaring a ParamArray</span></span>  
 <span data-ttu-id="faa75-108">Вы используете [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) ключевое слово для обозначения массива параметров в списке параметров.</span><span class="sxs-lookup"><span data-stu-id="faa75-108">You use the [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) keyword to denote a parameter array in the parameter list.</span></span> <span data-ttu-id="faa75-109">Действуют следующие правила.</span><span class="sxs-lookup"><span data-stu-id="faa75-109">The following rules apply:</span></span>  
  
-   <span data-ttu-id="faa75-110">Процедура может определять только один массив параметров, и он должен быть последним параметром в определении процедуры.</span><span class="sxs-lookup"><span data-stu-id="faa75-110">A procedure can define only one parameter array, and it must be the last parameter in the procedure definition.</span></span>  
  
-   <span data-ttu-id="faa75-111">Массив параметров должен передаваться по значению.</span><span class="sxs-lookup"><span data-stu-id="faa75-111">The parameter array must be passed by value.</span></span> <span data-ttu-id="faa75-112">Это целесообразно, чтобы явно включить [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) ключевого слова в определении процедуры.</span><span class="sxs-lookup"><span data-stu-id="faa75-112">It is good programming practice to explicitly include the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) keyword in the procedure definition.</span></span>  
  
-   <span data-ttu-id="faa75-113">Массив параметров автоматически является необязательным.</span><span class="sxs-lookup"><span data-stu-id="faa75-113">The parameter array is automatically optional.</span></span> <span data-ttu-id="faa75-114">Значением по умолчанию является пустой одномерный массив типа элемента в массиве параметров.</span><span class="sxs-lookup"><span data-stu-id="faa75-114">Its default value is an empty one-dimensional array of the parameter array's element type.</span></span>  
  
-   <span data-ttu-id="faa75-115">Все аргументы, предшествующие в массиве параметров должны быть обязательными.</span><span class="sxs-lookup"><span data-stu-id="faa75-115">All parameters preceding the parameter array must be required.</span></span> <span data-ttu-id="faa75-116">Массив параметров должен быть единственным необязательным параметром.</span><span class="sxs-lookup"><span data-stu-id="faa75-116">The parameter array must be the only optional parameter.</span></span>  
  
## <a name="calling-a-paramarray"></a><span data-ttu-id="faa75-117">Вызов ParamArray</span><span class="sxs-lookup"><span data-stu-id="faa75-117">Calling a ParamArray</span></span>  
 <span data-ttu-id="faa75-118">При вызове процедуры, определяющей массив параметров, можно указать аргумент одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="faa75-118">When you call a procedure that defines a parameter array, you can supply the argument in any one of the following ways:</span></span>  
  
-   <span data-ttu-id="faa75-119">Nothing, то есть можно опустить [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) аргумент.</span><span class="sxs-lookup"><span data-stu-id="faa75-119">Nothing — that is, you can omit the [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) argument.</span></span> <span data-ttu-id="faa75-120">В этом случае процедуре передается пустой массив.</span><span class="sxs-lookup"><span data-stu-id="faa75-120">In this case, an empty array is passed to the procedure.</span></span> <span data-ttu-id="faa75-121">Можно также передать [ничего](../../../../visual-basic/language-reference/nothing.md) ключевое слово с такой же эффект.</span><span class="sxs-lookup"><span data-stu-id="faa75-121">You can also pass the [Nothing](../../../../visual-basic/language-reference/nothing.md) keyword, with the same effect.</span></span>  
  
-   <span data-ttu-id="faa75-122">Список произвольное число аргументов, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="faa75-122">A list of an arbitrary number of arguments, separated by commas.</span></span> <span data-ttu-id="faa75-123">Тип данных каждого аргумента должен быть неявно преобразовываться в `ParamArray` тип элемента.</span><span class="sxs-lookup"><span data-stu-id="faa75-123">The data type of each argument must be implicitly convertible to the `ParamArray` element type.</span></span>  
  
-   <span data-ttu-id="faa75-124">Массив с тем же типом элемента, что тип элемента в массиве параметров.</span><span class="sxs-lookup"><span data-stu-id="faa75-124">An array with the same element type as the parameter array's element type.</span></span>  
  
 <span data-ttu-id="faa75-125">Во всех случаях код в процедуре рассматривает массив параметров как одномерный массив с элементами того же типа данных как `ParamArray` тип данных.</span><span class="sxs-lookup"><span data-stu-id="faa75-125">In all cases, the code within the procedure treats the parameter array as a one-dimensional array with elements of the same data type as the `ParamArray` data type.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="faa75-126">При работе с которой неограниченно большим массивом есть риск переполнения некоторой внутренней емкости приложения.</span><span class="sxs-lookup"><span data-stu-id="faa75-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="faa75-127">Если вы принимаете массив параметров, следует проверить размер массива, которое передано вызывающему коду.</span><span class="sxs-lookup"><span data-stu-id="faa75-127">If you accept a parameter array, you should test for the size of the array that the calling code passed to it.</span></span> <span data-ttu-id="faa75-128">Примите необходимые меры, если она слишком велика для приложения.</span><span class="sxs-lookup"><span data-stu-id="faa75-128">Take appropriate steps if it is too large for your application.</span></span> <span data-ttu-id="faa75-129">Дополнительные сведения см. в разделе [массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="faa75-129">For more information, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="faa75-130">Пример</span><span class="sxs-lookup"><span data-stu-id="faa75-130">Example</span></span>  
 <span data-ttu-id="faa75-131">Следующий пример определяет и вызывает функцию `calcSum`.</span><span class="sxs-lookup"><span data-stu-id="faa75-131">The following example defines and calls the function `calcSum`.</span></span> <span data-ttu-id="faa75-132">`ParamArray` Модификатор параметра `args` разрешает функции принимать переменное число аргументов.</span><span class="sxs-lookup"><span data-stu-id="faa75-132">The `ParamArray` modifier for the parameter `args` enables the function to accept a variable number of arguments.</span></span>  
  
 [!code-vb[VbVbalrStatements#26](../../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-arrays_1.vb)]  
  
 <span data-ttu-id="faa75-133">Следующий пример определяет процедуру с массивом параметров и выводит значения всех элементов массива, передаваемый в массиве параметров.</span><span class="sxs-lookup"><span data-stu-id="faa75-133">The following example defines a procedure with a parameter array, and outputs the values of all the array elements passed to the parameter array.</span></span>  
  
 [!code-vb[VbVbcnProcedures#48](./codesnippet/VisualBasic/parameter-arrays_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#49](./codesnippet/VisualBasic/parameter-arrays_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="faa75-134">См. также</span><span class="sxs-lookup"><span data-stu-id="faa75-134">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Information.UBound%2A>  
 [<span data-ttu-id="faa75-135">Процедуры</span><span class="sxs-lookup"><span data-stu-id="faa75-135">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="faa75-136">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="faa75-136">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="faa75-137">Передача аргументов по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="faa75-137">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="faa75-138">Передача аргументов по позиции и по имени</span><span class="sxs-lookup"><span data-stu-id="faa75-138">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="faa75-139">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="faa75-139">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="faa75-140">Перегрузка процедур</span><span class="sxs-lookup"><span data-stu-id="faa75-140">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="faa75-141">Массивы</span><span class="sxs-lookup"><span data-stu-id="faa75-141">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="faa75-142">Необязательный</span><span class="sxs-lookup"><span data-stu-id="faa75-142">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)
