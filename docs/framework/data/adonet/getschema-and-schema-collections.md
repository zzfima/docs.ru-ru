---
title: Коллекции GetSchema и Schema
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab93b89-1221-427c-84ad-04803b3c64b4
ms.openlocfilehash: 1694a6de515e5326264f345f50d0730fe2a62e4f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="getschema-and-schema-collections"></a>Коллекции GetSchema и Schema
**Подключения** классы в каждом из управляемых поставщиков .NET Framework реализует **GetSchema** метод, который используется для получения сведений о базе данных, в данный момент подключен, схеме и Возвращает сведения о схеме **GetSchema** представляются в виде <xref:System.Data.DataTable>. **GetSchema** это перегруженный метод, содержащий необязательные параметры для указания возвращаемой коллекции схем и ограничения объема возвращаемых сведений.  
  
## <a name="specifying-the-schema-collections"></a>Указание коллекций схем  
 Первым необязательным параметром метода **GetSchema** метод является имя коллекции, указанное в виде строки. Существует два типа коллекций схем: стандартные (общие для всех поставщиков) и специальные (определенные для каждого поставщика).  
  
 Можно запросить управляемый поставщик .NET Framework для определения списка поддерживаемых коллекций схем, вызвав **GetSchema** без аргументов или с именем коллекции схем «MetaDataCollections». При этом будет возвращена <xref:System.Data.DataTable> со списком поддерживаемых коллекций схем, число ограничений, которые каждая из них поддерживает, и число идентификационных частей, которые в них используются.  
  
### <a name="retrieving-schema-collections-example"></a>Получение примера коллекций схем  
 Следующие примеры демонстрируют, как использовать <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> метод поставщика данных .NET Framework для SQL Server <xref:System.Data.SqlClient.SqlConnection> класса для извлечения сведений о всех таблиц, содержащихся в схеме **AdventureWorks**образца базы данных:  
  
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
  
## <a name="see-also"></a>См. также  
 [Извлечение сведений о схеме базы данных](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
