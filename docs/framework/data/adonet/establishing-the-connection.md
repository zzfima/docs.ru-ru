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
# <a name="establishing-the-connection"></a>Установка подключения
Для создания соединения с Microsoft SQL Server используется объект <xref:System.Data.SqlClient.SqlConnection> поставщика данных .NET Framework для SQL Server. Для соединения с источником данных OLE DB используется объект <xref:System.Data.OleDb.OleDbConnection> поставщика данных .NET Framework для OLE DB. Для соединения с источником данных используется объект <xref:System.Data.Odbc.OdbcConnection> поставщика данных .NET Framework для ODBC. Для соединения с источником данных Oracle используется объект <xref:System.Data.OracleClient.OracleConnection> поставщика данных .NET Framework для Oracle. Для надежного хранения и извлечения строк соединения [см.](protecting-connection-information.md)  
  
## <a name="closing-connections"></a>Закрытие соединений  
 Рекомендуется всегда закрывать соединение после использования, чтобы обеспечить его возврат в пул. Блок `Using` в Visual Basic или C# автоматически удаляет соединение при выходе в коде из блока даже при наличии необработанного исключения. Для получения дополнительной информации можно [ознакомиться с использованием заявления](../../../csharp/language-reference/keywords/using-statement.md) и [с помощью заявления.](../../../visual-basic/language-reference/statements/using-statement.md)  
  
 Также можно использовать методы `Close` или `Dispose` объекта соединения для используемого поставщика. Соединения, которые явно не закрыты, нельзя добавить или вернуть в пул. Например, соединение, которое вышло за пределы области, но явно закрыто не было, будет возвращено в пул соединений только в том случае, если был достигнут максимальный размер этого пула, а соединение еще действует. Для получения дополнительной [информации см.](ole-db-odbc-and-oracle-connection-pooling.md)  
  
> [!NOTE]
> `Close` Не вызывайте `Dispose` или на **соединение,** **DataReader**, или `Finalize` любой другой управляемый объект в методе вашего класса. В методе завершения следует только освобождать неуправляемые ресурсы, которыми ваш класс непосредственно владеет. Если класс не владеет какими-либо неуправляемыми ресурсами, не включайте в его определение метод `Finalize`. Для получения дополнительной информации, см [Мусорная коллекция](../../../standard/garbage-collection/index.md).  
  
> [!NOTE]
> События входа в систему и выхода из системы не вызываются на сервере при выборке подключения из пула подключений и при возврате его в пул подключений, поскольку при возврате в пул подключений подключение фактически не закрывается. Дополнительные сведения см. в разделе [Объединение подключений в пул в SQL Server (ADO.NET)](sql-server-connection-pooling.md).  
  
## <a name="connecting-to-sql-server"></a>Подключение к SQL Server  
 Поставщик данных .NET Framework для SQL Server поддерживает формат строки соединения, аналогичный формату строки соединения OLE DB (ADO). Сведения о допустимых именах и значениях формата строки см. в свойстве <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> объекта <xref:System.Data.SqlClient.SqlConnection>. Можно также использовать класс <xref:System.Data.SqlClient.SqlConnectionStringBuilder> для создания синтаксически правильных строк соединения во время выполнения. Дополнительные сведения см. в статье [Connection String Builders](connection-string-builders.md) (Построители строк подключения).  
  
 В следующем примере кода демонстрируется способ создания и открытия соединения с базой данных SQL Server.  
  
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
  
