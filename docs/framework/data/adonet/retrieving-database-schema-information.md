---
title: Извлечение сведений о схеме базы данных
ms.date: 03/30/2017
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
ms.openlocfilehash: 00cf0e36dd7886897c26adf50102f32892ebb18e
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43772845"
---
# <a name="retrieving-database-schema-information"></a><span data-ttu-id="bb610-102">Извлечение сведений о схеме базы данных</span><span class="sxs-lookup"><span data-stu-id="bb610-102">Retrieving Database Schema Information</span></span>
<span data-ttu-id="bb610-103">Получение сведений о схеме из базы данных выполняется с помощью процесса обнаружения схемы.</span><span class="sxs-lookup"><span data-stu-id="bb610-103">Obtaining schema information from a database is accomplished with the process of schema discovery.</span></span> <span data-ttu-id="bb610-104">Обнаружение схемы позволяет приложениям запрашивать, что управляемые поставщики для поиска и возвращения сведений о схеме базы данных, также называется *метаданных*, конкретной базы данных.</span><span class="sxs-lookup"><span data-stu-id="bb610-104">Schema discovery allows applications to request that managed providers find and return information about the database schema, also known as *metadata*, of a given database.</span></span> <span data-ttu-id="bb610-105">Различные элементы схемы базы данных, например таблицы, столбцы и хранимые процедуры, предоставляются через коллекции схем.</span><span class="sxs-lookup"><span data-stu-id="bb610-105">Different database schema elements such as tables, columns, and stored-procedures are exposed through schema collections.</span></span> <span data-ttu-id="bb610-106">Каждая коллекция схемы в зависимости от используемого поставщика содержит различные сведения о схеме.</span><span class="sxs-lookup"><span data-stu-id="bb610-106">Each schema collection contains a variety of schema information specific to the provider being used.</span></span>  
  
 <span data-ttu-id="bb610-107">Каждый из управляемых поставщиков .NET Framework реализуют **GetSchema** метод в **подключения** класс и сведения схемы, которые возвращаются из **GetSchema**метод поставляется в виде <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="bb610-107">Each of the .NET Framework managed providers implement the **GetSchema** method in the **Connection** class, and the schema information that is returned from the **GetSchema** method comes in the form of a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="bb610-108">**GetSchema** это перегруженный метод, содержащий необязательные параметры для указания возвращаемой коллекции схем и ограничения объема возвращаемых сведений.</span><span class="sxs-lookup"><span data-stu-id="bb610-108">The **GetSchema** method is an overloaded method that provides optional parameters for specifying the schema collection to return, and restricting the amount of information returned.</span></span>  
  
 <span data-ttu-id="bb610-109">Поставщики данных .NET Framework для OLE DB, ODBC, Oracle и SqlClient предоставляют **GetSchemaTable** метод, возвращающий объект DataTable, описывающий метаданные столбца **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="bb610-109">The .NET Framework Data Providers for OLE DB, ODBC, Oracle, and SqlClient provide a **GetSchemaTable** method that returns a DataTable describing the column metadata of the **DataReader**.</span></span>  
  
 <span data-ttu-id="bb610-110">Поставщик данных .NET Framework для OLE DB также предоставляет данные схемы с помощью метода <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> объекта <xref:System.Data.OleDb.OleDbConnection>.</span><span class="sxs-lookup"><span data-stu-id="bb610-110">The .NET Framework Data Provider for OLE DB also exposes schema information by using the <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> method of the <xref:System.Data.OleDb.OleDbConnection> object.</span></span> <span data-ttu-id="bb610-111">Как аргументы **GetOleDbSchemaTable** принимает <xref:System.Data.OleDb.OleDbSchemaGuid> , идентифицирующий возвращаемые данные схемы, и массив ограничений, накладываемых на возвращаемые столбцы.</span><span class="sxs-lookup"><span data-stu-id="bb610-111">As arguments, **GetOleDbSchemaTable** takes an <xref:System.Data.OleDb.OleDbSchemaGuid> that identifies the schema information to return, and an array of restrictions on those returned columns.</span></span> <span data-ttu-id="bb610-112">**GetOleDbSchemaTable** возвращает <xref:System.Data.DataTable> заполненный запрошенными сведениями схемы.</span><span class="sxs-lookup"><span data-stu-id="bb610-112">**GetOleDbSchemaTable** returns a <xref:System.Data.DataTable> populated with the requested schema information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bb610-113">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="bb610-113">In This Section</span></span>  
 [<span data-ttu-id="bb610-114">Коллекции GetSchema и Schema</span><span class="sxs-lookup"><span data-stu-id="bb610-114">GetSchema and Schema Collections</span></span>](../../../../docs/framework/data/adonet/getschema-and-schema-collections.md)  
 <span data-ttu-id="bb610-115">Описывает **GetSchema** метод и как его можно использовать для получения и ограничения сведений о схеме из базы данных.</span><span class="sxs-lookup"><span data-stu-id="bb610-115">Describes the **GetSchema** method and how it can be used to retrieve and restrict schema information from a database.</span></span>  
  
 <span data-ttu-id="bb610-116">Ограничения схемы</span><span class="sxs-lookup"><span data-stu-id="bb610-116">Schema Restrictions</span></span>  
 <span data-ttu-id="bb610-117">Описываются ограничения схемы, которые могут использоваться с **GetSchema**.</span><span class="sxs-lookup"><span data-stu-id="bb610-117">Describes schema restrictions that can be used with **GetSchema**.</span></span>  
  
 [<span data-ttu-id="bb610-118">Общие коллекции схемы</span><span class="sxs-lookup"><span data-stu-id="bb610-118">Common Schema Collections</span></span>](../../../../docs/framework/data/adonet/common-schema-collections.md)  
 <span data-ttu-id="bb610-119">Описывает стандартные коллекции схем, поддерживаемые всеми управляемыми поставщиками .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bb610-119">Describes all of the common schema collections supported by all of the .NET Framework managed providers.</span></span>  
  
 [<span data-ttu-id="bb610-120">Коллекции схемы SQL Server</span><span class="sxs-lookup"><span data-stu-id="bb610-120">SQL Server Schema Collections</span></span>](../../../../docs/framework/data/adonet/sql-server-schema-collections.md)  
 <span data-ttu-id="bb610-121">Описывается коллекция схем, поддерживаемая поставщиком .NET Framework для SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bb610-121">Describes the schema collection supported by the .NET Framework provider for SQL Server.</span></span>  
  
 [<span data-ttu-id="bb610-122">Коллекции схемы Oracle</span><span class="sxs-lookup"><span data-stu-id="bb610-122">Oracle Schema Collections</span></span>](../../../../docs/framework/data/adonet/oracle-schema-collections.md)  
 <span data-ttu-id="bb610-123">Описывается коллекция схем, поддерживаемая поставщиком .NET Framework для Oracle.</span><span class="sxs-lookup"><span data-stu-id="bb610-123">Describes the schema collection supported by the .NET Framework provider for Oracle.</span></span>  
  
 [<span data-ttu-id="bb610-124">Коллекции схемы ODBC</span><span class="sxs-lookup"><span data-stu-id="bb610-124">ODBC Schema Collections</span></span>](../../../../docs/framework/data/adonet/odbc-schema-collections.md)  
 <span data-ttu-id="bb610-125">Описываются коллекции схем для драйверов ODBC.</span><span class="sxs-lookup"><span data-stu-id="bb610-125">Describes the schema collections for ODBC drivers.</span></span>  
  
 [<span data-ttu-id="bb610-126">Коллекции схемы OLE DB</span><span class="sxs-lookup"><span data-stu-id="bb610-126">OLE DB Schema Collections</span></span>](../../../../docs/framework/data/adonet/ole-db-schema-collections.md)  
 <span data-ttu-id="bb610-127">Описываются коллекции схем для поставщиков OLE DB.</span><span class="sxs-lookup"><span data-stu-id="bb610-127">Describes the schema collections for OLE DB providers.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="bb610-128">Ссылка</span><span class="sxs-lookup"><span data-stu-id="bb610-128">Reference</span></span>  
 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 <span data-ttu-id="bb610-129">Описывает **GetSchema** метод <xref:System.Data.Common.DbConnection> класса.</span><span class="sxs-lookup"><span data-stu-id="bb610-129">Describes the **GetSchema** method of the <xref:System.Data.Common.DbConnection> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 <span data-ttu-id="bb610-130">Описывает **GetSchema** метод <xref:System.Data.Odbc.OdbcConnection> класса.</span><span class="sxs-lookup"><span data-stu-id="bb610-130">Describes the **GetSchema** method of the <xref:System.Data.Odbc.OdbcConnection> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 <span data-ttu-id="bb610-131">Описывает **GetSchema** метод <xref:System.Data.OleDb.OleDbConnection> класса.</span><span class="sxs-lookup"><span data-stu-id="bb610-131">Describes the **GetSchema** method of the <xref:System.Data.OleDb.OleDbConnection> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 <span data-ttu-id="bb610-132">Описывает **GetSchema** метод <xref:System.Data.OracleClient.OracleConnection> класса.</span><span class="sxs-lookup"><span data-stu-id="bb610-132">Describes the **GetSchema** method of the <xref:System.Data.OracleClient.OracleConnection> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 <span data-ttu-id="bb610-133">Описывает **GetSchema** метод <xref:System.Data.SqlClient.SqlConnection> класса.</span><span class="sxs-lookup"><span data-stu-id="bb610-133">Describes the **GetSchema** method of the <xref:System.Data.SqlClient.SqlConnection> class.</span></span>  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="bb610-134">Описывает **GetSchemaTable** метод <xref:System.Data.Common.DbDataReader> класса.</span><span class="sxs-lookup"><span data-stu-id="bb610-134">Describes the **GetSchemaTable** method of the <xref:System.Data.Common.DbDataReader> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="bb610-135">Описывает **GetSchemaTable** метод <xref:System.Data.Odbc.OdbcDataReader> класса.</span><span class="sxs-lookup"><span data-stu-id="bb610-135">Describes the **GetSchemaTable** method of the <xref:System.Data.Odbc.OdbcDataReader> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="bb610-136">Описывает **GetSchemaTable** метод <xref:System.Data.OleDb.OleDbDataReader> класса.</span><span class="sxs-lookup"><span data-stu-id="bb610-136">Describes the **GetSchemaTable** method of the <xref:System.Data.OleDb.OleDbDataReader> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="bb610-137">Описывает **GetSchemaTable** метод <xref:System.Data.OracleClient.OracleDataReader> класса.</span><span class="sxs-lookup"><span data-stu-id="bb610-137">Describes the **GetSchemaTable** method of the <xref:System.Data.OracleClient.OracleDataReader> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="bb610-138">Описывает **GetSchemaTable** метод <xref:System.Data.SqlClient.SqlDataReader> класса.</span><span class="sxs-lookup"><span data-stu-id="bb610-138">Describes the **GetSchemaTable** method of the <xref:System.Data.SqlClient.SqlDataReader> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb610-139">См. также</span><span class="sxs-lookup"><span data-stu-id="bb610-139">See Also</span></span>  
 [<span data-ttu-id="bb610-140">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bb610-140">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="bb610-141">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bb610-141">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
