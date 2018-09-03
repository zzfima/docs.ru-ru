---
title: Примеры синтаксиса запросов на основе методов. Операторы набора (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa93af15-28af-4b5e-846b-897308410edb
ms.openlocfilehash: 75918450d3e08436578b1535316f19d2adf32695
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43476239"
---
# <a name="method-based-query-syntax-examples-set-operators-linq-to-dataset"></a><span data-ttu-id="cb040-102">Примеры синтаксиса запросов на основе методов. Операторы набора (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="cb040-102">Method-Based Query Syntax Examples: Set Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="cb040-103">Примеры в этом разделе демонстрируют, как использовать <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A>, и <xref:System.Linq.Enumerable.Union%2A> операторы для выполнения операций сравнения на основе значений в наборах строк данных.[ Загрузка данных в набор данных](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md) см. в разделе [сравнение объектов DataRow](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md) Дополнительные сведения о <xref:System.Data.DataRowComparer>.</span><span class="sxs-lookup"><span data-stu-id="cb040-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A>, and <xref:System.Linq.Enumerable.Union%2A> operators to perform value-based comparison operations on sets of data rows.[Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md) See [Comparing DataRows](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md) for more information on <xref:System.Data.DataRowComparer>.</span></span>  
  
 <span data-ttu-id="cb040-104">`FillDataSet` Метод, используемый в этих примерах указывается в [загрузка данных в DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="cb040-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="cb040-105">В примерах данного раздела используются таблицы Contact, Address, Product, SalesOrderHeader и SalesOrderDetail из образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="cb040-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="cb040-106">В примерах в этом разделе используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="cb040-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="cb040-107">Дополнительные сведения см. в разделе [как: Создание LINQ to DataSet проекта в Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="cb040-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="distinct"></a><span data-ttu-id="cb040-108">Distinct</span><span class="sxs-lookup"><span data-stu-id="cb040-108">Distinct</span></span>  
  
### <a name="example"></a><span data-ttu-id="cb040-109">Пример</span><span class="sxs-lookup"><span data-stu-id="cb040-109">Example</span></span>  
 <span data-ttu-id="cb040-110">В этом примере метод <xref:System.Linq.Enumerable.Distinct%2A> используется для удаления повторяющихся элементов в последовательности.</span><span class="sxs-lookup"><span data-stu-id="cb040-110">This example uses the <xref:System.Linq.Enumerable.Distinct%2A> method to remove duplicate elements in a sequence.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#distinctrows)]
 [!code-vb[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#distinctrows)]  
  
## <a name="except"></a><span data-ttu-id="cb040-111">Except</span><span class="sxs-lookup"><span data-stu-id="cb040-111">Except</span></span>  
  
### <a name="example"></a><span data-ttu-id="cb040-112">Пример</span><span class="sxs-lookup"><span data-stu-id="cb040-112">Example</span></span>  
 <span data-ttu-id="cb040-113">В этом примере метод <xref:System.Linq.Enumerable.Except%2A> используется, чтобы вернуть контакты, которые есть в первой таблице, но отсутствуют во второй.</span><span class="sxs-lookup"><span data-stu-id="cb040-113">This example uses the <xref:System.Linq.Enumerable.Except%2A> method to return contacts that appear in the first table but not in the second.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#except2)]
 [!code-vb[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#except2)]  
  
## <a name="intersect"></a><span data-ttu-id="cb040-114">Пересечение</span><span class="sxs-lookup"><span data-stu-id="cb040-114">Intersect</span></span>  
  
### <a name="example"></a><span data-ttu-id="cb040-115">Пример</span><span class="sxs-lookup"><span data-stu-id="cb040-115">Example</span></span>  
 <span data-ttu-id="cb040-116">В этом примере используется метод <xref:System.Linq.Enumerable.Intersect%2A>, чтобы вернуть контакты, которые есть в обеих таблицах.</span><span class="sxs-lookup"><span data-stu-id="cb040-116">This example uses the <xref:System.Linq.Enumerable.Intersect%2A> method to return contacts that appear in both tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
## <a name="union"></a><span data-ttu-id="cb040-117">Объединение</span><span class="sxs-lookup"><span data-stu-id="cb040-117">Union</span></span>  
  
### <a name="example"></a><span data-ttu-id="cb040-118">Пример</span><span class="sxs-lookup"><span data-stu-id="cb040-118">Example</span></span>  
 <span data-ttu-id="cb040-119">В этом примере используется метод <xref:System.Linq.Enumerable.Union%2A> для возврата уникальных контактов из двух таблиц.</span><span class="sxs-lookup"><span data-stu-id="cb040-119">This example uses the <xref:System.Linq.Enumerable.Union%2A> method to return unique contacts from either of the two tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#union2)]
 [!code-vb[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#union2)]  
  
## <a name="see-also"></a><span data-ttu-id="cb040-120">См. также</span><span class="sxs-lookup"><span data-stu-id="cb040-120">See Also</span></span>  
 [<span data-ttu-id="cb040-121">Загрузка данных в DataSet</span><span class="sxs-lookup"><span data-stu-id="cb040-121">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="cb040-122">Примеры LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="cb040-122">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="cb040-123">Общие сведения о стандартных операторах запроса</span><span class="sxs-lookup"><span data-stu-id="cb040-123">Standard Query Operators Overview</span></span>](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
