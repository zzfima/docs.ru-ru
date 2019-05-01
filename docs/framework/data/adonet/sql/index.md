---
title: SQL Server и ADO.NET
ms.date: 03/30/2017
ms.assetid: c18b1fb1-2af1-4de7-80a4-95e56fd976cb
ms.openlocfilehash: f30d9d715a2d94deee788f92cfc8eed0cba706de
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033895"
---
# <a name="sql-server-and-adonet"></a><span data-ttu-id="01c17-102">SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="01c17-102">SQL Server and ADO.NET</span></span>
<span data-ttu-id="01c17-103">В данном разделе описываются возможности и поведение, характерное для поставщика данных .NET Framework для SQL Server (<xref:System.Data.SqlClient>).</span><span class="sxs-lookup"><span data-stu-id="01c17-103">This section describes features and behaviors that are specific to the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>).</span></span>  
  
 <span data-ttu-id="01c17-104">Объект <xref:System.Data.SqlClient> предоставляет доступ к версиям SQL Server и инкапсулирует протоколы для конкретных баз данных.</span><span class="sxs-lookup"><span data-stu-id="01c17-104"><xref:System.Data.SqlClient> provides access to versions of SQL Server, which encapsulates database-specific protocols.</span></span> <span data-ttu-id="01c17-105">Возможности поставщика данных похожи на возможности поставщиков данных .NET Framework для OLE DB, ODBC и Oracle.</span><span class="sxs-lookup"><span data-stu-id="01c17-105">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for OLE DB, ODBC, and Oracle.</span></span> <span data-ttu-id="01c17-106">Объект <xref:System.Data.SqlClient> включает средство синтаксического анализа потока табличных данных, которое служит для непосредственного взаимодействия с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="01c17-106"><xref:System.Data.SqlClient> includes a tabular data stream (TDS) parser to communicate directly with SQL Server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="01c17-107">Чтобы использовать поставщик данных .NET Framework для SQL Server, приложение должно ссылаться на пространство имен <xref:System.Data.SqlClient>.</span><span class="sxs-lookup"><span data-stu-id="01c17-107">To use the .NET Framework Data Provider for SQL Server, an application must reference the <xref:System.Data.SqlClient> namespace.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="01c17-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="01c17-108">In This Section</span></span>  
 [<span data-ttu-id="01c17-109">Безопасность SQL Server</span><span class="sxs-lookup"><span data-stu-id="01c17-109">SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 <span data-ttu-id="01c17-110">Приводятся общие сведения о возможностях системы безопасности SQL Server, а также сценарии для создания безопасных приложений ADO.NET, предназначенных для работы с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="01c17-110">Provides an overview of SQL Server security features, and application scenarios for creating secure ADO.NET applications that target SQL Server.</span></span>  
  
 [<span data-ttu-id="01c17-111">Типы данных SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="01c17-111">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 <span data-ttu-id="01c17-112">Описывается работа с типами данных SQL Server и их взаимодействие с типами данных .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="01c17-112">Describes how to work with SQL Server data types and how they interact with .NET Framework data types.</span></span>  
  
 [<span data-ttu-id="01c17-113">Двоичные данные и данные большого объема SQL Server</span><span class="sxs-lookup"><span data-stu-id="01c17-113">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 <span data-ttu-id="01c17-114">Описывается работа в SQL Server с данными большого размера.</span><span class="sxs-lookup"><span data-stu-id="01c17-114">Describes how to work with large value data in SQL Server.</span></span>  
  
 [<span data-ttu-id="01c17-115">Операции данных SQL Server Data в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="01c17-115">SQL Server Data Operations in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 <span data-ttu-id="01c17-116">Описание работы с данными в SQL Server.</span><span class="sxs-lookup"><span data-stu-id="01c17-116">Describes how to work with data in SQL Server.</span></span> <span data-ttu-id="01c17-117">Содержит разделы, посвященные операциям массового копирования, MARS, асинхронным операциям и возвращающим табличное значение параметрам.</span><span class="sxs-lookup"><span data-stu-id="01c17-117">Contains sections about bulk copy operations, MARS, asynchronous operations, and table-valued parameters.</span></span>  
  
 [<span data-ttu-id="01c17-118">Возможности SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="01c17-118">SQL Server Features and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-features-and-adonet.md)  
 <span data-ttu-id="01c17-119">Описываются возможности SQL Server, полезные для разработчиков приложений ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="01c17-119">Describes SQL Server features that are useful for ADO.NET application developers.</span></span>  
  
 [<span data-ttu-id="01c17-120">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="01c17-120">LINQ to SQL</span></span>](../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 <span data-ttu-id="01c17-121">Описываются основные стандартные блоки, процессы и методы, необходимые для создания приложений по технологии LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="01c17-121">Describes the basic building blocks, processes, and techniques required for creating LINQ to SQL applications.</span></span>  
  
 <span data-ttu-id="01c17-122">Полную документацию по ядру СУБД SQL Server см. в электронной документации по SQL Server для используемой версии SQL Server.</span><span class="sxs-lookup"><span data-stu-id="01c17-122">For complete documentation of the SQL Server Database Engine, see SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 [<span data-ttu-id="01c17-123">Электронная документация по SQL Server</span><span class="sxs-lookup"><span data-stu-id="01c17-123">SQL Server Books Online</span></span>](/sql/sql-server/sql-server-technical-documentation)  
  
## <a name="see-also"></a><span data-ttu-id="01c17-124">См. также</span><span class="sxs-lookup"><span data-stu-id="01c17-124">See also</span></span>

- [<span data-ttu-id="01c17-125">Защита приложений ADO.NET</span><span class="sxs-lookup"><span data-stu-id="01c17-125">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [<span data-ttu-id="01c17-126">Сопоставления типов данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="01c17-126">Data Type Mappings in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)
- [<span data-ttu-id="01c17-127">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="01c17-127">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="01c17-128">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="01c17-128">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="01c17-129">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="01c17-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
