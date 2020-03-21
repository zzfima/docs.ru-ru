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
# <a name="oracle-bfiles"></a>BFILE в Oracle
Поставщик данных .NET Framework для Oracle содержит класс <xref:System.Data.OracleClient.OracleBFile>, который используется для работы с типом данных Oracle <xref:System.Data.OracleClient.OracleType.BFile>.  
  
 Тип данных Oracle **BFILE** — это тип данных Oracle **LOB,** содержащий ссылку на двоичные данные с максимальным размером 4 гигабайта. Oracle **BFILE** отличается от других типов данных Oracle **LOB** тем, что его данные хранятся в физическом файле в операционной системе, а не на сервере. Обратите внимание, что тип данных **BFILE** обеспечивает доступ к данным только для чтения.  
  
 Другие характеристики типа данных **BFILE,** которые отличают его от типа данных **LOB,** являются то, что он:  
  
- содержит неструктурированные данные;  
  
- поддерживает обработку данных на сервере в виде фрагментов;  
  
- использует ссылочную семантику копирования. Например, если вы выполняете операцию копирования на **BFILE,** копируется только локатор **BFILE** (который является ссылкой на файл). Данные файла не копируются.  
  
 Тип данных **BFILE** следует использовать для ссылки LOBs, которые имеют большой размер, и, следовательно, не практично для хранения в базе данных. При использовании типа данных **BFILE** используется больше накладных расходов на клиента, серверии и коммуникации по сравнению с типом данных **LOB.** Это более эффективно для доступа к **BFILE,** если вам нужно только получить небольшой объем данных. Доступ к большим объектам, хранящимся в базе данных, эффективнее, если нужно получить весь объект целиком.  
  
 Каждый объект **OracleBFile,** не являющиеся НУЛЛ, связан с двумя сущностями, определяющими местоположение базового физического файла:  
  
1. Объект Oracle DIRECTORY, который является псевдонимом базы данных для каталога в файловой системе.  
  
2. Имя файла базового физического файла, расположенного в каталоге, связанном с объектом DIRECTORY.  
  
## <a name="example"></a>Пример  
 Следующий пример C-образного примера показывает, как можно создать **BFILE** в таблице Oracle, а затем получить его в виде объекта **OracleBFile.** Пример демонстрирует использование <xref:System.Data.OracleClient.OracleDataReader> объекта и **OracleBFile** **искать** и **читать** методы. Обратите внимание, что для того, чтобы использовать этот образец, необходимо сначала создать каталог под названием "c:\\bfiles" и файл под названием "MyFile.jpg" на сервере Oracle.  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Oracle и ADO.NET](oracle-and-adonet.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
