---
title: BFILE в Oracle
ms.date: 03/30/2017
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
ms.openlocfilehash: 2d7db741cea5421b2391588c0479f44e2b478ca3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626426"
---
# <a name="oracle-bfiles"></a><span data-ttu-id="32519-102">BFILE в Oracle</span><span class="sxs-lookup"><span data-stu-id="32519-102">Oracle BFILEs</span></span>
<span data-ttu-id="32519-103">Поставщик данных .NET Framework для Oracle содержит класс <xref:System.Data.OracleClient.OracleBFile>, который используется для работы с типом данных Oracle <xref:System.Data.OracleClient.OracleType.BFile>.</span><span class="sxs-lookup"><span data-stu-id="32519-103">The .NET Framework Data Provider for Oracle includes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle <xref:System.Data.OracleClient.OracleType.BFile> data type.</span></span>  
  
 <span data-ttu-id="32519-104">Oracle **BFILE** имеет тип данных Oracle **LOB** тип данных, который содержит ссылку на двоичные данные с максимальным размером 4 гигабайта.</span><span class="sxs-lookup"><span data-stu-id="32519-104">The Oracle **BFILE** data type is an Oracle **LOB** data type that contains a reference to binary data with a maximum size of 4 gigabytes.</span></span> <span data-ttu-id="32519-105">Oracle **BFILE** отличается от других Oracle **LOB** типы данных, в том, что данные хранятся в физическом файле в операционной системе, а не на сервере.</span><span class="sxs-lookup"><span data-stu-id="32519-105">An Oracle **BFILE** differs from other Oracle **LOB** data types in that its data is stored in a physical file in the operating system instead of on the server.</span></span> <span data-ttu-id="32519-106">Обратите внимание, что **BFILE** тип данных предоставляет доступ только для чтения к данным.</span><span class="sxs-lookup"><span data-stu-id="32519-106">Note that the **BFILE** data type provides read-only access to data.</span></span>  
  
 <span data-ttu-id="32519-107">Другие характеристики **BFILE** тип данных, отличающие его от **LOB** типа данных:</span><span class="sxs-lookup"><span data-stu-id="32519-107">Other characteristics of a **BFILE** data type that distinguish it from a **LOB** data type are that it:</span></span>  
  
- <span data-ttu-id="32519-108">содержит неструктурированные данные;</span><span class="sxs-lookup"><span data-stu-id="32519-108">Contains unstructured data.</span></span>  
  
- <span data-ttu-id="32519-109">поддерживает обработку данных на сервере в виде фрагментов;</span><span class="sxs-lookup"><span data-stu-id="32519-109">Supports server-side chunking.</span></span>  
  
- <span data-ttu-id="32519-110">использует ссылочную семантику копирования.</span><span class="sxs-lookup"><span data-stu-id="32519-110">Uses reference copy semantics.</span></span> <span data-ttu-id="32519-111">Например, если выполнить операцию копирования на **BFILE**, только **BFILE** копируется указателя (который является ссылкой на файл).</span><span class="sxs-lookup"><span data-stu-id="32519-111">For example, if you perform a copy operation on a **BFILE**, only the **BFILE** locator (which is a reference to the file) is copied.</span></span> <span data-ttu-id="32519-112">Данные файла не копируются.</span><span class="sxs-lookup"><span data-stu-id="32519-112">The data in the file is not copied.</span></span>  
  
 <span data-ttu-id="32519-113">**BFILE** тип данных должен использоваться для ссылки на бизнес-приложений, которые являются большой размер и, следовательно, нецелесообразно хранить в базе данных.</span><span class="sxs-lookup"><span data-stu-id="32519-113">The **BFILE** data type should be used for referencing LOBs that are large in size, and therefore, not practical to store in the database.</span></span> <span data-ttu-id="32519-114">Дополнительные клиентских, серверных и обмен данными издержки при использовании **BFILE** по сравнению с типом данных **LOB** тип данных.</span><span class="sxs-lookup"><span data-stu-id="32519-114">More client, server, and communication overhead is involved when using a **BFILE** data type compared with the **LOB** data type.</span></span> <span data-ttu-id="32519-115">Более эффективно, для доступа к **BFILE** Если вам нужно получить небольшой объем данных.</span><span class="sxs-lookup"><span data-stu-id="32519-115">It is more efficient to access a **BFILE** if you only need to obtain a small amount of data.</span></span> <span data-ttu-id="32519-116">Доступ к большим объектам, хранящимся в базе данных, эффективнее, если нужно получить весь объект целиком.</span><span class="sxs-lookup"><span data-stu-id="32519-116">It is more efficient to access database-resident LOBs if you need to obtain the entire object.</span></span>  
  
 <span data-ttu-id="32519-117">Каждого НЕНУЛЕВОГО **OracleBFile** объект связан с двумя сущностями, определяющими местоположение базового физического файла:</span><span class="sxs-lookup"><span data-stu-id="32519-117">Each non-NULL **OracleBFile** object is associated with two entities that define the location of the underlying physical file:</span></span>  
  
