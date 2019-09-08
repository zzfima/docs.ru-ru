---
title: Объекты DataAdapter и DataReader
ms.date: 03/30/2017
ms.assetid: cc952ca2-ec19-46ab-9189-15174b52cb74
ms.openlocfilehash: 20c6d514e70d2e4db451e0fff02e72688bf7d0ba
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786646"
---
# <a name="dataadapters-and-datareaders"></a>Объекты DataAdapter и DataReader
ADO.NET **DataReader** можно использовать для получения однопроходного потока данных из базы данных только для чтения. Результаты возвращаются при выполнении запроса и хранятся в сетевом буфере на клиенте, пока они не будут запрошены с помощью метода **Read** объекта **DataReader**. Использование **DataReader** может увеличить производительность приложения, извлекая данные сразу после их доступности и (по умолчанию) сохраняя в памяти только одну строку за раз, уменьшая нагрузку на систему.  
  
 Класс <xref:System.Data.Common.DataAdapter> используется для получения данных из источника данных и заполнения таблиц в <xref:System.Data.DataSet>. Класс `DataAdapter` позволяет также решить задачу по возврату изменений, сделанных в объекте `DataSet`, обратно в источник данных. В классе `DataAdapter` используется объект `Connection` поставщика данных .NET Framework для подключения к источнику данных, а также используются объекты `Command` для получения из него данных и решения задачи по записи изменений в источник данных.  
  
 Каждый поставщик данных .NET Framework, входящий в состав .NET Framework, включает объекты <xref:System.Data.Common.DbDataReader> и <xref:System.Data.Common.DbDataAdapter>: поставщик данных .NET Framework для OLE DB - объекты <xref:System.Data.OleDb.OleDbDataReader> и <xref:System.Data.OleDb.OleDbDataAdapter>, поставщик данных .NET Framework для SQL Server - объекты <xref:System.Data.SqlClient.SqlDataReader> и <xref:System.Data.SqlClient.SqlDataAdapter>, поставщик данных .NET Framework для ODBC - объекты <xref:System.Data.Odbc.OdbcDataReader> и <xref:System.Data.Odbc.OdbcDataAdapter>, а поставщик данных .NET Framework для Oracle - объекты <xref:System.Data.OracleClient.OracleDataReader> и <xref:System.Data.OracleClient.OracleDataAdapter>.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Извлечение данных с помощью объекта DataReader](retrieving-data-using-a-datareader.md)  
 Описывает объект **datareader** ADO.NET и способ его использования для возврата потока результатов из источника данных.  
  
 [Заполнение набора данных с помощью адаптера данных DataAdapter](populating-a-dataset-from-a-dataadapter.md)  
 Содержит описание того, как заполнить `DataSet` таблицами, столбцами и строками с использованием `DataAdapter`.  
  
 [Параметры DataAdapter](dataadapter-parameters.md)  
 Показывает, как использовать параметры со свойствами команды `DataAdapter`, включая то, как сопоставить содержимое столбца в `DataSet` с параметром команды.  
  
 [Добавление существующих ограничений к набору данных](adding-existing-constraints-to-a-dataset.md)  
 Показывает, как добавить существующие ограничения к `DataSet`.  
  
 [Сопоставления DataAdapter, DataTable и DataColumn](dataadapter-datatable-and-datacolumn-mappings.md)  
 Описывает, как задать `DataTableMappings` и `ColumnMappings` для `DataAdapter`.  
  
 [Разбивка на страницы результатов запроса](paging-through-a-query-result.md)  
 Предоставляет пример просмотра результатов запроса в виде страниц данных.  
  
 [Обновление источников данных с объектами DataAdapter](updating-data-sources-with-dataadapters.md)  
 Описывает, как использовать `DataAdapter` для решения задачи записи изменений в `DataSet` обратно в базу данных.  
  
 [Обработка событий DataAdapter](handling-dataadapter-events.md)  
 Описывает события `DataAdapter` и способы их использования.  
  
 [Выполнение пакетных операций с использованием объектов DataAdapter](performing-batch-operations-using-dataadapters.md)  
 Показывает, как повысить производительность приложения путем уменьшения количества циклов обмена данными с SQL Server в ходе применения обновлений из `DataSet`.  
  
## <a name="see-also"></a>См. также

- [Подключение к источнику данных](connecting-to-a-data-source.md)
- [Команды и параметры](commands-and-parameters.md)
- [Транзакции и параллельность](transactions-and-concurrency.md)
- [Наборы данных, таблицы данных и объекты DataView](./dataset-datatable-dataview/index.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
