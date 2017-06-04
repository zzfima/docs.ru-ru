---
title: "Примеры синтаксиса для выражений запросов: секционирование (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: beb5f361-1ac8-44fb-afa1-2aacea15f166
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Примеры синтаксиса для выражений запросов: секционирование (LINQ to DataSet)
Примеры в данном разделе демонстрируют, как использовать методы <xref:System.Linq.Enumerable.Skip%2A> и <xref:System.Linq.Enumerable.Take%2A> для запроса к <xref:System.Data.DataSet> с использованием синтаксиса выражений запросов.  
  
 Метод `FillDataSet`, используемый в данных примерах, описан в разделе [Загрузка данных в DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).  
  
 В примерах данного раздела используются таблицы Contact, Address, Product, SalesOrderHeader и SalesOrderDetail из образца базы данных AdventureWorks.  
  
 В примерах, приведенных в этом разделе, используются следующие инструкции `using`\/`Imports`:  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 Для получения дополнительной информации см. [Как создать проект LINQ to DataSet в среде Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).  
  
## Пропустить  
  
### Пример  
 В данном примере используется метод <xref:System.Linq.Enumerable.Skip%2A> для получения всех адресов в Сиэтле \(Seattle\), кроме первых двух.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SkipNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#skipnested)]
 [!code-vb[DP LINQ to DataSet Examples#SkipNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#skipnested)]  
  
## Take  
  
### Пример  
 В данном примере используется метод <xref:System.Linq.Enumerable.Take%2A> для получения первых трех адресов в Сиэтле \(Seattle\).  
  
 [!code-csharp[DP LINQ to DataSet Examples#TakeNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#takenested)]
 [!code-vb[DP LINQ to DataSet Examples#TakeNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#takenested)]  
  
## См. также  
 [Загрузка данных в DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)   
 [Примеры LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)   
 [Standard Query Operators Overview](../../../../ocs/visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)