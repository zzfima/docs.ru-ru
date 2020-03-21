---
title: Параметры, возвращающие табличные значения
ms.date: 10/12/2018
dev_langs:
- csharp
- vb
ms.assetid: 370c16d5-db7b-43e3-945b-ccaab35b739b
ms.openlocfilehash: 2917a8d9b42d831566855271a2f2110637db586f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174476"
---
# <a name="table-valued-parameters"></a>Параметры, возвращающие табличные значения
Параметры, возвращающие табличное значение, упрощают маршалинг нескольких строк данных из клиентского приложения в SQL Server, устраняя потребность в нескольких круговых путях или специальной серверной логике для обработки данных. Параметры, возвращающие табличное значение, можно использовать для инкапсуляции строк данных в клиентском приложении и их отправки на сервер единой параметризованной командой. Входящие строки данных хранятся в переменной таблицы, которой затем можно управлять с помощью Transact-SQL.  
  
 Доступ к значениям столбца в возвращающих табличное значение параметрах обеспечивается с помощью стандартных инструкций Transact-SQL SELECT. Возвращающие табличное значение параметры строго типизированы, и проверка их структуры происходит автоматически. Размер возвращающих табличное значение параметров ограничен только объемом памяти сервера.  
  
> [!NOTE]
> В параметре, возвращающем табличное значение, невозможно вернуть данные. Возвращающие табличное значение параметры являются только входными. Ключевое слово OUTPUT не поддерживается.  
  
 Дополнительные сведения о возвращающих табличное значение параметрах см. в следующих ресурсах.  
  
|Ресурс|Описание|  
|--------------|-----------------|  
|[Использование параметров, возвращающих табличные значения (компонент Database Engine)](/sql/relational-databases/tables/use-table-valued-parameters-database-engine)|Здесь описывается создание и использование возвращающих табличное значение параметров.|  
|[Определяемые пользователем типы таблиц](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/bb522526(v=sql.100))|Описывает использование определяемых пользователем табличных типов для объявления возвращающих табличное значение параметров.|  
  
## <a name="passing-multiple-rows-in-previous-versions-of-sql-server"></a>Передача нескольких строк в предыдущие версии SQL Server  
 До появления в SQL Server 2008 параметров, возвращающих табличное значение, были ограниченны возможности передачи нескольких строк данных в хранимую процедуру или параметризованную команду SQL. Разработчик может выбрать один из следующих вариантов передачи нескольких строк на сервер.  
  
- Использовать ряд отдельных параметров, чтобы представить значения в нескольких столбцах и строках данных. Объем данных, которые можно передать с помощью этого метода, ограничен количеством допустимых параметров. В процедурах SQL Server можно использовать не более 2100 параметров. Для сборки этих отдельных значений в табличную переменную или временную таблицу для обработки требуется логика на стороне сервера.  
  
- Объединить несколько значений данных в строки с разделителями или документы XML, а затем передать эти текстовые значения в процедуру или инструкцию. Для этого требуется, чтобы процедура или инструкция содержали логику, необходимую для проверки структур данных и разъединения значений.  
  
- Создать ряд отдельных инструкций SQL для изменений данных, затрагивающих несколько строк, например, созданных путем вызова метода `Update` объекта <xref:System.Data.SqlClient.SqlDataAdapter>. Изменения можно отправлять на сервер по отдельности или объединять в группы. Тем не менее даже при отправке в пакетах, содержащих несколько инструкций, каждая из них выполняется на сервере отдельно.  
  
- Использовать программу `bcp` или объект <xref:System.Data.SqlClient.SqlBulkCopy>, чтобы загрузить в таблицу множество строк данных. Хотя этот метод очень эффективен, он не поддерживает обработку на стороне сервера, если данные не загружены во временную таблицу или табличную переменную.  
  
## <a name="creating-table-valued-parameter-types"></a>Создание типов параметров, возвращающих табличное значение  
 Возвращающие табличное значение параметры основаны на строго типизированных табличных структурах, заданных с помощью инструкций Transact-SQL CREATE TYPE. Перед использованием в клиентских приложениях возвращающих табличное значение параметров в SQL Server необходимо создать табличный тип и определить структуру. Для получения дополнительной информации [User-Defined Table Types](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/bb522526(v=sql.100))о создании типов таблиц см.  
  
 Следующая инструкция создает табличный тип с именем CategoryTableType, состоящий из столбцов CategoryID и CategoryName:  
  
