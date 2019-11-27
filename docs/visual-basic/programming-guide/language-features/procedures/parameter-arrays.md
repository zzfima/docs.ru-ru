---
title: Массивы параметров
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
ms.openlocfilehash: ffb532fbac70b9aa8ab210450e4d9207f5e0291f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351127"
---
# <a name="parameter-arrays-visual-basic"></a><span data-ttu-id="bfdbd-102">Массивы параметров (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bfdbd-102">Parameter Arrays (Visual Basic)</span></span>
<span data-ttu-id="bfdbd-103">Как правило, процедуру нельзя вызывать с дополнительными аргументами, чем указано в объявлении процедуры.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-103">Usually, you cannot call a procedure with more arguments than the procedure declaration specifies.</span></span> <span data-ttu-id="bfdbd-104">Если требуется неопределенное число аргументов, можно объявить *массив параметров*, который позволяет процедуре принимать массив значений для параметра.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-104">When you need an indefinite number of arguments, you can declare a *parameter array*, which allows a procedure to accept an array of values for a parameter.</span></span> <span data-ttu-id="bfdbd-105">При определении процедуры вам не нужно было узнать число элементов в массиве параметров.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-105">You do not have to know the number of elements in the parameter array when you define the procedure.</span></span> <span data-ttu-id="bfdbd-106">Размер массива определяется отдельно при каждом вызове процедуры.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-106">The array size is determined individually by each call to the procedure.</span></span>  
  
## <a name="declaring-a-paramarray"></a><span data-ttu-id="bfdbd-107">Объявление ParamArray</span><span class="sxs-lookup"><span data-stu-id="bfdbd-107">Declaring a ParamArray</span></span>  
 <span data-ttu-id="bfdbd-108">Используйте ключевое слово [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) для обозначения массива параметров в списке параметров.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-108">You use the [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) keyword to denote a parameter array in the parameter list.</span></span> <span data-ttu-id="bfdbd-109">Действуют следующие правила.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-109">The following rules apply:</span></span>  
  
- <span data-ttu-id="bfdbd-110">Процедура может определять только один массив параметров и должен быть последним параметром в определении процедуры.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-110">A procedure can define only one parameter array, and it must be the last parameter in the procedure definition.</span></span>  
  
- <span data-ttu-id="bfdbd-111">Массив параметров должен передаваться по значению.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-111">The parameter array must be passed by value.</span></span> <span data-ttu-id="bfdbd-112">Рекомендуется явно включать в определение процедуры ключевое слово [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) .</span><span class="sxs-lookup"><span data-stu-id="bfdbd-112">It is good programming practice to explicitly include the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) keyword in the procedure definition.</span></span>  
  
- <span data-ttu-id="bfdbd-113">Массив параметров является автоматически необязательным.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-113">The parameter array is automatically optional.</span></span> <span data-ttu-id="bfdbd-114">Его значением по умолчанию является пустой одномерный массив типа элемента массива параметров.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-114">Its default value is an empty one-dimensional array of the parameter array's element type.</span></span>  
  
- <span data-ttu-id="bfdbd-115">Должны быть необходимы все параметры, предшествующие массиву параметров.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-115">All parameters preceding the parameter array must be required.</span></span> <span data-ttu-id="bfdbd-116">Массив параметров должен быть единственным необязательным параметром.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-116">The parameter array must be the only optional parameter.</span></span>  
  
## <a name="calling-a-paramarray"></a><span data-ttu-id="bfdbd-117">Вызов метода ParamArray</span><span class="sxs-lookup"><span data-stu-id="bfdbd-117">Calling a ParamArray</span></span>  
 <span data-ttu-id="bfdbd-118">При вызове процедуры, определяющей массив параметров, можно указать аргумент одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="bfdbd-118">When you call a procedure that defines a parameter array, you can supply the argument in any one of the following ways:</span></span>  
  
- <span data-ttu-id="bfdbd-119">Нет, то есть можно опустить аргумент [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) .</span><span class="sxs-lookup"><span data-stu-id="bfdbd-119">Nothing — that is, you can omit the [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) argument.</span></span> <span data-ttu-id="bfdbd-120">В этом случае в процедуру передается пустой массив.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-120">In this case, an empty array is passed to the procedure.</span></span> <span data-ttu-id="bfdbd-121">При явном передаче ключевого слова [Nothing](../../../../visual-basic/language-reference/nothing.md) в процедуру передается пустой массив, который может привести к NullReferenceException, если вызываемая процедура не проверяет это условие.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-121">If you explicitly pass the [Nothing](../../../../visual-basic/language-reference/nothing.md) keyword, a null array is passed to the procedure and may result in a NullReferenceException if the called procedure does not check for this condition.</span></span>
  
