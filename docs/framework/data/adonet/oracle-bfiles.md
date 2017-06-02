---
title: "BFILE в Oracle | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# BFILE в Oracle
Поставщик данных .NET Framework для Oracle содержит класс <xref:System.Data.OracleClient.OracleBFile>, который используется для работы с типом данных Oracle <xref:System.Data.OracleClient.OracleType>.  
  
 Тип данных Oracle **BFILE** предназначен для работы с типом данных Oracle **LOB**, содержащим ссылку на двоичные данные с максимальным размером 4 гигабайта.  Тип данных Oracle **BFILE** отличается от типов данных Oracle **LOB** тем, что его данные хранятся в физическом файле в операционной системе, а не на сервере.  Обратите внимание, что тип данных **BFILE** обеспечивает доступ только для чтения данных.  
  
 Другие характеристики типа данных **BFILE**, отличающие его от типа данных **LOB**, состоят в том, что он:  
  
-   содержит неструктурированные данные;  
  
-   поддерживает обработку данных на сервере в виде фрагментов;  
  
-   использует ссылочную семантику копирования.  Например, при копировании **BFILE** копируется только указатель **BFILE** \(являющийся ссылкой на этот файл\).  Данные файла не копируются.  
  
 Тип данных **BFILE** следует использовать для ссылок на очень большие объекты, которые нецелесообразно хранить в базе данных.  При использовании типа данных **BFILE** возникают дополнительные издержки на клиенте, сервере и сети по сравнению с типом данных **LOB**.  Тип данных **BFILE** эффективнее, если нужно получить небольшой объем данных.  Доступ к большим объектам, хранящимся в базе данных, эффективнее, если нужно получить весь объект целиком.  
  
 Каждый объект **OracleBFile**, не допускающий значения NULL, связан с двумя сущностями, определяющими местоположение базового физического файла.  
  
1.  Объект Oracle DIRECTORY, который является псевдонимом базы данных для каталога в файловой системе.  
  
2.  Имя файла базового физического файла, расположенного в каталоге, связанном с объектом DIRECTORY.  
  
## Пример  
 Следующий пример на языке C\# демонстрирует создание типа данных **BFILE** в таблице Oracle и его получение в виде объекта **OracleBFile**.  В примере показано использование объекта <xref:System.Data.OracleClient.OracleDataReader> и методов **OracleBFile**: **Seek** и **Read**.  Обратите внимание, для использования этого образца вначале на сервере Oracle следует создать каталог «c:\\\\bfiles» и файл с именем «MyFile.jpg».  
  
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
  
## См. также  
 [Oracle и ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)