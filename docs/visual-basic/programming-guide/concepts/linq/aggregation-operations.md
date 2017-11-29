---
title: "Операции статистической обработки (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f47e92c-5dd2-4007-baf4-c5fe5dc3b4a8
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9d4b07eeb1d09d7db0f75d96629c816f66dbb128
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="aggregation-operations-visual-basic"></a><span data-ttu-id="d1cd1-102">Операции статистической обработки (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d1cd1-102">Aggregation Operations (Visual Basic)</span></span>
<span data-ttu-id="d1cd1-103">Статистическая операция вычисляет одно значение по коллекции значений.</span><span class="sxs-lookup"><span data-stu-id="d1cd1-103">An aggregation operation computes a single value from a collection of values.</span></span> <span data-ttu-id="d1cd1-104">Например, статистической обработкой является вычисление средней дневной температуры с использованием значений дневной температуры за месяц.</span><span class="sxs-lookup"><span data-stu-id="d1cd1-104">An example of an aggregation operation is calculating the average daily temperature from a month's worth of daily temperature values.</span></span>  
  
 <span data-ttu-id="d1cd1-105">На приведенном ниже рисунке показаны результаты двух различных операций агрегирования с последовательностью чисел.</span><span class="sxs-lookup"><span data-stu-id="d1cd1-105">The following illustration shows the results of two different aggregation operations on a sequence of numbers.</span></span> <span data-ttu-id="d1cd1-106">Первая операция суммирует числа.</span><span class="sxs-lookup"><span data-stu-id="d1cd1-106">The first operation sums the numbers.</span></span> <span data-ttu-id="d1cd1-107">Вторая операция возвращает максимальное значение в последовательности.</span><span class="sxs-lookup"><span data-stu-id="d1cd1-107">The second operation returns the maximum value in the sequence.</span></span>  
  
 <span data-ttu-id="d1cd1-108">![Операции агрегирования LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_aggregation.png "LINQ_Aggregation")</span><span class="sxs-lookup"><span data-stu-id="d1cd1-108">![LINQ Aggregation Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_aggregation.png "LINQ_Aggregation")</span></span>  
  
 <span data-ttu-id="d1cd1-109">В следующем разделе перечислены методы стандартных операторов запросов, которые выполняют операции агрегирования.</span><span class="sxs-lookup"><span data-stu-id="d1cd1-109">The standard query operator methods that perform aggregation operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d1cd1-110">Методы</span><span class="sxs-lookup"><span data-stu-id="d1cd1-110">Methods</span></span>  
  
|<span data-ttu-id="d1cd1-111">Имя метода</span><span class="sxs-lookup"><span data-stu-id="d1cd1-111">Method Name</span></span>|<span data-ttu-id="d1cd1-112">Описание</span><span class="sxs-lookup"><span data-stu-id="d1cd1-112">Description</span></span>|<span data-ttu-id="d1cd1-113">Синтаксис выражения запроса Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d1cd1-113">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="d1cd1-114">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="d1cd1-114">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="d1cd1-115">Статистическое выражение</span><span class="sxs-lookup"><span data-stu-id="d1cd1-115">Aggregate</span></span>|<span data-ttu-id="d1cd1-116">Выполняет пользовательскую операцию агрегирования со значениями коллекции.</span><span class="sxs-lookup"><span data-stu-id="d1cd1-116">Performs a custom aggregation operation on the values of a collection.</span></span>|<span data-ttu-id="d1cd1-117">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="d1cd1-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d1cd1-118">Метод Average</span><span class="sxs-lookup"><span data-stu-id="d1cd1-118">Average</span></span>|<span data-ttu-id="d1cd1-119">Вычисляет среднее значение коллекции значений.</span><span class="sxs-lookup"><span data-stu-id="d1cd1-119">Calculates the average value of a collection of values.</span></span>|`Aggregate … In … Into Average()`|<xref:System.Linq.Enumerable.Average%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d1cd1-120">Счетчик</span><span class="sxs-lookup"><span data-stu-id="d1cd1-120">Count</span></span>|<span data-ttu-id="d1cd1-121">Подсчитывает число элементов в коллекции (при необходимости только те элементы, которые удовлетворяют функции предиката).</span><span class="sxs-lookup"><span data-stu-id="d1cd1-121">Counts the elements in a collection, optionally only those elements that satisfy a predicate function.</span></span>|`Aggregate … In … Into Count()`|<xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d1cd1-122">LongCount</span><span class="sxs-lookup"><span data-stu-id="d1cd1-122">LongCount</span></span>|<span data-ttu-id="d1cd1-123">Подсчитывает число элементов в большой коллекции (при необходимости только те элементы, которые удовлетворяют функции предиката).</span><span class="sxs-lookup"><span data-stu-id="d1cd1-123">Counts the elements in a large collection, optionally only those elements that satisfy a predicate function.</span></span>|`Aggregate … In … Into LongCount()`|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d1cd1-124">Максимум</span><span class="sxs-lookup"><span data-stu-id="d1cd1-124">Max</span></span>|<span data-ttu-id="d1cd1-125">Определяет максимальное значение в коллекции.</span><span class="sxs-lookup"><span data-stu-id="d1cd1-125">Determines the maximum value in a collection.</span></span>|`Aggregate … In … Into Max()`|<xref:System.Linq.Enumerable.Max%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d1cd1-126">Минимум</span><span class="sxs-lookup"><span data-stu-id="d1cd1-126">Min</span></span>|<span data-ttu-id="d1cd1-127">Определяет минимальное значение в коллекции.</span><span class="sxs-lookup"><span data-stu-id="d1cd1-127">Determines the minimum value in a collection.</span></span>|`Aggregate … In … Into Min()`|<xref:System.Linq.Enumerable.Min%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d1cd1-128">Sum</span><span class="sxs-lookup"><span data-stu-id="d1cd1-128">Sum</span></span>|<span data-ttu-id="d1cd1-129">Вычисляет сумму значений в коллекции.</span><span class="sxs-lookup"><span data-stu-id="d1cd1-129">Calculates the sum of the values in a collection.</span></span>|`Aggregate … In … Into Sum()`|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="d1cd1-130">Примеры синтаксиса выражений запросов</span><span class="sxs-lookup"><span data-stu-id="d1cd1-130">Query Expression Syntax Examples</span></span>  
  
### <a name="average"></a><span data-ttu-id="d1cd1-131">Метод Average</span><span class="sxs-lookup"><span data-stu-id="d1cd1-131">Average</span></span>  
 <span data-ttu-id="d1cd1-132">Следующий пример кода использует `Aggregate Into Average` предложения в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] для вычисления средней температуры в массиве чисел, представляющих температуру.</span><span class="sxs-lookup"><span data-stu-id="d1cd1-132">The following code example uses the `Aggregate Into Average` clause in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] to calculate the average temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_1.vb)]  
  
