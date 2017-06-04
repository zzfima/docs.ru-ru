---
title: "Примеры синтаксиса для выражений запросов: операторы работы с элементами (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ca392dda-16e3-45c7-8d87-12d8d4ee0578
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Примеры синтаксиса для выражений запросов: операторы работы с элементами (LINQ to DataSet)
Примеры в этом разделе демонстрируют, как использовать методы <xref:System.Linq.Enumerable.First%2A> и <xref:System.Linq.Enumerable.ElementAt%2A>, чтобы получить элементы <xref:System.Data.DataRow> из объекта <xref:System.Data.DataSet> с использованием синтаксиса выражений запросов.  
  
 Метод `FillDataSet`, используемый в данных примерах, описан в разделе [Загрузка данных в DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).  
  
 В примерах данного раздела используются таблицы Contact, Address, Product, SalesOrderHeader и SalesOrderDetail из образца базы данных AdventureWorks.  
  
 В примерах, приведенных в этом разделе, используются следующие инструкции `using`\/`Imports`:  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 Для получения дополнительной информации см. [Как создать проект LINQ to DataSet в среде Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).  
  
## ElementAt  
  
### Пример  
 В этом примере используется метод <xref:System.Linq.Enumerable.ElementAt%2A>, чтобы получить пятый адрес, в котором `PostalCode` \=\= "M4B 1V7".  
  
 [!code-csharp[DP LINQ to DataSet Examples#ElementAt](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#elementat)]
 [!code-vb[DP LINQ to DataSet Examples#ElementAt](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#elementat)]  
  
## First  
  
### Пример  
 В этом примере используется метод <xref:System.Linq.Enumerable.First%2A>, чтобы возвратить первый контракт, в котором имя «Brooke».  
  
 [!code-csharp[DP LINQ to DataSet Examples#FirstSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#firstsimple)]
 [!code-vb[DP LINQ to DataSet Examples#FirstSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#firstsimple)]  
  
## См. также  
 [Загрузка данных в DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)   
 [Примеры LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)   
 [Standard Query Operators Overview](../../../../ocs/visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)