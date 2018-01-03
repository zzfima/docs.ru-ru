---
title: "Обновление источников данных с объектами DataAdapter"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d1bd9a8c-0e29-40e3-bda8-d89176b72fb1
caps.latest.revision: "8"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 44bd1672c6423277fa90eee98ce954e7c1c5334e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="updating-data-sources-with-dataadapters"></a>Обновление источников данных с объектами DataAdapter
Метод `Update` объекта <xref:System.Data.Common.DataAdapter> вызывается для решения задачи по передаче изменений из <xref:System.Data.DataSet> обратно в источник данных. Метод `Update`, как и метод `Fill`, принимает в качестве аргументов экземпляр `DataSet`, а также (необязательно) объект <xref:System.Data.DataTable> или имя `DataTable`. Экземпляр `DataSet` представляет собой объект `DataSet`, который содержит выполненные изменения, а `DataTable` указывает на таблицу, из которой должны быть получены эти изменения. Если ни один объект `DataTable` не задан, используется первый объект `DataTable` в `DataSet`.  
  
 При вызове метода `Update` в `DataAdapter` анализируются внесенные изменения и выполняется соответствующая команда (INSERT, UPDATE или DELETE). Если в `DataAdapter` обнаруживается изменение в <xref:System.Data.DataRow>, то в этом объекте используется команда <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A>, <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> или <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A> для обработки этого изменения. Это позволяет максимально повысить производительность приложения ADO.NET путем задания синтаксиса команды во время разработки, а также, по возможности, за счет применения хранимых процедур. Необходимо явно задавать команды перед вызовом `Update`. Если вызывается `Update`, и не существует подходящая команда для конкретного обновления (например, отсутствует `DeleteCommand` для удаленных строк), то активизируется исключение.  
  
> [!NOTE]
>  При использовании хранимых процедур SQL Server для изменения или удаления данных с помощью `DataAdapter` убедитесь, что в определении хранимой процедуры не указана инструкция SET NOCOUNT ON. В таком случае возвращается число затронутых строк, равное нулю, что `DataAdapter` интерпретирует как конфликт параллелизма. Это событие вызовет исключение <xref:System.Data.DBConcurrencyException>.  
  
 Параметры команды могут использоваться в целях указания входных и выходных значений для инструкции SQL или хранимой процедуры применительно к каждой модифицированной строке в `DataSet`. Дополнительные сведения см. в разделе [параметры DataAdapter](../../../../docs/framework/data/adonet/dataadapter-parameters.md).  
  
> [!NOTE]
>  Важно учитывать различие между обозначением строки как удаленной в <xref:System.Data.DataTable> и удалением этой строки. Если вызывается метод `Remove` или `RemoveAt`, строка немедленно удаляется. Любые соответствующие строки в серверном источнике данных остаются не затронутыми, если после этого будет передано значение `DataTable` или `DataSet` в `DataAdapter` и вызван метод `Update`. Если же используется метод `Delete`, то строка остается в `DataTable` и отмечается как предназначенная для удаления. Если после этого будет передано значение `DataTable` или `DataSet` в `DataAdapter` и вызван метод `Update`, то соответствующая строка в серверном источнике данных становится удаленной.  
  
 Если значение `DataTable` сопоставляется или создается на основе одной таблицы базы данных, то можно воспользоваться тем, что объект <xref:System.Data.Common.DbCommandBuilder> автоматически создает объекты `DeleteCommand`, `InsertCommand` и `UpdateCommand` для `DataAdapter`. Дополнительные сведения см. в разделе [создание команд с помощью построителей команд](../../../../docs/framework/data/adonet/generating-commands-with-commandbuilders.md).  
  
## <a name="using-updatedrowsource-to-map-values-to-a-dataset"></a>Использование объекта UpdatedRowSource для сопоставления значений с набором данных  
 Можно управлять тем, как значения, возвращенные из источника данных, сопоставляются в обратном направлении с `DataTable` вслед за вызовом метода Update объекта `DataAdapter` с использованием свойства <xref:System.Data.Common.DbCommand.UpdatedRowSource%2A> объекта <xref:System.Data.Common.DbCommand>. Задавая значение свойства `UpdatedRowSource` равным одному из значений перечисления <xref:System.Data.UpdateRowSource>, можно управлять тем, должны ли пропускаться выходные параметры, возвращаемые командами `DataAdapter`, или применяться к изменившейся строке в `DataSet`. Можно также указать, применяется ли первая возвращенная строка (если она существует) к изменившейся строке в `DataTable`.  
  
 В следующей таблице приведено описание различных значений перечисления `UpdateRowSource` и показано, как они влияют на поведение команды, используемой в сочетании с `DataAdapter`.  
  
