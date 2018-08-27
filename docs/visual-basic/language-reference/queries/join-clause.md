---
title: Предложение Join (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryJoinIn
- vb.QueryJoin
- vb.QueryJoinOn
helpviewer_keywords:
- queries [Visual Basic], Join
- Join statement [Visual Basic]
- Join clause [Visual Basic]
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
ms.openlocfilehash: b1551583079c66d1bf5f6963a42d5d24e518fff3
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2018
ms.locfileid: "42933871"
---
# <a name="join-clause-visual-basic"></a><span data-ttu-id="34ff3-102">Предложение Join (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="34ff3-102">Join Clause (Visual Basic)</span></span>
<span data-ttu-id="34ff3-103">Объединяет две коллекции в одну.</span><span class="sxs-lookup"><span data-stu-id="34ff3-103">Combines two collections into a single collection.</span></span> <span data-ttu-id="34ff3-104">Операция соединения основана на сопоставлении ключей и использует `Equals` оператор.</span><span class="sxs-lookup"><span data-stu-id="34ff3-104">The join operation is based on matching keys and uses the `Equals` operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34ff3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="34ff3-105">Syntax</span></span>  
  
```  
Join element In collection _  
  [ joinClause _ ]   
  [ groupJoinClause ... _ ]   
On key1 Equals key2 [ And key3 Equals key4 [... ]  
```  
  
## <a name="parts"></a><span data-ttu-id="34ff3-106">Части</span><span class="sxs-lookup"><span data-stu-id="34ff3-106">Parts</span></span>  
 `element`  
 <span data-ttu-id="34ff3-107">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="34ff3-107">Required.</span></span> <span data-ttu-id="34ff3-108">Переменная управления для присоединяемой коллекции.</span><span class="sxs-lookup"><span data-stu-id="34ff3-108">The control variable for the collection being joined.</span></span>  
  
 `collection`  
 <span data-ttu-id="34ff3-109">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="34ff3-109">Required.</span></span> <span data-ttu-id="34ff3-110">Коллекция для объединения с коллекцией, определенной в левой части `Join` оператор.</span><span class="sxs-lookup"><span data-stu-id="34ff3-110">The collection to combine with the collection identified on the left side of the `Join` operator.</span></span> <span data-ttu-id="34ff3-111">Объект `Join` предложение может быть вложенным в другой `Join` предложение, или в `Group Join` предложение.</span><span class="sxs-lookup"><span data-stu-id="34ff3-111">A `Join` clause can be nested in another `Join` clause, or in a `Group Join` clause.</span></span>  
  
 `joinClause`  
 <span data-ttu-id="34ff3-112">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="34ff3-112">Optional.</span></span> <span data-ttu-id="34ff3-113">Один или более дополнительных `Join` предложений для дальнейшего уточнения запроса.</span><span class="sxs-lookup"><span data-stu-id="34ff3-113">One or more additional `Join` clauses to further refine the query.</span></span>  
  
 `groupJoinClause`  
 <span data-ttu-id="34ff3-114">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="34ff3-114">Optional.</span></span> <span data-ttu-id="34ff3-115">Один или более дополнительных `Group Join` предложений для дальнейшего уточнения запроса.</span><span class="sxs-lookup"><span data-stu-id="34ff3-115">One or more additional `Group Join` clauses to further refine the query.</span></span>  
  
 <span data-ttu-id="34ff3-116">`key1` `Equals` `key2`</span><span class="sxs-lookup"><span data-stu-id="34ff3-116">`key1` `Equals` `key2`</span></span>  
 <span data-ttu-id="34ff3-117">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="34ff3-117">Required.</span></span> <span data-ttu-id="34ff3-118">Определяет ключи для соединяемых коллекций.</span><span class="sxs-lookup"><span data-stu-id="34ff3-118">Identifies keys for the collections being joined.</span></span> <span data-ttu-id="34ff3-119">Необходимо использовать `Equals` оператор для сравнения ключей из соединяемых коллекций.</span><span class="sxs-lookup"><span data-stu-id="34ff3-119">You must use the `Equals` operator to compare keys from the collections being joined.</span></span> <span data-ttu-id="34ff3-120">Можно комбинировать условия соединения с помощью `And` оператор для идентификации нескольких ключей.</span><span class="sxs-lookup"><span data-stu-id="34ff3-120">You can combine join conditions by using the `And` operator to identify multiple keys.</span></span> <span data-ttu-id="34ff3-121">`key1` должен быть из коллекции в левой части `Join` оператор.</span><span class="sxs-lookup"><span data-stu-id="34ff3-121">`key1` must be from the collection on the left side of the `Join` operator.</span></span> <span data-ttu-id="34ff3-122">`key2` должен быть из коллекции в правой части `Join` оператор.</span><span class="sxs-lookup"><span data-stu-id="34ff3-122">`key2` must be from the collection on the right side of the `Join` operator.</span></span>  
  
 <span data-ttu-id="34ff3-123">Ключи, используемые в условии соединения может быть выражений, содержащих более одного элемента из коллекции.</span><span class="sxs-lookup"><span data-stu-id="34ff3-123">The keys used in the join condition can be expressions that include more than one item from the collection.</span></span> <span data-ttu-id="34ff3-124">Тем не менее каждое ключевое выражение может содержать только элементы из соответствующей коллекции.</span><span class="sxs-lookup"><span data-stu-id="34ff3-124">However, each key expression can contain only items from its respective collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34ff3-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="34ff3-125">Remarks</span></span>  
 <span data-ttu-id="34ff3-126">`Join` Предложение объединяет две коллекции, на основе сопоставления значений ключа из соединяемых коллекций.</span><span class="sxs-lookup"><span data-stu-id="34ff3-126">The `Join` clause combines two collections based on matching key values from the collections being joined.</span></span> <span data-ttu-id="34ff3-127">Полученная в результате коллекция может содержать любую комбинацию значений из коллекции в левой части `Join` оператор и коллекции, указанной в `Join` предложение.</span><span class="sxs-lookup"><span data-stu-id="34ff3-127">The resulting collection can contain any combination of values from the collection identified on the left side of the `Join` operator and the collection identified in the `Join` clause.</span></span> <span data-ttu-id="34ff3-128">Запрос будет возвращать только результаты, для которых условие, заданное `Equals` оператор будет выполняться.</span><span class="sxs-lookup"><span data-stu-id="34ff3-128">The query will return only results for which the condition specified by the `Equals` operator is met.</span></span> <span data-ttu-id="34ff3-129">Это эквивалентно `INNER JOIN` в SQL.</span><span class="sxs-lookup"><span data-stu-id="34ff3-129">This is equivalent to an `INNER JOIN` in SQL.</span></span>  
  
 <span data-ttu-id="34ff3-130">Можно использовать несколько `Join` предложения в запросе на объединение двух или нескольких коллекций в одну коллекцию.</span><span class="sxs-lookup"><span data-stu-id="34ff3-130">You can use multiple `Join` clauses in a query to join two or more collections into a single collection.</span></span>  
  
 <span data-ttu-id="34ff3-131">Можно выполнить неявное соединение для объединения коллекций без `Join` предложение.</span><span class="sxs-lookup"><span data-stu-id="34ff3-131">You can perform an implicit join to combine collections without the `Join` clause.</span></span> <span data-ttu-id="34ff3-132">Чтобы сделать это, включать несколько `In` предложения в вашей `From` предложения и укажите `Where` предложение, определяющее ключи, которые вы хотите использовать для соединения.</span><span class="sxs-lookup"><span data-stu-id="34ff3-132">To do this, include multiple `In` clauses in your `From` clause and specify a `Where` clause that identifies the keys that you want to use for the join.</span></span>  
  
 <span data-ttu-id="34ff3-133">Можно использовать `Group Join` предложение для объединения коллекций в одну иерархическую коллекцию.</span><span class="sxs-lookup"><span data-stu-id="34ff3-133">You can use the `Group Join` clause to combine collections into a single hierarchical collection.</span></span> <span data-ttu-id="34ff3-134">Это аналогично `LEFT OUTER JOIN` в SQL.</span><span class="sxs-lookup"><span data-stu-id="34ff3-134">This is like a `LEFT OUTER JOIN` in SQL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34ff3-135">Пример</span><span class="sxs-lookup"><span data-stu-id="34ff3-135">Example</span></span>  
 <span data-ttu-id="34ff3-136">В следующем примере кода выполняется неявное соединение для объединения списка клиентов и их заказов.</span><span class="sxs-lookup"><span data-stu-id="34ff3-136">The following code example performs an implicit join to combine a list of customers with their orders.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#13](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="34ff3-137">Пример</span><span class="sxs-lookup"><span data-stu-id="34ff3-137">Example</span></span>  
 <span data-ttu-id="34ff3-138">В следующем примере объединяются две коллекции с помощью `Join` предложение.</span><span class="sxs-lookup"><span data-stu-id="34ff3-138">The following code example joins two collections by using the `Join` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#12](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_2.vb)]  
  
 <span data-ttu-id="34ff3-139">В этом примере выдаст результат, аналогичный приведенному ниже:</span><span class="sxs-lookup"><span data-stu-id="34ff3-139">This example will produce output similar to the following:</span></span>  
  
 `winlogon (968), Windows Logon`  
  
 `explorer (2424), File Explorer`  
  
 `cmd (5136), Command Window`  
  
## <a name="example"></a><span data-ttu-id="34ff3-140">Пример</span><span class="sxs-lookup"><span data-stu-id="34ff3-140">Example</span></span>  
 <span data-ttu-id="34ff3-141">В следующем примере объединяются две коллекции с помощью `Join` предложение с двумя ключевыми столбцами.</span><span class="sxs-lookup"><span data-stu-id="34ff3-141">The following code example joins two collections by using the `Join` clause with two key columns.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#17](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_3.vb)]  
  
 <span data-ttu-id="34ff3-142">Пример выдаст результат, аналогичный приведенному ниже:</span><span class="sxs-lookup"><span data-stu-id="34ff3-142">The example will produce output similar to the following:</span></span>  
  
 `winlogon (968), Windows Logon, Priority = 13`  
  
 `cmd (700), Command Window, Priority = 8`  
  
 `explorer (2424), File Explorer, Priority = 8`  
  
## <a name="see-also"></a><span data-ttu-id="34ff3-143">См. также</span><span class="sxs-lookup"><span data-stu-id="34ff3-143">See Also</span></span>  
 <span data-ttu-id="34ff3-144">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="34ff3-144">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>  
 [<span data-ttu-id="34ff3-145">Запросы</span><span class="sxs-lookup"><span data-stu-id="34ff3-145">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="34ff3-146">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="34ff3-146">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="34ff3-147">Предложение From</span><span class="sxs-lookup"><span data-stu-id="34ff3-147">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="34ff3-148">Предложение Group Join</span><span class="sxs-lookup"><span data-stu-id="34ff3-148">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [<span data-ttu-id="34ff3-149">Предложения Where</span><span class="sxs-lookup"><span data-stu-id="34ff3-149">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
