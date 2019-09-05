---
title: Примеры синтаксиса выражений запросов. Операторы соединения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 343e8dda-70b2-409d-9334-ce9a880c3cea
ms.openlocfilehash: e80c50daeb0de7f4a8477786f28441d1495033ea
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249485"
---
# <a name="query-expression-syntax-examples-join-operators"></a><span data-ttu-id="6c28c-102">Примеры синтаксиса выражений запросов. Операторы соединения</span><span class="sxs-lookup"><span data-stu-id="6c28c-102">Query Expression Syntax Examples: Join Operators</span></span>
<span data-ttu-id="6c28c-103">Соединение - важная операция в запросах, которые обращаются к источникам данных без доступных для навигации взаимосвязей, например к таблицам реляционной базы данных.</span><span class="sxs-lookup"><span data-stu-id="6c28c-103">Joining is an important operation in queries that target data sources that have no navigable relationships to each other, such as relational database tables.</span></span> <span data-ttu-id="6c28c-104">Соединение двух источников данных представляет собой взаимосвязь объектов одного источника данных с объектами, использующими общий атрибут в другом источнике данных.</span><span class="sxs-lookup"><span data-stu-id="6c28c-104">A join of two data sources is the association of objects in one data source with objects that share a common attribute in the other data source.</span></span> <span data-ttu-id="6c28c-105">Дополнительные сведения см. в разделе [Общие сведения о стандартных операторах запросов](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb397896(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="6c28c-105">For more information, see [Standard Query Operators Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb397896(v=vs.120)).</span></span>  
  
 <span data-ttu-id="6c28c-106">В примерах этого раздела показано, как использовать <xref:System.Linq.Enumerable.GroupJoin%2A> методы и <xref:System.Linq.Enumerable.Join%2A> для запроса [модели AdventureWorks Sales](https://archive.codeplex.com/?p=msftdbprodsamples) с помощью синтаксиса выражения запроса.</span><span class="sxs-lookup"><span data-stu-id="6c28c-106">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.GroupJoin%2A> and <xref:System.Linq.Enumerable.Join%2A> methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using query expression syntax.</span></span> <span data-ttu-id="6c28c-107">Модель AdventureWorks Sales, которая используется в этих примерах, состоит из таблиц Contact, Address, Product, SalesOrderHeader и SalesOrderDetail образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="6c28c-107">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="6c28c-108">В примерах этого раздела используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="6c28c-108">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="groupjoin"></a><span data-ttu-id="6c28c-109">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="6c28c-109">GroupJoin</span></span>  
  
### <a name="example"></a><span data-ttu-id="6c28c-110">Пример</span><span class="sxs-lookup"><span data-stu-id="6c28c-110">Example</span></span>  
 <span data-ttu-id="6c28c-111">В следующем примере выполняется соединение <xref:System.Linq.Enumerable.GroupJoin%2A> таблиц SalesOrderHeader и SalesOrderDetail, чтобы найти количество заказов для каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="6c28c-111">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the SalesOrderHeader and SalesOrderDetail tables to find the number of orders per customer.</span></span> <span data-ttu-id="6c28c-112">Групповое соединение эквивалентно левому внешнему соединению, которое возвращает каждый элемент первого (левого) источника данных, даже если в другом источнике данных не имеется соответствующих элементов.</span><span class="sxs-lookup"><span data-stu-id="6c28c-112">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin2)]
 [!code-vb[DP L2E Examples#GroupJoin2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin2)]  
  
### <a name="example"></a><span data-ttu-id="6c28c-113">Пример</span><span class="sxs-lookup"><span data-stu-id="6c28c-113">Example</span></span>  
 <span data-ttu-id="6c28c-114">В следующем примере выполняется соединение <xref:System.Linq.Enumerable.GroupJoin%2A> таблиц Contact и SalesOrderHeader, чтобы найти количество заказов на каждый контакт.</span><span class="sxs-lookup"><span data-stu-id="6c28c-114">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the Contact and SalesOrderHeader tables to find the number of orders per contact.</span></span> <span data-ttu-id="6c28c-115">Для каждого контакта отображается число заказов и идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="6c28c-115">The order count and IDs for each contact are displayed.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin)]
 [!code-vb[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin)]  
  
## <a name="join"></a><span data-ttu-id="6c28c-116">Join</span><span class="sxs-lookup"><span data-stu-id="6c28c-116">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="6c28c-117">Пример</span><span class="sxs-lookup"><span data-stu-id="6c28c-117">Example</span></span>  
 <span data-ttu-id="6c28c-118">В следующем примере выполняется соединение таблиц SalesOrderHeader и SalesOrderDetail для определения количества заказов через Интернет за август.</span><span class="sxs-lookup"><span data-stu-id="6c28c-118">The following example performs a join over the SalesOrderHeader and SalesOrderDetail tables to get online orders from the month of August.</span></span>  
  
 [!code-csharp[DP L2E Examples#Join](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#join)]
 [!code-vb[DP L2E Examples#Join](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a><span data-ttu-id="6c28c-119">См. также</span><span class="sxs-lookup"><span data-stu-id="6c28c-119">See also</span></span>

- [<span data-ttu-id="6c28c-120">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="6c28c-120">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
