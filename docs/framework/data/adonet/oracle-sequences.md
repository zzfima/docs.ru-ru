---
title: Последовательности Oracle
ms.date: 03/30/2017
ms.assetid: 27cd371d-8252-414d-b5b2-5d31fa44b585
ms.openlocfilehash: 9f89234168351191c63d81fd4f3b68b01bfac2da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358616"
---
# <a name="oracle-sequences"></a>Последовательности Oracle
Поставщик данных .NET Framework для Oracle поддерживает получение сформированных на сервере ключевых значений последовательности Oracle после выполнения вставок с помощью <xref:System.Data.OracleClient.OracleDataAdapter>.  
  
 SQL Server и Oracle поддерживают автоматическое создание столбцов автоприращения, которые могут использоваться в качестве первичных ключей. Эти значения формируются сервером по мере добавления строк в таблицу. В SQL Server задается свойство IDENTITY столбца, в Oracle создается последовательность. Разница между столбцами автоприращения в SQL Server и последовательностями в Oracle заключается в следующем.  
  
-   В SQL Server столбец помечается как столбец автоприращения, и SQL Server автоматически формирует для него новые значения при вставке новой строки.  
  
-   В Oracle создается последовательность новых значений для столбца таблицы, но отсутствует прямая связь между этой последовательностью и таблицей или столбцом. Последовательность Oracle является таким же объектом, как таблица или хранимая процедура.  
  
 При создании последовательности в базе данных Oracle можно определить ее начальное значение и приращение значений. Перед вставкой новых строк можно также запросить новые значения последовательности. Это означает, что код может получить ключевые значения для новых строк перед вставкой их в базу данных.  
  
 Дополнительные сведения о создании столбцов автоприращения с помощью SQL Server и ADO.NET см. в разделе [извлечение идентификации или значений автонумерации](../../../../docs/framework/data/adonet/retrieving-identity-or-autonumber-values.md) и [Создание столбцов AutoIncrement](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md).  
  
## <a name="example"></a>Пример  
 В следующем примере на языке C# показано получение новых значений последовательности в базе данных Oracle. Пример ссылается на последовательность в запросе INSERT INTO, который используется для вставки новых строк, и возвращает значение последовательности, сформированное предложением RETURNING, впервые появившемся в Oracle10g. В примере добавляется набор новых строк в таблицу <xref:System.Data.DataTable> с помощью возможности автоприращения ADO.NET для формирования значений «местозаполнителей» первичного ключа. Обратите внимание, что значение приращения ADO.NET, сформированное для новых строк, представляет собой просто «местозаполнитель». Это означает, что база данных может сама сформировать эти значения вместо значений, созданных ADO.NET.  
  
 Перед вставкой ожидающих строк в базу данных пример отображает их содержимое на экране. Затем создается новый объект <xref:System.Data.OracleClient.OracleDataAdapter>, и его свойствам <xref:System.Data.OracleClient.OracleDataAdapter.InsertCommand%2A> и <xref:System.Data.OracleClient.OracleDataAdapter.UpdateBatchSize%2A> присваиваются значения. Пример применяет ту же логику, чтобы возвратить сформированные сервером значения с помощью выходных параметров. После этого пример выполняет вставку строк и отображает содержимое таблицы <xref:System.Data.DataTable>.  
  
```csharp  
public void OracleSequence(String connectionString)  
{  
   String insertString =   
      "INSERT INTO SequenceTest_Table (ID, OtherColumn)" +  
      "VALUES (SequenceTest_Sequence.NEXTVAL, :OtherColumn)" +  
      "RETURNING ID INTO :ID";  
  
   using (OracleConnection conn = new OracleConnection(connectionString))  
   {  
      //Open a connection.  
      conn.Open();  
      OracleCommand cmd = conn.CreateCommand();  
  
      // Prepare the database.  
      cmd.CommandText = "DROP SEQUENCE SequenceTest_Sequence";  
      try { cmd.ExecuteNonQuery(); } catch { }  
  
      cmd.CommandText = "DROP TABLE SequenceTest_Table";  
      try { cmd.ExecuteNonQuery(); } catch { }  
  
      cmd.CommandText = "CREATE TABLE SequenceTest_Table " +  
                     "(ID int PRIMARY KEY, OtherColumn varchar(255))";  
      cmd.ExecuteNonQuery();  
  
      cmd.CommandText = "CREATE SEQUENCE SequenceTest_Sequence " +  
                        "START WITH 100 INCREMENT BY 5";  
      cmd.ExecuteNonQuery();  
  
      DataTable testTable = new DataTable();  
      DataColumn column = testTable.Columns.Add("ID", typeof(int));  
      column.AutoIncrement = true;  
      column.AutoIncrementSeed = -1;  
      column.AutoIncrementStep = -1;  
      testTable.PrimaryKey = new DataColumn[] { column };  
      testTable.Columns.Add("OtherColumn", typeof(string));  
      for (int rowCounter = 1; rowCounter <= 15; rowCounter++)  
      {  
         testTable.Rows.Add(null, "Row #" + rowCounter.ToString());  
      }  
  
      Console.WriteLine("Before Update => ");  
      foreach (DataRow row in testTable.Rows)  
      {  
         Console.WriteLine("   {0} - {1}", row["ID"], row["OtherColumn"]);  
      }  
      Console.WriteLine();  
  
      cmd.CommandText =   
        "SELECT ID, OtherColumn FROM SequenceTest_Table";  
      OracleDataAdapter da = new OracleDataAdapter(cmd);  
      da.InsertCommand = new OracleCommand(insertString, conn);  
      da.InsertCommand.Parameters.Add(":ID", OracleType.Int32, 0, "ID");  
      da.InsertCommand.Parameters[0].Direction = ParameterDirection.Output;  
      da.InsertCommand.Parameters.Add(":OtherColumn", OracleType.VarChar, 255, "OtherColumn");  
      da.InsertCommand.UpdatedRowSource = UpdateRowSource.OutputParameters;  
      da.UpdateBatchSize = 10;  
  
      da.Update(testTable);  
  
      Console.WriteLine("After Update => ");  
      foreach (DataRow row in testTable.Rows)  
      {  
         Console.WriteLine("   {0} - {1}", row["ID"], row["OtherColumn"]);  
      }  
      // Close the connection.  
      conn.Close();  
   }  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Oracle и ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
