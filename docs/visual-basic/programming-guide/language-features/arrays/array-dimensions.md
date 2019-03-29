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
ms.openlocfilehash: 47b90a6c513a5808dc0669d2d861de5e16406a34
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634171"
---
# <a name="array-dimensions-in-visual-basic"></a><span data-ttu-id="e64c8-102">Array Dimensions in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e64c8-102">Array Dimensions in Visual Basic</span></span>
<span data-ttu-id="e64c8-103">Объект *измерения* — это направление, в котором можно изменять спецификацию элементов массива.</span><span class="sxs-lookup"><span data-stu-id="e64c8-103">A *dimension* is a direction in which you can vary the specification of an array's elements.</span></span> <span data-ttu-id="e64c8-104">Массив, содержащий суммы продаж за каждый день месяца, имеет одно измерение (день месяца).</span><span class="sxs-lookup"><span data-stu-id="e64c8-104">An array that holds the sales total for each day of the month has one dimension (the day of the month).</span></span> <span data-ttu-id="e64c8-105">Массив, содержащий суммы по отделу продаж за каждый день месяца, имеет два измерения (номер отдела и день месяца).</span><span class="sxs-lookup"><span data-stu-id="e64c8-105">An array that holds the sales total by department for each day of the month has two dimensions (the department number and the day of the month).</span></span> <span data-ttu-id="e64c8-106">Число измерений массива называется его *ранг*.</span><span class="sxs-lookup"><span data-stu-id="e64c8-106">The number of dimensions an array has is called its *rank*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e64c8-107">Можно использовать <xref:System.Array.Rank%2A> свойство для определения количества измерений массива.</span><span class="sxs-lookup"><span data-stu-id="e64c8-107">You can use the <xref:System.Array.Rank%2A> property to determine the how many dimensions an array has.</span></span>  
  
## <a name="working-with-dimensions"></a><span data-ttu-id="e64c8-108">Работа с измерениями</span><span class="sxs-lookup"><span data-stu-id="e64c8-108">Working with Dimensions</span></span>  
 <span data-ttu-id="e64c8-109">Необходимо указывать элемент массива, указав *индекс* или *индекс* для каждого из его измерений.</span><span class="sxs-lookup"><span data-stu-id="e64c8-109">You specify an element of an array by supplying an *index* or *subscript* for each of its dimensions.</span></span> <span data-ttu-id="e64c8-110">Элементы являются смежными вдоль каждого измерения, от индекса 0 до наибольшего индекса для этого измерения.</span><span class="sxs-lookup"><span data-stu-id="e64c8-110">The elements are contiguous along each dimension from index 0 through the highest index for that dimension.</span></span>  
  
 <span data-ttu-id="e64c8-111">На следующих рисунках показаны концептуальная структура массивов с использованием разных рангов.</span><span class="sxs-lookup"><span data-stu-id="e64c8-111">The following illustrations show the conceptual structure of arrays with different ranks.</span></span> <span data-ttu-id="e64c8-112">Каждый элемент на рисунках показаны значения индекса, доступ к нему.</span><span class="sxs-lookup"><span data-stu-id="e64c8-112">Each element in the illustrations shows the index values that access it.</span></span> <span data-ttu-id="e64c8-113">Например, можно получить доступ к первый элемент второй строки двумерного массива, указав индексы `(1, 0)`.</span><span class="sxs-lookup"><span data-stu-id="e64c8-113">For example, you can access the first element of the second row of the two-dimensional array by specifying indexes `(1, 0)`.</span></span>  
  
 ![Схема, показывающая одномерного массива.](./media/array-dimensions/one-dimensional-array.gif)  
  
 ![Схема, показывающая двумерный массив.](./media/array-dimensions/two-dimensional-array.gif)  
  
 ![Схема, показывающая трехмерного массива.](./media/array-dimensions/three-dimensional-array.gif)  
  
### <a name="one-dimension"></a><span data-ttu-id="e64c8-117">Одно измерение</span><span class="sxs-lookup"><span data-stu-id="e64c8-117">One Dimension</span></span>  
 <span data-ttu-id="e64c8-118">Многие массивы имеют только одно измерение, например количество людей каждого возраста.</span><span class="sxs-lookup"><span data-stu-id="e64c8-118">Many arrays have only one dimension, such as the number of people of each age.</span></span> <span data-ttu-id="e64c8-119">Единственным требованием для указания элемента является возраст, для которого этот элемент содержит счетчик.</span><span class="sxs-lookup"><span data-stu-id="e64c8-119">The only requirement to specify an element is the age for which that element holds the count.</span></span> <span data-ttu-id="e64c8-120">Таким образом такой массив использует только один индекс.</span><span class="sxs-lookup"><span data-stu-id="e64c8-120">Therefore, such an array uses only one index.</span></span> <span data-ttu-id="e64c8-121">В следующем примере объявляется переменная для хранения *одномерный массив* возраста подсчитывает для возраста от 0 до 120.</span><span class="sxs-lookup"><span data-stu-id="e64c8-121">The following example declares a variable to hold a *one-dimensional array* of age counts for ages 0 through 120.</span></span>  
  
