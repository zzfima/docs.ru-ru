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
# <a name="oracle-bfiles"></a>BFILE в Oracle
Поставщик данных .NET Framework для Oracle содержит класс <xref:System.Data.OracleClient.OracleBFile>, который используется для работы с типом данных Oracle <xref:System.Data.OracleClient.OracleType.BFile>.  
  
 Oracle **BFILE** имеет тип данных Oracle **LOB** тип данных, который содержит ссылку на двоичные данные с максимальным размером 4 гигабайта. Oracle **BFILE** отличается от других Oracle **LOB** типы данных, в том, что данные хранятся в физическом файле в операционной системе, а не на сервере. Обратите внимание, что **BFILE** тип данных предоставляет доступ только для чтения к данным.  
  
 Другие характеристики **BFILE** тип данных, отличающие его от **LOB** типа данных:  
  
- содержит неструктурированные данные;  
  
- поддерживает обработку данных на сервере в виде фрагментов;  
  
- использует ссылочную семантику копирования. Например, если выполнить операцию копирования на **BFILE**, только **BFILE** копируется указателя (который является ссылкой на файл). Данные файла не копируются.  
  
 **BFILE** тип данных должен использоваться для ссылки на бизнес-приложений, которые являются большой размер и, следовательно, нецелесообразно хранить в базе данных. Дополнительные клиентских, серверных и обмен данными издержки при использовании **BFILE** по сравнению с типом данных **LOB** тип данных. Более эффективно, для доступа к **BFILE** Если вам нужно получить небольшой объем данных. Доступ к большим объектам, хранящимся в базе данных, эффективнее, если нужно получить весь объект целиком.  
  
 Каждого НЕНУЛЕВОГО **OracleBFile** объект связан с двумя сущностями, определяющими местоположение базового физического файла:  
  
1. Объект Oracle DIRECTORY, который является псевдонимом базы данных для каталога в файловой системе.  
  
2. Имя файла базового физического файла, расположенного в каталоге, связанном с объектом DIRECTORY.  
  
## <a name="example"></a>Пример  
 В следующем примере C# показано, как создать **BFILE** в таблице Oracle, а затем извлеките его в виде **OracleBFile** объекта. В примере показано использование <xref:System.Data.OracleClient.OracleDataReader> объекта и **OracleBFile** **Seek** и **чтения** методы. Обратите внимание, что для использования этого образца, необходимо сначала создать каталог с именем «c:\\\bfiles» и файл с именем «MyFile.jpg» на сервере Oracle.  
  
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

- [Oracle и ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
