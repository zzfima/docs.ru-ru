---
title: "Извлечение данных с помощью DataReader | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Извлечение данных с помощью DataReader
Для извлечения данных с помощью **DataReader** необходимо создать экземпляр объекта **Command**, а затем создать объект **DataReader**, вызвав метод **Command.ExecuteReader** для получения строк из источника данных.  В следующем примере иллюстрируется использование объекта **DataReader**, где `reader` представляет допустимый DataReader, а `command` представляет допустимый объект Command.  
  
```  
reader = command.ExecuteReader();  
```  
  
 Метод **Read** объекта **DataReader** используется для получения строки из результатов запроса.  Доступ к отдельным столбцам возвращенной строки осуществляется по имени или порядковому номеру столбца через объект **DataReader**.  Однако для максимальной производительности объект **DataReader** предоставляет ряд методов, позволяющих обращаться к значениям столбцов в их собственных типах данных \(**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32** и т. д.\).  Список типизированных методов доступа в объектах **DataReader** для конкретных поставщиков данных см. в разделах <xref:System.Data.OleDb.OleDbDataReader> и <xref:System.Data.SqlClient.SqlDataReader>.  Использование типизированных методов доступа при условии, что известен базовый тип данных, сокращает объем преобразований типов, необходимых при извлечении значения столбца.  
  
> [!NOTE]
>  В версии платформы .NET Framework для Windows Server 2003 имеется дополнительное свойство объекта **DataReader**, **HasRows**, которое позволяет определить, возвратил ли объект **DataReader** какие\-либо результаты, перед тем как читать из него.  
  
 В следующем примере кода просматриваются результаты, возвращенные объектом **DataReader** и возвращаются два столбца для каждой строки.  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
 Объект **DataReader** предоставляет небуферизованный поток данных, позволяющий процедурам последовательно обрабатывать результаты из источника данных.  Объект **DataReader** хорошо подходит для извлечения больших объемов данных, поскольку данные не кэшируются в памяти.  
  
## Закрытие DataReader  
 По окончании использования объекта **DataReader** всегда следует вызывать метод **Close**.  
  
 Если метод **Command** содержит выходные параметры или возвращаемые значения, они будут недоступны до закрытия объекта **DataReader**.  
  
 Имейте в виду, что пока объект **DataReader** открыт, соединение **Connection** используется исключительно этим объектом **DataReader**.  Невозможно выполнять какие\-либо команды для **Connection**, включая создание другого объекта **DataReader**, пока исходный объект **DataReader** не будет закрыт.  
  
> [!NOTE]
>  В методе **Finalize** вашего класса нельзя вызывать методы **Close** или **Dispose** объектов **Connection**, **DataReader** или любого другого управляемого объекта.  В методе завершения следует только освобождать неуправляемые ресурсы, которыми ваш класс непосредственно владеет.  Если класс не владеет какими\-либо неуправляемыми ресурсами, не включайте в его определение метод **Finalize**.  Для получения дополнительной информации см. [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).  
  
## Извлечение нескольких результирующих наборов при помощи NextResult  
 При возвращении нескольких результирующих наборов объект **DataReader** предоставляет метод **NextResult** для просмотра наборов результатов по порядку.  В следующем примере показан объект <xref:System.Data.SqlClient.SqlDataReader>, обрабатывающий результаты двух инструкций SELECT с помощью метода <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## Получение данных схемы от DataReader  
 Когда открыт объект **DataReader**, с помощью метода **GetSchemaTable** можно получить данные схемы о текущем результирующем наборе.  Метод **GetSchemaTable** возвращает объект <xref:System.Data.DataTable>, заполненный строками и столбцами, которые содержат данные схемы для текущего результирующего набора.  Объект **DataTable** содержит одну строку для каждого столбца результирующего набора.  Каждый столбец строки таблицы схемы соответствует свойству столбца, возвращенного в результирующем наборе, где **ColumnName** \- это имя свойства, а значение столбца \- это значение свойства.  В следующем примере кода на консоль выводятся данные схемы для объекта **DataReader**.  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## Работа с разделами OLE DB  
 Иерархические наборы строк или разделы \(тип **DBTYPE\_HCHAPTER** в OLE DB, тип **adChapter** в ADO\) можно получать с помощью объекта <xref:System.Data.OleDb.OleDbDataReader>.  Когда запрос, содержащий раздел, возвращается в виде объекта **DataReader**, раздел возвращается в виде столбца в этом объекте **DataReader** и представляется как объект **DataReader**.  
  
 Для представления иерархических наборов строк при помощи связей типа «родитель\-потомок» между таблицами также можно использовать объект ADO.NET **DataSet**.  Для получения дополнительной информации см. [Объекты DataSet, DataTable и DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).  
  
 В следующем примере кода поставщик MSDataShape используется, чтобы сформировать столбец раздела заказов по каждому клиенту из списка клиентов.  
  
