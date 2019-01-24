---
title: Примеры синтаксиса запросов на основе методов. Операторы работы с элементами (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eedf2fbd-f407-4f62-bb1a-c00eb001b1dd
ms.openlocfilehash: 3ea9b8cebdec2dc6fc7284907d8183750009678f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54725224"
---
# <a name="method-based-query-syntax-examples-element-operators-linq-to-dataset"></a><span data-ttu-id="1083d-102">Примеры синтаксиса запросов на основе методов. Операторы работы с элементами (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="1083d-102">Method-Based Query Syntax Examples: Element Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="1083d-103">Примеры в этом разделе демонстрируют, как использовать методы <xref:System.Linq.Enumerable.First%2A> и <xref:System.Linq.Enumerable.ElementAt%2A>, чтобы получить элементы <xref:System.Data.DataRow> из объекта <xref:System.Data.DataSet> с использованием синтаксиса выражений запросов.</span><span class="sxs-lookup"><span data-stu-id="1083d-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> and <xref:System.Linq.Enumerable.ElementAt%2A> methods to get <xref:System.Data.DataRow> elements from a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="1083d-104">`FillDataSet` Метод, используемый в этих примерах указывается в [загрузка данных в DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="1083d-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="1083d-105">В примерах данного раздела используются таблицы Contact, Address, Product, SalesOrderHeader и SalesOrderDetail из образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="1083d-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="1083d-106">В примерах в этом разделе используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="1083d-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
[!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]   
[!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]     

 <span data-ttu-id="1083d-107">Дополнительные сведения см. в разделе [Как Создание проектов LINQ to DataSet в Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="1083d-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="elementat"></a><span data-ttu-id="1083d-108">ElementAt</span><span class="sxs-lookup"><span data-stu-id="1083d-108">ElementAt</span></span>  
  
### <a name="example"></a><span data-ttu-id="1083d-109">Пример</span><span class="sxs-lookup"><span data-stu-id="1083d-109">Example</span></span>  
 <span data-ttu-id="1083d-110">В этом примере используется метод <xref:System.Linq.Enumerable.ElementAt%2A>, чтобы получить пятый адрес, в котором `PostalCode` == "M4B 1V7".</span><span class="sxs-lookup"><span data-stu-id="1083d-110">This example uses the <xref:System.Linq.Enumerable.ElementAt%2A> method to retrieve the fifth address where `PostalCode` == "M4B 1V7".</span></span>  
  
[!code-csharp[DP LINQ to DataSet Examples#ElementAt](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#elementat)]   
[!code-vb[DP LINQ to DataSet Examples#ElementAt](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#elementat)]     
  
## <a name="first"></a><span data-ttu-id="1083d-111">First</span><span class="sxs-lookup"><span data-stu-id="1083d-111">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="1083d-112">Пример</span><span class="sxs-lookup"><span data-stu-id="1083d-112">Example</span></span>  
 <span data-ttu-id="1083d-113">В этом примере используется метод <xref:System.Linq.Enumerable.First%2A>, чтобы возвратить первый контракт, в котором имя «Brooke».</span><span class="sxs-lookup"><span data-stu-id="1083d-113">This example uses the <xref:System.Linq.Enumerable.First%2A> method to return the first contact whose first name is 'Brooke'.</span></span>  
  
[!code-csharp[DP LINQ to DataSet Examples#FirstSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#firstsimple)]   
[!code-vb[DP LINQ to DataSet Examples#FirstSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#firstsimple)] 
  
## <a name="see-also"></a><span data-ttu-id="1083d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="1083d-114">See also</span></span>
- [<span data-ttu-id="1083d-115">Загрузка данных в DataSet</span><span class="sxs-lookup"><span data-stu-id="1083d-115">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [<span data-ttu-id="1083d-116">Примеры LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="1083d-116">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [<span data-ttu-id="1083d-117">Общие сведения о стандартных операторах запроса</span><span class="sxs-lookup"><span data-stu-id="1083d-117">Standard Query Operators Overview</span></span>](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
