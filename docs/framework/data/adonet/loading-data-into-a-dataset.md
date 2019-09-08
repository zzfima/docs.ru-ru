---
title: Загрузка данных в набор данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
ms.openlocfilehash: 53f0f5a589a0033c9612f0465dff090ab04e3fc4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794956"
---
# <a name="loading-data-into-a-dataset"></a><span data-ttu-id="c6be9-102">Загрузка данных в набор данных</span><span class="sxs-lookup"><span data-stu-id="c6be9-102">Loading Data Into a DataSet</span></span>
<span data-ttu-id="c6be9-103">Прежде <xref:System.Data.DataSet> чем можно будет выполнить запрос к нему с помощью LINQ to DataSet, сначала необходимо заполнить объект.</span><span class="sxs-lookup"><span data-stu-id="c6be9-103">A <xref:System.Data.DataSet> object must first be populated before you can query over it with LINQ to DataSet.</span></span> <span data-ttu-id="c6be9-104">Существует несколько способов заполнения объекта <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="c6be9-104">There are several different ways to populate the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="c6be9-105">Например, можно использовать [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] для запроса базы данных и загрузки результатов <xref:System.Data.DataSet>в.</span><span class="sxs-lookup"><span data-stu-id="c6be9-105">For example, you can use [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] to query the database and load the results into the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="c6be9-106">Дополнительные сведения см. в разделе [LINQ to SQL](./sql/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="c6be9-106">For more information, see [LINQ to SQL](./sql/linq/index.md).</span></span>  
  
 <span data-ttu-id="c6be9-107">Другой распространенный способ загрузки данных в объект <xref:System.Data.DataSet> - использование класса <xref:System.Data.Common.DataAdapter> для получения данных из базы данных.</span><span class="sxs-lookup"><span data-stu-id="c6be9-107">Another common way to load data into a <xref:System.Data.DataSet> is to use the <xref:System.Data.Common.DataAdapter> class to retrieve data from the database.</span></span> <span data-ttu-id="c6be9-108">Это показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="c6be9-108">This is illustrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6be9-109">Пример</span><span class="sxs-lookup"><span data-stu-id="c6be9-109">Example</span></span>  
 <span data-ttu-id="c6be9-110">В этом примере объект <xref:System.Data.Common.DataAdapter> используется для запроса к базе данных AdventureWorks, получения сведений о продажах начиная с 2002 года и загрузки результатов в объект <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="c6be9-110">This example uses a <xref:System.Data.Common.DataAdapter> to query the AdventureWorks database for sales information from the year 2002, and loads the results into a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="c6be9-111"><xref:System.Data.DataSet> После заполнения можно создавать запросы к нему с помощью LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="c6be9-111">After the <xref:System.Data.DataSet> has been populated, you can write queries against it by using LINQ to DataSet.</span></span> <span data-ttu-id="c6be9-112">Метод в этом примере используется в примерах запросов в [LINQ to DataSet примерах.](linq-to-dataset-examples.md) `FillDataSet`</span><span class="sxs-lookup"><span data-stu-id="c6be9-112">The `FillDataSet` method in this example is used in the example queries in [LINQ to DataSet Examples](linq-to-dataset-examples.md).</span></span> <span data-ttu-id="c6be9-113">Дополнительные сведения см. в разделе [запросы к наборам данных](querying-datasets-linq-to-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="c6be9-113">For more information, see [Querying DataSets](querying-datasets-linq-to-dataset.md).</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a><span data-ttu-id="c6be9-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c6be9-114">See also</span></span>

- [<span data-ttu-id="c6be9-115">Общие сведения о LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="c6be9-115">LINQ to DataSet Overview</span></span>](linq-to-dataset-overview.md)
- [<span data-ttu-id="c6be9-116">Запросы к DataSet</span><span class="sxs-lookup"><span data-stu-id="c6be9-116">Querying DataSets</span></span>](querying-datasets-linq-to-dataset.md)
- [<span data-ttu-id="c6be9-117">Примеры LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="c6be9-117">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
