---
title: Примеры синтаксиса выражений запроса. Операторы соединения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 343e8dda-70b2-409d-9334-ce9a880c3cea
ms.openlocfilehash: 4db511d74c4cce82bfd010f77cb1580dbb704b41
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43501902"
---
# <a name="query-expression-syntax-examples-join-operators"></a><span data-ttu-id="6b21e-102">Примеры синтаксиса выражений запроса. Операторы соединения</span><span class="sxs-lookup"><span data-stu-id="6b21e-102">Query Expression Syntax Examples: Join Operators</span></span>
<span data-ttu-id="6b21e-103">Соединение - важная операция в запросах, которые обращаются к источникам данных без доступных для навигации взаимосвязей, например к таблицам реляционной базы данных.</span><span class="sxs-lookup"><span data-stu-id="6b21e-103">Joining is an important operation in queries that target data sources that have no navigable relationships to each other, such as relational database tables.</span></span> <span data-ttu-id="6b21e-104">Соединение двух источников данных представляет собой взаимосвязь объектов одного источника данных с объектами, использующими общий атрибут в другом источнике данных.</span><span class="sxs-lookup"><span data-stu-id="6b21e-104">A join of two data sources is the association of objects in one data source with objects that share a common attribute in the other data source.</span></span> <span data-ttu-id="6b21e-105">Дополнительные сведения см. в разделе [Общие сведения о стандартных операторах запроса](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span><span class="sxs-lookup"><span data-stu-id="6b21e-105">For more information, see [Standard Query Operators Overview](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span></span>  
  
 <span data-ttu-id="6b21e-106">Примеры в этом разделе демонстрируют, как использовать <xref:System.Linq.Enumerable.GroupJoin%2A> и <xref:System.Linq.Enumerable.Join%2A> методы запроса [модели AdventureWorks Sales](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) с использованием синтаксиса выражений запроса.</span><span class="sxs-lookup"><span data-stu-id="6b21e-106">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.GroupJoin%2A> and <xref:System.Linq.Enumerable.Join%2A> methods to query the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using query expression syntax.</span></span> <span data-ttu-id="6b21e-107">Модель AdventureWorks Sales, которая используется в этих примерах, состоит из таблиц Contact, Address, Product, SalesOrderHeader и SalesOrderDetail образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="6b21e-107">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="6b21e-108">В примерах в этом разделе используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="6b21e-108">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="groupjoin"></a><span data-ttu-id="6b21e-109">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="6b21e-109">GroupJoin</span></span>  
  
### <a name="example"></a><span data-ttu-id="6b21e-110">Пример</span><span class="sxs-lookup"><span data-stu-id="6b21e-110">Example</span></span>  
 <span data-ttu-id="6b21e-111">В следующем примере выполняется соединение <xref:System.Linq.Enumerable.GroupJoin%2A> таблиц SalesOrderHeader и SalesOrderDetail, чтобы найти количество заказов для каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="6b21e-111">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the SalesOrderHeader and SalesOrderDetail tables to find the number of orders per customer.</span></span> <span data-ttu-id="6b21e-112">Групповое соединение эквивалентно левому внешнему соединению, которое возвращает каждый элемент первого (левого) источника данных, даже если в другом источнике данных не имеется соответствующих элементов.</span><span class="sxs-lookup"><span data-stu-id="6b21e-112">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin2)]
 [!code-vb[DP L2E Examples#GroupJoin2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin2)]  
  
### <a name="example"></a><span data-ttu-id="6b21e-113">Пример</span><span class="sxs-lookup"><span data-stu-id="6b21e-113">Example</span></span>  
 <span data-ttu-id="6b21e-114">В следующем примере выполняется соединение <xref:System.Linq.Enumerable.GroupJoin%2A> таблиц Contact и SalesOrderHeader, чтобы найти количество заказов на каждый контакт.</span><span class="sxs-lookup"><span data-stu-id="6b21e-114">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the Contact and SalesOrderHeader tables to find the number of orders per contact.</span></span> <span data-ttu-id="6b21e-115">Для каждого контакта отображается число заказов и идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="6b21e-115">The order count and IDs for each contact are displayed.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin)]
 [!code-vb[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin)]  
  
### <a name="example"></a><span data-ttu-id="6b21e-116">Пример</span><span class="sxs-lookup"><span data-stu-id="6b21e-116">Example</span></span>  
 <span data-ttu-id="6b21e-117">В следующем примере выполняется соединение <xref:System.Linq.Enumerable.GroupJoin%2A> таблиц Contact и SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="6b21e-117">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the Contact and SalesOrderHeader tables.</span></span> <span data-ttu-id="6b21e-118">Групповое соединение эквивалентно левому внешнему соединению, которое возвращает каждый элемент первого (левого) источника данных, даже если в другом источнике данных не имеется соответствующих элементов.</span><span class="sxs-lookup"><span data-stu-id="6b21e-118">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin)]
 [!code-vb[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin)]  
  
## <a name="join"></a><span data-ttu-id="6b21e-119">Join</span><span class="sxs-lookup"><span data-stu-id="6b21e-119">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="6b21e-120">Пример</span><span class="sxs-lookup"><span data-stu-id="6b21e-120">Example</span></span>  
 <span data-ttu-id="6b21e-121">В следующем примере выполняется соединение таблиц SalesOrderHeader и SalesOrderDetail для определения количества заказов через Интернет за август.</span><span class="sxs-lookup"><span data-stu-id="6b21e-121">The following example performs a join over the SalesOrderHeader and SalesOrderDetail tables to get online orders from the month of August.</span></span>  
  
 [!code-csharp[DP L2E Examples#Join](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#join)]
 [!code-vb[DP L2E Examples#Join](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a><span data-ttu-id="6b21e-122">См. также</span><span class="sxs-lookup"><span data-stu-id="6b21e-122">See Also</span></span>  
 [<span data-ttu-id="6b21e-123">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="6b21e-123">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
