---
title: Данные FILESTREAM
ms.date: 03/30/2017
ms.assetid: bd8b845c-0f09-4295-b466-97ef106eefa8
ms.openlocfilehash: eef03d171d288cb2bc62c3aaa477a95a5ce718c3
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43892695"
---
# <a name="filestream-data"></a>Данные FILESTREAM
Для двоичных данных (BLOB), хранящихся в столбце varbinary(max), появился новый атрибут хранилища FILESTREAM. До появления FILESTREAM для хранения двоичных данных была необходима специальная обработка. Неструктурированные данные, например текстовые документы, изображения и видеоролики, зачастую хранятся вне базы данных, что затрудняет работу с ними.  
  
> [!NOTE]
>  Для работы с данными FILESTREAM через SqlClient необходимо установить .NET Framework 3.5 с пакетом обновления 1 (SP1) или более поздней версии.  
  
 При указании для столбца varbinary(max) атрибута FILESTREAM сервер SQL Server сохраняет данные не в файле базы данных, а в файловой системе NTFS на локальном компьютере. Хотя эти данные хранятся отдельно, для работы с ними можно использовать те же инструкции [!INCLUDE[tsql](../../../../../includes/tsql-md.md)], что и для данных varbinary(max), хранящихся в базе данных.  
  
## <a name="sqlclient-support-for-filestream"></a>Поддержка атрибута FILESTREAM в SqlClient  
 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] Поставщик данных для SQL Server, <xref:System.Data.SqlClient>, поддерживает чтение и запись данных FILESTREAM с помощью <xref:System.Data.SqlTypes.SqlFileStream> класс, определенный в <xref:System.Data.SqlTypes> пространства имен. Класс `SqlFileStream` является производным от класса <xref:System.IO.Stream>, который содержит методы для чтения и записи потоков данных. При чтении из потока данные передаются в структуру данных, например в массив байтов. При записи данные передаются из структуры данных в поток.  
  
### <a name="creating-the-sql-server-table"></a>Создание таблицы SQL Server  
 Приведенная ниже инструкция [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] создает таблицу employees и вставляет в нее строку данных. После включения атрибута FILESTREAM эту таблицу можно использовать в приведенных ниже примерах кода. Ссылки на ресурсы в электронной документации по SQL Server приведены в конце этого раздела.  
  
```  
CREATE TABLE employees  
(  
  EmployeeId INT  NOT NULL  PRIMARY KEY,  
  Photo VARBINARY(MAX) FILESTREAM  NULL,  
  RowGuid UNIQUEIDENTIFIER  NOT NULL  ROWGUIDCOL  
  UNIQUE DEFAULT NEWID()  
)  
GO  
Insert into employees  
Values(1, 0x00, default)  
GO  
```  
  
### <a name="example-reading-overwriting-and-inserting-filestream-data"></a>Пример. Чтение, перезапись и вставка данных FILESTREAM  
 В приведенном ниже образце демонстрируется чтение данных из потока FILESTREAM. В коде определяется логический путь к файлу, свойству `FileAccess` присваивается значение `Read`, а свойству `FileOptions` - значение `SequentialScan`. Затем в коде считываются в буфер байты данных из потока SqlFileStream. Эти байты данных затем выводятся в окно консоли.  
  
 В приведенном ниже образце также демонстрируется запись данных в поток FILESTREAM с перезаписью всех существующих данных. В коде определяется логический путь к файлу, создается поток `SqlFileStream`, свойству `FileAccess` присваивается значение `Write`, а свойству `FileOptions` - значение `SequentialScan`. В поток `SqlFileStream` записывается один байт, заменяющий все данные в файле.  
  
 В этом примере кода также демонстрируется запись данных в поток FILESTREAM с использованием метода Seek для добавления данных в конец файла. В коде определяется логический путь к файлу, создается поток `SqlFileStream`, свойству `FileAccess` присваивается значение `ReadWrite`, а свойству `FileOptions` - значение `SequentialScan`. Для поиска конца файла в коде используется метод Seek, после чего в конец файла добавляется один байт.  
  
