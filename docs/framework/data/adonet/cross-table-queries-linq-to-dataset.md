---
title: "Запросы между таблицами (LINQ to DataSet)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 6819a16f-8656-41af-a54d-dfec0cb66366
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 059dd39f3583c3b8fcf6736e514b9cc4870d3ad6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="cross-table-queries-linq-to-dataset"></a><span data-ttu-id="a41a9-102">Запросы между таблицами (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="a41a9-102">Cross-Table Queries (LINQ to DataSet)</span></span>
<span data-ttu-id="a41a9-103">Кроме запросов к отдельной таблице, [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] позволяет выполнять межтабличные запросы.</span><span class="sxs-lookup"><span data-stu-id="a41a9-103">In addition to querying a single table, you can also perform cross-table queries in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="a41a9-104">Это делается с помощью *соединения*.</span><span class="sxs-lookup"><span data-stu-id="a41a9-104">This is done by using a *join*.</span></span> <span data-ttu-id="a41a9-105">Соединение представляет собой взаимосвязь объектов одного источника данных с объектами, использующими общий атрибут в другом источнике данных, такие как продукт или идентификатору контактного лица.</span><span class="sxs-lookup"><span data-stu-id="a41a9-105">A join is the association of objects in one data source with objects that share a common attribute in another data source, such as a product or contact ID.</span></span> <span data-ttu-id="a41a9-106">В объектно ориентированное программирование связей между объектами являются относительно легко переход, поскольку каждый объект имеет элемент, который ссылается на другой объект.</span><span class="sxs-lookup"><span data-stu-id="a41a9-106">In object-oriented programming, relationships between objects are relatively easy to navigate because each object has a member that references another object.</span></span> <span data-ttu-id="a41a9-107">Однако в таблицах внешних баз данных перемещение по связям не столь однозначно.</span><span class="sxs-lookup"><span data-stu-id="a41a9-107">In external database tables, however, navigating relationships is not as straightforward.</span></span> <span data-ttu-id="a41a9-108">Таблицы баз данных не содержат встроенных связей.</span><span class="sxs-lookup"><span data-stu-id="a41a9-108">Database tables do not contain built-in relationships.</span></span> <span data-ttu-id="a41a9-109">В таких случаях для соединения элементов из разных источников может использоваться операция объединения.</span><span class="sxs-lookup"><span data-stu-id="a41a9-109">In these cases, the join operation can be used to match elements from each source.</span></span> <span data-ttu-id="a41a9-110">Например, если две таблицы содержат данные о продуктах и о продажах, нужно использовать операцию соединения для сопоставления данных о продажах и о продуктах, относящихся к одному и тому же заказу на продажу.</span><span class="sxs-lookup"><span data-stu-id="a41a9-110">For example, given two tables that contain product information and sales information, you could use a join operation to match sales information and products for the same sales order.</span></span>  
  
 <span data-ttu-id="a41a9-111">[!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] Framework предоставляет два операторы соединения <xref:System.Linq.Enumerable.Join%2A> и <xref:System.Linq.Enumerable.GroupJoin%2A>.</span><span class="sxs-lookup"><span data-stu-id="a41a9-111">The [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] framework provides two join operators, <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A>.</span></span> <span data-ttu-id="a41a9-112">Эти операторы выполняют *эквивалентные соединения*: т. е соединения, сопоставляющие два данных источников, только если равны их ключей.</span><span class="sxs-lookup"><span data-stu-id="a41a9-112">These operators perform *equi-joins*: that is, joins that match two data sources only when their keys are equal.</span></span> <span data-ttu-id="a41a9-113">(В отличие от этого, [!INCLUDE[tsql](../../../../includes/tsql-md.md)] поддерживает операторы соединения, отличные от `equals`, например оператор `less than`.)</span><span class="sxs-lookup"><span data-stu-id="a41a9-113">(By contrast, [!INCLUDE[tsql](../../../../includes/tsql-md.md)] supports join operators other than `equals`, such as the `less than` operator.)</span></span>  
  
 <span data-ttu-id="a41a9-114">В терминах реляционной базы данных оператор <xref:System.Linq.Enumerable.Join%2A> выполняет внутреннее соединение.</span><span class="sxs-lookup"><span data-stu-id="a41a9-114">In relational database terms, <xref:System.Linq.Enumerable.Join%2A> implements an inner join.</span></span> <span data-ttu-id="a41a9-115">Внутреннее соединение представляет собой соединение, при котором возвращаются только объекты, имеющие соответствия в другом наборе данных.</span><span class="sxs-lookup"><span data-stu-id="a41a9-115">An inner join is a type of join in which only those objects that have a match in the opposite data set are returned.</span></span>  
  
 <span data-ttu-id="a41a9-116"><xref:System.Linq.Enumerable.GroupJoin%2A> Операторы не имеющих прямого эквивалента в терминах реляционных баз данных; они реализуют надмножество внутренних соединений и левых внешних соединений.</span><span class="sxs-lookup"><span data-stu-id="a41a9-116">The <xref:System.Linq.Enumerable.GroupJoin%2A> operators have no direct equivalent in relational database terms; they implement a superset of inner joins and left outer joins.</span></span> <span data-ttu-id="a41a9-117">Левое внешнее соединение является соединением, которое возвращает каждый элемент первого (левого) коллекции, даже если он не имеет соответствующих элементов второй коллекции.</span><span class="sxs-lookup"><span data-stu-id="a41a9-117">A left outer join is a join that returns each element of the first (left) collection, even if it has no correlated elements in the second collection.</span></span>  
  
 <span data-ttu-id="a41a9-118">Дополнительные сведения о соединениях см. в разделе [операции присоединения](http://msdn.microsoft.com/library/442d176d-028c-4beb-8d22-407d4ef89107).</span><span class="sxs-lookup"><span data-stu-id="a41a9-118">For more information about joins, see [Join Operations](http://msdn.microsoft.com/library/442d176d-028c-4beb-8d22-407d4ef89107).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a41a9-119">Пример</span><span class="sxs-lookup"><span data-stu-id="a41a9-119">Example</span></span>  
 <span data-ttu-id="a41a9-120">В следующем примере выполняется традиционное соединение таблиц `SalesOrderHeader` и `SalesOrderDetail` из образца базы данных AdventureWorks для получения заказов, сделанных через Интернет начиная с августа.</span><span class="sxs-lookup"><span data-stu-id="a41a9-120">The following example performs a traditional join of the `SalesOrderHeader` and `SalesOrderDetail` tables from the AdventureWorks sample database to obtain online orders from the month of August.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#join)]
 [!code-vb[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a><span data-ttu-id="a41a9-121">См. также</span><span class="sxs-lookup"><span data-stu-id="a41a9-121">See Also</span></span>  
 [<span data-ttu-id="a41a9-122">Запросы к DataSet</span><span class="sxs-lookup"><span data-stu-id="a41a9-122">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 [<span data-ttu-id="a41a9-123">Запросы к одной таблице</span><span class="sxs-lookup"><span data-stu-id="a41a9-123">Single-Table Queries</span></span>](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)  
 [<span data-ttu-id="a41a9-124">Запрос к типизированным объектам DataSet</span><span class="sxs-lookup"><span data-stu-id="a41a9-124">Querying Typed DataSets</span></span>](../../../../docs/framework/data/adonet/querying-typed-datasets.md)  
 [<span data-ttu-id="a41a9-125">Операции соединения</span><span class="sxs-lookup"><span data-stu-id="a41a9-125">Join Operations</span></span>](http://msdn.microsoft.com/library/442d176d-028c-4beb-8d22-407d4ef89107)  
 [<span data-ttu-id="a41a9-126">Примеры LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="a41a9-126">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
