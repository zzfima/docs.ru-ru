---
title: Примеры синтаксиса выражений запросов. Ограничение (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1daf42c2-c9f4-4cda-b291-7641b9c6d3fe
ms.openlocfilehash: 04a7b2027ac956d14086f94527b10d253749949d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794665"
---
# <a name="query-expression-syntax-examples-restriction-linq-to-dataset"></a><span data-ttu-id="3123c-102">Примеры синтаксиса выражений запросов. Ограничение (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="3123c-102">Query Expression Syntax Examples: Restriction (LINQ to DataSet)</span></span>
<span data-ttu-id="3123c-103">В примерах данного раздела показано, как использовать метод <xref:System.Linq.Enumerable.Where%2A> для запросов к объекту <xref:System.Data.DataSet> с использованием синтаксиса выражений запросов.</span><span class="sxs-lookup"><span data-stu-id="3123c-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Where%2A> method to query a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="3123c-104">Метод, используемый в этих примерах, задается при [загрузке данных в набор данных.](loading-data-into-a-dataset.md) `FillDataSet`</span><span class="sxs-lookup"><span data-stu-id="3123c-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="3123c-105">В примерах данного раздела используются таблицы Contact, Address, Product, SalesOrderHeader и SalesOrderDetail из образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="3123c-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="3123c-106">В примерах этого раздела используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="3123c-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
[!code-csharp[DP LINQ to DataSetExamples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]        
  
 <span data-ttu-id="3123c-107">Дополнительные сведения см. в разделе [Практическое руководство. Создание проекта LINQ to DataSet в Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="3123c-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="where"></a><span data-ttu-id="3123c-108">Where</span><span class="sxs-lookup"><span data-stu-id="3123c-108">Where</span></span>  
  
### <a name="example"></a><span data-ttu-id="3123c-109">Пример</span><span class="sxs-lookup"><span data-stu-id="3123c-109">Example</span></span>  
 <span data-ttu-id="3123c-110">В этом примере происходит возврат всех заказов в оперативном режиме.</span><span class="sxs-lookup"><span data-stu-id="3123c-110">This example returns all online orders.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where1)]  
 [!code-vb[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where1)]     
  
### <a name="example"></a><span data-ttu-id="3123c-111">Пример</span><span class="sxs-lookup"><span data-stu-id="3123c-111">Example</span></span>  
 <span data-ttu-id="3123c-112">В следующем примере возвращаются заказы, количество единиц товара в которых больше 2 и меньше 6.</span><span class="sxs-lookup"><span data-stu-id="3123c-112">This example returns the orders where the order quantity is greater than 2 and less than 6.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where2)]  
 [!code-vb[DP LINQ to DataSet Examples#Where2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where2)]     
  
### <a name="example"></a><span data-ttu-id="3123c-113">Пример</span><span class="sxs-lookup"><span data-stu-id="3123c-113">Example</span></span>  
 <span data-ttu-id="3123c-114">В этом примере возвращаются все продукты красного цвета.</span><span class="sxs-lookup"><span data-stu-id="3123c-114">This example returns all red colored products.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]  
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]     
  
### <a name="example"></a><span data-ttu-id="3123c-115">Пример</span><span class="sxs-lookup"><span data-stu-id="3123c-115">Example</span></span>  
 <span data-ttu-id="3123c-116">В этом примере метод <xref:System.Linq.Enumerable.Where%2A> используется для поиска заказов, сделанных после 1 декабря 2002 г. Затем с помощью метода <xref:System.Data.DataRow.GetChildRows%2A> определяются подробности каждого заказа.</span><span class="sxs-lookup"><span data-stu-id="3123c-116">This example uses the <xref:System.Linq.Enumerable.Where%2A> method to find orders that were made after December 1, 2002 and then uses the <xref:System.Data.DataRow.GetChildRows%2A> method to get the details for each order.</span></span>  
  
 [!code-csharp[DP LINQ to DataSetExamples#WhereDrillDown](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#wheredrilldown)]       
 [!code-vb[DP LINQ to DataSet Examples#WhereDrillDown](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#wheredrilldown)]  
  
## <a name="see-also"></a><span data-ttu-id="3123c-117">См. также</span><span class="sxs-lookup"><span data-stu-id="3123c-117">See also</span></span>

- [<span data-ttu-id="3123c-118">Загрузка данных в DataSet</span><span class="sxs-lookup"><span data-stu-id="3123c-118">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="3123c-119">Примеры LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="3123c-119">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="3123c-120">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="3123c-120">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="3123c-121">Общие сведения о стандартных операторах запроса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3123c-121">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