```vb  
Using connection As OleDbConnection = New OleDbConnection( _  
  "Provider=MSDataShape;Data Provider=SQLOLEDB;" & _  
  "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind")  
  
Dim custCMD As OleDbCommand = New OleDbCommand( _  
  "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " & _  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " & _  
  "RELATE CustomerID TO CustomerID)", connection)  
connection.Open()  
  
Dim custReader As OleDbDataReader = custCMD.ExecuteReader()  
Dim orderReader As OleDbDataReader  
  
Do While custReader.Read()  
  Console.WriteLine("Orders for " & custReader.GetString(1))   
  ' custReader.GetString(1) = CompanyName  
  
  orderReader = custReader.GetValue(2)  
  ' custReader.GetValue(2) = Orders chapter as DataReader  
  
  Do While orderReader.Read()  
    Console.WriteLine(vbTab & orderReader.GetInt32(1))  
    ' orderReader.GetInt32(1) = OrderID  
  Loop  
  orderReader.Close()  
Loop  
' Make sure to always close readers and connections.  
custReader.Close()  
End Using  
```  
  
```csharp  
Using (OleDbConnection connection = new OleDbConnection(  
  "Provider=MSDataShape;Data Provider=SQLOLEDB;" +  
  "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind"));  
{  
OleDbCommand custCMD = new OleDbCommand(  
  "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " +  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " +  
  "RELATE CustomerID TO CustomerID)", connection);  
connection.Open();  
  
OleDbDataReader custReader = custCMD.ExecuteReader();  
OleDbDataReader orderReader;  
  
while (custReader.Read())  
{  
  Console.WriteLine("Orders for " + custReader.GetString(1));   
  // custReader.GetString(1) = CompanyName  
  
  orderReader = (OleDbDataReader)custReader.GetValue(2);        
  // custReader.GetValue(2) = Orders chapter as DataReader  
  
  while (orderReader.Read())  
    Console.WriteLine("\t" + orderReader.GetInt32(1));          
    // orderReader.GetInt32(1) = OrderID  
  orderReader.Close();  
}  
// Make sure to always close readers and connections.  
custReader.Close();  
}  
```  
  
## Возвращение результатов при помощи Oracle REF CURSOR  
 Поставщик данных .NET Framework для Oracle поддерживает использование параметров Oracle REF CURSOR для возвращения результата запроса.  Параметр Oracle REF CURSOR возвращается в виде объекта <xref:System.Data.OracleClient.OracleDataReader>.  
  
 Объект **OracleDataReader**, который представляет параметр Oracle REF CURSOR, можно получить с помощью метода <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>. Кроме того, также можно указать экземпляр <xref:System.Data.OracleClient.OracleCommand>, который возвращает один или несколько параметров Oracle REF CURSOR в виде **SelectCommand** для адаптера <xref:System.Data.OracleClient.OracleDataAdapter>, используемого, чтобы заполнить набор данных <xref:System.Data.DataSet>.  
  
 Чтобы получить доступ к параметру REF CURSOR, возвращенному из источника данных Oracle, создайте экземпляр **OracleCommand** для данного запроса и добавьте выходной параметр, устанавливающий ссылку между REF CURSOR и коллекцией **Parameters** данного экземпляра **OracleCommand**.  Имя параметра должно соответствовать имени параметра REF CURSOR, используемого в запросе.  В качестве типа параметра установите **OracleType.Cursor**.  Метод **ExecuteReader** данного экземпляра **OracleCommand** возвратит объект **OracleDataReader** для параметра REF CURSOR.  
  
 Если экземпляр **OracleCommand** возвращает несколько параметров REF CURSOR, добавьте несколько выходных параметров.  Доступ к разным параметрам REF CURSOR можно получать с помощью метода **OracleCommand.ExecuteReader**.  Вызов метода **ExecuteReader** возвращает объект **OracleDataReader**, ссылающийся на первый параметр REF CURSOR.  Затем можно вызвать метод **OracleDataReader.NextResult**, чтобы получить доступ к последующим параметрам REF CURSOR.  Несмотря на то, что параметры в коллекции **OracleCommand.Parameters** соответствуют выходным параметрам REF CURSOR по имени, объект **OracleDataReader** получает к ним доступ в порядке их добавления в коллекцию **Parameters**.  
  
 Например, рассмотрим следующий пакет и текст пакета Oracle.  
  