### <a name="count"></a><span data-ttu-id="d1cd1-133">Счетчик</span><span class="sxs-lookup"><span data-stu-id="d1cd1-133">Count</span></span>  
 <span data-ttu-id="d1cd1-134">Следующий пример кода использует `Aggregate Into Count` предложения в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] для подсчета количества значений в массиве, которые больше или равно 80.</span><span class="sxs-lookup"><span data-stu-id="d1cd1-134">The following code example uses the `Aggregate Into Count` clause in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] to count the number of values in an array that are greater than or equal to 80.</span></span>  
  
 [!code-vb[CsLINQAggregating#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_2.vb)]  
  
### <a name="longcount"></a><span data-ttu-id="d1cd1-135">LongCount</span><span class="sxs-lookup"><span data-stu-id="d1cd1-135">LongCount</span></span>  
 <span data-ttu-id="d1cd1-136">Следующий пример кода использует `Aggregate Into LongCount` предложение для подсчета количества значений в массиве.</span><span class="sxs-lookup"><span data-stu-id="d1cd1-136">The following code example uses the `Aggregate Into LongCount` clause to count the number of values in an array.</span></span>  
  
 [!code-vb[CsLINQAggregating#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_3.vb)]  
  
### <a name="max"></a><span data-ttu-id="d1cd1-137">Максимум</span><span class="sxs-lookup"><span data-stu-id="d1cd1-137">Max</span></span>  
 <span data-ttu-id="d1cd1-138">Следующий пример кода использует `Aggregate Into Max` предложение для вычисления самой высокой температуры в массиве чисел, представляющих температуру.</span><span class="sxs-lookup"><span data-stu-id="d1cd1-138">The following code example uses the `Aggregate Into Max` clause  to calculate the maximum temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_4.vb)]  
  
### <a name="min"></a><span data-ttu-id="d1cd1-139">Минимум</span><span class="sxs-lookup"><span data-stu-id="d1cd1-139">Min</span></span>  
 <span data-ttu-id="d1cd1-140">Следующий пример кода использует `Aggregate Into Min` предложение для вычисления минимального температуры в массиве чисел, представляющих температуру.</span><span class="sxs-lookup"><span data-stu-id="d1cd1-140">The following code example uses the `Aggregate Into Min` clause  to calculate the minimum temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_5.vb)]  
  
