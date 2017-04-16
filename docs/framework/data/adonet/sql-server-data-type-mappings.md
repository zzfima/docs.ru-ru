---
title: "Сопоставления типов данных SQL Server | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fafdc31a-f435-4cd3-883f-1dfadd971277
caps.latest.revision: 8
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 8
---
# Сопоставления типов данных SQL Server
В SQL Server и .NET Framework используются различные системы типов.  Например, максимальная разрядность структуры .NET Framework <xref:System.Decimal> составляет 28, в то время как максимальная разрядность десятичных и числовых типов данных SQL Server \- 38.  Чтобы обеспечить целостность данных при чтении и записи, объект <xref:System.Data.SqlClient.SqlDataReader> предоставляет характерные для SQL Server типизированные методы доступа, возвращающие объекты <xref:System.Data.SqlTypes>, а также методы доступа, возвращающие типы .NET Framework.  Типы данных SQL Server и .NET Framework также представлены перечислениями в классах <xref:System.Data.DbType> и <xref:System.Data.SqlDbType>, которые можно использовать при указании типов данных <xref:System.Data.SqlClient.SqlParameter>.  
  
 В приведенной ниже таблице показан выводимый тип [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], перечисления <xref:System.Data.DbType> и <xref:System.Data.SqlDbType>, а также методы доступа для класса <xref:System.Data.SqlClient.SqlDataReader>.  
  
|Тип ядра СУБД SQL Server|Тип платформы .NET Framework|Перечисление SqlDbType|Типизированный метод доступа SqlDataReader SqlTypes|Перечисление DbType|Типизированный метод доступа SqlDataReader DbType|  
|------------------------------|----------------------------------|----------------------------|---------------------------------------------------------|-------------------------|-------------------------------------------------------|  
|bigint|Int64|<xref:System.Data.SqlDbType>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlInt64%2A>|<xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetInt64%2A>|  
|двоичные|Byte\[\]|<xref:System.Data.SqlDbType>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlBinary%2A>|<xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetBytes%2A>|  
|bit|Boolean|<xref:System.Data.SqlDbType>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlBoolean%2A>|<xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetBoolean%2A>|  
|char|Строковое<br /><br /> Char\[\]|<xref:System.Data.SqlDbType>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlString%2A>|<xref:System.Data.DbType>,<br /><br /> <xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetString%2A><br /><br /> <xref:System.Data.SqlClient.SqlDataReader.GetChars%2A>|  
|date<br /><br /> \(SQL Server 2008 и более поздние версии\)|DateTime|<xref:System.Data.SqlDbType>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlDateTime%2A>|<xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetDateTime%2A>|  
|datetime|DateTime|<xref:System.Data.SqlDbType>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlDateTime%2A>|<xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetDateTime%2A>|  
|datetime2<br /><br /> \(SQL Server 2008 и более поздние версии\)|DateTime|<xref:System.Data.SqlDbType>|Нет|<xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetDateTime%2A>|  
|datetimeoffset<br /><br /> \(SQL Server 2008 и более поздние версии\)|DateTimeOffset|<xref:System.Data.SqlDbType>|Нет|<xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetDateTimeOffset%2A>|  
|decimal|Десятичное число|<xref:System.Data.SqlDbType>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlDecimal%2A>|<xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetDecimal%2A>|  
|Атрибут FILESTREAM \(varbinary\(max\)\)|Byte\[\]|<xref:System.Data.SqlDbType>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlBytes%2A>|<xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetBytes%2A>|  
|float|Double|<xref:System.Data.SqlDbType>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlDouble%2A>|<xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetDouble%2A>|  
|изображение|Byte\[\]|<xref:System.Data.SqlDbType>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlBinary%2A>|<xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetBytes%2A>|  
|int|Int32|<xref:System.Data.SqlDbType>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlInt32%2A>|<xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetInt32%2A>|  
|money|Десятичное число|<xref:System.Data.SqlDbType>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlMoney%2A>|<xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetDecimal%2A>|  
|nchar|Строковое<br /><br /> Char\[\]|<xref:System.Data.SqlDbType>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlString%2A>|<xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetString%2A><br /><br /> <xref:System.Data.SqlClient.SqlDataReader.GetChars%2A>|  
|ntext|Строковое<br /><br /> Char\[\]|<xref:System.Data.SqlDbType>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlString%2A>|<xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetString%2A><br /><br /> <xref:System.Data.SqlClient.SqlDataReader.GetChars%2A>|  
|числовой|Десятичное число|<xref:System.Data.SqlDbType>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlDecimal%2A>|<xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetDecimal%2A>|  
|nvarchar|Строковое<br /><br /> Char\[\]|<xref:System.Data.SqlDbType>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlString%2A>|<xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetString%2A><br /><br /> <xref:System.Data.SqlClient.SqlDataReader.GetChars%2A>|  
|действительные|Single|<xref:System.Data.SqlDbType>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlSingle%2A>|<xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetFloat%2A>|  
|rowversion|Byte\[\]|<xref:System.Data.SqlDbType>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlBinary%2A>|<xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetBytes%2A>|  
|smalldatetime|DateTime|<xref:System.Data.SqlDbType>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlDateTime%2A>|<xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetDateTime%2A>|  
|smallint|Int16|<xref:System.Data.SqlDbType>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlInt16%2A>|<xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetInt16%2A>|  
|smallmoney|Десятичное число|<xref:System.Data.SqlDbType>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlMoney%2A>|<xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetDecimal%2A>|  
|sql\_variant|Object\*|<xref:System.Data.SqlDbType>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A> \*|<xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetValue%2A> \*|  
|текст|Строковое<br /><br /> Char\[\]|<xref:System.Data.SqlDbType>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlString%2A>|<xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetString%2A><br /><br /> <xref:System.Data.SqlClient.SqlDataReader.GetChars%2A>|  
|время<br /><br /> \(SQL Server 2008 и более поздние версии\)|TimeSpan|<xref:System.Data.SqlDbType>|Нет|<xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetDateTime%2A>|  
|отметка времени|Byte\[\]|<xref:System.Data.SqlDbType>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlBinary%2A>|<xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetBytes%2A>|  
|tinyint|Byte|<xref:System.Data.SqlDbType>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlByte%2A>|<xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetByte%2A>|  
|uniqueidentifier|Guid|<xref:System.Data.SqlDbType>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlGuid%2A>|<xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetGuid%2A>|  
|varbinary|Byte\[\]|<xref:System.Data.SqlDbType>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlBinary%2A>|<xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetBytes%2A>|  
|varchar|Строковое<br /><br /> Char\[\]|<xref:System.Data.SqlDbType>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlString%2A>|<xref:System.Data.DbType>, <xref:System.Data.DbType>|<xref:System.Data.SqlClient.SqlDataReader.GetString%2A><br /><br /> <xref:System.Data.SqlClient.SqlDataReader.GetChars%2A>|  
|xml|Xml|<xref:System.Data.SqlDbType>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A>|<xref:System.Data.DbType>|Нет|  
  
 \* Если известен базовый тип `sql_variant`, используйте конкретный типизированный метод доступа.  
  
## [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] Ссылка на раздел электронной документации  
 Дополнительные сведения о типах данных [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] см. в разделе [Типы данных \(ядро СУБД\)](http://go.microsoft.com/fwlink/?LinkID=107468).  
  
## См. также  
 [Типы данных SQL Server и ADO.NET](../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)   
 [Двоичные данные и данные большого размера SQL Server](../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)   
 [Сопоставления типов данных в ADO.NET](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)   
 [Настройка параметров и типы данных параметров](../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)