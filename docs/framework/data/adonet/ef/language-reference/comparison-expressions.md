---
title: Выражения сравнения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec7637a9-01d5-4a95-8bb0-478311cd263b
ms.openlocfilehash: cca909e67464d08c0bb4ff8a0d0186d9d600ce18
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596349"
---
# <a name="comparison-expressions"></a><span data-ttu-id="e3ed9-102">Выражения сравнения</span><span class="sxs-lookup"><span data-stu-id="e3ed9-102">Comparison Expressions</span></span>
<span data-ttu-id="e3ed9-103">Выражение сравнения проверяет, является ли значение константы, свойства или результата метода равным другому значению, не равным ему, большим или меньшим его.</span><span class="sxs-lookup"><span data-stu-id="e3ed9-103">A comparison expression checks whether a constant value, property value, or method result is equal, not equal, greater than, or less than another value.</span></span> <span data-ttu-id="e3ed9-104">Если данное сравнение недопустимо в языке [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)], будет выдано исключение.</span><span class="sxs-lookup"><span data-stu-id="e3ed9-104">If a particular comparison is not valid for [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)], an exception will be thrown.</span></span> <span data-ttu-id="e3ed9-105">Все сравнения, как явные, так и неявные, требуют сравнимости всех компонентов в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="e3ed9-105">All comparisons, both implicit and explicit, require that all components are comparable in the data source.</span></span> <span data-ttu-id="e3ed9-106">Выражения сравнения часто используются в предложениях `Where` для ограничения результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="e3ed9-106">Comparison expressions are frequently used in `Where` clauses for restricting the query results.</span></span>  
  
 <span data-ttu-id="e3ed9-107">Следующий пример с синтаксисом выражений запроса представляет собой запрос, возвращающий данные заказа, номер которого равен SO43663.</span><span class="sxs-lookup"><span data-stu-id="e3ed9-107">The following example in query expression syntax shows a query that returns results where the sales order number is equal to "SO43663":</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#RestrictionExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#restrictionexpression)]
 [!code-vb[DP L2E Conceptual Examples#RestrictionExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#restrictionexpression)]  
  
 <span data-ttu-id="e3ed9-108">Следующий пример с синтаксисом запроса на основе методов представляет собой запрос, возвращающий данные заказа с номером SO43663.</span><span class="sxs-lookup"><span data-stu-id="e3ed9-108">The following example in method-based query syntax shows a query that returns results where the sales order number is equal to "SO43663":</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#RestrictionExpression_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#restrictionexpression_mq)]
 [!code-vb[DP L2E Conceptual Examples#RestrictionExpression_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#restrictionexpression_mq)]  
  
 <span data-ttu-id="e3ed9-109">Следующий пример с синтаксисом выражений запроса представляет собой запрос, возвращающий данные заказов, отправленных 8 июля 2001 года.</span><span class="sxs-lookup"><span data-stu-id="e3ed9-109">The following example in query expression syntax shows a query that returns sales order information where the ship date is equal to July 8, 2001:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#DateTimeComparison](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#datetimecomparison)]
 [!code-vb[DP L2E Conceptual Examples#DateTimeComparison](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#datetimecomparison)]  
  
 <span data-ttu-id="e3ed9-110">Следующий пример с синтаксисом запроса на основе методов представляет собой запрос, возвращающий данные заказов, отправленных 8 июля 2001 года.</span><span class="sxs-lookup"><span data-stu-id="e3ed9-110">The following example in method-based query syntax shows a query that returns sales order information where the ship date is equal to July 8, 2001:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#DateTimeComparison_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#datetimecomparison_mq)]
 [!code-vb[DP L2E Conceptual Examples#DateTimeComparison_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#datetimecomparison_mq)]  
  
 <span data-ttu-id="e3ed9-111">Выражения, результатом которых является константа, преобразуются на сервере. Попытка вычислить их локально не производится.</span><span class="sxs-lookup"><span data-stu-id="e3ed9-111">Expressions that yield a constant are converted at the server, and no attempt to do local evaluation is performed.</span></span> <span data-ttu-id="e3ed9-112">В следующем примере в предложении `Where` используется выражение, возвращающее константу.</span><span class="sxs-lookup"><span data-stu-id="e3ed9-112">The following example uses an expression in the `Where` clause that yields a constant.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constantexpression)]
 [!code-vb[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constantexpression)]  
  
 <span data-ttu-id="e3ed9-113">Технология [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] не поддерживает использование пользовательского класса в качестве константы.</span><span class="sxs-lookup"><span data-stu-id="e3ed9-113">[!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] does not support using a user class as a constant.</span></span> <span data-ttu-id="e3ed9-114">Однако ссылка на свойство пользовательского класса считается константой; она будет преобразована в константное выражение дерева команд и выполнена в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="e3ed9-114">However, a property reference on a user class is considered a constant, and will be converted to a command tree constant expression and executed on the data source.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#MyClass](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#myclass)]
 [!code-vb[DP L2E Conceptual Examples#MyClass](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#myclass)]  
  
 [!code-csharp[DP L2E Conceptual Examples#PropertyAsConstant](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#propertyasconstant)]
 [!code-vb[DP L2E Conceptual Examples#PropertyAsConstant](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#propertyasconstant)]  
  
 <span data-ttu-id="e3ed9-115">Методы, возвращающие постоянное выражение, не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="e3ed9-115">Methods that return a constant expression are not supported.</span></span> <span data-ttu-id="e3ed9-116">В следующем примере в предложении `Where` используется метод, возвращающий константу.</span><span class="sxs-lookup"><span data-stu-id="e3ed9-116">The following example contains a method in the `Where` clause that returns a constant.</span></span> <span data-ttu-id="e3ed9-117">Во время выполнения этого примера будет выдано исключение.</span><span class="sxs-lookup"><span data-stu-id="e3ed9-117">This example will throw an exception at run time.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#MethodAsConstantFails](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#methodasconstantfails)]
 [!code-vb[DP L2E Conceptual Examples#MethodAsConstantFails](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#methodasconstantfails)]  
  
## <a name="see-also"></a><span data-ttu-id="e3ed9-118">См. также</span><span class="sxs-lookup"><span data-stu-id="e3ed9-118">See also</span></span>
- [<span data-ttu-id="e3ed9-119">Выражения в запросах LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="e3ed9-119">Expressions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)
