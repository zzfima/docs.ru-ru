---
title: Извлечение данных с помощью объекта DataReader
ms.date: 10/29/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 88cd85ce343aaab08b944f81c9659918014da0a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149028"
---
# <a name="retrieve-data-using-a-datareader"></a>Извлечение данных с помощью DataReader
Для получения данных с помощью **DataReader**создайте экземпляр объекта **командования,** а затем создайте **DataReader,** позвонив **в Command.ExecuteReader** для извлечения строк из источника данных. **DataReader** обеспечивает небуферированный поток данных, что позволяет процедурной логике эффективно обрабатывать результаты из источника данных последовательно. **DataReader** является хорошим выбором при извлечении больших объемов данных, поскольку данные не кэшируются в памяти.

Ниже приведен пример, иллюстрирующий использование **DataReader,** где `reader` он представляет собой действительный DataReader и `command` представляет собой допустимый объект Командного управления.  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

Используйте метод **DataReader.Read** для получения строки из результатов запроса. Вы можете получить доступ к каждой колонке возвращенной строки, передавая имя или ординаторский номер столбца **DataReader.** Однако, для лучшей производительности, **DataReader** предоставляет ряд методов, которые позволяют получить доступ к значениям столбцов в их родных типах данных **(GetDateTime,** **GetDouble**, **GetGuid**, **GetInt32**и так далее). Для списка набранных методов доступа для данных поставщика <xref:System.Data.OleDb.OleDbDataReader> <xref:System.Data.SqlClient.SqlDataReader>данных **конкретных DataReaders**, см. Использование набранных методов доступа, когда вы знаете, что базовый тип данных уменьшает количество преобразования типа, необходимого при извлечении значения столбца.  
  
 Следующий пример итерирует объект **DataReader** и возвращает по две столбцы из каждой строки.  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a>Закрытие DataReader  
 Всегда вызывайте метод **Close,** когда вы закончите использовать объект **DataReader.**  
  
 Если **команда** содержит параметры вывода или значения возврата, эти значения недоступны до закрытия **DataReader.**  
  
 В то время как **DataReader** открыт, **соединение** используется исключительно тем **DataReader**. Вы не можете выполнять какие-либо команды для **соединения,** включая создание другого **DataReader,** до тех пор, пока исходный **DataReader** не будет закрыт.  
  
> [!NOTE]
> Не вызывайте **Close** или **Dispose** на **соединение,** **DataReader**или любой другой управляемый объект в методе **завершения** вашего класса. В методе завершения следует только освобождать неуправляемые ресурсы, которыми ваш класс непосредственно владеет. Если ваш класс не владеет неуправляемыми ресурсами, не включайте метод **завершения** в определение класса. Для получения дополнительной информации, см [Мусорная коллекция](../../../standard/garbage-collection/index.md).  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a>Получение нескольких наборов результатов с помощью NextResult  
 Если **DataReader** возвращает несколько наборов результатов, вызовите метод **NextResult,** чтобы последовательно итерировать через наборы результатов. В следующем примере показан объект <xref:System.Data.SqlClient.SqlDataReader>, обрабатывающий результаты двух инструкций SELECT с помощью метода <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a>Получение информации о схемах от DataReader  
 Во время открытия **DataReader** можно получить информацию о результатах схемы с помощью метода **GetSchemaTable.** **GetSchemaTable** возвращает <xref:System.Data.DataTable> объект, населенный строками и столбцов, содержащими информацию о схеме для текущего набора результатов. **DataTable** содержит по одной строке для каждого столбца набора результатов. Каждая колонка таблицы схемы отображает свойство столбцов, возвращенных в ряды набора результатов, где **ColumnName** является именем свойства, а значение столбца — значением свойства. Следующий пример выписывает информацию о схеме для **DataReader**.  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a>Работа с главами OLE DB  
 Иерархические наборы строк или глав (тип OLE DB **DBTYPE_HCHAPTER,** ADO type <xref:System.Data.OleDb.OleDbDataReader> **adChapter),** можно получить с помощью . Когда запрос, включающий главу, возвращается в качестве **DataReader,** глава возвращается в качестве столбца в этом **DataReader** и подвергается воздействию объекта **DataReader.**  
  
 ADO.NET **DataSet** также может использоваться для представления иерархических рядов с помощью отношений между родительскими и детскими отношениями между таблицами. Для получения дополнительной [DataSets, DataTables, and DataViews](./dataset-datatable-dataview/index.md)информации см.  
  
 В следующем примере кода поставщик MSDataShape используется, чтобы сформировать столбец раздела заказов по каждому клиенту из списка клиентов.  
  
```vb  
Using connection As OleDbConnection = New OleDbConnection(
    "Provider=MSDataShape;Data Provider=SQLOLEDB;" &
    "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind")

    Using custCMD As OleDbCommand = New OleDbCommand(
        "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " &
        "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " &
        "RELATE CustomerID TO CustomerID)", connection)

        connection.Open()

        Using custReader As OleDbDataReader = custCMD.ExecuteReader()

            Do While custReader.Read()
                Console.WriteLine("Orders for " & custReader.GetString(1))
                ' custReader.GetString(1) = CompanyName  

                Using orderReader As OleDbDataReader = custReader.GetValue(2)
                    ' custReader.GetValue(2) = Orders chapter as DataReader  

                    Do While orderReader.Read()
                        Console.WriteLine(vbTab & orderReader.GetInt32(1))
                        ' orderReader.GetInt32(1) = OrderID  
                    Loop
                    orderReader.Close()
                End Using
            Loop
            ' Make sure to always close readers and connections.  
            custReader.Close()
        End Using
    End Using
End Using
```  
  
