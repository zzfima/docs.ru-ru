---
title: Примеры синтаксиса выражений запроса. Операторы соединения (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f4d86667-3392-470d-a076-5ca6cbb660f6
ms.openlocfilehash: d5415cb18d716e3122ee6f40a399cc212e934cc4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33357680"
---
# <a name="query-expression-syntax-examples-join-operators-linq-to-dataset"></a><span data-ttu-id="a31cb-102">Примеры синтаксиса выражений запроса. Операторы соединения (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="a31cb-102">Query Expression Syntax Examples: Join Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="a31cb-103">Соединение - важная операция в запросах, которые обращаются к источникам данных без доступных для навигации взаимосвязей, например к таблицам реляционной базы данных.</span><span class="sxs-lookup"><span data-stu-id="a31cb-103">Joining is an important operation in queries that target data sources that have no navigable relationships to each other, such as relational database tables.</span></span> <span data-ttu-id="a31cb-104">Соединение двух источников данных представляет собой взаимосвязь объектов одного источника данных с объектами, использующими общий атрибут в другом источнике данных.</span><span class="sxs-lookup"><span data-stu-id="a31cb-104">A join of two data sources is the association of objects in one data source with objects that share a common attribute in the other data source.</span></span> <span data-ttu-id="a31cb-105">Дополнительные сведения см. в разделе [Общие сведения о стандартных операторах запроса](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span><span class="sxs-lookup"><span data-stu-id="a31cb-105">For more information, see [Standard Query Operators Overview](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span></span>  
  
 <span data-ttu-id="a31cb-106">Примеры в данном разделе демонстрируют, как использовать методы <xref:System.Linq.Enumerable.GroupJoin%2A> и <xref:System.Linq.Enumerable.Join%2A> для запроса к <xref:System.Data.DataSet> с использованием синтаксиса выражений запросов.</span><span class="sxs-lookup"><span data-stu-id="a31cb-106">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.GroupJoin%2A> and <xref:System.Linq.Enumerable.Join%2A> methods to query a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="a31cb-107">`FillDataSet` Используется в этих примерах метод определен в [загрузка данных в наборе данных](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="a31cb-107">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="a31cb-108">В примерах данного раздела используются таблицы Contact, Address, Product, SalesOrderHeader и SalesOrderDetail из образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="a31cb-108">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="a31cb-109">В примерах в этом разделе используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="a31cb-109">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="a31cb-110">Дополнительные сведения см. в разделе [как: создайте LINQ to DataSet проекта в Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="a31cb-110">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="groupjoin"></a><span data-ttu-id="a31cb-111">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="a31cb-111">GroupJoin</span></span>  
  
### <a name="example"></a><span data-ttu-id="a31cb-112">Пример</span><span class="sxs-lookup"><span data-stu-id="a31cb-112">Example</span></span>  
 <span data-ttu-id="a31cb-113">В этом примере выполняется операция <xref:System.Linq.Enumerable.GroupJoin%2A> с таблицами `SalesOrderHeader` и `SalesOrderDetail`, чтобы найти количество заказов для каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="a31cb-113">This example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the `SalesOrderHeader` and `SalesOrderDetail` tables to find the number of orders per customer.</span></span> <span data-ttu-id="a31cb-114">Групповое соединение эквивалентно левому внешнему соединению, которое возвращает каждый элемент первого (левого) источника данных, даже если в другом источнике данных не имеется соответствующих элементов.</span><span class="sxs-lookup"><span data-stu-id="a31cb-114">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#GroupJoin2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#groupjoin2)]
 [!code-vb[DP LINQ to DataSet Examples#GroupJoin2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#groupjoin2)]  
  
### <a name="example"></a><span data-ttu-id="a31cb-115">Пример</span><span class="sxs-lookup"><span data-stu-id="a31cb-115">Example</span></span>  
 <span data-ttu-id="a31cb-116">В этом примере выполняется операция <xref:System.Linq.Enumerable.GroupJoin%2A> с таблицами `Contact` и `SalesOrderHeader`.</span><span class="sxs-lookup"><span data-stu-id="a31cb-116">This example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the `Contact` and `SalesOrderHeader` tables.</span></span> <span data-ttu-id="a31cb-117">Групповое соединение эквивалентно левому внешнему соединению, которое возвращает каждый элемент первого (левого) источника данных, даже если в другом источнике данных не имеется соответствующих элементов.</span><span class="sxs-lookup"><span data-stu-id="a31cb-117">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#GroupJoin](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#groupjoin)]
 [!code-vb[DP LINQ to DataSet Examples#GroupJoin](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#groupjoin)]  
  
## <a name="join"></a><span data-ttu-id="a31cb-118">Join</span><span class="sxs-lookup"><span data-stu-id="a31cb-118">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="a31cb-119">Пример</span><span class="sxs-lookup"><span data-stu-id="a31cb-119">Example</span></span>  
 <span data-ttu-id="a31cb-120">В этом примере выполняется соединение таблиц `SalesOrderHeader` и `SalesOrderDetail`, чтобы получить заказы, действующие с августа.</span><span class="sxs-lookup"><span data-stu-id="a31cb-120">This example performs a join over the `SalesOrderHeader` and `SalesOrderDetail` tables to get online orders from the month of August.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#join)]
 [!code-vb[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a><span data-ttu-id="a31cb-121">См. также</span><span class="sxs-lookup"><span data-stu-id="a31cb-121">See Also</span></span>  
 [<span data-ttu-id="a31cb-122">Загрузка данных в DataSet</span><span class="sxs-lookup"><span data-stu-id="a31cb-122">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="a31cb-123">Примеры LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="a31cb-123">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="a31cb-124">Общие сведения о стандартных операторах запроса</span><span class="sxs-lookup"><span data-stu-id="a31cb-124">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
