---
title: Извлечение и изменение данных
ms.date: 03/30/2017
ms.assetid: 722e7f87-3691-46c6-87e8-7d159722d675
ms.openlocfilehash: 65c373ecff004e219527754bf2e9cc56837dc305
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980058"
---
# <a name="retrieving-and-modifying-data-in-adonet"></a><span data-ttu-id="e9d7b-102">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e9d7b-102">Retrieving and Modifying Data in ADO.NET</span></span>
<span data-ttu-id="e9d7b-103">Основной функцией любого приложения базы данных является соединение с источником данных и извлечение данных, которые он содержит.</span><span class="sxs-lookup"><span data-stu-id="e9d7b-103">A primary function of any database application is connecting to a data source and retrieving the data that it contains.</span></span> <span data-ttu-id="e9d7b-104">.NET Framework поставщики данных ADO.NET служат мостом между приложением и источником данных, что позволяет выполнять команды, а также получать данные с помощью объекта **DataReader** или **DataAdapter**.</span><span class="sxs-lookup"><span data-stu-id="e9d7b-104">The .NET Framework data providers of ADO.NET serve as a bridge between an application and a data source, allowing you to execute commands as well as to retrieve data by using a **DataReader** or a **DataAdapter**.</span></span> <span data-ttu-id="e9d7b-105">Ключевой функцией любого приложения базы данных является возможность обновления данных, хранимых в базе данных.</span><span class="sxs-lookup"><span data-stu-id="e9d7b-105">A key function of any database application is the ability to update the data that is stored in the database.</span></span> <span data-ttu-id="e9d7b-106">В ADO.NET обновление данных включает использование **DataAdapter** и <xref:System.Data.DataSet>, а также **командных** объектов. Он также может использовать транзакции.</span><span class="sxs-lookup"><span data-stu-id="e9d7b-106">In ADO.NET, updating data involves using the **DataAdapter** and <xref:System.Data.DataSet>, and **Command** objects; and it may also involve using transactions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e9d7b-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="e9d7b-107">In This Section</span></span>  
 [<span data-ttu-id="e9d7b-108">Подключение к источнику данных</span><span class="sxs-lookup"><span data-stu-id="e9d7b-108">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)  
 <span data-ttu-id="e9d7b-109">Описывается установка подключения к источнику данных и работа с событиями подключения.</span><span class="sxs-lookup"><span data-stu-id="e9d7b-109">Describes how to establish a connection to a data source and how to work with connection events.</span></span>  
  
 [<span data-ttu-id="e9d7b-110">Строки подключения</span><span class="sxs-lookup"><span data-stu-id="e9d7b-110">Connection Strings</span></span>](connection-strings.md)  
 <span data-ttu-id="e9d7b-111">Содержит разделы, в которых описываются различные аспекты использования строк подключения, в том числе ключевых слов строки подключения, сведения о безопасности, их хранение и извлечение.</span><span class="sxs-lookup"><span data-stu-id="e9d7b-111">Contains topics describing various aspects of using connection strings, including connection string keywords, security info, and storing and retrieving them.</span></span>  
  
 [<span data-ttu-id="e9d7b-112">Объединение подключений в пул</span><span class="sxs-lookup"><span data-stu-id="e9d7b-112">Connection Pooling</span></span>](connection-pooling.md)  
 <span data-ttu-id="e9d7b-113">Описывает пул соединений для поставщиков данных платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e9d7b-113">Describes connection pooling for the .NET Framework data providers.</span></span>  
  
 [<span data-ttu-id="e9d7b-114">Команды и параметры</span><span class="sxs-lookup"><span data-stu-id="e9d7b-114">Commands and Parameters</span></span>](commands-and-parameters.md)  
 <span data-ttu-id="e9d7b-115">Содержит разделы, в которых описывается создание команд и построителей команд, настройка параметров и выполнение команд для извлечения и изменения данных.</span><span class="sxs-lookup"><span data-stu-id="e9d7b-115">Contains topics describing how to create commands and command builders, configure parameters, and how to execute commands to retrieve and modify data.</span></span>  
  
 [<span data-ttu-id="e9d7b-116">Объекты DataAdapter и DataReader</span><span class="sxs-lookup"><span data-stu-id="e9d7b-116">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)  
 <span data-ttu-id="e9d7b-117">Содержит разделы, в которых описываются объекты DataReader, DataAdapter, параметры, обработка событий объекта и выполнение пакетных операций.</span><span class="sxs-lookup"><span data-stu-id="e9d7b-117">Contains topics describing DataReaders, DataAdapters, parameters, handling DataAdapter events and performing batch operations.</span></span>  
  
 [<span data-ttu-id="e9d7b-118">Транзакции и параллельность</span><span class="sxs-lookup"><span data-stu-id="e9d7b-118">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)  
 <span data-ttu-id="e9d7b-119">Содержит разделы, в которых описывается выполнение локальных транзакций, распределенных транзакций и работа с оптимистичным параллелизмом.</span><span class="sxs-lookup"><span data-stu-id="e9d7b-119">Contains topics describing how to perform local transactions, distributed transactions, and work with optimistic concurrency.</span></span>  
  
 [<span data-ttu-id="e9d7b-120">Извлечение идентификации или значений автонумерации</span><span class="sxs-lookup"><span data-stu-id="e9d7b-120">Retrieving Identity or Autonumber Values</span></span>](retrieving-identity-or-autonumber-values.md)  
 <span data-ttu-id="e9d7b-121">Содержит пример сопоставления значений, созданных для столбца **идентификаторов** в таблице SQL Server или для поля **счетчика** в таблице Microsoft Access, со столбцом вставленной строки в таблице.</span><span class="sxs-lookup"><span data-stu-id="e9d7b-121">Provides an example of mapping the values generated for an **identity** column in a SQL Server table or for an **Autonumber** field in a Microsoft Access table, to a column of an inserted row in a table.</span></span> <span data-ttu-id="e9d7b-122">Рассматривается слияние значений идентификаторов в объекте `DataTable`.</span><span class="sxs-lookup"><span data-stu-id="e9d7b-122">Discusses merging identity values in a `DataTable`.</span></span>  
  
 [<span data-ttu-id="e9d7b-123">Извлечение двоичных данных</span><span class="sxs-lookup"><span data-stu-id="e9d7b-123">Retrieving Binary Data</span></span>](retrieving-binary-data.md)  
 <span data-ttu-id="e9d7b-124">Описывает, как получить двоичные данные или крупные структуры данных с помощью `CommandBehavior`.`SequentialAccess`</span><span class="sxs-lookup"><span data-stu-id="e9d7b-124">Describes how to retrieve binary data or large data structures using `CommandBehavior`.`SequentialAccess`</span></span> <span data-ttu-id="e9d7b-125">изменение поведения `DataReader`по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e9d7b-125">to modify the default behavior of a `DataReader`.</span></span>  
  
 [<span data-ttu-id="e9d7b-126">Изменение данных с помощью хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="e9d7b-126">Modifying Data with Stored Procedures</span></span>](modifying-data-with-stored-procedures.md)  
 <span data-ttu-id="e9d7b-127">Описывается использование входных и выходных параметров хранимой процедуры для вставки строки в базу данных с возвратом нового значения идентификатора.</span><span class="sxs-lookup"><span data-stu-id="e9d7b-127">Describes how to use stored procedure input parameters and output parameters to insert a row in a database, returning a new identity value.</span></span>  
  
 [<span data-ttu-id="e9d7b-128">Извлечение сведений о схеме базы данных</span><span class="sxs-lookup"><span data-stu-id="e9d7b-128">Retrieving Database Schema Information</span></span>](retrieving-database-schema-information.md)  
 <span data-ttu-id="e9d7b-129">Описывает получение доступных баз данных или каталогов, таблиц и представлений базы данных, существующих ограничений для таблиц и других сведений о схеме из источника данных.</span><span class="sxs-lookup"><span data-stu-id="e9d7b-129">Describes how to obtain available databases or catalogs, tables and views in a database, constraints that exist for tables, and other schema information from a data source.</span></span>  
  
 [<span data-ttu-id="e9d7b-130">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="e9d7b-130">DbProviderFactories</span></span>](dbproviderfactories.md)  
 <span data-ttu-id="e9d7b-131">Описывается модель фабрики поставщика и демонстрируется использование базовых классов в пространстве имен `System.Data.Common`.</span><span class="sxs-lookup"><span data-stu-id="e9d7b-131">Describes the provider factory model and demonstrates how to use the base classes in the `System.Data.Common` namespace.</span></span>  
  
 [<span data-ttu-id="e9d7b-132">Трассировка данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e9d7b-132">Data Tracing in ADO.NET</span></span>](data-tracing.md)  
 <span data-ttu-id="e9d7b-133">Описывается, как в ADO.NET реализованы встроенные функции трассировки данных.</span><span class="sxs-lookup"><span data-stu-id="e9d7b-133">Describes how ADO.NET provides built-in data tracing functionality.</span></span>  
  
 [<span data-ttu-id="e9d7b-134">Performance Counters</span><span class="sxs-lookup"><span data-stu-id="e9d7b-134">Performance Counters</span></span>](performance-counters.md)  
 <span data-ttu-id="e9d7b-135">Описываются счетчики производительности, доступные для `SqlClient` и `OracleClient`.</span><span class="sxs-lookup"><span data-stu-id="e9d7b-135">Describes performance counters available for `SqlClient` and `OracleClient`.</span></span>  
  
 [<span data-ttu-id="e9d7b-136">Асинхронное программирование</span><span class="sxs-lookup"><span data-stu-id="e9d7b-136">Asynchronous Programming</span></span>](asynchronous-programming.md)  
 <span data-ttu-id="e9d7b-137">Описывает поддержку ADO.NET для асинхронного программирования.</span><span class="sxs-lookup"><span data-stu-id="e9d7b-137">Describes ADO.NET support for asynchronous programming.</span></span>  
  
 [<span data-ttu-id="e9d7b-138">Поддержка потоковой передачи SqlClient</span><span class="sxs-lookup"><span data-stu-id="e9d7b-138">SqlClient Streaming Support</span></span>](sqlclient-streaming-support.md)  
 <span data-ttu-id="e9d7b-139">Описывает написание приложений, которые проводят потоковую передачу данных из SQL Server без полной загрузки в память.</span><span class="sxs-lookup"><span data-stu-id="e9d7b-139">Discusses how to write applications that stream data from SQL Server without having it fully loaded in memory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9d7b-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="e9d7b-140">See also</span></span>

- [<span data-ttu-id="e9d7b-141">Сопоставления типов данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e9d7b-141">Data Type Mappings in ADO.NET</span></span>](data-type-mappings-in-ado-net.md)
- [<span data-ttu-id="e9d7b-142">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="e9d7b-142">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)
- [<span data-ttu-id="e9d7b-143">Защита приложений ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e9d7b-143">Securing ADO.NET Applications</span></span>](securing-ado-net-applications.md)
- [<span data-ttu-id="e9d7b-144">SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e9d7b-144">SQL Server and ADO.NET</span></span>](./sql/index.md)
- [<span data-ttu-id="e9d7b-145">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e9d7b-145">ADO.NET Overview</span></span>](ado-net-overview.md)
