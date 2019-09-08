---
title: BFILE в Oracle
ms.date: 03/30/2017
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
ms.openlocfilehash: 214140bb8fcf43154b014ea3db609d355a27af7c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794628"
---
# <a name="oracle-bfiles"></a><span data-ttu-id="75290-102">BFILE в Oracle</span><span class="sxs-lookup"><span data-stu-id="75290-102">Oracle BFILEs</span></span>
<span data-ttu-id="75290-103">Поставщик данных .NET Framework для Oracle содержит класс <xref:System.Data.OracleClient.OracleBFile>, который используется для работы с типом данных Oracle <xref:System.Data.OracleClient.OracleType.BFile>.</span><span class="sxs-lookup"><span data-stu-id="75290-103">The .NET Framework Data Provider for Oracle includes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle <xref:System.Data.OracleClient.OracleType.BFile> data type.</span></span>  
  
 <span data-ttu-id="75290-104">Тип данных Oracle **BFILE** является типом данных Oracle **LOB** , который содержит ссылку на двоичные данные с максимальным размером 4 гигабайта.</span><span class="sxs-lookup"><span data-stu-id="75290-104">The Oracle **BFILE** data type is an Oracle **LOB** data type that contains a reference to binary data with a maximum size of 4 gigabytes.</span></span> <span data-ttu-id="75290-105">Тип **BFILE** Oracle отличается от других типов данных Oracle **LOB** тем, что его данные хранятся в физическом файле операционной системы, а не на сервере.</span><span class="sxs-lookup"><span data-stu-id="75290-105">An Oracle **BFILE** differs from other Oracle **LOB** data types in that its data is stored in a physical file in the operating system instead of on the server.</span></span> <span data-ttu-id="75290-106">Обратите внимание, что тип данных **BFILE** предоставляет доступ только для чтения к данным.</span><span class="sxs-lookup"><span data-stu-id="75290-106">Note that the **BFILE** data type provides read-only access to data.</span></span>  
  
 <span data-ttu-id="75290-107">Другие характеристики типа данных **BFILE** , которые отличают его от типа данных **LOB** ,:</span><span class="sxs-lookup"><span data-stu-id="75290-107">Other characteristics of a **BFILE** data type that distinguish it from a **LOB** data type are that it:</span></span>  
  
- <span data-ttu-id="75290-108">содержит неструктурированные данные;</span><span class="sxs-lookup"><span data-stu-id="75290-108">Contains unstructured data.</span></span>  
  
- <span data-ttu-id="75290-109">поддерживает обработку данных на сервере в виде фрагментов;</span><span class="sxs-lookup"><span data-stu-id="75290-109">Supports server-side chunking.</span></span>  
  
- <span data-ttu-id="75290-110">использует ссылочную семантику копирования.</span><span class="sxs-lookup"><span data-stu-id="75290-110">Uses reference copy semantics.</span></span> <span data-ttu-id="75290-111">Например, при выполнении операции копирования в **BFILE**копируется только указатель типа « **BFILE** » (являющийся ссылкой на файл).</span><span class="sxs-lookup"><span data-stu-id="75290-111">For example, if you perform a copy operation on a **BFILE**, only the **BFILE** locator (which is a reference to the file) is copied.</span></span> <span data-ttu-id="75290-112">Данные файла не копируются.</span><span class="sxs-lookup"><span data-stu-id="75290-112">The data in the file is not copied.</span></span>  
  
 <span data-ttu-id="75290-113">Тип данных **BFILE** следует использовать для ссылок на большие объекты, которые имеют большой размер и поэтому непрактично хранить в базе данных.</span><span class="sxs-lookup"><span data-stu-id="75290-113">The **BFILE** data type should be used for referencing LOBs that are large in size, and therefore, not practical to store in the database.</span></span> <span data-ttu-id="75290-114">При использовании типа данных **BFILE** , сравниваемого с типом данных **LOB** , используются дополнительные затраты на клиент, сервер и связь.</span><span class="sxs-lookup"><span data-stu-id="75290-114">More client, server, and communication overhead is involved when using a **BFILE** data type compared with the **LOB** data type.</span></span> <span data-ttu-id="75290-115">Более эффективно обращаться к **BFILE** , если нужно получить лишь небольшой объем данных.</span><span class="sxs-lookup"><span data-stu-id="75290-115">It is more efficient to access a **BFILE** if you only need to obtain a small amount of data.</span></span> <span data-ttu-id="75290-116">Доступ к большим объектам, хранящимся в базе данных, эффективнее, если нужно получить весь объект целиком.</span><span class="sxs-lookup"><span data-stu-id="75290-116">It is more efficient to access database-resident LOBs if you need to obtain the entire object.</span></span>  
  
 <span data-ttu-id="75290-117">Каждый объект **ораклебфиле** , отличный от NULL, связан с двумя сущностями, которые определяют расположение базового физического файла:</span><span class="sxs-lookup"><span data-stu-id="75290-117">Each non-NULL **OracleBFile** object is associated with two entities that define the location of the underlying physical file:</span></span>  
  
1. <span data-ttu-id="75290-118">Объект Oracle DIRECTORY, который является псевдонимом базы данных для каталога в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="75290-118">An Oracle DIRECTORY object, which is a database alias for a directory in the file system, and</span></span>  
  
2. <span data-ttu-id="75290-119">Имя файла базового физического файла, расположенного в каталоге, связанном с объектом DIRECTORY.</span><span class="sxs-lookup"><span data-stu-id="75290-119">The file name of the underlying physical file, which is located in the directory associated with the DIRECTORY object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75290-120">Пример</span><span class="sxs-lookup"><span data-stu-id="75290-120">Example</span></span>  
 <span data-ttu-id="75290-121">В следующем C# примере показано, как создать **BFILE** в таблице Oracle, а затем извлечь его в виде объекта **ораклебфиле** .</span><span class="sxs-lookup"><span data-stu-id="75290-121">The following C# example demonstrates how you can create a **BFILE** in an Oracle table and then retrieve it in the form of an **OracleBFile** object.</span></span> <span data-ttu-id="75290-122">В примере демонстрируется использование <xref:System.Data.OracleClient.OracleDataReader> объекта и методов **ораклебфиле** **Seek** и **Read** .</span><span class="sxs-lookup"><span data-stu-id="75290-122">The example demonstrates using the <xref:System.Data.OracleClient.OracleDataReader> object and the **OracleBFile** **Seek** and **Read** methods.</span></span> <span data-ttu-id="75290-123">Обратите внимание, что для использования этого примера необходимо сначала создать каталог с именем "c:\\\бфилес" и файлом с именем "MyFile. jpg" на сервере Oracle.</span><span class="sxs-lookup"><span data-stu-id="75290-123">Note that in order to use this sample, you must first create a directory named "c:\\\bfiles" and file named "MyFile.jpg" on the Oracle server.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="75290-124">См. также</span><span class="sxs-lookup"><span data-stu-id="75290-124">See also</span></span>

- [<span data-ttu-id="75290-125">Oracle и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="75290-125">Oracle and ADO.NET</span></span>](oracle-and-adonet.md)
- [<span data-ttu-id="75290-126">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="75290-126">ADO.NET Overview</span></span>](ado-net-overview.md)
