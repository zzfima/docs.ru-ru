---
title: Подключение к источнику данных в ADO.NET
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: c04624be758e4bc7c8b1981ad6a9dc44430d62b5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083716"
---
# <a name="connecting-to-a-data-source-in-adonet"></a><span data-ttu-id="d7837-102">Подключение к источнику данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d7837-102">Connecting to a Data Source in ADO.NET</span></span>
<span data-ttu-id="d7837-103">В ADO.NET используется **подключения** объекта для подключения к определенному источнику данных, указав необходимые данные для аутентификации в строке подключения.</span><span class="sxs-lookup"><span data-stu-id="d7837-103">In ADO.NET you use a **Connection** object to connect to a specific data source by supplying necessary authentication information in a connection string.</span></span> <span data-ttu-id="d7837-104">**Подключения** объектом, который используется зависит от типа источника данных.</span><span class="sxs-lookup"><span data-stu-id="d7837-104">The **Connection** object you use depends on the type of data source.</span></span>  
  
 <span data-ttu-id="d7837-105">Каждый поставщик данных .NET Framework, входящий в состав .NET Framework, включает объект <xref:System.Data.Common.DbConnection>: поставщик данных .NET Framework для OLE DB содержит объект <xref:System.Data.OleDb.OleDbConnection>, поставщик данных .NET Framework для SQL Server содержит объект <xref:System.Data.SqlClient.SqlConnection>, поставщик данных .NET Framework для ODBC содержит объект <xref:System.Data.Odbc.OdbcConnection>, поставщик данных .NET Framework для Oracle содержит объект <xref:System.Data.OracleClient.OracleConnection>.</span><span class="sxs-lookup"><span data-stu-id="d7837-105">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbConnection> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbConnection> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlConnection> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcConnection> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleConnection> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d7837-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="d7837-106">In This Section</span></span>  
 [<span data-ttu-id="d7837-107">Установка подключения</span><span class="sxs-lookup"><span data-stu-id="d7837-107">Establishing the Connection</span></span>](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 <span data-ttu-id="d7837-108">Описывает использование **подключения** объектов для установления соединения с источником данных.</span><span class="sxs-lookup"><span data-stu-id="d7837-108">Describes how to use a **Connection** object to establish a connection to a data source.</span></span>  
  
 [<span data-ttu-id="d7837-109">События подключения</span><span class="sxs-lookup"><span data-stu-id="d7837-109">Connection Events</span></span>](../../../../docs/framework/data/adonet/connection-events.md)  
 <span data-ttu-id="d7837-110">Описывает использование **InfoMessage** событий для получения информационных сообщений из источника данных.</span><span class="sxs-lookup"><span data-stu-id="d7837-110">Describes how to use an **InfoMessage** event to retrieve informational messages from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7837-111">См. также</span><span class="sxs-lookup"><span data-stu-id="d7837-111">See also</span></span>

- [<span data-ttu-id="d7837-112">Строки подключения</span><span class="sxs-lookup"><span data-stu-id="d7837-112">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)
- [<span data-ttu-id="d7837-113">Объединение подключений в пул</span><span class="sxs-lookup"><span data-stu-id="d7837-113">Connection Pooling</span></span>](../../../../docs/framework/data/adonet/connection-pooling.md)
- [<span data-ttu-id="d7837-114">Команды и параметры</span><span class="sxs-lookup"><span data-stu-id="d7837-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="d7837-115">Объекты DataAdapter и DataReader</span><span class="sxs-lookup"><span data-stu-id="d7837-115">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [<span data-ttu-id="d7837-116">Транзакции и параллельность</span><span class="sxs-lookup"><span data-stu-id="d7837-116">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)
- [<span data-ttu-id="d7837-117">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d7837-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
