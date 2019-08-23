---
title: Операции массового копирования в SQL Server
ms.date: 03/30/2017
ms.assetid: 83a7a0d2-8018-4354-97b9-0b1d99f8342b
ms.openlocfilehash: efa13eb1633fce3b59040ef8da79dba0f6ea81d5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918062"
---
# <a name="bulk-copy-operations-in-sql-server"></a>Операции массового копирования в SQL Server
Microsoft SQL Server включает популярную программу командной строки с именем **bcp** для быстрого копирования больших файлов в таблицы или представления в базах данных SQL Server. Класс <xref:System.Data.SqlClient.SqlBulkCopy> позволяет разрабатывать решения на управляемом коде, обеспечивающие аналогичную функциональность. Существуют другие способы загрузки данных в таблицу SQL Server (например, инструкция INSERT), но класс <xref:System.Data.SqlClient.SqlBulkCopy> существенно превосходит их по производительности.  
  
 Класс <xref:System.Data.SqlClient.SqlBulkCopy> может использоваться для записи данных только в таблицы SQL Server. SQL Server не является единственным источником данных. Можно использовать любой источник данных при условии, что данные можно будет загрузить в экземпляр <xref:System.Data.DataTable> или считать экземпляром <xref:System.Data.IDataReader>.  
  
 При помощи класса <xref:System.Data.SqlClient.SqlBulkCopy> можно выполнить следующие операции.  
  
- Отдельную операцию массового копирования.  
  
- Несколько операций массового копирования.  
  
- Операцию массового копирования внутри транзакции.  
  
> [!NOTE]
> При использовании .NET Framework версии 1,1 или более ранней (которая не поддерживает <xref:System.Data.SqlClient.SqlBulkCopy> класс) можно выполнить SQL Server инструкцию **BULK INSERT** Transact-SQL с помощью <xref:System.Data.SqlClient.SqlCommand> объекта.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Установка примера массового копирования](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md)  
 Описывает таблицы, используемые в примерах массового копирования, и содержит скрипты SQL для создания таблиц в базе данных AdventureWorks.  
  
 [Отдельные операции массового копирования](../../../../../docs/framework/data/adonet/sql/single-bulk-copy-operations.md)  
 Описывает выполнение отдельной операции массового копирования данных в экземпляр SQL Server с помощью класса <xref:System.Data.SqlClient.SqlBulkCopy> и операции массового копирования с помощью инструкций Transact-SQL и класса <xref:System.Data.SqlClient.SqlCommand>.  
  
 [Несколько операций массового копирования](../../../../../docs/framework/data/adonet/sql/multiple-bulk-copy-operations.md)  
 Описывает выполнение нескольких операций массового копирования данных в экземпляр SQL Server с помощью класса <xref:System.Data.SqlClient.SqlBulkCopy>.  
  
 [Транзакции и операции массового копирования](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md)  
 Описывает выполнение операции массового копирования внутри транзакции, включая фиксацию или откат транзакции.  
  
## <a name="see-also"></a>См. также

- [SQL Server и ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
