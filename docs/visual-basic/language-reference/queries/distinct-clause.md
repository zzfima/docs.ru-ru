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
ms.openlocfilehash: e8d3e38261a04c4d29faab351d24d6710413b09a
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004790"
---
# <a name="distinct-clause-visual-basic"></a><span data-ttu-id="5647d-102">Предложение Distinct (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5647d-102">Distinct Clause (Visual Basic)</span></span>
<span data-ttu-id="5647d-103">Ограничивают значения текущей переменной диапазона, чтобы исключить дублирующиеся значения в последующих предложениях запроса.</span><span class="sxs-lookup"><span data-stu-id="5647d-103">Restricts the values of the current range variable to eliminate duplicate values in subsequent query clauses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5647d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5647d-104">Syntax</span></span>  
  
```vb  
Distinct  
```  
  
## <a name="remarks"></a><span data-ttu-id="5647d-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="5647d-105">Remarks</span></span>  
 <span data-ttu-id="5647d-106">Чтобы получить список уникальных элементов, можно использовать предложение `Distinct`.</span><span class="sxs-lookup"><span data-stu-id="5647d-106">You can use the `Distinct` clause to return a list of unique items.</span></span> <span data-ttu-id="5647d-107">Предложение `Distinct` приводит к тому, что запрос пропускает дублирующиеся результаты запроса.</span><span class="sxs-lookup"><span data-stu-id="5647d-107">The `Distinct` clause causes the query to ignore duplicate query results.</span></span> <span data-ttu-id="5647d-108">Предложение `Distinct` применяется к повторяющимися значениям для всех полей возврата, указанных в предложении `Select`.</span><span class="sxs-lookup"><span data-stu-id="5647d-108">The `Distinct` clause applies to duplicate values for all return fields specified by the `Select` clause.</span></span> <span data-ttu-id="5647d-109">Если не указано предложение `Select`, предложение `Distinct` применяется к переменной диапазона для запроса, указанного в предложении `From`.</span><span class="sxs-lookup"><span data-stu-id="5647d-109">If no `Select` clause is specified, the `Distinct` clause is applied to the range variable for the query identified in the `From` clause.</span></span> <span data-ttu-id="5647d-110">Если переменная диапазона не является неизменяемым типом, запрос будет игнорировать только результат запроса, если все элементы типа соответствуют существующему результату запроса.</span><span class="sxs-lookup"><span data-stu-id="5647d-110">If the range variable is not an immutable type, the query will only ignore a query result if all members of the type match an existing query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5647d-111">Пример</span><span class="sxs-lookup"><span data-stu-id="5647d-111">Example</span></span>  
 <span data-ttu-id="5647d-112">Следующее выражение запроса соединяет список клиентов и список заказов клиентов.</span><span class="sxs-lookup"><span data-stu-id="5647d-112">The following query expression joins a list of customers and a list of customer orders.</span></span> <span data-ttu-id="5647d-113">Предложение `Distinct` включено для возврата списка уникальных имен клиентов и дат заказов.</span><span class="sxs-lookup"><span data-stu-id="5647d-113">The `Distinct` clause is included to return a list of unique customer names and order dates.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a><span data-ttu-id="5647d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="5647d-114">See also</span></span>

- <span data-ttu-id="5647d-115">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5647d-115">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="5647d-116">Запросы</span><span class="sxs-lookup"><span data-stu-id="5647d-116">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="5647d-117">Предложение From</span><span class="sxs-lookup"><span data-stu-id="5647d-117">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="5647d-118">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="5647d-118">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="5647d-119">Предложения Where</span><span class="sxs-lookup"><span data-stu-id="5647d-119">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
