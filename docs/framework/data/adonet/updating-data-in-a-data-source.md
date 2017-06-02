---
title: "Обновление данных в источнике данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 55c545e5-dcd5-4323-a5b9-3825c2157462
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Обновление данных в источнике данных
Инструкции SQL, изменяющие данные \(например, INSERT, UPDATE, или DELETE\), не возвращают строки.  Аналогичным образом, многие хранимые процедуры выполняют некоторое действие, но не возвращают строки.  Для выполнения команд, не возвращающих строки, следует создать объект **Command** с соответствующей командой SQL и объект **Connection**, включающий любую требуемую коллекцию **Parameters**.  Выполните команду с помощью метода **ExecuteNonQuery** объекта **Command**.  
  
 Метод **ExecuteNonQuery** возвращает значение типа integer, представляющее число строк, затрагиваемых выполненной инструкцией или хранимой процедурой.  Если выполняется несколько инструкций, возвращенное значение является суммой количеств записей, затронутых всеми выполненными инструкциями.  
  
## Пример  
 В следующем примере кода выполняется инструкция INSERT для вставки записи в базу данных с помощью **ExecuteNonQuery**.  
  
```vb  
' Assumes connection is a valid SqlConnection.  
connection.Open()  
  
Dim queryString As String = "INSERT INTO Customers " & _  
  "(CustomerID, CompanyName) Values('NWIND', 'Northwind Traders')"  
  
Dim command As SqlCommand = New SqlCommand(queryString, connection)  
Dim recordsAffected As Int32 = command.ExecuteNonQuery()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
connection.Open();  
  
string queryString = "INSERT INTO Customers " +  
  "(CustomerID, CompanyName) Values('NWIND', 'Northwind Traders')";  
  
SqlCommand command = new SqlCommand(queryString, connection);  
Int32 recordsAffected = command.ExecuteNonQuery();  
```  
  
 В следующем примере кода выполняется хранимая процедура, созданная образцом кода в разделе [Выполнение операций над каталогами](../../../../docs/framework/data/adonet/performing-catalog-operations.md).  Ни одна строка не возвращается хранимой процедурой, так что при использовании метода **ExecuteNonQuery** хранимая процедура получает входной параметр и возвращает выходной параметр и значение.  
  
 Что касается объекта <xref:System.Data.OleDb.OleDbCommand>, то параметр **ReturnValue** должен быть добавлен к коллекции **Parameters** в первую очередь.  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim command As SqlCommand = _  
   New SqlCommand("InsertCategory" , connection)  
command.CommandType = CommandType.StoredProcedure  
  
Dim parameter As SqlParameter = _  
 command.Parameters.Add("@RowCount", SqlDbType.Int)  
parameter.Direction = ParameterDirection.ReturnValue  
  
parameter = command.Parameters.Add( _  
  "@CategoryName", SqlDbType.NChar, 15)  
  
parameter = command.Parameters.Add("@Identity", SqlDbType.Int)  
parameter.Direction = ParameterDirection.Output  
  
command.Parameters("@CategoryName").Value = "New Category"  
command.ExecuteNonQuery()  
  
Dim categoryID As Int32 = CInt(command.Parameters("@Identity").Value)  
Dim rowCount As Int32 = CInt(command.Parameters("@RowCount").Value)   
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlCommand command = new SqlCommand("InsertCategory" , connection);  
command.CommandType = CommandType.StoredProcedure;  
  
SqlParameter parameter = command.Parameters.Add(  
  "@RowCount", SqlDbType.Int);  
parameter.Direction = ParameterDirection.ReturnValue;  
  
parameter = command.Parameters.Add(  
  "@CategoryName", SqlDbType.NChar, 15);  
  
parameter = command.Parameters.Add("@Identity", SqlDbType.Int);  
parameter.Direction = ParameterDirection.Output;  
  
command.Parameters["@CategoryName"].Value = "New Category";  
command.ExecuteNonQuery();  
  
Int32 categoryID = (Int32) command.Parameters["@Identity"].Value;  
Int32 rowCount = (Int32) command.Parameters["@RowCount"].Value;  
```  
  
## См. также  
 [Использование команд для изменения данных](../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)   
 [Обновление источников данных с помощью объектов DataAdapter](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)   
 [Команды и параметры](../../../../docs/framework/data/adonet/commands-and-parameters.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)