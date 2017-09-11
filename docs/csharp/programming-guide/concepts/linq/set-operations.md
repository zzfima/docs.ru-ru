---
title: "Операции над множествами (C#)"
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
ms.assetid: 7c589367-ef8f-4161-9050-642c47e6bf63
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
ms.openlocfilehash: 121dcd4d41dcfea332c45031a5fbed594e2f1e3e
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="set-operations-c"></a><span data-ttu-id="d6355-102">Операции над множествами (C#)</span><span class="sxs-lookup"><span data-stu-id="d6355-102">Set Operations (C#)</span></span>
<span data-ttu-id="d6355-103">Операции над множествами в LINQ — это операции запросов, результирующие наборы которых основываются на наличии или отсутствии эквивалентных элементов в одной или другой коллекции (или наборе).</span><span class="sxs-lookup"><span data-stu-id="d6355-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="d6355-104">Методы стандартных операторов запросов, которые выполняют операции над множествами, перечислены в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="d6355-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d6355-105">Методы</span><span class="sxs-lookup"><span data-stu-id="d6355-105">Methods</span></span>  
  
|<span data-ttu-id="d6355-106">Имя метода</span><span class="sxs-lookup"><span data-stu-id="d6355-106">Method Name</span></span>|<span data-ttu-id="d6355-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d6355-107">Description</span></span>|<span data-ttu-id="d6355-108">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="d6355-108">C# Query Expression Syntax</span></span>|<span data-ttu-id="d6355-109">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="d6355-109">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="d6355-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="d6355-110">Distinct</span></span>|<span data-ttu-id="d6355-111">Удаляет повторяющиеся значения из коллекции.</span><span class="sxs-lookup"><span data-stu-id="d6355-111">Removes duplicate values from a collection.</span></span>|<span data-ttu-id="d6355-112">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="d6355-112">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=fullName>|  
|<span data-ttu-id="d6355-113">Исключения</span><span class="sxs-lookup"><span data-stu-id="d6355-113">Except</span></span>|<span data-ttu-id="d6355-114">Возвращает разность множеств, т. е. элементы одной коллекции, которые отсутствуют во второй.</span><span class="sxs-lookup"><span data-stu-id="d6355-114">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="d6355-115">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="d6355-115">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=fullName>|  
|<span data-ttu-id="d6355-116">Пересечение</span><span class="sxs-lookup"><span data-stu-id="d6355-116">Intersect</span></span>|<span data-ttu-id="d6355-117">Возвращает пересечение множеств, т. е. элементы, присутствующие в каждой из двух коллекций.</span><span class="sxs-lookup"><span data-stu-id="d6355-117">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="d6355-118">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="d6355-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=fullName>|  
|<span data-ttu-id="d6355-119">Объединение</span><span class="sxs-lookup"><span data-stu-id="d6355-119">Union</span></span>|<span data-ttu-id="d6355-120">Возвращает объединение множеств, т. е. уникальные элементы, присутствующие в одной из двух коллекций.</span><span class="sxs-lookup"><span data-stu-id="d6355-120">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="d6355-121">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="d6355-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=fullName>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="d6355-122">Сравнение операций над множествами</span><span class="sxs-lookup"><span data-stu-id="d6355-122">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="d6355-123">Distinct</span><span class="sxs-lookup"><span data-stu-id="d6355-123">Distinct</span></span>  
 <span data-ttu-id="d6355-124">На следующем рисунке показано поведение метода <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName> применительно к последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="d6355-124">The following illustration depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName> method on a sequence of characters.</span></span> <span data-ttu-id="d6355-125">Возвращаемая последовательность содержит уникальные элементы из входной последовательности.</span><span class="sxs-lookup"><span data-stu-id="d6355-125">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 <span data-ttu-id="d6355-126">![График, демонстрирующий поведение Distinct&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/distinct.png "Distinct")</span><span class="sxs-lookup"><span data-stu-id="d6355-126">![Graphic showing the behavior of Distinct&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/distinct.png "Distinct")</span></span>  
  
### <a name="except"></a><span data-ttu-id="d6355-127">Исключения</span><span class="sxs-lookup"><span data-stu-id="d6355-127">Except</span></span>  
 <span data-ttu-id="d6355-128">На следующем рисунке показано поведение <xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="d6355-128">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="d6355-129">Возвращаемая последовательность содержит только те элементы из первой входной последовательности, которых нет во второй.</span><span class="sxs-lookup"><span data-stu-id="d6355-129">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="d6355-130">![График, отображающий действие Except&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/except.png "Except")</span><span class="sxs-lookup"><span data-stu-id="d6355-130">![Graphic showing the action of Except&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/except.png "Except")</span></span>  
  
### <a name="intersect"></a><span data-ttu-id="d6355-131">Пересечение</span><span class="sxs-lookup"><span data-stu-id="d6355-131">Intersect</span></span>  
 <span data-ttu-id="d6355-132">На следующем рисунке показано поведение <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="d6355-132">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="d6355-133">Возвращаемая последовательность содержит элементы, общие для обеих входных последовательностей.</span><span class="sxs-lookup"><span data-stu-id="d6355-133">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 <span data-ttu-id="d6355-134">![График, отображающий пересечение двух последовательностей.](../../../../csharp/programming-guide/concepts/linq/media/intersect.png "Intersect")</span><span class="sxs-lookup"><span data-stu-id="d6355-134">![Graphic showing the intersection of two sequences.](../../../../csharp/programming-guide/concepts/linq/media/intersect.png "Intersect")</span></span>  
  
### <a name="union"></a><span data-ttu-id="d6355-135">Объединение</span><span class="sxs-lookup"><span data-stu-id="d6355-135">Union</span></span>  
 <span data-ttu-id="d6355-136">На следующем рисунке показана операция объединения двух последовательностей символов.</span><span class="sxs-lookup"><span data-stu-id="d6355-136">The following illustration depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="d6355-137">Возвращаемая последовательность содержит уникальные элементы из обеих входных последовательностей.</span><span class="sxs-lookup"><span data-stu-id="d6355-137">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 <span data-ttu-id="d6355-138">![График, показывающий объединение двух последовательностей.](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")</span><span class="sxs-lookup"><span data-stu-id="d6355-138">![Graphic showing the union of two sequences.](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6355-139">См. также</span><span class="sxs-lookup"><span data-stu-id="d6355-139">See Also</span></span>  
 <span data-ttu-id="d6355-140"><xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="d6355-140"><xref:System.Linq></span></span>   
 <span data-ttu-id="d6355-141">[Общие сведения о стандартных операторах запроса (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="d6355-141">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 <span data-ttu-id="d6355-142">[Практическое руководство. Объединение и сравнение коллекций строк (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md) </span><span class="sxs-lookup"><span data-stu-id="d6355-142">[How to: Combine and Compare String Collections (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md) </span></span>  
 [<span data-ttu-id="d6355-143">Практическое руководство. Нахождение разности множеств между двумя списками (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="d6355-143">How to: Find the Set Difference Between Two Lists (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)

