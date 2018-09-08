---
title: Примеры синтаксиса выражений запроса. Упорядочение (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 653a4a97-1e4a-4b2d-8d24-7dbe1f2a5c84
ms.openlocfilehash: 1e3ee4372c1c2173cff0d93dfdf84c96c60130d4
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44186452"
---
# <a name="query-expression-syntax-examples-ordering-linq-to-dataset"></a><span data-ttu-id="7d34d-102">Примеры синтаксиса выражений запроса. Упорядочение (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="7d34d-102">Query Expression Syntax Examples: Ordering (LINQ to DataSet)</span></span>
<span data-ttu-id="7d34d-103">В примерах данного раздела показано, как использовать методы <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A> и <xref:System.Linq.Enumerable.ThenByDescending%2A> для запросов к объекту <xref:System.Data.DataSet> и сортировки результатов с использованием синтаксиса выражений запросов.</span><span class="sxs-lookup"><span data-stu-id="7d34d-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A>, and <xref:System.Linq.Enumerable.ThenByDescending%2A> methods to query a <xref:System.Data.DataSet> and order the results using the query expression syntax.</span></span>  
  
 <span data-ttu-id="7d34d-104">`FillDataSet` Метод, используемый в этих примерах указывается в [загрузка данных в DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="7d34d-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="7d34d-105">В примерах данного раздела используются таблицы Contact, Address, Product, SalesOrderHeader и SalesOrderDetail из образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="7d34d-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="7d34d-106">В примерах в этом разделе используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="7d34d-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="7d34d-107">Дополнительные сведения см. в разделе [как: Создание LINQ to DataSet проекта в Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="7d34d-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="orderby"></a><span data-ttu-id="7d34d-108">OrderBy</span><span class="sxs-lookup"><span data-stu-id="7d34d-108">OrderBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="7d34d-109">Пример</span><span class="sxs-lookup"><span data-stu-id="7d34d-109">Example</span></span>  
 <span data-ttu-id="7d34d-110">В этом примере метод <xref:System.Linq.Enumerable.OrderBy%2A> используется для возврата списка контактов, упорядоченных по фамилии.</span><span class="sxs-lookup"><span data-stu-id="7d34d-110">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> to return a list of contacts ordered by last name.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderBySimple1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbysimple1)]
 [!code-vb[DP LINQ to DataSet Examples#OrderBySimple1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbysimple1)]  
  
### <a name="example"></a><span data-ttu-id="7d34d-111">Пример</span><span class="sxs-lookup"><span data-stu-id="7d34d-111">Example</span></span>  
 <span data-ttu-id="7d34d-112">В этом примере метод <xref:System.Linq.Enumerable.OrderBy%2A> используется для сортировки списка контактов по длине фамилии.</span><span class="sxs-lookup"><span data-stu-id="7d34d-112">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> to sort a list of contacts by length of last name.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderBySimple2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbysimple2)]
 [!code-vb[DP LINQ to DataSet Examples#OrderBySimple2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbysimple2)]  
  
## <a name="orderbydescending"></a><span data-ttu-id="7d34d-113">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="7d34d-113">OrderByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="7d34d-114">Пример</span><span class="sxs-lookup"><span data-stu-id="7d34d-114">Example</span></span>  
 <span data-ttu-id="7d34d-115">В этом примере выражение `orderby… descending` (`Order By … Descending`), эквивалентное методу <xref:System.Linq.Enumerable.OrderByDescending%2A>, используется для сортировки прейскуранта по убыванию.</span><span class="sxs-lookup"><span data-stu-id="7d34d-115">This example uses `orderby… descending` (`Order By … Descending`), which is equivalent to the <xref:System.Linq.Enumerable.OrderByDescending%2A> method, to sort the price list from highest to lowest.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderByDescendingSimple1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbydescendingsimple1)]
 [!code-vb[DP LINQ to DataSet Examples#OrderByDescendingSimple1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbydescendingsimple1)]  
  
## <a name="reverse"></a><span data-ttu-id="7d34d-116">Reverse</span><span class="sxs-lookup"><span data-stu-id="7d34d-116">Reverse</span></span>  
  
### <a name="example"></a><span data-ttu-id="7d34d-117">Пример</span><span class="sxs-lookup"><span data-stu-id="7d34d-117">Example</span></span>  
 <span data-ttu-id="7d34d-118">В этом примере метод <xref:System.Linq.Enumerable.Reverse%2A> используется для создания списка заказов, в которых `OrderDate` предшествует 20 февраля 2002 г.</span><span class="sxs-lookup"><span data-stu-id="7d34d-118">This example uses <xref:System.Linq.Enumerable.Reverse%2A> to create a list of orders where `OrderDate` is earlier than Feb 20, 2002.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#reverse)]
 [!code-vb[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#reverse)]  
  
## <a name="thenbydescending"></a><span data-ttu-id="7d34d-119">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="7d34d-119">ThenByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="7d34d-120">Пример</span><span class="sxs-lookup"><span data-stu-id="7d34d-120">Example</span></span>  
 <span data-ttu-id="7d34d-121">В этом примере выражение `OrderBy… Descending`, эквивалентное методу <xref:System.Linq.Enumerable.ThenByDescending%2A>, используется для сортировки списка продуктов сначала по названию, а затем по прейскуранту по убыванию.</span><span class="sxs-lookup"><span data-stu-id="7d34d-121">This example uses `OrderBy… Descending` , which is equivalent to the <xref:System.Linq.Enumerable.ThenByDescending%2A> method, to sort a list of products, first by name and then by list price, from highest to lowest.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ThenByDescendingSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#thenbydescendingsimple)]
 [!code-vb[DP LINQ to DataSet Examples#ThenByDescendingSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#thenbydescendingsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="7d34d-122">См. также</span><span class="sxs-lookup"><span data-stu-id="7d34d-122">See Also</span></span>  
 [<span data-ttu-id="7d34d-123">Загрузка данных в DataSet</span><span class="sxs-lookup"><span data-stu-id="7d34d-123">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="7d34d-124">Примеры LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="7d34d-124">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="7d34d-125">Общие сведения о стандартных операторах запроса</span><span class="sxs-lookup"><span data-stu-id="7d34d-125">Standard Query Operators Overview</span></span>](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
