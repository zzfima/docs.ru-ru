---
title: "Подготовка к выполнению примера массового копирования | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d4dde6ac-b8b6-4593-965a-635c8fb2dadb
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Подготовка к выполнению примера массового копирования
Класс <xref:System.Data.SqlClient.SqlBulkCopy> может использоваться для записи данных только в таблицы SQL Server.  В примерах кода, рассматриваемых в настоящем разделе, используется образец базы данных SQL Server **AdventureWorks**.  В целях предотвращения модификации существующих таблиц в этих образцах кода запись данных осуществляется в таблицы, которые должны быть созданы заранее.  
  
 Обе применяемые таблицы, **BulkCopyDemoMatchingColumns** и **BulkCopyDemoDifferentColumns**, основаны на таблице **Production.Products** базы данных **AdventureWorks**.  В образцах кода, в которых используются эти таблицы, данные добавляются из таблицы **Production.Products** в одну из таблиц, применяемых в коде.  Таблица **BulkCopyDemoDifferentColumns** используется в образце кода для иллюстрации того, как сопоставлять столбцы из таблицы с исходными данными с целевой таблицей, а таблица **BulkCopyDemoMatchingColumns** применяется в большинстве остальных образцов.  
  
 В некоторых образцах кода демонстрируется использование одного класса <xref:System.Data.SqlClient.SqlBulkCopy> для записи в несколько таблиц.  В этих образцах в качестве целевых таблиц применяются таблицы **BulkCopyDemoOrderHeader** и **BulkCopyDemoOrderDetail**.  Эти таблицы основаны на таблицах **Sales.SalesOrderHeader** и **Sales.SalesOrderDetail** базы данных **AdventureWorks**.  
  
> [!NOTE]
>  Образцы кода **SqlBulkCopy** предоставляются только для демонстрации синтаксиса применения **SqlBulkCopy**.  Если исходная и целевая таблицы расположены в одном и том же экземпляре SQL Server, легче и быстрее использовать для копирования данных инструкцию `INSERT … SELECT` языка Transact\-SQL.  
  
## Подготовка таблиц  
 Чтобы создать таблицы, необходимые для правильного выполнения образцов кода, требуется выполнить следующие инструкции Transact\-SQL в базе данных SQL Server.  
  
```  
USE AdventureWorks  
  
IF EXISTS (SELECT * FROM dbo.sysobjects   
 WHERE id = object_id(N'[dbo].[BulkCopyDemoMatchingColumns]')   
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoMatchingColumns]  
  
CREATE TABLE [dbo].[BulkCopyDemoMatchingColumns]([ProductID] [int] IDENTITY(1,1) NOT NULL,  
    [Name] [nvarchar](50) NOT NULL,  
    [ProductNumber] [nvarchar](25) NOT NULL,  
 CONSTRAINT [PK_ProductID] PRIMARY KEY CLUSTERED   
(  
    [ProductID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
  
IF EXISTS (SELECT * FROM dbo.sysobjects   
 WHERE id = object_id(N'[dbo].[BulkCopyDemoDifferentColumns]')   
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoDifferentColumns]  
  
CREATE TABLE [dbo].[BulkCopyDemoDifferentColumns]([ProdID] [int] IDENTITY(1,1) NOT NULL,  
    [ProdNum] [nvarchar](25) NOT NULL,  
    [ProdName] [nvarchar](50) NOT NULL,  
 CONSTRAINT [PK_ProdID] PRIMARY KEY CLUSTERED   
(  
    [ProdID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
  
IF EXISTS (SELECT * FROM dbo.sysobjects   
 WHERE id = object_id(N'[dbo].[BulkCopyDemoOrderHeader]')   
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoOrderHeader]  
  
CREATE TABLE [dbo].[BulkCopyDemoOrderHeader]([SalesOrderID] [int] IDENTITY(1,1) NOT NULL,  
    [OrderDate] [datetime] NOT NULL,  
    [AccountNumber] [nvarchar](15) NULL,  
 CONSTRAINT [PK_SalesOrderID] PRIMARY KEY CLUSTERED   
(  
    [SalesOrderID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
  
IF EXISTS (SELECT * FROM dbo.sysobjects   
 WHERE id = object_id(N'[dbo].[BulkCopyDemoOrderDetail]')   
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoOrderDetail]  
  
CREATE TABLE [dbo].[BulkCopyDemoOrderDetail]([SalesOrderID] [int] NOT NULL,  
    [SalesOrderDetailID] [int] NOT NULL,  
    [OrderQty] [smallint] NOT NULL,  
    [ProductID] [int] NOT NULL,  
    [UnitPrice] [money] NOT NULL,  
 CONSTRAINT [PK_LineNumber] PRIMARY KEY CLUSTERED   
(  
    [SalesOrderID] ASC,  
    [SalesOrderDetailID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
```  
  
## См. также  
 [Операции массового копирования в SQL Server](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)