```sql
CREATE TYPE dbo.CategoryTableType AS TABLE  
    ( CategoryID int, CategoryName nvarchar(50) )  
```  
  
 После создания табличного типа можно объявить возвращающие табличное значение параметры на основе этого типа. В приведенном ниже фрагменте кода Transact-SQL демонстрируется объявление возвращающего табличное значение параметра в определении хранимой процедуры. Обратите внимание, что для объявления возвращающего табличное значение параметра требуется ключевое слово READONLY.  
  
```sql
CREATE PROCEDURE usp_UpdateCategories
    (@tvpNewCategories dbo.CategoryTableType READONLY)  
```  
  
## <a name="modifying-data-with-table-valued-parameters-transact-sql"></a>Изменение данных с помощью возвращающих табличное значение параметров (Transact-SQL)  
 Возвращающие табличное значение параметры можно использовать во влияющих на несколько строк изменениях данных на основе наборов, выполняя одну инструкцию. Например, можно выбрать в возвращающем табличное значение параметре все строки и вставить их в таблицу базы данных. Кроме того, можно создать инструкцию UPDATE, присоединив возвращающий табличное значение параметр к таблице, которую необходимо обновить.  
  
 В приведенной ниже инструкции Transact-SQL UPDATE демонстрируется соединение возвращающего табличное значение параметра с таблицей Categories. При использовании возвращающего табличное значение параметра со значением JOIN в предложении FROM необходимо также присвоить ему псевдоним, как показано здесь, где параметр с табличным значением имеет псевдоним "ec":  
  
```sql
UPDATE dbo.Categories  
    SET Categories.CategoryName = ec.CategoryName  
    FROM dbo.Categories INNER JOIN @tvpEditedCategories AS ec  
    ON dbo.Categories.CategoryID = ec.CategoryID;  
```  
  
 В этом примере кода Transact-SQL демонстрируется выбор строк из возвращающего табличное значение параметра для выполнения инструкции INSERT в одной операции на основе набора данных.  
  
```sql
INSERT INTO dbo.Categories (CategoryID, CategoryName)  
    SELECT nc.CategoryID, nc.CategoryName FROM @tvpNewCategories AS nc;  
```  
  
## <a name="limitations-of-table-valued-parameters"></a>Ограничения возвращающих табличное значение параметров  
 Для возвращающих табличное значение параметров существует несколько ограничений.  
  
- Возвращающие табличное значение параметры нельзя передавать [определяемым пользователем функциям CLR](/sql/relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions).  
  
- Возвращающие табличное значение параметры могут индексироваться только для поддержки ограничений UNIQUE или PRIMARY KEY. SQL Server не ведет статистику возвращающих табличные значения параметров.  
  
- В коде Transact-SQL возвращающие табличное значение параметры предназначены только для чтения. Нельзя обновлять значения столбцов в строках возвращающего табличное значение параметра, а также вставлять или удалять строки. Чтобы изменить данные, передаваемые в хранимую процедуру или параметризованную инструкцию в возвращающем табличное значение параметре, необходимо вставить данные во временную таблицу или в табличную переменную.  
  
- Нельзя использовать инструкции ALTER TABLE для изменения структуры возвращающих табличное значение параметров.  
  
## <a name="configuring-a-sqlparameter-example"></a>Пример настройки параметра SqlParameter  
 Поставщик <xref:System.Data.SqlClient> поддерживает заполнение возвращающих табличное значение параметров из объектов <xref:System.Data.DataTable>, <xref:System.Data.Common.DbDataReader> или <xref:System.Collections.Generic.IEnumerable%601> \ <xref:Microsoft.SqlServer.Server.SqlDataRecord>. Необходимо указать имя типа возвращающего табличное значение параметра с помощью свойства <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> объекта <xref:System.Data.SqlClient.SqlParameter>. `TypeName` должно совпадать с именем совместимого типа, ранее созданного на сервере. В приведенном ниже фрагменте кода демонстрируется, как настроить <xref:System.Data.SqlClient.SqlParameter> для вставки данных.  

