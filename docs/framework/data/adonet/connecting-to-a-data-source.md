---
title: "Подключение к источнику данных в ADO.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Подключение к источнику данных в ADO.NET
В ADO.NET объект **Connection** используется для подключения к определенному источнику данных путем предоставления в строке соединения сведений, необходимых для проверки подлинности.  Используемый объект **Connection** зависит от типа источника данных.  
  
 Каждый поставщик данных .NET Framework, входящий в состав .NET Framework, включает объект <xref:System.Data.Common.DbConnection>: поставщик данных .NET Framework для OLE DB содержит объект <xref:System.Data.OleDb.OleDbConnection>, поставщик данных .NET Framework для SQL Server содержит объект <xref:System.Data.SqlClient.SqlConnection>, поставщик данных .NET Framework для ODBC содержит объект <xref:System.Data.Odbc.OdbcConnection>, поставщик данных .NET Framework для Oracle содержит объект <xref:System.Data.OracleClient.OracleConnection>.  
  
## В этом подразделе  
 [Установление соединения](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 Описание использования объекта **Connection** для установления соединения с источником данных.  
  
 [События соединений](../../../../docs/framework/data/adonet/connection-events.md)  
 Описание использования события **InfoMessage** для получения информационных сообщений из источника данных.  
  
## См. также  
 [Строки подключения](../../../../docs/framework/data/adonet/connection-strings.md)   
 [Организация пулов соединений](../../../../docs/framework/data/adonet/connection-pooling.md)   
 [Команды и параметры](../../../../docs/framework/data/adonet/commands-and-parameters.md)   
 [Объекты DataAdapter и DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)   
 [Транзакции и параллелизм](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)