---
title: "Данные FILESTREAM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bd8b845c-0f09-4295-b466-97ef106eefa8
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 77d6dbafc5a7c3afd9998fd8e9ae54ce60f90a45
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="filestream-data"></a><span data-ttu-id="969ca-102">Данные FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="969ca-102">FILESTREAM Data</span></span>
<span data-ttu-id="969ca-103">Для двоичных данных (BLOB), хранящихся в столбце varbinary(max), появился новый атрибут хранилища FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="969ca-103">The FILESTREAM storage attribute is for binary (BLOB) data stored in a varbinary(max) column.</span></span> <span data-ttu-id="969ca-104">До появления FILESTREAM для хранения двоичных данных была необходима специальная обработка.</span><span class="sxs-lookup"><span data-stu-id="969ca-104">Before FILESTREAM, storing binary data required special handling.</span></span> <span data-ttu-id="969ca-105">Неструктурированные данные, например текстовые документы, изображения и видеоролики, зачастую хранятся вне базы данных, что затрудняет работу с ними.</span><span class="sxs-lookup"><span data-stu-id="969ca-105">Unstructured data, such as text documents, images and video, is often stored outside of the database, making it difficult to manage.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="969ca-106">Для работы с данными FILESTREAM через SqlClient необходимо установить .NET Framework 3.5 с пакетом обновления 1 (SP1) или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="969ca-106">You must install the .NET Framework 3.5 SP1 (or later) to work with FILESTREAM data using SqlClient.</span></span>  
  
 <span data-ttu-id="969ca-107">При указании для столбца varbinary(max) атрибута FILESTREAM сервер [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] сохраняет данные не в файле базы данных, а в файловой системе NTFS на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="969ca-107">Specifying the FILESTREAM attribute on a varbinary(max) column causes [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] to store the data on the local NTFS file system instead of in the database file.</span></span> <span data-ttu-id="969ca-108">Хотя эти данные хранятся отдельно, для работы с ними можно использовать те же инструкции [!INCLUDE[tsql](../../../../../includes/tsql-md.md)], что и для данных varbinary(max), хранящихся в базе данных.</span><span class="sxs-lookup"><span data-stu-id="969ca-108">Although it is stored separately, you can use the same [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] statements that are supported for working with varbinary(max) data that is stored in the database.</span></span>  
  
## <a name="sqlclient-support-for-filestream"></a><span data-ttu-id="969ca-109">Поддержка атрибута FILESTREAM в SqlClient</span><span class="sxs-lookup"><span data-stu-id="969ca-109">SqlClient Support for FILESTREAM</span></span>  
 <span data-ttu-id="969ca-110">Поставщик данных [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] для [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] (<xref:System.Data.SqlClient>) поддерживает чтение и запись данных FILESTREAM с помощью класса <xref:System.Data.SqlTypes.SqlFileStream>, определенного в пространстве имен <xref:System.Data.SqlTypes>.</span><span class="sxs-lookup"><span data-stu-id="969ca-110">The [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] Data Provider for [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)], <xref:System.Data.SqlClient>, supports reading and writing to FILESTREAM data using the <xref:System.Data.SqlTypes.SqlFileStream> class defined in the <xref:System.Data.SqlTypes> namespace.</span></span> <span data-ttu-id="969ca-111">Класс `SqlFileStream` является производным от класса <xref:System.IO.Stream>, который содержит методы для чтения и записи потоков данных.</span><span class="sxs-lookup"><span data-stu-id="969ca-111">`SqlFileStream` inherits from the <xref:System.IO.Stream> class, which provides methods for reading and writing to streams of data.</span></span> <span data-ttu-id="969ca-112">При чтении из потока данные передаются в структуру данных, например в массив байтов.</span><span class="sxs-lookup"><span data-stu-id="969ca-112">Reading from a stream transfers data from the stream into a data structure, such as an array of bytes.</span></span> <span data-ttu-id="969ca-113">При записи данные передаются из структуры данных в поток.</span><span class="sxs-lookup"><span data-stu-id="969ca-113">Writing transfers the data from the data structure into a stream.</span></span>  
  
### <a name="creating-the-includessnoversionincludesssnoversion-mdmd-table"></a><span data-ttu-id="969ca-114">Создание таблицы [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="969ca-114">Creating the [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Table</span></span>  
 <span data-ttu-id="969ca-115">Приведенная ниже инструкция [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] создает таблицу employees и вставляет в нее строку данных.</span><span class="sxs-lookup"><span data-stu-id="969ca-115">The following [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] statements creates a table named employees and inserts a row of data.</span></span> <span data-ttu-id="969ca-116">После включения атрибута FILESTREAM эту таблицу можно использовать в приведенных ниже примерах кода.</span><span class="sxs-lookup"><span data-stu-id="969ca-116">Once you have enabled FILESTREAM storage, you can use this table in conjunction with the code examples that follow.</span></span> <span data-ttu-id="969ca-117">Ссылки на ресурсы электронной документации по [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] приведены в конце данного раздела.</span><span class="sxs-lookup"><span data-stu-id="969ca-117">The links to resources in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Books Online are located at the end of this topic.</span></span>  
  
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
  
