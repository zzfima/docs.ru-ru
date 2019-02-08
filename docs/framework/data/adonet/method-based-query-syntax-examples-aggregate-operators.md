---
title: Примеры синтаксиса запросов на основе методов. Операторы агрегатной обработки (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5ed5f01d-acb2-4dd4-be60-f04c2d570fa8
ms.openlocfilehash: 88f7e71c3008818a657bc54ae6459e75359ab3f3
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2019
ms.locfileid: "55903596"
---
# <a name="method-based-query-syntax-examples-aggregate-operators-linq-to-dataset"></a><span data-ttu-id="d2441-102">Примеры синтаксиса запросов на основе методов. Операторы агрегатной обработки (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="d2441-102">Method-Based Query Syntax Examples: Aggregate Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="d2441-103">В примерах данного раздела показано, как применять операторы <xref:System.Linq.Enumerable.Aggregate%2A>, <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.LongCount%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A> и <xref:System.Linq.Enumerable.Sum%2A> для запросов к объекту <xref:System.Data.DataSet> и статистической обработки данных с использованием синтаксиса запросов на основе методов.</span><span class="sxs-lookup"><span data-stu-id="d2441-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Aggregate%2A>, <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.LongCount%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> operators to query a <xref:System.Data.DataSet> and aggregate data using method query syntax.</span></span>  
  
 <span data-ttu-id="d2441-104">`FillDataSet` Метод, используемый в этих примерах указывается в [загрузка данных в DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="d2441-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="d2441-105">В примерах данного раздела используются таблицы Contact, Address, Product, SalesOrderHeader и SalesOrderDetail из образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="d2441-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="d2441-106">В примерах в этом разделе используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="d2441-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="d2441-107">Дополнительные сведения см. в разделе [Как Создание проектов LINQ to DataSet в Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="d2441-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="aggregate"></a><span data-ttu-id="d2441-108">Aggregate</span><span class="sxs-lookup"><span data-stu-id="d2441-108">Aggregate</span></span>  
  
### <a name="example"></a><span data-ttu-id="d2441-109">Пример</span><span class="sxs-lookup"><span data-stu-id="d2441-109">Example</span></span>  
 <span data-ttu-id="d2441-110">В этом примере метод <xref:System.Linq.Enumerable.Aggregate%2A> используется для получения первых 5 контактов из таблицы `Contact` и построения списка фамилий, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="d2441-110">This example uses the <xref:System.Linq.Enumerable.Aggregate%2A> method to get the first 5 contacts from the `Contact` table and build a comma-delimited list of the last names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Aggregate_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#aggregate_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Aggregate_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#aggregate_mq)]  
  
## <a name="average"></a><span data-ttu-id="d2441-111">Метод Average</span><span class="sxs-lookup"><span data-stu-id="d2441-111">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="d2441-112">Пример</span><span class="sxs-lookup"><span data-stu-id="d2441-112">Example</span></span>  
 <span data-ttu-id="d2441-113">В этом примере метод <xref:System.Linq.Enumerable.Average%2A> используется для поиска средней цены продуктов по прейскуранту.</span><span class="sxs-lookup"><span data-stu-id="d2441-113">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Average_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#average_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Average_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#average_mq)]  
  
### <a name="example"></a><span data-ttu-id="d2441-114">Пример</span><span class="sxs-lookup"><span data-stu-id="d2441-114">Example</span></span>  
 <span data-ttu-id="d2441-115">В этом примере используется метод <xref:System.Linq.Enumerable.Average%2A> для поиска среднесписочной цены продуктов каждого стиля.</span><span class="sxs-lookup"><span data-stu-id="d2441-115">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="d2441-116">Пример</span><span class="sxs-lookup"><span data-stu-id="d2441-116">Example</span></span>  
 <span data-ttu-id="d2441-117">В этом примере метод <xref:System.Linq.Enumerable.Average%2A> используется для поиска средней суммы заказа.</span><span class="sxs-lookup"><span data-stu-id="d2441-117">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average total due.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averageprojection_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageProjection_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averageprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="d2441-118">Пример</span><span class="sxs-lookup"><span data-stu-id="d2441-118">Example</span></span>  
 <span data-ttu-id="d2441-119">В этом примере метод <xref:System.Linq.Enumerable.Average%2A> используется для получения средней суммы заказа по каждому идентификатору контактного лица.</span><span class="sxs-lookup"><span data-stu-id="d2441-119">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="d2441-120">Пример</span><span class="sxs-lookup"><span data-stu-id="d2441-120">Example</span></span>  
 <span data-ttu-id="d2441-121">В этом примере метод <xref:System.Linq.Enumerable.Average%2A> используется для получения заказов со средним значением `TotalDue` для каждого контакта.</span><span class="sxs-lookup"><span data-stu-id="d2441-121">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the orders with the average `TotalDue` for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="d2441-122">Количество</span><span class="sxs-lookup"><span data-stu-id="d2441-122">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="d2441-123">Пример</span><span class="sxs-lookup"><span data-stu-id="d2441-123">Example</span></span>  
 <span data-ttu-id="d2441-124">В этом примере метод <xref:System.Linq.Enumerable.Count%2A> используется для возврата количества продуктов в таблице `Product`.</span><span class="sxs-lookup"><span data-stu-id="d2441-124">This example uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in the `Product` table.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Count](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#count)]
 [!code-vb[DP LINQ to DataSet Examples#Count](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#count)]  
  
### <a name="example"></a><span data-ttu-id="d2441-125">Пример</span><span class="sxs-lookup"><span data-stu-id="d2441-125">Example</span></span>  
 <span data-ttu-id="d2441-126">В этом примере метод <xref:System.Linq.Enumerable.Count%2A> используется для возврата списка идентификаторов контактных лиц и количества заказов для каждого контактного лица.</span><span class="sxs-lookup"><span data-stu-id="d2441-126">This example uses the <xref:System.Linq.Enumerable.Count%2A> method to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countnested)]
 [!code-vb[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="d2441-127">Пример</span><span class="sxs-lookup"><span data-stu-id="d2441-127">Example</span></span>  
 <span data-ttu-id="d2441-128">В этом примере продукты группируются по цветам, а метод <xref:System.Linq.Enumerable.Count%2A> используется для возврата количества продуктов в каждой цветовой группе.</span><span class="sxs-lookup"><span data-stu-id="d2441-128">This example groups products by color and uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="longcount"></a><span data-ttu-id="d2441-129">LongCount</span><span class="sxs-lookup"><span data-stu-id="d2441-129">LongCount</span></span>  
  
### <a name="example"></a><span data-ttu-id="d2441-130">Пример</span><span class="sxs-lookup"><span data-stu-id="d2441-130">Example</span></span>  
 <span data-ttu-id="d2441-131">В этом примере количество контактов возвращается в виде данных типа long integer.</span><span class="sxs-lookup"><span data-stu-id="d2441-131">This example gets the contact count as a long integer.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#LongCountSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#longcountsimple)]
 [!code-vb[DP LINQ to DataSet Examples#LongCountSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#longcountsimple)]  
  
## <a name="max"></a><span data-ttu-id="d2441-132">Максимум</span><span class="sxs-lookup"><span data-stu-id="d2441-132">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="d2441-133">Пример</span><span class="sxs-lookup"><span data-stu-id="d2441-133">Example</span></span>  
 <span data-ttu-id="d2441-134">В этом примере метод <xref:System.Linq.Enumerable.Max%2A> используется для поиска наибольшей суммы заказа.</span><span class="sxs-lookup"><span data-stu-id="d2441-134">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxprojection_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxProjection_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="d2441-135">Пример</span><span class="sxs-lookup"><span data-stu-id="d2441-135">Example</span></span>  
 <span data-ttu-id="d2441-136">В этом примере используется метод <xref:System.Linq.Enumerable.Max%2A> для получения наибольшей общей выплаты для каждого идентификатора контакта.</span><span class="sxs-lookup"><span data-stu-id="d2441-136">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="d2441-137">Пример</span><span class="sxs-lookup"><span data-stu-id="d2441-137">Example</span></span>  
 <span data-ttu-id="d2441-138">В этом примере используется метод <xref:System.Linq.Enumerable.Max%2A> для получения заказов с наибольшим значением `TotalDue` для каждого идентификатора контакта.</span><span class="sxs-lookup"><span data-stu-id="d2441-138">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest `TotalDue` for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="d2441-139">Минимум</span><span class="sxs-lookup"><span data-stu-id="d2441-139">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="d2441-140">Пример</span><span class="sxs-lookup"><span data-stu-id="d2441-140">Example</span></span>  
 <span data-ttu-id="d2441-141">В этом примере метод <xref:System.Linq.Enumerable.Min%2A> используется для поиска наименьшей суммы заказа.</span><span class="sxs-lookup"><span data-stu-id="d2441-141">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#minprojection_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinProjection_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#minprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="d2441-142">Пример</span><span class="sxs-lookup"><span data-stu-id="d2441-142">Example</span></span>  
 <span data-ttu-id="d2441-143">В этом примере используется метод <xref:System.Linq.Enumerable.Min%2A> для получения наименьшей общей выплаты для каждого идентификатора контакта.</span><span class="sxs-lookup"><span data-stu-id="d2441-143">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="d2441-144">Пример</span><span class="sxs-lookup"><span data-stu-id="d2441-144">Example</span></span>  
 <span data-ttu-id="d2441-145">В этом примере используется метод <xref:System.Linq.Enumerable.Min%2A> для получения заказов с наименьшей общей выплатой для каждого контакта.</span><span class="sxs-lookup"><span data-stu-id="d2441-145">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="d2441-146">Sum</span><span class="sxs-lookup"><span data-stu-id="d2441-146">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="d2441-147">Пример</span><span class="sxs-lookup"><span data-stu-id="d2441-147">Example</span></span>  
 <span data-ttu-id="d2441-148">В этом примере метод <xref:System.Linq.Enumerable.Sum%2A> используется для возврата общего количества заказанных продуктов в таблице `SalesOrderDetail`.</span><span class="sxs-lookup"><span data-stu-id="d2441-148">This example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total number of order quantities in the `SalesOrderDetail` table.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SumProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#sumprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="d2441-149">Пример</span><span class="sxs-lookup"><span data-stu-id="d2441-149">Example</span></span>  
 <span data-ttu-id="d2441-150">В этом примере используется метод <xref:System.Linq.Enumerable.Sum%2A> для получения общей выплаты по каждому идентификатору контакта.</span><span class="sxs-lookup"><span data-stu-id="d2441-150">This example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="d2441-151">См. также</span><span class="sxs-lookup"><span data-stu-id="d2441-151">See also</span></span>
- [<span data-ttu-id="d2441-152">Загрузка данных в DataSet</span><span class="sxs-lookup"><span data-stu-id="d2441-152">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [<span data-ttu-id="d2441-153">Примеры LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="d2441-153">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [<span data-ttu-id="d2441-154">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="d2441-154">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="d2441-155">Общие сведения о стандартных операторах запроса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d2441-155">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
