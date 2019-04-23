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
# <a name="loading-data-into-a-dataset"></a>Загрузка данных в набор данных
Объект <xref:System.Data.DataSet> необходимо заполнить, прежде чем направлять к нему запросы [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]. Существует несколько способов заполнения объекта <xref:System.Data.DataSet>. Например, можно использовать [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] для запроса к базе данных и загрузки результатов в <xref:System.Data.DataSet>. Дополнительные сведения см. в разделе [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).  
  
 Другой распространенный способ загрузки данных в объект <xref:System.Data.DataSet> - использование класса <xref:System.Data.Common.DataAdapter> для получения данных из базы данных. Это показано в следующем примере:  
  
## <a name="example"></a>Пример  
 В этом примере объект <xref:System.Data.Common.DataAdapter> используется для запроса к базе данных AdventureWorks, получения сведений о продажах начиная с 2002 года и загрузки результатов в объект <xref:System.Data.DataSet>. После заполнения объекта <xref:System.Data.DataSet> можно создавать к нему запросы с помощью [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]. `FillDataSet` Метод в этом примере используется в примерах запросов в [примеры LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md). Дополнительные сведения см. в разделе [запросы наборов данных](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md).  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения о LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-overview.md)
- [Запросы к DataSet](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)
- [Примеры LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