### <a name="example-reading-overwriting-and-inserting-filestream-data"></a><span data-ttu-id="969ca-118">Пример. Чтение, перезапись и вставка данных FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="969ca-118">Example: Reading, Overwriting, and Inserting FILESTREAM Data</span></span>  
 <span data-ttu-id="969ca-119">В приведенном ниже образце демонстрируется чтение данных из потока FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="969ca-119">The following sample demonstrates how to read data from a FILESTREAM.</span></span> <span data-ttu-id="969ca-120">В коде определяется логический путь к файлу, свойству `FileAccess` присваивается значение `Read`, а свойству `FileOptions` - значение `SequentialScan`.</span><span class="sxs-lookup"><span data-stu-id="969ca-120">The code gets the logical path to the file, setting the `FileAccess` to `Read` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="969ca-121">Затем в коде считываются в буфер байты данных из потока SqlFileStream.</span><span class="sxs-lookup"><span data-stu-id="969ca-121">The code then reads the bytes from the SqlFileStream into the buffer.</span></span> <span data-ttu-id="969ca-122">Эти байты данных затем выводятся в окно консоли.</span><span class="sxs-lookup"><span data-stu-id="969ca-122">The bytes are then written to the console window.</span></span>  
  
 <span data-ttu-id="969ca-123">В приведенном ниже образце также демонстрируется запись данных в поток FILESTREAM с перезаписью всех существующих данных.</span><span class="sxs-lookup"><span data-stu-id="969ca-123">The sample also demonstrates how to write data to a FILESTREAM in which all existing data is overwritten.</span></span> <span data-ttu-id="969ca-124">В коде определяется логический путь к файлу, создается поток `SqlFileStream`, свойству `FileAccess` присваивается значение `Write`, а свойству `FileOptions` - значение `SequentialScan`.</span><span class="sxs-lookup"><span data-stu-id="969ca-124">The code gets the logical path to the file and creates the `SqlFileStream`, setting the `FileAccess` to `Write` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="969ca-125">В поток `SqlFileStream` записывается один байт, заменяющий все данные в файле.</span><span class="sxs-lookup"><span data-stu-id="969ca-125">A single byte is written to the `SqlFileStream`, replacing any data in the file.</span></span>  
  
 <span data-ttu-id="969ca-126">В этом примере кода также демонстрируется запись данных в поток FILESTREAM с использованием метода Seek для добавления данных в конец файла.</span><span class="sxs-lookup"><span data-stu-id="969ca-126">The sample also demonstrates how to write data to a FILESTREAM by using the Seek method to append data to the end of the file.</span></span> <span data-ttu-id="969ca-127">В коде определяется логический путь к файлу, создается поток `SqlFileStream`, свойству `FileAccess` присваивается значение `ReadWrite`, а свойству `FileOptions` - значение `SequentialScan`.</span><span class="sxs-lookup"><span data-stu-id="969ca-127">The code gets the logical path to the file and creates the `SqlFileStream`, setting the `FileAccess` to `ReadWrite` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="969ca-128">Для поиска конца файла в коде используется метод Seek, после чего в конец файла добавляется один байт.</span><span class="sxs-lookup"><span data-stu-id="969ca-128">The code uses the Seek method to seek to the end of the file, appending a single byte to the existing file.</span></span>  
  
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
  
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Write, FileOptions.SequentialScan, allocationSize: 0))  
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
} using (SqlConnection connection = new SqlConnection(  
    connStringBuilder.ToString()))  
{  
    connection.Open();  
  
    SqlCommand command = new SqlCommand("", connection);  
    command.CommandText = "select Top(1) Photo.PathName(), "  
    + "GET_FILESTREAM_TRANSACTION_CONTEXT () from employees";  
  
    SqlTransaction tran = connection.BeginTransaction(  
        System.Data.IsolationLevel.ReadCommitted);  
    command.Transaction = tran;  
  
    using (SqlDataReader reader = command.ExecuteReader())  
    {  
        while (reader.Read())  
        {  
            // Get the pointer for file  
            string path = reader.GetString(0);  
            byte[] transactionContext = reader.GetSqlBytes(1).Buffer;  
  
            FileStream fileStream = new SqlFileStream(path,  
                (byte[])reader.GetValue(1),  
                FileAccess.ReadWrite,  
                FileOptions.SequentialScan, 0);  
  
            // Seek to the end of the file  
            fs.Seek(0, SeekOrigin.End);  
  
            // Append a single byte   
            fileStream.WriteByte(0x01);  
            fileStream.Close();  
        }  
    }  
    tran.Commit();  
}  
```  
  
 <span data-ttu-id="969ca-129">Еще один пример см. в разделе [способы хранения и получения двоичных данных в столбце файлового потока](http://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str).</span><span class="sxs-lookup"><span data-stu-id="969ca-129">For another sample, see [How to store and fetch binary data into a file stream column](http://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str).</span></span>  
  
## <a name="resources-in-includessnoversionincludesssnoversion-mdmd-books-online"></a><span data-ttu-id="969ca-130">Ресурсы электронной документации по [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="969ca-130">Resources in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Books Online</span></span>  
 <span data-ttu-id="969ca-131">Полная документация по FILESTREAM содержится в указанных ниже разделах электронной документации по [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="969ca-131">The complete documentation for FILESTREAM is located in the following sections in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
|<span data-ttu-id="969ca-132">Раздел</span><span class="sxs-lookup"><span data-stu-id="969ca-132">Topic</span></span>|<span data-ttu-id="969ca-133">Описание:</span><span class="sxs-lookup"><span data-stu-id="969ca-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="969ca-134">[Проектирование и реализация хранилища FILESTREAM](http://msdn2.microsoft.com/library/bb895234\(SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="969ca-134">[Designing and Implementing FILESTREAM Storage](http://msdn2.microsoft.com/library/bb895234\(SQL.105\).aspx)</span></span>|<span data-ttu-id="969ca-135">Приводятся ссылки на документацию по атрибуту FILESTREAM и связанные с ним разделы.</span><span class="sxs-lookup"><span data-stu-id="969ca-135">Provides links to FILESTREAM documentation and related topics.</span></span>|  
|<span data-ttu-id="969ca-136">[Общие сведения о FILESTREAM](http://msdn2.microsoft.com/library/bb933993\(SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="969ca-136">[FILESTREAM Overview](http://msdn2.microsoft.com/library/bb933993\(SQL.105\).aspx)</span></span>|<span data-ttu-id="969ca-137">Приводятся сведения о том, когда необходимо использовать хранилище FILESTREAM; также описывается интеграция ядра СУБД SQL Server и файловой системы NTFS.</span><span class="sxs-lookup"><span data-stu-id="969ca-137">Describes when to use FILESTREAM storage and how it integrates the SQL Server Database Engine with an NTFS file system.</span></span>|  
|<span data-ttu-id="969ca-138">[Приступая к работе с хранилищем FILESTREAM](http://msdn.microsoft.com/library/bb933995\(SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="969ca-138">[Getting Started with FILESTREAM Storage](http://msdn.microsoft.com/library/bb933995\(SQL.105\).aspx)</span></span>|<span data-ttu-id="969ca-139">Описывается включение хранилища FILESTREAM для экземпляра SQL Server, создание базы данных и таблицы, в которой будут храниться данные FILESTREAM, а также работа со строками, содержащими данные FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="969ca-139">Describes how to enable FILESTREAM on an instance of SQL Server, how to create a database and a table to stored FILESTREAM data, and how to manipulate rows containing FILESTREAM data.</span></span>|  
|<span data-ttu-id="969ca-140">[Использование хранилища FILESTREAM в клиентских приложениях](http://msdn.microsoft.com/library/bb933877\(SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="969ca-140">[Using FILESTREAM Storage in Client Applications](http://msdn.microsoft.com/library/bb933877\(SQL.105\).aspx)</span></span>|<span data-ttu-id="969ca-141">Описываются функции API-интерфейса Win32, предназначенные для работы с данными FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="969ca-141">Describes the Win32 API functions for working with FILESTREAM data.</span></span>|  
|<span data-ttu-id="969ca-142">[FILESTREAM и другие функции SQL Server](http://msdn.microsoft.com/library/bb895334\(SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="969ca-142">[FILESTREAM and Other SQL Server Features](http://msdn.microsoft.com/library/bb895334\(SQL.105\).aspx)</span></span>|<span data-ttu-id="969ca-143">Приводятся общие сведения, рекомендации и ограничения при использовании данных FILESTREAM совместно с другими возможностями SQL Server.</span><span class="sxs-lookup"><span data-stu-id="969ca-143">Provides considerations, guidelines and limitations for using FILESTREAM data with other features of SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="969ca-144">См. также</span><span class="sxs-lookup"><span data-stu-id="969ca-144">See Also</span></span>  
 [<span data-ttu-id="969ca-145">Типы данных SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="969ca-145">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [<span data-ttu-id="969ca-146">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="969ca-146">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="969ca-147">Управление доступом для кода и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="969ca-147">Code Access Security and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/code-access-security.md)  
 [<span data-ttu-id="969ca-148">Двоичные данные и данные большого объема SQL Server</span><span class="sxs-lookup"><span data-stu-id="969ca-148">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [<span data-ttu-id="969ca-149">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="969ca-149">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
