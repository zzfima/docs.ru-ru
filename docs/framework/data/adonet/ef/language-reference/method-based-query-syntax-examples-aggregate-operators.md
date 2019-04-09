---
title: Примеры синтаксиса запросов на основе методов. Статистические операторы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0e306067-5720-4782-9719-2286570a7e47
ms.openlocfilehash: 06609ce14edeb7e9306816b8a8d58d2212b61751
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207777"
---
# <a name="method-based-query-syntax-examples-aggregate-operators"></a><span data-ttu-id="47186-102">Примеры синтаксиса запросов на основе методов. Статистические операторы</span><span class="sxs-lookup"><span data-stu-id="47186-102">Method-Based Query Syntax Examples: Aggregate Operators</span></span>
<span data-ttu-id="47186-103">Примеры в этом разделе демонстрируют, как использовать <xref:System.Linq.Enumerable.Aggregate%2A>, <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.LongCount%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, и <xref:System.Linq.Enumerable.Sum%2A> методы запроса [модели AdventureWorks Sales](https://archive.codeplex.com/?p=msftdbprodsamples) с использованием синтаксиса запросов на основе методов.</span><span class="sxs-lookup"><span data-stu-id="47186-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Aggregate%2A>, <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.LongCount%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using method-based query syntax.</span></span> <span data-ttu-id="47186-104">Модель AdventureWorks Sales, которая используется в этих примерах, состоит из таблиц Contact, Address, Product, SalesOrderHeader и SalesOrderDetail образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="47186-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="47186-105">В примерах в этом разделе используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="47186-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="average"></a><span data-ttu-id="47186-106">Метод Average</span><span class="sxs-lookup"><span data-stu-id="47186-106">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="47186-107">Пример</span><span class="sxs-lookup"><span data-stu-id="47186-107">Example</span></span>  
 <span data-ttu-id="47186-108">В следующем примере применяется метод <xref:System.Linq.Enumerable.Average%2A> для нахождения средней цены по прейскуранту продуктов.</span><span class="sxs-lookup"><span data-stu-id="47186-108">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products.</span></span>  
  
 [!code-csharp[DP L2E Examples#Average_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#average_mq)]
 [!code-vb[DP L2E Examples#Average_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#average_mq)]  
  
### <a name="example"></a><span data-ttu-id="47186-109">Пример</span><span class="sxs-lookup"><span data-stu-id="47186-109">Example</span></span>  
 <span data-ttu-id="47186-110">В следующем примере используется метод <xref:System.Linq.Enumerable.Average%2A> для нахождения средней цены по прейскуранту для продуктов каждого типа.</span><span class="sxs-lookup"><span data-stu-id="47186-110">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="47186-111">Пример</span><span class="sxs-lookup"><span data-stu-id="47186-111">Example</span></span>  
 <span data-ttu-id="47186-112">В следующем примере применяется метод <xref:System.Linq.Enumerable.Average%2A> для нахождения средней суммы заказа.</span><span class="sxs-lookup"><span data-stu-id="47186-112">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average total due.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averageprojection_mq)]
 [!code-vb[DP L2E Examples#AverageProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averageprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="47186-113">Пример</span><span class="sxs-lookup"><span data-stu-id="47186-113">Example</span></span>  
 <span data-ttu-id="47186-114">В следующем примере используется метод <xref:System.Linq.Enumerable.Average%2A> для получения средней суммы заказа для каждого идентификатора контактного лица.</span><span class="sxs-lookup"><span data-stu-id="47186-114">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="47186-115">Пример</span><span class="sxs-lookup"><span data-stu-id="47186-115">Example</span></span>  
 <span data-ttu-id="47186-116">В следующем примере используется метод <xref:System.Linq.Enumerable.Average%2A> для возврата заказов со средней суммой заказа для каждого контактного лица.</span><span class="sxs-lookup"><span data-stu-id="47186-116">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the orders with the average total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="47186-117">Количество</span><span class="sxs-lookup"><span data-stu-id="47186-117">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="47186-118">Пример</span><span class="sxs-lookup"><span data-stu-id="47186-118">Example</span></span>  
 <span data-ttu-id="47186-119">В следующем примере применяется метод <xref:System.Linq.Enumerable.Count%2A> для возврата количества продуктов в таблице Product.</span><span class="sxs-lookup"><span data-stu-id="47186-119">The following example uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in the Product table.</span></span>  
  
 [!code-csharp[DP L2E Examples#Count](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#count)]
 [!code-vb[DP L2E Examples#Count](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#count)]  
  
### <a name="example"></a><span data-ttu-id="47186-120">Пример</span><span class="sxs-lookup"><span data-stu-id="47186-120">Example</span></span>  
 <span data-ttu-id="47186-121">В следующем примере используется метод <xref:System.Linq.Enumerable.Count%2A> для возврата списка идентификаторов контактных лиц и определения того, сколько заказов имеет каждый из них.</span><span class="sxs-lookup"><span data-stu-id="47186-121">The following example uses the <xref:System.Linq.Enumerable.Count%2A> method to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countnested)]
 [!code-vb[DP L2E Examples#CountNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="47186-122">Пример</span><span class="sxs-lookup"><span data-stu-id="47186-122">Example</span></span>  
 <span data-ttu-id="47186-123">В следующем примере продукты группируются по цвету и используется метод <xref:System.Linq.Enumerable.Count%2A> для возврата количества продуктов в каждой цветовой группе.</span><span class="sxs-lookup"><span data-stu-id="47186-123">The following example groups products by color and uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="longcount"></a><span data-ttu-id="47186-124">LongCount</span><span class="sxs-lookup"><span data-stu-id="47186-124">LongCount</span></span>  
  
### <a name="example"></a><span data-ttu-id="47186-125">Пример</span><span class="sxs-lookup"><span data-stu-id="47186-125">Example</span></span>  
 <span data-ttu-id="47186-126">В следующем примере происходит возврат количества контактов с применением типа данных Long Integer.</span><span class="sxs-lookup"><span data-stu-id="47186-126">The following example gets the contact count as a long integer.</span></span>  
  
 [!code-csharp[DP L2E Examples#LongCountSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#longcountsimple)]
 [!code-vb[DP L2E Examples#LongCountSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#longcountsimple)]  
  
## <a name="max"></a><span data-ttu-id="47186-127">Максимум</span><span class="sxs-lookup"><span data-stu-id="47186-127">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="47186-128">Пример</span><span class="sxs-lookup"><span data-stu-id="47186-128">Example</span></span>  
 <span data-ttu-id="47186-129">В следующем примере используется метод <xref:System.Linq.Enumerable.Max%2A> для возврата наибольшей суммы заказа.</span><span class="sxs-lookup"><span data-stu-id="47186-129">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxprojection_mq)]
 [!code-vb[DP L2E Examples#MaxProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="47186-130">Пример</span><span class="sxs-lookup"><span data-stu-id="47186-130">Example</span></span>  
 <span data-ttu-id="47186-131">В следующем примере используется метод <xref:System.Linq.Enumerable.Max%2A> для получения наибольшей суммы заказа для каждого идентификатора контактного лица.</span><span class="sxs-lookup"><span data-stu-id="47186-131">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="47186-132">Пример</span><span class="sxs-lookup"><span data-stu-id="47186-132">Example</span></span>  
 <span data-ttu-id="47186-133">В следующем примере используется метод <xref:System.Linq.Enumerable.Max%2A> для получения наибольшей суммы заказа для каждого идентификатора контактного лица.</span><span class="sxs-lookup"><span data-stu-id="47186-133">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="47186-134">Минимум</span><span class="sxs-lookup"><span data-stu-id="47186-134">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="47186-135">Пример</span><span class="sxs-lookup"><span data-stu-id="47186-135">Example</span></span>  
 <span data-ttu-id="47186-136">В следующем примере используется метод <xref:System.Linq.Enumerable.Min%2A> для возврата наименьшей суммы заказа.</span><span class="sxs-lookup"><span data-stu-id="47186-136">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#minprojection_mq)]
 [!code-vb[DP L2E Examples#MinProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#minprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="47186-137">Пример</span><span class="sxs-lookup"><span data-stu-id="47186-137">Example</span></span>  
 <span data-ttu-id="47186-138">В следующем примере используется метод <xref:System.Linq.Enumerable.Min%2A> для получения заказов с наименьшей суммы заказа для каждого идентификатора контактного лица.</span><span class="sxs-lookup"><span data-stu-id="47186-138">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="47186-139">Пример</span><span class="sxs-lookup"><span data-stu-id="47186-139">Example</span></span>  
 <span data-ttu-id="47186-140">В следующем примере используется метод <xref:System.Linq.Enumerable.Min%2A> для получения заказов с наименьшей суммы заказа для каждого идентификатора контактного лица.</span><span class="sxs-lookup"><span data-stu-id="47186-140">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="47186-141">Sum</span><span class="sxs-lookup"><span data-stu-id="47186-141">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="47186-142">Пример</span><span class="sxs-lookup"><span data-stu-id="47186-142">Example</span></span>  
 <span data-ttu-id="47186-143">В следующем примере используется метод <xref:System.Linq.Enumerable.Sum%2A>, который возвращает общую сумму количества продуктов в заказах из таблицы SalesOrderDetail.</span><span class="sxs-lookup"><span data-stu-id="47186-143">The following example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total number of order quantities in the SalesOrderDetail table.</span></span>  
  
 [!code-csharp[DP L2E Examples#SumProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#sumprojection_mq)]
 [!code-vb[DP L2E Examples#SumProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#sumprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="47186-144">Пример</span><span class="sxs-lookup"><span data-stu-id="47186-144">Example</span></span>  
 <span data-ttu-id="47186-145">В следующем примере используется метод <xref:System.Linq.Enumerable.Sum%2A> для получения суммы заказа для каждого идентификатора контактного лица.</span><span class="sxs-lookup"><span data-stu-id="47186-145">The following example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="47186-146">См. также</span><span class="sxs-lookup"><span data-stu-id="47186-146">See also</span></span>

- [<span data-ttu-id="47186-147">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="47186-147">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
