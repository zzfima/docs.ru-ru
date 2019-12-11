---
title: Операции над множествами (C#)
ms.date: 07/20/2015
ms.assetid: 7c589367-ef8f-4161-9050-642c47e6bf63
ms.openlocfilehash: 22079b1d41533803f694af210f98bc9fb8a5b322
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711871"
---
# <a name="set-operations-c"></a><span data-ttu-id="03097-102">Операции над множествами (C#)</span><span class="sxs-lookup"><span data-stu-id="03097-102">Set Operations (C#)</span></span>
<span data-ttu-id="03097-103">Операции над множествами в LINQ — это операции запросов, результирующие наборы которых основываются на наличии или отсутствии эквивалентных элементов в одной или другой коллекции (или наборе).</span><span class="sxs-lookup"><span data-stu-id="03097-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="03097-104">Методы стандартных операторов запросов, которые выполняют операции над множествами, перечислены в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="03097-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="03097-105">Методы</span><span class="sxs-lookup"><span data-stu-id="03097-105">Methods</span></span>  
  
|<span data-ttu-id="03097-106">Имя метода</span><span class="sxs-lookup"><span data-stu-id="03097-106">Method Name</span></span>|<span data-ttu-id="03097-107">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="03097-107">Description</span></span>|<span data-ttu-id="03097-108">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="03097-108">C# Query Expression Syntax</span></span>|<span data-ttu-id="03097-109">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="03097-109">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="03097-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="03097-110">Distinct</span></span>|<span data-ttu-id="03097-111">Удаляет повторяющиеся значения из коллекции.</span><span class="sxs-lookup"><span data-stu-id="03097-111">Removes duplicate values from a collection.</span></span>|<span data-ttu-id="03097-112">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="03097-112">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="03097-113">Исключения</span><span class="sxs-lookup"><span data-stu-id="03097-113">Except</span></span>|<span data-ttu-id="03097-114">Возвращает разность множеств, т. е. элементы одной коллекции, которые отсутствуют во второй.</span><span class="sxs-lookup"><span data-stu-id="03097-114">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="03097-115">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="03097-115">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="03097-116">Пересечение</span><span class="sxs-lookup"><span data-stu-id="03097-116">Intersect</span></span>|<span data-ttu-id="03097-117">Возвращает пересечение множеств, т. е. элементы, присутствующие в каждой из двух коллекций.</span><span class="sxs-lookup"><span data-stu-id="03097-117">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="03097-118">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="03097-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="03097-119">Объединение</span><span class="sxs-lookup"><span data-stu-id="03097-119">Union</span></span>|<span data-ttu-id="03097-120">Возвращает объединение множеств, т. е. уникальные элементы, присутствующие в одной из двух коллекций.</span><span class="sxs-lookup"><span data-stu-id="03097-120">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="03097-121">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="03097-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="03097-122">Сравнение операций над множествами</span><span class="sxs-lookup"><span data-stu-id="03097-122">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="03097-123">Distinct</span><span class="sxs-lookup"><span data-stu-id="03097-123">Distinct</span></span>  
 <span data-ttu-id="03097-124">В следующем примере показано поведение метода <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> применительно к последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="03097-124">The following example depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="03097-125">Возвращаемая последовательность содержит уникальные элементы из входной последовательности.</span><span class="sxs-lookup"><span data-stu-id="03097-125">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 ![График, демонстрирующий поведение Distinct&#40;&#41;.](./media/set-operations/distinct-method-behavior.png)  
 
 [!code-csharp-interactive[Distinct](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#1)]
  
### <a name="except"></a><span data-ttu-id="03097-127">Исключения</span><span class="sxs-lookup"><span data-stu-id="03097-127">Except</span></span>  
 <span data-ttu-id="03097-128">В следующем примере показано поведение <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="03097-128">The following example depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="03097-129">Возвращаемая последовательность содержит только те элементы из первой входной последовательности, которых нет во второй.</span><span class="sxs-lookup"><span data-stu-id="03097-129">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="03097-130">![График, отображающий действие Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Демонстрирует поведение Except.")</span><span class="sxs-lookup"><span data-stu-id="03097-130">![Graphic showing the action of Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Shows the behavior of Except.")</span></span>  
  
[!code-csharp-interactive[Except](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#2)]

### <a name="intersect"></a><span data-ttu-id="03097-131">Пересечение</span><span class="sxs-lookup"><span data-stu-id="03097-131">Intersect</span></span>  
 <span data-ttu-id="03097-132">В следующем примере показано поведение <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="03097-132">The following example depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="03097-133">Возвращаемая последовательность содержит элементы, общие для обеих входных последовательностей.</span><span class="sxs-lookup"><span data-stu-id="03097-133">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 ![График, отображающий пересечение двух последовательностей.](./media/set-operations/intersection-two-sequences.png)  
 
[!code-csharp-interactive[Intersect](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#3)]

### <a name="union"></a><span data-ttu-id="03097-135">Объединение</span><span class="sxs-lookup"><span data-stu-id="03097-135">Union</span></span>  
 <span data-ttu-id="03097-136">В следующем примере показана операция объединения двух последовательностей символов.</span><span class="sxs-lookup"><span data-stu-id="03097-136">The following example depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="03097-137">Возвращаемая последовательность содержит уникальные элементы из обеих входных последовательностей.</span><span class="sxs-lookup"><span data-stu-id="03097-137">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 ![График, показывающий объединение двух последовательностей.](./media/set-operations/union-operation-two-sequences.png)  

[!code-csharp-interactive[Union](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#4)]
 
## <a name="see-also"></a><span data-ttu-id="03097-139">См. также</span><span class="sxs-lookup"><span data-stu-id="03097-139">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="03097-140">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="03097-140">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="03097-141">Практическое руководство. Объединение и сравнение коллекций строк (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="03097-141">How to combine and compare string collections (LINQ) (C#)</span></span>](./how-to-combine-and-compare-string-collections-linq.md)
- [<span data-ttu-id="03097-142">Практическое руководство. Нахождение разности множеств между двумя списками (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="03097-142">How to: Find the Set Difference Between Two Lists (LINQ) (C#)</span></span>](./how-to-find-the-set-difference-between-two-lists-linq.md)
