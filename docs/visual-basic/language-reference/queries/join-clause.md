---
title: Предложение Join
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
ms.openlocfilehash: b0baca9f897a00b3c6c67699629477ff385d6ef7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353268"
---
# <a name="join-clause-visual-basic"></a><span data-ttu-id="9e2fb-102">Предложение Join (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e2fb-102">Join Clause (Visual Basic)</span></span>

<span data-ttu-id="9e2fb-103">Объединяет две коллекции в одну.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-103">Combines two collections into a single collection.</span></span> <span data-ttu-id="9e2fb-104">Операция Join основана на совпадающих ключах и использует оператор `Equals`.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-104">The join operation is based on matching keys and uses the `Equals` operator.</span></span>

## <a name="syntax"></a><span data-ttu-id="9e2fb-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e2fb-105">Syntax</span></span>

```vb
Join element In collection _
  [ joinClause _ ]
  [ groupJoinClause ... _ ]
On key1 Equals key2 [ And key3 Equals key4 [... ]
```

## <a name="parts"></a><span data-ttu-id="9e2fb-106">Части</span><span class="sxs-lookup"><span data-stu-id="9e2fb-106">Parts</span></span>

<span data-ttu-id="9e2fb-107">`element` Обязательный.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-107">`element` Required.</span></span> <span data-ttu-id="9e2fb-108">Управляющая переменная для объединяемой коллекции.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-108">The control variable for the collection being joined.</span></span>

`collection`  
<span data-ttu-id="9e2fb-109">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-109">Required.</span></span> <span data-ttu-id="9e2fb-110">Коллекция для объединения с коллекцией, указанной в левой части оператора `Join`.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-110">The collection to combine with the collection identified on the left side of the `Join` operator.</span></span> <span data-ttu-id="9e2fb-111">Предложение `Join` может быть вложено в другое предложение `Join` или в предложении `Group Join`.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-111">A `Join` clause can be nested in another `Join` clause, or in a `Group Join` clause.</span></span>

`joinClause`  
<span data-ttu-id="9e2fb-112">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-112">Optional.</span></span> <span data-ttu-id="9e2fb-113">Одно или несколько дополнительных `Join` предложений для дальнейшего уточнения запроса.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-113">One or more additional `Join` clauses to further refine the query.</span></span>

`groupJoinClause`  
<span data-ttu-id="9e2fb-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-114">Optional.</span></span> <span data-ttu-id="9e2fb-115">Одно или несколько дополнительных `Group Join` предложений для дальнейшего уточнения запроса.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-115">One or more additional `Group Join` clauses to further refine the query.</span></span>

<span data-ttu-id="9e2fb-116">`key1` `Equals` `key2`</span><span class="sxs-lookup"><span data-stu-id="9e2fb-116">`key1` `Equals` `key2`</span></span>  
<span data-ttu-id="9e2fb-117">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-117">Required.</span></span> <span data-ttu-id="9e2fb-118">Определяет ключи для соединяемых коллекций.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-118">Identifies keys for the collections being joined.</span></span> <span data-ttu-id="9e2fb-119">Для сравнения ключей из объединяемых коллекций необходимо использовать оператор `Equals`.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-119">You must use the `Equals` operator to compare keys from the collections being joined.</span></span> <span data-ttu-id="9e2fb-120">Условия JOIN можно комбинировать с помощью оператора `And` для обнаружения нескольких ключей.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-120">You can combine join conditions by using the `And` operator to identify multiple keys.</span></span> <span data-ttu-id="9e2fb-121">`key1` должен быть из коллекции в левой части оператора `Join`.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-121">`key1` must be from the collection on the left side of the `Join` operator.</span></span> <span data-ttu-id="9e2fb-122">`key2` должны находиться в коллекции с правой стороны оператора `Join`.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-122">`key2` must be from the collection on the right side of the `Join` operator.</span></span>

<span data-ttu-id="9e2fb-123">Ключи, используемые в условии объединения, могут быть выражениями, включающими более одного элемента из коллекции.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-123">The keys used in the join condition can be expressions that include more than one item from the collection.</span></span> <span data-ttu-id="9e2fb-124">Однако каждое ключевое выражение может содержать только элементы из соответствующей коллекции.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-124">However, each key expression can contain only items from its respective collection.</span></span>

## <a name="remarks"></a><span data-ttu-id="9e2fb-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="9e2fb-125">Remarks</span></span>

