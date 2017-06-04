---
title: "Примеры синтаксиса запросов на основе методов: проекция (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0fc2c8f0-1967-4f30-8b20-39b8dccfb82f
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Примеры синтаксиса запросов на основе методов: проекция (LINQ to DataSet)
В примерах данного раздела показано, как использовать методы <xref:System.Linq.Enumerable.Select%2A> и <xref:System.Linq.Enumerable.SelectMany%2A> для запросов к объекту <xref:System.Data.DataSet> с использованием синтаксиса запросов на основе методов.  
  
 Метод `FillDataSet`, используемый в данных примерах, описан в разделе [Загрузка данных в DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).  
  
 В примерах данного раздела используются таблицы Contact, Address, Product, SalesOrderHeader и SalesOrderDetail из образца базы данных AdventureWorks.  
  
 В примерах, приведенных в этом разделе, используются следующие инструкции `using`\/`Imports`:  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 Для получения дополнительной информации см. [Как создать проект LINQ to DataSet в среде Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).  
  
## Выберите  
  
### Пример  
 В следующем примере метод <xref:System.Linq.Enumerable.Select%2A> используется для проецирования свойств `Name`, `ProductNumber` и `ListPrice` в последовательность анонимных типов.  В результирующем типе свойство `ListPrice` переименовывается в `Price`.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectanonymoustypes_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectanonymoustypes_mq)]  
  
## SelectMany  
  
### Пример  
 В этом примере метод <xref:System.Linq.Enumerable.SelectMany%2A> используется для выбора всех заказов, в которых `TotalDue` составляет менее 500,00.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyCompoundFrom_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanycompoundfrom_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyCompoundFrom_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanycompoundfrom_mq)]  
  
### Пример  
 В этом примере метод <xref:System.Linq.Enumerable.SelectMany%2A> используется для выбора всех заказов, сделанных 1 октября 2002 года или позднее.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyCompoundFrom2_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanycompoundfrom2_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyCompoundFrom2_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanycompoundfrom2_mq)]  
  
## См. также  
 [Загрузка данных в DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)   
 [Примеры LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)   
 [Standard Query Operators Overview](../../../../ocs/visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)