```  
CREATE OR REPLACE PACKAGE CURSPKG AS   
  TYPE T_CURSOR IS REF CURSOR;   
  PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,   
    DEPTCURSOR OUT T_CURSOR);   
END CURSPKG;  
  
CREATE OR REPLACE PACKAGE BODY CURSPKG AS   
  PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,   
    DEPTCURSOR OUT T_CURSOR)   
  IS   
  BEGIN   
    OPEN EMPCURSOR FOR SELECT * FROM DEMO.EMPLOYEE;   
    OPEN DEPTCURSOR FOR SELECT * FROM DEMO.DEPARTMENT;   
  END OPEN_TWO_CURSORS;   
END CURSPKG;   
```  
  
 В следующем коде создается экземпляр **OracleCommand**, который возвращает параметры REF CURSOR из предыдущего пакета Oracle путем добавления двух параметров типа **OracleType.Cursor** в коллекцию **Parameters**.  
  
```vb  
Dim cursCmd As OracleCommand = New OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn)  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
```  
  
```csharp  
OracleCommand cursCmd = new OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn);  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
```  
  
 В следующем коде возвращаются результаты предыдущей команды при помощи методов **Read** и **NextResult** объекта **OracleDataReader**.  Параметры REF CURSOR возвращаются по порядку.  
  
```vb  
oraConn.Open()  
  
Dim cursCmd As OracleCommand = New OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn)  
cursCmd.CommandType = CommandType.StoredProcedure  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
  
Dim reader As OracleDataReader = cursCmd.ExecuteReader()  
  
Console.WriteLine(vbCrLf & "Emp ID" & vbTab & "Name")  
  
Do While reader.Read()  
  Console.WriteLine("{0}" & vbTab & "{1}, {2}", reader.GetOracleNumber(0), reader.GetString(1), reader.GetString(2))  
Loop  
  
reader.NextResult()  
  
Console.WriteLine(vbCrLf & "Dept ID" & vbTab & "Name")  
  
Do While reader.Read()  
  Console.WriteLine("{0}" & vbTab & "{1}", reader.GetOracleNumber(0), reader.GetString(1))  
Loop  
' Make sure to always close readers and connections.  
reader.Close()  
oraConn.Close()  
```  
  
```csharp  
oraConn.Open();  
  
OracleCommand cursCmd = new OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn);  
cursCmd.CommandType = CommandType.StoredProcedure;  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
  
OracleDataReader reader = cursCmd.ExecuteReader();  
  
Console.WriteLine("\nEmp ID\tName");  
  
while (reader.Read())  
  Console.WriteLine("{0}\t{1}, {2}", reader.GetOracleNumber(0), reader.GetString(1), reader.GetString(2));  
  
reader.NextResult();  
  
Console.WriteLine("\nDept ID\tName");  
  
while (reader.Read())  
  Console.WriteLine("{0}\t{1}", reader.GetOracleNumber(0), reader.GetString(1));  
// Make sure to always close readers and connections.  
reader.Close();  
oraConn.Close();  
```  
  
 В следующем примере предыдущая команда используется для заполнения объекта **DataSet** результатами пакета Oracle.  
  
> [!NOTE]
>  Во избежание исключения **OverflowException** рекомендуется также производить преобразования из типа Oracle NUMBER в допустимый тип .NET Framework перед сохранением значения в **DataRow**.  Событие **FillError** можно использовать, чтобы определять, появилось ли исключение **OverflowException**.  Дополнительные сведения о событии **FillError** см. в разделе [Обработка событий DataAdapter](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).  
  
```vb  
Dim ds As DataSet = New DataSet()  
  
Dim adapter As OracleDataAdapter = New OracleDataAdapter(cursCmd)  
adapter.TableMappings.Add("Table", "Employees")  
adapter.TableMappings.Add("Table1", "Departments")  
  
adapter.Fill(ds)  
```  
  
```csharp  
DataSet ds = new DataSet();  
  
OracleDataAdapter adapter = new OracleDataAdapter(cursCmd);  
adapter.TableMappings.Add("Table", "Employees");  
adapter.TableMappings.Add("Table1", "Departments");  
  
adapter.Fill(ds);  
```  
  
## См. также  
 [Working with DataReaders](http://msdn.microsoft.com/ru-ru/126a966a-d08d-4d22-a19f-f432908b2b54)   
 [Объекты DataAdapter и DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)   
 [Команды и параметры](../../../../docs/framework/data/adonet/commands-and-parameters.md)   
 [Получение сведений о схеме базы данных](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)