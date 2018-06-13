---
title: Несколько операций массового копирования
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5ad12f94-7459-4a93-a421-4160d1a90715
ms.openlocfilehash: 267103e7315e337d223ce60652bdfddedbe4ec02
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358148"
---
# <a name="multiple-bulk-copy-operations"></a>Несколько операций массового копирования
Несколько операций массового копирования можно выполнять при помощи одного экземпляра класса <xref:System.Data.SqlClient.SqlBulkCopy>. При изменении параметров операции в копиях (например, имя целевой таблицы), необходимо обновить их до последующих вызовов к любому из **WriteToServer** методы, как показано в следующем примере. Значения всех свойств, если они не были явно изменены, остаются такими же, какие они были в предыдущей операции массового копирования для данного экземпляра.  
  
> [!NOTE]
>  Выполнение нескольких операций массового копирования при помощи одного экземпляра объекта <xref:System.Data.SqlClient.SqlBulkCopy> обычно более эффективно, чем использование отдельного экземпляра для каждой операции.  
  
 При выполнении нескольких операций массового копирования с помощью одного объекта <xref:System.Data.SqlClient.SqlBulkCopy> нет ограничений в отношении того, отличается ли исходная и целевая информация в каждой операции или является одинаковой. Однако каждый раз при записи на сервер необходимо проверять, что сведения ассоциирования столбцов заданы правильно.  
  
> [!IMPORTANT]
>  Этот образец не запустится, пока вы не создадите рабочие таблицы, как описано в [пример настройки массового копирования](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md). Данный код предназначен для демонстрации синтаксиса использования **SqlBulkCopy** только. Если исходная и целевая таблицы расположены в одном и том же экземпляре SQL Server, легче и быстрее использовать для копирования данных инструкцию `INSERT … SELECT` языка Transact-SQL.  
  
 [!code-csharp[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/VB/source.vb#1)]  
  
## <a name="see-also"></a>См. также  
 [Операции массового копирования в SQL Server](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
