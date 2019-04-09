---
title: SQL Server и ADO.NET
ms.date: 03/30/2017
ms.assetid: c18b1fb1-2af1-4de7-80a4-95e56fd976cb
ms.openlocfilehash: f30d9d715a2d94deee788f92cfc8eed0cba706de
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59172774"
---
# <a name="sql-server-and-adonet"></a><span data-ttu-id="7fbb5-102">SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7fbb5-102">SQL Server and ADO.NET</span></span>
<span data-ttu-id="7fbb5-103">В данном разделе описываются возможности и поведение, характерное для поставщика данных .NET Framework для SQL Server (<xref:System.Data.SqlClient>).</span><span class="sxs-lookup"><span data-stu-id="7fbb5-103">This section describes features and behaviors that are specific to the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>).</span></span>  
  
 <xref:System.Data.SqlClient> <span data-ttu-id="7fbb5-104">предоставляет доступ к версиям SQL Server, который инкапсулирует протоколы для конкретной базы данных.</span><span class="sxs-lookup"><span data-stu-id="7fbb5-104">provides access to versions of SQL Server, which encapsulates database-specific protocols.</span></span> <span data-ttu-id="7fbb5-105">Возможности поставщика данных похожи на возможности поставщиков данных .NET Framework для OLE DB, ODBC и Oracle.</span><span class="sxs-lookup"><span data-stu-id="7fbb5-105">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for OLE DB, ODBC, and Oracle.</span></span> <xref:System.Data.SqlClient> <span data-ttu-id="7fbb5-106">включает средство синтаксического анализа табличных данных stream (TDS) для взаимодействия непосредственно с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7fbb5-106">includes a tabular data stream (TDS) parser to communicate directly with SQL Server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7fbb5-107">Чтобы использовать поставщик данных .NET Framework для SQL Server, приложение должно ссылаться на пространство имен <xref:System.Data.SqlClient>.</span><span class="sxs-lookup"><span data-stu-id="7fbb5-107">To use the .NET Framework Data Provider for SQL Server, an application must reference the <xref:System.Data.SqlClient> namespace.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7fbb5-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="7fbb5-108">In This Section</span></span>  
 [<span data-ttu-id="7fbb5-109">Безопасность SQL Server</span><span class="sxs-lookup"><span data-stu-id="7fbb5-109">SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 <span data-ttu-id="7fbb5-110">Приводятся общие сведения о возможностях системы безопасности SQL Server, а также сценарии для создания безопасных приложений ADO.NET, предназначенных для работы с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7fbb5-110">Provides an overview of SQL Server security features, and application scenarios for creating secure ADO.NET applications that target SQL Server.</span></span>  
  
 [<span data-ttu-id="7fbb5-111">Типы данных SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7fbb5-111">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 <span data-ttu-id="7fbb5-112">Описывается работа с типами данных SQL Server и их взаимодействие с типами данных .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7fbb5-112">Describes how to work with SQL Server data types and how they interact with .NET Framework data types.</span></span>  
  
 [<span data-ttu-id="7fbb5-113">Двоичные данные и данные большого объема SQL Server</span><span class="sxs-lookup"><span data-stu-id="7fbb5-113">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 <span data-ttu-id="7fbb5-114">Описывается работа в SQL Server с данными большого размера.</span><span class="sxs-lookup"><span data-stu-id="7fbb5-114">Describes how to work with large value data in SQL Server.</span></span>  
  
 [<span data-ttu-id="7fbb5-115">Операции данных SQL Server Data в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7fbb5-115">SQL Server Data Operations in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 <span data-ttu-id="7fbb5-116">Описание работы с данными в SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7fbb5-116">Describes how to work with data in SQL Server.</span></span> <span data-ttu-id="7fbb5-117">Содержит разделы, посвященные операциям массового копирования, MARS, асинхронным операциям и возвращающим табличное значение параметрам.</span><span class="sxs-lookup"><span data-stu-id="7fbb5-117">Contains sections about bulk copy operations, MARS, asynchronous operations, and table-valued parameters.</span></span>  
  
 [<span data-ttu-id="7fbb5-118">Возможности SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7fbb5-118">SQL Server Features and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-features-and-adonet.md)  
 <span data-ttu-id="7fbb5-119">Описываются возможности SQL Server, полезные для разработчиков приложений ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="7fbb5-119">Describes SQL Server features that are useful for ADO.NET application developers.</span></span>  
  
 [<span data-ttu-id="7fbb5-120">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="7fbb5-120">LINQ to SQL</span></span>](../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 <span data-ttu-id="7fbb5-121">Описываются основные стандартные блоки, процессы и методы, необходимые для создания приложений по технологии LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="7fbb5-121">Describes the basic building blocks, processes, and techniques required for creating LINQ to SQL applications.</span></span>  
  
 <span data-ttu-id="7fbb5-122">Полную документацию по ядру СУБД SQL Server см. в электронной документации по SQL Server для используемой версии SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7fbb5-122">For complete documentation of the SQL Server Database Engine, see SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 [<span data-ttu-id="7fbb5-123">Электронная документация по SQL Server</span><span class="sxs-lookup"><span data-stu-id="7fbb5-123">SQL Server Books Online</span></span>](/sql/sql-server/sql-server-technical-documentation)  
  
## <a name="see-also"></a><span data-ttu-id="7fbb5-124">См. также</span><span class="sxs-lookup"><span data-stu-id="7fbb5-124">See also</span></span>

- [<span data-ttu-id="7fbb5-125">Защита приложений ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7fbb5-125">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [<span data-ttu-id="7fbb5-126">Сопоставления типов данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7fbb5-126">Data Type Mappings in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)
- [<span data-ttu-id="7fbb5-127">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="7fbb5-127">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="7fbb5-128">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7fbb5-128">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="7fbb5-129">Управляемые поставщики ADO.NET и центр разработчиков DataSet</span><span class="sxs-lookup"><span data-stu-id="7fbb5-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
