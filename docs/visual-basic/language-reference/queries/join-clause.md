---
title: "Предложение Join (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QueryJoinIn
- vb.QueryJoin
- vb.QueryJoinOn
helpviewer_keywords:
- queries [Visual Basic], Join
- Join statement [Visual Basic]
- Join clause [Visual Basic]
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2bb25c9dac8994e7f975539c1d036f0f0d9d239e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="join-clause-visual-basic"></a><span data-ttu-id="3cc76-102">Предложение Join (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3cc76-102">Join Clause (Visual Basic)</span></span>
<span data-ttu-id="3cc76-103">Объединяет две коллекции в одну.</span><span class="sxs-lookup"><span data-stu-id="3cc76-103">Combines two collections into a single collection.</span></span> <span data-ttu-id="3cc76-104">Операция соединения основана на сопоставлении ключей и использует `Equals` оператор.</span><span class="sxs-lookup"><span data-stu-id="3cc76-104">The join operation is based on matching keys and uses the `Equals` operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cc76-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3cc76-105">Syntax</span></span>  
  
```  
Join element In collection _  
  [ joinClause _ ]   
  [ groupJoinClause ... _ ]   
On key1 Equals key2 [ And key3 Equals key4 [... ]  
```  
  
## <a name="parts"></a><span data-ttu-id="3cc76-106">Части</span><span class="sxs-lookup"><span data-stu-id="3cc76-106">Parts</span></span>  
 `element`  
 <span data-ttu-id="3cc76-107">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="3cc76-107">Required.</span></span> <span data-ttu-id="3cc76-108">Переменная управления для присоединяемой коллекции.</span><span class="sxs-lookup"><span data-stu-id="3cc76-108">The control variable for the collection being joined.</span></span>  
  
 `collection`  
 <span data-ttu-id="3cc76-109">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="3cc76-109">Required.</span></span> <span data-ttu-id="3cc76-110">Коллекция для объединения с коллекцией, определенной в левой части `Join` оператор.</span><span class="sxs-lookup"><span data-stu-id="3cc76-110">The collection to combine with the collection identified on the left side of the `Join` operator.</span></span> <span data-ttu-id="3cc76-111">Объект `Join` предложение может быть вложенным в другой `Join` предложения, либо в `Group Join` предложения.</span><span class="sxs-lookup"><span data-stu-id="3cc76-111">A `Join` clause can be nested in another `Join` clause, or in a `Group Join` clause.</span></span>  
  
 `joinClause`  
 <span data-ttu-id="3cc76-112">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="3cc76-112">Optional.</span></span> <span data-ttu-id="3cc76-113">Один или более дополнительных `Join` предложения для дальнейшего уточнения запроса.</span><span class="sxs-lookup"><span data-stu-id="3cc76-113">One or more additional `Join` clauses to further refine the query.</span></span>  
  
 `groupJoinClause`  
 <span data-ttu-id="3cc76-114">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="3cc76-114">Optional.</span></span> <span data-ttu-id="3cc76-115">Один или более дополнительных `Group Join` предложения для дальнейшего уточнения запроса.</span><span class="sxs-lookup"><span data-stu-id="3cc76-115">One or more additional `Group Join` clauses to further refine the query.</span></span>  
  
 <span data-ttu-id="3cc76-116">`key1` `Equals` `key2`</span><span class="sxs-lookup"><span data-stu-id="3cc76-116">`key1` `Equals` `key2`</span></span>  
 <span data-ttu-id="3cc76-117">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="3cc76-117">Required.</span></span> <span data-ttu-id="3cc76-118">Определяет ключи для соединяемых коллекций.</span><span class="sxs-lookup"><span data-stu-id="3cc76-118">Identifies keys for the collections being joined.</span></span> <span data-ttu-id="3cc76-119">Необходимо использовать `Equals` оператор для сравнения ключей из соединяемых коллекций.</span><span class="sxs-lookup"><span data-stu-id="3cc76-119">You must use the `Equals` operator to compare keys from the collections being joined.</span></span> <span data-ttu-id="3cc76-120">Можно комбинировать условия соединения с помощью `And` оператор для идентификации нескольких ключей.</span><span class="sxs-lookup"><span data-stu-id="3cc76-120">You can combine join conditions by using the `And` operator to identify multiple keys.</span></span> <span data-ttu-id="3cc76-121">`key1`должен быть из коллекции в левой части `Join` оператор.</span><span class="sxs-lookup"><span data-stu-id="3cc76-121">`key1` must be from the collection on the left side of the `Join` operator.</span></span> <span data-ttu-id="3cc76-122">`key2`должен быть из коллекции в правой части `Join` оператор.</span><span class="sxs-lookup"><span data-stu-id="3cc76-122">`key2` must be from the collection on the right side of the `Join` operator.</span></span>  
  
 <span data-ttu-id="3cc76-123">Ключи, используемые в условии соединения может быть выражений, содержащих более одного элемента из коллекции.</span><span class="sxs-lookup"><span data-stu-id="3cc76-123">The keys used in the join condition can be expressions that include more than one item from the collection.</span></span> <span data-ttu-id="3cc76-124">Однако каждое ключевое выражение может содержать только элементы из соответствующей ему коллекции.</span><span class="sxs-lookup"><span data-stu-id="3cc76-124">However, each key expression can contain only items from its respective collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3cc76-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="3cc76-125">Remarks</span></span>  
 <span data-ttu-id="3cc76-126">`Join` Предложение объединяет две коллекции на основании совпадающих значений ключей из соединяемых коллекций.</span><span class="sxs-lookup"><span data-stu-id="3cc76-126">The `Join` clause combines two collections based on matching key values from the collections being joined.</span></span> <span data-ttu-id="3cc76-127">Полученная в результате коллекция может содержать любую комбинацию значений из коллекции в левой части `Join` оператор и коллекции, указанной в `Join` предложения.</span><span class="sxs-lookup"><span data-stu-id="3cc76-127">The resulting collection can contain any combination of values from the collection identified on the left side of the `Join` operator and the collection identified in the `Join` clause.</span></span> <span data-ttu-id="3cc76-128">Запрос будет возвращать только те результаты, для которых условие, заданное `Equals` выполняется оператор.</span><span class="sxs-lookup"><span data-stu-id="3cc76-128">The query will return only results for which the condition specified by the `Equals` operator is met.</span></span> <span data-ttu-id="3cc76-129">Это эквивалентно `INNER JOIN` в SQL.</span><span class="sxs-lookup"><span data-stu-id="3cc76-129">This is equivalent to an `INNER JOIN` in SQL.</span></span>  
  
 <span data-ttu-id="3cc76-130">Можно использовать несколько `Join` предложения в запросе, для соединения двух или нескольких коллекций в одну коллекцию.</span><span class="sxs-lookup"><span data-stu-id="3cc76-130">You can use multiple `Join` clauses in a query to join two or more collections into a single collection.</span></span>  
  
 <span data-ttu-id="3cc76-131">Можно выполнять неявные соединения для объединения коллекций без `Join` предложения.</span><span class="sxs-lookup"><span data-stu-id="3cc76-131">You can perform an implicit join to combine collections without the `Join` clause.</span></span> <span data-ttu-id="3cc76-132">Чтобы сделать это, включать несколько `In` предложения в вашей `From` предложения и укажите `Where` предложение, определяющее ключи, которые вы хотите использовать для соединения.</span><span class="sxs-lookup"><span data-stu-id="3cc76-132">To do this, include multiple `In` clauses in your `From` clause and specify a `Where` clause that identifies the keys that you want to use for the join.</span></span>  
  
 <span data-ttu-id="3cc76-133">Можно использовать `Group Join` предложение для объединения коллекции в одну иерархическую коллекцию.</span><span class="sxs-lookup"><span data-stu-id="3cc76-133">You can use the `Group Join` clause to combine collections into a single hierarchical collection.</span></span> <span data-ttu-id="3cc76-134">Это аналогично `LEFT OUTER JOIN` в SQL.</span><span class="sxs-lookup"><span data-stu-id="3cc76-134">This is like a `LEFT OUTER JOIN` in SQL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cc76-135">Пример</span><span class="sxs-lookup"><span data-stu-id="3cc76-135">Example</span></span>  
 <span data-ttu-id="3cc76-136">В следующем примере кода выполняется неявное соединение для объединения списка клиентов и их заказов.</span><span class="sxs-lookup"><span data-stu-id="3cc76-136">The following code example performs an implicit join to combine a list of customers with their orders.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#13](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="3cc76-137">Пример</span><span class="sxs-lookup"><span data-stu-id="3cc76-137">Example</span></span>  
 <span data-ttu-id="3cc76-138">В следующем примере кода две коллекции объединяются с помощью `Join` предложения.</span><span class="sxs-lookup"><span data-stu-id="3cc76-138">The following code example joins two collections by using the `Join` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#12](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_2.vb)]  
  
 <span data-ttu-id="3cc76-139">В этом примере будет создавать выходные данные, аналогичные следующим:</span><span class="sxs-lookup"><span data-stu-id="3cc76-139">This example will produce output similar to the following:</span></span>  
  
 `winlogon (968), Windows Logon`  
  
 `explorer (2424), File Explorer`  
  
 `cmd (5136), Command Window`  
  
## <a name="example"></a><span data-ttu-id="3cc76-140">Пример</span><span class="sxs-lookup"><span data-stu-id="3cc76-140">Example</span></span>  
 <span data-ttu-id="3cc76-141">В следующем примере кода две коллекции объединяются с помощью `Join` предложение, содержащее два ключевых столбцов.</span><span class="sxs-lookup"><span data-stu-id="3cc76-141">The following code example joins two collections by using the `Join` clause with two key columns.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#17](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_3.vb)]  
  
 <span data-ttu-id="3cc76-142">Пример вывода следующего вида:</span><span class="sxs-lookup"><span data-stu-id="3cc76-142">The example will produce output similar to the following:</span></span>  
  
 `winlogon (968), Windows Logon, Priority = 13`  
  
 `cmd (700), Command Window, Priority = 8`  
  
 `explorer (2424), File Explorer, Priority = 8`  
  
## <a name="see-also"></a><span data-ttu-id="3cc76-143">См. также</span><span class="sxs-lookup"><span data-stu-id="3cc76-143">See Also</span></span>  
 <span data-ttu-id="3cc76-144">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3cc76-144">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>  
 [<span data-ttu-id="3cc76-145">Запросы</span><span class="sxs-lookup"><span data-stu-id="3cc76-145">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="3cc76-146">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="3cc76-146">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="3cc76-147">Предложение From</span><span class="sxs-lookup"><span data-stu-id="3cc76-147">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="3cc76-148">Предложение Group Join</span><span class="sxs-lookup"><span data-stu-id="3cc76-148">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [<span data-ttu-id="3cc76-149">Предложения Where</span><span class="sxs-lookup"><span data-stu-id="3cc76-149">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
