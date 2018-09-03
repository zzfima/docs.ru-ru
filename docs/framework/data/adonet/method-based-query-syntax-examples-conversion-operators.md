---
title: Примеры синтаксиса запросов на основе методов. Операторы преобразования (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a084c16b-9b55-4690-aefd-f8e0810a92c3
ms.openlocfilehash: 4828aafc4e19b9a9d1c74a215dc255caa2dae01d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43456825"
---
# <a name="method-based-query-syntax-examples-conversion-operators-linq-to-dataset"></a><span data-ttu-id="ac33f-102">Примеры синтаксиса запросов на основе методов. Операторы преобразования (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="ac33f-102">Method-Based Query Syntax Examples: Conversion Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="ac33f-103">Примеры в данном разделе демонстрируют, как использовать методы <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> и <xref:System.Linq.Enumerable.ToList%2A> для немедленного выполнения выражения запроса.</span><span class="sxs-lookup"><span data-stu-id="ac33f-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A>, and <xref:System.Linq.Enumerable.ToList%2A> methods to immediately execute a query expression.</span></span>  
  
 <span data-ttu-id="ac33f-104">`FillDataSet` Метод, используемый в этих примерах указывается в [загрузка данных в DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="ac33f-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="ac33f-105">В примерах данного раздела используются таблицы Contact, Address, Product, SalesOrderHeader и SalesOrderDetail из образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="ac33f-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="ac33f-106">В примерах в этом разделе используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="ac33f-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="ac33f-107">Дополнительные сведения см. в разделе [как: Создание LINQ to DataSet проекта в Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="ac33f-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="toarray"></a><span data-ttu-id="ac33f-108">ToArray</span><span class="sxs-lookup"><span data-stu-id="ac33f-108">ToArray</span></span>  
  
### <a name="example"></a><span data-ttu-id="ac33f-109">Пример</span><span class="sxs-lookup"><span data-stu-id="ac33f-109">Example</span></span>  
 <span data-ttu-id="ac33f-110">В этом примере метод <xref:System.Linq.Enumerable.ToArray%2A> используется для немедленного преобразования последовательности в массив.</span><span class="sxs-lookup"><span data-stu-id="ac33f-110">This example uses the <xref:System.Linq.Enumerable.ToArray%2A> method to immediately evaluate a sequence into an array.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToArray](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#toarray)]
 [!code-vb[DP LINQ to DataSet Examples#ToArray](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#toarray)]  
  
## <a name="todictionary"></a><span data-ttu-id="ac33f-111">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="ac33f-111">ToDictionary</span></span>  
  
### <a name="example"></a><span data-ttu-id="ac33f-112">Пример</span><span class="sxs-lookup"><span data-stu-id="ac33f-112">Example</span></span>  
 <span data-ttu-id="ac33f-113">В этом примере метод <xref:System.Linq.Enumerable.ToDictionary%2A> используется для немедленного преобразования последовательности и связанного выражения ключа в словарь.</span><span class="sxs-lookup"><span data-stu-id="ac33f-113">This example uses the <xref:System.Linq.Enumerable.ToDictionary%2A> method to immediately evaluate a sequence and a related key expression into a dictionary.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToDictionary](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#todictionary)]
 [!code-vb[DP LINQ to DataSet Examples#ToDictionary](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#todictionary)]  
  
## <a name="tolist"></a><span data-ttu-id="ac33f-114">ToList</span><span class="sxs-lookup"><span data-stu-id="ac33f-114">ToList</span></span>  
  
### <a name="example"></a><span data-ttu-id="ac33f-115">Пример</span><span class="sxs-lookup"><span data-stu-id="ac33f-115">Example</span></span>  
 <span data-ttu-id="ac33f-116">В этом примере метод <xref:System.Linq.Enumerable.ToList%2A> используется для немедленного преобразования последовательности в объект <xref:System.Collections.Generic.List%601>, где `T` - тип объекта <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="ac33f-116">This example uses the <xref:System.Linq.Enumerable.ToList%2A> method to immediately evaluate a sequence into a <xref:System.Collections.Generic.List%601>, where `T` is of type <xref:System.Data.DataRow>.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToList](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#tolist)]
 [!code-vb[DP LINQ to DataSet Examples#ToList](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#tolist)]  
  
## <a name="see-also"></a><span data-ttu-id="ac33f-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ac33f-117">See Also</span></span>  
 [<span data-ttu-id="ac33f-118">Загрузка данных в DataSet</span><span class="sxs-lookup"><span data-stu-id="ac33f-118">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="ac33f-119">Примеры LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="ac33f-119">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="ac33f-120">Общие сведения о стандартных операторах запроса</span><span class="sxs-lookup"><span data-stu-id="ac33f-120">Standard Query Operators Overview</span></span>](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