<span data-ttu-id="9e2fb-126">Предложение `Join` объединяет две коллекции на основе совпадающих значений ключей из объединяемых коллекций.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-126">The `Join` clause combines two collections based on matching key values from the collections being joined.</span></span> <span data-ttu-id="9e2fb-127">Результирующая коллекция может содержать любое сочетание значений из коллекции, определенной в левой части оператора `Join`, и коллекции, указанной в предложении `Join`.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-127">The resulting collection can contain any combination of values from the collection identified on the left side of the `Join` operator and the collection identified in the `Join` clause.</span></span> <span data-ttu-id="9e2fb-128">Запрос возвратит только результаты, для которых выполняется условие, заданное оператором `Equals`.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-128">The query will return only results for which the condition specified by the `Equals` operator is met.</span></span> <span data-ttu-id="9e2fb-129">Это эквивалентно `INNER JOIN` в SQL.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-129">This is equivalent to an `INNER JOIN` in SQL.</span></span>

<span data-ttu-id="9e2fb-130">Можно использовать несколько предложений `Join` в запросе для объединения двух или более коллекций в одну коллекцию.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-130">You can use multiple `Join` clauses in a query to join two or more collections into a single collection.</span></span>

<span data-ttu-id="9e2fb-131">Можно выполнить неявное соединение для объединения коллекций без предложения `Join`.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-131">You can perform an implicit join to combine collections without the `Join` clause.</span></span> <span data-ttu-id="9e2fb-132">Для этого включите несколько предложений `In` в предложение `From` и укажите предложение `Where`, определяющее ключи, которые необходимо использовать для объединения.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-132">To do this, include multiple `In` clauses in your `From` clause and specify a `Where` clause that identifies the keys that you want to use for the join.</span></span>

<span data-ttu-id="9e2fb-133">Можно использовать предложение `Group Join` для объединения коллекций в одну иерархическую коллекцию.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-133">You can use the `Group Join` clause to combine collections into a single hierarchical collection.</span></span> <span data-ttu-id="9e2fb-134">Это похоже на `LEFT OUTER JOIN` в SQL.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-134">This is like a `LEFT OUTER JOIN` in SQL.</span></span>

## <a name="example"></a><span data-ttu-id="9e2fb-135">Пример</span><span class="sxs-lookup"><span data-stu-id="9e2fb-135">Example</span></span>

<span data-ttu-id="9e2fb-136">В следующем примере кода выполняется неявное соединение для объединения списка клиентов с их заказами.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-136">The following code example performs an implicit join to combine a list of customers with their orders.</span></span>

[!code-vb[VbSimpleQuerySamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#13)]

## <a name="example"></a><span data-ttu-id="9e2fb-137">Пример</span><span class="sxs-lookup"><span data-stu-id="9e2fb-137">Example</span></span>

<span data-ttu-id="9e2fb-138">В следующем примере кода две коллекции объединяются с помощью предложения `Join`.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-138">The following code example joins two collections by using the `Join` clause.</span></span>

[!code-vb[VbSimpleQuerySamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples2.vb#12)]

<span data-ttu-id="9e2fb-139">В этом примере выводятся выходные данные, аналогичные приведенным ниже.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-139">This example will produce output similar to the following:</span></span>

`winlogon (968), Windows Logon`

`explorer (2424), File Explorer`

`cmd (5136), Command Window`

## <a name="example"></a><span data-ttu-id="9e2fb-140">Пример</span><span class="sxs-lookup"><span data-stu-id="9e2fb-140">Example</span></span>

<span data-ttu-id="9e2fb-141">В следующем примере кода две коллекции объединяются с помощью предложения `Join` с двумя ключевыми столбцами.</span><span class="sxs-lookup"><span data-stu-id="9e2fb-141">The following code example joins two collections by using the `Join` clause with two key columns.</span></span>

[!code-vb[VbSimpleQuerySamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples3.vb#17)]

<span data-ttu-id="9e2fb-142">В примере будет выведен результат, аналогичный приведенному ниже:</span><span class="sxs-lookup"><span data-stu-id="9e2fb-142">The example will produce output similar to the following:</span></span>

`winlogon (968), Windows Logon, Priority = 13`

`cmd (700), Command Window, Priority = 8`

`explorer (2424), File Explorer, Priority = 8`

## <a name="see-also"></a><span data-ttu-id="9e2fb-143">См. также</span><span class="sxs-lookup"><span data-stu-id="9e2fb-143">See also</span></span>

- <span data-ttu-id="9e2fb-144">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e2fb-144">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="9e2fb-145">Запросы</span><span class="sxs-lookup"><span data-stu-id="9e2fb-145">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="9e2fb-146">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="9e2fb-146">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="9e2fb-147">Предложение From</span><span class="sxs-lookup"><span data-stu-id="9e2fb-147">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="9e2fb-148">Предложение Group Join</span><span class="sxs-lookup"><span data-stu-id="9e2fb-148">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)
- [<span data-ttu-id="9e2fb-149">Предложения Where</span><span class="sxs-lookup"><span data-stu-id="9e2fb-149">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
