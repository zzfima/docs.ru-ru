---
title: Коллекции GetSchema и Schema
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab93b89-1221-427c-84ad-04803b3c64b4
ms.openlocfilehash: e18c23e9bbec97a64110aba6eb7241761ecece06
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149561"
---
# <a name="getschema-and-schema-collections"></a>Коллекции GetSchema и Schema
Классы **подключения** в каждом из управляемых провайдеров .NET используют метод **GetSchema,** который используется для получения информации о схеме, которая в настоящее время подключена, и информация о схеме, возвращенная из метода **GetSchema,** поступает в виде <xref:System.Data.DataTable>. Метод **GetSchema** — это перегруженный метод, который предоставляет дополнительные параметры для определения сбора схемы для возврата и ограничения объема возвращенной информации.  
  
## <a name="specifying-the-schema-collections"></a>Указание коллекций схем  
 Первым дополнительным параметром метода **GetSchema** является имя коллекции, которое указывается как строка. Существует два типа коллекций схем: стандартные (общие для всех поставщиков) и специальные (определенные для каждого поставщика).  
  
 Вы можете задать запрос управляемому провайдеру .NET Framework для определения списка поддерживаемых коллекций схем, позвонив в метод **GetSchema** без каких-либо аргументов или с именем коллекции схемы "MetaDataCollections". При этом будет возвращена <xref:System.Data.DataTable> со списком поддерживаемых коллекций схем, число ограничений, которые каждая из них поддерживает, и число идентификационных частей, которые в них используются.  
  
### <a name="retrieving-schema-collections-example"></a>Получение примера коллекций схем  
 Следующие примеры демонстрируют, <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> как использовать метод поставщика рамочных <xref:System.Data.SqlClient.SqlConnection> данных .NET для класса S'L Server для получения информации о схемах обо всех таблицах, содержащихся в базе данных **образцов AdventureWorks:**  
  
```vb  
Imports System.Data.SqlClient  
  
Module Module1  
   Sub Main()  
      Dim connectionString As String = GetConnectionString()  
      Using connection As New SqlConnection(connectionString)  
         'Connect to the database then retrieve the schema information.  
         connection.Open()  
         Dim table As DataTable = connection.GetSchema("Tables")  
  
         ' Display the contents of the table.  
         DisplayData(table)  
         Console.WriteLine("Press any key to continue.")  
         Console.ReadKey()  
      End Using  
   End Sub  
  
   Private Function GetConnectionString() As String  
      ' To avoid storing the connection string in your code,
      ' you can retrieve it from a configuration file.  
      Return "Data Source=(local);Database=AdventureWorks;" _  
         & "Integrated Security=true;"  
   End Function  
  
   Private Sub DisplayData(ByVal table As DataTable)  
      For Each row As DataRow In table.Rows  
         For Each col As DataColumn In table.Columns  
            Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
         Next  
         Console.WriteLine("============================")  
      Next  
   End Sub  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Program  
{  
  static void Main()  
  {  
  string connectionString = GetConnectionString();  
  using (SqlConnection connection = new SqlConnection(connectionString))  
  {  
   // Connect to the database then retrieve the schema information.  
   connection.Open();  
   DataTable table = connection.GetSchema("Tables");  
  
   // Display the contents of the table.  
   DisplayData(table);  
   Console.WriteLine("Press any key to continue.");  
   Console.ReadKey();  
   }  
 }  
  
  private static string GetConnectionString()  
  {  
   // To avoid storing the connection string in your code,  
   // you can retrieve it from a configuration file.  
   return "Data Source=(local);Database=AdventureWorks;" +  
      "Integrated Security=true;";  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
     foreach (System.Data.DataRow row in table.Rows)  
     {  
        foreach (System.Data.DataColumn col in table.Columns)  
        {  
           Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
        }  
     Console.WriteLine("============================");  
     }  
  }  
}  
```  
  
## <a name="see-also"></a>См. также раздел

- [Извлечение сведений о схеме базы данных](retrieving-database-schema-information.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
