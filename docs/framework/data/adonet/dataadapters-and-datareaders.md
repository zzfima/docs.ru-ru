---
title: "Объекты DataAdapter и DataReader | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cc952ca2-ec19-46ab-9189-15174b52cb74
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Объекты DataAdapter и DataReader
С помощью объекта ADO.NET **DataReader** можно получить из базы данных поток данных, доступный только для чтения и допускающий перемещение только в прямом направлении.  Результаты возвращаются после выполнения запроса и хранятся в сетевом буфере на клиенте до тех пор, пока не будут запрошены с помощью метода **Read** класса **DataReader**.  Класс **DataReader** позволяет увеличить производительность приложения как путем получения данных, как только они становятся доступны, так и \(по умолчанию\) путем сохранения в памяти только одной строки за один раз, что снижает нагрузку на системные ресурсы.  
  
 Класс <xref:System.Data.Common.DataAdapter> используется для получения данных из источника данных и заполнения таблиц в <xref:System.Data.DataSet>.  Класс `DataAdapter` позволяет также решить задачу по возврату изменений, сделанных в объекте `DataSet`, обратно в источник данных.  В классе `DataAdapter` используется объект `Connection` поставщика данных .NET Framework для подключения к источнику данных, а также используются объекты `Command` для получения из него данных и решения задачи по записи изменений в источник данных.  
  
 Каждый поставщик данных .NET Framework, входящий в состав .NET Framework, включает объекты <xref:System.Data.Common.DbDataReader> и <xref:System.Data.Common.DbDataAdapter>: поставщик данных .NET Framework для OLE DB \- объекты <xref:System.Data.OleDb.OleDbDataReader> и <xref:System.Data.OleDb.OleDbDataAdapter>, поставщик данных .NET Framework для SQL Server \- объекты <xref:System.Data.SqlClient.SqlDataReader> и <xref:System.Data.SqlClient.SqlDataAdapter>, поставщик данных .NET Framework для ODBC \- объекты <xref:System.Data.Odbc.OdbcDataReader> и <xref:System.Data.Odbc.OdbcDataAdapter>, а поставщик данных .NET Framework для Oracle \- объекты <xref:System.Data.OracleClient.OracleDataReader> и <xref:System.Data.OracleClient.OracleDataAdapter>.  
  
## В этом подразделе  
 [Извлечение данных с помощью DataReader](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md)  
 Описывает объект ADO.NET **DataReader** и способы возвращения результатов из источника данных с его помощью.  
  
 [Заполнение набора данных с помощью адаптера данных DataAdapter](../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 Содержит описание того, как заполнить `DataSet` таблицами, столбцами и строками с использованием `DataAdapter`.  
  
 [Параметры DataAdapter](../../../../docs/framework/data/adonet/dataadapter-parameters.md)  
 Показывает, как использовать параметры со свойствами команды `DataAdapter`, включая то, как сопоставить содержимое столбца в `DataSet` с параметром команды.  
  
 [Добавление существующих ограничений к DataSet](../../../../docs/framework/data/adonet/adding-existing-constraints-to-a-dataset.md)  
 Показывает, как добавить существующие ограничения к `DataSet`.  
  
 [Сопоставления DataAdapter, DataTable и DataColumn](../../../../docs/framework/data/adonet/dataadapter-datatable-and-datacolumn-mappings.md)  
 Описывает, как задать `DataTableMappings` и `ColumnMappings` для `DataAdapter`.  
  
 [Постраничный просмотр результата запроса](../../../../docs/framework/data/adonet/paging-through-a-query-result.md)  
 Предоставляет пример просмотра результатов запроса в виде страниц данных.  
  
 [Обновление источников данных с помощью объектов DataAdapter](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 Описывает, как использовать `DataAdapter` для решения задачи записи изменений в `DataSet` обратно в базу данных.  
  
 [Обработка событий DataAdapter](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)  
 Описывает события `DataAdapter` и способы их использования.  
  
 [Выполнение пакетных операций с помощью объектов DataAdapter \(ADO.NET\)](../../../../docs/framework/data/adonet/performing-batch-operations-using-dataadapters.md)  
 Показывает, как повысить производительность приложения путем уменьшения количества циклов обмена данными с SQL Server в ходе применения обновлений из `DataSet`.  
  
## См. также  
 [Подключение к источнику данных](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)   
 [Команды и параметры](../../../../docs/framework/data/adonet/commands-and-parameters.md)   
 [Транзакции и параллелизм](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)   
 [Объекты DataSet, DataTable и DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)