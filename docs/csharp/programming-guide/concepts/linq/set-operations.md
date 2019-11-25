---
title: Операции над множествами (C#)
ms.date: 07/20/2015
ms.assetid: 7c589367-ef8f-4161-9050-642c47e6bf63
ms.openlocfilehash: 7fd61e17c37c3d9056159cf4ec3ccfafa2ceb871
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "74140932"
---
# <a name="set-operations-c"></a><span data-ttu-id="120c7-102">Операции над множествами (C#)</span><span class="sxs-lookup"><span data-stu-id="120c7-102">Set Operations (C#)</span></span>
<span data-ttu-id="120c7-103">Операции над множествами в LINQ — это операции запросов, результирующие наборы которых основываются на наличии или отсутствии эквивалентных элементов в одной или другой коллекции (или наборе).</span><span class="sxs-lookup"><span data-stu-id="120c7-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="120c7-104">Методы стандартных операторов запросов, которые выполняют операции над множествами, перечислены в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="120c7-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="120c7-105">Методы</span><span class="sxs-lookup"><span data-stu-id="120c7-105">Methods</span></span>  
  
|<span data-ttu-id="120c7-106">Имя метода</span><span class="sxs-lookup"><span data-stu-id="120c7-106">Method Name</span></span>|<span data-ttu-id="120c7-107">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="120c7-107">Description</span></span>|<span data-ttu-id="120c7-108">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="120c7-108">C# Query Expression Syntax</span></span>|<span data-ttu-id="120c7-109">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="120c7-109">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="120c7-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="120c7-110">Distinct</span></span>|<span data-ttu-id="120c7-111">Удаляет повторяющиеся значения из коллекции.</span><span class="sxs-lookup"><span data-stu-id="120c7-111">Removes duplicate values from a collection.</span></span>|<span data-ttu-id="120c7-112">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="120c7-112">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="120c7-113">Исключения</span><span class="sxs-lookup"><span data-stu-id="120c7-113">Except</span></span>|<span data-ttu-id="120c7-114">Возвращает разность множеств, т. е. элементы одной коллекции, которые отсутствуют во второй.</span><span class="sxs-lookup"><span data-stu-id="120c7-114">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="120c7-115">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="120c7-115">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="120c7-116">Пересечение</span><span class="sxs-lookup"><span data-stu-id="120c7-116">Intersect</span></span>|<span data-ttu-id="120c7-117">Возвращает пересечение множеств, т. е. элементы, присутствующие в каждой из двух коллекций.</span><span class="sxs-lookup"><span data-stu-id="120c7-117">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="120c7-118">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="120c7-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="120c7-119">Объединение</span><span class="sxs-lookup"><span data-stu-id="120c7-119">Union</span></span>|<span data-ttu-id="120c7-120">Возвращает объединение множеств, т. е. уникальные элементы, присутствующие в одной из двух коллекций.</span><span class="sxs-lookup"><span data-stu-id="120c7-120">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="120c7-121">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="120c7-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="120c7-122">Сравнение операций над множествами</span><span class="sxs-lookup"><span data-stu-id="120c7-122">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="120c7-123">Distinct</span><span class="sxs-lookup"><span data-stu-id="120c7-123">Distinct</span></span>  
 <span data-ttu-id="120c7-124">На следующем рисунке показано поведение метода <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> применительно к последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="120c7-124">The following illustration depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="120c7-125">Возвращаемая последовательность содержит уникальные элементы из входной последовательности.</span><span class="sxs-lookup"><span data-stu-id="120c7-125">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 ![График, демонстрирующий поведение Distinct&#40;&#41;.](./media/set-operations/distinct-method-behavior.png)  
  
### <a name="except"></a><span data-ttu-id="120c7-127">Исключения</span><span class="sxs-lookup"><span data-stu-id="120c7-127">Except</span></span>  
 <span data-ttu-id="120c7-128">На следующем рисунке показано поведение <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="120c7-128">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="120c7-129">Возвращаемая последовательность содержит только те элементы из первой входной последовательности, которых нет во второй.</span><span class="sxs-lookup"><span data-stu-id="120c7-129">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="120c7-130">![График, отображающий действие Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Демонстрирует поведение Except.")</span><span class="sxs-lookup"><span data-stu-id="120c7-130">![Graphic showing the action of Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Shows the behavior of Except.")</span></span>  
  
### <a name="intersect"></a><span data-ttu-id="120c7-131">Пересечение</span><span class="sxs-lookup"><span data-stu-id="120c7-131">Intersect</span></span>  
 <span data-ttu-id="120c7-132">На следующем рисунке показано поведение <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="120c7-132">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="120c7-133">Возвращаемая последовательность содержит элементы, общие для обеих входных последовательностей.</span><span class="sxs-lookup"><span data-stu-id="120c7-133">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 ![График, отображающий пересечение двух последовательностей.](./media/set-operations/intersection-two-sequences.png)  
 
### <a name="union"></a><span data-ttu-id="120c7-135">Объединение</span><span class="sxs-lookup"><span data-stu-id="120c7-135">Union</span></span>  
 <span data-ttu-id="120c7-136">На следующем рисунке показана операция объединения двух последовательностей символов.</span><span class="sxs-lookup"><span data-stu-id="120c7-136">The following illustration depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="120c7-137">Возвращаемая последовательность содержит уникальные элементы из обеих входных последовательностей.</span><span class="sxs-lookup"><span data-stu-id="120c7-137">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 ![График, показывающий объединение двух последовательностей.](./media/set-operations/union-operation-two-sequences.png)  
## <a name="see-also"></a><span data-ttu-id="120c7-139">См. также</span><span class="sxs-lookup"><span data-stu-id="120c7-139">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="120c7-140">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="120c7-140">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="120c7-141">Практическое руководство. Объединение и сравнение коллекций строк (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="120c7-141">How to combine and compare string collections (LINQ) (C#)</span></span>](./how-to-combine-and-compare-string-collections-linq.md)
- [<span data-ttu-id="120c7-142">Практическое руководство. Нахождение разности множеств между двумя списками (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="120c7-142">How to: Find the Set Difference Between Two Lists (LINQ) (C#)</span></span>](./how-to-find-the-set-difference-between-two-lists-linq.md)
