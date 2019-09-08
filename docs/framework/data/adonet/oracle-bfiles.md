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
# <a name="oracle-bfiles"></a>BFILE в Oracle
Поставщик данных .NET Framework для Oracle содержит класс <xref:System.Data.OracleClient.OracleBFile>, который используется для работы с типом данных Oracle <xref:System.Data.OracleClient.OracleType.BFile>.  
  
 Тип данных Oracle **BFILE** является типом данных Oracle **LOB** , который содержит ссылку на двоичные данные с максимальным размером 4 гигабайта. Тип **BFILE** Oracle отличается от других типов данных Oracle **LOB** тем, что его данные хранятся в физическом файле операционной системы, а не на сервере. Обратите внимание, что тип данных **BFILE** предоставляет доступ только для чтения к данным.  
  
 Другие характеристики типа данных **BFILE** , которые отличают его от типа данных **LOB** ,:  
  
- содержит неструктурированные данные;  
  
- поддерживает обработку данных на сервере в виде фрагментов;  
  
- использует ссылочную семантику копирования. Например, при выполнении операции копирования в **BFILE**копируется только указатель типа « **BFILE** » (являющийся ссылкой на файл). Данные файла не копируются.  
  
 Тип данных **BFILE** следует использовать для ссылок на большие объекты, которые имеют большой размер и поэтому непрактично хранить в базе данных. При использовании типа данных **BFILE** , сравниваемого с типом данных **LOB** , используются дополнительные затраты на клиент, сервер и связь. Более эффективно обращаться к **BFILE** , если нужно получить лишь небольшой объем данных. Доступ к большим объектам, хранящимся в базе данных, эффективнее, если нужно получить весь объект целиком.  
  
 Каждый объект **ораклебфиле** , отличный от NULL, связан с двумя сущностями, которые определяют расположение базового физического файла:  
  
1. Объект Oracle DIRECTORY, который является псевдонимом базы данных для каталога в файловой системе.  
  
2. Имя файла базового физического файла, расположенного в каталоге, связанном с объектом DIRECTORY.  
  
## <a name="example"></a>Пример  
 В следующем C# примере показано, как создать **BFILE** в таблице Oracle, а затем извлечь его в виде объекта **ораклебфиле** . В примере демонстрируется использование <xref:System.Data.OracleClient.OracleDataReader> объекта и методов **ораклебфиле** **Seek** и **Read** . Обратите внимание, что для использования этого примера необходимо сначала создать каталог с именем "c:\\\бфилес" и файлом с именем "MyFile. jpg" на сервере Oracle.  
  
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
  
## <a name="see-also"></a>См. также

- [Oracle и ADO.NET](oracle-and-adonet.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
