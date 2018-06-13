---
title: Array Dimensions in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- dimensions, arrays
- arrays [Visual Basic], dimensions
- arrays [Visual Basic], rectangular
- arrays [Visual Basic], rank
- rectangular arrays
- ranking, arrays
ms.assetid: 385e911b-18c1-4e98-9924-c6d279101dd9
ms.openlocfilehash: cf295288dd034d744dceb71b5c58278be5cc2a2f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651760"
---
# <a name="array-dimensions-in-visual-basic"></a><span data-ttu-id="1a3c7-102">Array Dimensions in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1a3c7-102">Array Dimensions in Visual Basic</span></span>
<span data-ttu-id="1a3c7-103">Объект *измерения* направление, в котором можно изменять спецификацию элементов массива.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-103">A *dimension* is a direction in which you can vary the specification of an array's elements.</span></span> <span data-ttu-id="1a3c7-104">Массив, содержащий суммы продаж за каждый день месяца, имеет одного измерения (день месяца).</span><span class="sxs-lookup"><span data-stu-id="1a3c7-104">An array that holds the sales total for each day of the month has one dimension (the day of the month).</span></span> <span data-ttu-id="1a3c7-105">Массив, содержащий суммы по отделу продаж за каждый день месяца, имеет два измерения (номер отдела и день месяца).</span><span class="sxs-lookup"><span data-stu-id="1a3c7-105">An array that holds the sales total by department for each day of the month has two dimensions (the department number and the day of the month).</span></span> <span data-ttu-id="1a3c7-106">Размерность массива не вызывается его *ранг*.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-106">The number of dimensions an array has is called its *rank*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a3c7-107">Можно использовать <xref:System.Array.Rank%2A> свойство для определения количества измерений массива.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-107">You can use the <xref:System.Array.Rank%2A> property to determine the how many dimensions an array has.</span></span>  
  