### <a name="sum"></a><span data-ttu-id="d1cd1-141">Sum</span><span class="sxs-lookup"><span data-stu-id="d1cd1-141">Sum</span></span>  
 <span data-ttu-id="d1cd1-142">Следующий пример кода использует `Aggregate Into Sum` предложения для расчета общего расхода на основании массива значений, представляющих расходы.</span><span class="sxs-lookup"><span data-stu-id="d1cd1-142">The following code example uses the `Aggregate Into Sum` clause  to calculate the total expense amount from an array of values that represent expenses.</span></span>  
  
 [!code-vb[CsLINQAggregating#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_6.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d1cd1-143">См. также</span><span class="sxs-lookup"><span data-stu-id="d1cd1-143">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="d1cd1-144">Общие сведения о стандартных операторах запроса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d1cd1-144">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="d1cd1-145">Предложение Aggregate</span><span class="sxs-lookup"><span data-stu-id="d1cd1-145">Aggregate Clause</span></span>](../../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [<span data-ttu-id="d1cd1-146">Как: вычисление значений столбцов в текстовом CSV-файле (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d1cd1-146">How to: Compute Column Values in a CSV Text File (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-compute-column-values-in-a-csv-text-file-linq.md)  
 <span data-ttu-id="d1cd1-147">[How to: Count, Sum, or Average Data](../../../../visual-basic/programming-guide/language-features/linq/how-to-count-sum-or-average-data-by-using-linq.md) (Практическое руководство. Выполнение функций Count, Sum и Average)</span><span class="sxs-lookup"><span data-stu-id="d1cd1-147">[How to: Count, Sum, or Average Data](../../../../visual-basic/programming-guide/language-features/linq/how-to-count-sum-or-average-data-by-using-linq.md)</span></span>  
 <span data-ttu-id="d1cd1-148">[How to: Find the Minimum or Maximum Value in a Query Result](../../../../visual-basic/programming-guide/language-features/linq/how-to-find-the-minimum-or-maximum-value-in-a-query-result.md) (Практическое руководство. Нахождение минимального или максимального значения в результатах запроса)</span><span class="sxs-lookup"><span data-stu-id="d1cd1-148">[How to: Find the Minimum or Maximum Value in a Query Result](../../../../visual-basic/programming-guide/language-features/linq/how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)</span></span>  
 [<span data-ttu-id="d1cd1-149">Как: запрос самого большого файла или файлов в дереве каталогов (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d1cd1-149">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)  
 [<span data-ttu-id="d1cd1-150">Как: запрос общее число байтов в наборе папок (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d1cd1-150">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)
