---
title: Операции над множествами (C#)
ms.date: 07/20/2015
ms.assetid: 7c589367-ef8f-4161-9050-642c47e6bf63
ms.openlocfilehash: 44a145a625b5e2e16d2469b20f8cfda1858560a2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79167937"
---
# <a name="set-operations-c"></a><span data-ttu-id="b190e-102">Операции над множествами (C#)</span><span class="sxs-lookup"><span data-stu-id="b190e-102">Set Operations (C#)</span></span>
<span data-ttu-id="b190e-103">Операции над множествами в LINQ — это операции запросов, результирующие наборы которых основываются на наличии или отсутствии эквивалентных элементов в одной или другой коллекции (или наборе).</span><span class="sxs-lookup"><span data-stu-id="b190e-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="b190e-104">Методы стандартных операторов запросов, которые выполняют операции над множествами, перечислены в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="b190e-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b190e-105">Методы</span><span class="sxs-lookup"><span data-stu-id="b190e-105">Methods</span></span>  
  
|<span data-ttu-id="b190e-106">Имя метода</span><span class="sxs-lookup"><span data-stu-id="b190e-106">Method Name</span></span>|<span data-ttu-id="b190e-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="b190e-107">Description</span></span>|<span data-ttu-id="b190e-108">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="b190e-108">C# Query Expression Syntax</span></span>|<span data-ttu-id="b190e-109">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="b190e-109">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="b190e-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="b190e-110">Distinct</span></span>|<span data-ttu-id="b190e-111">Удаляет повторяющиеся значения из коллекции.</span><span class="sxs-lookup"><span data-stu-id="b190e-111">Removes duplicate values from a collection.</span></span>|<span data-ttu-id="b190e-112">Не применяется</span><span class="sxs-lookup"><span data-stu-id="b190e-112">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b190e-113">Исключения</span><span class="sxs-lookup"><span data-stu-id="b190e-113">Except</span></span>|<span data-ttu-id="b190e-114">Возвращает разность множеств, т. е. элементы одной коллекции, которые отсутствуют во второй.</span><span class="sxs-lookup"><span data-stu-id="b190e-114">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="b190e-115">Не применяется</span><span class="sxs-lookup"><span data-stu-id="b190e-115">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b190e-116">Пересечение</span><span class="sxs-lookup"><span data-stu-id="b190e-116">Intersect</span></span>|<span data-ttu-id="b190e-117">Возвращает пересечение множеств, т. е. элементы, присутствующие в каждой из двух коллекций.</span><span class="sxs-lookup"><span data-stu-id="b190e-117">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="b190e-118">Не применяется</span><span class="sxs-lookup"><span data-stu-id="b190e-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b190e-119">Union</span><span class="sxs-lookup"><span data-stu-id="b190e-119">Union</span></span>|<span data-ttu-id="b190e-120">Возвращает объединение множеств, т. е. уникальные элементы, присутствующие в одной из двух коллекций.</span><span class="sxs-lookup"><span data-stu-id="b190e-120">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="b190e-121">Не применяется</span><span class="sxs-lookup"><span data-stu-id="b190e-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="b190e-122">Сравнение операций над множествами</span><span class="sxs-lookup"><span data-stu-id="b190e-122">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="b190e-123">Distinct</span><span class="sxs-lookup"><span data-stu-id="b190e-123">Distinct</span></span>  
 <span data-ttu-id="b190e-124">В следующем примере показано поведение метода <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> применительно к последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="b190e-124">The following example depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="b190e-125">Возвращаемая последовательность содержит уникальные элементы из входной последовательности.</span><span class="sxs-lookup"><span data-stu-id="b190e-125">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 ![График, демонстрирующий поведение Distinct&#40;&#41;.](./media/set-operations/distinct-method-behavior.png)  

 [!code-csharp-interactive[Distinct](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#1)]
  
### <a name="except"></a><span data-ttu-id="b190e-127">Исключения</span><span class="sxs-lookup"><span data-stu-id="b190e-127">Except</span></span>  
 <span data-ttu-id="b190e-128">В следующем примере показано поведение <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b190e-128">The following example depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b190e-129">Возвращаемая последовательность содержит только те элементы из первой входной последовательности, которых нет во второй.</span><span class="sxs-lookup"><span data-stu-id="b190e-129">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="b190e-130">![График, отображающий действие Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Демонстрирует поведение Except.")</span><span class="sxs-lookup"><span data-stu-id="b190e-130">![Graphic showing the action of Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Shows the behavior of Except.")</span></span>  
  
[!code-csharp-interactive[Except](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#2)]

### <a name="intersect"></a><span data-ttu-id="b190e-131">Пересечение</span><span class="sxs-lookup"><span data-stu-id="b190e-131">Intersect</span></span>  
 <span data-ttu-id="b190e-132">В следующем примере показано поведение <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b190e-132">The following example depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b190e-133">Возвращаемая последовательность содержит элементы, общие для обеих входных последовательностей.</span><span class="sxs-lookup"><span data-stu-id="b190e-133">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 ![График, отображающий пересечение двух пакетов.](./media/set-operations/intersection-two-sequences.png)  

[!code-csharp-interactive[Intersect](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#3)]

### <a name="union"></a><span data-ttu-id="b190e-135">Union</span><span class="sxs-lookup"><span data-stu-id="b190e-135">Union</span></span>  
 <span data-ttu-id="b190e-136">В следующем примере показана операция объединения двух последовательностей символов.</span><span class="sxs-lookup"><span data-stu-id="b190e-136">The following example depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="b190e-137">Возвращаемая последовательность содержит уникальные элементы из обеих входных последовательностей.</span><span class="sxs-lookup"><span data-stu-id="b190e-137">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 ![График, показывающий объединение двух пакетов.](./media/set-operations/union-operation-two-sequences.png)  

[!code-csharp-interactive[Union](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#4)]

## <a name="see-also"></a><span data-ttu-id="b190e-139">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b190e-139">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="b190e-140">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="b190e-140">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="b190e-141">Практическое руководство. Объединение и сравнение коллекций строк (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="b190e-141">How to combine and compare string collections (LINQ) (C#)</span></span>](./how-to-combine-and-compare-string-collections-linq.md)
- [<span data-ttu-id="b190e-142">Нахождение разности множеств между двумя списками (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="b190e-142">How to find the set difference between two lists (LINQ) (C#)</span></span>](./how-to-find-the-set-difference-between-two-lists-linq.md)
