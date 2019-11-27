---
title: Измерения массива
ms.date: 07/20/2015
helpviewer_keywords:
- dimensions, arrays
- arrays [Visual Basic], dimensions
- arrays [Visual Basic], rectangular
- arrays [Visual Basic], rank
- rectangular arrays
- ranking, arrays
ms.assetid: 385e911b-18c1-4e98-9924-c6d279101dd9
ms.openlocfilehash: 12e983ae62fa9f9ea762d434ffe5b73873a4a2e8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351899"
---
# <a name="array-dimensions-in-visual-basic"></a><span data-ttu-id="8255a-102">Array Dimensions in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8255a-102">Array Dimensions in Visual Basic</span></span>

<span data-ttu-id="8255a-103">*Измерение* — это направление, в котором можно изменять спецификацию элементов массива.</span><span class="sxs-lookup"><span data-stu-id="8255a-103">A *dimension* is a direction in which you can vary the specification of an array's elements.</span></span> <span data-ttu-id="8255a-104">В массиве, содержащем общую сумму продаж за каждый день месяца, должно быть одно измерение (день месяца).</span><span class="sxs-lookup"><span data-stu-id="8255a-104">An array that holds the sales total for each day of the month has one dimension (the day of the month).</span></span> <span data-ttu-id="8255a-105">Массив, содержащий сумму продаж по Отделу для каждого дня месяца, имеет два измерения (номер отдела и день месяца).</span><span class="sxs-lookup"><span data-stu-id="8255a-105">An array that holds the sales total by department for each day of the month has two dimensions (the department number and the day of the month).</span></span> <span data-ttu-id="8255a-106">Количество измерений массива называется его *рангом*.</span><span class="sxs-lookup"><span data-stu-id="8255a-106">The number of dimensions an array has is called its *rank*.</span></span>

> [!NOTE]
> <span data-ttu-id="8255a-107">Чтобы определить, сколько измерений имеет массив, можно использовать свойство <xref:System.Array.Rank%2A>.</span><span class="sxs-lookup"><span data-stu-id="8255a-107">You can use the <xref:System.Array.Rank%2A> property to determine the how many dimensions an array has.</span></span>

## <a name="working-with-dimensions"></a><span data-ttu-id="8255a-108">Работа с измерениями</span><span class="sxs-lookup"><span data-stu-id="8255a-108">Working with Dimensions</span></span>

<span data-ttu-id="8255a-109">Элемент массива указывается путем предоставления *индекса* или *подстрочного скрипта* для каждого из его измерений.</span><span class="sxs-lookup"><span data-stu-id="8255a-109">You specify an element of an array by supplying an *index* or *subscript* for each of its dimensions.</span></span> <span data-ttu-id="8255a-110">Элементы являются непрерывными по отношению к каждому измерению от индекса 0 до самого высокого индекса для этого измерения.</span><span class="sxs-lookup"><span data-stu-id="8255a-110">The elements are contiguous along each dimension from index 0 through the highest index for that dimension.</span></span>

<span data-ttu-id="8255a-111">На следующих иллюстрациях показана концептуальная структура массивов с разными рангами.</span><span class="sxs-lookup"><span data-stu-id="8255a-111">The following illustrations show the conceptual structure of arrays with different ranks.</span></span> <span data-ttu-id="8255a-112">Каждый элемент на иллюстрациях показывает значения индекса, к которым он обращается.</span><span class="sxs-lookup"><span data-stu-id="8255a-112">Each element in the illustrations shows the index values that access it.</span></span> <span data-ttu-id="8255a-113">Например, можно получить доступ к первому элементу второй строки двумерного массива, указав индексы `(1, 0)`.</span><span class="sxs-lookup"><span data-stu-id="8255a-113">For example, you can access the first element of the second row of the two-dimensional array by specifying indexes `(1, 0)`.</span></span>

![Схема, на которой показан одномерный массив.](./media/array-dimensions/one-dimensional-array.gif)

![Схема, на которой показан двухмерный массив.](./media/array-dimensions/two-dimensional-array.gif)

![Схема, на которой показан трехмерный массив.](./media/array-dimensions/three-dimensional-array.gif)

### <a name="one-dimension"></a><span data-ttu-id="8255a-117">Одно измерение</span><span class="sxs-lookup"><span data-stu-id="8255a-117">One Dimension</span></span>

