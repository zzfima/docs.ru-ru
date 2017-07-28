---
title: "Получение сведений о схеме базы данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Получение сведений о схеме базы данных
Получение сведений о схеме из базы данных выполняется с помощью процесса обнаружения схемы.  Обнаружение схемы позволяет приложениям запрашивать управляемые поставщики для поиска и возвращения сведений о схеме базы данных, также называемых *метаданные*, для данной базы данных.  Различные элементы схемы базы данных, например таблицы, столбцы и хранимые процедуры, предоставляются через коллекции схем.  Каждая коллекция схемы в зависимости от используемого поставщика содержит различные сведения о схеме.  
  
 Каждый из управляемых поставщиков .NET Framework реализует метод **GetSchema** в классе **Connection**, и сведения о схеме, возвращаемые из метода **GetSchema**, представляются в виде объекта <xref:System.Data.DataTable>.  **GetSchema** — перегружаемый метод, содержащий необязательные параметры для указания возвращаемой коллекции схем и ограничения объема возвращаемых сведений.  
  
 Поставщики данных .NET Framework для OLE DB, ODBC, Oracle и SqlClient предоставляют метод **GetSchemaTable**, возвращающий объект DataTable с описанием метаданных столбцов объекта **DataReader**.  
  
 Поставщик данных .NET Framework для OLE DB также предоставляет данные схемы с помощью метода <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> объекта <xref:System.Data.OleDb.OleDbConnection>.  В качестве аргументов метод **GetOleDbSchemaTable** принимает объект <xref:System.Data.OleDb.OleDbSchemaGuid>, идентифицирующий возвращаемые данные схемы, и массив ограничений, накладываемых на возвращаемые столбцы.  Метод **GetOleDbSchemaTable** возвращает объект <xref:System.Data.DataTable>, заполненный запрошенными сведениями о схеме.  
  
## В этом подразделе  
 [Метод GetSchema и коллекции схем](../../../../docs/framework/data/adonet/getschema-and-schema-collections.md)  
 Описывает метод **GetSchema** и его использование для получения и ограничения сведений о схеме из базы данных.  
  
 Ограничения схемы  
 Описываются ограничения схемы, которые можно использовать с методом **GetSchema**.  
  
 [Стандартные коллекции схем](../../../../docs/framework/data/adonet/common-schema-collections.md)  
 Описывает стандартные коллекции схем, поддерживаемые всеми управляемыми поставщиками .NET Framework.  
  
 [Коллекции схем SQL Server](../../../../docs/framework/data/adonet/sql-server-schema-collections.md)  
 Описывается коллекция схем, поддерживаемая поставщиком .NET Framework для SQL Server.  
  
 [Коллекции схем Oracle](../../../../docs/framework/data/adonet/oracle-schema-collections.md)  
 Описывается коллекция схем, поддерживаемая поставщиком .NET Framework для Oracle.  
  
 [Коллекции схем ODBC](../../../../docs/framework/data/adonet/odbc-schema-collections.md)  
 Описываются коллекции схем для драйверов ODBC.  
  
 [Коллекции схем OLE DB](../../../../docs/framework/data/adonet/ole-db-schema-collections.md)  
 Описываются коллекции схем для поставщиков OLE DB.  
  
## Ссылка  
 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 Описывает метод **GetSchema** класса <xref:System.Data.Common.DbConnection>.  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 Описывает метод **GetSchema** класса <xref:System.Data.Odbc.OdbcConnection>.  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 Описывает метод **GetSchema** класса <xref:System.Data.OleDb.OleDbConnection>.  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 Описывает метод **GetSchema** класса <xref:System.Data.OracleClient.OracleConnection>.  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 Описывает метод **GetSchema** класса <xref:System.Data.SqlClient.SqlConnection>.  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 Описывается метод **GetSchemaTable** класса <xref:System.Data.Common.DbDataReader>.  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 Описывается метод **GetSchemaTable** класса <xref:System.Data.Odbc.OdbcDataReader>.  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 Описывается метод **GetSchemaTable** класса <xref:System.Data.OleDb.OleDbDataReader>.  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 Описывается метод **GetSchemaTable** класса <xref:System.Data.OracleClient.OracleDataReader>.  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 Описывается метод **GetSchemaTable** класса <xref:System.Data.SqlClient.SqlDataReader>.  
  
## См. также  
 [Получение и изменение данных в ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)