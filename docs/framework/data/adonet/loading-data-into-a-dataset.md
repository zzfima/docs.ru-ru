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
# <a name="loading-data-into-a-dataset"></a>Загрузка данных в набор данных
Прежде <xref:System.Data.DataSet> чем можно будет выполнить запрос к нему с помощью LINQ to DataSet, сначала необходимо заполнить объект. Существует несколько способов заполнения объекта <xref:System.Data.DataSet>. Например, можно использовать [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] для запроса базы данных и загрузки результатов <xref:System.Data.DataSet>в. Дополнительные сведения см. в разделе [LINQ to SQL](./sql/linq/index.md).  
  
 Другой распространенный способ загрузки данных в объект <xref:System.Data.DataSet> - использование класса <xref:System.Data.Common.DataAdapter> для получения данных из базы данных. Это показано в следующем примере:  
  
## <a name="example"></a>Пример  
 В этом примере объект <xref:System.Data.Common.DataAdapter> используется для запроса к базе данных AdventureWorks, получения сведений о продажах начиная с 2002 года и загрузки результатов в объект <xref:System.Data.DataSet>. <xref:System.Data.DataSet> После заполнения можно создавать запросы к нему с помощью LINQ to DataSet. Метод в этом примере используется в примерах запросов в [LINQ to DataSet примерах.](linq-to-dataset-examples.md) `FillDataSet` Дополнительные сведения см. в разделе [запросы к наборам данных](querying-datasets-linq-to-dataset.md).  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения о LINQ to DataSet](linq-to-dataset-overview.md)
- [Запросы к DataSet](querying-datasets-linq-to-dataset.md)
- [Примеры LINQ to DataSet](linq-to-dataset-examples.md)
