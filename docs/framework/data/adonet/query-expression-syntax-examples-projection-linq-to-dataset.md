---
title: "Примеры синтаксиса выражений запросов: проекция (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 48c9f5ed-76bf-4228-ab10-5217bbb295a3
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Примеры синтаксиса выражений запросов: проекция (LINQ to DataSet)
Примеры в данном разделе демонстрируют, как использовать методы <xref:System.Linq.Enumerable.Select%2A> и <xref:System.Linq.Enumerable.SelectMany%2A> для запроса к <xref:System.Data.DataSet> с использованием синтаксиса выражений запросов.  
  
 Метод `FillDataSet`, используемый в данных примерах, описан в разделе [Загрузка данных в DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).  
  
 В примерах данного раздела используются таблицы Contact, Address, Product, SalesOrderHeader и SalesOrderDetail из образца базы данных AdventureWorks.  
  
 В примерах, приведенных в этом разделе, используются следующие инструкции `using`\/`Imports`:  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 Для получения дополнительной информации см. [Как создать проект LINQ to DataSet в среде Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).  
  
## Выберите  
  
### Пример  
 В этом примере метод <xref:System.Linq.Enumerable.Select%2A> используется, чтобы вернуть все строки из таблицы `Product` и отобразить названия продуктов.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectSimple1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectsimple1)]
 [!code-vb[DP LINQ to DataSet Examples#SelectSimple1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectsimple1)]  
  
### Пример  
 В этом примере метод <xref:System.Linq.Enumerable.Select%2A> используется для возврата последовательности, состоящей только из названий продуктов.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectSimple2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectsimple2)]
 [!code-vb[DP LINQ to DataSet Examples#SelectSimple2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectsimple2)]  
  
## SelectMany  
  
### Пример  
 В этом примере инструкция `From …, …` \(эквивалент метода <xref:System.Linq.Enumerable.SelectMany%2A>\) используется для выбора всех заказов, в которых `TotalDue` составляет менее 500,00.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyCompoundFrom](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanycompoundfrom)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyCompoundFrom](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanycompoundfrom)]  
  
### Пример  
 В этом примере инструкция `From …, …` \(эквивалент метода <xref:System.Linq.Enumerable.SelectMany%2A>\) используется для выбора всех заказов, сделанных 1 октября 2002 года или позднее.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyCompoundFrom2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanycompoundfrom2)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyCompoundFrom2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanycompoundfrom2)]  
  
### Пример  
 В этом примере инструкция `From …, …` \(эквивалент метода <xref:System.Linq.Enumerable.SelectMany%2A>\) используется для выбора всех заказов, в которых общий объем продаж составляет более 10 000,00, а ключевое слово `From` применяется, чтобы исключить повторный запрос общего объема.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyFromAssignment](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanyfromassignment)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyFromAssignment](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanyfromassignment)]  
  
## См. также  
 [Загрузка данных в DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)   
 [Примеры LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)   
 [Standard Query Operators Overview](../../../../ocs/visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)