|Перечисление UpdatedRowSource|Описание|  
|----------------------------------|-----------------|  
|<xref:System.Data.UpdateRowSource.Both>|И выходные параметры, и первая строка возвращенного результирующего набора могут быть сопоставлены с модифицированной строкой в `DataSet`.|  
|<xref:System.Data.UpdateRowSource.FirstReturnedRecord>|Только данные из первой строки возвращенного результирующего набора могут быть сопоставлены с модифицированной строкой в `DataSet`.|  
|<xref:System.Data.UpdateRowSource.None>|Любые выходные параметры или строки возвращенного результирующего набора пропускаются.|  
|<xref:System.Data.UpdateRowSource.OutputParameters>|Только выходные параметры могут быть сопоставлены с модифицированной строкой в `DataSet`.|  
  
 Метод `Update` позволяет решить задачу по передаче внесенных изменений обратно в источник данных; но может оказаться так, что другие клиенты уже внесли изменения в данные источника данных с того момента, как последний раз было осуществлено заполнение `DataSet`. Чтобы обновить применяемый объект `DataSet` с использованием текущих данных, воспользуйтесь `DataAdapter` и методом `Fill`. Произойдет добавление новых строк к таблице, а обновленная информация будет включена в существующие строки. Метод `Fill` определяет, должна ли быть добавлена новая строка или обновлена существующая строка, путем проверки значений первичного ключа в строках объекта `DataSet` и в строках, возвращенных `SelectCommand`. Если в методе `Fill` обнаруживается значение первичного ключа какой-то строки в `DataSet`, которое совпадает со значением первичного ключа строки в результатах, возвращенных `SelectCommand`, то метод обновляет существующую строку на основании данных из строки, возвращенной `SelectCommand`, и задает значение <xref:System.Data.DataRow.RowState%2A> существующей строки, равное `Unchanged`. Если строка, возвращенная `SelectCommand`, имеет значение первичного ключа, не совпадающее ни с одним из значений первичного ключа в строках в `DataSet`, то метод `Fill` добавляет новую строку со значением `RowState`, равным `Unchanged`.  
  
> [!NOTE]
>  Если метод `SelectCommand` возвращает результаты инструкции OUTER JOIN, то `DataAdapter` не задает значение `PrimaryKey` для результирующего набора `DataTable`. Необходимо непосредственно определить значение `PrimaryKey` для обеспечения того, чтобы решение по обработке повторяющихся строк было принято правильно. Дополнительные сведения см. в разделе [Определение первичных ключей](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).  
  
 Для обработки исключений, которые могут возникать при вызове `Update` метод, можно использовать `RowUpdated` события, происходящие реагировать на ошибки обновления строк (в разделе [обработка событий DataAdapter](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)), или можно задать `DataAdapter.ContinueUpdateOnError` для `true` перед вызовом `Update`и реагировать на ошибки сведениями, хранящимися в `RowError` свойство конкретной строки после завершения обновления (в разделе [сведения об ошибках строк](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-error-information.md)).  
  
 **Примечание** вызов `AcceptChanges` на `DataSet`, `DataTable`, или `DataRow` все `Original` значения для `DataRow` перезапись `Current` значения для `DataRow`. Если были изменены значения полей, уникальным образом идентифицирующих строку, то после вызова метода `AcceptChanges` значения `Original` больше не будут соответствовать этим значениям в источнике данных. Метод `AcceptChanges` вызывается автоматически для каждой строки во время вызова метода Update объекта `DataAdapter`. Можно сохранить первоначальные значения во время вызова метода Update, для чего вначале следует задать значение свойства `AcceptChangesDuringUpdate` объекта `DataAdapter` равным false, или создать обработчик событий для события `RowUpdated` и задать значение <xref:System.Data.Common.RowUpdatedEventArgs.Status%2A>, равное <xref:System.Data.UpdateStatus.SkipCurrentRow>. Дополнительные сведения см. в разделе [слияние содержимого набора данных](../../../../docs/framework/data/adonet/dataset-datatable-dataview/merging-dataset-contents.md) и [обработка событий DataAdapter](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).  
  
