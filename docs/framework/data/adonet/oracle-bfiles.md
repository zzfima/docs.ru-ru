---
title: BFILE в Oracle
ms.date: 03/30/2017
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
ms.openlocfilehash: 40060a7ea8576e08140d972072d086606d640366
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149444"
---
# <a name="oracle-bfiles"></a><span data-ttu-id="cde99-102">BFILE в Oracle</span><span class="sxs-lookup"><span data-stu-id="cde99-102">Oracle BFILEs</span></span>
<span data-ttu-id="cde99-103">Поставщик данных .NET Framework для Oracle содержит класс <xref:System.Data.OracleClient.OracleBFile>, который используется для работы с типом данных Oracle <xref:System.Data.OracleClient.OracleType.BFile>.</span><span class="sxs-lookup"><span data-stu-id="cde99-103">The .NET Framework Data Provider for Oracle includes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle <xref:System.Data.OracleClient.OracleType.BFile> data type.</span></span>  
  
 <span data-ttu-id="cde99-104">Тип данных Oracle **BFILE** — это тип данных Oracle **LOB,** содержащий ссылку на двоичные данные с максимальным размером 4 гигабайта.</span><span class="sxs-lookup"><span data-stu-id="cde99-104">The Oracle **BFILE** data type is an Oracle **LOB** data type that contains a reference to binary data with a maximum size of 4 gigabytes.</span></span> <span data-ttu-id="cde99-105">Oracle **BFILE** отличается от других типов данных Oracle **LOB** тем, что его данные хранятся в физическом файле в операционной системе, а не на сервере.</span><span class="sxs-lookup"><span data-stu-id="cde99-105">An Oracle **BFILE** differs from other Oracle **LOB** data types in that its data is stored in a physical file in the operating system instead of on the server.</span></span> <span data-ttu-id="cde99-106">Обратите внимание, что тип данных **BFILE** обеспечивает доступ к данным только для чтения.</span><span class="sxs-lookup"><span data-stu-id="cde99-106">Note that the **BFILE** data type provides read-only access to data.</span></span>  
  
 <span data-ttu-id="cde99-107">Другие характеристики типа данных **BFILE,** которые отличают его от типа данных **LOB,** являются то, что он:</span><span class="sxs-lookup"><span data-stu-id="cde99-107">Other characteristics of a **BFILE** data type that distinguish it from a **LOB** data type are that it:</span></span>  
  
- <span data-ttu-id="cde99-108">содержит неструктурированные данные;</span><span class="sxs-lookup"><span data-stu-id="cde99-108">Contains unstructured data.</span></span>  
  
- <span data-ttu-id="cde99-109">поддерживает обработку данных на сервере в виде фрагментов;</span><span class="sxs-lookup"><span data-stu-id="cde99-109">Supports server-side chunking.</span></span>  
  
- <span data-ttu-id="cde99-110">использует ссылочную семантику копирования.</span><span class="sxs-lookup"><span data-stu-id="cde99-110">Uses reference copy semantics.</span></span> <span data-ttu-id="cde99-111">Например, если вы выполняете операцию копирования на **BFILE,** копируется только локатор **BFILE** (который является ссылкой на файл).</span><span class="sxs-lookup"><span data-stu-id="cde99-111">For example, if you perform a copy operation on a **BFILE**, only the **BFILE** locator (which is a reference to the file) is copied.</span></span> <span data-ttu-id="cde99-112">Данные файла не копируются.</span><span class="sxs-lookup"><span data-stu-id="cde99-112">The data in the file is not copied.</span></span>  
  
 <span data-ttu-id="cde99-113">Тип данных **BFILE** следует использовать для ссылки LOBs, которые имеют большой размер, и, следовательно, не практично для хранения в базе данных.</span><span class="sxs-lookup"><span data-stu-id="cde99-113">The **BFILE** data type should be used for referencing LOBs that are large in size, and therefore, not practical to store in the database.</span></span> <span data-ttu-id="cde99-114">При использовании типа данных **BFILE** используется больше накладных расходов на клиента, серверии и коммуникации по сравнению с типом данных **LOB.**</span><span class="sxs-lookup"><span data-stu-id="cde99-114">More client, server, and communication overhead is involved when using a **BFILE** data type compared with the **LOB** data type.</span></span> <span data-ttu-id="cde99-115">Это более эффективно для доступа к **BFILE,** если вам нужно только получить небольшой объем данных.</span><span class="sxs-lookup"><span data-stu-id="cde99-115">It is more efficient to access a **BFILE** if you only need to obtain a small amount of data.</span></span> <span data-ttu-id="cde99-116">Доступ к большим объектам, хранящимся в базе данных, эффективнее, если нужно получить весь объект целиком.</span><span class="sxs-lookup"><span data-stu-id="cde99-116">It is more efficient to access database-resident LOBs if you need to obtain the entire object.</span></span>  
  
 <span data-ttu-id="cde99-117">Каждый объект **OracleBFile,** не являющиеся НУЛЛ, связан с двумя сущностями, определяющими местоположение базового физического файла:</span><span class="sxs-lookup"><span data-stu-id="cde99-117">Each non-NULL **OracleBFile** object is associated with two entities that define the location of the underlying physical file:</span></span>  
  
1. <span data-ttu-id="cde99-118">Объект Oracle DIRECTORY, который является псевдонимом базы данных для каталога в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="cde99-118">An Oracle DIRECTORY object, which is a database alias for a directory in the file system, and</span></span>  
  
2. <span data-ttu-id="cde99-119">Имя файла базового физического файла, расположенного в каталоге, связанном с объектом DIRECTORY.</span><span class="sxs-lookup"><span data-stu-id="cde99-119">The file name of the underlying physical file, which is located in the directory associated with the DIRECTORY object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cde99-120">Пример</span><span class="sxs-lookup"><span data-stu-id="cde99-120">Example</span></span>  
 <span data-ttu-id="cde99-121">Следующий пример C-образного примера показывает, как можно создать **BFILE** в таблице Oracle, а затем получить его в виде объекта **OracleBFile.**</span><span class="sxs-lookup"><span data-stu-id="cde99-121">The following C# example demonstrates how you can create a **BFILE** in an Oracle table and then retrieve it in the form of an **OracleBFile** object.</span></span> <span data-ttu-id="cde99-122">Пример демонстрирует использование <xref:System.Data.OracleClient.OracleDataReader> объекта и **OracleBFile** **искать** и **читать** методы.</span><span class="sxs-lookup"><span data-stu-id="cde99-122">The example demonstrates using the <xref:System.Data.OracleClient.OracleDataReader> object and the **OracleBFile** **Seek** and **Read** methods.</span></span> <span data-ttu-id="cde99-123">Обратите внимание, что для того, чтобы использовать этот образец, необходимо сначала создать каталог под названием "c:\\bfiles" и файл под названием "MyFile.jpg" на сервере Oracle.</span><span class="sxs-lookup"><span data-stu-id="cde99-123">Note that in order to use this sample, you must first create a directory named "c:\\\bfiles" and file named "MyFile.jpg" on the Oracle server.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cde99-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cde99-124">See also</span></span>

- [<span data-ttu-id="cde99-125">Oracle и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="cde99-125">Oracle and ADO.NET</span></span>](oracle-and-adonet.md)
- [<span data-ttu-id="cde99-126">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="cde99-126">ADO.NET Overview</span></span>](ado-net-overview.md)
