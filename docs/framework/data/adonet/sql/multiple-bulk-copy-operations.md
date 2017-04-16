---
title: "Проведение нескольких операций массового копирования | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5ad12f94-7459-4a93-a421-4160d1a90715
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Проведение нескольких операций массового копирования
Несколько операций массового копирования можно выполнять при помощи одного экземпляра класса <xref:System.Data.SqlClient.SqlBulkCopy>.  При изменении параметров операции в копиях \(например, имени целевой таблицы\) их необходимо обновить перед тем, как вызывать какие\-либо методы **WriteToServer**, как показано в следующем примере.  Значения всех свойств, если они не были явно изменены, остаются такими же, какие они были в предыдущей операции массового копирования для данного экземпляра.  
  
> [!NOTE]
>  Выполнение нескольких операций массового копирования при помощи одного экземпляра объекта <xref:System.Data.SqlClient.SqlBulkCopy> обычно более эффективно, чем использование отдельного экземпляра для каждой операции.  
  
 При выполнении нескольких операций массового копирования с помощью одного объекта <xref:System.Data.SqlClient.SqlBulkCopy> нет ограничений в отношении того, отличается ли исходная и целевая информация в каждой операции или является одинаковой.  Однако каждый раз при записи на сервер необходимо проверять, что сведения ассоциирования столбцов заданы правильно.  
  
> [!IMPORTANT]
>  Этот образец не запустится до тех пор, пока не будут созданы рабочие таблицы, описанные в разделе [Подготовка к выполнению примера массового копирования](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md).  Данный код предназначен только для демонстрации синтаксиса использования **SqlBulkCopy**.  Если исходная и целевая таблицы расположены в одном и том же экземпляре SQL Server, легче и быстрее использовать для копирования данных инструкцию `INSERT … SELECT` языка Transact\-SQL.  
  
 [!code-csharp[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/VB/source.vb#1)]  
  
## См. также  
 [Операции массового копирования в SQL Server](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)