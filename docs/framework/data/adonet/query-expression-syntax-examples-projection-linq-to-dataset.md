---
title: Примеры синтаксиса выражений запроса. Проекция (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 48c9f5ed-76bf-4228-ab10-5217bbb295a3
ms.openlocfilehash: d84396a15f8122df38bd10781ab7351bdbf685eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33359511"
---
# <a name="query-expression-syntax-examples-projection--linq-to-dataset"></a><span data-ttu-id="e5a87-102">Примеры синтаксиса выражений запроса. Проекция (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="e5a87-102">Query Expression Syntax Examples: Projection  (LINQ to DataSet)</span></span>
<span data-ttu-id="e5a87-103">Примеры в данном разделе демонстрируют, как использовать методы <xref:System.Linq.Enumerable.Select%2A> и <xref:System.Linq.Enumerable.SelectMany%2A> для запроса к <xref:System.Data.DataSet> с использованием синтаксиса выражений запросов.</span><span class="sxs-lookup"><span data-stu-id="e5a87-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Select%2A> and <xref:System.Linq.Enumerable.SelectMany%2A> methods to query a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="e5a87-104">`FillDataSet` Используется в этих примерах метод определен в [загрузка данных в наборе данных](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="e5a87-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="e5a87-105">В примерах данного раздела используются таблицы Contact, Address, Product, SalesOrderHeader и SalesOrderDetail из образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="e5a87-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="e5a87-106">В примерах в этом разделе используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="e5a87-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="e5a87-107">Дополнительные сведения см. в разделе [как: создайте LINQ to DataSet проекта в Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="e5a87-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="select"></a><span data-ttu-id="e5a87-108">Выбрать</span><span class="sxs-lookup"><span data-stu-id="e5a87-108">Select</span></span>  
  
### <a name="example"></a><span data-ttu-id="e5a87-109">Пример</span><span class="sxs-lookup"><span data-stu-id="e5a87-109">Example</span></span>  
 <span data-ttu-id="e5a87-110">В этом примере метод <xref:System.Linq.Enumerable.Select%2A> используется, чтобы вернуть все строки из таблицы `Product` и отобразить названия продуктов.</span><span class="sxs-lookup"><span data-stu-id="e5a87-110">This example uses the <xref:System.Linq.Enumerable.Select%2A> method to return all the rows from the `Product` table and display the product names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectSimple1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectsimple1)]
 [!code-vb[DP LINQ to DataSet Examples#SelectSimple1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectsimple1)]  
  
### <a name="example"></a><span data-ttu-id="e5a87-111">Пример</span><span class="sxs-lookup"><span data-stu-id="e5a87-111">Example</span></span>  
 <span data-ttu-id="e5a87-112">В этом примере метод <xref:System.Linq.Enumerable.Select%2A> используется для возврата последовательности, состоящей только из названий продуктов.</span><span class="sxs-lookup"><span data-stu-id="e5a87-112">This example uses <xref:System.Linq.Enumerable.Select%2A> to return a sequence of only product names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectSimple2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectsimple2)]
 [!code-vb[DP LINQ to DataSet Examples#SelectSimple2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectsimple2)]  
  
## <a name="selectmany"></a><span data-ttu-id="e5a87-113">SelectMany</span><span class="sxs-lookup"><span data-stu-id="e5a87-113">SelectMany</span></span>  
  
### <a name="example"></a><span data-ttu-id="e5a87-114">Пример</span><span class="sxs-lookup"><span data-stu-id="e5a87-114">Example</span></span>  
 <span data-ttu-id="e5a87-115">В этом примере инструкция `From …, …` (эквивалент метода <xref:System.Linq.Enumerable.SelectMany%2A>) используется для выбора всех заказов, в которых `TotalDue` составляет менее 500,00.</span><span class="sxs-lookup"><span data-stu-id="e5a87-115">This example uses `From …, …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where `TotalDue` is less than 500.00.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyCompoundFrom](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanycompoundfrom)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyCompoundFrom](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanycompoundfrom)]  
  
### <a name="example"></a><span data-ttu-id="e5a87-116">Пример</span><span class="sxs-lookup"><span data-stu-id="e5a87-116">Example</span></span>  
 <span data-ttu-id="e5a87-117">В этом примере инструкция `From …, …` (эквивалент метода <xref:System.Linq.Enumerable.SelectMany%2A>) используется для выбора всех заказов, сделанных 1 октября 2002 года или позднее.</span><span class="sxs-lookup"><span data-stu-id="e5a87-117">This example uses `From …, …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where the order was made on October 1, 2002 or later.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyCompoundFrom2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanycompoundfrom2)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyCompoundFrom2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanycompoundfrom2)]  
  
### <a name="example"></a><span data-ttu-id="e5a87-118">Пример</span><span class="sxs-lookup"><span data-stu-id="e5a87-118">Example</span></span>  
 <span data-ttu-id="e5a87-119">В этом примере инструкция `From …, …` (эквивалент метода <xref:System.Linq.Enumerable.SelectMany%2A>) используется для выбора всех заказов, в которых общий объем продаж составляет более 10 000,00, а ключевое слово `From` применяется, чтобы исключить повторный запрос общего объема.</span><span class="sxs-lookup"><span data-stu-id="e5a87-119">This example uses a `From …, …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where the order total is greater than 10000.00 and uses `From` assignment to avoid requesting the total twice.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyFromAssignment](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanyfromassignment)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyFromAssignment](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanyfromassignment)]  
  
## <a name="see-also"></a><span data-ttu-id="e5a87-120">См. также</span><span class="sxs-lookup"><span data-stu-id="e5a87-120">See Also</span></span>  
 [<span data-ttu-id="e5a87-121">Загрузка данных в DataSet</span><span class="sxs-lookup"><span data-stu-id="e5a87-121">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="e5a87-122">Примеры LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="e5a87-122">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="e5a87-123">Общие сведения о стандартных операторах запроса</span><span class="sxs-lookup"><span data-stu-id="e5a87-123">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
