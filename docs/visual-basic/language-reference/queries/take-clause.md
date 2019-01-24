---
title: Предложение Take (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: bdd12340c5a0bd522c09a22e74c7b4f487cc5821
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54626736"
---
# <a name="take-clause-visual-basic"></a><span data-ttu-id="8e159-102">Предложение Take (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e159-102">Take Clause (Visual Basic)</span></span>
<span data-ttu-id="8e159-103">Возвращает указанное число идущих подряд элементов с начала коллекции.</span><span class="sxs-lookup"><span data-stu-id="8e159-103">Returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e159-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8e159-104">Syntax</span></span>  
  
```  
Take count  
```  
  
## <a name="parts"></a><span data-ttu-id="8e159-105">Части</span><span class="sxs-lookup"><span data-stu-id="8e159-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="8e159-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="8e159-106">Required.</span></span> <span data-ttu-id="8e159-107">Значение или выражение, результатом является число элементов последовательности для возврата.</span><span class="sxs-lookup"><span data-stu-id="8e159-107">A value or an expression that evaluates to the number of elements of the sequence to return.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e159-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="8e159-108">Remarks</span></span>  
 <span data-ttu-id="8e159-109">`Take` Предложение вызывает запрос, чтобы включить указанное число идущих подряд элементов с начала списка результатов.</span><span class="sxs-lookup"><span data-stu-id="8e159-109">The `Take` clause causes a query to include a specified number of contiguous elements from the start of a results list.</span></span> <span data-ttu-id="8e159-110">Число элементов для включения задается `count` параметра.</span><span class="sxs-lookup"><span data-stu-id="8e159-110">The number of elements to include is specified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="8e159-111">Можно использовать `Take` предложение with `Skip` предложение можно получить диапазон данных из любого фрагмента запроса.</span><span class="sxs-lookup"><span data-stu-id="8e159-111">You can use the `Take` clause with the `Skip` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="8e159-112">Для этого передайте индекс первого элемента диапазона `Skip` предложение и размер диапазона `Take` предложение.</span><span class="sxs-lookup"><span data-stu-id="8e159-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span> <span data-ttu-id="8e159-113">В этом случае `Take` предложение должно быть указано после `Skip` предложение.</span><span class="sxs-lookup"><span data-stu-id="8e159-113">In this case, the `Take` clause must be specified after the `Skip` clause.</span></span>  
  
 <span data-ttu-id="8e159-114">При использовании `Take` предложением запроса, также необходимо убедиться, что результаты возвращаются в порядке, который позволит `Take` предложение для включения нужных результатов.</span><span class="sxs-lookup"><span data-stu-id="8e159-114">When you use the `Take` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Take` clause to include the intended results.</span></span> <span data-ttu-id="8e159-115">Дополнительные сведения о сортировке результатов запроса, см. в разделе [предложение Order By](../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="8e159-115">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="8e159-116">Можно использовать `TakeWhile` предложение, чтобы указать, что возвращаться только определенные элементы, в зависимости от предоставленного условия.</span><span class="sxs-lookup"><span data-stu-id="8e159-116">You can use the `TakeWhile` clause to specify that only certain elements be returned, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e159-117">Пример</span><span class="sxs-lookup"><span data-stu-id="8e159-117">Example</span></span>  
 <span data-ttu-id="8e159-118">В следующем примере кода используется `Take` предложение вместе с `Skip` предложение, чтобы вернуть данные из запроса на страницах.</span><span class="sxs-lookup"><span data-stu-id="8e159-118">The following code example uses the `Take` clause together with the `Skip` clause to return data from a query in pages.</span></span> <span data-ttu-id="8e159-119">GetCustomers функция использует `Skip` предложение для пропуска всех клиентов, в списке, пока не указанного начального индекса значение, а также используется `Take` предложение для возврата страницы клиентов, начиная с этого значения индекса.</span><span class="sxs-lookup"><span data-stu-id="8e159-119">The GetCustomers function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8e159-120">См. также</span><span class="sxs-lookup"><span data-stu-id="8e159-120">See also</span></span>
- <span data-ttu-id="8e159-121">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e159-121">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="8e159-122">Запросы</span><span class="sxs-lookup"><span data-stu-id="8e159-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="8e159-123">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="8e159-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="8e159-124">Предложение From</span><span class="sxs-lookup"><span data-stu-id="8e159-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="8e159-125">Предложение Order By</span><span class="sxs-lookup"><span data-stu-id="8e159-125">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="8e159-126">Предложение Take While</span><span class="sxs-lookup"><span data-stu-id="8e159-126">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [<span data-ttu-id="8e159-127">Предложение Skip</span><span class="sxs-lookup"><span data-stu-id="8e159-127">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
