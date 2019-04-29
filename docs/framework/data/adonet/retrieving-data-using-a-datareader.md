---
title: Извлечение данных с помощью объекта DataReader
ms.date: 10/29/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 8063f239123ec1a2f2650adf9d76f7ceaaa50673
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61664264"
---
# <a name="retrieve-data-using-a-datareader"></a>Извлечение данных с помощью объекта DataReader
Для получения данных с помощью **DataReader** создайте экземпляр объекта **Command**, а затем создайте **DataReader** путем вызова **Command.ExecuteReader** для получения строк из источника данных. **DataReader** предоставляет небуферизованный поток данных, позволяющий эффективно реализовать процедурную логику последовательной обработки результатов из источника данных. **DataReader** хорошо подходит для извлечения больших объемов данных, поскольку данные не кэшируются в памяти.

В следующем примере демонстрируется использование **DataReader**, где `reader` представляет допустимый DataReader и `command` представляет допустимый объект Command.  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

Используйте метод **DataReader.Read** для получения строки из результатов запроса. Можно получить доступ к каждому столбцу возвращенной строки, передав **DataReader** имя или порядковый номер столбца. Тем не менее, для наилучшей производительности **DataReader** предоставляет ряд методов, которые дают возможность обращаться к значениям столбцов в собственных типах данных (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, и так далее). Список типизированных методов доступа для объектов **DataReader** конкретных поставщиков данных см. в разделах <xref:System.Data.OleDb.OleDbDataReader> и <xref:System.Data.SqlClient.SqlDataReader>. Использование типизированных методов доступа при известном базовом типе данных сокращает объем преобразований типов, необходимых при извлечении значения столбца.  
  
 В следующем примере осуществляется проход по **DataReader** и возврат двух столбцов из каждой строки.  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a>Закрытие DataReader  
 Всегда вызывайте метод **Close** после завершения использования объекта **DataReader**.  
  
 Если ваш объект **Command** содержит выходные параметры или возвращаемые значения, они будут доступны только после закрытия **DataReader**.  
  
 Когда **DataReader** открыт, объект **Connection** монопольно используется этим объектом **DataReader**. До тех пор, пока исходный объект **DataReader** не закрыт, для объекта **Connection** невозможно выполнение команд, в том числе создание еще одного **DataReader**.  
  
> [!NOTE]
>  Не вызывайте **Close** или **Dispose** для объектов **Connection**, **DataReader** или любого другого управляемого объекта в методе **Finalize**  класса. В методе завершения следует освобождать только неуправляемые ресурсы, которыми ваш класс непосредственно владеет. Если ваш класс не владеет неуправляемыми ресурсами, не включайте в определение класс метод **Finalize**. Дополнительные сведения см. в разделе [Сборка мусора](../../../../docs/standard/garbage-collection/index.md).  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a>Извлечение нескольких результирующих наборов с помощью NextResult  
 Если **DataReader** возвращает несколько результирующих наборов, используйте метод **NextResult** для последовательного прохода по ним. В следующем примере показана обработка результатов двух инструкций SELECT в <xref:System.Data.SqlClient.SqlDataReader> с помощью метода <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a>Получение сведений о схеме из DataReader  
 Пока **DataReader** открыт, можно получить сведения о схеме для текущего результирующего набора с помощью метода **GetSchemaTable**. **GetSchemaTable** возвращает объект <xref:System.Data.DataTable>, заполненный строками и столбцами, содержащими сведения о схеме для текущего результирующего набора. **DataTable** содержит по одной строке для каждого столбца результирующего набора. Каждый столбец в таблице схемы соответствует свойству столбца, возвращаемого в строках результирующего набора, где **ColumnName** — это имя свойства, а значением столбца является значение свойства. Следующий пример выводит сведения о схеме для **DataReader**.  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a>Работа с разделами OLE DB  
 Иерархические наборы строк, или разделы (тип OLE DB **DBTYPE_HCHAPTER**, тип ADO **adChapter**), можно получить с помощью <xref:System.Data.OleDb.OleDbDataReader>. Когда для возврата результатов запроса, содержащего раздел, используется **DataReader**, раздел возвращается в виде столбца в этом **DataReader** и представляется в виде объекта **DataReader**.  
  
 **DataSet** из ADO.NET также может использоваться для представления иерархических наборов строк с использованием отношений "родитель — потомок" между таблицами. Дополнительные сведения см. в разделе [Наборы данных, таблицы данных и объекты DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).  
  
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
  
