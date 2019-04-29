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
ms.openlocfilehash: db2d79596895505ddaa7778e831082a94c7ad44e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945253"
---
# <a name="skip-clause-visual-basic"></a><span data-ttu-id="23a1d-102">Предложение Skip (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23a1d-102">Skip Clause (Visual Basic)</span></span>
<span data-ttu-id="23a1d-103">Пропускает заданное число элементов в коллекции и возвращает остальные элементы.</span><span class="sxs-lookup"><span data-stu-id="23a1d-103">Bypasses a specified number of elements in a collection and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23a1d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="23a1d-104">Syntax</span></span>  
  
```  
Skip count  
```  
  
## <a name="parts"></a><span data-ttu-id="23a1d-105">Части</span><span class="sxs-lookup"><span data-stu-id="23a1d-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="23a1d-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="23a1d-106">Required.</span></span> <span data-ttu-id="23a1d-107">Значение или выражение, результатом является число элементов последовательности, чтобы пропустить.</span><span class="sxs-lookup"><span data-stu-id="23a1d-107">A value or an expression that evaluates to the number of elements of the sequence to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23a1d-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="23a1d-108">Remarks</span></span>  
 <span data-ttu-id="23a1d-109">`Skip` Предложение вызывает запрос для пропуска элементов в начале списка результатов и возвращает остальные элементы.</span><span class="sxs-lookup"><span data-stu-id="23a1d-109">The `Skip` clause causes a query to bypass elements at the beginning of a results list and return the remaining elements.</span></span> <span data-ttu-id="23a1d-110">Количество пропускаемых элементов определяется `count` параметра.</span><span class="sxs-lookup"><span data-stu-id="23a1d-110">The number of elements to skip is identified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="23a1d-111">Можно использовать `Skip` предложение with `Take` предложение можно получить диапазон данных из любого фрагмента запроса.</span><span class="sxs-lookup"><span data-stu-id="23a1d-111">You can use the `Skip` clause with the `Take` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="23a1d-112">Для этого передайте индекс первого элемента диапазона `Skip` предложение и размер диапазона `Take` предложение.</span><span class="sxs-lookup"><span data-stu-id="23a1d-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span>  
  
 <span data-ttu-id="23a1d-113">При использовании `Skip` предложением запроса, также необходимо убедиться, что результаты возвращаются в порядке, который позволит `Skip` предложение для обхода желаемых результатов.</span><span class="sxs-lookup"><span data-stu-id="23a1d-113">When you use the `Skip` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Skip` clause to bypass the intended results.</span></span> <span data-ttu-id="23a1d-114">Дополнительные сведения о сортировке результатов запроса, см. в разделе [предложение Order By](../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="23a1d-114">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="23a1d-115">Можно использовать `SkipWhile` предложение, чтобы указать, что только определенные элементы игнорируются, в зависимости от предоставленного условия.</span><span class="sxs-lookup"><span data-stu-id="23a1d-115">You can use the `SkipWhile` clause to specify that only certain elements are ignored, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23a1d-116">Пример</span><span class="sxs-lookup"><span data-stu-id="23a1d-116">Example</span></span>  
 <span data-ttu-id="23a1d-117">В следующем примере кода используется `Skip` предложение вместе с `Take` предложение, чтобы вернуть данные из запроса на страницах.</span><span class="sxs-lookup"><span data-stu-id="23a1d-117">The following code example uses the `Skip` clause together with the `Take` clause to return data from a query in pages.</span></span> <span data-ttu-id="23a1d-118">`GetCustomers` Функция использует `Skip` предложение для пропуска всех клиентов, в списке, пока не указанного начального индекса значение, а также используется `Take` предложение для возврата страницы клиентов, начиная с этого значения индекса.</span><span class="sxs-lookup"><span data-stu-id="23a1d-118">The `GetCustomers` function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="23a1d-119">См. также</span><span class="sxs-lookup"><span data-stu-id="23a1d-119">See also</span></span>

- <span data-ttu-id="23a1d-120">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23a1d-120">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="23a1d-121">Запросы</span><span class="sxs-lookup"><span data-stu-id="23a1d-121">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="23a1d-122">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="23a1d-122">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="23a1d-123">Предложение From</span><span class="sxs-lookup"><span data-stu-id="23a1d-123">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="23a1d-124">Предложение Order By</span><span class="sxs-lookup"><span data-stu-id="23a1d-124">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="23a1d-125">Предложение Skip While</span><span class="sxs-lookup"><span data-stu-id="23a1d-125">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="23a1d-126">Предложение Take</span><span class="sxs-lookup"><span data-stu-id="23a1d-126">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