- <span data-ttu-id="bfdbd-122">Список произвольного числа аргументов, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-122">A list of an arbitrary number of arguments, separated by commas.</span></span> <span data-ttu-id="bfdbd-123">Тип данных каждого аргумента должен быть неявно преобразован в тип элемента `ParamArray`.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-123">The data type of each argument must be implicitly convertible to the `ParamArray` element type.</span></span>  
  
- <span data-ttu-id="bfdbd-124">Массив с тем же типом элемента, что и у типа элемента массива параметров.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-124">An array with the same element type as the parameter array's element type.</span></span>  
  
 <span data-ttu-id="bfdbd-125">Во всех случаях код в процедуре обрабатывает массив параметров как одномерный массив с элементами того же типа данных, что и тип данных `ParamArray`.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-125">In all cases, the code within the procedure treats the parameter array as a one-dimensional array with elements of the same data type as the `ParamArray` data type.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="bfdbd-126">Всякий раз при работе с массивом, который может быть неограниченным большим, существует риск перегрузки внутренней емкости приложения.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="bfdbd-127">Если вы принимаете массив параметров, следует проверить размер массива, которому был передан вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-127">If you accept a parameter array, you should test for the size of the array that the calling code passed to it.</span></span> <span data-ttu-id="bfdbd-128">Выполните соответствующие действия, если оно слишком велико для вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-128">Take appropriate steps if it is too large for your application.</span></span> <span data-ttu-id="bfdbd-129">Дополнительные сведения см. в статье [Arrays (C++/CLI and C++/CX)](../../../../visual-basic/programming-guide/language-features/arrays/index.md) (Массивы (C++/CLI и C++/CX)).</span><span class="sxs-lookup"><span data-stu-id="bfdbd-129">For more information, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bfdbd-130">Пример</span><span class="sxs-lookup"><span data-stu-id="bfdbd-130">Example</span></span>  
 <span data-ttu-id="bfdbd-131">В следующем примере определяется и вызывается функция, `calcSum`.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-131">The following example defines and calls the function `calcSum`.</span></span> <span data-ttu-id="bfdbd-132">Модификатор `ParamArray` для параметра `args` позволяет функции принимать переменное число аргументов.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-132">The `ParamArray` modifier for the parameter `args` enables the function to accept a variable number of arguments.</span></span>  
  
 [!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]  
  
 <span data-ttu-id="bfdbd-133">В следующем примере определяется процедура с массивом параметров и выводятся значения всех элементов массива, переданных в массив параметров.</span><span class="sxs-lookup"><span data-stu-id="bfdbd-133">The following example defines a procedure with a parameter array, and outputs the values of all the array elements passed to the parameter array.</span></span>  
  
 [!code-vb[VbVbcnProcedures#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#48)]  
  
 [!code-vb[VbVbcnProcedures#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#49)]  
  
## <a name="see-also"></a><span data-ttu-id="bfdbd-134">См. также</span><span class="sxs-lookup"><span data-stu-id="bfdbd-134">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [<span data-ttu-id="bfdbd-135">Процедуры</span><span class="sxs-lookup"><span data-stu-id="bfdbd-135">Procedures</span></span>](./index.md)
- [<span data-ttu-id="bfdbd-136">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="bfdbd-136">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="bfdbd-137">Передача аргументов по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="bfdbd-137">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="bfdbd-138">Передача аргументов по позиции и по имени</span><span class="sxs-lookup"><span data-stu-id="bfdbd-138">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="bfdbd-139">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="bfdbd-139">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="bfdbd-140">Перегрузка процедур</span><span class="sxs-lookup"><span data-stu-id="bfdbd-140">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="bfdbd-141">Массивы</span><span class="sxs-lookup"><span data-stu-id="bfdbd-141">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="bfdbd-142">Optional</span><span class="sxs-lookup"><span data-stu-id="bfdbd-142">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)
