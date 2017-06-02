---
title: "Операции массового копирования в SQL Server | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 83a7a0d2-8018-4354-97b9-0b1d99f8342b
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Операции массового копирования в SQL Server
Microsoft SQL Server включает в себя распространенную программу командной строки **bcp**, обеспечивающую быстрое массовое копирование файлов большого объема в таблицы или представления баз данных SQL Server.  Класс <xref:System.Data.SqlClient.SqlBulkCopy> позволяет разрабатывать решения на управляемом коде, обеспечивающие аналогичную функциональность.  Существуют другие способы загрузки данных в таблицу SQL Server \(например, инструкция INSERT\), но класс <xref:System.Data.SqlClient.SqlBulkCopy> существенно превосходит их по производительности.  
  
 Класс <xref:System.Data.SqlClient.SqlBulkCopy> может использоваться для записи данных только в таблицы SQL Server.  SQL Server не является единственным источником данных. Можно использовать любой источник данных при условии, что данные можно будет загрузить в экземпляр <xref:System.Data.DataTable> или считать экземпляром <xref:System.Data.IDataReader>.  
  
 При помощи класса <xref:System.Data.SqlClient.SqlBulkCopy> можно выполнить следующие операции.  
  
-   Отдельную операцию массового копирования.  
  
-   Несколько операций массового копирования.  
  
-   Операцию массового копирования внутри транзакции.  
  
> [!NOTE]
>  При использовании платформы .NET Framework 1.1 или более ранней версии \(не поддерживающей класс <xref:System.Data.SqlClient.SqlBulkCopy>\) инструкцию SQL Server Transact\-SQL **BULK INSERT** можно выполнить при помощи объекта <xref:System.Data.SqlClient.SqlCommand>.  
  
## В этом подразделе  
 [Подготовка к выполнению примера массового копирования](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md)  
 Описывает таблицы, используемые в примерах массового копирования, и содержит скрипты SQL для создания таблиц в базе данных AdventureWorks.  
  
 [Отдельные операции массового копирования](../../../../../docs/framework/data/adonet/sql/single-bulk-copy-operations.md)  
 Описывает выполнение отдельной операции массового копирования данных в экземпляр SQL Server с помощью класса <xref:System.Data.SqlClient.SqlBulkCopy> и операции массового копирования с помощью инструкций Transact\-SQL и класса <xref:System.Data.SqlClient.SqlCommand>.  
  
 [Проведение нескольких операций массового копирования](../../../../../docs/framework/data/adonet/sql/multiple-bulk-copy-operations.md)  
 Описывает выполнение нескольких операций массового копирования данных в экземпляр SQL Server с помощью класса <xref:System.Data.SqlClient.SqlBulkCopy>.  
  
 [Операции транзакций и массового копирования](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md)  
 Описывает выполнение операции массового копирования внутри транзакции, включая фиксацию или откат транзакции.  
  
## См. также  
 [SQL Server и ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)