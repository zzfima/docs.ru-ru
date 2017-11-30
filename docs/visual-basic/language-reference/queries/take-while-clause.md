---
title: "Предложение Take While (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5c8add6c55bb9353bac3489e68f497cb32785aad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="take-while-clause-visual-basic"></a><span data-ttu-id="0cd18-102">Предложение Take While (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0cd18-102">Take While Clause (Visual Basic)</span></span>
<span data-ttu-id="0cd18-103">Включает элементы в коллекцию, если заданное условие имеет значение `true`, и пропускает остальные элементы.</span><span class="sxs-lookup"><span data-stu-id="0cd18-103">Includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cd18-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0cd18-104">Syntax</span></span>  
  
```  
Take While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="0cd18-105">Части</span><span class="sxs-lookup"><span data-stu-id="0cd18-105">Parts</span></span>  
  
|<span data-ttu-id="0cd18-106">Термин</span><span class="sxs-lookup"><span data-stu-id="0cd18-106">Term</span></span>|<span data-ttu-id="0cd18-107">Определение</span><span class="sxs-lookup"><span data-stu-id="0cd18-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="0cd18-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="0cd18-108">Required.</span></span> <span data-ttu-id="0cd18-109">Выражение, представляющее условие для проверки элементов.</span><span class="sxs-lookup"><span data-stu-id="0cd18-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="0cd18-110">Выражение должно возвращать `Boolean` значение или функциональный эквивалент, таких как `Integer` будут вычисляться как `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="0cd18-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0cd18-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="0cd18-111">Remarks</span></span>  
 <span data-ttu-id="0cd18-112">`Take While` Предложение включает элементы от начала результата запроса до предоставленного `expression` возвращает `false`.</span><span class="sxs-lookup"><span data-stu-id="0cd18-112">The `Take While` clause includes elements from the start of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="0cd18-113">После `expression` возвращает `false`, запрос будет выполнять все оставшиеся элементы.</span><span class="sxs-lookup"><span data-stu-id="0cd18-113">After the `expression` returns `false`, the query will bypass all remaining elements.</span></span> <span data-ttu-id="0cd18-114">`expression` Игнорируется для оставшихся результатов.</span><span class="sxs-lookup"><span data-stu-id="0cd18-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="0cd18-115">`Take While` Предложение отличается от `Where` предложение в том, что `Where` предложение может использоваться для включения всех элементов из запроса, которые удовлетворяют определенному условию.</span><span class="sxs-lookup"><span data-stu-id="0cd18-115">The `Take While` clause differs from the `Where` clause in that the `Where` clause can be used to include all elements from a query that meet a particular condition.</span></span> <span data-ttu-id="0cd18-116">`Take While` Предложение включает элементы только до момента первого, условие не выполняется.</span><span class="sxs-lookup"><span data-stu-id="0cd18-116">The `Take While` clause includes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="0cd18-117">`Take While` Предложение наиболее полезно при работе с упорядоченным результатом запроса.</span><span class="sxs-lookup"><span data-stu-id="0cd18-117">The `Take While` clause is most useful when you are working with an ordered query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0cd18-118">Пример</span><span class="sxs-lookup"><span data-stu-id="0cd18-118">Example</span></span>  
 <span data-ttu-id="0cd18-119">Следующий пример кода использует `Take While` предложение для получения результатов, пока не будет найден первый клиент без заказов.</span><span class="sxs-lookup"><span data-stu-id="0cd18-119">The following code example uses the `Take While` clause to retrieve results until the first customer without any orders is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#2](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-while-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="0cd18-120">См. также</span><span class="sxs-lookup"><span data-stu-id="0cd18-120">See Also</span></span>  
 <span data-ttu-id="0cd18-121">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0cd18-121">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>  
 [<span data-ttu-id="0cd18-122">Запросы</span><span class="sxs-lookup"><span data-stu-id="0cd18-122">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="0cd18-123">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="0cd18-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="0cd18-124">Предложение From</span><span class="sxs-lookup"><span data-stu-id="0cd18-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="0cd18-125">Предложение Take</span><span class="sxs-lookup"><span data-stu-id="0cd18-125">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)  
 [<span data-ttu-id="0cd18-126">Предложение Skip While</span><span class="sxs-lookup"><span data-stu-id="0cd18-126">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [<span data-ttu-id="0cd18-127">Предложения Where</span><span class="sxs-lookup"><span data-stu-id="0cd18-127">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
