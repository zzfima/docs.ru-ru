---
title: Извлечение сведений о схеме базы данных
ms.date: 03/30/2017
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
ms.openlocfilehash: 26b234e35a0d0849914d87b61f4e8c8a87599448
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782736"
---
# <a name="retrieving-database-schema-information"></a>Извлечение сведений о схеме базы данных
Получение сведений о схеме из базы данных выполняется с помощью процесса обнаружения схемы. Обнаружение схемы позволяет приложениям запрашивать, что управляемые поставщики находят и возвращают сведения о схеме базы данных, также известные как *метаданные*заданной базы данных. Различные элементы схемы базы данных, например таблицы, столбцы и хранимые процедуры, предоставляются через коллекции схем. Каждая коллекция схемы в зависимости от используемого поставщика содержит различные сведения о схеме.  
  
 Каждый из .NET Framework управляемых поставщиков реализует метод **GetSchema** в классе **Connection** , а сведения о схеме, возвращаемые методом **GetSchema** , поступают <xref:System.Data.DataTable>в виде. Метод **GetSchema** является перегруженным методом, который предоставляет необязательные параметры для указания возвращаемой коллекции схем и ограниченный объем возвращаемой информации.  
  
 Поставщики данных .NET Framework для OLE DB, ODBC, Oracle и SqlClient предоставляют метод **GetSchemaTable** , возвращающий объект DataTable, описывающий метаданные столбца для **DataReader**.  
  
 Поставщик данных .NET Framework для OLE DB также предоставляет данные схемы с помощью метода <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> объекта <xref:System.Data.OleDb.OleDbConnection>. В качестве аргументов **жетоледбсчематабле** принимает <xref:System.Data.OleDb.OleDbSchemaGuid> , определяющий возвращаемую информацию о схеме, и массив ограничений на возвращаемые столбцы. **Жетоледбсчематабле** возвращает <xref:System.Data.DataTable> заполненную информацию о запрашиваемой схеме.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Коллекции GetSchema и Schema](getschema-and-schema-collections.md)  
 Описывает метод **GetSchema** и способ его использования для извлечения и ограничения сведений о схеме из базы данных.  
  
 Ограничения схемы  
 Описывает ограничения схемы, которые можно использовать с **GetSchema**.  
  
 [Общие коллекции схемы](common-schema-collections.md)  
 Описывает стандартные коллекции схем, поддерживаемые всеми управляемыми поставщиками .NET Framework.  
  
 [Коллекции схемы SQL Server](sql-server-schema-collections.md)  
 Описывается коллекция схем, поддерживаемая поставщиком .NET Framework для SQL Server.  
  
 [Коллекции схемы Oracle](oracle-schema-collections.md)  
 Описывается коллекция схем, поддерживаемая поставщиком .NET Framework для Oracle.  
  
 [Коллекции схемы ODBC](odbc-schema-collections.md)  
 Описываются коллекции схем для драйверов ODBC.  
  
 [Коллекции схемы OLE DB](ole-db-schema-collections.md)  
 Описываются коллекции схем для поставщиков OLE DB.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 Описывает <xref:System.Data.Common.DbConnection> метод **GetSchema** класса.  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 Описывает <xref:System.Data.Odbc.OdbcConnection> метод **GetSchema** класса.  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 Описывает <xref:System.Data.OleDb.OleDbConnection> метод **GetSchema** класса.  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 Описывает <xref:System.Data.OracleClient.OracleConnection> метод **GetSchema** класса.  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 Описывает <xref:System.Data.SqlClient.SqlConnection> метод **GetSchema** класса.  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 Описывает <xref:System.Data.Common.DbDataReader> метод **GetSchemaTable** класса.  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 Описывает <xref:System.Data.Odbc.OdbcDataReader> метод **GetSchemaTable** класса.  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 Описывает <xref:System.Data.OleDb.OleDbDataReader> метод **GetSchemaTable** класса.  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 Описывает <xref:System.Data.OracleClient.OracleDataReader> метод **GetSchemaTable** класса.  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 Описывает <xref:System.Data.SqlClient.SqlDataReader> метод **GetSchemaTable** класса.  
  
## <a name="see-also"></a>См. также

- [Извлечение и изменение данных в ADO.NET](retrieving-and-modifying-data.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
