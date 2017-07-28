---
title: "Запрос к типизированным объектам DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Запрос к типизированным объектам DataSet
Если схема объекта <xref:System.Data.DataSet> известна во время разработки приложения, при создании запроса [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] рекомендуется использовать типизированный объект <xref:System.Data.DataSet>.  Типизированный объект <xref:System.Data.DataSet> представляет класс, производный от <xref:System.Data.DataSet>.  Поэтому он наследует все методы, события и свойства класса <xref:System.Data.DataSet>.  Кроме того, типизированный объект <xref:System.Data.DataSet> предоставляет методы, события и свойства со строгой типизацией.  Это означает, что доступ к таблицам и столбцам можно получить по имени, не используя методы на основе коллекций.  Это упрощает запросы и повышает их читаемость.  Для получения дополнительной информации см. [Типизированные объекты DataSets](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] также поддерживает запросы к типизированным объектам <xref:System.Data.DataSet>.  Если объект <xref:System.Data.DataSet> типизирован, нет необходимости использовать универсальный метод <xref:System.Data.DataRowExtensions.Field%2A> или метод <xref:System.Data.DataRowExtensions.SetField%2A> для доступа к данным столбцов.  Имена свойств доступны во время компиляции, так как сведения о типе включаются в объект <xref:System.Data.DataSet>. Запрос [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] предоставляет доступ к значениям столбцов правильного типа, поэтому ошибки несоответствия типов обнаруживаются во время компиляции, а не во время выполнения.  
  
 Прежде чем направлять запросы к типизированному объекту <xref:System.Data.DataSet>, необходимо создать класс с помощью конструктора DataSet в среде [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  Для получения дополнительной информации см. [Практическое руководство. Создание типизированного набора данных](../Topic/Create%20and%20configure%20datasets%20in%20Visual%20Studio.md).  
  
## Пример  
 В следующем примере показан запрос к типизированному объекту <xref:System.Data.DataSet>:  
  
```csharp  
var query = from o in orders  
            where o.OnlineOrderFlag == true  
            select new { o.SalesOrderID,  
                         o.OrderDate,  
                         o.SalesOrderNumber };  
  
foreach(var order in query)   
{  
    Console.WriteLine("{0}\t{1:d}\t{2}",   
order.SalesOrderID,   
order.OrderDate,   
order.SalesOrderNumber);  
}  
```  
  
```vb  
Dim orders = ds.Tables("SalesOrderHeader")  
  
Dim query = _  
       From o In orders _  
       Where o.OnlineOrderFlag = True _  
       Select New {SalesOrderID := o.SalesOrderID, _  
                   OrderDate := o.OrderDate, _  
                   SalesOrderNumber := o.SalesOrderNumber}  
  
For Each Dim onlineOrder In query  
 Console.WriteLine("{0}\t{1:d}\t{2}", _  
 onlineOrder.SalesOrderID, _  
 onlineOrder.OrderDate, _  
 onlineOrder.SalesOrderNumber)  
Next  
```  
  
## См. также  
 [Запросы к объектам DataSet](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)   
 [Межтабличные запросы](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)   
 [Запросы к одиночным таблицам](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)