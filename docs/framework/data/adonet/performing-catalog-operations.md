---
title: Выполнение операций каталога
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e60f542f-6271-495b-a9e4-48553481c2a3
ms.openlocfilehash: 1b13d1e3e210964331a710512876bd1f8503069e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648080"
---
# <a name="performing-catalog-operations"></a><span data-ttu-id="83b2a-102">Выполнение операций каталога</span><span class="sxs-lookup"><span data-stu-id="83b2a-102">Performing Catalog Operations</span></span>
<span data-ttu-id="83b2a-103">Чтобы выполнить команду изменения базы данных или каталога, такие как инструкция CREATE TABLE или CREATE PROCEDURE, создайте **команда** с помощью соответствующих инструкций SQL и **подключения** объекта.</span><span class="sxs-lookup"><span data-stu-id="83b2a-103">To execute a command to modify a database or catalog, such as the CREATE TABLE or CREATE PROCEDURE statement, create a **Command** object using the appropriate SQL statements and a **Connection** object.</span></span> <span data-ttu-id="83b2a-104">Выполните команду с **ExecuteNonQuery** метод **команда** объекта.</span><span class="sxs-lookup"><span data-stu-id="83b2a-104">Execute the command with the **ExecuteNonQuery** method of the **Command** object.</span></span>  
  
 <span data-ttu-id="83b2a-105">В следующем примере кода создается хранимая процедура в базе данных Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="83b2a-105">The following code example creates a stored procedure in a Microsoft SQL Server database.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim queryString As String = "CREATE PROCEDURE InsertCategory " & _  
    "@CategoryName nchar(15), " & _  
    "@Identity int OUT " & _  
    "AS " & _  
    "INSERT INTO Categories (CategoryName) VALUES(@CategoryName) " & _  
    "SET @Identity = @@Identity " & _  
    "RETURN @@ROWCOUNT"  
  
Dim command As SqlCommand = New SqlCommand(queryString, connection)  
command.ExecuteNonQuery()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
string queryString = "CREATE PROCEDURE InsertCategory  " +   
    "@CategoryName nchar(15), " +  
    "@Identity int OUT " +  
    "AS " +   
    "INSERT INTO Categories (CategoryName) VALUES(@CategoryName) " +   
    "SET @Identity = @@Identity " +  
    "RETURN @@ROWCOUNT";  
  
SqlCommand command = new SqlCommand(queryString, connection);  
command.ExecuteNonQuery();  
```  
  
## <a name="see-also"></a><span data-ttu-id="83b2a-106">См. также</span><span class="sxs-lookup"><span data-stu-id="83b2a-106">See also</span></span>
- [<span data-ttu-id="83b2a-107">Использование команд для изменения данных</span><span class="sxs-lookup"><span data-stu-id="83b2a-107">Using Commands to Modify Data</span></span>](../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)
- [<span data-ttu-id="83b2a-108">Команды и параметры</span><span class="sxs-lookup"><span data-stu-id="83b2a-108">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="83b2a-109">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="83b2a-109">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
