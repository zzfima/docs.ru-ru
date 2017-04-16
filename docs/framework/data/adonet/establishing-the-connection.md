---
title: "Установление соединения | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3af512f3-87d9-4005-9e2f-abb1060ff43f
caps.latest.revision: 7
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Установление соединения
Для создания соединения с Microsoft SQL Server используется объект <xref:System.Data.SqlClient.SqlConnection> поставщика данных .NET Framework для SQL Server.  Для соединения с источником данных OLE DB используется объект <xref:System.Data.OleDb.OleDbConnection> поставщика данных .NET Framework для OLE DB.  Для соединения с источником данных используется объект <xref:System.Data.Odbc.OdbcConnection> поставщика данных .NET Framework для ODBC.  Для соединения с источником данных Oracle используется объект <xref:System.Data.OracleClient.OracleConnection> поставщика данных .NET Framework для Oracle.  Сведения о безопасном хранении и получение строк соединения см. в разделе [Защита сведений о соединении](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
## Закрытие соединений  
 Рекомендуется всегда закрывать соединение после использования, чтобы обеспечить его возврат в пул.  Блок `Using` в Visual Basic или C\# автоматически удаляет соединение при выходе в коде из блока даже при наличии необработанного исключения.  Дополнительные сведения см. в разделах [Оператор using](../Topic/using%20Statement%20\(C%23%20Reference\).md) и [Оператор Using](../Topic/Using%20Statement%20\(Visual%20Basic\).md).  
  
 Также можно использовать методы `Close` или `Dispose` объекта соединения для используемого поставщика.  Соединения, которые явно не закрыты, нельзя добавить или вернуть в пул.  Например, соединение, которое вышло за пределы области, но явно закрыто не было, будет возвращено в пул соединений только в том случае, если был достигнут максимальный размер этого пула, а соединение еще действует.  Для получения дополнительной информации см. [Организация пулов соединений OLE DB, ODBC, and Oracle](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md).  
  
> [!NOTE]
>  В методе `Finalize` вашего класса нельзя вызывать методы `Close` или `Dispose` объектов **Connection**, **DataReader** или любого другого управляемого объекта.  В методе завершения следует только освобождать неуправляемые ресурсы, которыми ваш класс непосредственно владеет.  Если класс не владеет какими\-либо неуправляемыми ресурсами, не включайте в его определение метод `Finalize`.  Для получения дополнительной информации см. [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).  
  
> [!NOTE]
>  События входа в систему и выхода из системы не вызываются на сервере при выборке подключения из пула подключений и при возврате его в пул подключений, поскольку при возврате в пул подключений подключение фактически не закрывается.  Для получения дополнительной информации см. [Организация пулов соединений SQL Server \(ADO.NET\)](../../../../docs/framework/data/adonet/sql-server-connection-pooling.md).  
  
## Соединение с SQL Server  
 Поставщик данных .NET Framework для SQL Server поддерживает формат строки соединения, аналогичный формату строки соединения OLE DB \(ADO\).  Сведения о допустимых именах и значениях формата строки см. в свойстве <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> объекта <xref:System.Data.SqlClient.SqlConnection>.  Можно также использовать класс <xref:System.Data.SqlClient.SqlConnectionStringBuilder> для создания синтаксически правильных строк соединения во время выполнения.  Для получения дополнительной информации см. [Построители строк подключения](../../../../docs/framework/data/adonet/connection-string-builders.md).  
  
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
  
### Встроенная безопасность и ASP.NET  
 Встроенная безопасность SQL Server \(именуемая также доверительными соединениями\) обеспечивает защиту при соединении с SQL Server, так как не отображает идентификатор пользователя и пароль в строке соединения, поэтому является рекомендуемым методом проверки подлинности соединения.  Встроенная безопасность основана на использовании текущего идентификатора безопасности, или маркера выполняемого процесса.  В приложениях рабочего стола, как правило, используется идентификатор текущего, вошедшего в систему пользователя.  
  
 Идентификатор безопасности приложений ASP.NET может быть настроен на получение одного из нескольких различных параметров.  Дополнительные сведения об идентификаторе безопасности, который используется в приложении ASP.NET при соединении с SQL Server, см. в разделах [ASP.NET Impersonation](../Topic/ASP.NET%20Impersonation.md), [ASP.NET Authentication](../Topic/ASP.NET%20Authentication.md) и [How to: Access SQL Server Using Windows Integrated Security](../Topic/How%20to:%20Access%20SQL%20Server%20Using%20Windows%20Integrated%20Security.md).  
  
## Соединение с источником данных OLE DB  
 Поставщик данных .NET Framework для OLE DB обеспечивает обмен данными с источниками данных, доступ к которым предоставляется в рамках технологии OLE DB \(используя SQLOLEDB, поставщик OLE DB для SQL Server\) с помощью объекта **OleDbConnection**.  
  
 Формат строки соединения поставщика данных .NET Framework для OLE DB идентичен формату строки соединения, используемому в ADO, за исключением следующего.  
  
-   Ключевое слово **Provider** является обязательным.  
  
-   Ключевые слова **URL**, **Remote Provider** и **Remote Server** не поддерживаются.  
  
 Дополнительные сведения о строках соединения OLE DB см. в разделе <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A>.  Построитель <xref:System.Data.OleDb.OleDbConnectionStringBuilder> также используется для создания строк соединения во время выполнения.  
  
> [!NOTE]
>  Объект **OleDbConnection** не поддерживает установку или получение динамических свойств, определенных для поставщика OLE DB.  Поддерживаются только те свойства, которые можно передать в строке соединения поставщику OLE DB.  
  
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
  
## Отказ от использования файлов в формате UDL  
 Сведения о соединении **OleDbConnection** можно указать в UDL\-файле, однако этого следует избегать.  UDL\-файлы не подвергаются шифрованию, и строки соединения хранятся в них в виде простого текста.  Так как UDL\-файл представляет собой внешний файловый ресурс для приложения, его нельзя защитить средствами .NET Framework.  
  
## Соединение с источником данных ODBC  
 Поставщик данных .NET Framework для ODBC обеспечивает соединение с источниками данных с помощью интерфейса ODBC, в котором используется объект **OdbcConnection**.  
  
 Формат строки соединения поставщика данных .NET Framework для ODBC создан с учетом настолько полного согласования с форматом строки соединения ODBC, насколько это возможно.  Также можно указать имя источника данных ODBC \(DSN\).  Дополнительные сведения об объекте **OdbcConnection** см. в разделе [Класс OdbcConnection](frlrfSystemDataOdbcOdbcConnectionClassTopic).  
  
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
  
## Соединение с источником данных Oracle  
 Поставщик данных .NET Framework для Oracle обеспечивает соединение с источниками данных Oracle с помощью объекта **OdbcConnection**.  
  
 Формат строки соединения поставщика данных .NET Framework для Oracle создан с учетом настолько полного согласования с форматом строки соединения поставщика OLE DB для Oracle \(MSDAORA\), насколько это возможно.  Дополнительные сведения об объекте **OracleConnection** см. в разделе [Класс OracleConnection](frlrfSystemDataOracleClientOracleConnectionClassTopic).  
  
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
  
## См. также  
 [Подключение к источнику данных](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)   
 [Строки подключения](../../../../docs/framework/data/adonet/connection-strings.md)   
 [Организация пулов соединений OLE DB, ODBC, and Oracle](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)