## <a name="working-with-dimensions"></a><span data-ttu-id="1a3c7-108">Работа с измерениями</span><span class="sxs-lookup"><span data-stu-id="1a3c7-108">Working with Dimensions</span></span>  
 <span data-ttu-id="1a3c7-109">Необходимо указывать элемент массива, указав *индекс* или *индекс* для каждого из его измерений.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-109">You specify an element of an array by supplying an *index* or *subscript* for each of its dimensions.</span></span> <span data-ttu-id="1a3c7-110">Элементы непрерывны вдоль каждого измерения, от индекса 0 до наибольшего индекса для этого измерения.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-110">The elements are contiguous along each dimension from index 0 through the highest index for that dimension.</span></span>  
  
 <span data-ttu-id="1a3c7-111">Общая структура массивов различного ранга на рисунках ниже.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-111">The following illustrations show the conceptual structure of arrays with different ranks.</span></span> <span data-ttu-id="1a3c7-112">Каждый элемент на рисунках показаны значения индекса, которые к нему доступ.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-112">Each element in the illustrations shows the index values that access it.</span></span> <span data-ttu-id="1a3c7-113">Например, можно получить доступ к первый элемент второй строки двумерного массива, указав индексы `(1, 0)`.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-113">For example, you can access the first element of the second row of the two-dimensional array by specifying indexes `(1, 0)`.</span></span>  
  
 <span data-ttu-id="1a3c7-114">![Графическая схема одного&#45;двумерный массив](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimone.gif "ArrayExDimOne")</span><span class="sxs-lookup"><span data-stu-id="1a3c7-114">![Graphic diagram of one&#45;dimensional array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimone.gif "ArrayExDimOne")</span></span>  
<span data-ttu-id="1a3c7-115">Одномерный массив</span><span class="sxs-lookup"><span data-stu-id="1a3c7-115">One-dimensional array</span></span>  
  
 <span data-ttu-id="1a3c7-116">![Графическая схема двух&#45;двумерный массив](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimtwo.gif "ArrayExDimTwo")</span><span class="sxs-lookup"><span data-stu-id="1a3c7-116">![Graphic diagram of two&#45;dimensional array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimtwo.gif "ArrayExDimTwo")</span></span>  
<span data-ttu-id="1a3c7-117">Двумерный массив</span><span class="sxs-lookup"><span data-stu-id="1a3c7-117">Two-dimensional array</span></span>  
  
 <span data-ttu-id="1a3c7-118">![Графическая схема из трех&#45;двумерный массив](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimthree.gif "ArrayExDimThree")</span><span class="sxs-lookup"><span data-stu-id="1a3c7-118">![Graphic diagram of three&#45;dimensional array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimthree.gif "ArrayExDimThree")</span></span>  
<span data-ttu-id="1a3c7-119">Трехмерный массив</span><span class="sxs-lookup"><span data-stu-id="1a3c7-119">Three-dimensional array</span></span>  
  
### <a name="one-dimension"></a><span data-ttu-id="1a3c7-120">Одно измерение</span><span class="sxs-lookup"><span data-stu-id="1a3c7-120">One Dimension</span></span>  
 <span data-ttu-id="1a3c7-121">Многие массивы имеют только одно измерение, например, сколько людей каждого возраста.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-121">Many arrays have only one dimension, such as the number of people of each age.</span></span> <span data-ttu-id="1a3c7-122">Единственное требование для указания элемента является возраст, для которого этот элемент содержит счетчик.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-122">The only requirement to specify an element is the age for which that element holds the count.</span></span> <span data-ttu-id="1a3c7-123">Таким образом такой массив использует только один индекс.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-123">Therefore, such an array uses only one index.</span></span> <span data-ttu-id="1a3c7-124">В следующем примере объявляется переменная для хранения *одномерный массив* возраст подсчитывает для возраста от 0 до 120.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-124">The following example declares a variable to hold a *one-dimensional array* of age counts for ages 0 through 120.</span></span>  
  
```  
Dim ageCounts(120) As UInteger  
```  
  
### <a name="two-dimensions"></a><span data-ttu-id="1a3c7-125">Два измерения</span><span class="sxs-lookup"><span data-stu-id="1a3c7-125">Two Dimensions</span></span>  
 <span data-ttu-id="1a3c7-126">Некоторые массивы имеют два измерения, такие как количество офисов в каждой установки каждого построения на другой.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-126">Some arrays have two dimensions, such as the number of offices on each floor of each building on a campus.</span></span> <span data-ttu-id="1a3c7-127">Спецификация элемента требует номера здания и пол, а каждый элемент содержит счетчик для данного сочетания здание и этаж.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-127">The specification of an element requires both the building number and the floor, and each element holds the count for that combination of building and floor.</span></span> <span data-ttu-id="1a3c7-128">Таким образом такой массив использует два индекса.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-128">Therefore, such an array uses two indexes.</span></span> <span data-ttu-id="1a3c7-129">В следующем примере объявляется переменная для хранения *двумерный массив* из счетчиков офисов для зданий от 0 до 40 и этажи 0 – 5.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-129">The following example declares a variable to hold a *two-dimensional array* of office counts, for buildings 0 through 40 and floors 0 through 5.</span></span>  
  
```  
Dim officeCounts(40, 5) As Byte  
```  
  
 <span data-ttu-id="1a3c7-130">Также называется двумерный массив *прямоугольный массив*.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-130">A two-dimensional array is also called a *rectangular array*.</span></span>  
  
### <a name="three-dimensions"></a><span data-ttu-id="1a3c7-131">Три измерения</span><span class="sxs-lookup"><span data-stu-id="1a3c7-131">Three Dimensions</span></span>  
 <span data-ttu-id="1a3c7-132">Некоторые массивы имеют три измерения, такие как значения в трехмерном пространстве.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-132">A few arrays have three dimensions, such as values in three-dimensional space.</span></span> <span data-ttu-id="1a3c7-133">Такой массив использует три индекса, которые в этом случае представляют x, y и z координаты физического пространства.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-133">Such an array uses three indexes, which in this case represent the x, y, and z coordinates of physical space.</span></span> <span data-ttu-id="1a3c7-134">В следующем примере объявляется переменная для хранения *трехмерный массив* температуры воздуха в различных точках трехмерного объема.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-134">The following example declares a variable to hold a *three-dimensional array* of air temperatures at various points in a three-dimensional volume.</span></span>  
  
```  
Dim airTemperatures(99, 99, 24) As Single  
```  
  
### <a name="more-than-three-dimensions"></a><span data-ttu-id="1a3c7-135">Более трех измерений</span><span class="sxs-lookup"><span data-stu-id="1a3c7-135">More than Three Dimensions</span></span>  
 <span data-ttu-id="1a3c7-136">Несмотря на то, что массив может иметь до 32 измерений, довольно редко бывает более трех.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-136">Although an array can have as many as 32 dimensions, it is rare to have more than three.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a3c7-137">При добавлении измерения массива, общий объем хранилища, необходимого для массива, значительно, увеличивается так многомерные массивы используйте с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-137">When you add dimensions to an array, the total storage needed by the array increases considerably, so use multidimensional arrays with care.</span></span>  
  
## <a name="using-different-dimensions"></a><span data-ttu-id="1a3c7-138">Использование различных измерений</span><span class="sxs-lookup"><span data-stu-id="1a3c7-138">Using Different Dimensions</span></span>  
 <span data-ttu-id="1a3c7-139">Предположим, что требуется отслеживать суммы продаж за каждый день текущего месяца.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-139">Suppose you want to track sales amounts for every day of the present month.</span></span> <span data-ttu-id="1a3c7-140">Можно объявить одномерный массив с 31 элементом одному на каждый день месяца, в следующем примере показано.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-140">You might declare a one-dimensional array with 31 elements, one for each day of the month, as the following example shows.</span></span>  
  
```  
Dim salesAmounts(30) As Double  
```  
  
 <span data-ttu-id="1a3c7-141">Теперь предположим, что требуется отслеживать те же сведения, не только для каждого дня в месяце, но и для каждого месяца года.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-141">Now suppose you want to track the same information not only for every day of a month but also for every month of the year.</span></span> <span data-ttu-id="1a3c7-142">Можно объявить двумерный массив с 12 строк (по месяцам) и 31 колонок (дни), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-142">You might declare a two-dimensional array with 12 rows (for the months) and 31 columns (for the days), as the following example shows.</span></span>  
  
```  
Dim salesAmounts(11, 30) As Double  
```  
  
 <span data-ttu-id="1a3c7-143">Теперь предположим, что вы решили хранить сведения для более чем одного года.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-143">Now suppose you decide to have your array hold information for more than one year.</span></span> <span data-ttu-id="1a3c7-144">Если вы хотите отслеживать суммы продаж в течение 5 лет, можно объявить трехмерный массив с 5 слоями, 12 строк и 31 столбцом, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-144">If you want to track sales amounts for 5 years, you could declare a three-dimensional array with 5 layers, 12 rows, and 31 columns, as the following example shows.</span></span>  
  
```  
Dim salesAmounts(4, 11, 30) As Double  
```  
  
 <span data-ttu-id="1a3c7-145">Обратите внимание, что, так как каждый индекс меняется от 0 до своего максимального значения, каждое измерение массива `salesAmounts` объявлен на единицу меньше, чем требуемая длина этого измерения.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-145">Note that, because each index varies from 0 to its maximum, each dimension of `salesAmounts` is declared as one less than the required length for that dimension.</span></span> <span data-ttu-id="1a3c7-146">Обратите внимание, что размер массива увеличивается с каждым новым измерением.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-146">Note also that the size of the array increases with each new dimension.</span></span> <span data-ttu-id="1a3c7-147">В приведенном примере три размера: 31, 372 и 1860 элементов.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-147">The three sizes in the preceding examples are 31, 372, and 1,860 elements respectively.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a3c7-148">Можно создать массив без использования `Dim` инструкции или `New` предложения.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-148">You can create an array without using the `Dim` statement or the `New` clause.</span></span> <span data-ttu-id="1a3c7-149">Например, можно вызвать <xref:System.Array.CreateInstance%2A> метода или другим компонентом массив можно передать кода создается таким образом.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-149">For example, you can call the <xref:System.Array.CreateInstance%2A> method, or another component can pass your code an array created in this manner.</span></span> <span data-ttu-id="1a3c7-150">Такой массив может иметь нижнюю границу, отличное от 0.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-150">Such an array can have a lower bound other than 0.</span></span> <span data-ttu-id="1a3c7-151">Можно всегда проверять для нижней границы измерения с помощью <xref:System.Array.GetLowerBound%2A> метода или `LBound` функции.</span><span class="sxs-lookup"><span data-stu-id="1a3c7-151">You can always test for the lower bound of a dimension by using the <xref:System.Array.GetLowerBound%2A> method or the `LBound` function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a3c7-152">См. также</span><span class="sxs-lookup"><span data-stu-id="1a3c7-152">See Also</span></span>  
 [<span data-ttu-id="1a3c7-153">Массивы</span><span class="sxs-lookup"><span data-stu-id="1a3c7-153">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="1a3c7-154">Устранение неполадок, связанных с массивами</span><span class="sxs-lookup"><span data-stu-id="1a3c7-154">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
