---
title: Извлечение сведений о схеме базы данных
ms.date: 03/30/2017
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
ms.openlocfilehash: 885d3c9ad61c9099c960ddb0c0f77fa8a98dbefa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133709"
---
# <a name="retrieving-database-schema-information"></a>Извлечение сведений о схеме базы данных
Получение сведений о схеме из базы данных выполняется с помощью процесса обнаружения схемы. Обнаружение схемы позволяет приложениям запрашивать, что управляемые поставщики для поиска и возвращения сведений о схеме базы данных, также называется *метаданных*, конкретной базы данных. Различные элементы схемы базы данных, например таблицы, столбцы и хранимые процедуры, предоставляются через коллекции схем. Каждая коллекция схемы в зависимости от используемого поставщика содержит различные сведения о схеме.  
  
 Каждый из управляемых поставщиков .NET Framework реализуют **GetSchema** метод в **подключения** класс и сведения схемы, которые возвращаются из **GetSchema**метод поставляется в виде <xref:System.Data.DataTable>. **GetSchema** это перегруженный метод, содержащий необязательные параметры для указания возвращаемой коллекции схем и ограничения объема возвращаемых сведений.  
  
 Поставщики данных .NET Framework для OLE DB, ODBC, Oracle и SqlClient предоставляют **GetSchemaTable** метод, возвращающий объект DataTable, описывающий метаданные столбца **DataReader**.  
  
 Поставщик данных .NET Framework для OLE DB также предоставляет данные схемы с помощью метода <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> объекта <xref:System.Data.OleDb.OleDbConnection>. Как аргументы **GetOleDbSchemaTable** принимает <xref:System.Data.OleDb.OleDbSchemaGuid> , идентифицирующий возвращаемые данные схемы, и массив ограничений, накладываемых на возвращаемые столбцы. **GetOleDbSchemaTable** возвращает <xref:System.Data.DataTable> заполненный запрошенными сведениями схемы.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Коллекции GetSchema и Schema](../../../../docs/framework/data/adonet/getschema-and-schema-collections.md)  
 Описывает **GetSchema** метод и как его можно использовать для получения и ограничения сведений о схеме из базы данных.  
  
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

- [Извлечение и изменение данных в ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