## <a name="example"></a>Пример  
 Следующие примеры демонстрируют, как для выполнения обновлений к модифицированным строкам путем явного задания `UpdateCommand` из `DataAdapter` и вызов его `Update` метод. Обратите внимание на то, что задан параметр, указанный в предложении WHERE инструкции UPDATE, чтобы использовалось значение `Original` объекта `SourceColumn`. Это важно, поскольку значение `Current` могло быть изменено, поэтому может не соответствовать этому значению в источнике данных. Значение `Original` представляет собой значение, которое использовалось для заполнения `DataTable` из источника данных.  
  
 [!code-csharp[DataWorks SqlClient.DataAdapterUpdate#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.DataAdapterUpdate/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.DataAdapterUpdate#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.DataAdapterUpdate/VB/source.vb#1)]  
  
## <a name="autoincrement-columns"></a>Столбцы AutoIncrement  
 Если в таблицах из применяемого источника данных имеются столбцы с автоматическим увеличением значений, то можно обеспечить заполнение столбцов в применяемом `DataSet` путем возврата автоматически увеличивающегося значения как выходного параметра хранимой процедуры и сопоставления его со столбцом таблицы; возврата автоматически увеличивающегося значения в первой строке результирующего набора, возвращенного хранимой процедурой или инструкцией SQL; а также использование события `RowUpdated` объекта `DataAdapter` для выполнения дополнительной инструкции SELECT. Дополнительные сведения и пример см. в разделе [извлечение идентификации или значений автонумерации](../../../../docs/framework/data/adonet/retrieving-identity-or-autonumber-values.md).  
  
## <a name="ordering-of-inserts-updates-and-deletes"></a>Упорядочение вставок, обновлений и удалений  
 Во многих обстоятельствах имеет значение последовательность передачи изменений, внесенных с помощью `DataSet`, в источник данных. Например, если происходит обновление значения первичного ключа для существующей строки и добавляется новая строка с новым значением первичного ключа в качестве внешнего ключа, то важно вначале осуществить обновление, а затем вставку.  
  
 Можно использовать метод `Select` объекта `DataTable` для возврата массива `DataRow`, который ссылается только на строки с конкретным значением `RowState`. После этого можно передать возвращенный массив `DataRow` в метод `Update` объекта `DataAdapter` для обработки измененных строк. Задавая подмножество строк, подлежащих обновлению, можно управлять тем, в какой последовательности обрабатываются вставки, обновления и удаления.  
  
## <a name="example"></a>Пример  
 Например, в следующем коде обеспечивается то, что удаленные строки таблицы обрабатываются в первую очередь, затем происходит обработка обновленных строк, после чего обрабатываются вставленные строки.  
  
```vb  
Dim table As DataTable = dataSet.Tables("Customers")  
  
' First process deletes.  
dataSet.Update(table.Select(Nothing, Nothing, _  
  DataViewRowState.Deleted))  
  
' Next process updates.  
adapter.Update(table.Select(Nothing, Nothing, _  
  DataViewRowState.ModifiedCurrent))  
  
' Finally, process inserts.  
dataAdapater.Update(table.Select(Nothing, Nothing, _  
  DataViewRowState.Added))  
```  
  
```csharp  
DataTable table = dataSet.Tables["Customers"];  
  
// First process deletes.  
adapter.Update(table.Select(null, null, DataViewRowState.Deleted));  
  
// Next process updates.  
adapter.Update(table.Select(null, null,   
  DataViewRowState.ModifiedCurrent));  
  
// Finally, process inserts.  
adapter.Update(table.Select(null, null, DataViewRowState.Added));  
```  
  
## <a name="use-a-dataadapter-to-retrieve-and-update-data"></a>Используйте DataAdapter для извлечения и обновления данных  
 DataAdapter можно использовать для извлечения и обновления данных.  
  
-   В этом примере DataAdapter.AcceptChangesDuringFill используется для клонирования данных в базе данных. Если свойство имеет значение false, AcceptChanges при заполнении таблицы не вызывается и позднее добавленные строки рассматриваются как вставленные строки. Таким образом, в примере эти строки используются для вставки новых строк в базу данных.  
  
-   В этом примере DataAdapter.TableMappings используется для определения сопоставления между исходной таблицей и DataTable.  
  
-   В этом примере DataAdapter.FillLoadOption используется для определения того, как адаптер заполняет DataTable из DbDataReader. При создании объекта DataTable можно выполнять запись данных из базы данных только в текущую или исходную версию путем установки свойства в LoadOption.Upsert или LoadOption.PreserveChanges.  
  
-   В примере также обновляется таблица путем использования DbDataAdapter.UpdateBatchSize для выполнения пакетных операций.  
  
 Перед компиляцией и выполнением примера необходимо создать образец базы данных:  
  
```  
USE [master]  
GO  
  
CREATE DATABASE [MySchool]   
  
GO  
  
USE [MySchool]  
GO  
  
SET ANSI_NULLS ON  
GO  
SET QUOTED_IDENTIFIER ON  
GO  
CREATE TABLE [dbo].[Course]([CourseID] [nvarchar](10) NOT NULL,  
[Year] [smallint] NOT NULL,  
[Title] [nvarchar](100) NOT NULL,  
[Credits] [int] NOT NULL,  
[DepartmentID] [int] NOT NULL,  
 CONSTRAINT [PK_Course] PRIMARY KEY CLUSTERED  
(  
[CourseID] ASC,  
[Year] ASC  
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]  
  
GO  
  
SET ANSI_NULLS ON  
GO  
SET QUOTED_IDENTIFIER ON  
GO  
CREATE TABLE [dbo].[Department]([DepartmentID] [int] IDENTITY(1,1) NOT NULL,  
[Name] [nvarchar](50) NOT NULL,  
[Budget] [money] NOT NULL,  
[StartDate] [datetime] NOT NULL,  
[Administrator] [int] NULL,  
 CONSTRAINT [PK_Department] PRIMARY KEY CLUSTERED  
(  
[DepartmentID] ASC  
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]  
  
GO  
  
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C1045', 2012, N'Calculus', 4, 7)  
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C1061', 2012, N'Physics', 4, 1)  
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C2021', 2012, N'Composition', 3, 2)  
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C2042', 2012, N'Literature', 4, 2)  
  
SET IDENTITY_INSERT [dbo].[Department] ON   
  
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (1, N'Engineering', 350000.0000, CAST(0x0000999C00000000 AS DateTime), 2)  
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (2, N'English', 120000.0000, CAST(0x0000999C00000000 AS DateTime), 6)  
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (4, N'Economics', 200000.0000, CAST(0x0000999C00000000 AS DateTime), 4)  
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (7, N'Mathematics', 250024.0000, CAST(0x0000999C00000000 AS DateTime), 3)  
SET IDENTITY_INSERT [dbo].[Department] OFF  
  
ALTER TABLE [dbo].[Course]  WITH CHECK ADD  CONSTRAINT [FK_Course_Department] FOREIGN KEY([DepartmentID])  
REFERENCES [dbo].[Department] ([DepartmentID])  
GO  
ALTER TABLE [dbo].[Course] CHECK CONSTRAINT [FK_Course_Department]  
GO  
```  
  
 Проекты C# и Visual Basic с этим образцом кода можно найти на [примеры кода от разработчиков](http://code.msdn.microsoft.com/site/search?f%5B0%5D.Type=SearchText&f%5B0%5D.Value=How%20to%20use%20DataAdapter%20to%20retrieve%20and%20update%20data&f%5B1%5D).  
  
```  
using System;  
using System.Data;  
using System.Data.Common;  
using System.Data.SqlClient;  
using System.Linq;  
using CSDataAdapterOperations.Properties;  
  
namespace CSDataAdapterOperations.Properties {  
   internal sealed partial class Settings : global::System.Configuration.ApplicationSettingsBase {  
  
      private static Settings defaultInstance = ((Settings)(global::System.Configuration.ApplicationSettingsBase.Synchronized(new Settings())));  
  
      public static Settings Default {  
         get {  
            return defaultInstance;  
         }  
      }  
  
      [global::System.Configuration.ApplicationScopedSettingAttribute()]  
      [global::System.Configuration.DefaultSettingValueAttribute("Data Source=(local);Initial Catalog=MySchool;Integrated Security=True")]  
      public string MySchoolConnectionString {  
         get {  
            return ((string)(this["MySchoolConnectionString"]));  
         }  
      }  
   }  
}  
  
class Program {  
   static void Main(string[] args) {  
      Settings settings = new Settings();  
  
      // Copy the data from the database.  Get the table Department and Course from the database.  
      String selectString = @"SELECT [DepartmentID],[Name],[Budget],[StartDate],[Administrator]  
                                     FROM [MySchool].[dbo].[Department];  
  
                                   SELECT [CourseID],@Year as [Year],Max([Title]) as [Title],  
                                   Max([Credits]) as [Credits],Max([DepartmentID]) as [DepartmentID]  
                                   FROM [MySchool].[dbo].[Course]  
                                   Group by [CourseID]";  
  
      DataSet mySchool = new DataSet();  
  
      SqlCommand selectCommand = new SqlCommand(selectString);  
      SqlParameter parameter = selectCommand.Parameters.Add("@Year", SqlDbType.SmallInt, 2);  
      parameter.Value = new Random(DateTime.Now.Millisecond).Next(9999);  
  
      // Use DataTableMapping to map the source tables and the destination tables.  
      DataTableMapping[] tableMappings = {new DataTableMapping("Table", "Department"), new DataTableMapping("Table1", "Course")};  
      CopyData(mySchool, settings.MySchoolConnectionString, selectCommand, tableMappings);  
  
      Console.WriteLine("The following tables are from the database.");  
      foreach (DataTable table in mySchool.Tables) {  
         Console.WriteLine(table.TableName);  
         ShowDataTable(table);  
      }  
  
      // Roll back the changes  
      DataTable department = mySchool.Tables["Department"];  
      DataTable course = mySchool.Tables["Course"];  
  
      department.Rows[0]["Name"] = "New" + department.Rows[0][1];  
      course.Rows[0]["Title"] = "New" + course.Rows[0]["Title"];  
      course.Rows[0]["Credits"] = 10;  
  
      Console.WriteLine("After we changed the tables:");  
      foreach (DataTable table in mySchool.Tables) {  
         Console.WriteLine(table.TableName);  
         ShowDataTable(table);  
      }  
  
      department.RejectChanges();  
      Console.WriteLine("After use the RejectChanges method in Department table to roll back the changes:");  
      ShowDataTable(department);  
  
      DataColumn[] primaryColumns = { course.Columns["CourseID"] };  
      DataColumn[] resetColumns = { course.Columns["Title"] };  
      ResetCourse(course, settings.MySchoolConnectionString, primaryColumns, resetColumns);  
      Console.WriteLine("After use the ResetCourse method in Course table to roll back the changes:");  
      ShowDataTable(course);  
  
      // Batch update the table.  
      String insertString = @"Insert into [MySchool].[dbo].[Course]([CourseID],[Year],[Title],   
                                   [Credits],[DepartmentID])   
             values (@CourseID,@Year,@Title,@Credits,@DepartmentID)";  
      SqlCommand insertCommand = new SqlCommand(insertString);  
      insertCommand.Parameters.Add("@CourseID", SqlDbType.NVarChar, 10, "CourseID");  
      insertCommand.Parameters.Add("@Year", SqlDbType.SmallInt, 2, "Year");  
      insertCommand.Parameters.Add("@Title", SqlDbType.NVarChar, 100, "Title");  
      insertCommand.Parameters.Add("@Credits", SqlDbType.Int, 4, "Credits");  
      insertCommand.Parameters.Add("@DepartmentID", SqlDbType.Int, 4, "DepartmentID");  
  
      const Int32 batchSize = 10;  
      BatchInsertUpdate(course, settings.MySchoolConnectionString, insertCommand, batchSize);  
   }  
  
   private static void CopyData(DataSet dataSet, String connectionString, SqlCommand selectCommand, DataTableMapping[] tableMappings) {  
      using (SqlConnection connection = new SqlConnection(connectionString)) {  
         selectCommand.Connection = connection;  
  
         connection.Open();  
  
         using (SqlDataAdapter adapter = new SqlDataAdapter(selectCommand)) {adapter.TableMappings.AddRange(tableMappings);  
            // If set the AcceptChangesDuringFill as the false, AcceptChanges will not be called on a   
            // DataRow after it is added to the DataTable during any of the Fill operations.  
            adapter.AcceptChangesDuringFill = false;  
  
            adapter.Fill(dataSet);  
         }  
      }  
   }  
  
   // Roll back only one column or several columns data of the Course table by call ResetDataTable method.  
   private static void ResetCourse(DataTable table, String connectionString,  
       DataColumn[] primaryColumns, DataColumn[] resetColumns) {  
      table.PrimaryKey = primaryColumns;  
  
      // Build the query string  
      String primaryCols = String.Join(",", primaryColumns.Select(col => col.ColumnName));  
      String resetCols = String.Join(",", resetColumns.Select(col => "Max(" + col.ColumnName + ") as " + col.ColumnName));  
  
      String selectString = String.Format("Select {0},{1} from Course Group by {0}", primaryCols, resetCols);  
  
      SqlCommand selectCommand = new SqlCommand(selectString);  
  
      ResetDataTable(table, connectionString, selectCommand);  
   }  
  
   // RejectChanges will roll back all changes made to the table since it was loaded, or the last time AcceptChanges   
   // was called. When you copy from the database, you can lose all the data after calling RejectChanges  
   // The ResetDataTable method rolls back one or more columns of data.  
   private static void ResetDataTable(DataTable table, String connectionString,  
       SqlCommand selectCommand) {  
      using (SqlConnection connection = new SqlConnection(connectionString)) {  
         selectCommand.Connection = connection;  
  
         connection.Open();  
  
         using (SqlDataAdapter adapter = new SqlDataAdapter(selectCommand)) {  
            // The incoming values for this row will be written to the current version of each   
            // column. The original version of each column's data will not be changed.  
            adapter.FillLoadOption = LoadOption.Upsert;  
  
            adapter.Fill(table);  
         }  
      }  
   }  
  
   private static void BatchInsertUpdate(DataTable table, String connectionString,  
       SqlCommand insertCommand, Int32 batchSize) {  
      using (SqlConnection connection = new SqlConnection(connectionString)) {  
         insertCommand.Connection = connection;  
         // When setting UpdateBatchSize to a value other than 1, all the commands   
         // associated with the SqlDataAdapter have to have their UpdatedRowSource   
         // property set to None or OutputParameters. An exception is thrown otherwise.  
         insertCommand.UpdatedRowSource = UpdateRowSource.None;  
  
         connection.Open();  
  
         using (SqlDataAdapter adapter = new SqlDataAdapter()) {  
            adapter.InsertCommand = insertCommand;  
            // Gets or sets the number of rows that are processed in each round-trip to the server.  
            // Setting it to 1 disables batch updates, as rows are sent one at a time.  
            adapter.UpdateBatchSize = batchSize;  
  
            adapter.Update(table);  
  
            Console.WriteLine("Successfully to update the table.");  
         }  
      }  
   }  
  
   private static void ShowDataTable(DataTable table) {  
      foreach (DataColumn col in table.Columns) {  
         Console.Write("{0,-14}", col.ColumnName);  
      }  
      Console.WriteLine("{0,-14}", "RowState");  
  
      foreach (DataRow row in table.Rows) {  
         foreach (DataColumn col in table.Columns) {  
            if (col.DataType.Equals(typeof(DateTime)))  
               Console.Write("{0,-14:d}", row[col]);  
            else if (col.DataType.Equals(typeof(Decimal)))  
               Console.Write("{0,-14:C}", row[col]);  
            else  
               Console.Write("{0,-14}", row[col]);  
         }  
         Console.WriteLine("{0,-14}", row.RowState);  
      }  
   }  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Объекты DataAdapter и DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [Состояния и версии строк](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)  
 [AcceptChanges и RejectChanges](../../../../docs/framework/data/adonet/dataset-datatable-dataview/acceptchanges-and-rejectchanges.md)  
 [Слияние содержимого набора данных](../../../../docs/framework/data/adonet/dataset-datatable-dataview/merging-dataset-contents.md)  
 [Извлечение идентификации или значений автонумерации](../../../../docs/framework/data/adonet/retrieving-identity-or-autonumber-values.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
