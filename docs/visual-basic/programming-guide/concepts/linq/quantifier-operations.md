---
title: "Операции, использующие кванторы (Visual Basic) | Документы Microsoft"
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
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
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
ms.openlocfilehash: 4e0c982508640ef1ecb47d477d3e9330198474ca
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="quantifier-operations-visual-basic"></a><span data-ttu-id="c3bd3-102">Операции, использующие кванторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c3bd3-102">Quantifier Operations (Visual Basic)</span></span>
<span data-ttu-id="c3bd3-103">Квантификаторы возвращают <xref:System.Boolean>значение, указывающее, является ли некоторые или все элементы в последовательности, удовлетворяющих заданному условию.</xref:System.Boolean></span><span class="sxs-lookup"><span data-stu-id="c3bd3-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="c3bd3-104">На следующем рисунке показано два различных квантификатора двух различных исходных последовательностей.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="c3bd3-105">Первая операция проверяет, если один или несколько элементов имеют символ «A», а результат — `true`.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="c3bd3-106">Вторая операция проверяет, если все элементы — символ «A», а результат — `true`.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 <span data-ttu-id="c3bd3-107">![Операции, использующие кванторы LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span><span class="sxs-lookup"><span data-stu-id="c3bd3-107">![LINQ Quantifier Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span></span>  
  
 <span data-ttu-id="c3bd3-108">В следующем разделе перечислены методы стандартных операторов запросов, выполняющие операции, использующие кванторы.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c3bd3-109">Методы</span><span class="sxs-lookup"><span data-stu-id="c3bd3-109">Methods</span></span>  
  
|<span data-ttu-id="c3bd3-110">Имя метода</span><span class="sxs-lookup"><span data-stu-id="c3bd3-110">Method Name</span></span>|<span data-ttu-id="c3bd3-111">Описание</span><span class="sxs-lookup"><span data-stu-id="c3bd3-111">Description</span></span>|<span data-ttu-id="c3bd3-112">Синтаксис выражения запроса для Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c3bd3-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="c3bd3-113">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c3bd3-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="c3bd3-114">Все</span><span class="sxs-lookup"><span data-stu-id="c3bd3-114">All</span></span>|<span data-ttu-id="c3bd3-115">Определяет, является ли элементы последовательности удовлетворяют условию.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into All(…)`|<span data-ttu-id="c3bd3-116"><xref:System.Linq.Enumerable.All%2A?displayProperty=fullName></xref:System.Linq.Enumerable.All%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c3bd3-116"><xref:System.Linq.Enumerable.All%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="c3bd3-117"><xref:System.Linq.Queryable.All%2A?displayProperty=fullName></xref:System.Linq.Queryable.All%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c3bd3-117"><xref:System.Linq.Queryable.All%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="c3bd3-118">Любой</span><span class="sxs-lookup"><span data-stu-id="c3bd3-118">Any</span></span>|<span data-ttu-id="c3bd3-119">Определяет, является ли все элементы в последовательности удовлетворяют условию.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-119">Determines whether any elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into Any()`|<span data-ttu-id="c3bd3-120"><xref:System.Linq.Enumerable.Any%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Any%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c3bd3-120"><xref:System.Linq.Enumerable.Any%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="c3bd3-121"><xref:System.Linq.Queryable.Any%2A?displayProperty=fullName></xref:System.Linq.Queryable.Any%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c3bd3-121"><xref:System.Linq.Queryable.Any%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="c3bd3-122">Содержит</span><span class="sxs-lookup"><span data-stu-id="c3bd3-122">Contains</span></span>|<span data-ttu-id="c3bd3-123">Определяет, содержит ли последовательность указанный элемент.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-123">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="c3bd3-124">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-124">Not applicable.</span></span>|<span data-ttu-id="c3bd3-125"><xref:System.Linq.Enumerable.Contains%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Contains%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c3bd3-125"><xref:System.Linq.Enumerable.Contains%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="c3bd3-126"><xref:System.Linq.Queryable.Contains%2A?displayProperty=fullName></xref:System.Linq.Queryable.Contains%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c3bd3-126"><xref:System.Linq.Queryable.Contains%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="c3bd3-127">Примеры синтаксиса выражений запросов</span><span class="sxs-lookup"><span data-stu-id="c3bd3-127">Query Expression Syntax Examples</span></span>  
 <span data-ttu-id="c3bd3-128">В этих примерах используются `Aggregate` предложение в Visual Basic как часть условия фильтрации в запросе LINQ.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-128">These examples use the `Aggregate` clause in Visual Basic as part of the filtering condition in a LINQ query.</span></span>  
  
 <span data-ttu-id="c3bd3-129">В следующем примере используется `Aggregate` предложения и <xref:System.Linq.Enumerable.All%2A>метод расширения для возвращения из коллекции тех людей, чьи животными все старше указанного срока.</xref:System.Linq.Enumerable.All%2A></span><span class="sxs-lookup"><span data-stu-id="c3bd3-129">The following example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.All%2A> extension method to return from a collection those people whose pets are all older than a specified age.</span></span>  
  
 <span data-ttu-id="c3bd3-130">[!code-vb[CsLINQAnyAll&#1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c3bd3-130">[!code-vb[CsLINQAnyAll#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_1.vb)]</span></span>  
  
 <span data-ttu-id="c3bd3-131">В следующем примере используется `Aggregate` предложения и <xref:System.Linq.Enumerable.Any%2A>метод расширения для возвращения из коллекции тем, кто не менее одного pet, старше указанного срока.</xref:System.Linq.Enumerable.Any%2A></span><span class="sxs-lookup"><span data-stu-id="c3bd3-131">The next example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.Any%2A> extension method to return from a collection those people who have at least one pet that is older than a specified age.</span></span>  
  
 <span data-ttu-id="c3bd3-132">[!code-vb[CsLINQAnyAll&#2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="c3bd3-132">[!code-vb[CsLINQAnyAll#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3bd3-133">См. также</span><span class="sxs-lookup"><span data-stu-id="c3bd3-133">See Also</span></span>  
 <span data-ttu-id="c3bd3-134"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="c3bd3-134"><xref:System.Linq></span></span>   
<span data-ttu-id="c3bd3-135"> [Общие сведения о стандартных операторах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="c3bd3-135"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="c3bd3-136"> [Aggregate-предложение](../../../../visual-basic/language-reference/queries/aggregate-clause.md) </span><span class="sxs-lookup"><span data-stu-id="c3bd3-136"> [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) </span></span>  
<span data-ttu-id="c3bd3-137"> [Практическое руководство: запрос к предложениям, содержащим указанный набор слов (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)</span><span class="sxs-lookup"><span data-stu-id="c3bd3-137"> [How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)</span></span>
