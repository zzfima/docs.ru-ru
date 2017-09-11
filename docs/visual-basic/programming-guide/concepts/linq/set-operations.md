---
title: "Набор операций (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 2b06e822-e030-438f-9db7-ee402bd3a706
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2b9fd7ec122fff2601296ae3a46bb7607b2b32ef
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="set-operations-visual-basic"></a><span data-ttu-id="bef6a-102">Набор операций (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bef6a-102">Set Operations (Visual Basic)</span></span>
<span data-ttu-id="bef6a-103">Операции с наборами в LINQ см. в операции запроса, образующие результирующий набор, основанный на наличии или отсутствии эквивалентных элементов в одной или разных коллекций (или наборы).</span><span class="sxs-lookup"><span data-stu-id="bef6a-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="bef6a-104">В следующем разделе перечислены методы стандартных операторов запросов, выполняющие операции с множествами.</span><span class="sxs-lookup"><span data-stu-id="bef6a-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bef6a-105">Методы</span><span class="sxs-lookup"><span data-stu-id="bef6a-105">Methods</span></span>  
  
|<span data-ttu-id="bef6a-106">Имя метода</span><span class="sxs-lookup"><span data-stu-id="bef6a-106">Method Name</span></span>|<span data-ttu-id="bef6a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="bef6a-107">Description</span></span>|<span data-ttu-id="bef6a-108">Синтаксис выражения запроса для Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bef6a-108">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="bef6a-109">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="bef6a-109">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="bef6a-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="bef6a-110">Distinct</span></span>|<span data-ttu-id="bef6a-111">Удаляет повторяющиеся значения из коллекции.</span><span class="sxs-lookup"><span data-stu-id="bef6a-111">Removes duplicate values from a collection.</span></span>|`Distinct`|<span data-ttu-id="bef6a-112"><xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="bef6a-112"><xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="bef6a-113"><xref:System.Linq.Queryable.Distinct%2A?displayProperty=fullName></xref:System.Linq.Queryable.Distinct%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="bef6a-113"><xref:System.Linq.Queryable.Distinct%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="bef6a-114">Исключения</span><span class="sxs-lookup"><span data-stu-id="bef6a-114">Except</span></span>|<span data-ttu-id="bef6a-115">Возвращает разность множеств — означает, что элементы одной коллекции, которые не отображаются во второй коллекции.</span><span class="sxs-lookup"><span data-stu-id="bef6a-115">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="bef6a-116">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="bef6a-116">Not applicable.</span></span>|<span data-ttu-id="bef6a-117"><xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="bef6a-117"><xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="bef6a-118"><xref:System.Linq.Queryable.Except%2A?displayProperty=fullName></xref:System.Linq.Queryable.Except%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="bef6a-118"><xref:System.Linq.Queryable.Except%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="bef6a-119">Пересечение</span><span class="sxs-lookup"><span data-stu-id="bef6a-119">Intersect</span></span>|<span data-ttu-id="bef6a-120">Возвращает пересечение, что означает элементов, отображаемых в каждой из двух коллекций.</span><span class="sxs-lookup"><span data-stu-id="bef6a-120">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="bef6a-121">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="bef6a-121">Not applicable.</span></span>|<span data-ttu-id="bef6a-122"><xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="bef6a-122"><xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="bef6a-123"><xref:System.Linq.Queryable.Intersect%2A?displayProperty=fullName></xref:System.Linq.Queryable.Intersect%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="bef6a-123"><xref:System.Linq.Queryable.Intersect%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="bef6a-124">Объединение</span><span class="sxs-lookup"><span data-stu-id="bef6a-124">Union</span></span>|<span data-ttu-id="bef6a-125">Возвращает объединение, означающее уникальных элементов, содержащихся в любой из коллекций.</span><span class="sxs-lookup"><span data-stu-id="bef6a-125">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="bef6a-126">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="bef6a-126">Not applicable.</span></span>|<span data-ttu-id="bef6a-127"><xref:System.Linq.Enumerable.Union%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Union%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="bef6a-127"><xref:System.Linq.Enumerable.Union%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="bef6a-128"><xref:System.Linq.Queryable.Union%2A?displayProperty=fullName></xref:System.Linq.Queryable.Union%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="bef6a-128"><xref:System.Linq.Queryable.Union%2A?displayProperty=fullName></span></span>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="bef6a-129">Сравнение операций</span><span class="sxs-lookup"><span data-stu-id="bef6a-129">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="bef6a-130">Distinct</span><span class="sxs-lookup"><span data-stu-id="bef6a-130">Distinct</span></span>  
 <span data-ttu-id="bef6a-131">На следующем рисунке показано поведение <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName>метод последовательность символов.</xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="bef6a-131">The following illustration depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName> method on a sequence of characters.</span></span> <span data-ttu-id="bef6a-132">Возвращаемая последовательность содержит уникальные элементы из входной последовательности.</span><span class="sxs-lookup"><span data-stu-id="bef6a-132">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 <span data-ttu-id="bef6a-133">![График, демонстрирующий поведение Distinct(). ] (../../../../csharp/programming-guide/concepts/linq/media/distinct.png "Distinct")</span><span class="sxs-lookup"><span data-stu-id="bef6a-133">![Graphic showing the behavior of Distinct&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/distinct.png "Distinct")</span></span>  
  
### <a name="except"></a><span data-ttu-id="bef6a-134">Исключения</span><span class="sxs-lookup"><span data-stu-id="bef6a-134">Except</span></span>  
 <span data-ttu-id="bef6a-135">На следующем рисунке показано поведение <xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName>.</xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="bef6a-135">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="bef6a-136">Возвращаемая последовательность содержит только те элементы из первой входной последовательностью, которые не находятся в второй входной последовательности.</span><span class="sxs-lookup"><span data-stu-id="bef6a-136">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="bef6a-137">![График, отображающий действие Except(). ](../../../../csharp/programming-guide/concepts/linq/media/except.png "Except")</span><span class="sxs-lookup"><span data-stu-id="bef6a-137">![Graphic showing the action of Except&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/except.png "Except")</span></span>  
  
### <a name="intersect"></a><span data-ttu-id="bef6a-138">Пересечение</span><span class="sxs-lookup"><span data-stu-id="bef6a-138">Intersect</span></span>  
 <span data-ttu-id="bef6a-139">На следующем рисунке показано поведение <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName>.</xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="bef6a-139">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="bef6a-140">Возвращаемая последовательность содержит элементы, общие для обеих входных последовательностей.</span><span class="sxs-lookup"><span data-stu-id="bef6a-140">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 <span data-ttu-id="bef6a-141">![График, отображающий пересечение двух пакетов. ] (../../../../csharp/programming-guide/concepts/linq/media/intersect.png "Intersect")</span><span class="sxs-lookup"><span data-stu-id="bef6a-141">![Graphic showing the intersection of two sequences.](../../../../csharp/programming-guide/concepts/linq/media/intersect.png "Intersect")</span></span>  
  
### <a name="union"></a><span data-ttu-id="bef6a-142">Объединение</span><span class="sxs-lookup"><span data-stu-id="bef6a-142">Union</span></span>  
 <span data-ttu-id="bef6a-143">Ниже показаны операции объединения двух последовательностей символов.</span><span class="sxs-lookup"><span data-stu-id="bef6a-143">The following illustration depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="bef6a-144">Возвращаемая последовательность содержит уникальные элементы из обеих входных последовательностей.</span><span class="sxs-lookup"><span data-stu-id="bef6a-144">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 <span data-ttu-id="bef6a-145">![График, показывающий объединение двух последовательностей. ](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")</span><span class="sxs-lookup"><span data-stu-id="bef6a-145">![Graphic showing the union of two sequences.](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")</span></span>  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="bef6a-146">Пример синтаксиса выражения запроса</span><span class="sxs-lookup"><span data-stu-id="bef6a-146">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="bef6a-147">В следующем примере используется `Distinct` предложение в запросе LINQ для возвращения уникальных чисел из списка целых чисел.</span><span class="sxs-lookup"><span data-stu-id="bef6a-147">The following example uses the `Distinct` clause in a LINQ query to return the unique numbers from a list of integers.</span></span>  
  
 <span data-ttu-id="bef6a-148">[!code-vb[CsLINQSetOps&#1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/set-operations_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="bef6a-148">[!code-vb[CsLINQSetOps#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/set-operations_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bef6a-149">См. также</span><span class="sxs-lookup"><span data-stu-id="bef6a-149">See Also</span></span>  
 <span data-ttu-id="bef6a-150"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="bef6a-150"><xref:System.Linq></span></span>   
<span data-ttu-id="bef6a-151"> [Общие сведения о стандартных операторах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="bef6a-151"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="bef6a-152"> [Предложение DISTINCT](../../../../visual-basic/language-reference/queries/distinct-clause.md) </span><span class="sxs-lookup"><span data-stu-id="bef6a-152"> [Distinct Clause](../../../../visual-basic/language-reference/queries/distinct-clause.md) </span></span>  
<span data-ttu-id="bef6a-153"> [Практическое руководство: объединение и сравнение коллекций строк (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md) </span><span class="sxs-lookup"><span data-stu-id="bef6a-153"> [How to: Combine and Compare String Collections (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md) </span></span>  
<span data-ttu-id="bef6a-154"> [Практическое руководство: нахождение разности наборов между двумя списками (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)</span><span class="sxs-lookup"><span data-stu-id="bef6a-154"> [How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)</span></span>
