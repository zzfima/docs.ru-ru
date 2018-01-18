---
title: "Извлечение сведений о схеме базы данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 09a0ec444801d1fe2caccf9e25a68e3c6ae8f5c2
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="retrieving-database-schema-information"></a>Извлечение сведений о схеме базы данных
Получение сведений о схеме из базы данных выполняется с помощью процесса обнаружения схемы. Обнаружение схемы позволяет приложениям запрашивать, управляемые поставщики для поиска и возвращения сведений о схеме базы данных, также называется *метаданных*, базы данных. Различные элементы схемы базы данных, например таблицы, столбцы и хранимые процедуры, предоставляются через коллекции схем. Каждая коллекция схемы в зависимости от используемого поставщика содержит различные сведения о схеме.  
  
 Каждый из управляемых поставщиков .NET Framework реализует **GetSchema** метод в **подключения** класс и сведения о схеме, возвращаемые из **GetSchema**представляются в виде <xref:System.Data.DataTable>. **GetSchema** это перегруженный метод, содержащий необязательные параметры для указания возвращаемой коллекции схем и ограничения объема возвращаемых сведений.  
  
 Поставщики данных .NET Framework для OLE DB, ODBC, Oracle и SqlClient предоставляют **GetSchemaTable** метод, возвращающий объект DataTable с описанием метаданных столбцов объекта **DataReader**.  
  
 Поставщик данных .NET Framework для OLE DB также предоставляет данные схемы с помощью метода <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> объекта <xref:System.Data.OleDb.OleDbConnection>. Как аргументы **GetOleDbSchemaTable** принимает <xref:System.Data.OleDb.OleDbSchemaGuid> , идентифицирующий возвращаемые данные схемы, и массив ограничений, накладываемых на возвращаемые столбцы. **GetOleDbSchemaTable** возвращает <xref:System.Data.DataTable> заполненный запрошенными сведениями схемы.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Коллекции GetSchema и Schema](../../../../docs/framework/data/adonet/getschema-and-schema-collections.md)  
 Описывает **GetSchema** и его использование для получения и ограничения сведений о схеме из базы данных.  
  
 Ограничения схемы  
 Описываются ограничения схемы, которые могут использоваться с **GetSchema**.  
  
 [Общие коллекции схемы](../../../../docs/framework/data/adonet/common-schema-collections.md)  
 Описывает стандартные коллекции схем, поддерживаемые всеми управляемыми поставщиками .NET Framework.  
  
 [Коллекции схемы SQL Server](../../../../docs/framework/data/adonet/sql-server-schema-collections.md)  
 Описывается коллекция схем, поддерживаемая поставщиком .NET Framework для SQL Server.  
  
 [Коллекции схемы Oracle](../../../../docs/framework/data/adonet/oracle-schema-collections.md)  
 Описывается коллекция схем, поддерживаемая поставщиком .NET Framework для Oracle.  
  
 [Коллекции схемы ODBC](../../../../docs/framework/data/adonet/odbc-schema-collections.md)  
 Описываются коллекции схем для драйверов ODBC.  
  
 [Коллекции схемы OLE DB](../../../../docs/framework/data/adonet/ole-db-schema-collections.md)  
 Описываются коллекции схем для поставщиков OLE DB.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 Описывает **GetSchema** метод <xref:System.Data.Common.DbConnection> класса.  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 Описывает **GetSchema** метод <xref:System.Data.Odbc.OdbcConnection> класса.  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 Описывает **GetSchema** метод <xref:System.Data.OleDb.OleDbConnection> класса.  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 Описывает **GetSchema** метод <xref:System.Data.OracleClient.OracleConnection> класса.  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 Описывает **GetSchema** метод <xref:System.Data.SqlClient.SqlConnection> класса.  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 Описывает **GetSchemaTable** метод <xref:System.Data.Common.DbDataReader> класса.  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 Описывает **GetSchemaTable** метод <xref:System.Data.Odbc.OdbcDataReader> класса.  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 Описывает **GetSchemaTable** метод <xref:System.Data.OleDb.OleDbDataReader> класса.  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 Описывает **GetSchemaTable** метод <xref:System.Data.OracleClient.OracleDataReader> класса.  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 Описывает **GetSchemaTable** метод <xref:System.Data.SqlClient.SqlDataReader> класса.  
  
## <a name="see-also"></a>См. также  
 [Извлечение и изменение данных в ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
