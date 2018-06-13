---
title: Связанные с определенными наборами данных примеры операторов (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8fdd64af-6ad0-46cd-91c8-dbe26620eeb1
ms.openlocfilehash: 8abcab3bc2e2ee65f7b54581d9144d62cb5d5dd6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759989"
---
# <a name="dataset-specific-operator-examples-linq-to-dataset"></a><span data-ttu-id="fbdd9-102">Связанные с определенными наборами данных примеры операторов (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="fbdd9-102">DataSet-Specific Operator Examples (LINQ to DataSet)</span></span>
<span data-ttu-id="fbdd9-103">В примерах этого раздела показано, как использовать методы <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> и класс <xref:System.Data.DataRowComparer>.</span><span class="sxs-lookup"><span data-stu-id="fbdd9-103">The examples in this topic demonstrate how to use the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method and the <xref:System.Data.DataRowComparer> class.</span></span>  
  
 <span data-ttu-id="fbdd9-104">`FillDataSet` Используется в этих примерах метод определен в [загрузка данных в наборе данных](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="fbdd9-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="fbdd9-105">В примерах данного раздела используются таблицы Contact, Address, Product, SalesOrderHeader и SalesOrderDetail из образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="fbdd9-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="fbdd9-106">В примерах в этом разделе используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="fbdd9-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="fbdd9-107">Дополнительные сведения см. в разделе [как: создайте LINQ to DataSet проекта в Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="fbdd9-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="copytodatatable"></a><span data-ttu-id="fbdd9-108">CopyToDataTable</span><span class="sxs-lookup"><span data-stu-id="fbdd9-108">CopyToDataTable</span></span>  
  
### <a name="example"></a><span data-ttu-id="fbdd9-109">Пример</span><span class="sxs-lookup"><span data-stu-id="fbdd9-109">Example</span></span>  
 <span data-ttu-id="fbdd9-110">В данном примере в объект <xref:System.Data.DataTable> загружаются результаты запроса с помощью метода <xref:System.Data.DataTableExtensions.CopyToDataTable%2A>.</span><span class="sxs-lookup"><span data-stu-id="fbdd9-110">This example loads a <xref:System.Data.DataTable> with query results by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#LoadDataTableWithQueryResults](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#loaddatatablewithqueryresults)]
 [!code-vb[DP LINQ to DataSet Examples#LoadDataTableWithQueryResults](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#loaddatatablewithqueryresults)]  
  
## <a name="datarowcomparer"></a><span data-ttu-id="fbdd9-111">DataRowComparer</span><span class="sxs-lookup"><span data-stu-id="fbdd9-111">DataRowComparer</span></span>  
  
### <a name="example"></a><span data-ttu-id="fbdd9-112">Пример</span><span class="sxs-lookup"><span data-stu-id="fbdd9-112">Example</span></span>  
 <span data-ttu-id="fbdd9-113">В данном примере две строки данных сравниваются с помощью класса <xref:System.Data.DataRowComparer>.</span><span class="sxs-lookup"><span data-stu-id="fbdd9-113">This example compares two different data rows by using <xref:System.Data.DataRowComparer>.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CompareDifferentDataRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#comparedifferentdatarows)]  
  
## <a name="see-also"></a><span data-ttu-id="fbdd9-114">См. также</span><span class="sxs-lookup"><span data-stu-id="fbdd9-114">See Also</span></span>  
 [<span data-ttu-id="fbdd9-115">Загрузка данных в DataSet</span><span class="sxs-lookup"><span data-stu-id="fbdd9-115">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="fbdd9-116">Примеры LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="fbdd9-116">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
