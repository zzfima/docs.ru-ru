---
title: Подключение к источнику данных
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: 84dc15c0965b7ac8209bd9115d611162e57d6dda
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980253"
---
# <a name="connecting-to-a-data-source-in-adonet"></a><span data-ttu-id="c40a4-102">Подключение к источнику данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c40a4-102">Connecting to a Data Source in ADO.NET</span></span>
<span data-ttu-id="c40a4-103">В ADO.NET для подключения к определенному источнику данных используется объект **соединения** путем предоставления необходимых сведений о проверке подлинности в строке подключения.</span><span class="sxs-lookup"><span data-stu-id="c40a4-103">In ADO.NET you use a **Connection** object to connect to a specific data source by supplying necessary authentication information in a connection string.</span></span> <span data-ttu-id="c40a4-104">Используемый объект **соединения** зависит от типа источника данных.</span><span class="sxs-lookup"><span data-stu-id="c40a4-104">The **Connection** object you use depends on the type of data source.</span></span>  
  
 <span data-ttu-id="c40a4-105">Каждый поставщик данных .NET Framework, входящий в состав .NET Framework, включает объект <xref:System.Data.Common.DbConnection>: поставщик данных .NET Framework для OLE DB содержит объект <xref:System.Data.OleDb.OleDbConnection>, поставщик данных .NET Framework для SQL Server содержит объект <xref:System.Data.SqlClient.SqlConnection>, поставщик данных .NET Framework для ODBC содержит объект <xref:System.Data.Odbc.OdbcConnection>, поставщик данных .NET Framework для Oracle содержит объект <xref:System.Data.OracleClient.OracleConnection>.</span><span class="sxs-lookup"><span data-stu-id="c40a4-105">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbConnection> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbConnection> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlConnection> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcConnection> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleConnection> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c40a4-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="c40a4-106">In This Section</span></span>  
 [<span data-ttu-id="c40a4-107">Установка подключения</span><span class="sxs-lookup"><span data-stu-id="c40a4-107">Establishing the Connection</span></span>](establishing-the-connection.md)  
 <span data-ttu-id="c40a4-108">Описывает использование объекта **Connection** для установления соединения с источником данных.</span><span class="sxs-lookup"><span data-stu-id="c40a4-108">Describes how to use a **Connection** object to establish a connection to a data source.</span></span>  
  
 [<span data-ttu-id="c40a4-109">События подключения</span><span class="sxs-lookup"><span data-stu-id="c40a4-109">Connection Events</span></span>](connection-events.md)  
 <span data-ttu-id="c40a4-110">Описывает использование события **InfoMessage** для получения информационных сообщений из источника данных.</span><span class="sxs-lookup"><span data-stu-id="c40a4-110">Describes how to use an **InfoMessage** event to retrieve informational messages from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c40a4-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="c40a4-111">See also</span></span>

- [<span data-ttu-id="c40a4-112">Строки подключения</span><span class="sxs-lookup"><span data-stu-id="c40a4-112">Connection Strings</span></span>](connection-strings.md)
- [<span data-ttu-id="c40a4-113">Объединение подключений в пул</span><span class="sxs-lookup"><span data-stu-id="c40a4-113">Connection Pooling</span></span>](connection-pooling.md)
- [<span data-ttu-id="c40a4-114">Команды и параметры</span><span class="sxs-lookup"><span data-stu-id="c40a4-114">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="c40a4-115">Объекты DataAdapter и DataReader</span><span class="sxs-lookup"><span data-stu-id="c40a4-115">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="c40a4-116">Транзакции и параллельность</span><span class="sxs-lookup"><span data-stu-id="c40a4-116">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)
- [<span data-ttu-id="c40a4-117">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c40a4-117">ADO.NET Overview</span></span>](ado-net-overview.md)
