---
title: "Предложение Take (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ee289a24c15226126a526af116ed53b4a9055b35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="take-clause-visual-basic"></a><span data-ttu-id="e66ea-102">Предложение Take (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e66ea-102">Take Clause (Visual Basic)</span></span>
<span data-ttu-id="e66ea-103">Возвращает указанное число идущих подряд элементов с начала коллекции.</span><span class="sxs-lookup"><span data-stu-id="e66ea-103">Returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e66ea-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e66ea-104">Syntax</span></span>  
  
```  
Take count  
```  
  
## <a name="parts"></a><span data-ttu-id="e66ea-105">Части</span><span class="sxs-lookup"><span data-stu-id="e66ea-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="e66ea-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="e66ea-106">Required.</span></span> <span data-ttu-id="e66ea-107">Значение или выражение, результатом является число элементов последовательности для возврата.</span><span class="sxs-lookup"><span data-stu-id="e66ea-107">A value or an expression that evaluates to the number of elements of the sequence to return.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e66ea-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="e66ea-108">Remarks</span></span>  
 <span data-ttu-id="e66ea-109">`Take` Предложение вызывает запрос, чтобы включить заданное число смежных элементов от начала списка результатов.</span><span class="sxs-lookup"><span data-stu-id="e66ea-109">The `Take` clause causes a query to include a specified number of contiguous elements from the start of a results list.</span></span> <span data-ttu-id="e66ea-110">Число элементов для включения определяется `count` параметра.</span><span class="sxs-lookup"><span data-stu-id="e66ea-110">The number of elements to include is specified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="e66ea-111">Можно использовать `Take` предложение with `Skip` предложение для возврата диапазона данных из любого сегмента запроса.</span><span class="sxs-lookup"><span data-stu-id="e66ea-111">You can use the `Take` clause with the `Skip` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="e66ea-112">Для этого передайте индекс первого элемента диапазона `Skip` предложение и размер диапазона `Take` предложения.</span><span class="sxs-lookup"><span data-stu-id="e66ea-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span> <span data-ttu-id="e66ea-113">В этом случае `Take` предложение должно быть указано после `Skip` предложения.</span><span class="sxs-lookup"><span data-stu-id="e66ea-113">In this case, the `Take` clause must be specified after the `Skip` clause.</span></span>  
  
 <span data-ttu-id="e66ea-114">При использовании `Take` предложения в запросе могут также необходимо убедиться, что результаты возвращаются в порядке, который позволит `Take` предложений, чтобы включить нужные результаты.</span><span class="sxs-lookup"><span data-stu-id="e66ea-114">When you use the `Take` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Take` clause to include the intended results.</span></span> <span data-ttu-id="e66ea-115">Дополнительные сведения о сортировке результатов запроса см. в разделе [предложение Order By](../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="e66ea-115">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="e66ea-116">Можно использовать `TakeWhile` предложений, чтобы указать, что возвращаться только некоторые элементы, в зависимости от предоставленного условия.</span><span class="sxs-lookup"><span data-stu-id="e66ea-116">You can use the `TakeWhile` clause to specify that only certain elements be returned, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e66ea-117">Пример</span><span class="sxs-lookup"><span data-stu-id="e66ea-117">Example</span></span>  
 <span data-ttu-id="e66ea-118">Следующий пример кода использует `Take` предложение вместе с `Skip` предложение для возврата данных из запроса на страницах.</span><span class="sxs-lookup"><span data-stu-id="e66ea-118">The following code example uses the `Take` clause together with the `Skip` clause to return data from a query in pages.</span></span> <span data-ttu-id="e66ea-119">Использует функцию GetCustomers `Skip` предложение для пропуска всех клиентов в списке, пока указанного начального индекса значение, а также используется `Take` предложение для возвращения страницы клиентов, начиная с этого значения индекса.</span><span class="sxs-lookup"><span data-stu-id="e66ea-119">The GetCustomers function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e66ea-120">См. также</span><span class="sxs-lookup"><span data-stu-id="e66ea-120">See Also</span></span>  
 <span data-ttu-id="e66ea-121">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e66ea-121">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>  
 [<span data-ttu-id="e66ea-122">Запросы</span><span class="sxs-lookup"><span data-stu-id="e66ea-122">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="e66ea-123">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="e66ea-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="e66ea-124">Предложение From</span><span class="sxs-lookup"><span data-stu-id="e66ea-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="e66ea-125">Предложение Order By</span><span class="sxs-lookup"><span data-stu-id="e66ea-125">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [<span data-ttu-id="e66ea-126">Предложение Take While</span><span class="sxs-lookup"><span data-stu-id="e66ea-126">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 [<span data-ttu-id="e66ea-127">Предложение Skip</span><span class="sxs-lookup"><span data-stu-id="e66ea-127">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
