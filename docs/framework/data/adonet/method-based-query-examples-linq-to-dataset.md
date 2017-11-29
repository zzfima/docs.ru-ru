---
title: "Примеры запросов на основе методов (LINQ to DataSet)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d340775c-7f39-4087-a290-5cbec6cfa68e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 995ac8b4fc91517573dbf9cc02dd1133074ade54
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="method-based-query-examples-linq-to-dataset"></a><span data-ttu-id="eef6f-102">Примеры запросов на основе методов (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="eef6f-102">Method-Based Query Examples (LINQ to DataSet)</span></span>
<span data-ttu-id="eef6f-103">В этом разделе приведены примеры программирования [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] с использованием синтаксиса запросов на основе методов, в которых используются стандартные операторы запросов.</span><span class="sxs-lookup"><span data-stu-id="eef6f-103">This section provides [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] programming examples in method-based query syntax that use the standard query operators.</span></span> <span data-ttu-id="eef6f-104"><xref:System.Data.DataSet> Используется в этих примерах заполняется с помощью `FillDataSet` метод, который указывается в [загрузка данных в наборе данных](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="eef6f-104">The <xref:System.Data.DataSet> used in these examples is populated by using the `FillDataSet` method, which is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span> <span data-ttu-id="eef6f-105">Дополнительные сведения см. в разделе [Общие сведения о стандартных операторах запроса](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span><span class="sxs-lookup"><span data-stu-id="eef6f-105">For more information, see [Standard Query Operators Overview](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eef6f-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="eef6f-106">In This Section</span></span>  
 [<span data-ttu-id="eef6f-107">Проекции</span><span class="sxs-lookup"><span data-stu-id="eef6f-107">Projection</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-projection.md)  
 <span data-ttu-id="eef6f-108">Примеры в данном разделе демонстрируют, как использовать методы <xref:System.Linq.Enumerable.Select%2A> и <xref:System.Linq.Enumerable.SelectMany%2A> для запроса к <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="eef6f-108">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Select%2A> and <xref:System.Linq.Enumerable.SelectMany%2A> methods to query a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="eef6f-109">Секционирование</span><span class="sxs-lookup"><span data-stu-id="eef6f-109">Partitioning</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-partitioning-linq.md)  
 <span data-ttu-id="eef6f-110">Примеры в данном разделе демонстрируют, как использовать методы <xref:System.Linq.Enumerable.Skip%2A> и <xref:System.Linq.Enumerable.Take%2A> для запроса <xref:System.Data.DataSet> и секционирования результатов.</span><span class="sxs-lookup"><span data-stu-id="eef6f-110">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> methods to query a <xref:System.Data.DataSet> and partition the results.</span></span>  
  
 [<span data-ttu-id="eef6f-111">Упорядочение</span><span class="sxs-lookup"><span data-stu-id="eef6f-111">Ordering</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-ordering-linq-to-dataset.md)  
 <span data-ttu-id="eef6f-112">Примеры в данном разделе демонстрируют, как использовать методы <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A> и <xref:System.Linq.Enumerable.ThenByDescending%2A> для запроса к <xref:System.Data.DataSet> и упорядочения результатов.</span><span class="sxs-lookup"><span data-stu-id="eef6f-112">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A>, and <xref:System.Linq.Enumerable.ThenByDescending%2A> methods to query a <xref:System.Data.DataSet> and order the results.</span></span>  
  
 [<span data-ttu-id="eef6f-113">Операторы наборов</span><span class="sxs-lookup"><span data-stu-id="eef6f-113">Set Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-set-operators.md)  
 <span data-ttu-id="eef6f-114">В примерах этого раздела показано, как использовать операторы <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A> и <xref:System.Linq.Enumerable.Union%2A> для сравнения на основе значений наборов и рядов данных.</span><span class="sxs-lookup"><span data-stu-id="eef6f-114">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A>, and <xref:System.Linq.Enumerable.Union%2A> operators to perform value-based comparison operations on sets of data rows.</span></span>  
  
 [<span data-ttu-id="eef6f-115">Операторы преобразования</span><span class="sxs-lookup"><span data-stu-id="eef6f-115">Conversion Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-conversion-operators.md)  
 <span data-ttu-id="eef6f-116">Примеры в данном разделе демонстрируют, как использовать методы <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> и <xref:System.Linq.Enumerable.ToList%2A> для немедленного выполнения выражения запроса.</span><span class="sxs-lookup"><span data-stu-id="eef6f-116">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A>, and <xref:System.Linq.Enumerable.ToList%2A> methods to immediately execute a query expression.</span></span>  
  
 [<span data-ttu-id="eef6f-117">Операторы элементов</span><span class="sxs-lookup"><span data-stu-id="eef6f-117">Element Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-element-operators.md)  
 <span data-ttu-id="eef6f-118">Примеры в данном разделе демонстрируют, как использовать методы <xref:System.Linq.Enumerable.First%2A> и <xref:System.Linq.Enumerable.ElementAt%2A> для получения элементов <xref:System.Data.DataRow> из <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="eef6f-118">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> and <xref:System.Linq.Enumerable.ElementAt%2A> methods to get <xref:System.Data.DataRow> elements from a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="eef6f-119">Статистические операторы</span><span class="sxs-lookup"><span data-stu-id="eef6f-119">Aggregate Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-aggregate-operators.md)  
 <span data-ttu-id="eef6f-120">Примеры в данном разделе демонстрируют, как использовать методы <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A> и <xref:System.Linq.Enumerable.Sum%2A> для запроса <xref:System.Data.DataSet> и статистической обработки данных.</span><span class="sxs-lookup"><span data-stu-id="eef6f-120">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query a <xref:System.Data.DataSet> and aggregate data.</span></span>  
  
 [<span data-ttu-id="eef6f-121">Join</span><span class="sxs-lookup"><span data-stu-id="eef6f-121">Join</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-join-linq-to-dataset.md)  
 <span data-ttu-id="eef6f-122">Примеры в данном разделе демонстрируют, как использовать методы <xref:System.Linq.Enumerable.GroupJoin%2A> и <xref:System.Linq.Enumerable.Join%2A> для запроса к <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="eef6f-122">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.GroupJoin%2A> and <xref:System.Linq.Enumerable.Join%2A> methods to query a <xref:System.Data.DataSet>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eef6f-123">См. также</span><span class="sxs-lookup"><span data-stu-id="eef6f-123">See Also</span></span>  
 [<span data-ttu-id="eef6f-124">Примеры выражений запроса</span><span class="sxs-lookup"><span data-stu-id="eef6f-124">Query Expression Examples</span></span>](../../../../docs/framework/data/adonet/query-expression-examples-linq-to-dataset.md)  
 [<span data-ttu-id="eef6f-125">Примеры операторов, специфичных для набора данных</span><span class="sxs-lookup"><span data-stu-id="eef6f-125">DataSet-Specific Operator Examples</span></span>](../../../../docs/framework/data/adonet/dataset-specific-operator-examples-linq-to-dataset.md)  
 [<span data-ttu-id="eef6f-126">Примеры LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="eef6f-126">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
