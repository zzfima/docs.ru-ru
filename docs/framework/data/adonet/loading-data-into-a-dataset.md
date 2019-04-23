---
title: Загрузка данных в набор данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
ms.openlocfilehash: cb5578d790e5d3f54f75f964bb3288d861c9d7c3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074057"
---
# <a name="loading-data-into-a-dataset"></a><span data-ttu-id="f17b6-102">Загрузка данных в набор данных</span><span class="sxs-lookup"><span data-stu-id="f17b6-102">Loading Data Into a DataSet</span></span>
<span data-ttu-id="f17b6-103">Объект <xref:System.Data.DataSet> необходимо заполнить, прежде чем направлять к нему запросы [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f17b6-103">A <xref:System.Data.DataSet> object must first be populated before you can query over it with [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="f17b6-104">Существует несколько способов заполнения объекта <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="f17b6-104">There are several different ways to populate the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="f17b6-105">Например, можно использовать [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] для запроса к базе данных и загрузки результатов в <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="f17b6-105">For example, you can use [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] to query the database and load the results into the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="f17b6-106">Дополнительные сведения см. в разделе [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="f17b6-106">For more information, see [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).</span></span>  
  
 <span data-ttu-id="f17b6-107">Другой распространенный способ загрузки данных в объект <xref:System.Data.DataSet> - использование класса <xref:System.Data.Common.DataAdapter> для получения данных из базы данных.</span><span class="sxs-lookup"><span data-stu-id="f17b6-107">Another common way to load data into a <xref:System.Data.DataSet> is to use the <xref:System.Data.Common.DataAdapter> class to retrieve data from the database.</span></span> <span data-ttu-id="f17b6-108">Это показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f17b6-108">This is illustrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f17b6-109">Пример</span><span class="sxs-lookup"><span data-stu-id="f17b6-109">Example</span></span>  
 <span data-ttu-id="f17b6-110">В этом примере объект <xref:System.Data.Common.DataAdapter> используется для запроса к базе данных AdventureWorks, получения сведений о продажах начиная с 2002 года и загрузки результатов в объект <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="f17b6-110">This example uses a <xref:System.Data.Common.DataAdapter> to query the AdventureWorks database for sales information from the year 2002, and loads the results into a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="f17b6-111">После заполнения объекта <xref:System.Data.DataSet> можно создавать к нему запросы с помощью [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f17b6-111">After the <xref:System.Data.DataSet> has been populated, you can write queries against it by using [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="f17b6-112">`FillDataSet` Метод в этом примере используется в примерах запросов в [примеры LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md).</span><span class="sxs-lookup"><span data-stu-id="f17b6-112">The `FillDataSet` method in this example is used in the example queries in [LINQ to DataSet Examples](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md).</span></span> <span data-ttu-id="f17b6-113">Дополнительные сведения см. в разделе [запросы наборов данных](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="f17b6-113">For more information, see [Querying DataSets](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md).</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a><span data-ttu-id="f17b6-114">См. также</span><span class="sxs-lookup"><span data-stu-id="f17b6-114">See also</span></span>

- [<span data-ttu-id="f17b6-115">Общие сведения о LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="f17b6-115">LINQ to DataSet Overview</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-overview.md)
- [<span data-ttu-id="f17b6-116">Запросы к DataSet</span><span class="sxs-lookup"><span data-stu-id="f17b6-116">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)
- [<span data-ttu-id="f17b6-117">Примеры LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="f17b6-117">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
