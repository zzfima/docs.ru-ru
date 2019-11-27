---
title: Предложение Take
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: 3082954ef84560ccb70f7a47cd3532f622829392
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349637"
---
# <a name="take-clause-visual-basic"></a><span data-ttu-id="0706e-102">Предложение Take (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0706e-102">Take Clause (Visual Basic)</span></span>
<span data-ttu-id="0706e-103">Возвращает указанное число идущих подряд элементов с начала коллекции.</span><span class="sxs-lookup"><span data-stu-id="0706e-103">Returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0706e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0706e-104">Syntax</span></span>  
  
```vb  
Take count  
```  
  
## <a name="parts"></a><span data-ttu-id="0706e-105">Части</span><span class="sxs-lookup"><span data-stu-id="0706e-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="0706e-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="0706e-106">Required.</span></span> <span data-ttu-id="0706e-107">Значение или выражение, результатом которого является число возвращаемых элементов последовательности.</span><span class="sxs-lookup"><span data-stu-id="0706e-107">A value or an expression that evaluates to the number of elements of the sequence to return.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0706e-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="0706e-108">Remarks</span></span>  
 <span data-ttu-id="0706e-109">Предложение `Take` вызывает включение в запрос указанного числа смежных элементов из начала списка результатов.</span><span class="sxs-lookup"><span data-stu-id="0706e-109">The `Take` clause causes a query to include a specified number of contiguous elements from the start of a results list.</span></span> <span data-ttu-id="0706e-110">Число включаемых элементов задается параметром `count`.</span><span class="sxs-lookup"><span data-stu-id="0706e-110">The number of elements to include is specified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="0706e-111">Можно использовать предложение `Take` с предложением `Skip`, чтобы получить диапазон данных из любого сегмента запроса.</span><span class="sxs-lookup"><span data-stu-id="0706e-111">You can use the `Take` clause with the `Skip` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="0706e-112">Для этого передайте индекс первого элемента диапазона в предложение `Skip` и размер диапазона в предложение `Take`.</span><span class="sxs-lookup"><span data-stu-id="0706e-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span> <span data-ttu-id="0706e-113">В этом случае предложение `Take` должно быть указано после предложения `Skip`.</span><span class="sxs-lookup"><span data-stu-id="0706e-113">In this case, the `Take` clause must be specified after the `Skip` clause.</span></span>  
  
 <span data-ttu-id="0706e-114">При использовании предложения `Take` в запросе может также потребоваться убедиться, что результаты возвращены в порядке, который позволит предложению `Take` включить предполагаемые результаты.</span><span class="sxs-lookup"><span data-stu-id="0706e-114">When you use the `Take` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Take` clause to include the intended results.</span></span> <span data-ttu-id="0706e-115">Дополнительные сведения о упорядочении результатов запроса см. в разделе [предложение ORDER BY](../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="0706e-115">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="0706e-116">Можно использовать предложение `TakeWhile`, чтобы указать, что возвращаются только определенные элементы, в зависимости от указанного условия.</span><span class="sxs-lookup"><span data-stu-id="0706e-116">You can use the `TakeWhile` clause to specify that only certain elements be returned, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0706e-117">Пример</span><span class="sxs-lookup"><span data-stu-id="0706e-117">Example</span></span>  
 <span data-ttu-id="0706e-118">В следующем примере кода используется предложение `Take` вместе с предложением `Skip` для возврата данных из запроса на страницах.</span><span class="sxs-lookup"><span data-stu-id="0706e-118">The following code example uses the `Take` clause together with the `Skip` clause to return data from a query in pages.</span></span> <span data-ttu-id="0706e-119">Функция "клиенты" использует предложение `Skip` для обхода клиентов в списке до получения значения начального индекса и использует предложение `Take` для возврата страницы клиентов, начиная с этого значения индекса.</span><span class="sxs-lookup"><span data-stu-id="0706e-119">The GetCustomers function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0706e-120">См. также</span><span class="sxs-lookup"><span data-stu-id="0706e-120">See also</span></span>

- <span data-ttu-id="0706e-121">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0706e-121">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="0706e-122">Запросы</span><span class="sxs-lookup"><span data-stu-id="0706e-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="0706e-123">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="0706e-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="0706e-124">Предложение From</span><span class="sxs-lookup"><span data-stu-id="0706e-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="0706e-125">Предложение Order By</span><span class="sxs-lookup"><span data-stu-id="0706e-125">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="0706e-126">Предложение Take While</span><span class="sxs-lookup"><span data-stu-id="0706e-126">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [<span data-ttu-id="0706e-127">Предложение Skip</span><span class="sxs-lookup"><span data-stu-id="0706e-127">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
