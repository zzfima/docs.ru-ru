---
title: Предложение From (Visual Basic)
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
ms.openlocfilehash: 781902f1bf28bd029c8d9825aee155a6691cbae9
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004776"
---
# <a name="from-clause-visual-basic"></a><span data-ttu-id="f2d0d-102">Предложение From (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f2d0d-102">From Clause (Visual Basic)</span></span>
<span data-ttu-id="f2d0d-103">Указывает одну или несколько переменных диапазона и коллекцию для запроса.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-103">Specifies one or more range variables and a collection to query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2d0d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f2d0d-104">Syntax</span></span>  
  
```vb  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="f2d0d-105">Части</span><span class="sxs-lookup"><span data-stu-id="f2d0d-105">Parts</span></span>  
  
|<span data-ttu-id="f2d0d-106">Термин</span><span class="sxs-lookup"><span data-stu-id="f2d0d-106">Term</span></span>|<span data-ttu-id="f2d0d-107">Определение</span><span class="sxs-lookup"><span data-stu-id="f2d0d-107">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="f2d0d-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-108">Required.</span></span> <span data-ttu-id="f2d0d-109">*Переменная диапазона* , используемая для прохода по элементам коллекции.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-109">A *range variable* used to iterate through the elements of the collection.</span></span> <span data-ttu-id="f2d0d-110">Переменная диапазона используется для ссылки на каждый элемент `collection`, так как запрос выполняет итерацию по `collection`.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-110">A range variable is used to refer to each member of the `collection` as the query iterates through the `collection`.</span></span> <span data-ttu-id="f2d0d-111">Должен быть перечислимым типом.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-111">Must be an enumerable type.</span></span>|  
|`type`|<span data-ttu-id="f2d0d-112">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-112">Optional.</span></span> <span data-ttu-id="f2d0d-113">Тип параметра `element`.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-113">The type of `element`.</span></span> <span data-ttu-id="f2d0d-114">Если `type` не указан, тип `element` выводится из `collection`.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-114">If no `type` is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="f2d0d-115">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-115">Required.</span></span> <span data-ttu-id="f2d0d-116">Ссылается на коллекцию, к которой выполняется запрос.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-116">Refers to the collection to be queried.</span></span> <span data-ttu-id="f2d0d-117">Должен быть перечислимым типом.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-117">Must be an enumerable type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2d0d-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="f2d0d-118">Remarks</span></span>  
 <span data-ttu-id="f2d0d-119">Предложение `From` используется для указания исходных данных для запроса и переменных, используемых для ссылки на элемент из исходной коллекции.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-119">The `From` clause is used to identify the source data for a query and the variables that are used to refer to an element from the source collection.</span></span> <span data-ttu-id="f2d0d-120">Эти переменные называются *переменными диапазона*.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-120">These variables are called *range variables*.</span></span> <span data-ttu-id="f2d0d-121">Предложение `From` является обязательным для запроса, за исключением случаев, когда для задания запроса, возвращающего только агрегированные результаты, используется предложение `Aggregate`.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-121">The `From` clause is required for a query, except when the `Aggregate` clause is used to identify a query that returns only aggregated results.</span></span> <span data-ttu-id="f2d0d-122">Дополнительные сведения см. в разделе [предложение Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span><span class="sxs-lookup"><span data-stu-id="f2d0d-122">For more information, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="f2d0d-123">В запросе можно указать несколько предложений `From`, чтобы определить несколько коллекций для объединения.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-123">You can specify multiple `From` clauses in a query to identify multiple collections to be joined.</span></span> <span data-ttu-id="f2d0d-124">Если указано несколько коллекций, они проходят по отдельности или объединяются, если они связаны.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-124">When multiple collections are specified, they are iterated over independently, or you can join them if they are related.</span></span> <span data-ttu-id="f2d0d-125">Вы можете объединить коллекции неявным образом с помощью предложения `Select` или явно с помощью предложений `Join` или `Group Join`.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-125">You can join collections implicitly by using the `Select` clause, or explicitly by using the `Join` or `Group Join` clauses.</span></span> <span data-ttu-id="f2d0d-126">В качестве альтернативы можно указать несколько переменных диапазона и коллекций в одном предложении `From`, при этом каждая связанная переменная диапазона и коллекция, отделенные друг от друга запятыми.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-126">As an alternative, you can specify multiple range variables and collections in a single `From` clause, with each related range variable and collection separated from the others by a comma.</span></span> <span data-ttu-id="f2d0d-127">В следующем примере кода показаны оба синтаксических параметра для предложения `From`.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-127">The following code example shows both syntax options for the `From` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#21)]  
  
 <span data-ttu-id="f2d0d-128">Предложение `From` определяет область запроса, что аналогично области действия цикла `For`.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-128">The `From` clause defines the scope of a query, which is similar to the scope of a `For` loop.</span></span> <span data-ttu-id="f2d0d-129">Таким образом, каждая переменная диапазона `element` в области запроса должна иметь уникальное имя.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-129">Therefore, each `element` range variable in the scope of a query must have a unique name.</span></span> <span data-ttu-id="f2d0d-130">Поскольку можно указать несколько предложений `From` для запроса, последующие предложения `From` могут ссылаться на переменные диапазона в предложении `From` или могут ссылаться на переменные диапазона в предыдущем предложении `From`.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-130">Because you can specify multiple `From` clauses for a query, subsequent `From` clauses can refer to range variables in the `From` clause, or they can refer to range variables in a previous `From` clause.</span></span> <span data-ttu-id="f2d0d-131">Например, в следующем примере показано вложенное предложение `From`, где коллекция во втором предложении основана на свойстве переменной диапазона в первом предложении.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-131">For example, the following example shows a nested `From` clause where the collection in the second clause is based on a property of the range variable in the first clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#22)]  
  
 <span data-ttu-id="f2d0d-132">За каждым предложением `From` может следовать любое сочетание дополнительных предложений запроса для уточнения запроса.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-132">Each `From` clause can be followed by any combination of additional query clauses to refine the query.</span></span> <span data-ttu-id="f2d0d-133">Запрос можно уточнить следующими способами.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-133">You can refine the query in the following ways:</span></span>  
  
- <span data-ttu-id="f2d0d-134">Объедините несколько коллекций неявным образом с помощью предложений `From` и `Select` или явно с помощью предложений `Join` или `Group Join`.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-134">Combine multiple collections implicitly by using the `From` and `Select` clauses, or explicitly by using the `Join` or `Group Join` clauses.</span></span>  
  
- <span data-ttu-id="f2d0d-135">Чтобы отфильтровать результат запроса, используйте предложение `Where`.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-135">Use the `Where` clause to filter the query result.</span></span>  
  
- <span data-ttu-id="f2d0d-136">Отсортируйте результат с помощью предложения `Order By`.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-136">Sort the result by using the `Order By` clause.</span></span>  
  
- <span data-ttu-id="f2d0d-137">Сгруппируйте аналогичные результаты вместе с помощью предложения `Group By`.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-137">Group similar results together by using the `Group By` clause.</span></span>  
  
- <span data-ttu-id="f2d0d-138">Используйте предложение `Aggregate`, чтобы определить агрегатные функции для вычисления результата всего запроса.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-138">Use the `Aggregate` clause to identify aggregate functions to evaluate for the whole query result.</span></span>  
  
- <span data-ttu-id="f2d0d-139">Используйте предложение `Let`, чтобы ввести переменную итерации, значение которой определяется выражением, а не коллекцией.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-139">Use the `Let` clause to introduce an iteration variable whose value is determined by an expression instead of a collection.</span></span>  
  
- <span data-ttu-id="f2d0d-140">Используйте предложение `Distinct` для пропуска повторяющихся результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-140">Use the `Distinct` clause to ignore duplicate query results.</span></span>  
  
- <span data-ttu-id="f2d0d-141">Выявление частей результата, возвращаемых с помощью предложений `Skip`, `Take`, `Skip While` и `Take While`.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-141">Identify parts of the result to return by using the `Skip`, `Take`, `Skip While`, and `Take While` clauses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2d0d-142">Пример</span><span class="sxs-lookup"><span data-stu-id="f2d0d-142">Example</span></span>  
 <span data-ttu-id="f2d0d-143">Следующее выражение запроса использует предложение `From` для объявления переменной диапазона `cust` для каждого объекта `Customer` в коллекции `customers`.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-143">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="f2d0d-144">Предложение `Where` использует переменную диапазона для ограничения выходных данных для клиентов из указанной области.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-144">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="f2d0d-145">Цикл `For Each` отображает название компании для каждого клиента в результатах запроса.</span><span class="sxs-lookup"><span data-stu-id="f2d0d-145">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="f2d0d-146">См. также</span><span class="sxs-lookup"><span data-stu-id="f2d0d-146">See also</span></span>

- [<span data-ttu-id="f2d0d-147">Запросы</span><span class="sxs-lookup"><span data-stu-id="f2d0d-147">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- <span data-ttu-id="f2d0d-148">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f2d0d-148">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="f2d0d-149">Оператор For Each...Next</span><span class="sxs-lookup"><span data-stu-id="f2d0d-149">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="f2d0d-150">Оператор For...Next</span><span class="sxs-lookup"><span data-stu-id="f2d0d-150">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="f2d0d-151">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="f2d0d-151">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="f2d0d-152">Предложения Where</span><span class="sxs-lookup"><span data-stu-id="f2d0d-152">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
- [<span data-ttu-id="f2d0d-153">Предложение Aggregate</span><span class="sxs-lookup"><span data-stu-id="f2d0d-153">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="f2d0d-154">Предложение Distinct</span><span class="sxs-lookup"><span data-stu-id="f2d0d-154">Distinct Clause</span></span>](../../../visual-basic/language-reference/queries/distinct-clause.md)
- [<span data-ttu-id="f2d0d-155">Предложение Join</span><span class="sxs-lookup"><span data-stu-id="f2d0d-155">Join Clause</span></span>](../../../visual-basic/language-reference/queries/join-clause.md)
- [<span data-ttu-id="f2d0d-156">Предложение Group Join</span><span class="sxs-lookup"><span data-stu-id="f2d0d-156">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)
- [<span data-ttu-id="f2d0d-157">Предложение Order By</span><span class="sxs-lookup"><span data-stu-id="f2d0d-157">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="f2d0d-158">Предложение Let</span><span class="sxs-lookup"><span data-stu-id="f2d0d-158">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)
- [<span data-ttu-id="f2d0d-159">Предложение Skip</span><span class="sxs-lookup"><span data-stu-id="f2d0d-159">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
- [<span data-ttu-id="f2d0d-160">Предложение Take</span><span class="sxs-lookup"><span data-stu-id="f2d0d-160">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="f2d0d-161">Предложение Skip While</span><span class="sxs-lookup"><span data-stu-id="f2d0d-161">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="f2d0d-162">Предложение Take While</span><span class="sxs-lookup"><span data-stu-id="f2d0d-162">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
