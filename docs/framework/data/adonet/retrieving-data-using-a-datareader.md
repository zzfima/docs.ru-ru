---
title: Извлечение данных с помощью объекта DataReader
ms.date: 10/259/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: c97c30d77551f519777afa6efd31d507b3f21851
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53155357"
---
# <a name="retrieve-data-using-a-datareader"></a>Извлечение данных с помощью объекта DataReader
Для получения данных с помощью **DataReader**, создайте экземпляр **команда** объекта, а затем создайте **DataReader** путем вызова **Command.ExecuteReader**  для получения строк из источника данных. **DataReader** предоставляет небуферизованный поток данных, позволяющий процедурам последовательно обрабатывать результаты из источника данных. **DataReader** хорошо подходит при извлечении больших объемов данных, поскольку данные не кэшируются в памяти.

В следующем примере демонстрируется использование **DataReader**, где `reader` представляет допустимый DataReader и `command` представляет допустимый объект Command.  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

Используйте **DataReader.Read** метод для получения строки из результатов запроса. Можно получить доступ к каждого столбца возвращенной строки, передав имя или порядковый номер столбца, **DataReader**. Тем не менее, для наилучшей производительности **DataReader** предоставляет ряд методов, которые дают возможность обращаться к значениям столбцов в собственных типах данных (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, и так далее). Список типизированных методов доступа для конкретных поставщиков данных **объекты DataReader**, см. в разделе <xref:System.Data.OleDb.OleDbDataReader> и <xref:System.Data.SqlClient.SqlDataReader>. Тип с помощью типизированных методов доступа, когда вы знаете базовых данных и сокращает объем преобразований типов, необходимых при извлечении значения столбца.  
  
 В следующем примере просматриваются **DataReader** и возвращает два столбца из каждой строки.  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a>Закрытие DataReader  
 Всегда вызывайте метод **закрыть** метод после завершения с помощью **DataReader** объекта.  
  
 Если ваш **команда** содержит выходные данные параметров или возвращаемых значений, эти значения доступны только **DataReader** закрыт.  
  
 Хотя **DataReader** открыт, **подключения** используется исключительно этим объектом **DataReader**. Невозможно выполнить команды для **подключения**, включая создание еще одного **DataReader**, пока исходный **DataReader** закрыт.  
  
> [!NOTE]
>  Не вызывайте **закрыть** или **Dispose** на **подключения**, **DataReader**, или любого другого управляемого объекта в **Finalize**  метод класса. В методе завершения следует только освобождать неуправляемые ресурсы, которыми ваш класс непосредственно владеет. Если ваш класс не владеет неуправляемые ресурсы, не включайте **Finalize** метод в определении класса. Дополнительные сведения см. в разделе [мусора](../../../../docs/standard/garbage-collection/index.md).  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a>Извлечение нескольких результирующих наборов с помощью NextResult  
 Если **DataReader** возвращает несколько результирующих наборов, вызов **NextResult** последовательно задает метод для выполнения итерации по результат. В следующем примере показан объект <xref:System.Data.SqlClient.SqlDataReader>, обрабатывающий результаты двух инструкций SELECT с помощью метода <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a>Получение данных схемы от DataReader  
 Хотя **DataReader** является открытым, можно получить данные схемы о текущем результирующем наборе с помощью **GetSchemaTable** метод. **GetSchemaTable** возвращает <xref:System.Data.DataTable> заполненный строк и столбцов, содержащих сведения о схеме для текущего результирующего набора. **DataTable** содержит по одной строке для каждого столбца результирующего набора. Каждый столбец в таблице схемы соответствует свойству столбцы, возвращаемые в наборе строк результата, где **ColumnName** — это имя свойства и значением столбца является значением свойства. Следующий пример записывает сведения о схеме для **DataReader**.  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a>Работа с главы OLE DB  
 Иерархические наборы строк, или разделы (тип OLE DB **DBTYPE_HCHAPTER**, тип ADO **adChapter**), можно получить с помощью <xref:System.Data.OleDb.OleDbDataReader>. Когда запрос, содержащий раздел возвращается в виде **DataReader**, раздел возвращается в виде столбца в этом **DataReader** и указывается в виде **DataReader** объекта.  
  
 ADO.NET **набора данных** также может использоваться для представления иерархических наборов строк с помощью родительско дочерних отношений между таблицами. Дополнительные сведения см. в разделе [наборы данных, таблицы данных и объекты DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).  
  
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
  