В следующем примере переменная `addedCategories` содержит <xref:System.Data.DataTable>. Чтобы увидеть, как заполняется переменная, просмотрите примеры в следующем разделе: [Передача возвращающего табличное значение параметра в хранимую процедуру](#passing).

```csharp  
// Configure the command and parameter.  
SqlCommand insertCommand = new SqlCommand(sqlInsert, connection);  
SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
tvpParam.SqlDbType = SqlDbType.Structured;  
tvpParam.TypeName = "dbo.CategoryTableType";  
```  
  
```vb  
' Configure the command and parameter.  
Dim insertCommand As New SqlCommand(sqlInsert, connection)  
Dim tvpParam As SqlParameter = _  
   insertCommand.Parameters.AddWithValue( _  
  "@tvpNewCategories", addedCategories)  
tvpParam.SqlDbType = SqlDbType.Structured  
tvpParam.TypeName = "dbo.CategoryTableType"  
```  
  
 Также для передачи строк данных в возвращающий табличное значение параметр можно использовать любой производный от <xref:System.Data.Common.DbDataReader> объект, как показано в этом фрагменте.  
  
```csharp  
// Configure the SqlCommand and table-valued parameter.  
SqlCommand insertCommand = new SqlCommand("usp_InsertCategories", connection);  
insertCommand.CommandType = CommandType.StoredProcedure;  
SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", dataReader);  
tvpParam.SqlDbType = SqlDbType.Structured;  
```  
  
```vb  
' Configure the SqlCommand and table-valued parameter.  
Dim insertCommand As New SqlCommand("usp_InsertCategories", connection)  
insertCommand.CommandType = CommandType.StoredProcedure  
Dim tvpParam As SqlParameter = _  
  insertCommand.Parameters.AddWithValue("@tvpNewCategories", _  
  dataReader)  
tvpParam.SqlDbType = SqlDbType.Structured  
```  
  
## <a name="passing-a-table-valued-parameter-to-a-stored-procedure"></a><a name="passing"></a>Передача параметра, оцениваемого таблицей, к сохраненной процедуре  
 В этом примере демонстрируется передача данных возвращающего табличное значение параметра в хранимую процедуру. Код извлекает добавленные строки в новый объект <xref:System.Data.DataTable> с помощью метода <xref:System.Data.DataTable.GetChanges%2A>. Затем код определяет <xref:System.Data.SqlClient.SqlCommand>, устанавливая для свойства <xref:System.Data.SqlClient.SqlCommand.CommandType%2A> значение <xref:System.Data.CommandType.StoredProcedure>. <xref:System.Data.SqlClient.SqlParameter> заполняется с помощью метода <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A>, а параметру <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> задано значение `Structured`. Затем <xref:System.Data.SqlClient.SqlCommand> выполняется с помощью метода <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>.  
  
```csharp  
// Assumes connection is an open SqlConnection object.  
using (connection)  
{  
  // Create a DataTable with the modified rows.  
  DataTable addedCategories = CategoriesDataTable.GetChanges(DataRowState.Added);  

  // Configure the SqlCommand and SqlParameter.  
  SqlCommand insertCommand = new SqlCommand("usp_InsertCategories", connection);  
  insertCommand.CommandType = CommandType.StoredProcedure;  
  SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
  tvpParam.SqlDbType = SqlDbType.Structured;  

  // Execute the command.  
  insertCommand.ExecuteNonQuery();  
}  
```  
  
```vb  
' Assumes connection is an open SqlConnection object.  
Using connection  
   '  Create a DataTable with the modified rows.  
   Dim addedCategories As DataTable = _  
     CategoriesDataTable.GetChanges(DataRowState.Added)  
  
  ' Configure the SqlCommand and SqlParameter.  
   Dim insertCommand As New SqlCommand( _  
     "usp_InsertCategories", connection)  
   insertCommand.CommandType = CommandType.StoredProcedure  
   Dim tvpParam As SqlParameter = _  
     insertCommand.Parameters.AddWithValue( _  
     "@tvpNewCategories", addedCategories)  
   tvpParam.SqlDbType = SqlDbType.Structured  
  
   '  Execute the command.  
   insertCommand.ExecuteNonQuery()  
End Using  
```  
  
### <a name="passing-a-table-valued-parameter-to-a-parameterized-sql-statement"></a>Передача возвращающего табличное значение параметра в параметризованную инструкцию SQL  
 В следующем примере показано, как вставить данные в таблицу dbo.Categories с помощью инструкции INSERT с вложенным запросом SELECT, имеющим в качестве источника данных возвращающий табличное значение параметр. При передаче возвращающего табличное значение параметра в параметризованную инструкцию SQL необходимо указать имя типа этого параметра с помощью нового свойства <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> объекта <xref:System.Data.SqlClient.SqlParameter>. `TypeName` должно совпадать с именем совместимого типа, ранее созданного на сервере. Код в этом примере использует свойство `TypeName` для ссылки на структуру типа, определенную в dbo.CategoryTableType.  
  
> [!NOTE]
> Если для столбца идентификаторов задается значение в возвращающем табличное значение параметре, необходимо выполнить инструкцию SET IDENTITY_INSERT для сеанса.  
  
```csharp  
// Assumes connection is an open SqlConnection.  
using (connection)  
{  
  // Create a DataTable with the modified rows.  
  DataTable addedCategories = CategoriesDataTable.GetChanges(DataRowState.Added);  

  // Define the INSERT-SELECT statement.  
  string sqlInsert =
      "INSERT INTO dbo.Categories (CategoryID, CategoryName)"  
      + " SELECT nc.CategoryID, nc.CategoryName"  
      + " FROM @tvpNewCategories AS nc;"  

  // Configure the command and parameter.  
  SqlCommand insertCommand = new SqlCommand(sqlInsert, connection);  
  SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
  tvpParam.SqlDbType = SqlDbType.Structured;  
  tvpParam.TypeName = "dbo.CategoryTableType";  

  // Execute the command.  
  insertCommand.ExecuteNonQuery();  
}  
```  
  
```vb  
' Assumes connection is an open SqlConnection.  
Using connection  
  ' Create a DataTable with the modified rows.  
  Dim addedCategories As DataTable = _  
    CategoriesDataTable.GetChanges(DataRowState.Added)  
  
  ' Define the INSERT-SELECT statement.  
  Dim sqlInsert As String = _  
  "INSERT INTO dbo.Categories (CategoryID, CategoryName)" _  
  & " SELECT nc.CategoryID, nc.CategoryName" _  
  & " FROM @tvpNewCategories AS nc;"  
  
  ' Configure the command and parameter.  
  Dim insertCommand As New SqlCommand(sqlInsert, connection)  
  Dim tvpParam As SqlParameter = _  
     insertCommand.Parameters.AddWithValue( _  
    "@tvpNewCategories", addedCategories)  
  tvpParam.SqlDbType = SqlDbType.Structured  
  tvpParam.TypeName = "dbo.CategoryTableType"  
  
  ' Execute the query  
  insertCommand.ExecuteNonQuery()  
End Using  
```  
  
## <a name="streaming-rows-with-a-datareader"></a>Потоковая передача строк с помощью объекта DataReader  
 Также для передачи строк данных в возвращающий табличное значение параметр можно использовать любой производный от <xref:System.Data.Common.DbDataReader> объект. В следующем фрагменте кода демонстрируется получение данных из базы данных Oracle с помощью <xref:System.Data.OracleClient.OracleCommand> и <xref:System.Data.OracleClient.OracleDataReader>. Затем код настраивает <xref:System.Data.SqlClient.SqlCommand> для вызова хранимой процедуры с одним входным параметром. Свойство <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> объекта <xref:System.Data.SqlClient.SqlParameter> имеет значение `Structured`. <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> передает результирующий набор `OracleDataReader` в хранимую процедуру в виде возвращающего табличное значение параметра.  
  
```csharp  
// Assumes connection is an open SqlConnection.  
// Retrieve data from Oracle.  
OracleCommand selectCommand = new OracleCommand(  
   "Select CategoryID, CategoryName FROM Categories;",  
   oracleConnection);  
OracleDataReader oracleReader = selectCommand.ExecuteReader(  
   CommandBehavior.CloseConnection);  
  
 // Configure the SqlCommand and table-valued parameter.  
 SqlCommand insertCommand = new SqlCommand(  
   "usp_InsertCategories", connection);  
 insertCommand.CommandType = CommandType.StoredProcedure;  
 SqlParameter tvpParam =  
    insertCommand.Parameters.AddWithValue(  
    "@tvpNewCategories", oracleReader);  
 tvpParam.SqlDbType = SqlDbType.Structured;  
  
 // Execute the command.  
 insertCommand.ExecuteNonQuery();  
```  
  
```vb  
' Assumes connection is an open SqlConnection.  
' Retrieve data from Oracle.  
Dim selectCommand As New OracleCommand( _  
  "Select CategoryID, CategoryName FROM Categories;", _  
  oracleConnection)  
Dim oracleReader As OracleDataReader = _  
  selectCommand.ExecuteReader(CommandBehavior.CloseConnection)  
  
' Configure SqlCommand and table-valued parameter.  
Dim insertCommand As New SqlCommand("usp_InsertCategories", connection)  
insertCommand.CommandType = CommandType.StoredProcedure  
Dim tvpParam As SqlParameter = _  
  insertCommand.Parameters.AddWithValue("@tvpNewCategories", _  
  oracleReader)  
tvpParam.SqlDbType = SqlDbType.Structured  
  
' Execute the command.  
insertCommand.ExecuteNonQuery()  
```  
  
## <a name="see-also"></a>См. также раздел

- [Настройка параметров и типы данных параметров](../configuring-parameters-and-parameter-data-types.md)
- [Команды и параметры](../commands-and-parameters.md)
- [Параметры DataAdapter](../dataadapter-parameters.md)
- [Операции с серверами серверов в ADO.NET](sql-server-data-operations.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
