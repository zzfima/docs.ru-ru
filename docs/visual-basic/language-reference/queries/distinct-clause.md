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
ms.openlocfilehash: fbca9fa8aa227d8d5b6488bef179f4bda08bb38c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58830062"
---
# <a name="distinct-clause-visual-basic"></a><span data-ttu-id="8d326-102">Предложение Distinct (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8d326-102">Distinct Clause (Visual Basic)</span></span>
<span data-ttu-id="8d326-103">Ограничивает значения текущей переменной диапазона, чтобы исключить повторяющиеся значения в предложениях последующих запросов.</span><span class="sxs-lookup"><span data-stu-id="8d326-103">Restricts the values of the current range variable to eliminate duplicate values in subsequent query clauses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d326-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d326-104">Syntax</span></span>  
  
```  
Distinct  
```  
  
## <a name="remarks"></a><span data-ttu-id="8d326-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="8d326-105">Remarks</span></span>  
 <span data-ttu-id="8d326-106">Можно использовать `Distinct` предложение, чтобы получить список уникальных элементов.</span><span class="sxs-lookup"><span data-stu-id="8d326-106">You can use the `Distinct` clause to return a list of unique items.</span></span> <span data-ttu-id="8d326-107">`Distinct` Предложение вызывает игнорировать повторяющиеся результаты запроса.</span><span class="sxs-lookup"><span data-stu-id="8d326-107">The `Distinct` clause causes the query to ignore duplicate query results.</span></span> <span data-ttu-id="8d326-108">`Distinct` Предложение применяется к повторяющимся значениям для все возвращаемые поля, заданные параметром `Select` предложение.</span><span class="sxs-lookup"><span data-stu-id="8d326-108">The `Distinct` clause applies to duplicate values for all return fields specified by the `Select` clause.</span></span> <span data-ttu-id="8d326-109">Если не `Select` указано предложение, `Distinct` предложение применяется к переменной диапазона для запроса, указанного в `From` предложение.</span><span class="sxs-lookup"><span data-stu-id="8d326-109">If no `Select` clause is specified, the `Distinct` clause is applied to the range variable for the query identified in the `From` clause.</span></span> <span data-ttu-id="8d326-110">Если переменной диапазона не является неизменяемым типом, запрос только игнорирует результат запроса, если все члены типа соответствуют существующим результатам запроса.</span><span class="sxs-lookup"><span data-stu-id="8d326-110">If the range variable is not an immutable type, the query will only ignore a query result if all members of the type match an existing query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d326-111">Пример</span><span class="sxs-lookup"><span data-stu-id="8d326-111">Example</span></span>  
 <span data-ttu-id="8d326-112">Следующее выражение запроса объединяет список клиентов и список заказов клиентов.</span><span class="sxs-lookup"><span data-stu-id="8d326-112">The following query expression joins a list of customers and a list of customer orders.</span></span> <span data-ttu-id="8d326-113">`Distinct` Предложение включена, чтобы получить список уникальных имен клиентов и порядок даты.</span><span class="sxs-lookup"><span data-stu-id="8d326-113">The `Distinct` clause is included to return a list of unique customer names and order dates.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a><span data-ttu-id="8d326-114">См. также</span><span class="sxs-lookup"><span data-stu-id="8d326-114">See also</span></span>

- <span data-ttu-id="8d326-115">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8d326-115">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="8d326-116">Запросы</span><span class="sxs-lookup"><span data-stu-id="8d326-116">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="8d326-117">Предложение From</span><span class="sxs-lookup"><span data-stu-id="8d326-117">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="8d326-118">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="8d326-118">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="8d326-119">Предложения Where</span><span class="sxs-lookup"><span data-stu-id="8d326-119">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
