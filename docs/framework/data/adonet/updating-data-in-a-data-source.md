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
# <a name="updating-data-in-a-data-source"></a><span data-ttu-id="6e744-102">Обновление данных в источнике данных</span><span class="sxs-lookup"><span data-stu-id="6e744-102">Updating Data in a Data Source</span></span>
<span data-ttu-id="6e744-103">Инструкции SQL, изменяющие данные (например, INSERT, UPDATE, или DELETE), не возвращают строки.</span><span class="sxs-lookup"><span data-stu-id="6e744-103">SQL statements that modify data (such as INSERT, UPDATE, or DELETE) do not return rows.</span></span> <span data-ttu-id="6e744-104">Аналогичным образом, многие хранимые процедуры выполняют некоторое действие, но не возвращают строки.</span><span class="sxs-lookup"><span data-stu-id="6e744-104">Similarly, many stored procedures perform an action but do not return rows.</span></span> <span data-ttu-id="6e744-105">Для выполнения команд, которые не возвращают строки, создайте объект **команды** с соответствующей командой SQL и **соединением**, включая все необходимые **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="6e744-105">To execute commands that do not return rows, create a **Command** object with the appropriate SQL command and a **Connection**, including any required **Parameters**.</span></span> <span data-ttu-id="6e744-106">Выполните команду с помощью метода **ExecuteNonQuery** объекта **Command** .</span><span class="sxs-lookup"><span data-stu-id="6e744-106">Execute the command with the **ExecuteNonQuery** method of the **Command** object.</span></span>  
  
 <span data-ttu-id="6e744-107">Метод **ExecuteNonQuery** возвращает целое число, представляющее количество строк, затронутых выполняемой инструкцией или хранимой процедурой.</span><span class="sxs-lookup"><span data-stu-id="6e744-107">The **ExecuteNonQuery** method returns an integer that represents the number of rows affected by the statement or stored procedure that was executed.</span></span> <span data-ttu-id="6e744-108">Если выполняется несколько инструкций, возвращенное значение является суммой количеств записей, затронутых всеми выполненными инструкциями.</span><span class="sxs-lookup"><span data-stu-id="6e744-108">If multiple statements are executed, the value returned is the sum of the records affected by all of the statements executed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e744-109">Пример</span><span class="sxs-lookup"><span data-stu-id="6e744-109">Example</span></span>  
 <span data-ttu-id="6e744-110">В следующем примере кода инструкция INSERT выполняется для вставки записи в базу данных с помощью **ExecuteNonQuery**.</span><span class="sxs-lookup"><span data-stu-id="6e744-110">The following code example executes an INSERT statement to insert a record into a database using **ExecuteNonQuery**.</span></span>  
  
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
  
 <span data-ttu-id="6e744-111">В следующем примере кода выполняется хранимая процедура, созданная в примере кода для [выполнения операций с каталогом](performing-catalog-operations.md).</span><span class="sxs-lookup"><span data-stu-id="6e744-111">The following code example executes the stored procedure created by the sample code in [Performing Catalog Operations](performing-catalog-operations.md).</span></span> <span data-ttu-id="6e744-112">Хранимая процедура не возвращает ни одной строки, поэтому используется метод **ExecuteNonQuery** , но хранимая процедура получает входной параметр и возвращает выходной параметр и возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="6e744-112">No rows are returned by the stored procedure, so the **ExecuteNonQuery** method is used, but the stored procedure does receive an input parameter and returns an output parameter and a return value.</span></span>  
  
 <span data-ttu-id="6e744-113">Для объекта необходимо сначала добавить параметр **ReturnValue** в коллекцию **Parameters.** <xref:System.Data.OleDb.OleDbCommand></span><span class="sxs-lookup"><span data-stu-id="6e744-113">For the <xref:System.Data.OleDb.OleDbCommand> object, the **ReturnValue** parameter must be added to the **Parameters** collection first.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6e744-114">См. также</span><span class="sxs-lookup"><span data-stu-id="6e744-114">See also</span></span>

- [<span data-ttu-id="6e744-115">Использование команд для изменения данных</span><span class="sxs-lookup"><span data-stu-id="6e744-115">Using Commands to Modify Data</span></span>](using-commands-to-modify-data.md)
- [<span data-ttu-id="6e744-116">Обновление источников данных с объектами DataAdapter</span><span class="sxs-lookup"><span data-stu-id="6e744-116">Updating Data Sources with DataAdapters</span></span>](updating-data-sources-with-dataadapters.md)
- [<span data-ttu-id="6e744-117">Команды и параметры</span><span class="sxs-lookup"><span data-stu-id="6e744-117">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="6e744-118">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6e744-118">ADO.NET Overview</span></span>](ado-net-overview.md)