```  
Dim ageCounts(120) As UInteger  
```  
  
### <a name="two-dimensions"></a><span data-ttu-id="e64c8-122">Два измерения</span><span class="sxs-lookup"><span data-stu-id="e64c8-122">Two Dimensions</span></span>  
 <span data-ttu-id="e64c8-123">Некоторые массивы имеют два измерения, такие как количество офисов на каждого этажа для каждого здания в другой.</span><span class="sxs-lookup"><span data-stu-id="e64c8-123">Some arrays have two dimensions, such as the number of offices on each floor of each building on a campus.</span></span> <span data-ttu-id="e64c8-124">Спецификация элемента требует указания номера и ближайшее снизу целое, и каждый элемент содержит счетчик для этого сочетания здание и этаж.</span><span class="sxs-lookup"><span data-stu-id="e64c8-124">The specification of an element requires both the building number and the floor, and each element holds the count for that combination of building and floor.</span></span> <span data-ttu-id="e64c8-125">Таким образом такой массив использует два индекса.</span><span class="sxs-lookup"><span data-stu-id="e64c8-125">Therefore, such an array uses two indexes.</span></span> <span data-ttu-id="e64c8-126">В следующем примере объявляется переменная для хранения *двумерный массив* из счетчиков office для зданий от 0 до 40 и этажей от 0 до 5.</span><span class="sxs-lookup"><span data-stu-id="e64c8-126">The following example declares a variable to hold a *two-dimensional array* of office counts, for buildings 0 through 40 and floors 0 through 5.</span></span>  
  
```  
Dim officeCounts(40, 5) As Byte  
```  
  
 <span data-ttu-id="e64c8-127">Двумерный массив также называют *прямоугольного массива*.</span><span class="sxs-lookup"><span data-stu-id="e64c8-127">A two-dimensional array is also called a *rectangular array*.</span></span>  
  
### <a name="three-dimensions"></a><span data-ttu-id="e64c8-128">Три измерения</span><span class="sxs-lookup"><span data-stu-id="e64c8-128">Three Dimensions</span></span>  
 <span data-ttu-id="e64c8-129">Некоторые массивы имеют три измерения, такие как значения в трехмерном пространстве.</span><span class="sxs-lookup"><span data-stu-id="e64c8-129">A few arrays have three dimensions, such as values in three-dimensional space.</span></span> <span data-ttu-id="e64c8-130">Такой массив использует три индекса, которые в этом случае представляют x, y и z координаты физического пространства.</span><span class="sxs-lookup"><span data-stu-id="e64c8-130">Such an array uses three indexes, which in this case represent the x, y, and z coordinates of physical space.</span></span> <span data-ttu-id="e64c8-131">В следующем примере объявляется переменная для хранения *трехмерный массив* температуры воздуха в различных точках трехмерного объема.</span><span class="sxs-lookup"><span data-stu-id="e64c8-131">The following example declares a variable to hold a *three-dimensional array* of air temperatures at various points in a three-dimensional volume.</span></span>  
  
```  
Dim airTemperatures(99, 99, 24) As Single  
```  
  
### <a name="more-than-three-dimensions"></a><span data-ttu-id="e64c8-132">Более чем трех измерений</span><span class="sxs-lookup"><span data-stu-id="e64c8-132">More than Three Dimensions</span></span>  
 <span data-ttu-id="e64c8-133">Несмотря на то, что массив может иметь до 32 измерений, применяется довольно редко бывает более трех.</span><span class="sxs-lookup"><span data-stu-id="e64c8-133">Although an array can have as many as 32 dimensions, it is rare to have more than three.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e64c8-134">При добавлении измерения массива, общий объем хранилища, необходимая значительно, увеличивается так многомерные массивы используйте с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="e64c8-134">When you add dimensions to an array, the total storage needed by the array increases considerably, so use multidimensional arrays with care.</span></span>  
  
