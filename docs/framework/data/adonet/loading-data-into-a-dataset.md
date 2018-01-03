---
title: "Загрузка данных в набор данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 471a13b5d209def227bf8bc57b1551550b76a0c8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="loading-data-into-a-dataset"></a><span data-ttu-id="0e8aa-102">Загрузка данных в набор данных</span><span class="sxs-lookup"><span data-stu-id="0e8aa-102">Loading Data Into a DataSet</span></span>
<span data-ttu-id="0e8aa-103">Объект <xref:System.Data.DataSet> необходимо заполнить, прежде чем направлять к нему запросы [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e8aa-103">A <xref:System.Data.DataSet> object must first be populated before you can query over it with [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="0e8aa-104">Существует несколько способов заполнения объекта <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="0e8aa-104">There are several different ways to populate the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="0e8aa-105">Например, можно использовать [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] для запросов к базе данных и загрузки результатов в <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="0e8aa-105">For example, you can use [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] to query the database and load the results into the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="0e8aa-106">Дополнительные сведения см. в разделе [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="0e8aa-106">For more information, see [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).</span></span>  
  
 <span data-ttu-id="0e8aa-107">Другой распространенный способ загрузки данных в объект <xref:System.Data.DataSet> - использование класса <xref:System.Data.Common.DataAdapter> для получения данных из базы данных.</span><span class="sxs-lookup"><span data-stu-id="0e8aa-107">Another common way to load data into a <xref:System.Data.DataSet> is to use the <xref:System.Data.Common.DataAdapter> class to retrieve data from the database.</span></span> <span data-ttu-id="0e8aa-108">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="0e8aa-108">This is illustrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e8aa-109">Пример</span><span class="sxs-lookup"><span data-stu-id="0e8aa-109">Example</span></span>  
 <span data-ttu-id="0e8aa-110">В этом примере объект <xref:System.Data.Common.DataAdapter> используется для запроса к базе данных AdventureWorks, получения сведений о продажах начиная с 2002 года и загрузки результатов в объект <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="0e8aa-110">This example uses a <xref:System.Data.Common.DataAdapter> to query the AdventureWorks database for sales information from the year 2002, and loads the results into a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="0e8aa-111">После заполнения объекта <xref:System.Data.DataSet> можно создавать к нему запросы с помощью [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e8aa-111">After the <xref:System.Data.DataSet> has been populated, you can write queries against it by using [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="0e8aa-112">`FillDataSet` Метод в этом примере используется запросов в [примеры LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md).</span><span class="sxs-lookup"><span data-stu-id="0e8aa-112">The `FillDataSet` method in this example is used in the example queries in [LINQ to DataSet Examples](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md).</span></span> <span data-ttu-id="0e8aa-113">Дополнительные сведения см. в разделе [запросы наборов данных](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="0e8aa-113">For more information, see [Querying DataSets](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md).</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a><span data-ttu-id="0e8aa-114">См. также</span><span class="sxs-lookup"><span data-stu-id="0e8aa-114">See Also</span></span>  
 [<span data-ttu-id="0e8aa-115">Общие сведения о LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="0e8aa-115">LINQ to DataSet Overview</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-overview.md)  
 [<span data-ttu-id="0e8aa-116">Запросы к DataSet</span><span class="sxs-lookup"><span data-stu-id="0e8aa-116">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 [<span data-ttu-id="0e8aa-117">Примеры LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="0e8aa-117">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