```csharp  
using (OleDbConnection connection = new OleDbConnection(
    "Provider=MSDataShape;Data Provider=SQLOLEDB;" +
    "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind"))
{
    using (OleDbCommand custCMD = new OleDbCommand(
        "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " +
        "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " +
        "RELATE CustomerID TO CustomerID)", connection))
    {
        connection.Open();

        using (OleDbDataReader custReader = custCMD.ExecuteReader())
        {

            while (custReader.Read())
            {
                Console.WriteLine("Orders for " + custReader.GetString(1));
                // custReader.GetString(1) = CompanyName  

                using (OleDbDataReader orderReader = (OleDbDataReader)custReader.GetValue(2))
                {
                    // custReader.GetValue(2) = Orders chapter as DataReader  

                    while (orderReader.Read())
                        Console.WriteLine("\t" + orderReader.GetInt32(1));
                    // orderReader.GetInt32(1) = OrderID  
                    orderReader.Close();
                }
            }
            // Make sure to always close readers and connections.  
            custReader.Close();
        }
    }
}
```  
  
## <a name="returning-results-with-oracle-ref-cursors"></a>Возвращение результатов с Oracle REF CURSORs  
 Поставщик данных .NET Framework для Oracle поддерживает использование параметров Oracle REF CURSOR для возвращения результата запроса. Параметр Oracle REF CURSOR возвращается в виде объекта <xref:System.Data.OracleClient.OracleDataReader>.  
  
 Вы можете получить <xref:System.Data.OracleClient.OracleDataReader> объект, представляющий Oracle REF CURSOR, с помощью метода. <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> Вы также можете <xref:System.Data.OracleClient.OracleCommand> указать, что возвращает один или несколько Oracle <xref:System.Data.OracleClient.OracleDataAdapter> REF <xref:System.Data.DataSet>CURSORs в качестве **SelectCommand** для используемого для заполнения .  
  
 Чтобы получить доступ к REF CURSOR, возвращенным из источника данных Oracle, создайте <xref:System.Data.OracleClient.OracleCommand> для запроса <xref:System.Data.OracleClient.OracleCommand.Parameters> и добавьте параметр вывода, который ссылается на REF CURSOR в коллекцию вашего. <xref:System.Data.OracleClient.OracleCommand> Имя параметра должно соответствовать имени параметра REF CURSOR, используемого в запросе. Установите тип параметра. <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> Метод <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> вашего <xref:System.Data.OracleClient.OracleCommand> возврата <xref:System.Data.OracleClient.OracleDataReader> для REF CURSOR.  
  
 Если <xref:System.Data.OracleClient.OracleCommand> возвращается несколько REF CURSORS, добавьте несколько параметров вывода. Вы можете получить доступ к различным REF CURSORs, позвонив по методу. <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> Призыв к <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> возврату <xref:System.Data.OracleClient.OracleDataReader> ссылки на первый REF CURSOR. Затем можно вызвать <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> метод для доступа к последующим REF CURSORs. Хотя параметры в <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> вашей коллекции соответствуют параметрам вывода <xref:System.Data.OracleClient.OracleDataReader> REF CURSOR по имени, доступ <xref:System.Data.OracleClient.OracleCommand.Parameters> к ним в порядке, в котором они были добавлены в коллекцию.  
  
 Например, рассмотрим следующий пакет и текст пакета Oracle.  
  
```sql
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
  
 Следующий код <xref:System.Data.OracleClient.OracleCommand> создает, что возвращает REF CURSORs из предыдущего пакета <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> Oracle, добавив два параметра типа в коллекцию. <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType>  
  
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
  
 Следующий код возвращает результаты предыдущей <xref:System.Data.OracleClient.OracleDataReader.Read> <xref:System.Data.OracleClient.OracleDataReader.NextResult> команды с <xref:System.Data.OracleClient.OracleDataReader>использованием и методов . Параметры REF CURSOR возвращаются по порядку.  
  
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
  
 В следующем примере предыдущая команда <xref:System.Data.DataSet> заполняет результаты пакета Oracle.  
  
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

> [!NOTE]
> Чтобы избежать **OverflowException,** мы рекомендуем также обрабатывать любое преобразование из типа Oracle NUMBER в действительный тип рамочного соглашения .NET, прежде чем хранить значение в <xref:System.Data.DataRow>. Событие можно <xref:System.Data.Common.DataAdapter.FillError> использовать, чтобы определить, произошло ли **переполнение.** Для получения дополнительной <xref:System.Data.Common.DataAdapter.FillError> информации о событии см. [Handling DataAdapter Events](handling-dataadapter-events.md)  
  
## <a name="see-also"></a>См. также раздел

- [Объекты DataAdapter и DataReader](dataadapters-and-datareaders.md)
- [Команды и параметры](commands-and-parameters.md)
- [Извлечение сведений о схеме базы данных](retrieving-database-schema-information.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