1. <span data-ttu-id="32519-118">Объект Oracle DIRECTORY, который является псевдонимом базы данных для каталога в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="32519-118">An Oracle DIRECTORY object, which is a database alias for a directory in the file system, and</span></span>  
  
2. <span data-ttu-id="32519-119">Имя файла базового физического файла, расположенного в каталоге, связанном с объектом DIRECTORY.</span><span class="sxs-lookup"><span data-stu-id="32519-119">The file name of the underlying physical file, which is located in the directory associated with the DIRECTORY object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32519-120">Пример</span><span class="sxs-lookup"><span data-stu-id="32519-120">Example</span></span>  
 <span data-ttu-id="32519-121">В следующем примере C# показано, как создать **BFILE** в таблице Oracle, а затем извлеките его в виде **OracleBFile** объекта.</span><span class="sxs-lookup"><span data-stu-id="32519-121">The following C# example demonstrates how you can create a **BFILE** in an Oracle table and then retrieve it in the form of an **OracleBFile** object.</span></span> <span data-ttu-id="32519-122">В примере показано использование <xref:System.Data.OracleClient.OracleDataReader> объекта и **OracleBFile** **Seek** и **чтения** методы.</span><span class="sxs-lookup"><span data-stu-id="32519-122">The example demonstrates using the <xref:System.Data.OracleClient.OracleDataReader> object and the **OracleBFile** **Seek** and **Read** methods.</span></span> <span data-ttu-id="32519-123">Обратите внимание, что для использования этого образца, необходимо сначала создать каталог с именем «c:\\\bfiles» и файл с именем «MyFile.jpg» на сервере Oracle.</span><span class="sxs-lookup"><span data-stu-id="32519-123">Note that in order to use this sample, you must first create a directory named "c:\\\bfiles" and file named "MyFile.jpg" on the Oracle server.</span></span>  
  
```csharp  
using System;  
using System.IO;  
using System.Data;  
using System.Data.OracleClient;  
  
public class Sample  
{  
   public static void Main(string[] args)  
   {  
      OracleConnection connection = new OracleConnection(  
        "Data Source=Oracle8i;Integrated Security=yes");  
      connection.Open();  
  
      OracleCommand command = connection.CreateCommand();  
      command.CommandText =   
        "CREATE or REPLACE DIRECTORY MyDir as 'c:\\bfiles'";  
      command.ExecuteNonQuery();  
      command.CommandText =   
        "DROP TABLE MyBFileTable";  
      try {  
        command.ExecuteNonQuery();  
      }  
      catch {  
      }  
      command.CommandText =   
        "CREATE TABLE MyBFileTable(col1 number, col2 BFILE)";  
      command.ExecuteNonQuery();  
      command.CommandText =   
        "INSERT INTO MyBFileTable values ('2', BFILENAME('MyDir', " +  
        "'MyFile.jpg'))";  
      command.ExecuteNonQuery();  
      command.CommandText = "SELECT * FROM MyBFileTable";  
  
        byte[] buffer = new byte[100];  
  
      OracleDataReader reader = command.ExecuteReader();  
      using (reader) {  
          if (reader.Read()) {  
                OracleBFile bFile = reader.GetOracleBFile(1);  
                using (bFile) {  
                  bFile.Seek(0, SeekOrigin.Begin);  
                  bFile.Read(buffer, 0, 100);  
              }  
          }  
      }  
  
      connection.Close();  
   }  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="32519-124">См. также</span><span class="sxs-lookup"><span data-stu-id="32519-124">See also</span></span>

- [<span data-ttu-id="32519-125">Oracle и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="32519-125">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [<span data-ttu-id="32519-126">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="32519-126">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