<span data-ttu-id="8255a-118">Многие массивы имеют только одно измерение, например число людей каждого возраста.</span><span class="sxs-lookup"><span data-stu-id="8255a-118">Many arrays have only one dimension, such as the number of people of each age.</span></span> <span data-ttu-id="8255a-119">Единственным требованием для указания элемента является возраст, для которого этот элемент содержит число.</span><span class="sxs-lookup"><span data-stu-id="8255a-119">The only requirement to specify an element is the age for which that element holds the count.</span></span> <span data-ttu-id="8255a-120">Таким образом, такой массив использует только один индекс.</span><span class="sxs-lookup"><span data-stu-id="8255a-120">Therefore, such an array uses only one index.</span></span> <span data-ttu-id="8255a-121">В следующем примере объявляется переменная для хранения *одномерного массива* счетчиков возраста в возрасте от 0 до 120.</span><span class="sxs-lookup"><span data-stu-id="8255a-121">The following example declares a variable to hold a *one-dimensional array* of age counts for ages 0 through 120.</span></span>

```vb
Dim ageCounts(120) As UInteger
```

### <a name="two-dimensions"></a><span data-ttu-id="8255a-122">Два измерения</span><span class="sxs-lookup"><span data-stu-id="8255a-122">Two Dimensions</span></span>

<span data-ttu-id="8255a-123">Некоторые массивы имеют два измерения, такие как количество офисов на каждом этаже каждого здания на кампусе.</span><span class="sxs-lookup"><span data-stu-id="8255a-123">Some arrays have two dimensions, such as the number of offices on each floor of each building on a campus.</span></span> <span data-ttu-id="8255a-124">Спецификация элемента требует как номер здания, так и этаж, и каждый элемент содержит количество для этого сочетания здания и этажа.</span><span class="sxs-lookup"><span data-stu-id="8255a-124">The specification of an element requires both the building number and the floor, and each element holds the count for that combination of building and floor.</span></span> <span data-ttu-id="8255a-125">Таким образом, такой массив использует два индекса.</span><span class="sxs-lookup"><span data-stu-id="8255a-125">Therefore, such an array uses two indexes.</span></span> <span data-ttu-id="8255a-126">В следующем примере объявляется переменная для хранения *двумерного массива* счетчиков Office, для зданий от 0 до 40 и этажей от 0 до 5.</span><span class="sxs-lookup"><span data-stu-id="8255a-126">The following example declares a variable to hold a *two-dimensional array* of office counts, for buildings 0 through 40 and floors 0 through 5.</span></span>

```vb
Dim officeCounts(40, 5) As Byte
```

<span data-ttu-id="8255a-127">Двумерный массив также называется *прямоугольным массивом*.</span><span class="sxs-lookup"><span data-stu-id="8255a-127">A two-dimensional array is also called a *rectangular array*.</span></span>

### <a name="three-dimensions"></a><span data-ttu-id="8255a-128">Три измерения</span><span class="sxs-lookup"><span data-stu-id="8255a-128">Three Dimensions</span></span>

<span data-ttu-id="8255a-129">Несколько массивов имеют три измерения, такие как значения в трехмерном пространстве.</span><span class="sxs-lookup"><span data-stu-id="8255a-129">A few arrays have three dimensions, such as values in three-dimensional space.</span></span> <span data-ttu-id="8255a-130">Такой массив использует три индекса, которые в данном случае представляют координаты x, y и z физического пространства.</span><span class="sxs-lookup"><span data-stu-id="8255a-130">Such an array uses three indexes, which in this case represent the x, y, and z coordinates of physical space.</span></span> <span data-ttu-id="8255a-131">В следующем примере объявляется переменная для хранения *трехмерного массива* температур воздуха в различных точках трехмерного тома.</span><span class="sxs-lookup"><span data-stu-id="8255a-131">The following example declares a variable to hold a *three-dimensional array* of air temperatures at various points in a three-dimensional volume.</span></span>

```vb
Dim airTemperatures(99, 99, 24) As Single
```

### <a name="more-than-three-dimensions"></a><span data-ttu-id="8255a-132">Более трех измерений</span><span class="sxs-lookup"><span data-stu-id="8255a-132">More than Three Dimensions</span></span>

<span data-ttu-id="8255a-133">Несмотря на то, что массив может иметь столько же измерений, как 32, редко бывает больше трех.</span><span class="sxs-lookup"><span data-stu-id="8255a-133">Although an array can have as many as 32 dimensions, it is rare to have more than three.</span></span>

> [!NOTE]
> <span data-ttu-id="8255a-134">При добавлении измерений в массив значительно возрастает объем необходимого для массива хранилища, поэтому используйте многомерные массивы с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="8255a-134">When you add dimensions to an array, the total storage needed by the array increases considerably, so use multidimensional arrays with care.</span></span>

## <a name="using-different-dimensions"></a><span data-ttu-id="8255a-135">Использование различных измерений</span><span class="sxs-lookup"><span data-stu-id="8255a-135">Using Different Dimensions</span></span>

