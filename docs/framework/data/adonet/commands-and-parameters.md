---
title: "Команды и параметры"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b623f810-d871-49a5-b0f5-078cc3c34db6
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: f28f4ed728ee429a691a0a19b3fc143ac0e832ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="commands-and-parameters"></a><span data-ttu-id="265ee-102">Команды и параметры</span><span class="sxs-lookup"><span data-stu-id="265ee-102">Commands and Parameters</span></span>
<span data-ttu-id="265ee-103">После установки соединения с источником данных при помощи объекта <xref:System.Data.Common.DbCommand> можно выполнять команды и возвращать результаты из источника данных.</span><span class="sxs-lookup"><span data-stu-id="265ee-103">After establishing a connection to a data source, you can execute commands and return results from the data source using a <xref:System.Data.Common.DbCommand> object.</span></span> <span data-ttu-id="265ee-104">Команду можно создать с помощью одного из используемых конструкторов команд для поставщика данных .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="265ee-104">You can create a command using one of the command constructors for the .NET Framework data provider you are working with.</span></span> <span data-ttu-id="265ee-105">Конструкторы могут принимать необязательные аргументы, например инструкцию SQL для выполнения в источнике данных, объект <xref:System.Data.Common.DbConnection> или объект <xref:System.Data.Common.DbTransaction>.</span><span class="sxs-lookup"><span data-stu-id="265ee-105">Constructors can take optional arguments, such as an SQL statement to execute at the data source, a <xref:System.Data.Common.DbConnection> object, or a <xref:System.Data.Common.DbTransaction> object.</span></span> <span data-ttu-id="265ee-106">Эти объекты также можно настроить как свойства команды.</span><span class="sxs-lookup"><span data-stu-id="265ee-106">You can also configure those objects as properties of the command.</span></span> <span data-ttu-id="265ee-107">При помощи метода <xref:System.Data.Common.DbConnection.CreateCommand%2A> объекта `DbConnection` также можно создать команду для конкретного соединения.</span><span class="sxs-lookup"><span data-stu-id="265ee-107">You can also create a command for a particular connection using the <xref:System.Data.Common.DbConnection.CreateCommand%2A> method of a `DbConnection` object.</span></span> <span data-ttu-id="265ee-108">Инструкцию SQL, выполняемую командой, можно настроить с помощью свойства <xref:System.Data.Common.DbCommand.CommandText%2A>.</span><span class="sxs-lookup"><span data-stu-id="265ee-108">The SQL statement being executed by the command can be configured using the <xref:System.Data.Common.DbCommand.CommandText%2A> property.</span></span>  
  
 <span data-ttu-id="265ee-109">У каждого поставщика данных .NET Framework, имеющегося в платформе .NET Framework, есть объект `Command`.</span><span class="sxs-lookup"><span data-stu-id="265ee-109">Each .NET Framework data provider included with the .NET Framework has a `Command` object.</span></span> <span data-ttu-id="265ee-110">Поставщик данных .NET Framework для OLE DB содержит объект <xref:System.Data.OleDb.OleDbCommand>, поставщик данных .NET Framework для SQL Server - объект <xref:System.Data.SqlClient.SqlCommand>, поставщик данных .NET Framework для ODBC - объект <xref:System.Data.Odbc.OdbcCommand>, а поставщик данных .NET Framework для Oracle - объект <xref:System.Data.OracleClient.OracleCommand>.</span><span class="sxs-lookup"><span data-stu-id="265ee-110">The .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbCommand> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlCommand> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcCommand> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleCommand> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="265ee-111">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="265ee-111">In This Section</span></span>  
 [<span data-ttu-id="265ee-112">Выполнение команды</span><span class="sxs-lookup"><span data-stu-id="265ee-112">Executing a Command</span></span>](../../../../docs/framework/data/adonet/executing-a-command.md)  
 <span data-ttu-id="265ee-113">Описание объекта ADO.NET `Command` и его использования для выполнения запросов и команд в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="265ee-113">Describes the ADO.NET `Command` object and how to use it to execute queries and commands against a data source.</span></span>  
  
 [<span data-ttu-id="265ee-114">Настройка параметров и типы данных параметров</span><span class="sxs-lookup"><span data-stu-id="265ee-114">Configuring Parameters and Parameter Data Types</span></span>](../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 <span data-ttu-id="265ee-115">Описание работы с параметрами `Command`, включая направление, типы данных и синтаксис параметров.</span><span class="sxs-lookup"><span data-stu-id="265ee-115">Describes working with `Command` parameters, including direction, data types, and parameter syntax.</span></span>  
  
 [<span data-ttu-id="265ee-116">Создание команд с помощью построителей CommandBuilder</span><span class="sxs-lookup"><span data-stu-id="265ee-116">Generating Commands with CommandBuilders</span></span>](../../../../docs/framework/data/adonet/generating-commands-with-commandbuilders.md)  
 <span data-ttu-id="265ee-117">Описание использования построителей команд для автоматического формирования команд INSERT, UPDATE и DELETE для адаптера `DataAdapter`, у которого имеется команда SELECT с одной таблицей.</span><span class="sxs-lookup"><span data-stu-id="265ee-117">Describes how to use command builders to automatically generate INSERT, UPDATE, and DELETE commands for a `DataAdapter` that has a single-table SELECT command.</span></span>  
  
 [<span data-ttu-id="265ee-118">Получение одного значения из базы данных</span><span class="sxs-lookup"><span data-stu-id="265ee-118">Obtaining a Single Value from a Database</span></span>](../../../../docs/framework/data/adonet/obtaining-a-single-value-from-a-database.md)  
 <span data-ttu-id="265ee-119">Описывается использование метода `ExecuteScalar` объекта `Command` для возврата из запроса к базе данных одиночного значения.</span><span class="sxs-lookup"><span data-stu-id="265ee-119">Describes how to use the `ExecuteScalar` method of a `Command` object to return a single value from a database query.</span></span>  
  
 [<span data-ttu-id="265ee-120">Использование команд для изменения данных</span><span class="sxs-lookup"><span data-stu-id="265ee-120">Using Commands to Modify Data</span></span>](../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)  
 <span data-ttu-id="265ee-121">Описывается использование поставщика данных для выполнения хранимых процедур или инструкций языка описания данных DDL.</span><span class="sxs-lookup"><span data-stu-id="265ee-121">Describes how to use a data provider to execute stored procedures or data definition language (DDL) statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="265ee-122">См. также</span><span class="sxs-lookup"><span data-stu-id="265ee-122">See Also</span></span>  
 [<span data-ttu-id="265ee-123">Объекты DataAdapter и DataReader</span><span class="sxs-lookup"><span data-stu-id="265ee-123">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="265ee-124">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="265ee-124">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="265ee-125">Подключение к источнику данных</span><span class="sxs-lookup"><span data-stu-id="265ee-125">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [<span data-ttu-id="265ee-126">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="265ee-126">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
