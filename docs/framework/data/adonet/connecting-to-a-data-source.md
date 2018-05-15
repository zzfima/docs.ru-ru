---
title: Подключение к источнику данных в ADO.NET
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: 27653c3e1f14e08fc8b5e1225a441072778a0cc8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="connecting-to-a-data-source-in-adonet"></a><span data-ttu-id="6520c-102">Подключение к источнику данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6520c-102">Connecting to a Data Source in ADO.NET</span></span>
<span data-ttu-id="6520c-103">В ADO.NET используется **подключения** для подключения к определенному источнику данных путем передачи сведений о необходимости проверки подлинности в строке подключения.</span><span class="sxs-lookup"><span data-stu-id="6520c-103">In ADO.NET you use a **Connection** object to connect to a specific data source by supplying necessary authentication information in a connection string.</span></span> <span data-ttu-id="6520c-104">**Подключения** использовании объект зависит от типа источника данных.</span><span class="sxs-lookup"><span data-stu-id="6520c-104">The **Connection** object you use depends on the type of data source.</span></span>  
  
 <span data-ttu-id="6520c-105">Каждый поставщик данных .NET Framework, входящий в состав .NET Framework, включает объект <xref:System.Data.Common.DbConnection>: поставщик данных .NET Framework для OLE DB содержит объект <xref:System.Data.OleDb.OleDbConnection>, поставщик данных .NET Framework для SQL Server содержит объект <xref:System.Data.SqlClient.SqlConnection>, поставщик данных .NET Framework для ODBC содержит объект <xref:System.Data.Odbc.OdbcConnection>, поставщик данных .NET Framework для Oracle содержит объект <xref:System.Data.OracleClient.OracleConnection>.</span><span class="sxs-lookup"><span data-stu-id="6520c-105">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbConnection> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbConnection> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlConnection> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcConnection> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleConnection> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6520c-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="6520c-106">In This Section</span></span>  
 [<span data-ttu-id="6520c-107">Установка подключения</span><span class="sxs-lookup"><span data-stu-id="6520c-107">Establishing the Connection</span></span>](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 <span data-ttu-id="6520c-108">Описывает использование **подключения** объектов для установления соединения с источником данных.</span><span class="sxs-lookup"><span data-stu-id="6520c-108">Describes how to use a **Connection** object to establish a connection to a data source.</span></span>  
  
 [<span data-ttu-id="6520c-109">События подключения</span><span class="sxs-lookup"><span data-stu-id="6520c-109">Connection Events</span></span>](../../../../docs/framework/data/adonet/connection-events.md)  
 <span data-ttu-id="6520c-110">Описывает использование **InfoMessage** событий для получения информационных сообщений из источника данных.</span><span class="sxs-lookup"><span data-stu-id="6520c-110">Describes how to use an **InfoMessage** event to retrieve informational messages from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6520c-111">См. также</span><span class="sxs-lookup"><span data-stu-id="6520c-111">See Also</span></span>  
 [<span data-ttu-id="6520c-112">Строки подключения</span><span class="sxs-lookup"><span data-stu-id="6520c-112">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)  
 [<span data-ttu-id="6520c-113">Объединение подключений в пул</span><span class="sxs-lookup"><span data-stu-id="6520c-113">Connection Pooling</span></span>](../../../../docs/framework/data/adonet/connection-pooling.md)  
 [<span data-ttu-id="6520c-114">Команды и параметры</span><span class="sxs-lookup"><span data-stu-id="6520c-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="6520c-115">Объекты DataAdapter и DataReader</span><span class="sxs-lookup"><span data-stu-id="6520c-115">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="6520c-116">Транзакции и параллельность</span><span class="sxs-lookup"><span data-stu-id="6520c-116">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [<span data-ttu-id="6520c-117">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6520c-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
