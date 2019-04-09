---
title: Примеры синтаксиса запросов на основе методов. Операторы соединения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d00f0efa-9084-4c17-843f-54904fcb4204
ms.openlocfilehash: 700c29222d10177774e118e53fb51f177b723679
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176908"
---
# <a name="method-based-query-syntax-examples-join-operators"></a><span data-ttu-id="196fa-102">Примеры синтаксиса запросов на основе методов. Операторы соединения</span><span class="sxs-lookup"><span data-stu-id="196fa-102">Method-Based Query Syntax Examples: Join Operators</span></span>
<span data-ttu-id="196fa-103">Примеры в этом разделе демонстрируют, как использовать <xref:System.Linq.Enumerable.Join%2A> и <xref:System.Linq.Enumerable.GroupJoin%2A> методы запроса [модели AdventureWorks Sales](https://archive.codeplex.com/?p=msftdbprodsamples) с использованием синтаксиса запросов на основе методов.</span><span class="sxs-lookup"><span data-stu-id="196fa-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A> methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using method-based query syntax.</span></span> <span data-ttu-id="196fa-104">Модель AdventureWorks Sales, которая используется в этих примерах, состоит из таблиц Contact, Address, Product, SalesOrderHeader и SalesOrderDetail образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="196fa-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="196fa-105">В примерах в этом разделе используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="196fa-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="groupjoin"></a><span data-ttu-id="196fa-106">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="196fa-106">GroupJoin</span></span>  
  
### <a name="example"></a><span data-ttu-id="196fa-107">Пример</span><span class="sxs-lookup"><span data-stu-id="196fa-107">Example</span></span>  
 <span data-ttu-id="196fa-108">В следующем примере выполняется соединение <xref:System.Linq.Enumerable.GroupJoin%2A> таблиц SalesOrderHeader и SalesOrderDetail, чтобы найти количество заказов для каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="196fa-108">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the SalesOrderHeader and SalesOrderDetail tables to find the number of orders per customer.</span></span> <span data-ttu-id="196fa-109">Групповое соединение эквивалентно левому внешнему соединению, которое возвращает каждый элемент первого (левого) источника данных, даже если в другом источнике данных не имеется соответствующих элементов.</span><span class="sxs-lookup"><span data-stu-id="196fa-109">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin2_mq)]
 [!code-vb[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin2_mq)]  
  
### <a name="example"></a><span data-ttu-id="196fa-110">Пример</span><span class="sxs-lookup"><span data-stu-id="196fa-110">Example</span></span>  
 <span data-ttu-id="196fa-111">В следующем примере выполняется соединение <xref:System.Linq.Enumerable.GroupJoin%2A> таблиц Contact и SalesOrderHeader, чтобы найти количество заказов на каждый контакт.</span><span class="sxs-lookup"><span data-stu-id="196fa-111">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the Contact and SalesOrderHeader tables to find the number of orders per contact.</span></span> <span data-ttu-id="196fa-112">Для каждого контакта отображается число заказов и идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="196fa-112">The order count and IDs for each contact are displayed.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin_mq)]
 [!code-vb[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin_mq)]  
  
## <a name="join"></a><span data-ttu-id="196fa-113">Join</span><span class="sxs-lookup"><span data-stu-id="196fa-113">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="196fa-114">Пример</span><span class="sxs-lookup"><span data-stu-id="196fa-114">Example</span></span>  
 <span data-ttu-id="196fa-115">В следующем примере выполняется соединение с таблицами Contact и SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="196fa-115">The following example performs a join over the Contact and SalesOrderHeader tables.</span></span>  
  
 [!code-csharp[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinsimple_mq)]
 [!code-vb[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinsimple_mq)]  
  
### <a name="example"></a><span data-ttu-id="196fa-116">Пример</span><span class="sxs-lookup"><span data-stu-id="196fa-116">Example</span></span>  
 <span data-ttu-id="196fa-117">В следующем примере выполняется соединение с таблицами Contact и SalesOrderHeader с группированием результатов по идентификатору контактного лица.</span><span class="sxs-lookup"><span data-stu-id="196fa-117">The following example performs a join over the Contact and SalesOrderHeader tables, grouping the results by contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinwithgroupedresults_mq)]
 [!code-vb[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinwithgroupedresults_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="196fa-118">См. также</span><span class="sxs-lookup"><span data-stu-id="196fa-118">See also</span></span>

- [<span data-ttu-id="196fa-119">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="196fa-119">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
