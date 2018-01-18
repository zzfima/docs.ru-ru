---
title: "Объекты DataAdapter и DataReader"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc952ca2-ec19-46ab-9189-15174b52cb74
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 3a7ce8787dec2f80ba04bef08c5ac355a907feaf
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="dataadapters-and-datareaders"></a><span data-ttu-id="8a564-102">Объекты DataAdapter и DataReader</span><span class="sxs-lookup"><span data-stu-id="8a564-102">DataAdapters and DataReaders</span></span>
<span data-ttu-id="8a564-103">Вы можете использовать ADO.NET **DataReader** для извлечения только для чтения однопроходный поток данных из базы данных.</span><span class="sxs-lookup"><span data-stu-id="8a564-103">You can use the ADO.NET **DataReader** to retrieve a read-only, forward-only stream of data from a database.</span></span> <span data-ttu-id="8a564-104">Результаты возвращаются после выполнения запроса и хранятся в сетевом буфере на клиенте, пока не будут запрошены с помощью **чтения** метод **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="8a564-104">Results are returned as the query executes, and are stored in the network buffer on the client until you request them using the **Read** method of the **DataReader**.</span></span> <span data-ttu-id="8a564-105">С помощью **DataReader** можно повысить производительность приложения как путем получения данных, как только она доступна, так и (по умолчанию) хранится в памяти, снижения нагрузки на систему одновременно только одна строка.</span><span class="sxs-lookup"><span data-stu-id="8a564-105">Using the **DataReader** can increase application performance both by retrieving data as soon as it is available, and (by default) storing only one row at a time in memory, reducing system overhead.</span></span>  
  
 <span data-ttu-id="8a564-106">Класс <xref:System.Data.Common.DataAdapter> используется для получения данных из источника данных и заполнения таблиц в <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="8a564-106">A <xref:System.Data.Common.DataAdapter> is used to retrieve data from a data source and populate tables within a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="8a564-107">Класс `DataAdapter` позволяет также решить задачу по возврату изменений, сделанных в объекте `DataSet`, обратно в источник данных.</span><span class="sxs-lookup"><span data-stu-id="8a564-107">The `DataAdapter` also resolves changes made to the `DataSet` back to the data source.</span></span> <span data-ttu-id="8a564-108">В классе `DataAdapter` используется объект `Connection` поставщика данных .NET Framework для подключения к источнику данных, а также используются объекты `Command` для получения из него данных и решения задачи по записи изменений в источник данных.</span><span class="sxs-lookup"><span data-stu-id="8a564-108">The `DataAdapter` uses the `Connection` object of the .NET Framework data provider to connect to a data source, and it uses `Command` objects to retrieve data from and resolve changes to the data source.</span></span>  
  
 <span data-ttu-id="8a564-109">Каждый поставщик данных .NET Framework, входящий в состав .NET Framework, включает объекты <xref:System.Data.Common.DbDataReader> и <xref:System.Data.Common.DbDataAdapter>: поставщик данных .NET Framework для OLE DB - объекты <xref:System.Data.OleDb.OleDbDataReader> и <xref:System.Data.OleDb.OleDbDataAdapter>, поставщик данных .NET Framework для SQL Server - объекты <xref:System.Data.SqlClient.SqlDataReader> и <xref:System.Data.SqlClient.SqlDataAdapter>, поставщик данных .NET Framework для ODBC - объекты <xref:System.Data.Odbc.OdbcDataReader> и <xref:System.Data.Odbc.OdbcDataAdapter>, а поставщик данных .NET Framework для Oracle - объекты <xref:System.Data.OracleClient.OracleDataReader> и <xref:System.Data.OracleClient.OracleDataAdapter>.</span><span class="sxs-lookup"><span data-stu-id="8a564-109">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbDataReader> and a <xref:System.Data.Common.DbDataAdapter> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbDataReader> and an <xref:System.Data.OleDb.OleDbDataAdapter> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlDataReader> and a <xref:System.Data.SqlClient.SqlDataAdapter> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcDataReader> and an <xref:System.Data.Odbc.OdbcDataAdapter> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleDataReader> and an <xref:System.Data.OracleClient.OracleDataAdapter> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8a564-110">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="8a564-110">In This Section</span></span>  
 [<span data-ttu-id="8a564-111">Извлечение данных с помощью объекта DataReader</span><span class="sxs-lookup"><span data-stu-id="8a564-111">Retrieving Data Using a DataReader</span></span>](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md)  
 <span data-ttu-id="8a564-112">Описание объекта ADO.NET **DataReader** объект и способ его использования для возврата потока результатов из источника данных.</span><span class="sxs-lookup"><span data-stu-id="8a564-112">Describes the ADO.NET **DataReader** object and how to use it to return a stream of results from a data source.</span></span>  
  
 [<span data-ttu-id="8a564-113">Заполнение набора данных с помощью адаптера данных DataAdapter</span><span class="sxs-lookup"><span data-stu-id="8a564-113">Populating a DataSet from a DataAdapter</span></span>](../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 <span data-ttu-id="8a564-114">Содержит описание того, как заполнить `DataSet` таблицами, столбцами и строками с использованием `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="8a564-114">Describes how to fill a `DataSet` with tables, columns, and rows by using a `DataAdapter`.</span></span>  
  
 [<span data-ttu-id="8a564-115">Параметры DataAdapter</span><span class="sxs-lookup"><span data-stu-id="8a564-115">DataAdapter Parameters</span></span>](../../../../docs/framework/data/adonet/dataadapter-parameters.md)  
 <span data-ttu-id="8a564-116">Показывает, как использовать параметры со свойствами команды `DataAdapter`, включая то, как сопоставить содержимое столбца в `DataSet` с параметром команды.</span><span class="sxs-lookup"><span data-stu-id="8a564-116">Describes how to use parameters with the command properties of a `DataAdapter` including how to map the contents of a column in a `DataSet` to a command parameter.</span></span>  
  
 [<span data-ttu-id="8a564-117">Добавление существующих ограничений к набору данных</span><span class="sxs-lookup"><span data-stu-id="8a564-117">Adding Existing Constraints to a DataSet</span></span>](../../../../docs/framework/data/adonet/adding-existing-constraints-to-a-dataset.md)  
 <span data-ttu-id="8a564-118">Показывает, как добавить существующие ограничения к `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="8a564-118">Describes how to add existing constraints to a `DataSet`.</span></span>  
  
 [<span data-ttu-id="8a564-119">Сопоставления DataAdapter, DataTable и DataColumn</span><span class="sxs-lookup"><span data-stu-id="8a564-119">DataAdapter DataTable and DataColumn Mappings</span></span>](../../../../docs/framework/data/adonet/dataadapter-datatable-and-datacolumn-mappings.md)  
 <span data-ttu-id="8a564-120">Описывает, как задать `DataTableMappings` и `ColumnMappings` для `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="8a564-120">Describes how to set up `DataTableMappings` and `ColumnMappings` for a `DataAdapter`.</span></span>  
  
 [<span data-ttu-id="8a564-121">Разбивка на страницы результатов запроса</span><span class="sxs-lookup"><span data-stu-id="8a564-121">Paging Through a Query Result</span></span>](../../../../docs/framework/data/adonet/paging-through-a-query-result.md)  
 <span data-ttu-id="8a564-122">Предоставляет пример просмотра результатов запроса в виде страниц данных.</span><span class="sxs-lookup"><span data-stu-id="8a564-122">Provides an example of viewing the results of a query as pages of data.</span></span>  
  
 [<span data-ttu-id="8a564-123">Обновление источников данных с объектами DataAdapter</span><span class="sxs-lookup"><span data-stu-id="8a564-123">Updating Data Sources with DataAdapters</span></span>](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 <span data-ttu-id="8a564-124">Описывает, как использовать `DataAdapter` для решения задачи записи изменений в `DataSet` обратно в базу данных.</span><span class="sxs-lookup"><span data-stu-id="8a564-124">Describes how to use a `DataAdapter` to resolve changes in a `DataSet` back to the database.</span></span>  
  
 [<span data-ttu-id="8a564-125">Обработка событий DataAdapter</span><span class="sxs-lookup"><span data-stu-id="8a564-125">Handling DataAdapter Events</span></span>](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)  
 <span data-ttu-id="8a564-126">Описывает события `DataAdapter` и способы их использования.</span><span class="sxs-lookup"><span data-stu-id="8a564-126">Describes `DataAdapter` events and how to use them.</span></span>  
  
 [<span data-ttu-id="8a564-127">Выполнение пакетных операций с использованием объектов DataAdapter</span><span class="sxs-lookup"><span data-stu-id="8a564-127">Performing Batch Operations Using DataAdapters</span></span>](../../../../docs/framework/data/adonet/performing-batch-operations-using-dataadapters.md)  
 <span data-ttu-id="8a564-128">Показывает, как повысить производительность приложения путем уменьшения количества циклов обмена данными с SQL Server в ходе применения обновлений из `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="8a564-128">Describes enhancing application performance by reducing the number of round trips to SQL Server when applying updates from the `DataSet`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a564-129">См. также</span><span class="sxs-lookup"><span data-stu-id="8a564-129">See Also</span></span>  
 [<span data-ttu-id="8a564-130">Подключение к источнику данных</span><span class="sxs-lookup"><span data-stu-id="8a564-130">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [<span data-ttu-id="8a564-131">Команды и параметры</span><span class="sxs-lookup"><span data-stu-id="8a564-131">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="8a564-132">Транзакции и параллельность</span><span class="sxs-lookup"><span data-stu-id="8a564-132">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [<span data-ttu-id="8a564-133">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="8a564-133">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="8a564-134">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8a564-134">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
