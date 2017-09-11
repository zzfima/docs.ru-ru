---
title: "Операции агрегирования (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 6fc035e5-7639-48b8-bc7f-b093dd31b039
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6c453bdccdb3af026fe4f4fb79c6e33e44e7a8f0
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="aggregation-operations-c"></a><span data-ttu-id="7d3ac-102">Операции агрегирования (C#)</span><span class="sxs-lookup"><span data-stu-id="7d3ac-102">Aggregation Operations (C#)</span></span>
<span data-ttu-id="7d3ac-103">Статистическая операция вычисляет одно значение по коллекции значений.</span><span class="sxs-lookup"><span data-stu-id="7d3ac-103">An aggregation operation computes a single value from a collection of values.</span></span> <span data-ttu-id="7d3ac-104">Например, статистической обработкой является вычисление средней дневной температуры с использованием значений дневной температуры за месяц.</span><span class="sxs-lookup"><span data-stu-id="7d3ac-104">An example of an aggregation operation is calculating the average daily temperature from a month's worth of daily temperature values.</span></span>  
  
 <span data-ttu-id="7d3ac-105">На приведенном ниже рисунке показаны результаты двух различных операций агрегирования с последовательностью чисел.</span><span class="sxs-lookup"><span data-stu-id="7d3ac-105">The following illustration shows the results of two different aggregation operations on a sequence of numbers.</span></span> <span data-ttu-id="7d3ac-106">Первая операция суммирует числа.</span><span class="sxs-lookup"><span data-stu-id="7d3ac-106">The first operation sums the numbers.</span></span> <span data-ttu-id="7d3ac-107">Вторая операция возвращает максимальное значение в последовательности.</span><span class="sxs-lookup"><span data-stu-id="7d3ac-107">The second operation returns the maximum value in the sequence.</span></span>  
  
 <span data-ttu-id="7d3ac-108">![Операции агрегирования LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_aggregation.png "LINQ_Aggregation")</span><span class="sxs-lookup"><span data-stu-id="7d3ac-108">![LINQ Aggregation Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_aggregation.png "LINQ_Aggregation")</span></span>  
  
 <span data-ttu-id="7d3ac-109">В следующем разделе перечислены методы стандартных операторов запросов, которые выполняют операции агрегирования.</span><span class="sxs-lookup"><span data-stu-id="7d3ac-109">The standard query operator methods that perform aggregation operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7d3ac-110">Методы</span><span class="sxs-lookup"><span data-stu-id="7d3ac-110">Methods</span></span>  
  
|<span data-ttu-id="7d3ac-111">Имя метода</span><span class="sxs-lookup"><span data-stu-id="7d3ac-111">Method Name</span></span>|<span data-ttu-id="7d3ac-112">Описание</span><span class="sxs-lookup"><span data-stu-id="7d3ac-112">Description</span></span>|<span data-ttu-id="7d3ac-113">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="7d3ac-113">C# Query Expression Syntax</span></span>|<span data-ttu-id="7d3ac-114">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="7d3ac-114">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="7d3ac-115">Статистическое выражение</span><span class="sxs-lookup"><span data-stu-id="7d3ac-115">Aggregate</span></span>|<span data-ttu-id="7d3ac-116">Выполняет пользовательскую операцию агрегирования со значениями коллекции.</span><span class="sxs-lookup"><span data-stu-id="7d3ac-116">Performs a custom aggregation operation on the values of a collection.</span></span>|<span data-ttu-id="7d3ac-117">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="7d3ac-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=fullName>|  
|<span data-ttu-id="7d3ac-118">Среднее значение</span><span class="sxs-lookup"><span data-stu-id="7d3ac-118">Average</span></span>|<span data-ttu-id="7d3ac-119">Вычисляет среднее значение коллекции значений.</span><span class="sxs-lookup"><span data-stu-id="7d3ac-119">Calculates the average value of a collection of values.</span></span>|<span data-ttu-id="7d3ac-120">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="7d3ac-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Average%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=fullName>|  
|<span data-ttu-id="7d3ac-121">Счетчик</span><span class="sxs-lookup"><span data-stu-id="7d3ac-121">Count</span></span>|<span data-ttu-id="7d3ac-122">Подсчитывает число элементов в коллекции (при необходимости только те элементы, которые удовлетворяют функции предиката).</span><span class="sxs-lookup"><span data-stu-id="7d3ac-122">Counts the elements in a collection, optionally only those elements that satisfy a predicate function.</span></span>|<span data-ttu-id="7d3ac-123">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="7d3ac-123">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Count%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=fullName>|  
|<span data-ttu-id="7d3ac-124">LongCount</span><span class="sxs-lookup"><span data-stu-id="7d3ac-124">LongCount</span></span>|<span data-ttu-id="7d3ac-125">Подсчитывает число элементов в большой коллекции (при необходимости только те элементы, которые удовлетворяют функции предиката).</span><span class="sxs-lookup"><span data-stu-id="7d3ac-125">Counts the elements in a large collection, optionally only those elements that satisfy a predicate function.</span></span>|<span data-ttu-id="7d3ac-126">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="7d3ac-126">Not applicable.</span></span>|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=fullName>|  
|<span data-ttu-id="7d3ac-127">Макс</span><span class="sxs-lookup"><span data-stu-id="7d3ac-127">Max</span></span>|<span data-ttu-id="7d3ac-128">Определяет максимальное значение в коллекции.</span><span class="sxs-lookup"><span data-stu-id="7d3ac-128">Determines the maximum value in a collection.</span></span>|<span data-ttu-id="7d3ac-129">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="7d3ac-129">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Max%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=fullName>|  
|<span data-ttu-id="7d3ac-130">мин.</span><span class="sxs-lookup"><span data-stu-id="7d3ac-130">Min</span></span>|<span data-ttu-id="7d3ac-131">Определяет минимальное значение в коллекции.</span><span class="sxs-lookup"><span data-stu-id="7d3ac-131">Determines the minimum value in a collection.</span></span>|<span data-ttu-id="7d3ac-132">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="7d3ac-132">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Min%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=fullName>|  
|<span data-ttu-id="7d3ac-133">Sum</span><span class="sxs-lookup"><span data-stu-id="7d3ac-133">Sum</span></span>|<span data-ttu-id="7d3ac-134">Вычисляет сумму значений в коллекции.</span><span class="sxs-lookup"><span data-stu-id="7d3ac-134">Calculates the sum of the values in a collection.</span></span>|<span data-ttu-id="7d3ac-135">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="7d3ac-135">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=fullName>|  
  
## <a name="see-also"></a><span data-ttu-id="7d3ac-136">См. также</span><span class="sxs-lookup"><span data-stu-id="7d3ac-136">See Also</span></span>  
 <span data-ttu-id="7d3ac-137"><xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="7d3ac-137"><xref:System.Linq></span></span>   
 <span data-ttu-id="7d3ac-138">[Общие сведения о стандартных операторах запроса (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="7d3ac-138">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 <span data-ttu-id="7d3ac-139">[Практическое руководство. Вычисление значений столбцов в текстовом CSV-файле (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-compute-column-values-in-a-csv-text-file-linq.md) </span><span class="sxs-lookup"><span data-stu-id="7d3ac-139">[How to: Compute Column Values in a CSV Text File (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-compute-column-values-in-a-csv-text-file-linq.md) </span></span>  
 <span data-ttu-id="7d3ac-140">[Практическое руководство. Запрос самого большого файла или файлов в дереве папок (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq.md) </span><span class="sxs-lookup"><span data-stu-id="7d3ac-140">[How to: Query for the Largest File or Files in a Directory Tree (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq.md) </span></span>  
 [<span data-ttu-id="7d3ac-141">Практическое руководство. Запрос общего числа байтов в наборе папок (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="7d3ac-141">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq.md)

