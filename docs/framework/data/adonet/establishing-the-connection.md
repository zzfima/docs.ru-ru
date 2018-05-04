---
title: Установка подключения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3af512f3-87d9-4005-9e2f-abb1060ff43f
ms.openlocfilehash: a416994e5d5a1be5da9571d9f8e7564f0f14f238
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="establishing-the-connection"></a>Установка подключения
Для создания соединения с Microsoft SQL Server используется объект <xref:System.Data.SqlClient.SqlConnection> поставщика данных .NET Framework для SQL Server. Для соединения с источником данных OLE DB используется объект <xref:System.Data.OleDb.OleDbConnection> поставщика данных .NET Framework для OLE DB. Для соединения с источником данных используется объект <xref:System.Data.Odbc.OdbcConnection> поставщика данных .NET Framework для ODBC. Для соединения с источником данных Oracle используется объект <xref:System.Data.OracleClient.OracleConnection> поставщика данных .NET Framework для Oracle. Безопасное хранение и извлечение строк подключения см. в разделе [Защита сведений о соединении](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
## <a name="closing-connections"></a>Закрытие соединений  
 Рекомендуется всегда закрывать соединение после использования, чтобы обеспечить его возврат в пул. Блок `Using` в Visual Basic или C# автоматически удаляет соединение при выходе в коде из блока даже при наличии необработанного исключения. В разделе [с помощью инструкции](~/docs/csharp/language-reference/keywords/using-statement.md) и [инструкции Using](~/docs/visual-basic/language-reference/statements/using-statement.md) для получения дополнительной информации.  
  
 Также можно использовать методы `Close` или `Dispose` объекта соединения для используемого поставщика. Соединения, которые явно не закрыты, нельзя добавить или вернуть в пул. Например, соединение, которое вышло за пределы области, но явно закрыто не было, будет возвращено в пул соединений только в том случае, если был достигнут максимальный размер этого пула, а соединение еще действует. Дополнительные сведения см. в разделе [OLE DB, ODBC и Oracle пулов соединений](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md).  
  
> [!NOTE]
>  Не вызывайте `Close` или `Dispose` на **подключения**, **DataReader**, или любого другого управляемого объекта в `Finalize` метод класса. В методе завершения следует только освобождать неуправляемые ресурсы, которыми ваш класс непосредственно владеет. Если класс не владеет какими-либо неуправляемыми ресурсами, не включайте в его определение метод `Finalize`. Дополнительные сведения см. в разделе [мусора](../../../../docs/standard/garbage-collection/index.md).  
  
> [!NOTE]
>  События входа в систему и выхода из системы не вызываются на сервере при выборке подключения из пула подключений и при возврате его в пул подключений, поскольку при возврате в пул подключений подключение фактически не закрывается. Дополнительные сведения см. в разделе [Пулы подключений SQL Server (ADO.NET)](../../../../docs/framework/data/adonet/sql-server-connection-pooling.md).  
  
## <a name="connecting-to-sql-server"></a>Соединение с SQL Server  
 Поставщик данных .NET Framework для SQL Server поддерживает формат строки соединения, аналогичный формату строки соединения OLE DB (ADO). Сведения о допустимых именах и значениях формата строки см. в свойстве <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> объекта <xref:System.Data.SqlClient.SqlConnection>. Можно также использовать класс <xref:System.Data.SqlClient.SqlConnectionStringBuilder> для создания синтаксически правильных строк соединения во время выполнения. Дополнительные сведения см. в разделе [построители строк соединения](../../../../docs/framework/data/adonet/connection-string-builders.md).  
  
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
  
 Идентификатор безопасности приложений ASP.NET может быть настроен на получение одного из нескольких различных параметров. Чтобы лучше понять удостоверения безопасности, приложение ASP.NET при подключении к SQL Server, см. [олицетворение ASP.NET](http://msdn.microsoft.com/library/a0cb3024-562f-4184-9d3c-095504787d3d), [проверки подлинности ASP.NET](http://msdn.microsoft.com/library/fc10b0ef-4ce4-4a7f-9174-886325221ee1), и [как: доступа SQL Сервер Windows с помощью встроенной безопасности](http://msdn.microsoft.com/library/683f9c9f-4375-4de6-8111-943c4423fde5).  
  
## <a name="connecting-to-an-ole-db-data-source"></a>Соединение с источником данных OLE DB  
 Поставщик данных .NET Framework для OLE DB предоставляет возможность подключения к данным источников данных OLE DB (используя SQLOLEDB, поставщик OLE DB для SQL Server), с помощью **OleDbConnection** объекта.  
  
 Формат строки соединения поставщика данных .NET Framework для OLE DB идентичен формату строки соединения, используемому в ADO, за исключением следующего.  
  
-   **Поставщика** требуется ключевое слово.  
  
-   **URL-адрес**, **удаленного поставщика**, и **удаленного сервера** ключевые слова не поддерживаются.  
  
 Дополнительные сведения о строках соединения OLE DB см. в разделе <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A>. Построитель <xref:System.Data.OleDb.OleDbConnectionStringBuilder> также используется для создания строк соединения во время выполнения.  
  
> [!NOTE]
>  **OleDbConnection** объект не поддерживает установку или получение динамических свойств, определенных для поставщика OLE DB. Поддерживаются только те свойства, которые можно передать в строке соединения поставщику OLE DB.  
  
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
 Можно указать сведения о соединении для **OleDbConnection** в файле универсальной Data Link (UDL); Однако вам следует избегать. UDL-файлы не подвергаются шифрованию, и строки соединения хранятся в них в виде простого текста. Так как UDL-файл представляет собой внешний файловый ресурс для приложения, его нельзя защитить средствами .NET Framework.  
  
## <a name="connecting-to-an-odbc-data-source"></a>Соединение с источником данных ODBC  
 Поставщик данных .NET Framework для ODBC обеспечивает возможность подключения к данным источников данных ODBC с помощью **OdbcConnection** объекта.  
  
 Формат строки соединения поставщика данных .NET Framework для ODBC создан с учетом настолько полного согласования с форматом строки соединения ODBC, насколько это возможно. Также можно указать имя источника данных ODBC (DSN). Дополнительные сведения о **OdbcConnection** , в разделе <xref:System.Data.Odbc.OdbcConnection>.  
  
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
 Поставщик данных .NET Framework для Oracle обеспечивает возможность подключения к источникам данных Oracle, используя **OracleConnection** объекта.  
  
 Формат строки соединения поставщика данных .NET Framework для Oracle создан с учетом настолько полного согласования с форматом строки соединения поставщика OLE DB для Oracle (MSDAORA), насколько это возможно. Дополнительные сведения о **OracleConnection**, в разделе <xref:System.Data.OracleClient.OracleConnection>.  
  
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
  
## <a name="see-also"></a>См. также  
 [Подключение к источнику данных](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [Строки подключения](../../../../docs/framework/data/adonet/connection-strings.md)  
 [Организация пулов соединений OLE DB, ODBC и Oracle](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
