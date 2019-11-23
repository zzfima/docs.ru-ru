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
ms.openlocfilehash: fe6ee470698504bc0434930cc9aa6de712e04254
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004672"
---
# <a name="take-while-clause-visual-basic"></a><span data-ttu-id="fa3ba-102">Предложение Take While (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa3ba-102">Take While Clause (Visual Basic)</span></span>
<span data-ttu-id="fa3ba-103">Включает элементы в коллекцию, если заданное условие имеет значение `true`, и пропускает остальные элементы.</span><span class="sxs-lookup"><span data-stu-id="fa3ba-103">Includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa3ba-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fa3ba-104">Syntax</span></span>  
  
```vb  
Take While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="fa3ba-105">Части</span><span class="sxs-lookup"><span data-stu-id="fa3ba-105">Parts</span></span>  
  
|<span data-ttu-id="fa3ba-106">Термин</span><span class="sxs-lookup"><span data-stu-id="fa3ba-106">Term</span></span>|<span data-ttu-id="fa3ba-107">Определение</span><span class="sxs-lookup"><span data-stu-id="fa3ba-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="fa3ba-108">Обязательное.</span><span class="sxs-lookup"><span data-stu-id="fa3ba-108">Required.</span></span> <span data-ttu-id="fa3ba-109">Выражение, представляющее условие для проверки элементов.</span><span class="sxs-lookup"><span data-stu-id="fa3ba-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="fa3ba-110">Выражение должно возвращать `Boolean` значение или функциональный эквивалент, например `Integer`, который вычисляется как `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="fa3ba-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa3ba-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="fa3ba-111">Remarks</span></span>  
 <span data-ttu-id="fa3ba-112">Предложение `Take While` включает элементы из начала результата запроса до тех пор, пока переданный `expression` не возвратит `false`.</span><span class="sxs-lookup"><span data-stu-id="fa3ba-112">The `Take While` clause includes elements from the start of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="fa3ba-113">После того как `expression` возвращает `false`, запрос будет обходить все оставшиеся элементы.</span><span class="sxs-lookup"><span data-stu-id="fa3ba-113">After the `expression` returns `false`, the query will bypass all remaining elements.</span></span> <span data-ttu-id="fa3ba-114">Для оставшихся результатов `expression` игнорируется.</span><span class="sxs-lookup"><span data-stu-id="fa3ba-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="fa3ba-115">Предложение `Take While` отличается от предложения `Where` в том, что предложение `Where` можно использовать для включения всех элементов из запроса, удовлетворяющего определенному условию.</span><span class="sxs-lookup"><span data-stu-id="fa3ba-115">The `Take While` clause differs from the `Where` clause in that the `Where` clause can be used to include all elements from a query that meet a particular condition.</span></span> <span data-ttu-id="fa3ba-116">Предложение `Take While` включает элементы только до первого момента, когда условие не будет удовлетворено.</span><span class="sxs-lookup"><span data-stu-id="fa3ba-116">The `Take While` clause includes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="fa3ba-117">Предложение `Take While` наиболее полезно при работе с упорядоченным результатом запроса.</span><span class="sxs-lookup"><span data-stu-id="fa3ba-117">The `Take While` clause is most useful when you are working with an ordered query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa3ba-118">Пример</span><span class="sxs-lookup"><span data-stu-id="fa3ba-118">Example</span></span>  
 <span data-ttu-id="fa3ba-119">В следующем примере кода предложение `Take While` используется для получения результатов до тех пор, пока не будет найден первый клиент без заказов.</span><span class="sxs-lookup"><span data-stu-id="fa3ba-119">The following code example uses the `Take While` clause to retrieve results until the first customer without any orders is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="fa3ba-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="fa3ba-120">See also</span></span>

- <span data-ttu-id="fa3ba-121">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa3ba-121">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="fa3ba-122">Запросы</span><span class="sxs-lookup"><span data-stu-id="fa3ba-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="fa3ba-123">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="fa3ba-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="fa3ba-124">Предложение From</span><span class="sxs-lookup"><span data-stu-id="fa3ba-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="fa3ba-125">Предложение Take</span><span class="sxs-lookup"><span data-stu-id="fa3ba-125">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="fa3ba-126">Предложение Skip While</span><span class="sxs-lookup"><span data-stu-id="fa3ba-126">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="fa3ba-127">Предложения Where</span><span class="sxs-lookup"><span data-stu-id="fa3ba-127">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