<span data-ttu-id="8255a-136">Предположим, что требуется отслеживание объемов продаж за каждый день текущего месяца.</span><span class="sxs-lookup"><span data-stu-id="8255a-136">Suppose you want to track sales amounts for every day of the present month.</span></span> <span data-ttu-id="8255a-137">Вы можете объявить одномерный массив с 31 элементами, по одному на каждый день месяца, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8255a-137">You might declare a one-dimensional array with 31 elements, one for each day of the month, as the following example shows.</span></span>

```vb
Dim salesAmounts(30) As Double
```

<span data-ttu-id="8255a-138">Теперь предположим, что необходимо отвести одну и ту же информацию не только для каждого дня месяца, но и для каждого месяца года.</span><span class="sxs-lookup"><span data-stu-id="8255a-138">Now suppose you want to track the same information not only for every day of a month but also for every month of the year.</span></span> <span data-ttu-id="8255a-139">Можно объявить двумерный массив с 12 строками (для месяцев) и 31 столбцами (в днях), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8255a-139">You might declare a two-dimensional array with 12 rows (for the months) and 31 columns (for the days), as the following example shows.</span></span>

```vb
Dim salesAmounts(11, 30) As Double
```

<span data-ttu-id="8255a-140">Теперь предположим, что вы решили, чтобы ваш массив содержал данные в течение более чем одного года.</span><span class="sxs-lookup"><span data-stu-id="8255a-140">Now suppose you decide to have your array hold information for more than one year.</span></span> <span data-ttu-id="8255a-141">Если вы хотите отследить объем продаж в течение 5 лет, можно объявить трехмерный массив с 5 слоями, 12 строками и 31 столбцами, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8255a-141">If you want to track sales amounts for 5 years, you could declare a three-dimensional array with 5 layers, 12 rows, and 31 columns, as the following example shows.</span></span>

```vb
Dim salesAmounts(4, 11, 30) As Double
```

<span data-ttu-id="8255a-142">Обратите внимание, что, поскольку каждый индекс принимает значение от 0 до максимального значения, каждое измерение `salesAmounts` объявляется как меньше, чем требуемая длина для этого измерения.</span><span class="sxs-lookup"><span data-stu-id="8255a-142">Note that, because each index varies from 0 to its maximum, each dimension of `salesAmounts` is declared as one less than the required length for that dimension.</span></span> <span data-ttu-id="8255a-143">Обратите внимание, что размер массива увеличивается с каждым новым измерением.</span><span class="sxs-lookup"><span data-stu-id="8255a-143">Note also that the size of the array increases with each new dimension.</span></span> <span data-ttu-id="8255a-144">Три размера в предыдущих примерах — 31, 372 и 1 860 соответственно.</span><span class="sxs-lookup"><span data-stu-id="8255a-144">The three sizes in the preceding examples are 31, 372, and 1,860 elements respectively.</span></span>

> [!NOTE]
> <span data-ttu-id="8255a-145">Массив можно создать без использования оператора `Dim` или предложения `New`.</span><span class="sxs-lookup"><span data-stu-id="8255a-145">You can create an array without using the `Dim` statement or the `New` clause.</span></span> <span data-ttu-id="8255a-146">Например, можно вызвать метод <xref:System.Array.CreateInstance%2A>, или другой компонент может передать ваш код массиву, созданному таким образом.</span><span class="sxs-lookup"><span data-stu-id="8255a-146">For example, you can call the <xref:System.Array.CreateInstance%2A> method, or another component can pass your code an array created in this manner.</span></span> <span data-ttu-id="8255a-147">Такой массив может иметь нижнюю границу, отличную от 0.</span><span class="sxs-lookup"><span data-stu-id="8255a-147">Such an array can have a lower bound other than 0.</span></span> <span data-ttu-id="8255a-148">Вы всегда можете проверить нижнюю границу измерения с помощью метода <xref:System.Array.GetLowerBound%2A> или функции `LBound`.</span><span class="sxs-lookup"><span data-stu-id="8255a-148">You can always test for the lower bound of a dimension by using the <xref:System.Array.GetLowerBound%2A> method or the `LBound` function.</span></span>

## <a name="see-also"></a><span data-ttu-id="8255a-149">См. также</span><span class="sxs-lookup"><span data-stu-id="8255a-149">See also</span></span>

- [<span data-ttu-id="8255a-150">Массивы</span><span class="sxs-lookup"><span data-stu-id="8255a-150">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="8255a-151">Устранение неполадок, связанных с массивами</span><span class="sxs-lookup"><span data-stu-id="8255a-151">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