### <a name="integrated-security-and-aspnet"></a>Встроенная безопасность и ASP.NET  
 Встроенная безопасность SQL Server (именуемая также доверительными соединениями) обеспечивает защиту при соединении с SQL Server, так как не отображает идентификатор пользователя и пароль в строке соединения, поэтому является рекомендуемым методом проверки подлинности соединения. Встроенная безопасность основана на использовании текущего идентификатора безопасности, или маркера выполняемого процесса. В приложениях рабочего стола, как правило, используется идентификатор текущего, вошедшего в систему пользователя.  
  
 Идентификатор безопасности приложений ASP.NET может быть настроен на получение одного из нескольких различных параметров. Чтобы лучше понять идентификатор безопасности, который приложение ASP.NET использует при подключении к серверу S'L, см. [ASP.NET олицетворение,](https://docs.microsoft.com/previous-versions/aspnet/xh507fc5(v=vs.100))ASP.NET [аутентификация,](https://docs.microsoft.com/previous-versions/aspnet/eeyk640h(v=vs.100))и [Как: Доступ к серверу S'L с помощью интегрированной безопасности Windows.](https://docs.microsoft.com/previous-versions/aspnet/bsz5788z(v=vs.100))  
  
## <a name="connecting-to-an-ole-db-data-source"></a>Соединение с источником данных OLE DB  
 Поставщик рамочных данных .NET для OLE DB обеспечивает подключение к источникам данных, подвергаемым воздействию OLE DB (через СЛОЛОЛЕДЕБ, поставщика OLE DB для сервера S'L), с использованием объекта **OleDbConnection.**  
  
 Формат строки соединения поставщика данных .NET Framework для OLE DB идентичен формату строки соединения, используемому в ADO, за исключением следующего.  
  
- Требуется ключевое слово **Поставщика.**  
  
- **URL,** **удаленный провайдер**и ключевые слова **удаленного сервера** не поддерживаются.  
  
 Дополнительные сведения о строках соединения OLE DB см. в разделе <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A>. Построитель <xref:System.Data.OleDb.OleDbConnectionStringBuilder> также используется для создания строк соединения во время выполнения.  
  
> [!NOTE]
> Объект **OleDbConnection** не поддерживает настройку или получение динамических свойств, характерных для поставщика OLE DB. Поддерживаются только те свойства, которые можно передать в строке соединения поставщику OLE DB.  
  
 В следующем примере кода демонстрируется способ создания и открытия соединения с источником данных OLE DB.  
  
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
  
## <a name="do-not-use-universal-data-link-files"></a>Отказ от использования файлов в формате UDL  
 Можно предоставить информацию о подключении к **OleDbConnection** в файле Универсальной ссылки данных (UDL); однако вы должны избегать этого. UDL-файлы не подвергаются шифрованию, и строки соединения хранятся в них в виде простого текста. Так как UDL-файл представляет собой внешний файловый ресурс для приложения, его нельзя защитить средствами .NET Framework.  
  
## <a name="connecting-to-an-odbc-data-source"></a>Соединение с источником данных ODBC  
 Поставщик рамочных данных .NET для ODBC обеспечивает подключение к источникам данных, подвергаемым воздействию ODBC с помощью объекта **OdbcConnection.**  
  
 Формат строки соединения поставщика данных .NET Framework для ODBC создан с учетом настолько полного согласования с форматом строки соединения ODBC, насколько это возможно. Также можно указать имя источника данных ODBC (DSN). Для получения более подробной информации <xref:System.Data.Odbc.OdbcConnection>о **OdbcConnection** , см.  
  
 В следующем примере кода демонстрируется способ создания и открытия соединения с источником данных ODBC.  
  
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
  
## <a name="connecting-to-an-oracle-data-source"></a>Соединение с источником данных Oracle  
 Поставщик рамочных данных .NET для Oracle обеспечивает подключение к источникам данных Oracle с помощью объекта **OracleConnection.**  
  
 Формат строки соединения поставщика данных .NET Framework для Oracle создан с учетом настолько полного согласования с форматом строки соединения поставщика OLE DB для Oracle (MSDAORA), насколько это возможно. Для получения более подробной информации о **OracleConnection**, см. <xref:System.Data.OracleClient.OracleConnection>  
  
 В следующем примере кода демонстрируется способ создания и открытия соединения с источником данных Oracle.  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Подключение к источнику данных](connecting-to-a-data-source.md)
- [Строки подключения](connection-strings.md)
- [Организация пулов соединений OLE DB, ODBC и Oracle](ole-db-odbc-and-oracle-connection-pooling.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
