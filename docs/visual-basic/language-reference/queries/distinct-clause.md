---
title: Предложение Distinct
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: 94471898807ef4552564c3e01465f2b2f6211d0c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74335377"
---
# <a name="distinct-clause-visual-basic"></a><span data-ttu-id="b60fb-102">Предложение Distinct (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b60fb-102">Distinct Clause (Visual Basic)</span></span>
<span data-ttu-id="b60fb-103">Ограничивают значения текущей переменной диапазона, чтобы исключить дублирующиеся значения в последующих предложениях запроса.</span><span class="sxs-lookup"><span data-stu-id="b60fb-103">Restricts the values of the current range variable to eliminate duplicate values in subsequent query clauses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b60fb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b60fb-104">Syntax</span></span>  
  
```vb  
Distinct  
```  
  
## <a name="remarks"></a><span data-ttu-id="b60fb-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="b60fb-105">Remarks</span></span>  
 <span data-ttu-id="b60fb-106">Для получения списка уникальных элементов можно использовать предложение `Distinct`.</span><span class="sxs-lookup"><span data-stu-id="b60fb-106">You can use the `Distinct` clause to return a list of unique items.</span></span> <span data-ttu-id="b60fb-107">Предложение `Distinct` приводит к тому, что запрос пропускает дублирующиеся результаты запроса.</span><span class="sxs-lookup"><span data-stu-id="b60fb-107">The `Distinct` clause causes the query to ignore duplicate query results.</span></span> <span data-ttu-id="b60fb-108">Предложение `Distinct` применяется к повторяющимися значениям для всех полей возврата, указанных в предложении `Select`.</span><span class="sxs-lookup"><span data-stu-id="b60fb-108">The `Distinct` clause applies to duplicate values for all return fields specified by the `Select` clause.</span></span> <span data-ttu-id="b60fb-109">Если предложение `Select` не указано, предложение `Distinct` применяется к переменной диапазона для запроса, указанного в предложении `From`.</span><span class="sxs-lookup"><span data-stu-id="b60fb-109">If no `Select` clause is specified, the `Distinct` clause is applied to the range variable for the query identified in the `From` clause.</span></span> <span data-ttu-id="b60fb-110">Если переменная диапазона не является неизменяемым типом, запрос будет игнорировать только результат запроса, если все элементы типа соответствуют существующему результату запроса.</span><span class="sxs-lookup"><span data-stu-id="b60fb-110">If the range variable is not an immutable type, the query will only ignore a query result if all members of the type match an existing query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b60fb-111">Пример</span><span class="sxs-lookup"><span data-stu-id="b60fb-111">Example</span></span>  
 <span data-ttu-id="b60fb-112">Следующее выражение запроса соединяет список клиентов и список заказов клиентов.</span><span class="sxs-lookup"><span data-stu-id="b60fb-112">The following query expression joins a list of customers and a list of customer orders.</span></span> <span data-ttu-id="b60fb-113">Предложение `Distinct` включается для возврата списка уникальных имен клиентов и дат заказов.</span><span class="sxs-lookup"><span data-stu-id="b60fb-113">The `Distinct` clause is included to return a list of unique customer names and order dates.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a><span data-ttu-id="b60fb-114">См. также</span><span class="sxs-lookup"><span data-stu-id="b60fb-114">See also</span></span>

- <span data-ttu-id="b60fb-115">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b60fb-115">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="b60fb-116">Запросы</span><span class="sxs-lookup"><span data-stu-id="b60fb-116">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="b60fb-117">Предложение From</span><span class="sxs-lookup"><span data-stu-id="b60fb-117">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="b60fb-118">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="b60fb-118">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="b60fb-119">Предложения Where</span><span class="sxs-lookup"><span data-stu-id="b60fb-119">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
