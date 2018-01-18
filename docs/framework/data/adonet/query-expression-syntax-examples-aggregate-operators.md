---
title: "Примеры синтаксиса выражений запроса. Операторы статистических выражений (LINQ to DataSet)"
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
ms.assetid: 85dafa07-e102-46e7-ab78-37bf06f257a6
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: b8ed6d3d2ca99a185620af3e34f3ee860fd6fd12
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="query-expression-syntax-examples-aggregate-operators-linq-to-dataset"></a><span data-ttu-id="cfb69-102">Примеры синтаксиса выражений запроса. Операторы статистических выражений (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="cfb69-102">Query Expression Syntax Examples: Aggregate Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="cfb69-103">Примеры в данном разделе демонстрируют, как применять методы <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A> и <xref:System.Linq.Enumerable.Sum%2A> для запроса к объекту <xref:System.Data.DataSet> и статистической обработки данных с использованием синтаксиса выражений запросов.</span><span class="sxs-lookup"><span data-stu-id="cfb69-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query a <xref:System.Data.DataSet> and aggregate data using query expression syntax.</span></span>  
  
 <span data-ttu-id="cfb69-104">`FillDataSet` Используется в этих примерах метод определен в [загрузка данных в наборе данных](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="cfb69-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="cfb69-105">В примерах данного раздела используются таблицы Contact, Address, Product, SalesOrderHeader и SalesOrderDetail из образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="cfb69-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="cfb69-106">В примерах в этом разделе используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="cfb69-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="cfb69-107">Дополнительные сведения см. в разделе [как: создайте LINQ to DataSet проекта в Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="cfb69-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="average"></a><span data-ttu-id="cfb69-108">Метод Average</span><span class="sxs-lookup"><span data-stu-id="cfb69-108">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="cfb69-109">Пример</span><span class="sxs-lookup"><span data-stu-id="cfb69-109">Example</span></span>  
 <span data-ttu-id="cfb69-110">В этом примере используется метод <xref:System.Linq.Enumerable.Average%2A> для поиска среднесписочной цены продуктов каждого стиля.</span><span class="sxs-lookup"><span data-stu-id="cfb69-110">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="cfb69-111">Пример</span><span class="sxs-lookup"><span data-stu-id="cfb69-111">Example</span></span>  
 <span data-ttu-id="cfb69-112">В этом примере метод <xref:System.Linq.Enumerable.Average%2A> используется для получения средней суммы заказа по каждому идентификатору контактного лица.</span><span class="sxs-lookup"><span data-stu-id="cfb69-112">This example uses <xref:System.Linq.Enumerable.Average%2A> to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="cfb69-113">Пример</span><span class="sxs-lookup"><span data-stu-id="cfb69-113">Example</span></span>  
 <span data-ttu-id="cfb69-114">В этом примере метод <xref:System.Linq.Enumerable.Average%2A> используется для получения заказов со средним значением `TotalDue` для каждого контакта.</span><span class="sxs-lookup"><span data-stu-id="cfb69-114">This example uses <xref:System.Linq.Enumerable.Average%2A> to get the orders with the average `TotalDue` for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="cfb69-115">Количество</span><span class="sxs-lookup"><span data-stu-id="cfb69-115">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="cfb69-116">Пример</span><span class="sxs-lookup"><span data-stu-id="cfb69-116">Example</span></span>  
 <span data-ttu-id="cfb69-117">В этом примере метод <xref:System.Linq.Enumerable.Count%2A> используется для возвращения списка идентификаторов контактного лица и количества заказов для каждого контактного лица.</span><span class="sxs-lookup"><span data-stu-id="cfb69-117">This example uses <xref:System.Linq.Enumerable.Count%2A> to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countnested)]
 [!code-vb[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="cfb69-118">Пример</span><span class="sxs-lookup"><span data-stu-id="cfb69-118">Example</span></span>  
 <span data-ttu-id="cfb69-119">В этом примере продукты группируются по цветам и метод <xref:System.Linq.Enumerable.Count%2A> используется для возвращения количества продуктов в каждой цветовой группе.</span><span class="sxs-lookup"><span data-stu-id="cfb69-119">This example groups products by color and uses <xref:System.Linq.Enumerable.Count%2A> to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="max"></a><span data-ttu-id="cfb69-120">Максимум</span><span class="sxs-lookup"><span data-stu-id="cfb69-120">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="cfb69-121">Пример</span><span class="sxs-lookup"><span data-stu-id="cfb69-121">Example</span></span>  
 <span data-ttu-id="cfb69-122">В этом примере используется метод <xref:System.Linq.Enumerable.Max%2A> для получения наибольшей общей выплаты для каждого идентификатора контакта.</span><span class="sxs-lookup"><span data-stu-id="cfb69-122">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="cfb69-123">Пример</span><span class="sxs-lookup"><span data-stu-id="cfb69-123">Example</span></span>  
 <span data-ttu-id="cfb69-124">В этом примере используется метод <xref:System.Linq.Enumerable.Max%2A> для получения заказов с наибольшим значением `TotalDue` для каждого идентификатора контакта.</span><span class="sxs-lookup"><span data-stu-id="cfb69-124">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest `TotalDue` for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="cfb69-125">Минимум</span><span class="sxs-lookup"><span data-stu-id="cfb69-125">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="cfb69-126">Пример</span><span class="sxs-lookup"><span data-stu-id="cfb69-126">Example</span></span>  
 <span data-ttu-id="cfb69-127">В этом примере используется метод <xref:System.Linq.Enumerable.Min%2A> для получения наименьшей общей выплаты для каждого идентификатора контакта.</span><span class="sxs-lookup"><span data-stu-id="cfb69-127">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="cfb69-128">Пример</span><span class="sxs-lookup"><span data-stu-id="cfb69-128">Example</span></span>  
 <span data-ttu-id="cfb69-129">В этом примере используется метод <xref:System.Linq.Enumerable.Min%2A> для получения заказов с наименьшей общей выплатой для каждого контакта.</span><span class="sxs-lookup"><span data-stu-id="cfb69-129">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="cfb69-130">Sum</span><span class="sxs-lookup"><span data-stu-id="cfb69-130">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="cfb69-131">Пример</span><span class="sxs-lookup"><span data-stu-id="cfb69-131">Example</span></span>  
 <span data-ttu-id="cfb69-132">В этом примере используется метод <xref:System.Linq.Enumerable.Sum%2A> для получения общей выплаты по каждому идентификатору контакта.</span><span class="sxs-lookup"><span data-stu-id="cfb69-132">This example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="cfb69-133">См. также</span><span class="sxs-lookup"><span data-stu-id="cfb69-133">See Also</span></span>  
 [<span data-ttu-id="cfb69-134">Загрузка данных в DataSet</span><span class="sxs-lookup"><span data-stu-id="cfb69-134">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="cfb69-135">Примеры LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="cfb69-135">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="cfb69-136">Общие сведения о стандартных операторах запроса</span><span class="sxs-lookup"><span data-stu-id="cfb69-136">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
