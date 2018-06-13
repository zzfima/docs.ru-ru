---
title: Предложение Distinct (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: 4b0ce12f6361d3dc6e5cc3601e96fc3a9bcf3841
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603981"
---
# <a name="distinct-clause-visual-basic"></a><span data-ttu-id="1422f-102">Предложение Distinct (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1422f-102">Distinct Clause (Visual Basic)</span></span>
<span data-ttu-id="1422f-103">Ограничивает значения текущей переменной диапазона, чтобы исключить повторяющиеся значения в предложениях последующих запросов.</span><span class="sxs-lookup"><span data-stu-id="1422f-103">Restricts the values of the current range variable to eliminate duplicate values in subsequent query clauses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1422f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1422f-104">Syntax</span></span>  
  
```  
Distinct  
```  
  
## <a name="remarks"></a><span data-ttu-id="1422f-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="1422f-105">Remarks</span></span>  
 <span data-ttu-id="1422f-106">Можно использовать `Distinct` предложение, чтобы получить список уникальных элементов.</span><span class="sxs-lookup"><span data-stu-id="1422f-106">You can use the `Distinct` clause to return a list of unique items.</span></span> <span data-ttu-id="1422f-107">`Distinct` Предложение вызывает запрос, чтобы игнорировать повторяющиеся результаты запроса.</span><span class="sxs-lookup"><span data-stu-id="1422f-107">The `Distinct` clause causes the query to ignore duplicate query results.</span></span> <span data-ttu-id="1422f-108">`Distinct` Предложение распространяется на повторяющиеся значения все возвращаемые поля, заданные параметром `Select` предложения.</span><span class="sxs-lookup"><span data-stu-id="1422f-108">The `Distinct` clause applies to duplicate values for all return fields specified by the `Select` clause.</span></span> <span data-ttu-id="1422f-109">Если не `Select` указано предложение `Distinct` предложение применяется к переменной диапазона для запроса, указанного в `From` предложения.</span><span class="sxs-lookup"><span data-stu-id="1422f-109">If no `Select` clause is specified, the `Distinct` clause is applied to the range variable for the query identified in the `From` clause.</span></span> <span data-ttu-id="1422f-110">Если переменная диапазона не является неизменяемым типом, запрос только игнорировать результата запроса, если все члены типа соответствуют существующим результатам запроса.</span><span class="sxs-lookup"><span data-stu-id="1422f-110">If the range variable is not an immutable type, the query will only ignore a query result if all members of the type match an existing query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1422f-111">Пример</span><span class="sxs-lookup"><span data-stu-id="1422f-111">Example</span></span>  
 <span data-ttu-id="1422f-112">Следующее выражение запроса соединяет список клиентов и список заказов клиента.</span><span class="sxs-lookup"><span data-stu-id="1422f-112">The following query expression joins a list of customers and a list of customer orders.</span></span> <span data-ttu-id="1422f-113">`Distinct` Предложение включена, чтобы получить список уникальных имен клиентов и порядок даты.</span><span class="sxs-lookup"><span data-stu-id="1422f-113">The `Distinct` clause is included to return a list of unique customer names and order dates.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#20](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/distinct-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="1422f-114">См. также</span><span class="sxs-lookup"><span data-stu-id="1422f-114">See Also</span></span>  
 <span data-ttu-id="1422f-115">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1422f-115">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>  
 [<span data-ttu-id="1422f-116">Запросы</span><span class="sxs-lookup"><span data-stu-id="1422f-116">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="1422f-117">Предложение From</span><span class="sxs-lookup"><span data-stu-id="1422f-117">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="1422f-118">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="1422f-118">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="1422f-119">Предложения Where</span><span class="sxs-lookup"><span data-stu-id="1422f-119">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
