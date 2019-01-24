---
title: Объекты DataAdapter и DataReader
ms.date: 03/30/2017
ms.assetid: cc952ca2-ec19-46ab-9189-15174b52cb74
ms.openlocfilehash: f4588187aad910d0b50b0c804e6de20a477b567b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54583513"
---
# <a name="dataadapters-and-datareaders"></a>Объекты DataAdapter и DataReader
Можно использовать ADO.NET **DataReader** для получения только для чтения однопроходный поток данных из базы данных. Результаты возвращаются после выполнения запроса и хранятся в сетевом буфере на клиенте, пока не запрошены с помощью **чтения** метод **DataReader**. С помощью **DataReader** позволяет увеличить производительность приложения как путем получения данных, как только он доступен, так и (по умолчанию) хранится только одна строка в памяти, уменьшая нагрузку на системные ресурсы одновременно.  
  
 Класс <xref:System.Data.Common.DataAdapter> используется для получения данных из источника данных и заполнения таблиц в <xref:System.Data.DataSet>. Класс `DataAdapter` позволяет также решить задачу по возврату изменений, сделанных в объекте `DataSet`, обратно в источник данных. В классе `DataAdapter` используется объект `Connection` поставщика данных .NET Framework для подключения к источнику данных, а также используются объекты `Command` для получения из него данных и решения задачи по записи изменений в источник данных.  
  
 Каждый поставщик данных .NET Framework, входящий в состав .NET Framework, включает объекты <xref:System.Data.Common.DbDataReader> и <xref:System.Data.Common.DbDataAdapter>: поставщик данных .NET Framework для OLE DB - объекты <xref:System.Data.OleDb.OleDbDataReader> и <xref:System.Data.OleDb.OleDbDataAdapter>, поставщик данных .NET Framework для SQL Server - объекты <xref:System.Data.SqlClient.SqlDataReader> и <xref:System.Data.SqlClient.SqlDataAdapter>, поставщик данных .NET Framework для ODBC - объекты <xref:System.Data.Odbc.OdbcDataReader> и <xref:System.Data.Odbc.OdbcDataAdapter>, а поставщик данных .NET Framework для Oracle - объекты <xref:System.Data.OracleClient.OracleDataReader> и <xref:System.Data.OracleClient.OracleDataAdapter>.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Извлечение данных с помощью объекта DataReader](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md)  
 Описывает объект ADO.NET **DataReader** объекта и способы ее использования для возврата потока результатов из источника данных.  
  
 [Заполнение набора данных с помощью адаптера данных DataAdapter](../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 Содержит описание того, как заполнить `DataSet` таблицами, столбцами и строками с использованием `DataAdapter`.  
  
 [Параметры DataAdapter](../../../../docs/framework/data/adonet/dataadapter-parameters.md)  
 Показывает, как использовать параметры со свойствами команды `DataAdapter`, включая то, как сопоставить содержимое столбца в `DataSet` с параметром команды.  
  
 [Добавление существующих ограничений к набору данных](../../../../docs/framework/data/adonet/adding-existing-constraints-to-a-dataset.md)  
 Показывает, как добавить существующие ограничения к `DataSet`.  
  
 [Сопоставления DataAdapter, DataTable и DataColumn](../../../../docs/framework/data/adonet/dataadapter-datatable-and-datacolumn-mappings.md)  
 Описывает, как задать `DataTableMappings` и `ColumnMappings` для `DataAdapter`.  
  
 [Разбивка на страницы результатов запроса](../../../../docs/framework/data/adonet/paging-through-a-query-result.md)  
 Предоставляет пример просмотра результатов запроса в виде страниц данных.  
  
 [Обновление источников данных с объектами DataAdapter](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 Описывает, как использовать `DataAdapter` для решения задачи записи изменений в `DataSet` обратно в базу данных.  
  
 [Обработка событий DataAdapter](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)  
 Описывает события `DataAdapter` и способы их использования.  
  
 [Выполнение пакетных операций с использованием объектов DataAdapter](../../../../docs/framework/data/adonet/performing-batch-operations-using-dataadapters.md)  
 Показывает, как повысить производительность приложения путем уменьшения количества циклов обмена данными с SQL Server в ходе применения обновлений из `DataSet`.  
  
## <a name="see-also"></a>См. также
- [Подключение к источнику данных](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)
- [Команды и параметры](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [Транзакции и параллельность](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)
- [Наборы данных, таблицы данных и объекты DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
