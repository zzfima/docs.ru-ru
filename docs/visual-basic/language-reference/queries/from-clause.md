---
title: "Предложение From (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QueryFrom
- vb.QueryFromIn
- vb.QueryFromLet
helpviewer_keywords:
- queries [Visual Basic], From
- From clause [Visual Basic]
- From statement [Visual Basic]
ms.assetid: 83e3665e-68a0-4540-a3a3-3d777a0f95d5
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0ecdc8b70fb1ae164a6c78998ce11db9938fbb56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="from-clause-visual-basic"></a><span data-ttu-id="44cea-102">Предложение From (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="44cea-102">From Clause (Visual Basic)</span></span>
<span data-ttu-id="44cea-103">Указывает один или несколько переменных диапазона и коллекции для запроса.</span><span class="sxs-lookup"><span data-stu-id="44cea-103">Specifies one or more range variables and a collection to query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44cea-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="44cea-104">Syntax</span></span>  
  
```  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="44cea-105">Части</span><span class="sxs-lookup"><span data-stu-id="44cea-105">Parts</span></span>  
  
|<span data-ttu-id="44cea-106">Термин</span><span class="sxs-lookup"><span data-stu-id="44cea-106">Term</span></span>|<span data-ttu-id="44cea-107">Определение</span><span class="sxs-lookup"><span data-stu-id="44cea-107">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="44cea-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="44cea-108">Required.</span></span> <span data-ttu-id="44cea-109">Объект *переменной диапазона* используется для итерации элементов коллекции.</span><span class="sxs-lookup"><span data-stu-id="44cea-109">A *range variable* used to iterate through the elements of the collection.</span></span> <span data-ttu-id="44cea-110">Переменная диапазона используется для ссылки на каждый член `collection` как запрос осуществляет итерацию по `collection`.</span><span class="sxs-lookup"><span data-stu-id="44cea-110">A range variable is used to refer to each member of the `collection` as the query iterates through the `collection`.</span></span> <span data-ttu-id="44cea-111">Должно быть перечислимым типом.</span><span class="sxs-lookup"><span data-stu-id="44cea-111">Must be an enumerable type.</span></span>|  
|`type`|<span data-ttu-id="44cea-112">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="44cea-112">Optional.</span></span> <span data-ttu-id="44cea-113">Тип параметра `element`.</span><span class="sxs-lookup"><span data-stu-id="44cea-113">The type of `element`.</span></span> <span data-ttu-id="44cea-114">Если не `type` указан, тип `element` выводится из `collection`.</span><span class="sxs-lookup"><span data-stu-id="44cea-114">If no `type` is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="44cea-115">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="44cea-115">Required.</span></span> <span data-ttu-id="44cea-116">Ссылается на коллекцию, которой будет отправлен запрос.</span><span class="sxs-lookup"><span data-stu-id="44cea-116">Refers to the collection to be queried.</span></span> <span data-ttu-id="44cea-117">Должно быть перечислимым типом.</span><span class="sxs-lookup"><span data-stu-id="44cea-117">Must be an enumerable type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44cea-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="44cea-118">Remarks</span></span>  
 <span data-ttu-id="44cea-119">`From` Предложение используется для определения источника данных для запроса и переменные, которые используются для ссылки на элемент исходной коллекции.</span><span class="sxs-lookup"><span data-stu-id="44cea-119">The `From` clause is used to identify the source data for a query and the variables that are used to refer to an element from the source collection.</span></span> <span data-ttu-id="44cea-120">Эти переменные называются *переменные диапазона*.</span><span class="sxs-lookup"><span data-stu-id="44cea-120">These variables are called *range variables*.</span></span> <span data-ttu-id="44cea-121">`From` Предложение является обязательным для запроса, за исключением случаев `Aggregate` предложение используется для обнаружения, возвращает только агрегированными результаты запроса.</span><span class="sxs-lookup"><span data-stu-id="44cea-121">The `From` clause is required for a query, except when the `Aggregate` clause is used to identify a query that returns only aggregated results.</span></span> <span data-ttu-id="44cea-122">Дополнительные сведения см. в разделе [предложение Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span><span class="sxs-lookup"><span data-stu-id="44cea-122">For more information, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="44cea-123">Можно указать несколько `From` предложения в запросе, чтобы определить несколько коллекций для объединения.</span><span class="sxs-lookup"><span data-stu-id="44cea-123">You can specify multiple `From` clauses in a query to identify multiple collections to be joined.</span></span> <span data-ttu-id="44cea-124">При указании нескольких коллекций, они воспринимаются независимо друг от друга, или можно объединить их, если они относятся.</span><span class="sxs-lookup"><span data-stu-id="44cea-124">When multiple collections are specified, they are iterated over independently, or you can join them if they are related.</span></span> <span data-ttu-id="44cea-125">Объединение коллекций неявно с помощью `Select` предложение, или явно с использованием `Join` или `Group Join` предложения.</span><span class="sxs-lookup"><span data-stu-id="44cea-125">You can join collections implicitly by using the `Select` clause, or explicitly by using the `Join` or `Group Join` clauses.</span></span> <span data-ttu-id="44cea-126">В качестве альтернативы можно указать несколько переменных диапазонов и коллекций в одном `From` вместе с каждой связанной переменной диапазона и коллекций, разделенных запятой от остальных.</span><span class="sxs-lookup"><span data-stu-id="44cea-126">As an alternative, you can specify multiple range variables and collections in a single `From` clause, with each related range variable and collection separated from the others by a comma.</span></span> <span data-ttu-id="44cea-127">В следующем примере кода показано, как параметры синтаксиса для `From` предложения.</span><span class="sxs-lookup"><span data-stu-id="44cea-127">The following code example shows both syntax options for the `From` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#21](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_1.vb)]  
  
 <span data-ttu-id="44cea-128">`From` Предложение определяет область запроса, что похоже на область `For` цикла.</span><span class="sxs-lookup"><span data-stu-id="44cea-128">The `From` clause defines the scope of a query, which is similar to the scope of a `For` loop.</span></span> <span data-ttu-id="44cea-129">Таким образом, каждый `element` переменная диапазона в область запроса должен иметь уникальное имя.</span><span class="sxs-lookup"><span data-stu-id="44cea-129">Therefore, each `element` range variable in the scope of a query must have a unique name.</span></span> <span data-ttu-id="44cea-130">Поскольку можно указать несколько `From` предложения запроса, последующие `From` предложений можно ссылаться на переменные диапазона в `From` предложения или они могут ссылаться на переменные диапазона при выполнении предыдущего `From` предложения.</span><span class="sxs-lookup"><span data-stu-id="44cea-130">Because you can specify multiple `From` clauses for a query, subsequent `From` clauses can refer to range variables in the `From` clause, or they can refer to range variables in a previous `From` clause.</span></span> <span data-ttu-id="44cea-131">Например, в следующем примере показано во вложенной `From` предложение, где коллекция во втором предложении основана на свойстве переменной диапазона в первом предложении.</span><span class="sxs-lookup"><span data-stu-id="44cea-131">For example, the following example shows a nested `From` clause where the collection in the second clause is based on a property of the range variable in the first clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#22](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_2.vb)]  
  
 <span data-ttu-id="44cea-132">Каждый `From` предложение может следовать любое сочетание предложений дополнительных запросов для уточнения запроса.</span><span class="sxs-lookup"><span data-stu-id="44cea-132">Each `From` clause can be followed by any combination of additional query clauses to refine the query.</span></span> <span data-ttu-id="44cea-133">Можно уточнить запрос следующими способами:</span><span class="sxs-lookup"><span data-stu-id="44cea-133">You can refine the query in the following ways:</span></span>  
  
-   <span data-ttu-id="44cea-134">Объединить несколько коллекций неявно с помощью `From` и `Select` предложений, или явно с использованием `Join` или `Group Join` предложения.</span><span class="sxs-lookup"><span data-stu-id="44cea-134">Combine multiple collections implicitly by using the `From` and `Select` clauses, or explicitly by using the `Join` or `Group Join` clauses.</span></span>  
  
-   <span data-ttu-id="44cea-135">Используйте `Where` предложение для фильтрации результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="44cea-135">Use the `Where` clause to filter the query result.</span></span>  
  
-   <span data-ttu-id="44cea-136">Отсортировать результаты с помощью `Order By` предложения.</span><span class="sxs-lookup"><span data-stu-id="44cea-136">Sort the result by using the `Order By` clause.</span></span>  
  
-   <span data-ttu-id="44cea-137">Сгруппировать аналогичные результаты с помощью `Group By` предложения.</span><span class="sxs-lookup"><span data-stu-id="44cea-137">Group similar results together by using the `Group By` clause.</span></span>  
  
-   <span data-ttu-id="44cea-138">Используйте `Aggregate` предложение для идентификации агрегатных функций для вычисления результата всего запроса.</span><span class="sxs-lookup"><span data-stu-id="44cea-138">Use the `Aggregate` clause to identify aggregate functions to evaluate for the whole query result.</span></span>  
  
-   <span data-ttu-id="44cea-139">Используйте `Let` предложение для представления переменной итерации, значение которого определяется выражения, а не коллекцию.</span><span class="sxs-lookup"><span data-stu-id="44cea-139">Use the `Let` clause to introduce an iteration variable whose value is determined by an expression instead of a collection.</span></span>  
  
-   <span data-ttu-id="44cea-140">Используйте `Distinct` предложений, чтобы игнорировать повторяющиеся результаты запроса.</span><span class="sxs-lookup"><span data-stu-id="44cea-140">Use the `Distinct` clause to ignore duplicate query results.</span></span>  
  
-   <span data-ttu-id="44cea-141">Определения частей результат, возвращаемый с помощью `Skip`, `Take`, `Skip While`, и `Take While` предложения.</span><span class="sxs-lookup"><span data-stu-id="44cea-141">Identify parts of the result to return by using the `Skip`, `Take`, `Skip While`, and `Take While` clauses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44cea-142">Пример</span><span class="sxs-lookup"><span data-stu-id="44cea-142">Example</span></span>  
 <span data-ttu-id="44cea-143">В следующем запросе используется выражение `From` предложение для объявления переменной диапазона `cust` для каждого `Customer` объекта в `customers` коллекции.</span><span class="sxs-lookup"><span data-stu-id="44cea-143">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="44cea-144">`Where` Предложение использует переменную диапазона для ограничения выходных данных для клиентов из заданной области.</span><span class="sxs-lookup"><span data-stu-id="44cea-144">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="44cea-145">`For Each` Цикл имя компании для каждого клиента в результатах запроса.</span><span class="sxs-lookup"><span data-stu-id="44cea-145">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="44cea-146">См. также</span><span class="sxs-lookup"><span data-stu-id="44cea-146">See Also</span></span>  
 [<span data-ttu-id="44cea-147">Запросы</span><span class="sxs-lookup"><span data-stu-id="44cea-147">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 <span data-ttu-id="44cea-148">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="44cea-148">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>  
 [<span data-ttu-id="44cea-149">Оператор For Each...Next</span><span class="sxs-lookup"><span data-stu-id="44cea-149">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [<span data-ttu-id="44cea-150">Оператор For...Next</span><span class="sxs-lookup"><span data-stu-id="44cea-150">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="44cea-151">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="44cea-151">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="44cea-152">Предложения Where</span><span class="sxs-lookup"><span data-stu-id="44cea-152">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)  
 [<span data-ttu-id="44cea-153">Предложение Aggregate</span><span class="sxs-lookup"><span data-stu-id="44cea-153">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [<span data-ttu-id="44cea-154">Предложение Distinct</span><span class="sxs-lookup"><span data-stu-id="44cea-154">Distinct Clause</span></span>](../../../visual-basic/language-reference/queries/distinct-clause.md)  
 [<span data-ttu-id="44cea-155">Предложение Join</span><span class="sxs-lookup"><span data-stu-id="44cea-155">Join Clause</span></span>](../../../visual-basic/language-reference/queries/join-clause.md)  
 [<span data-ttu-id="44cea-156">Предложение Group Join</span><span class="sxs-lookup"><span data-stu-id="44cea-156">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [<span data-ttu-id="44cea-157">Предложение Order By</span><span class="sxs-lookup"><span data-stu-id="44cea-157">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [<span data-ttu-id="44cea-158">Предложение Let</span><span class="sxs-lookup"><span data-stu-id="44cea-158">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)  
 [<span data-ttu-id="44cea-159">Предложение Skip</span><span class="sxs-lookup"><span data-stu-id="44cea-159">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)  
 [<span data-ttu-id="44cea-160">Предложение Take</span><span class="sxs-lookup"><span data-stu-id="44cea-160">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)  
 [<span data-ttu-id="44cea-161">Предложение Skip While</span><span class="sxs-lookup"><span data-stu-id="44cea-161">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [<span data-ttu-id="44cea-162">Предложение Take While</span><span class="sxs-lookup"><span data-stu-id="44cea-162">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
