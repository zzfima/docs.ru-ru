---
title: "Практическое руководство. Инициализация переменной массива в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], initializing
- arrays [Visual Basic], variables
- arrays [Visual Basic], initializing
- arrays [Visual Basic], declaring
ms.assetid: aadd7a60-7ca4-4608-b986-091f19e7fc10
caps.latest.revision: "42"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3ccdbed601d3fa87acb0833bc153c199b17a4eba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-initialize-an-array-variable-in-visual-basic"></a><span data-ttu-id="947bb-102">Практическое руководство. Инициализация переменной массива в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="947bb-102">How to: Initialize an Array Variable in Visual Basic</span></span>
<span data-ttu-id="947bb-103">Инициализация переменной массива, включив в литерал массива `New` предложения и указав начальные значения массива.</span><span class="sxs-lookup"><span data-stu-id="947bb-103">You initialize an array variable by including an array literal in a `New` clause and specifying the initial values of the array.</span></span> <span data-ttu-id="947bb-104">Можно указать тип или разрешить ему выводится из значения литерала массива.</span><span class="sxs-lookup"><span data-stu-id="947bb-104">You can either specify the type or allow it to be inferred from the values in the array literal.</span></span> <span data-ttu-id="947bb-105">Дополнительные сведения о том, как вывести тип. в разделе «Заполнение массива с начального значения» в [массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="947bb-105">For more information about how the type is inferred, see "Populating an Array with Initial Values" in [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
### <a name="to-initialize-an-array-variable-by-using-an-array-literal"></a><span data-ttu-id="947bb-106">Для инициализации переменной массива с помощью литерала массива</span><span class="sxs-lookup"><span data-stu-id="947bb-106">To initialize an array variable by using an array literal</span></span>  
  
-   <span data-ttu-id="947bb-107">Либо в `New` предложение, или при присвоении значения массива, значения элементов внутри фигурных скобок (`{}`).</span><span class="sxs-lookup"><span data-stu-id="947bb-107">Either in the `New` clause, or when you assign the array value, supply the element values inside braces (`{}`).</span></span> <span data-ttu-id="947bb-108">В следующем примере показано несколько способов объявить, создать и инициализировать переменную для хранения массива с элементами типа `Char`.</span><span class="sxs-lookup"><span data-stu-id="947bb-108">The following example shows several ways to declare, create, and initialize a variable to contain an array that has elements of type `Char`.</span></span>  
  
     [!code-vb[VbVbalrArrays#16](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_1.vb)]  
  
     <span data-ttu-id="947bb-109">После выполнения каждой инструкции, массив, который создается имеет длину 3, элементы с индексом 0 по индексу 2, содержащая начальные значения.</span><span class="sxs-lookup"><span data-stu-id="947bb-109">After each statement executes, the array that's created has a length of 3, with elements at index 0 through index 2 containing the initial values.</span></span> <span data-ttu-id="947bb-110">Если указать верхнюю границу и значения, необходимо включить значение для каждого элемента от индекса 0 до верхней границы.</span><span class="sxs-lookup"><span data-stu-id="947bb-110">If you supply both the upper bound and the values, you must include a value for every element from index 0 through the upper bound.</span></span>  
  
     <span data-ttu-id="947bb-111">Обратите внимание, что не нужно указать верхнюю границу индекса при указании значения элементов литерала массива.</span><span class="sxs-lookup"><span data-stu-id="947bb-111">Notice that you do not have to specify the index upper bound if you supply element values in an array literal.</span></span> <span data-ttu-id="947bb-112">Если верхняя граница не указан, размер массива определяется на основе количества значений литерала массива.</span><span class="sxs-lookup"><span data-stu-id="947bb-112">If no upper bound is specified, the size of the array is inferred based on the number of values in the array literal.</span></span>  
  
### <a name="to-initialize-a-multidimensional-array-variable-by-using-array-literals"></a><span data-ttu-id="947bb-113">Для инициализации переменной многомерного массива с помощью литералов массива</span><span class="sxs-lookup"><span data-stu-id="947bb-113">To initialize a multidimensional array variable by using array literals</span></span>  
  
-   <span data-ttu-id="947bb-114">Поместите значения в фигурные скобки (`{}`) в фигурных скобках.</span><span class="sxs-lookup"><span data-stu-id="947bb-114">Nest values inside braces (`{}`) within braces.</span></span> <span data-ttu-id="947bb-115">Убедитесь, что вложенные литералы массива все подразумевают массивы одного типа и длины.</span><span class="sxs-lookup"><span data-stu-id="947bb-115">Ensure that the nested array literals all infer as arrays of the same type and length.</span></span> <span data-ttu-id="947bb-116">В следующем примере кода показано несколько примеров инициализации многомерного массива.</span><span class="sxs-lookup"><span data-stu-id="947bb-116">The following code example shows several examples of multidimensional array initialization.</span></span>  
  
     [!code-vb[VbVbalrArrays#17](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_2.vb)]  
  
-   <span data-ttu-id="947bb-117">Можно явно указать границы массива или опустить их и тогда компилятор выведет границы массива на основе значений в литерале массива.</span><span class="sxs-lookup"><span data-stu-id="947bb-117">You can explicitly specify the array bounds, or leave them out and have the compiler infer the array bounds based on the values in the array literal.</span></span> <span data-ttu-id="947bb-118">Если указать верхней границы и значения, необходимо включить значение для каждого элемента от индекса 0 до верхней границы каждого измерения.</span><span class="sxs-lookup"><span data-stu-id="947bb-118">If you supply both the upper bounds and the values, you must include a value for every element from index 0 through the upper bound in every dimension.</span></span> <span data-ttu-id="947bb-119">В следующем примере показано несколько способов объявить, создать и инициализировать переменную должна содержать двухмерный массив элементов типа`Short`</span><span class="sxs-lookup"><span data-stu-id="947bb-119">The following example shows several ways to declare, create, and initialize a variable to contain a two-dimensional array that has elements of type `Short`</span></span>  
  
     [!code-vb[VbVbalrArrays#18](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_3.vb)]  
  
     <span data-ttu-id="947bb-120">После выполнения каждой инструкции, созданный массив содержит шесть инициализированных элементов индексы `(0,0)`, `(0,1)`, `(0,2)`, `(1,0)`, `(1,1)`, и `(1,2)`.</span><span class="sxs-lookup"><span data-stu-id="947bb-120">After each statement executes, the created array contains six initialized elements that have indexes `(0,0)`, `(0,1)`, `(0,2)`, `(1,0)`, `(1,1)`, and `(1,2)`.</span></span> <span data-ttu-id="947bb-121">Каждое место массива содержит значение `10`.</span><span class="sxs-lookup"><span data-stu-id="947bb-121">Each array location contains the value `10`.</span></span>  
  
-   <span data-ttu-id="947bb-122">Следующий пример выполняется перебор многомерного массива.</span><span class="sxs-lookup"><span data-stu-id="947bb-122">The following example iterates through a multidimensional array.</span></span> <span data-ttu-id="947bb-123">В консольном приложении Windows, написанного на языке Visual Basic, вставьте код в `Sub Main()` метод.</span><span class="sxs-lookup"><span data-stu-id="947bb-123">In a Windows console application that is written in Visual Basic, paste the code inside the `Sub Main()` method.</span></span> <span data-ttu-id="947bb-124">Последний комментарии показаны выходные данные.</span><span class="sxs-lookup"><span data-stu-id="947bb-124">The last comments show the output.</span></span>  
  
     [!code-vb[VbVbalrArrays#31](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_4.vb)]  
  
### <a name="to-initialize-a-jagged-array-variable-by-using-array-literals"></a><span data-ttu-id="947bb-125">Для инициализации переменной массива массивов с помощью литералов массива</span><span class="sxs-lookup"><span data-stu-id="947bb-125">To initialize a jagged array variable by using array literals</span></span>  
  
-   <span data-ttu-id="947bb-126">Поместите значения объектов в фигурные скобки (`{}`).</span><span class="sxs-lookup"><span data-stu-id="947bb-126">Nest object values inside braces (`{}`).</span></span> <span data-ttu-id="947bb-127">Хотя можно также вложить литералы массива, задающие массивы разной длины, в случае массива массивов, убедитесь, что, вложенные литералы массива заключены в скобки (`()`).</span><span class="sxs-lookup"><span data-stu-id="947bb-127">Although you can also nest array literals that specify arrays of different lengths, in the case of a jagged array, make sure that that the nested array literals are enclosed in parentheses (`()`).</span></span> <span data-ttu-id="947bb-128">Скобки задают принудительное вычисление вложенных литералов массива и результирующие массивы используются как начальные значения массива массивов.</span><span class="sxs-lookup"><span data-stu-id="947bb-128">The parentheses force the evaluation of the nested array literals, and the resulting arrays are used as the initial values of the jagged array.</span></span> <span data-ttu-id="947bb-129">В следующем примере кода показаны два примера инициализации массива массивов.</span><span class="sxs-lookup"><span data-stu-id="947bb-129">The following code example shows two examples of jagged array initialization.</span></span>  
  
     [!code-vb[VbVbalrArrays#19](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_5.vb)]  
  
-   <span data-ttu-id="947bb-130">В следующем примере выполняется перебор массива массивов.</span><span class="sxs-lookup"><span data-stu-id="947bb-130">The following example iterates through a jagged array.</span></span> <span data-ttu-id="947bb-131">В консольном приложении Windows, написанного на языке Visual Basic, вставьте код в `Sub Main()` метод.</span><span class="sxs-lookup"><span data-stu-id="947bb-131">In a Windows console application that is written in Visual Basic, paste the code inside the `Sub Main()` method.</span></span>  <span data-ttu-id="947bb-132">Последние комментарии в коде показан вывод.</span><span class="sxs-lookup"><span data-stu-id="947bb-132">The last comments in the code show the output.</span></span>  
  
     [!code-vb[VbVbalrArrays#32](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_6.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="947bb-133">См. также</span><span class="sxs-lookup"><span data-stu-id="947bb-133">See Also</span></span>  
 [<span data-ttu-id="947bb-134">Массивы</span><span class="sxs-lookup"><span data-stu-id="947bb-134">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="947bb-135">Устранение неполадок, связанных с массивами</span><span class="sxs-lookup"><span data-stu-id="947bb-135">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
