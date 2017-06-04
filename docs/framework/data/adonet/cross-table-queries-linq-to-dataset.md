---
title: "Перекрестные запросы между таблицами (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6819a16f-8656-41af-a54d-dfec0cb66366
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Перекрестные запросы между таблицами (LINQ to DataSet)
Кроме запросов к отдельной таблице, [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] позволяет выполнять межтабличные запросы, которые выполняются с помощью *соединений*.  Соединение представляет собой взаимосвязь объектов одного источника данных с объектами, использующими общий атрибут, например идентификатор продукта или контактного лица, в другом источнике данных.  В объектно\-ориентированном программировании связи между объектами относительно просты для перемещения, так как каждый объект содержит элементы, ссылающиеся на другой объект. Однако в таблицах внешних баз данных перемещение по связям выполняется не столь просто.  Таблицы баз данных не содержат встроенных связей. В таких случаях для соединения элементов из разных источников может потребоваться операция объединения.  Например, если две таблицы содержат данные о продуктах и о продажах, нужно использовать операцию соединения для сопоставления данных о продажах и о продуктах, относящихся к одному и тому же заказу на продажу.  
  
 [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] реализует два оператора соединения: <xref:System.Linq.Enumerable.Join%2A> и <xref:System.Linq.Enumerable.GroupJoin%2A>. Эти операторы выполняют *эквивалентные соединения*, то есть соединения, связывающие два источника данных по равенству ключей.  \(В отличие от этого, [!INCLUDE[tsql](../../../../includes/tsql-md.md)] поддерживает операторы соединения, отличные от `equals`, например оператор `less than`.\)  
  
 В терминах реляционной базы данных оператор <xref:System.Linq.Enumerable.Join%2A> выполняет внутреннее соединение.  Внутреннее соединение представляет собой соединение, при котором возвращаются только объекты, имеющие соответствия в другом наборе данных.  
  
 Операторы <xref:System.Linq.Enumerable.GroupJoin%2A> не имеют прямых аналогов в реляционных базах данных, используют надмножества внутренних соединений и левых внешних соединений. Левое внешнее соединение представляет собой соединение, возвращающее каждый элемент первой \(левой\) коллекции, даже если он не имеет соответствующих элементов во второй коллекции.  
  
 Дополнительные сведения о соединениях см. в разделе [Join Operations](../../../../ocs/visual-basic/programming-guide/concepts/linq/join-operations.md).  
  
## Пример  
 В следующем примере выполняется традиционное соединение таблиц `SalesOrderHeader` и `SalesOrderDetail` из образца базы данных AdventureWorks для получения заказов, сделанных через Интернет начиная с августа.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#join)]
 [!code-vb[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#join)]  
  
## См. также  
 [Запросы к объектам DataSet](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)   
 [Запросы к одиночным таблицам](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)   
 [Запрос к типизированным объектам DataSet](../../../../docs/framework/data/adonet/querying-typed-datasets.md)   
 [Join Operations](../../../../ocs/visual-basic/programming-guide/concepts/linq/join-operations.md)   
 [Примеры LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)