## <a name="using-different-dimensions"></a><span data-ttu-id="e64c8-135">Использование различных измерений</span><span class="sxs-lookup"><span data-stu-id="e64c8-135">Using Different Dimensions</span></span>  
 <span data-ttu-id="e64c8-136">Предположим, что вы хотите отслеживать суммы продаж за каждый день текущего месяца.</span><span class="sxs-lookup"><span data-stu-id="e64c8-136">Suppose you want to track sales amounts for every day of the present month.</span></span> <span data-ttu-id="e64c8-137">Можно объявить одномерный массив с 31 элементы один за каждый день месяца, в приведенном ниже примере показано.</span><span class="sxs-lookup"><span data-stu-id="e64c8-137">You might declare a one-dimensional array with 31 elements, one for each day of the month, as the following example shows.</span></span>  
  
```  
Dim salesAmounts(30) As Double  
```  
  
 <span data-ttu-id="e64c8-138">Теперь предположим, что требуется отслеживать те же сведения, не только на каждый день в месяце, но и для каждого месяца года.</span><span class="sxs-lookup"><span data-stu-id="e64c8-138">Now suppose you want to track the same information not only for every day of a month but also for every month of the year.</span></span> <span data-ttu-id="e64c8-139">Можно объявить двумерного массива с 12 строк (в течение месяцев) и 31 колонок (дни), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="e64c8-139">You might declare a two-dimensional array with 12 rows (for the months) and 31 columns (for the days), as the following example shows.</span></span>  
  
```  
Dim salesAmounts(11, 30) As Double  
```  
  
 <span data-ttu-id="e64c8-140">Теперь предположим, что вам необходимо хранить сведения для более чем одного года.</span><span class="sxs-lookup"><span data-stu-id="e64c8-140">Now suppose you decide to have your array hold information for more than one year.</span></span> <span data-ttu-id="e64c8-141">Если вы хотите отслеживать суммы продаж в течение 5 лет, можно объявить трехмерный массив с 5 слоями, 12 строк и 31 столбцом, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="e64c8-141">If you want to track sales amounts for 5 years, you could declare a three-dimensional array with 5 layers, 12 rows, and 31 columns, as the following example shows.</span></span>  
  
```  
Dim salesAmounts(4, 11, 30) As Double  
```  
  
 <span data-ttu-id="e64c8-142">Обратите внимание, что, поскольку каждый индекс находится в диапазоне от 0 до своего максимального значения каждого измерения массива, `salesAmounts` объявляется как единицу меньше, чем требуемая длина для данного измерения.</span><span class="sxs-lookup"><span data-stu-id="e64c8-142">Note that, because each index varies from 0 to its maximum, each dimension of `salesAmounts` is declared as one less than the required length for that dimension.</span></span> <span data-ttu-id="e64c8-143">Кроме того, обратите внимание, что размер массива увеличивается с каждым новым измерением.</span><span class="sxs-lookup"><span data-stu-id="e64c8-143">Note also that the size of the array increases with each new dimension.</span></span> <span data-ttu-id="e64c8-144">Три размера в предыдущих примерах, 31, 372 и 1860 элементов соответственно.</span><span class="sxs-lookup"><span data-stu-id="e64c8-144">The three sizes in the preceding examples are 31, 372, and 1,860 elements respectively.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e64c8-145">Можно создать массив без использования `Dim` инструкции или `New` предложение.</span><span class="sxs-lookup"><span data-stu-id="e64c8-145">You can create an array without using the `Dim` statement or the `New` clause.</span></span> <span data-ttu-id="e64c8-146">Например, можно вызвать <xref:System.Array.CreateInstance%2A> метод или другой компонент массив можно передать код создается таким образом.</span><span class="sxs-lookup"><span data-stu-id="e64c8-146">For example, you can call the <xref:System.Array.CreateInstance%2A> method, or another component can pass your code an array created in this manner.</span></span> <span data-ttu-id="e64c8-147">Такой массив может иметь нижнюю границу, отличное от 0.</span><span class="sxs-lookup"><span data-stu-id="e64c8-147">Such an array can have a lower bound other than 0.</span></span> <span data-ttu-id="e64c8-148">Всегда можно протестировать для нижней границы измерения с помощью <xref:System.Array.GetLowerBound%2A> метод или `LBound` функции.</span><span class="sxs-lookup"><span data-stu-id="e64c8-148">You can always test for the lower bound of a dimension by using the <xref:System.Array.GetLowerBound%2A> method or the `LBound` function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e64c8-149">См. также</span><span class="sxs-lookup"><span data-stu-id="e64c8-149">See also</span></span>
- [<span data-ttu-id="e64c8-150">Массивы</span><span class="sxs-lookup"><span data-stu-id="e64c8-150">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="e64c8-151">Устранение неполадок, связанных с массивами</span><span class="sxs-lookup"><span data-stu-id="e64c8-151">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