```csharp  
using System;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Data;  
using System.IO;  
  
namespace FileStreamTest  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            SqlConnectionStringBuilder builder = new SqlConnectionStringBuilder("server=(local);integrated security=true;database=myDB");  
            ReadFilestream(builder);  
            OverwriteFilestream(builder);  
            InsertFilestream(builder);  
  
            Console.WriteLine("Done");  
        }  
  
        private static void ReadFilestream(SqlConnectionStringBuilder connStringBuilder)  
        {  
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))  
            {  
                connection.Open();  
                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);  
  
                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);  
                command.Transaction = tran;  
  
                using (SqlDataReader reader = command.ExecuteReader())  
                {  
                    while (reader.Read())  
                    {  
                        // Get the pointer for the file  
                        string path = reader.GetString(0);  
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;  
  
                        // Create the SqlFileStream  
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Read, FileOptions.SequentialScan, allocationSize: 0))  
                        {  
                            // Read the contents as bytes and write them to the console  
                            for (long index = 0; index < fileStream.Length; index++)  
                            {  
                                Console.WriteLine(fileStream.ReadByte());  
                            }  
                        }  
                    }  
                }  
                tran.Commit();  
            }  
        }  
  
        private static void OverwriteFilestream(SqlConnectionStringBuilder connStringBuilder)  
        {  
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))  
            {  
                connection.Open();  
  
                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);  
  
                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);  
                command.Transaction = tran;  
  
                using (SqlDataReader reader = command.ExecuteReader())  
                {  
                    while (reader.Read())  
                    {  
                        // Get the pointer for file   
                        string path = reader.GetString(0);  
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;  
  
                        // Create the SqlFileStream  
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Write, FileOptions.SequentialScan, allocationSize: 0))  
                        {  
                            // Write a single byte to the file. This will  
                            // replace any data in the file.  
                            fileStream.WriteByte(0x01);  
                        }  
                    }  
                }  
                tran.Commit();  
            }  
        }  
  
        private static void InsertFilestream(SqlConnectionStringBuilder connStringBuilder)  
        {  
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))  
            {  
                connection.Open();  
  
                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);  
  
                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);  
                command.Transaction = tran;  
  
                using (SqlDataReader reader = command.ExecuteReader())  
                {  
                    while (reader.Read())  
                    {  
                        // Get the pointer for file  
                        string path = reader.GetString(0);  
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;  
  
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.ReadWrite, FileOptions.SequentialScan, allocationSize: 0))  
                        {  
                            // Seek to the end of the file  
                            fileStream.Seek(0, SeekOrigin.End);  
  
                            // Append a single byte   
                            fileStream.WriteByte(0x01);  
                        }  
                    }  
                }  
                tran.Commit();  
            }  
  
        }  
    }  
}
```  
  
 Другой пример, см. в разделе [способы хранения и получения двоичных данных в столбце файлового потока](http://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str).  
  
## <a name="resources-in-sql-server-books-online"></a>Ресурсы электронной документации по SQL Server  
 Полная документация по FILESTREAM содержится в следующих разделах документации по SQL Server.  
  
|Раздел|Описание|  
|-----------|-----------------|  
|[Проектирование и реализация хранилища FILESTREAM](http://msdn2.microsoft.com/library/bb895234\(SQL.105\).aspx)|Приводятся ссылки на документацию по атрибуту FILESTREAM и связанные с ним разделы.|  
|[Общие сведения о FILESTREAM](http://msdn2.microsoft.com/library/bb933993\(SQL.105\).aspx)|Приводятся сведения о том, когда необходимо использовать хранилище FILESTREAM; также описывается интеграция ядра СУБД SQL Server и файловой системы NTFS.|  
|[Приступая к работе с хранилищем FILESTREAM](https://msdn.microsoft.com/library/bb933995\(SQL.105\).aspx)|Описывается включение хранилища FILESTREAM для экземпляра SQL Server, создание базы данных и таблицы, в которой будут храниться данные FILESTREAM, а также работа со строками, содержащими данные FILESTREAM.|  
|[Использование хранилища FILESTREAM в клиентских приложениях](https://msdn.microsoft.com/library/bb933877\(SQL.105\).aspx)|Описываются функции API-интерфейса Win32, предназначенные для работы с данными FILESTREAM.|  
|[FILESTREAM и другими компонентами SQL Server](/sql/relational-databases/blob/filestream-compatibility-with-other-sql-server-features)|Приводятся общие сведения, рекомендации и ограничения при использовании данных FILESTREAM совместно с другими возможностями SQL Server.|  
  
## <a name="see-also"></a>См. также  
 [Типы данных SQL Server и ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [Извлечение и изменение данных в ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Управление доступом для кода и ADO.NET](../../../../../docs/framework/data/adonet/code-access-security.md)  
 [Двоичные данные и данные большого объема SQL Server](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
