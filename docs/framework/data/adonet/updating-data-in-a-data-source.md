---
title: Обновление данных в источнике данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 55c545e5-dcd5-4323-a5b9-3825c2157462
ms.openlocfilehash: 0926e3c6513a698ae47b9983d0e6ad195394a4df
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780612"
---
# <a name="updating-data-in-a-data-source"></a>Обновление данных в источнике данных
Инструкции SQL, изменяющие данные (например, INSERT, UPDATE, или DELETE), не возвращают строки. Аналогичным образом, многие хранимые процедуры выполняют некоторое действие, но не возвращают строки. Для выполнения команд, которые не возвращают строки, создайте объект **команды** с соответствующей командой SQL и **соединением**, включая все необходимые **Параметры**. Выполните команду с помощью метода **ExecuteNonQuery** объекта **Command** .  
  
 Метод **ExecuteNonQuery** возвращает целое число, представляющее количество строк, затронутых выполняемой инструкцией или хранимой процедурой. Если выполняется несколько инструкций, возвращенное значение является суммой количеств записей, затронутых всеми выполненными инструкциями.  
  
## <a name="example"></a>Пример  
 В следующем примере кода инструкция INSERT выполняется для вставки записи в базу данных с помощью **ExecuteNonQuery**.  
  
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
  
 В следующем примере кода выполняется хранимая процедура, созданная в примере кода для [выполнения операций с каталогом](performing-catalog-operations.md). Хранимая процедура не возвращает ни одной строки, поэтому используется метод **ExecuteNonQuery** , но хранимая процедура получает входной параметр и возвращает выходной параметр и возвращаемое значение.  
  
 Для объекта необходимо сначала добавить параметр **ReturnValue** в коллекцию **Parameters.** <xref:System.Data.OleDb.OleDbCommand>  
  
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

- [Использование команд для изменения данных](using-commands-to-modify-data.md)
- [Обновление источников данных с объектами DataAdapter](updating-data-sources-with-dataadapters.md)
- [Команды и параметры](commands-and-parameters.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
