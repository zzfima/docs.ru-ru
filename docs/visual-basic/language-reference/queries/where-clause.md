---
title: Предложение Where
ms.date: 07/20/2015
f1_keywords:
- vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
ms.openlocfilehash: 60b7ebe96ce0c4580c36675b2e4aa5f9888732c3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349627"
---
# <a name="where-clause-visual-basic"></a><span data-ttu-id="5f579-102">Предложение Where (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5f579-102">Where Clause (Visual Basic)</span></span>
<span data-ttu-id="5f579-103">Specifies the filtering condition for a query.</span><span class="sxs-lookup"><span data-stu-id="5f579-103">Specifies the filtering condition for a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f579-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5f579-104">Syntax</span></span>  
  
```vb  
Where condition  
```  
  
## <a name="parts"></a><span data-ttu-id="5f579-105">Части</span><span class="sxs-lookup"><span data-stu-id="5f579-105">Parts</span></span>  
 `condition`  
 <span data-ttu-id="5f579-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="5f579-106">Required.</span></span> <span data-ttu-id="5f579-107">An expression that determines whether the values for the current item in the collection are included in the output collection.</span><span class="sxs-lookup"><span data-stu-id="5f579-107">An expression that determines whether the values for the current item in the collection are included in the output collection.</span></span> <span data-ttu-id="5f579-108">The expression must evaluate to a `Boolean` value or the equivalent of a `Boolean` value.</span><span class="sxs-lookup"><span data-stu-id="5f579-108">The expression must evaluate to a `Boolean` value or the equivalent of a `Boolean` value.</span></span> <span data-ttu-id="5f579-109">If the condition evaluates to `True`, the element is included in the query result; otherwise, the element is excluded from the query result.</span><span class="sxs-lookup"><span data-stu-id="5f579-109">If the condition evaluates to `True`, the element is included in the query result; otherwise, the element is excluded from the query result.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f579-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="5f579-110">Remarks</span></span>  
 <span data-ttu-id="5f579-111">The `Where` clause enables you to filter query data by selecting only elements that meet certain criteria.</span><span class="sxs-lookup"><span data-stu-id="5f579-111">The `Where` clause enables you to filter query data by selecting only elements that meet certain criteria.</span></span> <span data-ttu-id="5f579-112">Elements whose values cause the `Where` clause to evaluate to `True` are included in the query result; other elements are excluded.</span><span class="sxs-lookup"><span data-stu-id="5f579-112">Elements whose values cause the `Where` clause to evaluate to `True` are included in the query result; other elements are excluded.</span></span> <span data-ttu-id="5f579-113">The expression that is used in a `Where` clause must evaluate to a `Boolean` or the equivalent of a `Boolean`, such as an Integer that evaluates to `False` when its value is zero.</span><span class="sxs-lookup"><span data-stu-id="5f579-113">The expression that is used in a `Where` clause must evaluate to a `Boolean` or the equivalent of a `Boolean`, such as an Integer that evaluates to `False` when its value is zero.</span></span> <span data-ttu-id="5f579-114">You can combine multiple expressions in a `Where` clause by using logical operators such as `And`, `Or`, `AndAlso`, `OrElse`, `Is`, and `IsNot`.</span><span class="sxs-lookup"><span data-stu-id="5f579-114">You can combine multiple expressions in a `Where` clause by using logical operators such as `And`, `Or`, `AndAlso`, `OrElse`, `Is`, and `IsNot`.</span></span>  
  
 <span data-ttu-id="5f579-115">By default, query expressions are not evaluated until they are accessed—for example, when they are data-bound or iterated through in a `For` loop.</span><span class="sxs-lookup"><span data-stu-id="5f579-115">By default, query expressions are not evaluated until they are accessed—for example, when they are data-bound or iterated through in a `For` loop.</span></span> <span data-ttu-id="5f579-116">As a result, the `Where` clause is not evaluated until the query is accessed.</span><span class="sxs-lookup"><span data-stu-id="5f579-116">As a result, the `Where` clause is not evaluated until the query is accessed.</span></span> <span data-ttu-id="5f579-117">If you have values external to the query that are used in the `Where` clause, ensure that the appropriate value is used in the `Where` clause at the time the query is executed.</span><span class="sxs-lookup"><span data-stu-id="5f579-117">If you have values external to the query that are used in the `Where` clause, ensure that the appropriate value is used in the `Where` clause at the time the query is executed.</span></span> <span data-ttu-id="5f579-118">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span><span class="sxs-lookup"><span data-stu-id="5f579-118">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
 <span data-ttu-id="5f579-119">You can call functions within a `Where` clause to perform a calculation or operation on a value from the current element in the collection.</span><span class="sxs-lookup"><span data-stu-id="5f579-119">You can call functions within a `Where` clause to perform a calculation or operation on a value from the current element in the collection.</span></span> <span data-ttu-id="5f579-120">Calling a function in a `Where` clause can cause the query to be executed immediately when it is defined instead of when it is accessed.</span><span class="sxs-lookup"><span data-stu-id="5f579-120">Calling a function in a `Where` clause can cause the query to be executed immediately when it is defined instead of when it is accessed.</span></span> <span data-ttu-id="5f579-121">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span><span class="sxs-lookup"><span data-stu-id="5f579-121">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f579-122">Пример</span><span class="sxs-lookup"><span data-stu-id="5f579-122">Example</span></span>  
 <span data-ttu-id="5f579-123">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span><span class="sxs-lookup"><span data-stu-id="5f579-123">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="5f579-124">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span><span class="sxs-lookup"><span data-stu-id="5f579-124">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="5f579-125">The `For Each` loop displays the company name for each customer in the query result.</span><span class="sxs-lookup"><span data-stu-id="5f579-125">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a><span data-ttu-id="5f579-126">Пример</span><span class="sxs-lookup"><span data-stu-id="5f579-126">Example</span></span>  
 <span data-ttu-id="5f579-127">The following example uses `And` and `Or` logical operators in the `Where` clause.</span><span class="sxs-lookup"><span data-stu-id="5f579-127">The following example uses `And` and `Or` logical operators in the `Where` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="5f579-128">См. также</span><span class="sxs-lookup"><span data-stu-id="5f579-128">See also</span></span>

- <span data-ttu-id="5f579-129">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5f579-129">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="5f579-130">Запросы</span><span class="sxs-lookup"><span data-stu-id="5f579-130">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="5f579-131">Предложение From</span><span class="sxs-lookup"><span data-stu-id="5f579-131">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="5f579-132">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="5f579-132">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="5f579-133">Оператор For Each...Next</span><span class="sxs-lookup"><span data-stu-id="5f579-133">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
