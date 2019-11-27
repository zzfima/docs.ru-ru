---
title: Предложение From
ms.date: 07/20/2015
f1_keywords:
- vb.QueryFrom
- vb.QueryFromIn
- vb.QueryFromLet
helpviewer_keywords:
- queries [Visual Basic], From
- From clause [Visual Basic]
- From statement [Visual Basic]
ms.assetid: 83e3665e-68a0-4540-a3a3-3d777a0f95d5
ms.openlocfilehash: a63fb41fc2b0ad885acf76ad5d56e446922f5b90
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343780"
---
# <a name="from-clause-visual-basic"></a><span data-ttu-id="dafab-102">Предложение From (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dafab-102">From Clause (Visual Basic)</span></span>
<span data-ttu-id="dafab-103">Указывает одну или несколько переменных диапазона и коллекцию для запроса.</span><span class="sxs-lookup"><span data-stu-id="dafab-103">Specifies one or more range variables and a collection to query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dafab-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dafab-104">Syntax</span></span>  
  
```vb  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="dafab-105">Части</span><span class="sxs-lookup"><span data-stu-id="dafab-105">Parts</span></span>  
  
|<span data-ttu-id="dafab-106">Термин</span><span class="sxs-lookup"><span data-stu-id="dafab-106">Term</span></span>|<span data-ttu-id="dafab-107">Определение</span><span class="sxs-lookup"><span data-stu-id="dafab-107">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="dafab-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="dafab-108">Required.</span></span> <span data-ttu-id="dafab-109">*Переменная диапазона* , используемая для прохода по элементам коллекции.</span><span class="sxs-lookup"><span data-stu-id="dafab-109">A *range variable* used to iterate through the elements of the collection.</span></span> <span data-ttu-id="dafab-110">Переменная диапазона используется для ссылки на каждый элемент `collection`, так как запрос проходит по `collection`.</span><span class="sxs-lookup"><span data-stu-id="dafab-110">A range variable is used to refer to each member of the `collection` as the query iterates through the `collection`.</span></span> <span data-ttu-id="dafab-111">Должен быть перечислимым типом.</span><span class="sxs-lookup"><span data-stu-id="dafab-111">Must be an enumerable type.</span></span>|  
|`type`|<span data-ttu-id="dafab-112">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="dafab-112">Optional.</span></span> <span data-ttu-id="dafab-113">Тип параметра `element`.</span><span class="sxs-lookup"><span data-stu-id="dafab-113">The type of `element`.</span></span> <span data-ttu-id="dafab-114">Если `type` не указано, тип `element` выводится из `collection`.</span><span class="sxs-lookup"><span data-stu-id="dafab-114">If no `type` is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="dafab-115">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="dafab-115">Required.</span></span> <span data-ttu-id="dafab-116">Ссылается на коллекцию, к которой выполняется запрос.</span><span class="sxs-lookup"><span data-stu-id="dafab-116">Refers to the collection to be queried.</span></span> <span data-ttu-id="dafab-117">Должен быть перечислимым типом.</span><span class="sxs-lookup"><span data-stu-id="dafab-117">Must be an enumerable type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dafab-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="dafab-118">Remarks</span></span>  
 <span data-ttu-id="dafab-119">Предложение `From` используется для указания исходных данных для запроса и переменных, которые используются для ссылки на элемент из исходной коллекции.</span><span class="sxs-lookup"><span data-stu-id="dafab-119">The `From` clause is used to identify the source data for a query and the variables that are used to refer to an element from the source collection.</span></span> <span data-ttu-id="dafab-120">Эти переменные называются *переменными диапазона*.</span><span class="sxs-lookup"><span data-stu-id="dafab-120">These variables are called *range variables*.</span></span> <span data-ttu-id="dafab-121">Предложение `From` является обязательным для запроса, за исключением случаев, когда для задания запроса, возвращающего только агрегированные результаты, используется предложение `Aggregate`.</span><span class="sxs-lookup"><span data-stu-id="dafab-121">The `From` clause is required for a query, except when the `Aggregate` clause is used to identify a query that returns only aggregated results.</span></span> <span data-ttu-id="dafab-122">Дополнительные сведения см. в разделе [предложение Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span><span class="sxs-lookup"><span data-stu-id="dafab-122">For more information, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="dafab-123">Можно указать несколько предложений `From` в запросе, чтобы определить несколько коллекций для объединения.</span><span class="sxs-lookup"><span data-stu-id="dafab-123">You can specify multiple `From` clauses in a query to identify multiple collections to be joined.</span></span> <span data-ttu-id="dafab-124">Если указано несколько коллекций, они проходят по отдельности или объединяются, если они связаны.</span><span class="sxs-lookup"><span data-stu-id="dafab-124">When multiple collections are specified, they are iterated over independently, or you can join them if they are related.</span></span> <span data-ttu-id="dafab-125">Коллекции можно объединять неявным образом с помощью предложения `Select` или явно с помощью предложений `Join` или `Group Join`.</span><span class="sxs-lookup"><span data-stu-id="dafab-125">You can join collections implicitly by using the `Select` clause, or explicitly by using the `Join` or `Group Join` clauses.</span></span> <span data-ttu-id="dafab-126">В качестве альтернативы можно указать несколько переменных диапазона и коллекций в одном предложении `From`, где каждая связанная переменная диапазона и коллекция отделены друг от друга запятыми.</span><span class="sxs-lookup"><span data-stu-id="dafab-126">As an alternative, you can specify multiple range variables and collections in a single `From` clause, with each related range variable and collection separated from the others by a comma.</span></span> <span data-ttu-id="dafab-127">В следующем примере кода показаны оба синтаксических параметра для предложения `From`.</span><span class="sxs-lookup"><span data-stu-id="dafab-127">The following code example shows both syntax options for the `From` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#21)]  
  
 <span data-ttu-id="dafab-128">Предложение `From` определяет область запроса, которая аналогична области цикла `For`.</span><span class="sxs-lookup"><span data-stu-id="dafab-128">The `From` clause defines the scope of a query, which is similar to the scope of a `For` loop.</span></span> <span data-ttu-id="dafab-129">Таким образом, каждая переменная диапазона `element` в области запроса должна иметь уникальное имя.</span><span class="sxs-lookup"><span data-stu-id="dafab-129">Therefore, each `element` range variable in the scope of a query must have a unique name.</span></span> <span data-ttu-id="dafab-130">Поскольку можно указать несколько предложений `From` для запроса, последующие предложения `From` могут ссылаться на переменные диапазона в предложении `From` или они могут ссылаться на переменные диапазона в предыдущем предложении `From`.</span><span class="sxs-lookup"><span data-stu-id="dafab-130">Because you can specify multiple `From` clauses for a query, subsequent `From` clauses can refer to range variables in the `From` clause, or they can refer to range variables in a previous `From` clause.</span></span> <span data-ttu-id="dafab-131">Например, в следующем примере показано вложенное предложение `From`, где коллекция во втором предложении основана на свойстве переменной диапазона в первом предложении.</span><span class="sxs-lookup"><span data-stu-id="dafab-131">For example, the following example shows a nested `From` clause where the collection in the second clause is based on a property of the range variable in the first clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#22)]  
  
 <span data-ttu-id="dafab-132">За каждым предложением `From` может следовать любое сочетание дополнительных предложений запроса для уточнения запроса.</span><span class="sxs-lookup"><span data-stu-id="dafab-132">Each `From` clause can be followed by any combination of additional query clauses to refine the query.</span></span> <span data-ttu-id="dafab-133">Запрос можно уточнить следующими способами.</span><span class="sxs-lookup"><span data-stu-id="dafab-133">You can refine the query in the following ways:</span></span>  
  
- <span data-ttu-id="dafab-134">Объедините несколько коллекций неявным образом с помощью предложений `From` и `Select` или явно с помощью предложений `Join` или `Group Join`.</span><span class="sxs-lookup"><span data-stu-id="dafab-134">Combine multiple collections implicitly by using the `From` and `Select` clauses, or explicitly by using the `Join` or `Group Join` clauses.</span></span>  
  
- <span data-ttu-id="dafab-135">Чтобы отфильтровать результат запроса, используйте предложение `Where`.</span><span class="sxs-lookup"><span data-stu-id="dafab-135">Use the `Where` clause to filter the query result.</span></span>  
  
- <span data-ttu-id="dafab-136">Отсортируйте результат с помощью предложения `Order By`.</span><span class="sxs-lookup"><span data-stu-id="dafab-136">Sort the result by using the `Order By` clause.</span></span>  
  
- <span data-ttu-id="dafab-137">Сгруппируйте аналогичные результаты вместе с помощью предложения `Group By`.</span><span class="sxs-lookup"><span data-stu-id="dafab-137">Group similar results together by using the `Group By` clause.</span></span>  
  
- <span data-ttu-id="dafab-138">Используйте предложение `Aggregate`, чтобы определить агрегатные функции для вычисления результата всего запроса.</span><span class="sxs-lookup"><span data-stu-id="dafab-138">Use the `Aggregate` clause to identify aggregate functions to evaluate for the whole query result.</span></span>  
  
- <span data-ttu-id="dafab-139">Используйте предложение `Let`, чтобы ввести переменную итерации, значение которой определяется выражением, а не коллекцией.</span><span class="sxs-lookup"><span data-stu-id="dafab-139">Use the `Let` clause to introduce an iteration variable whose value is determined by an expression instead of a collection.</span></span>  
  
- <span data-ttu-id="dafab-140">Используйте предложение `Distinct` для пропуска повторяющихся результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="dafab-140">Use the `Distinct` clause to ignore duplicate query results.</span></span>  
  
- <span data-ttu-id="dafab-141">Выявление частей результата, возвращаемых с помощью предложений `Skip`, `Take`, `Skip While`и `Take While`.</span><span class="sxs-lookup"><span data-stu-id="dafab-141">Identify parts of the result to return by using the `Skip`, `Take`, `Skip While`, and `Take While` clauses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dafab-142">Пример</span><span class="sxs-lookup"><span data-stu-id="dafab-142">Example</span></span>  
 <span data-ttu-id="dafab-143">Следующее выражение запроса использует предложение `From`, чтобы объявить переменную диапазона `cust` для каждого объекта `Customer` в коллекции `customers`.</span><span class="sxs-lookup"><span data-stu-id="dafab-143">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="dafab-144">Предложение `Where` использует переменную диапазона для ограничения выходных данных для клиентов из указанной области.</span><span class="sxs-lookup"><span data-stu-id="dafab-144">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="dafab-145">Цикл `For Each` отображает название компании для каждого клиента в результатах запроса.</span><span class="sxs-lookup"><span data-stu-id="dafab-145">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="dafab-146">См. также</span><span class="sxs-lookup"><span data-stu-id="dafab-146">See also</span></span>

- [<span data-ttu-id="dafab-147">Запросы</span><span class="sxs-lookup"><span data-stu-id="dafab-147">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- <span data-ttu-id="dafab-148">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dafab-148">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="dafab-149">Оператор For Each...Next</span><span class="sxs-lookup"><span data-stu-id="dafab-149">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="dafab-150">Оператор For...Next</span><span class="sxs-lookup"><span data-stu-id="dafab-150">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="dafab-151">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="dafab-151">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="dafab-152">Предложения Where</span><span class="sxs-lookup"><span data-stu-id="dafab-152">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
- [<span data-ttu-id="dafab-153">Предложение Aggregate</span><span class="sxs-lookup"><span data-stu-id="dafab-153">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="dafab-154">Предложение Distinct</span><span class="sxs-lookup"><span data-stu-id="dafab-154">Distinct Clause</span></span>](../../../visual-basic/language-reference/queries/distinct-clause.md)
- [<span data-ttu-id="dafab-155">Предложение Join</span><span class="sxs-lookup"><span data-stu-id="dafab-155">Join Clause</span></span>](../../../visual-basic/language-reference/queries/join-clause.md)
- [<span data-ttu-id="dafab-156">Предложение Group Join</span><span class="sxs-lookup"><span data-stu-id="dafab-156">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)
- [<span data-ttu-id="dafab-157">Предложение Order By</span><span class="sxs-lookup"><span data-stu-id="dafab-157">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="dafab-158">Предложение Let</span><span class="sxs-lookup"><span data-stu-id="dafab-158">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)
- [<span data-ttu-id="dafab-159">Предложение Skip</span><span class="sxs-lookup"><span data-stu-id="dafab-159">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
- [<span data-ttu-id="dafab-160">Предложение Take</span><span class="sxs-lookup"><span data-stu-id="dafab-160">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="dafab-161">Предложение Skip While</span><span class="sxs-lookup"><span data-stu-id="dafab-161">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="dafab-162">Предложение Take While</span><span class="sxs-lookup"><span data-stu-id="dafab-162">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
