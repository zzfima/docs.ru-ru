---
title: Предложение Skip (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
ms.openlocfilehash: 1810bf4a6573c6fa36f1d8149bf341d45cfd6f52
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="skip-clause-visual-basic"></a><span data-ttu-id="5db64-102">Предложение Skip (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5db64-102">Skip Clause (Visual Basic)</span></span>
<span data-ttu-id="5db64-103">Пропускает заданное число элементов в коллекции и возвращает остальные элементы.</span><span class="sxs-lookup"><span data-stu-id="5db64-103">Bypasses a specified number of elements in a collection and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5db64-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5db64-104">Syntax</span></span>  
  
```  
Skip count  
```  
  
## <a name="parts"></a><span data-ttu-id="5db64-105">Части</span><span class="sxs-lookup"><span data-stu-id="5db64-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="5db64-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="5db64-106">Required.</span></span> <span data-ttu-id="5db64-107">Значение или выражение, результатом является число элементов последовательности, чтобы пропустить.</span><span class="sxs-lookup"><span data-stu-id="5db64-107">A value or an expression that evaluates to the number of elements of the sequence to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5db64-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="5db64-108">Remarks</span></span>  
 <span data-ttu-id="5db64-109">`Skip` Предложение вызывает запрос для пропуска элементов в начале списка результатов и возвращает остальные элементы.</span><span class="sxs-lookup"><span data-stu-id="5db64-109">The `Skip` clause causes a query to bypass elements at the beginning of a results list and return the remaining elements.</span></span> <span data-ttu-id="5db64-110">Число пропускаемых элементов определяется `count` параметра.</span><span class="sxs-lookup"><span data-stu-id="5db64-110">The number of elements to skip is identified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="5db64-111">Можно использовать `Skip` предложение with `Take` предложение для возврата диапазона данных из любого сегмента запроса.</span><span class="sxs-lookup"><span data-stu-id="5db64-111">You can use the `Skip` clause with the `Take` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="5db64-112">Для этого передайте индекс первого элемента диапазона `Skip` предложение и размер диапазона `Take` предложения.</span><span class="sxs-lookup"><span data-stu-id="5db64-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span>  
  
 <span data-ttu-id="5db64-113">При использовании `Skip` предложения в запросе могут также необходимо убедиться, что результаты возвращаются в порядке, который позволит `Skip` предложение для обхода желаемых результатов.</span><span class="sxs-lookup"><span data-stu-id="5db64-113">When you use the `Skip` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Skip` clause to bypass the intended results.</span></span> <span data-ttu-id="5db64-114">Дополнительные сведения о сортировке результатов запроса см. в разделе [предложение Order By](../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="5db64-114">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="5db64-115">Можно использовать `SkipWhile` предложений, чтобы указать, что только определенные элементы игнорируются в зависимости от предоставленного условия.</span><span class="sxs-lookup"><span data-stu-id="5db64-115">You can use the `SkipWhile` clause to specify that only certain elements are ignored, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5db64-116">Пример</span><span class="sxs-lookup"><span data-stu-id="5db64-116">Example</span></span>  
 <span data-ttu-id="5db64-117">Следующий пример кода использует `Skip` предложение вместе с `Take` предложение для возврата данных из запроса на страницах.</span><span class="sxs-lookup"><span data-stu-id="5db64-117">The following code example uses the `Skip` clause together with the `Take` clause to return data from a query in pages.</span></span> <span data-ttu-id="5db64-118">`GetCustomers` Функция использует `Skip` предложение для пропуска всех клиентов в списке, пока указанного начального индекса значение, а также используется `Take` предложение для возвращения страницы клиентов, начиная с этого значения индекса.</span><span class="sxs-lookup"><span data-stu-id="5db64-118">The `GetCustomers` function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5db64-119">См. также</span><span class="sxs-lookup"><span data-stu-id="5db64-119">See Also</span></span>  
 <span data-ttu-id="5db64-120">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5db64-120">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>  
 [<span data-ttu-id="5db64-121">Запросы</span><span class="sxs-lookup"><span data-stu-id="5db64-121">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="5db64-122">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="5db64-122">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="5db64-123">Предложение From</span><span class="sxs-lookup"><span data-stu-id="5db64-123">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="5db64-124">Предложение Order By</span><span class="sxs-lookup"><span data-stu-id="5db64-124">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [<span data-ttu-id="5db64-125">Предложение Skip While</span><span class="sxs-lookup"><span data-stu-id="5db64-125">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [<span data-ttu-id="5db64-126">Предложение Take</span><span class="sxs-lookup"><span data-stu-id="5db64-126">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
