---
title: Примеры синтаксиса запросов на основе методов. Упорядочение
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5d21b178-d731-471a-8534-1f8184a2ef06
ms.openlocfilehash: e213046955c2c4e720c56adb96da29078ea3c48d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59226863"
---
# <a name="method-based-query-syntax-examples-ordering"></a><span data-ttu-id="b6c9c-102">Примеры синтаксиса запросов на основе методов. Упорядочение</span><span class="sxs-lookup"><span data-stu-id="b6c9c-102">Method-Based Query Syntax Examples: Ordering</span></span>
<span data-ttu-id="b6c9c-103">Примеры в этом разделе демонстрируют, как использовать <xref:System.Linq.Enumerable.ThenBy%2A> метод для запроса [модели AdventureWorks Sales](https://archive.codeplex.com/?p=msftdbprodsamples) с использованием синтаксиса запросов на основе методов.</span><span class="sxs-lookup"><span data-stu-id="b6c9c-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ThenBy%2A> method to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using method-based query syntax.</span></span> <span data-ttu-id="b6c9c-104">Модель AdventureWorks Sales, которая используется в этих примерах, состоит из таблиц Contact, Address, Product, SalesOrderHeader и SalesOrderDetail образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="b6c9c-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="b6c9c-105">В примерах в этом разделе используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="b6c9c-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="thenby"></a><span data-ttu-id="b6c9c-106">ThenBy</span><span class="sxs-lookup"><span data-stu-id="b6c9c-106">ThenBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="b6c9c-107">Пример</span><span class="sxs-lookup"><span data-stu-id="b6c9c-107">Example</span></span>  
 <span data-ttu-id="b6c9c-108">В следующем примере, в синтаксисе запросов на основе методов, используются методы <xref:System.Linq.Queryable.OrderBy%2A> и <xref:System.Linq.Queryable.ThenBy%2A>, чтобы вернуть список контактов, отсортированный сначала по фамилии, а затем по имени.</span><span class="sxs-lookup"><span data-stu-id="b6c9c-108">The following example in method-based query syntax uses <xref:System.Linq.Queryable.OrderBy%2A> and <xref:System.Linq.Queryable.ThenBy%2A> to return a list of contacts ordered by last name and then by first name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderByThenBy_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbythenby_mq)]
 [!code-vb[DP L2E Examples#OrderByThenBy_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbythenby_mq)]  
  
## <a name="thenbydescending"></a><span data-ttu-id="b6c9c-109">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="b6c9c-109">ThenByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="b6c9c-110">Пример</span><span class="sxs-lookup"><span data-stu-id="b6c9c-110">Example</span></span>  
 <span data-ttu-id="b6c9c-111">В следующем примере используются методы <xref:System.Linq.Queryable.OrderBy%2A> и <xref:System.Linq.Queryable.ThenByDescending%2A>, чтобы вначале выполнить сортировку по стоимости, а затем сортировку по убыванию по названию продуктов.</span><span class="sxs-lookup"><span data-stu-id="b6c9c-111">The following example uses the <xref:System.Linq.Queryable.OrderBy%2A> and <xref:System.Linq.Queryable.ThenByDescending%2A> methods to first sort by list price, and then perform a descending sort of the product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#ThenByDescending_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#thenbydescending_mq)]
 [!code-vb[DP L2E Examples#ThenByDescending_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#thenbydescending_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="b6c9c-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b6c9c-112">See also</span></span>

- [<span data-ttu-id="b6c9c-113">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="b6c9c-113">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
