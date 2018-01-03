---
title: "Извлечение и изменение данных в ADO.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 722e7f87-3691-46c6-87e8-7d159722d675
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 4ea157cd52bf92dace924baaa40f5b1bba6f13a6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="retrieving-and-modifying-data-in-adonet"></a><span data-ttu-id="ce889-102">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ce889-102">Retrieving and Modifying Data in ADO.NET</span></span>
<span data-ttu-id="ce889-103">Основной функцией любого приложения базы данных является соединение с источником данных и извлечение данных, которые он содержит.</span><span class="sxs-lookup"><span data-stu-id="ce889-103">A primary function of any database application is connecting to a data source and retrieving the data that it contains.</span></span> <span data-ttu-id="ce889-104">Поставщики данных .NET Framework для ADO.NET служат в качестве моста между приложением и источником данных, что позволяет выполнять команды и получать данные с помощью **DataReader** или **DataAdapter** .</span><span class="sxs-lookup"><span data-stu-id="ce889-104">The .NET Framework data providers of ADO.NET serve as a bridge between an application and a data source, allowing you to execute commands as well as to retrieve data by using a **DataReader** or a **DataAdapter**.</span></span> <span data-ttu-id="ce889-105">Ключевой функцией любого приложения базы данных является возможность обновления данных, хранимых в базе данных.</span><span class="sxs-lookup"><span data-stu-id="ce889-105">A key function of any database application is the ability to update the data that is stored in the database.</span></span> <span data-ttu-id="ce889-106">В ADO.NET обновление данных включает использование **DataAdapter** и <xref:System.Data.DataSet>, и **команда** объектов; может также включать использование транзакций.</span><span class="sxs-lookup"><span data-stu-id="ce889-106">In ADO.NET, updating data involves using the **DataAdapter** and <xref:System.Data.DataSet>, and **Command** objects; and it may also involve using transactions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ce889-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="ce889-107">In This Section</span></span>  
 [<span data-ttu-id="ce889-108">Подключение к источнику данных</span><span class="sxs-lookup"><span data-stu-id="ce889-108">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 <span data-ttu-id="ce889-109">Описывается установка подключения к источнику данных и работа с событиями подключения.</span><span class="sxs-lookup"><span data-stu-id="ce889-109">Describes how to establish a connection to a data source and how to work with connection events.</span></span>  
  
 [<span data-ttu-id="ce889-110">Строки подключения</span><span class="sxs-lookup"><span data-stu-id="ce889-110">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)  
 <span data-ttu-id="ce889-111">Содержит разделы, в которых описываются различные аспекты использования строк подключения, в том числе ключевых слов строки подключения, сведения о безопасности, их хранение и извлечение.</span><span class="sxs-lookup"><span data-stu-id="ce889-111">Contains topics describing various aspects of using connection strings, including connection string keywords, security info, and storing and retrieving them.</span></span>  
  
 [<span data-ttu-id="ce889-112">Объединение подключений в пул</span><span class="sxs-lookup"><span data-stu-id="ce889-112">Connection Pooling</span></span>](../../../../docs/framework/data/adonet/connection-pooling.md)  
 <span data-ttu-id="ce889-113">Описывает пул соединений для поставщиков данных платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ce889-113">Describes connection pooling for the .NET Framework data providers.</span></span>  
  
 [<span data-ttu-id="ce889-114">Команды и параметры</span><span class="sxs-lookup"><span data-stu-id="ce889-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 <span data-ttu-id="ce889-115">Содержит разделы, в которых описывается создание команд и построителей команд, настройка параметров и выполнение команд для извлечения и изменения данных.</span><span class="sxs-lookup"><span data-stu-id="ce889-115">Contains topics describing how to create commands and command builders, configure parameters, and how to execute commands to retrieve and modify data.</span></span>  
  
 [<span data-ttu-id="ce889-116">Объекты DataAdapter и DataReader</span><span class="sxs-lookup"><span data-stu-id="ce889-116">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 <span data-ttu-id="ce889-117">Содержит разделы, в которых описываются объекты DataReader, DataAdapter, параметры, обработка событий объекта и выполнение пакетных операций.</span><span class="sxs-lookup"><span data-stu-id="ce889-117">Contains topics describing DataReaders, DataAdapters, parameters, handling DataAdapter events and performing batch operations.</span></span>  
  
 [<span data-ttu-id="ce889-118">Транзакции и параллельность</span><span class="sxs-lookup"><span data-stu-id="ce889-118">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 <span data-ttu-id="ce889-119">Содержит разделы, в которых описывается выполнение локальных транзакций, распределенных транзакций и работа с оптимистичным параллелизмом.</span><span class="sxs-lookup"><span data-stu-id="ce889-119">Contains topics describing how to perform local transactions, distributed transactions, and work with optimistic concurrency.</span></span>  
  
 [<span data-ttu-id="ce889-120">Извлечение идентификации или значений автонумерации</span><span class="sxs-lookup"><span data-stu-id="ce889-120">Retrieving Identity or Autonumber Values</span></span>](../../../../docs/framework/data/adonet/retrieving-identity-or-autonumber-values.md)  
 <span data-ttu-id="ce889-121">Пример сопоставления значений, созданных для **удостоверение** столбца в [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] таблицы или для **Autonumber** в таблицы Microsoft Access, со столбцом вставленной строки в таблице.</span><span class="sxs-lookup"><span data-stu-id="ce889-121">Provides an example of mapping the values generated for an **identity** column in a [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] table or for an **Autonumber** field in a Microsoft Access table, to a column of an inserted row in a table.</span></span> <span data-ttu-id="ce889-122">Рассматривается слияние значений идентификаторов в объекте `DataTable`.</span><span class="sxs-lookup"><span data-stu-id="ce889-122">Discusses merging identity values in a `DataTable`.</span></span>  
  
 [<span data-ttu-id="ce889-123">Извлечение двоичных данных</span><span class="sxs-lookup"><span data-stu-id="ce889-123">Retrieving Binary Data</span></span>](../../../../docs/framework/data/adonet/retrieving-binary-data.md)  
 <span data-ttu-id="ce889-124">Описывается извлечение двоичных данных или крупных структур данных с помощью `CommandBehavior`.`SequentialAccess`</span><span class="sxs-lookup"><span data-stu-id="ce889-124">Describes how to retrieve binary data or large data structures using `CommandBehavior`.`SequentialAccess`</span></span> <span data-ttu-id="ce889-125">для изменения поведения по умолчанию `DataReader`.</span><span class="sxs-lookup"><span data-stu-id="ce889-125">to modify the default behavior of a `DataReader`.</span></span>  
  
 [<span data-ttu-id="ce889-126">Изменение данных с помощью хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="ce889-126">Modifying Data with Stored Procedures</span></span>](../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)  
 <span data-ttu-id="ce889-127">Описывается использование входных и выходных параметров хранимой процедуры для вставки строки в базу данных с возвратом нового значения идентификатора.</span><span class="sxs-lookup"><span data-stu-id="ce889-127">Describes how to use stored procedure input parameters and output parameters to insert a row in a database, returning a new identity value.</span></span>  
  
 [<span data-ttu-id="ce889-128">Извлечение сведений о схеме базы данных</span><span class="sxs-lookup"><span data-stu-id="ce889-128">Retrieving Database Schema Information</span></span>](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 <span data-ttu-id="ce889-129">Описывает получение доступных баз данных или каталогов, таблиц и представлений базы данных, существующих ограничений для таблиц и других сведений о схеме из источника данных.</span><span class="sxs-lookup"><span data-stu-id="ce889-129">Describes how to obtain available databases or catalogs, tables and views in a database, constraints that exist for tables, and other schema information from a data source.</span></span>  
  
 [<span data-ttu-id="ce889-130">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="ce889-130">DbProviderFactories</span></span>](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 <span data-ttu-id="ce889-131">Описывается модель фабрики поставщика и демонстрируется использование базовых классов в пространстве имен `System.Data.Common`.</span><span class="sxs-lookup"><span data-stu-id="ce889-131">Describes the provider factory model and demonstrates how to use the base classes in the `System.Data.Common` namespace.</span></span>  
  
 [<span data-ttu-id="ce889-132">Трассировка данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ce889-132">Data Tracing in ADO.NET</span></span>](../../../../docs/framework/data/adonet/data-tracing.md)  
 <span data-ttu-id="ce889-133">Описывается, как в ADO.NET реализованы встроенные функции трассировки данных.</span><span class="sxs-lookup"><span data-stu-id="ce889-133">Describes how ADO.NET provides built-in data tracing functionality.</span></span>  
  
 [<span data-ttu-id="ce889-134">Счетчики производительности</span><span class="sxs-lookup"><span data-stu-id="ce889-134">Performance Counters</span></span>](../../../../docs/framework/data/adonet/performance-counters.md)  
 <span data-ttu-id="ce889-135">Описываются счетчики производительности, доступные для `SqlClient` и `OracleClient`.</span><span class="sxs-lookup"><span data-stu-id="ce889-135">Describes performance counters available for `SqlClient` and `OracleClient`.</span></span>  
  
 [<span data-ttu-id="ce889-136">Асинхронное программирование</span><span class="sxs-lookup"><span data-stu-id="ce889-136">Asynchronous Programming</span></span>](../../../../docs/framework/data/adonet/asynchronous-programming.md)  
 <span data-ttu-id="ce889-137">Описывает поддержку [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] для асинхронного программирования.</span><span class="sxs-lookup"><span data-stu-id="ce889-137">Describes [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] support for asynchronous programming.</span></span>  
  
 [<span data-ttu-id="ce889-138">Поддержка потоковой передачи SqlClient</span><span class="sxs-lookup"><span data-stu-id="ce889-138">SqlClient Streaming Support</span></span>](../../../../docs/framework/data/adonet/sqlclient-streaming-support.md)  
 <span data-ttu-id="ce889-139">Описывает, как создавать приложения с потоком данных из [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] без полной загрузки в память.</span><span class="sxs-lookup"><span data-stu-id="ce889-139">Discusses how to write applications that stream data from [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] without having it fully loaded in memory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce889-140">См. также</span><span class="sxs-lookup"><span data-stu-id="ce889-140">See Also</span></span>  
 [<span data-ttu-id="ce889-141">Сопоставления типов данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ce889-141">Data Type Mappings in ADO.NET</span></span>](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)  
 [<span data-ttu-id="ce889-142">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="ce889-142">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="ce889-143">Защита приложений ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ce889-143">Securing ADO.NET Applications</span></span>](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="ce889-144">SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ce889-144">SQL Server and ADO.NET</span></span>](../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="ce889-145">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ce889-145">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
