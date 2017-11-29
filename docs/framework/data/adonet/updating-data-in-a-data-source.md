---
title: "Обновление данных в источнике данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 55c545e5-dcd5-4323-a5b9-3825c2157462
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 91e6a5f2b956816b5e001701a7fbe4a40e7866e5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="updating-data-in-a-data-source"></a>Обновление данных в источнике данных
Инструкции SQL, изменяющие данные (например, INSERT, UPDATE, или DELETE), не возвращают строки. Аналогичным образом, многие хранимые процедуры выполняют некоторое действие, но не возвращают строки. Для выполнения команд, которые не возвращают строки, создайте **команда** объект с соответствующей командой SQL и **подключения**, включая все необходимые **параметры**. Выполните команду с **ExecuteNonQuery** метод **команда** объекта.  
  
 **ExecuteNonQuery** метод возвращает целое число, представляющее число строк, затронутых инструкцией или хранимой процедуры, которая была выполнена. Если выполняется несколько инструкций, возвращенное значение является суммой количеств записей, затронутых всеми выполненными инструкциями.  
  
## <a name="example"></a>Пример  
 В следующем примере кода выполняется инструкция INSERT для вставки записи в базе данных с помощью **ExecuteNonQuery**.  
  
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
  
 В следующем примере кода выполняется хранимая процедура, созданная в примере кода в [выполнение операций над каталогами](../../../../docs/framework/data/adonet/performing-catalog-operations.md). Строки не возвращаются хранимой процедурой, поэтому **ExecuteNonQuery** метод используется, но хранимая процедура получает входной параметр и возвращает выходной параметр и возвращаемое значение.  
  
 Для <xref:System.Data.OleDb.OleDbCommand> объекта, **ReturnValue** необходимо добавить параметр **параметры** коллекции первой.  
  
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
  
## <a name="see-also"></a>См. также  
 [Изменение данных с помощью команды](../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)  
 [Обновление источников данных с объектами DataAdapter](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 [Команды и параметры](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
