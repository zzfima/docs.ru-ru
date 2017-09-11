---
title: "Запросы (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- queries [Visual Basic]
- LINQ, queries
ms.assetid: 8edc717c-4a24-4cbc-9c16-11f479c935db
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4a178714055076537033fbda32d7c7c1c544351d
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="queries-visual-basic"></a><span data-ttu-id="83989-102">Запросы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83989-102">Queries (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="83989-103">позволяет создавать [!INCLUDE[vbteclinqext](../../../csharp/getting-started/includes/vbteclinqext_md.md)] выражения в коде.</span><span class="sxs-lookup"><span data-stu-id="83989-103"> enables you to create [!INCLUDE[vbteclinqext](../../../csharp/getting-started/includes/vbteclinqext_md.md)] expressions in your code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="83989-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="83989-104">In This Section</span></span>  
 [<span data-ttu-id="83989-105">Предложение Aggregate</span><span class="sxs-lookup"><span data-stu-id="83989-105">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 <span data-ttu-id="83989-106">Описывает `Aggregate` предложение, которое применяет одну или несколько агрегатных функций к коллекции.</span><span class="sxs-lookup"><span data-stu-id="83989-106">Describes the `Aggregate` clause, which applies one or more aggregate functions to a collection.</span></span>  
  
 [<span data-ttu-id="83989-107">Предложение Distinct</span><span class="sxs-lookup"><span data-stu-id="83989-107">Distinct Clause</span></span>](../../../visual-basic/language-reference/queries/distinct-clause.md)  
 <span data-ttu-id="83989-108">Описывает `Distinct` предложение, которое ограничивает значения текущей переменной диапазона, чтобы исключить повторяющиеся значения в результатах запроса.</span><span class="sxs-lookup"><span data-stu-id="83989-108">Describes the `Distinct` clause, which restricts the values of the current range variable to eliminate duplicate values in query results.</span></span>  
  
 [<span data-ttu-id="83989-109">Предложение From</span><span class="sxs-lookup"><span data-stu-id="83989-109">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 <span data-ttu-id="83989-110">Описывает `From` предложение, которое определяет коллекцию и переменную диапазона для запроса.</span><span class="sxs-lookup"><span data-stu-id="83989-110">Describes the `From` clause, which specifies a collection and a range variable for a query.</span></span>  
  
 [<span data-ttu-id="83989-111">Предложение Group By</span><span class="sxs-lookup"><span data-stu-id="83989-111">Group By Clause</span></span>](../../../visual-basic/language-reference/queries/group-by-clause.md)  
 <span data-ttu-id="83989-112">Описывает `Group By` предложение, которое группирует элементы результата запроса и может использоваться для применения статистических функций к каждой группе.</span><span class="sxs-lookup"><span data-stu-id="83989-112">Describes the `Group By` clause, which groups the elements of a query result and can be used to apply aggregate functions to each group.</span></span>  
  
 [<span data-ttu-id="83989-113">Предложение Group Join</span><span class="sxs-lookup"><span data-stu-id="83989-113">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 <span data-ttu-id="83989-114">Описывает `Group Join` предложение, которое объединяет две коллекции в одну иерархическую коллекцию.</span><span class="sxs-lookup"><span data-stu-id="83989-114">Describes the `Group Join` clause, which combines two collections into a single hierarchical collection.</span></span>  
  
 [<span data-ttu-id="83989-115">Предложение Join</span><span class="sxs-lookup"><span data-stu-id="83989-115">Join Clause</span></span>](../../../visual-basic/language-reference/queries/join-clause.md)  
 <span data-ttu-id="83989-116">Описывает `Join` предложение, которое объединяет две коллекции в одну коллекцию.</span><span class="sxs-lookup"><span data-stu-id="83989-116">Describes the `Join` clause, which combines two collections into a single collection.</span></span>  
  
 [<span data-ttu-id="83989-117">Предложение Let</span><span class="sxs-lookup"><span data-stu-id="83989-117">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)  
 <span data-ttu-id="83989-118">Описывает `Let` предложение, которое вычисляет значение и присваивает его новой переменной в запросе.</span><span class="sxs-lookup"><span data-stu-id="83989-118">Describes the `Let` clause, which computes a value and assigns it to a new variable in the query.</span></span>  
  
 [<span data-ttu-id="83989-119">Предложение Order By</span><span class="sxs-lookup"><span data-stu-id="83989-119">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 <span data-ttu-id="83989-120">Описывает `Order By` предложение, которое указывает порядок сортировки для столбцов в запросе.</span><span class="sxs-lookup"><span data-stu-id="83989-120">Describes the `Order By` clause, which specifies the sort order for columns in a query.</span></span>  
  
 [<span data-ttu-id="83989-121">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="83989-121">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 <span data-ttu-id="83989-122">Описывает `Select` предложение, которое объявляет набор переменных диапазона для запроса.</span><span class="sxs-lookup"><span data-stu-id="83989-122">Describes the `Select` clause, which declares a set of range variables for a query.</span></span>  
  
 [<span data-ttu-id="83989-123">Предложение Skip</span><span class="sxs-lookup"><span data-stu-id="83989-123">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)  
 <span data-ttu-id="83989-124">Описывает `Skip` предложение, которое обходит заданное число элементов в коллекции и затем возвращает оставшиеся элементы.</span><span class="sxs-lookup"><span data-stu-id="83989-124">Describes the `Skip` clause, which bypasses a specified number of elements in a collection and then returns the remaining elements.</span></span>  
  
 [<span data-ttu-id="83989-125">Предложение Skip While</span><span class="sxs-lookup"><span data-stu-id="83989-125">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 <span data-ttu-id="83989-126">Описывает `Skip While` предложение, которое обходит элементы в коллекции, пока заданное условие является `true` и затем возвращает оставшиеся элементы.</span><span class="sxs-lookup"><span data-stu-id="83989-126">Describes the `Skip While` clause, which bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements.</span></span>  
  
 [<span data-ttu-id="83989-127">Предложение Take</span><span class="sxs-lookup"><span data-stu-id="83989-127">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)  
 <span data-ttu-id="83989-128">Описывает `Take` предложение, которое возвращает заданное число смежных элементов из начала коллекции.</span><span class="sxs-lookup"><span data-stu-id="83989-128">Describes the `Take` clause, which returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
 [<span data-ttu-id="83989-129">Предложение Take While</span><span class="sxs-lookup"><span data-stu-id="83989-129">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 <span data-ttu-id="83989-130">Описывает `Take While` предложение, которое включает элементы в коллекции, пока заданное условие является `true` и обходит оставшиеся элементы.</span><span class="sxs-lookup"><span data-stu-id="83989-130">Describes the `Take While` clause, which includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
 [<span data-ttu-id="83989-131">Предложения Where</span><span class="sxs-lookup"><span data-stu-id="83989-131">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)  
 <span data-ttu-id="83989-132">Описывает `Where` предложение, которое задает условие фильтрации для запроса.</span><span class="sxs-lookup"><span data-stu-id="83989-132">Describes the `Where` clause, which specifies a filtering condition for a query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83989-133">См. также</span><span class="sxs-lookup"><span data-stu-id="83989-133">See Also</span></span>  
 <span data-ttu-id="83989-134">[LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="83989-134">[LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="83989-135"> [Введение в LINQ в Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span><span class="sxs-lookup"><span data-stu-id="83989-135"> [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
