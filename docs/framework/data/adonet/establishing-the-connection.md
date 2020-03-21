---
title: Установка подключения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3af512f3-87d9-4005-9e2f-abb1060ff43f
ms.openlocfilehash: 4606ecb370b7e85cf5ebd92754471f5253321251
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149665"
---
# <a name="establishing-the-connection"></a><span data-ttu-id="1f685-102">Установка подключения</span><span class="sxs-lookup"><span data-stu-id="1f685-102">Establishing the Connection</span></span>
<span data-ttu-id="1f685-103">Для создания соединения с Microsoft SQL Server используется объект <xref:System.Data.SqlClient.SqlConnection> поставщика данных .NET Framework для SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1f685-103">To connect to Microsoft SQL Server, use the <xref:System.Data.SqlClient.SqlConnection> object of the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="1f685-104">Для соединения с источником данных OLE DB используется объект <xref:System.Data.OleDb.OleDbConnection> поставщика данных .NET Framework для OLE DB.</span><span class="sxs-lookup"><span data-stu-id="1f685-104">To connect to an OLE DB data source, use the <xref:System.Data.OleDb.OleDbConnection> object of the .NET Framework Data Provider for OLE DB.</span></span> <span data-ttu-id="1f685-105">Для соединения с источником данных используется объект <xref:System.Data.Odbc.OdbcConnection> поставщика данных .NET Framework для ODBC.</span><span class="sxs-lookup"><span data-stu-id="1f685-105">To connect to an ODBC data source, use the <xref:System.Data.Odbc.OdbcConnection> object of the .NET Framework Data Provider for ODBC.</span></span> <span data-ttu-id="1f685-106">Для соединения с источником данных Oracle используется объект <xref:System.Data.OracleClient.OracleConnection> поставщика данных .NET Framework для Oracle.</span><span class="sxs-lookup"><span data-stu-id="1f685-106">To connect to an Oracle data source, use the <xref:System.Data.OracleClient.OracleConnection> object of the .NET Framework Data Provider for Oracle.</span></span> <span data-ttu-id="1f685-107">Для надежного хранения и извлечения строк соединения [см.](protecting-connection-information.md)</span><span class="sxs-lookup"><span data-stu-id="1f685-107">For securely storing and retrieving connection strings, see [Protecting Connection Information](protecting-connection-information.md).</span></span>  
  
