---
title: Настройка параметров и типы данных параметров
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 537d8a2c-d40b-4000-83eb-bc1fcc93f707
ms.openlocfilehash: e4414e33efb077e00e4b38e3e53d218ecd7343a7
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53242052"
---
# <a name="configuring-parameters-and-parameter-data-types"></a>Настройка параметров и типы данных параметров

Объекты команды используют параметры для передачи значений в выражения SQL или хранимые процедуры, обеспечивая проверку типов и правильности. В отличие от текста команд, входные параметры обрабатываются как буквенные значения, а не как исполняемый код. Это помогает защищаться от атак путем внедрения кода SQL, при которых злоумышленник вставляет в инструкцию SQL команду, ставящую под угрозу безопасность сервера.

Параметризованные команды также позволяют повысить производительность при выполнении запроса, поскольку при их использовании сервер баз данных может точно сопоставить входящей команде правильный кэшированных план запроса. Дополнительные сведения см. в разделе [кэширование и плана выполнения повторного использования](/sql/relational-databases/query-processing-architecture-guide#execution-plan-caching-and-reuse) и [параметры и повторное использование планов выполнения](/sql/relational-databases/query-processing-architecture-guide#PlanReuse). Помимо повышения безопасности и производительности параметризованные команды обеспечивают удобный метод организации значений, передающихся в источник данных.

Объект <xref:System.Data.Common.DbParameter> можно создать при помощи конструктора или путем добавления его в коллекцию <xref:System.Data.Common.DbCommand.DbParameterCollection%2A> с помощью метода `Add` коллекции <xref:System.Data.Common.DbParameterCollection> . Метод `Add` принимает в качестве входных данных либо аргументы конструктора, либо существующий объект параметра - в зависимости от поставщика данных.

## <a name="supplying-the-parameterdirection-property"></a>Указание свойства ParameterDirection

При добавлении параметров необходимо указать свойство <xref:System.Data.ParameterDirection> для параметров, не являющихся входными. В следующей таблице показаны значения `ParameterDirection` , которые можно использовать с перечислением <xref:System.Data.ParameterDirection> .

|Имя члена|Описание|
|-----------------|-----------------|
|<xref:System.Data.ParameterDirection.Input>|Параметр является входным. Это значение по умолчанию.|
|<xref:System.Data.ParameterDirection.InputOutput>|Параметр можно использовать как для ввода, так и для вывода.|
|<xref:System.Data.ParameterDirection.Output>|Параметр является выходным.|
|<xref:System.Data.ParameterDirection.ReturnValue>|Параметр представляет значение, возвращаемое как результат операции, например хранимой процедуры, встроенной функции или определяемой пользователем функции.|

## <a name="working-with-parameter-placeholders"></a>Работа с местозаполнителями параметров

Синтаксис местозаполнителей параметров зависит от источника данных. Для поставщиков данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] используются разные способы задания имен и указания параметров и их местозаполнителей. Синтаксис зависит от конкретного источника данных, как описано в следующей таблице.

|Поставщик данных|Синтаксис именования параметров|
|-------------------|-----------------------------|
|<xref:System.Data.SqlClient>|Использует именованные параметры в формате `@`*имяпараметра*.|
|<xref:System.Data.OleDb>|Использует маркеры позиционных параметров, указываемые знаком вопроса (`?`).|
|<xref:System.Data.Odbc>|Использует маркеры позиционных параметров, указываемые знаком вопроса (`?`).|
|<xref:System.Data.OracleClient>|Использует именованные параметры в формате `:`*имяпараметра* (или *имяпараметра*).|

## <a name="specifying-parameter-data-types"></a>Указание типов данных параметров

Тип данных параметра зависит от поставщика данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] . При указании типа значение `Parameter` преобразуется в тип поставщика данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] до передачи значения в источник данных. Можно также указать тип `Parameter` универсальным способом, задав свойству `DbType` объекта `Parameter` определенное значение <xref:System.Data.DbType>.

Тип поставщика данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] объекта `Parameter` выводится из типа [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] значения `Value` объекта `Parameter` или из `DbType` объекта `Parameter` . Следующая таблица показывает тип `Parameter` , выводимый из объекта, переданного как значение `Parameter` , или указанного значения `DbType`.