## <a name="returning-results-with-oracle-ref-cursors"></a>Возврат результатов с использованием параметров REF CURSOR Oracle  
 Поставщик данных .NET Framework для Oracle поддерживает использование параметров Oracle REF CURSOR для возврата результата запроса. Параметр Oracle REF CURSOR возвращается в виде объекта <xref:System.Data.OracleClient.OracleDataReader>.  
  
 Вы можете получить объект <xref:System.Data.OracleClient.OracleDataReader>, представляющий Oracle REF CURSOR, используя метод <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>. Можно также указать <xref:System.Data.OracleClient.OracleCommand>, возвращающий один или несколько REF CURSOR Oracle, в качестве **SelectCommand** для <xref:System.Data.OracleClient.OracleDataAdapter>, используемого для заполнения <xref:System.Data.DataSet>.  
  
 Чтобы получить доступ к REF CURSOR, возвращенному из источника данных Oracle, создайте запрос <xref:System.Data.OracleClient.OracleCommand> и добавьте выходной параметр, который ссылается на REF CURSOR, в коллекцию <xref:System.Data.OracleClient.OracleCommand.Parameters> вашего объекта <xref:System.Data.OracleClient.OracleCommand>. Имя параметра должно соответствовать имени параметра REF CURSOR, используемого в запросе. В качестве типа параметра установите <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>. Метод <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> вашего объекта <xref:System.Data.OracleClient.OracleCommand> возвращает <xref:System.Data.OracleClient.OracleDataReader> для параметра REF CURSOR.  
  
 Если ваш объект <xref:System.Data.OracleClient.OracleCommand> возвращает несколько параметров REF CURSOR, добавьте несколько выходных параметров. Можно получить доступ к разным параметрам REF CURSOR, вызвав метод <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType>. Вызов <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> возвращает <xref:System.Data.OracleClient.OracleDataReader>, ссылающийся на первый REF CURSOR. Затем можно вызвать метод <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> для доступа к следующим параметрам REF CURSOR. Хотя параметры в вашей коллекции <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> соответствуют выходным параметрам REF CURSOR по имени, <xref:System.Data.OracleClient.OracleDataReader> осуществляет доступ к ним в том порядке, в котором они были добавлены в коллекцию <xref:System.Data.OracleClient.OracleCommand.Parameters>.  
  
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
  
 Следующий код создает команду <xref:System.Data.OracleClient.OracleCommand>, которая возвращает параметры REF CURSOR из приведенного выше пакета Oracle путем добавления двух параметров типа <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> в коллекцию <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType>.  
  
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
  
 Следующий код возвращает результаты приведенной выше команды, используя методы <xref:System.Data.OracleClient.OracleDataReader.Read> и <xref:System.Data.OracleClient.OracleDataReader.NextResult> объекта <xref:System.Data.OracleClient.OracleDataReader>. Параметры REF CURSOR возвращаются по порядку.  
  
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
  
 В следующем примере приведенная выше команда используется для заполнения <xref:System.Data.DataSet> результатами пакета Oracle.  
  
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
>  Чтобы избежать **OverflowException**, рекомендуется также производить преобразование из типа Oracle NUMBER в допустимый тип .NET Framework перед сохранением значения в <xref:System.Data.DataRow>. Чтобы отследить возникновение **OverflowException**, можно использовать событие <xref:System.Data.Common.DataAdapter.FillError>. Дополнительные сведения о событии <xref:System.Data.Common.DataAdapter.FillError> см. в разделе [Обработка событий DataAdapter](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).  
  
## <a name="see-also"></a>См. также

- [Объекты DataAdapter и DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [Команды и параметры](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [Извлечение сведений о схеме базы данных](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