## <a name="closing-connections"></a><span data-ttu-id="1f685-108">Закрытие соединений</span><span class="sxs-lookup"><span data-stu-id="1f685-108">Closing Connections</span></span>  
 <span data-ttu-id="1f685-109">Рекомендуется всегда закрывать соединение после использования, чтобы обеспечить его возврат в пул.</span><span class="sxs-lookup"><span data-stu-id="1f685-109">We recommend that you always close the connection when you are finished using it, so that the connection can be returned to the pool.</span></span> <span data-ttu-id="1f685-110">Блок `Using` в Visual Basic или C# автоматически удаляет соединение при выходе в коде из блока даже при наличии необработанного исключения.</span><span class="sxs-lookup"><span data-stu-id="1f685-110">The `Using` block in Visual Basic or C# automatically disposes of the connection when the code exits the block, even in the case of an unhandled exception.</span></span> <span data-ttu-id="1f685-111">Для получения дополнительной информации можно [ознакомиться с использованием заявления](../../../csharp/language-reference/keywords/using-statement.md) и [с помощью заявления.](../../../visual-basic/language-reference/statements/using-statement.md)</span><span class="sxs-lookup"><span data-stu-id="1f685-111">See [using Statement](../../../csharp/language-reference/keywords/using-statement.md) and [Using Statement](../../../visual-basic/language-reference/statements/using-statement.md) for more information.</span></span>  
  
 <span data-ttu-id="1f685-112">Также можно использовать методы `Close` или `Dispose` объекта соединения для используемого поставщика.</span><span class="sxs-lookup"><span data-stu-id="1f685-112">You can also use the `Close` or `Dispose` methods of the connection object for the provider that you are using.</span></span> <span data-ttu-id="1f685-113">Соединения, которые явно не закрыты, нельзя добавить или вернуть в пул.</span><span class="sxs-lookup"><span data-stu-id="1f685-113">Connections that are not explicitly closed might not be added or returned to the pool.</span></span> <span data-ttu-id="1f685-114">Например, соединение, которое вышло за пределы области, но явно закрыто не было, будет возвращено в пул соединений только в том случае, если был достигнут максимальный размер этого пула, а соединение еще действует.</span><span class="sxs-lookup"><span data-stu-id="1f685-114">For example, a connection that has gone out of scope but that has not been explicitly closed will only be returned to the connection pool if the maximum pool size has been reached and the connection is still valid.</span></span> <span data-ttu-id="1f685-115">Для получения дополнительной [информации см.](ole-db-odbc-and-oracle-connection-pooling.md)</span><span class="sxs-lookup"><span data-stu-id="1f685-115">For more information, see [OLE DB, ODBC, and Oracle Connection Pooling](ole-db-odbc-and-oracle-connection-pooling.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1f685-116">`Close` Не вызывайте `Dispose` или на **соединение,** **DataReader**, или `Finalize` любой другой управляемый объект в методе вашего класса.</span><span class="sxs-lookup"><span data-stu-id="1f685-116">Do not call `Close` or `Dispose` on a **Connection**, a **DataReader**, or any other managed object in the `Finalize` method of your class.</span></span> <span data-ttu-id="1f685-117">В методе завершения следует только освобождать неуправляемые ресурсы, которыми ваш класс непосредственно владеет.</span><span class="sxs-lookup"><span data-stu-id="1f685-117">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="1f685-118">Если класс не владеет какими-либо неуправляемыми ресурсами, не включайте в его определение метод `Finalize`.</span><span class="sxs-lookup"><span data-stu-id="1f685-118">If your class does not own any unmanaged resources, do not include a `Finalize` method in your class definition.</span></span> <span data-ttu-id="1f685-119">Для получения дополнительной информации, см [Мусорная коллекция](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="1f685-119">For more information, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1f685-120">События входа в систему и выхода из системы не вызываются на сервере при выборке подключения из пула подключений и при возврате его в пул подключений, поскольку при возврате в пул подключений подключение фактически не закрывается.</span><span class="sxs-lookup"><span data-stu-id="1f685-120">Login and logout events will not be raised on the server when a connection is fetched from or returned to the connection pool, because the connection is not actually closed when it is returned to the connection pool.</span></span> <span data-ttu-id="1f685-121">Дополнительные сведения см. в разделе [Объединение подключений в пул в SQL Server (ADO.NET)](sql-server-connection-pooling.md).</span><span class="sxs-lookup"><span data-stu-id="1f685-121">For more information, see [SQL Server Connection Pooling (ADO.NET)](sql-server-connection-pooling.md).</span></span>  
  
## <a name="connecting-to-sql-server"></a><span data-ttu-id="1f685-122">Подключение к SQL Server</span><span class="sxs-lookup"><span data-stu-id="1f685-122">Connecting to SQL Server</span></span>  
 <span data-ttu-id="1f685-123">Поставщик данных .NET Framework для SQL Server поддерживает формат строки соединения, аналогичный формату строки соединения OLE DB (ADO).</span><span class="sxs-lookup"><span data-stu-id="1f685-123">The .NET Framework Data Provider for SQL Server supports a connection string format that is similar to the OLE DB (ADO) connection string format.</span></span> <span data-ttu-id="1f685-124">Сведения о допустимых именах и значениях формата строки см. в свойстве <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> объекта <xref:System.Data.SqlClient.SqlConnection>.</span><span class="sxs-lookup"><span data-stu-id="1f685-124">For valid string format names and values, see the <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> property of the <xref:System.Data.SqlClient.SqlConnection> object.</span></span> <span data-ttu-id="1f685-125">Можно также использовать класс <xref:System.Data.SqlClient.SqlConnectionStringBuilder> для создания синтаксически правильных строк соединения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="1f685-125">You can also use the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> class to create syntactically valid connection strings at run time.</span></span> <span data-ttu-id="1f685-126">Дополнительные сведения см. в статье [Connection String Builders](connection-string-builders.md) (Построители строк подключения).</span><span class="sxs-lookup"><span data-stu-id="1f685-126">For more information, see [Connection String Builders](connection-string-builders.md).</span></span>  
  
 <span data-ttu-id="1f685-127">В следующем примере кода демонстрируется способ создания и открытия соединения с базой данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1f685-127">The following code example demonstrates how to create and open a connection to a SQL Server database.</span></span>  
  
```vb  
' Assumes connectionString is a valid connection string.  
Using connection As New SqlConnection(connectionString)  
    connection.Open()  
    ' Do work here.  
End Using  
```  
  
```csharp  
// Assumes connectionString is a valid connection string.  
using (SqlConnection connection = new SqlConnection(connectionString))  
{  
    connection.Open();  
    // Do work here.  
}  
```  
  
### <a name="integrated-security-and-aspnet"></a><span data-ttu-id="1f685-128">Встроенная безопасность и ASP.NET</span><span class="sxs-lookup"><span data-stu-id="1f685-128">Integrated Security and ASP.NET</span></span>  
 <span data-ttu-id="1f685-129">Встроенная безопасность SQL Server (именуемая также доверительными соединениями) обеспечивает защиту при соединении с SQL Server, так как не отображает идентификатор пользователя и пароль в строке соединения, поэтому является рекомендуемым методом проверки подлинности соединения.</span><span class="sxs-lookup"><span data-stu-id="1f685-129">SQL Server integrated security (also known as trusted connections) helps to provide protection when connecting to SQL Server as it does not expose a user ID and password in the connection string and is the recommended method for authenticating a connection.</span></span> <span data-ttu-id="1f685-130">Встроенная безопасность основана на использовании текущего идентификатора безопасности, или маркера выполняемого процесса.</span><span class="sxs-lookup"><span data-stu-id="1f685-130">Integrated security uses the current security identity, or token, of the executing process.</span></span> <span data-ttu-id="1f685-131">В приложениях рабочего стола, как правило, используется идентификатор текущего, вошедшего в систему пользователя.</span><span class="sxs-lookup"><span data-stu-id="1f685-131">For desktop applications, this is typically the identity of the currently logged-on user.</span></span>  
  
 <span data-ttu-id="1f685-132">Идентификатор безопасности приложений ASP.NET может быть настроен на получение одного из нескольких различных параметров.</span><span class="sxs-lookup"><span data-stu-id="1f685-132">The security identity for ASP.NET applications can be set to one of several different options.</span></span> <span data-ttu-id="1f685-133">Чтобы лучше понять идентификатор безопасности, который приложение ASP.NET использует при подключении к серверу S'L, см. [ASP.NET олицетворение,](https://docs.microsoft.com/previous-versions/aspnet/xh507fc5(v=vs.100))ASP.NET [аутентификация,](https://docs.microsoft.com/previous-versions/aspnet/eeyk640h(v=vs.100))и [Как: Доступ к серверу S'L с помощью интегрированной безопасности Windows.](https://docs.microsoft.com/previous-versions/aspnet/bsz5788z(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1f685-133">To better understand the security identity that an ASP.NET application uses when connecting to SQL Server, see [ASP.NET Impersonation](https://docs.microsoft.com/previous-versions/aspnet/xh507fc5(v=vs.100)), [ASP.NET Authentication](https://docs.microsoft.com/previous-versions/aspnet/eeyk640h(v=vs.100)), and [How to: Access SQL Server Using Windows Integrated Security](https://docs.microsoft.com/previous-versions/aspnet/bsz5788z(v=vs.100)).</span></span>  
  
## <a name="connecting-to-an-ole-db-data-source"></a><span data-ttu-id="1f685-134">Соединение с источником данных OLE DB</span><span class="sxs-lookup"><span data-stu-id="1f685-134">Connecting to an OLE DB Data Source</span></span>  
 <span data-ttu-id="1f685-135">Поставщик рамочных данных .NET для OLE DB обеспечивает подключение к источникам данных, подвергаемым воздействию OLE DB (через СЛОЛОЛЕДЕБ, поставщика OLE DB для сервера S'L), с использованием объекта **OleDbConnection.**</span><span class="sxs-lookup"><span data-stu-id="1f685-135">The .NET Framework Data Provider for OLE DB provides connectivity to data sources exposed using OLE DB (through SQLOLEDB, the OLE DB Provider for SQL Server), using the **OleDbConnection** object.</span></span>  
  
 <span data-ttu-id="1f685-136">Формат строки соединения поставщика данных .NET Framework для OLE DB идентичен формату строки соединения, используемому в ADO, за исключением следующего.</span><span class="sxs-lookup"><span data-stu-id="1f685-136">For the .NET Framework Data Provider for OLE DB, the connection string format is identical to the connection string format used in ADO, with the following exceptions:</span></span>  
  
- <span data-ttu-id="1f685-137">Требуется ключевое слово **Поставщика.**</span><span class="sxs-lookup"><span data-stu-id="1f685-137">The **Provider** keyword is required.</span></span>  
  
- <span data-ttu-id="1f685-138">**URL,** **удаленный провайдер**и ключевые слова **удаленного сервера** не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="1f685-138">The **URL**, **Remote Provider**, and **Remote Server** keywords are not supported.</span></span>  
  
 <span data-ttu-id="1f685-139">Дополнительные сведения о строках соединения OLE DB см. в разделе <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A>.</span><span class="sxs-lookup"><span data-stu-id="1f685-139">For more information about OLE DB connection strings, see the <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A> topic.</span></span> <span data-ttu-id="1f685-140">Построитель <xref:System.Data.OleDb.OleDbConnectionStringBuilder> также используется для создания строк соединения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="1f685-140">You can also use the <xref:System.Data.OleDb.OleDbConnectionStringBuilder> to create connection strings at run time.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1f685-141">Объект **OleDbConnection** не поддерживает настройку или получение динамических свойств, характерных для поставщика OLE DB.</span><span class="sxs-lookup"><span data-stu-id="1f685-141">The **OleDbConnection** object does not support setting or retrieving dynamic properties specific to an OLE DB provider.</span></span> <span data-ttu-id="1f685-142">Поддерживаются только те свойства, которые можно передать в строке соединения поставщику OLE DB.</span><span class="sxs-lookup"><span data-stu-id="1f685-142">Only properties that can be passed in the connection string for the OLE DB provider are supported.</span></span>  
  
 <span data-ttu-id="1f685-143">В следующем примере кода демонстрируется способ создания и открытия соединения с источником данных OLE DB.</span><span class="sxs-lookup"><span data-stu-id="1f685-143">The following code example demonstrates how to create and open a connection to an OLE DB data source.</span></span>  
  
```vb  
' Assumes connectionString is a valid connection string.  
Using connection As New OleDbConnection(connectionString)  
    connection.Open()  
    ' Do work here.  
End Using  
```  
  
```csharp  
// Assumes connectionString is a valid connection string.  
using (OleDbConnection connection =
  new OleDbConnection(connectionString))  
{  
    connection.Open();  
    // Do work here.  
}  
```  
  
## <a name="do-not-use-universal-data-link-files"></a><span data-ttu-id="1f685-144">Отказ от использования файлов в формате UDL</span><span class="sxs-lookup"><span data-stu-id="1f685-144">Do Not Use Universal Data Link Files</span></span>  
 <span data-ttu-id="1f685-145">Можно предоставить информацию о подключении к **OleDbConnection** в файле Универсальной ссылки данных (UDL); однако вы должны избегать этого.</span><span class="sxs-lookup"><span data-stu-id="1f685-145">It is possible to supply connection information for an **OleDbConnection** in a Universal Data Link (UDL) file; however you should avoid doing so.</span></span> <span data-ttu-id="1f685-146">UDL-файлы не подвергаются шифрованию, и строки соединения хранятся в них в виде простого текста.</span><span class="sxs-lookup"><span data-stu-id="1f685-146">UDL files are not encrypted, and expose connection string information in clear text.</span></span> <span data-ttu-id="1f685-147">Так как UDL-файл представляет собой внешний файловый ресурс для приложения, его нельзя защитить средствами .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1f685-147">Because a UDL file is an external file-based resource to your application, it cannot be secured using the .NET Framework.</span></span>  
  
## <a name="connecting-to-an-odbc-data-source"></a><span data-ttu-id="1f685-148">Соединение с источником данных ODBC</span><span class="sxs-lookup"><span data-stu-id="1f685-148">Connecting to an ODBC Data Source</span></span>  
 <span data-ttu-id="1f685-149">Поставщик рамочных данных .NET для ODBC обеспечивает подключение к источникам данных, подвергаемым воздействию ODBC с помощью объекта **OdbcConnection.**</span><span class="sxs-lookup"><span data-stu-id="1f685-149">The .NET Framework Data Provider for ODBC provides connectivity to data sources exposed using ODBC using the **OdbcConnection** object.</span></span>  
  
 <span data-ttu-id="1f685-150">Формат строки соединения поставщика данных .NET Framework для ODBC создан с учетом настолько полного согласования с форматом строки соединения ODBC, насколько это возможно.</span><span class="sxs-lookup"><span data-stu-id="1f685-150">For the .NET Framework Data Provider for ODBC, the connection string format is designed to match the ODBC connection string format as closely as possible.</span></span> <span data-ttu-id="1f685-151">Также можно указать имя источника данных ODBC (DSN).</span><span class="sxs-lookup"><span data-stu-id="1f685-151">You may also supply an ODBC data source name (DSN).</span></span> <span data-ttu-id="1f685-152">Для получения более подробной информации <xref:System.Data.Odbc.OdbcConnection>о **OdbcConnection** , см.</span><span class="sxs-lookup"><span data-stu-id="1f685-152">For more detail on the **OdbcConnection** , see the <xref:System.Data.Odbc.OdbcConnection>.</span></span>  
  
 <span data-ttu-id="1f685-153">В следующем примере кода демонстрируется способ создания и открытия соединения с источником данных ODBC.</span><span class="sxs-lookup"><span data-stu-id="1f685-153">The following code example demonstrates how to create and open a connection to an ODBC data source.</span></span>  
  
```vb  
' Assumes connectionString is a valid connection string.  
Using connection As New OdbcConnection(connectionString)  
    connection.Open()  
    ' Do work here.  
End Using  
```  
  
```csharp  
// Assumes connectionString is a valid connection string.  
using (OdbcConnection connection =
  new OdbcConnection(connectionString))  
{  
    connection.Open();  
    // Do work here.  
}  
```  
  
## <a name="connecting-to-an-oracle-data-source"></a><span data-ttu-id="1f685-154">Соединение с источником данных Oracle</span><span class="sxs-lookup"><span data-stu-id="1f685-154">Connecting to an Oracle Data Source</span></span>  
 <span data-ttu-id="1f685-155">Поставщик рамочных данных .NET для Oracle обеспечивает подключение к источникам данных Oracle с помощью объекта **OracleConnection.**</span><span class="sxs-lookup"><span data-stu-id="1f685-155">The .NET Framework Data Provider for Oracle provides connectivity to Oracle data sources using the **OracleConnection** object.</span></span>  
  
 <span data-ttu-id="1f685-156">Формат строки соединения поставщика данных .NET Framework для Oracle создан с учетом настолько полного согласования с форматом строки соединения поставщика OLE DB для Oracle (MSDAORA), насколько это возможно.</span><span class="sxs-lookup"><span data-stu-id="1f685-156">For the .NET Framework Data Provider for Oracle, the connection string format is designed to match the OLE DB Provider for Oracle (MSDAORA) connection string format as closely as possible.</span></span> <span data-ttu-id="1f685-157">Для получения более подробной информации о **OracleConnection**, см. <xref:System.Data.OracleClient.OracleConnection></span><span class="sxs-lookup"><span data-stu-id="1f685-157">For more detail on the **OracleConnection**, see the <xref:System.Data.OracleClient.OracleConnection>.</span></span>  
  
 <span data-ttu-id="1f685-158">В следующем примере кода демонстрируется способ создания и открытия соединения с источником данных Oracle.</span><span class="sxs-lookup"><span data-stu-id="1f685-158">The following code example demonstrates how to create and open a connection to an Oracle data source.</span></span>  
  
```vb  
' Assumes connectionString is a valid connection string.  
Using connection As New OracleConnection(connectionString)  
    connection.Open()  
    ' Do work here.  
End Using  
```  
  
```csharp  
// Assumes connectionString is a valid connection string.  
using (OracleConnection connection =
  new OracleConnection(connectionString))  
{  
    connection.Open();  
    // Do work here.  
}  
OracleConnection nwindConn = new OracleConnection("Data Source=MyOracleServer;Integrated Security=yes;");  
nwindConn.Open();  
```  
  
## <a name="see-also"></a><span data-ttu-id="1f685-159">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1f685-159">See also</span></span>

- [<span data-ttu-id="1f685-160">Подключение к источнику данных</span><span class="sxs-lookup"><span data-stu-id="1f685-160">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)
- [<span data-ttu-id="1f685-161">Строки подключения</span><span class="sxs-lookup"><span data-stu-id="1f685-161">Connection Strings</span></span>](connection-strings.md)
- [<span data-ttu-id="1f685-162">Организация пулов соединений OLE DB, ODBC и Oracle</span><span class="sxs-lookup"><span data-stu-id="1f685-162">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](ole-db-odbc-and-oracle-connection-pooling.md)
- [<span data-ttu-id="1f685-163">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1f685-163">ADO.NET Overview</span></span>](ado-net-overview.md)
