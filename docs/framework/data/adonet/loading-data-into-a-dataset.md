---
title: "Загрузка данных в DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Загрузка данных в DataSet
Объект <xref:System.Data.DataSet> необходимо заполнить, прежде чем направлять к нему запросы [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].  Существует несколько способов заполнения объекта <xref:System.Data.DataSet>.  Например, можно использовать [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] для запроса к базе данных и загрузки результатов в объект <xref:System.Data.DataSet>.  Для получения дополнительной информации см. [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).  
  
 Другой распространенный способ загрузки данных в объект <xref:System.Data.DataSet> \- использование класса <xref:System.Data.Common.DataAdapter> для получения данных из базы данных.  Это показано в следующем примере.  
  
## Пример  
 В этом примере объект <xref:System.Data.Common.DataAdapter> используется для запроса к базе данных AdventureWorks, получения сведений о продажах начиная с 2002 года и загрузки результатов в объект <xref:System.Data.DataSet>.  После заполнения объекта <xref:System.Data.DataSet> можно создавать к нему запросы с помощью [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].  Метод `FillDataSet`, используемый в данном примере, также используется в примерах запросов в разделе [Примеры LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md).  Для получения дополнительной информации см. [Запросы к объектам DataSet](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md).  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## См. также  
 [Общие сведения о LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-overview.md)   
 [Запросы к объектам DataSet](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)   
 [Примеры LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)