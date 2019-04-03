---
title: Предложение Take While (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: 080a106fc1deeb54165511ed03d7c7c5d2060f21
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818753"
---
# <a name="take-while-clause-visual-basic"></a><span data-ttu-id="88fe8-102">Предложение Take While (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88fe8-102">Take While Clause (Visual Basic)</span></span>
<span data-ttu-id="88fe8-103">Включает элементы в коллекцию, если заданное условие имеет значение `true`, и пропускает остальные элементы.</span><span class="sxs-lookup"><span data-stu-id="88fe8-103">Includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88fe8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="88fe8-104">Syntax</span></span>  
  
```  
Take While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="88fe8-105">Части</span><span class="sxs-lookup"><span data-stu-id="88fe8-105">Parts</span></span>  
  
|<span data-ttu-id="88fe8-106">Термин</span><span class="sxs-lookup"><span data-stu-id="88fe8-106">Term</span></span>|<span data-ttu-id="88fe8-107">Определение</span><span class="sxs-lookup"><span data-stu-id="88fe8-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="88fe8-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="88fe8-108">Required.</span></span> <span data-ttu-id="88fe8-109">Выражение, которое представляет условие для проверки элементов.</span><span class="sxs-lookup"><span data-stu-id="88fe8-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="88fe8-110">Выражение должно возвращать `Boolean` значение или функциональный эквивалент, например `Integer` для оценки в качестве `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="88fe8-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88fe8-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="88fe8-111">Remarks</span></span>  
 <span data-ttu-id="88fe8-112">`Take While` Предложение включает элементы от начала результата запроса до предоставленного `expression` возвращает `false`.</span><span class="sxs-lookup"><span data-stu-id="88fe8-112">The `Take While` clause includes elements from the start of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="88fe8-113">После `expression` возвращает `false`, запрос будет выполнять все оставшиеся элементы.</span><span class="sxs-lookup"><span data-stu-id="88fe8-113">After the `expression` returns `false`, the query will bypass all remaining elements.</span></span> <span data-ttu-id="88fe8-114">`expression` Игнорируется для оставшихся результатов.</span><span class="sxs-lookup"><span data-stu-id="88fe8-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="88fe8-115">`Take While` Предложение отличается от `Where` предложение, в который `Where` предложение может использоваться для включения всех элементов из запроса, которые удовлетворяют определенному условию.</span><span class="sxs-lookup"><span data-stu-id="88fe8-115">The `Take While` clause differs from the `Where` clause in that the `Where` clause can be used to include all elements from a query that meet a particular condition.</span></span> <span data-ttu-id="88fe8-116">`Take While` Предложение включает элементы только до момента первого, условие не выполняется.</span><span class="sxs-lookup"><span data-stu-id="88fe8-116">The `Take While` clause includes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="88fe8-117">`Take While` Предложение наиболее полезно при работе с упорядоченным результатом запроса.</span><span class="sxs-lookup"><span data-stu-id="88fe8-117">The `Take While` clause is most useful when you are working with an ordered query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88fe8-118">Пример</span><span class="sxs-lookup"><span data-stu-id="88fe8-118">Example</span></span>  
 <span data-ttu-id="88fe8-119">В следующем примере кода используется `Take While` предложение для получения результатов, пока не будет найден первый клиент без заказов.</span><span class="sxs-lookup"><span data-stu-id="88fe8-119">The following code example uses the `Take While` clause to retrieve results until the first customer without any orders is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="88fe8-120">См. также</span><span class="sxs-lookup"><span data-stu-id="88fe8-120">See also</span></span>

- <span data-ttu-id="88fe8-121">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88fe8-121">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="88fe8-122">Запросы</span><span class="sxs-lookup"><span data-stu-id="88fe8-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="88fe8-123">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="88fe8-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="88fe8-124">Предложение From</span><span class="sxs-lookup"><span data-stu-id="88fe8-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="88fe8-125">Предложение Take</span><span class="sxs-lookup"><span data-stu-id="88fe8-125">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="88fe8-126">Предложение Skip While</span><span class="sxs-lookup"><span data-stu-id="88fe8-126">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="88fe8-127">Предложения Where</span><span class="sxs-lookup"><span data-stu-id="88fe8-127">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