|Тип платформы .NET Framework|DbType|SqlDbType|OleDbType|OdbcType|OracleType|
|-------------------------|------------|---------------|---------------|--------------|----------------|
|<xref:System.Boolean>|Boolean|Разряд|Boolean|Разряд|Byte|
|<xref:System.Byte>|Byte|TinyInt|UnsignedTinyInt|TinyInt|Byte|
|byte[]|Binary|VarBinary. Это неявное преобразование завершится ошибкой, если массив байтов больше, чем максимальный размер VarBinary, который является более 8000 байт. Для массивов байтов, превышающих 8000 байт, необходимо явно указать <xref:System.Data.SqlDbType>.|VarBinary|Binary|Raw|
|<xref:System.Char>| |Вывод типа <xref:System.Data.SqlDbType> из типа char не поддерживается.|Char|Char|Byte|
|<xref:System.DateTime>|DateTime|DateTime|DBTimeStamp|DateTime|DateTime|
|<xref:System.DateTimeOffset>|DateTimeOffset|Тип DateTimeOffset в SQL Server 2008. Вывод типа <xref:System.Data.SqlDbType> из типа DateTimeOffset не поддерживается в версиях SQL Server до SQL Server 2008.|||DateTime|
|<xref:System.Decimal>|Десятичное число|Десятичное число|Десятичное число|Numeric|Числовой|
|<xref:System.Double>|Double|Float|Double|Double|Double|
|<xref:System.Single>|Single|Real|Single|Real|Float|
|<xref:System.Guid>|Guid|UniqueIdentifier|Guid|UniqueIdentifier|Raw|
|<xref:System.Int16>|Int16|SmallInt|SmallInt|SmallInt|Int16|
|<xref:System.Int32>|Int32|Int|Int|Int|Int32|
|<xref:System.Int64>|Int64|BigInt|BigInt|BigInt|Числовой|
|<xref:System.Object>|Объект|Вариант|Вариант|Вывод типа OdbcType из типа Object не поддерживается.|Blob|
|<xref:System.String>|Строковое|NVarChar. Это неявное преобразование завершится ошибкой, если строка превышает максимальный размер для типа NVarChar (4000 символов). Для строк длиннее 4000 символов явно установите значение <xref:System.Data.SqlDbType>.|VarWChar|NVarChar|NVarChar|
|<xref:System.TimeSpan>|Время|Тип Time в SQL Server 2008. Вывод типа <xref:System.Data.SqlDbType> из типа TimeSpan не поддерживается в версиях SQL Server до SQL Server 2008.|DBTime|Время|DateTime|
|<xref:System.UInt16>|UInt16|Вывод типа <xref:System.Data.SqlDbType> из типа UInt16 не поддерживается.|UnsignedSmallInt|Int|UInt16|
|<xref:System.UInt32>|UInt32|Вывод типа <xref:System.Data.SqlDbType> из типа UInt32 не поддерживается.|UnsignedInt|BigInt|UInt32|
|<xref:System.UInt64>|UInt64|Вывод типа <xref:System.Data.SqlDbType> из типа UInt64 не поддерживается.|UnsignedBigInt|Numeric|Числовой|
||AnsiString|VarChar|VarChar|VarChar|VarChar|
||AnsiStringFixedLength|Char|Char|Char|Char|
||Валюта|Money|Валюта|Вывод типа `OdbcType` из типа `Currency` не поддерживается.|Числовой|
||Дата|Тип Date в SQL Server 2008. Вывод типа <xref:System.Data.SqlDbType> из типа Date не поддерживается в версиях SQL Server до SQL Server 2008.|DBDate|дата.|DateTime|
||SByte|Вывод типа <xref:System.Data.SqlDbType> из типа SByte не поддерживается.|TinyInt|Вывод типа `OdbcType` из типа SByte не поддерживается.|SByte|
||StringFixedLength|NChar|WChar|NChar|NChar|
||Время|Тип Time в SQL Server 2008. Вывод типа <xref:System.Data.SqlDbType> из типа Time не поддерживается в версиях SQL Server до SQL Server 2008.|DBTime|Время|DateTime|
||VarNumeric|Вывод типа <xref:System.Data.SqlDbType> из типа VarNumeric не поддерживается.|VarNumeric|Вывод типа `OdbcType` из типа VarNumeric не поддерживается.|Числовой|
|определяемый пользователем тип (объект с <xref:Microsoft.SqlServer.Server.SqlUserDefinedAggregateAttribute>|Объект или строка в зависимости от поставщика (SqlClient всегда возвращает объект, ODBC всегда возвращает строку, а поставщик данных, управляемый OleDb, может вернуть и то и другое).|SqlDbType.Udt, если присутствует <xref:Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute> , в противном случае Variant|OleDbType.VarWChar (при значении NULL), в противном случае OleDbType.Variant.|OdbcType.NVarChar|не поддерживается|

> [!NOTE]
> Преобразования из типа decimal в другие типы являются сужающими. Они округляют десятичное значение до ближайшего целого в направлении нуля. Если результат преобразования нельзя представить в целевом типе, возникает исключение <xref:System.OverflowException> .

> [!NOTE]
> При отправке значения параметра null на сервер, необходимо указать <xref:System.DBNull>, а не `null` (`Nothing` в Visual Basic). В системе значение null - это пустой объект, не имеющий значения. Для представления значений null используется тип<xref:System.DBNull> . Дополнительные сведения о значении NULL базы данных см. в разделе [Handling Null Values](./sql/handling-null-values.md).

## <a name="deriving-parameter-information"></a>Выведение информации о параметрах

Информацию о параметрах можно вывести из хранимой процедуры с помощью класса `DbCommandBuilder` . Оба класса, `SqlCommandBuilder` и `OleDbCommandBuilder` , обеспечивают статический метод `DeriveParameters`, который автоматически заполняет коллекцию параметров объекта команд, использующего информацию о параметрах от хранимой процедуры. Обратите внимание, что метод `DeriveParameters` перезаписывает существующую информацию о параметрах для команды.

> [!NOTE]
> Выведение информации о параметрах снижает производительность, так как для этого требуется дополнительный обмен данных с источником данных. Если информация о параметрах известна во время разработки, можно увеличить производительность приложения, задав параметры явным образом.

Дополнительные сведения см. в разделе [создание команд с помощью построителей CommandBuilder](generating-commands-with-commandbuilders.md).

## <a name="using-parameters-with-a-sqlcommand-and-a-stored-procedure"></a>Использование параметров с объектом SqlCommand и хранимой процедуры

Хранимые процедуры дают множество преимуществ в приложениях, управляемых данными. С помощью хранимых процедур операции с базой данных можно инкапсулировать в одну команду, оптимизированную для производительности и обладающую повышенной безопасностью. Хотя хранимые процедуры можно вызывать и с помощью инструкции SQL, указывая в ней имя процедуры и ее аргументы, использование коллекции <xref:System.Data.Common.DbCommand.Parameters%2A> объекта [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] в <xref:System.Data.Common.DbCommand> позволяет более явно задать параметры процедуры, а также обращаться к выходным параметрам и возвращаемым значениям.

> [!NOTE]
> Параметризованные инструкции выполняются на сервере с помощью хранимой процедуры `sp_executesql,` которая позволяет повторно использовать планы запросов. Локальные курсоры или переменные в пакете `sp_executesql` недоступны пакету, вызвавшему `sp_executesql`. Изменения в контексте базы данных длятся только до завершения выполнения инструкции `sp_executesql` . Дополнительные сведения см. в разделе [sp_executesql (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-executesql-transact-sql).

Если параметры используются с объектом <xref:System.Data.SqlClient.SqlCommand> для выполнения хранимой процедуры SQL Server, то имена параметров, добавляемых в коллекцию <xref:System.Data.SqlClient.SqlCommand.Parameters%2A> , должны соответствовать именам маркеров параметров в хранимой процедуре. Поставщик данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для SQL Server не поддерживает местозаполнитель (?) для передачи параметров в инструкции SQL и хранимые процедуры. Он обрабатывает параметры в хранимой процедуре как именованные параметры и ищет соответствующие маркеры параметров. Например, хранимая процедура `CustOrderHist` определяется с использованием параметра `@CustomerID`. Когда программа выполняет эта хранимую процедуру, она также должна использовать параметр `@CustomerID`.

```sql
CREATE PROCEDURE dbo.CustOrderHist @CustomerID varchar(5)
```

### <a name="example"></a>Пример

Этот пример показывает, как вызвать хранимую процедуру SQL Server в образце базы данных `Northwind` . Имя хранимой процедуры – `dbo.SalesByCategory` . Она имеет входной параметр `@CategoryName` с типом данных `nvarchar(15)`. Код создает создает новый объект класса <xref:System.Data.SqlClient.SqlConnection> в блоке Using, чтобы в конце процедуры соединение удалялось. Создаются объекты <xref:System.Data.SqlClient.SqlCommand> и <xref:System.Data.SqlClient.SqlParameter> устанавливаются их свойства. Объект класса <xref:System.Data.SqlClient.SqlDataReader> выполняет `SqlCommand` и возвращает результирующий набор из хранимой процедуры, отображая выходные данные в окне консоли.

> [!NOTE]
> Вместо того, чтобы создавать объекты `SqlCommand` и `SqlParameter` и затем задавать их свойства в отдельных инструкциях, можно использовать один из перегруженных конструкторов и задать свойства в одной инструкции.

[!code-csharp[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/CS/source.cs#1)]
[!code-vb[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/VB/source.vb#1)]

## <a name="using-parameters-with-an-oledbcommand-or-odbccommand"></a>Использование параметров с OleDbCommand или OdbcCommand

Если с объектами <xref:System.Data.OleDb.OleDbCommand> или <xref:System.Data.Odbc.OdbcCommand>используются параметры, порядок параметров, добавляемых в коллекцию `Parameters` , должен соответствовать порядку параметров, заданных в хранимой процедуре. Поставщик данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для OLE DB и поставщик данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для ODBC обрабатывают параметры в хранимой процедуре как местозаполнители и применяют значения параметров в правильном порядке. Кроме того, параметры возвращаемых значений должны быть первыми параметрами, добавляемыми в коллекцию `Parameters` .

Поставщик данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для OLE DB и поставщик данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для ODBC не поддерживают именованные параметры для передачи параметров в инструкции SQL и хранимые процедуры. В этом случае необходимо использовать местозаполнитель (?), как в следующем примере.

```sql
SELECT * FROM Customers WHERE CustomerID = ?
```

В результате порядок добавления объектов `Parameter` в коллекцию `Parameters` должен строго соответствовать позиции местозаполнителя параметра (?).

### <a name="oledb-example"></a>Пример OleDb

```vb
Dim command As OleDbCommand = New OleDbCommand( _
  "SampleProc", connection)
command.CommandType = CommandType.StoredProcedure

Dim parameter As OleDbParameter = command.Parameters.Add( _
  "RETURN_VALUE", OleDbType.Integer)
parameter.Direction = ParameterDirection.ReturnValue

parameter = command.Parameters.Add( _
  "@InputParm", OleDbType.VarChar, 12)
parameter.Value = "Sample Value"

parameter = command.Parameters.Add( _
  "@OutputParm", OleDbType.VarChar, 28)
parameter.Direction = ParameterDirection.Output
```

```csharp
OleDbCommand command = new OleDbCommand("SampleProc", connection);
command.CommandType = CommandType.StoredProcedure;

OleDbParameter parameter = command.Parameters.Add(
  "RETURN_VALUE", OleDbType.Integer);
parameter.Direction = ParameterDirection.ReturnValue;

parameter = command.Parameters.Add(
  "@InputParm", OleDbType.VarChar, 12);
parameter.Value = "Sample Value";

parameter = command.Parameters.Add(
  "@OutputParm", OleDbType.VarChar, 28);
parameter.Direction = ParameterDirection.Output;
```

## <a name="odbc-example"></a>Пример Odbc

```vb
Dim command As OdbcCommand = New OdbcCommand( _
  "{ ? = CALL SampleProc(?, ?) }", connection)
command.CommandType = CommandType.StoredProcedure

Dim parameter As OdbcParameter = command.Parameters.Add("RETURN_VALUE", OdbcType.Int)
parameter.Direction = ParameterDirection.ReturnValue

parameter = command.Parameters.Add( _
  "@InputParm", OdbcType.VarChar, 12)
parameter.Value = "Sample Value"

parameter = command.Parameters.Add( _
  "@OutputParm", OdbcType.VarChar, 28)
parameter.Direction = ParameterDirection.Output
```

```csharp
OdbcCommand command = new OdbcCommand( _
  "{ ? = CALL SampleProc(?, ?) }", connection);
command.CommandType = CommandType.StoredProcedure;

OdbcParameter parameter = command.Parameters.Add( _
  "RETURN_VALUE", OdbcType.Int);
parameter.Direction = ParameterDirection.ReturnValue;

parameter = command.Parameters.Add( _
  "@InputParm", OdbcType.VarChar, 12);
parameter.Value = "Sample Value";

parameter = command.Parameters.Add( _
  "@OutputParm", OdbcType.VarChar, 28);
parameter.Direction = ParameterDirection.Output;
```

## <a name="see-also"></a>См. также

- [Команды и параметры](commands-and-parameters.md)
- [Параметры DataAdapter](dataadapter-parameters.md)
- [Сопоставления типов данных в ADO.NET](data-type-mappings-in-ado-net.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