## <a name="returning-results-with-oracle-ref-cursors"></a>Возвращение результатов при помощи параметров REF CURSOR Oracle  
 Поставщик данных .NET Framework для Oracle поддерживает использование параметров Oracle REF CURSOR для возвращения результата запроса. Параметр Oracle REF CURSOR возвращается в виде объекта <xref:System.Data.OracleClient.OracleDataReader>.  
  
 Вы можете получить <xref:System.Data.OracleClient.OracleDataReader> , представляющий Oracle REF CURSOR с использованием <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> метод. Можно также указать <xref:System.Data.OracleClient.OracleCommand> , возвращающий один или несколько REF CURSOR Oracle в виде **SelectCommand** для <xref:System.Data.OracleClient.OracleDataAdapter> используются для заполнения <xref:System.Data.DataSet>.  
  
 Чтобы получить доступ к REF CURSOR, возвращенному из источника данных Oracle, создайте <xref:System.Data.OracleClient.OracleCommand> запроса и добавьте выходной параметр, который ссылается на REF CURSOR <xref:System.Data.OracleClient.OracleCommand.Parameters> коллекцию вашей <xref:System.Data.OracleClient.OracleCommand>. Имя параметра должно соответствовать имени параметра REF CURSOR, используемого в запросе. Задайте тип параметра для <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>. <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> Метод вашей <xref:System.Data.OracleClient.OracleCommand> возвращает <xref:System.Data.OracleClient.OracleDataReader> для параметра REF CURSOR.  
  
 Если ваш <xref:System.Data.OracleClient.OracleCommand> возвращает несколько параметров REF CURSOR, добавьте несколько выходных параметров. Доступны различные параметры REF CURSOR, вызвав <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> метод. Вызов <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> возвращает <xref:System.Data.OracleClient.OracleDataReader> ссылки на первый параметр REF CURSOR. Затем можно вызвать <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> метод для доступа к последующих параметров REF CURSOR. Хотя параметры в вашей <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> соответствуют REF CURSOR выходных параметров по имени, <xref:System.Data.OracleClient.OracleDataReader> получает доступ к ним в порядке, в котором они были добавлены к <xref:System.Data.OracleClient.OracleCommand.Parameters> коллекции.  
  
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
  
 Следующий код создает <xref:System.Data.OracleClient.OracleCommand> , возвращает параметры REF CURSOR из предыдущего пакета Oracle путем добавления двух параметров типа <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> для <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> коллекции.  
  
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
  
 Следующий код возвращает результаты предыдущей команды при помощи <xref:System.Data.OracleClient.OracleDataReader.Read> и <xref:System.Data.OracleClient.OracleDataReader.NextResult> методы <xref:System.Data.OracleClient.OracleDataReader>. Параметры REF CURSOR возвращаются по порядку.  
  
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
  
 В следующем примере предыдущая команда используется для заполнения <xref:System.Data.DataSet> с результатами пакета Oracle.  
  
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
>  Чтобы избежать **OverflowException**, рекомендуется также производить преобразования из типа Oracle NUMBER в допустимый тип .NET Framework перед сохранением значения в <xref:System.Data.DataRow>. Можно использовать <xref:System.Data.Common.DataAdapter.FillError> событий на предмет **OverflowException** произошла. Дополнительные сведения о <xref:System.Data.Common.DataAdapter.FillError> событий, см. в разделе [обработка событий DataAdapter](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).  
  
## <a name="see-also"></a>См. также  
 [Работа с объекты DataReader](https://msdn.microsoft.com/library/126a966a-d08d-4d22-a19f-f432908b2b54)  
 [Объекты DataAdapter и DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [Команды и параметры](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [Извлечение сведений о схеме базы данных](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
