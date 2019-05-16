---
title: Извлечение идентификации или значений автонумерации
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d6b7f9cb-81be-44e1-bb94-56137954876d
ms.openlocfilehash: ef4831af0b7bafed7d40bd86d2684c73d84a0f93
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634160"
---
# <a name="retrieving-identity-or-autonumber-values"></a>Извлечение идентификации или значений автонумерации

Первичным ключом в реляционной базе данных является столбец или сочетание столбцов, которые всегда содержат уникальные значения. Если известно значение первичного ключа, то можно найти строку, которая содержит это значение. Такие СУРБД, как SQL Server, Oracle и Microsoft Access/Jet, поддерживают создание столбцов с автоматически увеличивающимися значениями, которые могут назначаться в качестве первичных ключей. Эти значения формируются сервером по мере добавления строк в таблицу. В SQL Server задается свойство идентификатора столбца, в Oracle создается последовательность Sequence, а в Microsoft Access создается столбец AutoNumber.

Для формирования автоматически увеличивающихся значений также можно использовать объект <xref:System.Data.DataColumn>, присвоив его свойству <xref:System.Data.DataColumn.AutoIncrement%2A> значение true. Но это может привести к появлению повторяющихся значений в отдельных экземплярах <xref:System.Data.DataTable>, если в нескольких клиентских приложениях будут независимо формироваться автоматически увеличивающиеся значения. Применение сервера для формирования автоматически увеличивающихся значений позволяет устранить потенциальные конфликты, поскольку каждый пользователь может получать создаваемые сервером значения для каждой вставляемой строки.

Во время вызова метода `Update` объекта `DataAdapter` база данных может отправлять данные обратно в приложение ADO.NET в качестве выходных параметров или в виде первой возвращенной записи результирующего набора инструкции SELECT, выполняемой в том же пакете, что и инструкция INSERT. Среда ADO.NET позволяет получать эти значения и обновлять соответствующие столбцы в обновляемом объекте <xref:System.Data.DataRow>.

Некоторые СУБД, такие как Microsoft Access Jet, не поддерживают выходные параметры и не могут обрабатывать несколько инструкций в одном пакете. Работая с ядром базы данных Jet, новое значение AutoNumber, создаваемое для вставленной строки, можно получить, выполнив отдельную команду SELECT в обработчике событий `RowUpdated` объекта `DataAdapter`.

> [!NOTE]
> Подход, альтернативный по отношению к использованию автоматически увеличивающегося значения, состоит в применении метода <xref:System.Guid.NewGuid%2A> объекта <xref:System.Guid> для формирования идентификатора GUID (глобально уникального идентификатора) на клиентском компьютере, который может копироваться на сервер при вставке каждой новой строки. Метод `NewGuid` формирует 16-байтовое двоичное значение с помощью алгоритма, который обеспечивает высокую вероятность того, что ни одно из полученных значений не будет повторяться. В базе данных SQL Server идентификатор GUID хранится в столбце `uniqueidentifier`, который может автоматически создаваться в SQL Server с помощью функции `NEWID()` языка Transact-SQL. Использование идентификатора GUID в качестве первичного ключа может привести к снижению производительности. SQL Server обеспечивает поддержку `NEWSEQUENTIALID()` функцию, которая создает последовательные значения идентификатора GUID, глобальная уникальность не гарантируется, но которые могут быть более эффективно индексировать.

## <a name="retrieving-sql-server-identity-column-values"></a>Получение значений столбца идентификатора в базе данных SQL Server

При работе с Microsoft SQL Server можно создать хранимую процедуру с выходным параметром, возвращающим значение идентификатора для вставленной строки. В следующей таблице описаны три функции Transact-SQL, применимые в SQL Server, с помощью которых можно извлекать значения столбцов идентификаторов.

|Функция|Описание|
|--------------|-----------------|
|SCOPE_IDENTITY|Возвращает последнее значение идентификатора в текущей области выполнения. В большинстве случаев рекомендуется использовать SCOPE_IDENTITY.|
|@@IDENTITY|Содержит последнее значение идентификатора, сформированного в любой таблице в текущем сеансе. @@IDENTITY может зависеть от триггеров и могут не возвращать значение идентификатора, который предполагается.|
|IDENT_CURRENT|Возвращает последнее значение идентификатора, сформированное для указанной таблицы в любом сеансе и любой области.|

 Следующая хранимая процедура демонстрирует, как вставить строку в **категории** таблице и использовать выходной параметр для возврата нового значения идентификатора, созданные этой функцией SCOPE_IDENTITY() языка Transact-SQL.

```sql
CREATE PROCEDURE dbo.InsertCategory
  @CategoryName nvarchar(15),
  @Identity int OUT
AS
INSERT INTO Categories (CategoryName) VALUES(@CategoryName)
SET @Identity = SCOPE_IDENTITY()
```

После этого данную хранимую процедуру можно указать в качестве источника <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> объекта <xref:System.Data.SqlClient.SqlDataAdapter>. Свойство <xref:System.Data.SqlClient.SqlCommand.CommandType%2A> объекта <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> должно иметь значение <xref:System.Data.CommandType.StoredProcedure>. Получение выходного значения идентификатора осуществляется путем создания объекта <xref:System.Data.SqlClient.SqlParameter>, который имеет свойство <xref:System.Data.ParameterDirection> со значением <xref:System.Data.ParameterDirection.Output>. При `InsertCommand` — обработано, автоматически увеличивающееся значение идентификатора возвращается и помещаются в **CategoryID** столбца текущей строки, если задать <xref:System.Data.SqlClient.SqlCommand.UpdatedRowSource%2A> свойство команды вставки имеет значение `UpdateRowSource.OutputParameters` или `UpdateRowSource.Both`.

Если в команде вставки выполняется пакет, который включает и инструкцию INSERT, и инструкцию SELECT, возвращающую новое значение идентификатора, то это новое значение можно получить, задав свойство `UpdatedRowSource` команды вставки, равное `UpdateRowSource.FirstReturnedRecord`.

[!code-csharp[DataWorks SqlClient.RetrieveIdentityStoredProcedure#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.RetrieveIdentityStoredProcedure/CS/source.cs#1)]
[!code-vb[DataWorks SqlClient.RetrieveIdentityStoredProcedure#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.RetrieveIdentityStoredProcedure/VB/source.vb#1)]

## <a name="merging-new-identity-values"></a>Слияние новых значений идентификаторов

Распространенный сценарий состоит в вызове метода `GetChanges` объекта `DataTable` для создания копии, которая содержит только изменившиеся строки, после чего эта новая копия используется при вызове метода `Update` объекта `DataAdapter`. Это особенно удобно, если требуется маршалировать и передать изменившиеся строки для отдельного компонента, который выполняет обновление. После обновления эта копия может содержать новые значения идентификаторов, которые затем должны быть переданы обратно в оригинал `DataTable` для слияния. Причем новые значения идентификаторов, по всей вероятности, будут отличаться от исходных значений в `DataTable`. Чтобы выполнить это слияние, исходные значения **AutoIncrement** столбцы в копии должны сохраняться, чтобы иметь возможность находить и обновлять существующие строки в исходном `DataTable`, вместо того чтобы добавлять новые строки, содержащие новые значения идентификаторов. Однако по умолчанию эти первоначальные значения теряются после вызова метода `Update` объекта `DataAdapter`, поскольку для каждой обновляемой строки `AcceptChanges` неявно вызывается метод `DataRow`.

Существует два способа сохранения первоначальных значений `DataColumn` в объекте `DataRow` во время обновления `DataAdapter`.

- Первый способ сохранения первоначальных значений состоит в присвоении свойству `AcceptChangesDuringUpdate` объекта `DataAdapter` значения `false`. Это влияет на каждый объект `DataRow` в обновляемом объекте `DataTable`. Дополнительные сведения и пример кода см. в разделе <xref:System.Data.Common.DataAdapter.AcceptChangesDuringUpdate%2A>.

- Второй способ предусматривает применение в обработчике событий `RowUpdated` объекта `DataAdapter` кода, в котором свойству <xref:System.Data.Common.RowUpdatedEventArgs.Status%2A> присваивается значение <xref:System.Data.UpdateStatus.SkipCurrentRow>. Значение `DataRow` обновляется, но первоначальное значение каждого объекта `DataColumn` сохраняется. Этот способ позволяет сохранять первоначальные значения одних строк, но не других. Например, в коде можно сохранить первоначальные значения добавляемых строк, а не изменяемых или удаляемых строк путем проверки значения <xref:System.Data.Common.RowUpdatedEventArgs.StatementType%2A> с последующим присваиванием свойству <xref:System.Data.Common.RowUpdatedEventArgs.Status%2A> значения <xref:System.Data.UpdateStatus.SkipCurrentRow> только для строк со свойством `StatementType` равным `Insert`.

Если любой из этих способов используется для сохранения первоначальных значений в объекте `DataRow` во время обновления `DataAdapter`, то в приложении ADO.NET выполняется ряд действий по замене текущих значений `DataRow` на новые значения, возвращаемые в качестве выходных параметров или в виде первой возвращаемой строки результирующего набора, с сохранением первоначального значения в каждом `DataColumn`. Сначала вызывается метод `AcceptChanges` объекта `DataRow` для сохранения текущих значений в качестве первоначальных значений, а затем присваиваются новые значения. После этого у объектов `DataRows`, у которых свойство <xref:System.Data.DataRow.RowState%2A> равно <xref:System.Data.DataRowState.Added>, значение этого свойства `RowState` заменяется на <xref:System.Data.DataRowState.Modified>, что может не соответствовать ожиданиям.

Способ применения результатов команды к каждому обновляемому объекту <xref:System.Data.DataRow> определяется свойством <xref:System.Data.Common.DbCommand.UpdatedRowSource%2A> каждой команды <xref:System.Data.Common.DbCommand>. Это свойство задается равным одному из значений из перечисления `UpdateRowSource`.

В следующей таблице приведено описание того, как значения перечисления `UpdateRowSource` влияют на свойство <xref:System.Data.DataRow.RowState%2A> обновленных строк.

|Имя члена|Описание|
|-----------------|-----------------|
|<xref:System.Data.UpdateRowSource.Both>|Вызывается метод `AcceptChanges`, после чего значения выходных параметров и (или) значения из первой строки любого возвращенного результирующего набора помещаются в обновляемый объект `DataRow`. Если применимые значения отсутствуют, то `RowState` становится равным <xref:System.Data.DataRowState.Unchanged>.|
|<xref:System.Data.UpdateRowSource.FirstReturnedRecord>|Если возвращена строка, вызывается метод `AcceptChanges`, и эта строка сопоставляется с измененной строкой в `DataTable`, в связи с чем свойству `RowState` присваивается значение `Modified`. Если не возвращена ни одна строка, то метод `AcceptChanges` не вызывается, и `RowState` остается равным `Added`.|
|<xref:System.Data.UpdateRowSource.None>|Любые возвращенные параметры или строки пропускаются. Метод `AcceptChanges` не вызывается, и `RowState` остается равным `Added`.|
|<xref:System.Data.UpdateRowSource.OutputParameters>|Вызывается метод `AcceptChanges`, и все выходные параметры сопоставляются с измененной строкой в `DataTable`, в связи с чем свойству `RowState` присваивается значение `Modified`. Если выходные параметры отсутствуют, то `RowState` становится равным `Unchanged`.|

### <a name="example"></a>Пример

В этом примере демонстрируется извлечение измененных строк из `DataTable` и использование объекта <xref:System.Data.SqlClient.SqlDataAdapter> для обновления источника данных и получения нового значения столбца идентификаторов. В <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> выполняются две инструкции Transact-SQL; первая из них представляет собой инструкцию INSERT, а вторая является инструкцией SELECT, в которой для получения значения идентификатора используется функция SCOPE_IDENTITY.

```sql
INSERT INTO dbo.Shippers (CompanyName)
VALUES (@CompanyName);
SELECT ShipperID, CompanyName FROM dbo.Shippers
WHERE ShipperID = SCOPE_IDENTITY();
```

Свойство `UpdatedRowSource` команды вставки задается равным `UpdateRowSource.FirstReturnedRow`, а свойство <xref:System.Data.MissingSchemaAction> объекта `DataAdapter` задается равным `MissingSchemaAction.AddWithKey`. Объект `DataTable` заполняется, и в коде происходит добавление новой строки к `DataTable`. Затем измененные строки извлекаются в новый объект `DataTable`, передаваемый в `DataAdapter`, с помощью которого после этого происходит обновление на сервере.

[!code-csharp[DataWorks SqlClient.MergeIdentity#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.MergeIdentity/CS/source.cs#1)]
[!code-vb[DataWorks SqlClient.MergeIdentity#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.MergeIdentity/VB/source.vb#1)]

В обработчике событий `OnRowUpdated` проверяется значение <xref:System.Data.Common.RowUpdatedEventArgs.StatementType%2A> свойства <xref:System.Data.SqlClient.SqlRowUpdatedEventArgs>, чтобы определить, была ли вставлена данная строка. Если результат этой проверки является положительным, то свойство <xref:System.Data.Common.RowUpdatedEventArgs.Status%2A> задается равным <xref:System.Data.UpdateStatus.SkipCurrentRow>. Строка обновляется, но первоначальные значения в строке сохраняются. В основной части рассматриваемой процедуры вызывается метод <xref:System.Data.DataSet.Merge%2A> для слияния нового значения идентификатора с оригинальным значением `DataTable`, и в конечном счете вызывается метод `AcceptChanges`.

[!code-csharp[DataWorks SqlClient.MergeIdentity#2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.MergeIdentity/CS/source.cs#2)]
[!code-vb[DataWorks SqlClient.MergeIdentity#2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.MergeIdentity/VB/source.vb#2)]

## <a name="retrieving-microsoft-access-autonumber-values"></a>Получение значений Autonumber в программе Microsoft Access

В этом разделе представлен образец, показывающий, как получить значения `Autonumber` из базы данных Jet 4.0. Ядро базы данных Jet не поддерживает выполнение нескольких инструкций в пакете или использование выходных параметров, поэтому использовать какой-либо из описанных выше методов для возврата нового значения `Autonumber`, присвоенного вставленной строке, нельзя. Тем не менее, можно добавить код для `RowUpdated` обработчик событий, который выполняет отдельные SELECT @@IDENTITY инструкции для получения нового `Autonumber` значение.

### <a name="example"></a>Пример

Вместо добавления сведений о схеме с использованием `MissingSchemaAction.AddWithKey` в этом примере конфигурация `DataTable` настраивается с помощью правильной схемы до вызова <xref:System.Data.OleDb.OleDbDataAdapter> для заполнения `DataTable`. В этом случае **CategoryID** столбце настроено на уменьшение значения в каждой вставляемой строке, начиная с нуля, задав <xref:System.Data.DataColumn.AutoIncrement%2A> для `true`, <xref:System.Data.DataColumn.AutoIncrementSeed%2A> 0, и <xref:System.Data.DataColumn.AutoIncrementStep%2A> значение -1. После этого производится добавление двух новых строк и вызывается метод `GetChanges` для добавления изменившихся строк в новый объект `DataTable`, который передан методу `Update`.

[!code-csharp[DataWorks OleDb.JetAutonumberMerge#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks OleDb.JetAutonumberMerge/CS/source.cs#1)]
[!code-vb[DataWorks OleDb.JetAutonumberMerge#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks OleDb.JetAutonumberMerge/VB/source.vb#1)]

В обработчике событий `RowUpdated` используется то же открытое соединение <xref:System.Data.OleDb.OleDbConnection>, что и в инструкции `Update` объекта `OleDbDataAdapter`. В нем происходит проверка значения `StatementType` свойства <xref:System.Data.OleDb.OleDbRowUpdatedEventArgs> для вставленных строк. Для каждой вставленной строки создается новая <xref:System.Data.OleDb.OleDbCommand> создается для выполнять инструкцию SELECT @@IDENTITY инструкции соединения, возвращающей новое `Autonumber` значение, которое помещается в **CategoryID** столбец `DataRow`. Затем свойству `Status` присваивается значение `UpdateStatus.SkipCurrentRow`, что позволяет блокировать скрытый вызов `AcceptChanges`. В основной части процедуры вызывается метод `Merge` для слияния этих двух объектов `DataTable`, и в конечном счете вызывается `AcceptChanges`.

[!code-csharp[DataWorks OleDb.JetAutonumberMerge#2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks OleDb.JetAutonumberMerge/CS/source.cs#2)]
[!code-vb[DataWorks OleDb.JetAutonumberMerge#2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks OleDb.JetAutonumberMerge/VB/source.vb#2)]

### <a name="retrieving-identity-values"></a>Извлечение значений идентификаторов

Мы часто задаем столбец как идентификатор, когда значения в столбце должны быть уникальными. А иногда нам требуется значение идентификатора для новых данных. В этом примере показано, как извлекать значения идентификаторов:

- Создает хранимую процедуру для вставки данных и возвращения значения идентификатора.

- Выполняет команду для вставки новых данных и отображения результата.

- Использует <xref:System.Data.SqlClient.SqlDataAdapter> для вставки новых данных и отображения результата.

Перед компиляцией и выполнением образца необходимо создать образец базы данных с помощью следующего скрипта:

```sql
USE [master]
GO

CREATE DATABASE [MySchool]
GO

USE [MySchool]
GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE procedure [dbo].[CourseExtInfo] @CourseId int
as
select c.CourseID,c.Title,c.Credits,d.Name as DepartmentName
from Course as c left outer join Department as d on c.DepartmentID=d.DepartmentID
where c.CourseID=@CourseId

GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
create procedure [dbo].[DepartmentInfo] @DepartmentId int,@CourseCount int output
as
select @CourseCount=Count(c.CourseID)
from course as c
where c.DepartmentID=@DepartmentId

select d.DepartmentID,d.Name,d.Budget,d.StartDate,d.Administrator
from Department as d
where d.DepartmentID=@DepartmentId

GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
Create PROCEDURE [dbo].[GetDepartmentsOfSpecifiedYear]
@Year int,@BudgetSum money output
AS
BEGIN
        SELECT @BudgetSum=SUM([Budget])
  FROM [MySchool].[dbo].[Department]
  Where YEAR([StartDate])=@Year

SELECT [DepartmentID]
      ,[Name]
      ,[Budget]
      ,[StartDate]
      ,[Administrator]
  FROM [MySchool].[dbo].[Department]
  Where YEAR([StartDate])=@Year

END
GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE PROCEDURE [dbo].[GradeOfStudent]
-- Add the parameters for the stored procedure here
@CourseTitle nvarchar(100),@FirstName nvarchar(50),
@LastName nvarchar(50),@Grade decimal(3,2) output
AS
BEGIN
select @Grade=Max(Grade)
from [dbo].[StudentGrade] as s join [dbo].[Course] as c on
s.CourseID=c.CourseID join [dbo].[Person] as p on s.StudentID=p.PersonID
where c.Title=@CourseTitle and p.FirstName=@FirstName
and p.LastName= @LastName
END
GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE PROCEDURE [dbo].[InsertPerson]
-- Add the parameters for the stored procedure here
@FirstName nvarchar(50),@LastName nvarchar(50),
@PersonID int output
AS
BEGIN
    insert [dbo].[Person](LastName,FirstName) Values(@LastName,@FirstName)

    set @PersonID=SCOPE_IDENTITY()
END
Go

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Course]([CourseID] [nvarchar](10) NOT NULL,
[Year] [smallint] NOT NULL,
[Title] [nvarchar](100) NOT NULL,
[Credits] [int] NOT NULL,
[DepartmentID] [int] NOT NULL,
 CONSTRAINT [PK_Course] PRIMARY KEY CLUSTERED
(
[CourseID] ASC,
[Year] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]

GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Department]([DepartmentID] [int] IDENTITY(1,1) NOT NULL,
[Name] [nvarchar](50) NOT NULL,
[Budget] [money] NOT NULL,
[StartDate] [datetime] NOT NULL,
[Administrator] [int] NULL,
 CONSTRAINT [PK_Department] PRIMARY KEY CLUSTERED
(
[DepartmentID] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]

GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
SET ANSI_PADDING ON
GO
CREATE TABLE [dbo].[Person]([PersonID] [int] IDENTITY(1,1) NOT NULL,
[LastName] [nvarchar](50) NOT NULL,
[FirstName] [nvarchar](50) NOT NULL,
[HireDate] [datetime] NULL,
[EnrollmentDate] [datetime] NULL,
[Picture] [varbinary](max) NULL,
 CONSTRAINT [PK_School.Student] PRIMARY KEY CLUSTERED
(
[PersonID] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY] TEXTIMAGE_ON [PRIMARY]

GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[StudentGrade]([EnrollmentID] [int] IDENTITY(1,1) NOT NULL,
[CourseID] [nvarchar](10) NOT NULL,
[StudentID] [int] NOT NULL,
[Grade] [decimal](3, 2) NOT NULL,
 CONSTRAINT [PK_StudentGrade] PRIMARY KEY CLUSTERED
(
[EnrollmentID] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]

GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
create view [dbo].[EnglishCourse]
as
select c.CourseID,c.Title,c.Credits,c.DepartmentID
from Course as c join Department as d on c.DepartmentID=d.DepartmentID
where d.Name=N'English'

GO
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C1045', 2012, N'Calculus', 4, 7)
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C1061', 2012, N'Physics', 4, 1)
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C2021', 2012, N'Composition', 3, 2)
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C2042', 2012, N'Literature', 4, 2)
SET IDENTITY_INSERT [dbo].[Department] ON

INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (1, N'Engineering', 350000.0000, CAST(0x0000999C00000000 AS DateTime), 2)
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (2, N'English', 120000.0000, CAST(0x0000999C00000000 AS DateTime), 6)
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (4, N'Economics', 200000.0000, CAST(0x0000999C00000000 AS DateTime), 4)
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (7, N'Mathematics', 250024.0000, CAST(0x0000999C00000000 AS DateTime), 3)
SET IDENTITY_INSERT [dbo].[Department] OFF
SET IDENTITY_INSERT [dbo].[Person] ON

INSERT [dbo].[Person] ([PersonID], [LastName], [FirstName], [HireDate], [EnrollmentDate]) VALUES (1, N'Hu', N'Nan', NULL, CAST(0x0000A0BF00000000 AS DateTime))
INSERT [dbo].[Person] ([PersonID], [LastName], [FirstName], [HireDate], [EnrollmentDate]) VALUES (2, N'Norman', N'Laura', NULL, CAST(0x0000A0BF00000000 AS DateTime))
INSERT [dbo].[Person] ([PersonID], [LastName], [FirstName], [HireDate], [EnrollmentDate]) VALUES (3, N'Olivotto', N'Nino', NULL, CAST(0x0000A0BF00000000 AS DateTime))
INSERT [dbo].[Person] ([PersonID], [LastName], [FirstName], [HireDate], [EnrollmentDate]) VALUES (4, N'Anand', N'Arturo', NULL, CAST(0x0000A0BF00000000 AS DateTime))
INSERT [dbo].[Person] ([PersonID], [LastName], [FirstName], [HireDate], [EnrollmentDate]) VALUES (5, N'Jai', N'Damien', NULL, CAST(0x0000A0BF00000000 AS DateTime))
INSERT [dbo].[Person] ([PersonID], [LastName], [FirstName], [HireDate], [EnrollmentDate]) VALUES (6, N'Holt', N'Roger', CAST(0x000097F100000000 AS DateTime), NULL)
INSERT [dbo].[Person] ([PersonID], [LastName], [FirstName], [HireDate], [EnrollmentDate]) VALUES (7, N'Martin', N'Randall', CAST(0x00008B1A00000000 AS DateTime), NULL)
SET IDENTITY_INSERT [dbo].[Person] OFF
SET IDENTITY_INSERT [dbo].[StudentGrade] ON

INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (1, N'C1045', 1, CAST(3.50 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (2, N'C1045', 2, CAST(3.00 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (3, N'C1045', 3, CAST(2.50 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (4, N'C1045', 4, CAST(4.00 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (5, N'C1045', 5, CAST(3.50 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (6, N'C1061', 1, CAST(4.00 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (7, N'C1061', 3, CAST(3.50 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (8, N'C1061', 4, CAST(2.50 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (9, N'C1061', 5, CAST(1.50 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (10, N'C2021', 1, CAST(2.50 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (11, N'C2021', 2, CAST(3.50 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (12, N'C2021', 4, CAST(3.00 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (13, N'C2021', 5, CAST(3.00 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (14, N'C2042', 1, CAST(2.00 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (15, N'C2042', 2, CAST(3.50 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (16, N'C2042', 3, CAST(4.00 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (17, N'C2042', 5, CAST(3.00 AS Decimal(3, 2)))
SET IDENTITY_INSERT [dbo].[StudentGrade] OFF
ALTER TABLE [dbo].[Course]  WITH CHECK ADD  CONSTRAINT [FK_Course_Department] FOREIGN KEY([DepartmentID])
REFERENCES [dbo].[Department] ([DepartmentID])
GO
ALTER TABLE [dbo].[Course] CHECK CONSTRAINT [FK_Course_Department]
GO
ALTER TABLE [dbo].[StudentGrade]  WITH CHECK ADD  CONSTRAINT [FK_StudentGrade_Student] FOREIGN KEY([StudentID])
REFERENCES [dbo].[Person] ([PersonID])
GO
ALTER TABLE [dbo].[StudentGrade] CHECK CONSTRAINT [FK_StudentGrade_Student]
GO
```

Код имеет следующий вид:

> [!TIP]
> Листинг кода относится к файлу базы данных Access, который называется MySchool.mdb. Файл MySchool.mdb (как часть полного примера проекта C# или Visual Basic) можно загрузить из [code.msdn.microsoft.com](https://code.msdn.microsoft.com/How-to-Retrieve-the-511acece).

```csharp
using System;
using System.Data;
using System.Data.OleDb;
using System.Data.SqlClient;

class Program {
   static void Main(string[] args) {
      String SqlDbConnectionString = "Data Source=(local);Initial Catalog=MySchool;Integrated Security=True;Asynchronous Processing=true;";

      InsertPerson(SqlDbConnectionString, "Janice", "Galvin");
      Console.WriteLine();

      InsertPersonInAdapter(SqlDbConnectionString, "Peter", "Krebs");
      Console.WriteLine();

      String oledbConnectionString = "Provider=Microsoft.Jet.OLEDB.4.0; Data Source=Database\\MySchool.mdb";
      InsertPersonInJet4Database(oledbConnectionString, "Janice", "Galvin");
      Console.WriteLine();

      Console.WriteLine("Please press any key to exit.....");
      Console.ReadKey();
   }

   // Using stored procedure to insert a new row and retrieve the identity value
   static void InsertPerson(String connectionString, String firstName, String lastName) {
      String commandText = "dbo.InsertPerson";

      using (SqlConnection conn = new SqlConnection(connectionString)) {
         using (SqlCommand cmd = new SqlCommand(commandText, conn)) {
            cmd.CommandType = CommandType.StoredProcedure;

            cmd.Parameters.Add(new SqlParameter("@FirstName", firstName));
            cmd.Parameters.Add(new SqlParameter("@LastName", lastName));
            SqlParameter personId = new SqlParameter("@PersonID", SqlDbType.Int);
            personId.Direction = ParameterDirection.Output;
            cmd.Parameters.Add(personId);

            conn.Open();
            cmd.ExecuteNonQuery();

            Console.WriteLine("Person Id of new person:{0}", personId.Value);
         }
      }
   }

   // Using stored procedure in adapter to insert new rows and update the identity value.
   static void InsertPersonInAdapter(String connectionString, String firstName, String lastName) {
      String commandText = "dbo.InsertPerson";
      using (SqlConnection conn = new SqlConnection(connectionString)) {
         SqlDataAdapter mySchool = new SqlDataAdapter("Select PersonID,FirstName,LastName from [dbo].[Person]", conn);

         mySchool.InsertCommand = new SqlCommand(commandText, conn);
         mySchool.InsertCommand.CommandType = CommandType.StoredProcedure;

         mySchool.InsertCommand.Parameters.Add(
             new SqlParameter("@FirstName", SqlDbType.NVarChar, 50, "FirstName"));
         mySchool.InsertCommand.Parameters.Add(
             new SqlParameter("@LastName", SqlDbType.NVarChar, 50, "LastName"));

         SqlParameter personId = mySchool.InsertCommand.Parameters.Add(new SqlParameter("@PersonID", SqlDbType.Int, 0, "PersonID"));
         personId.Direction = ParameterDirection.Output;

         DataTable persons = new DataTable();
         mySchool.Fill(persons);

         DataRow newPerson = persons.NewRow();
         newPerson["FirstName"] = firstName;
         newPerson["LastName"] = lastName;
         persons.Rows.Add(newPerson);

         mySchool.Update(persons);
         Console.WriteLine("Show all persons:");
         ShowDataTable(persons, 14);
      }
   }

   /// For a Jet 4.0 database, we need use the single statement and event handler to insert new rows and retrieve the identity value.
   static void InsertPersonInJet4Database(String connectionString, String firstName, String lastName) {
      String commandText = "Insert into Person(FirstName,LastName) Values(?,?)";
      using (OleDbConnection conn = new OleDbConnection(connectionString)) {
         OleDbDataAdapter mySchool = new OleDbDataAdapter("Select PersonID,FirstName,LastName from Person", conn);

         // Create Insert Command
         mySchool.InsertCommand = new OleDbCommand(commandText, conn);
         mySchool.InsertCommand.CommandType = CommandType.Text;

         mySchool.InsertCommand.Parameters.Add(new OleDbParameter("@FirstName", OleDbType.VarChar, 50, "FirstName"));
         mySchool.InsertCommand.Parameters.Add(new OleDbParameter("@LastName", OleDbType.VarChar, 50, "LastName"));
         mySchool.InsertCommand.UpdatedRowSource = UpdateRowSource.Both;

         DataTable persons = CreatePersonsTable();

         mySchool.Fill(persons);

         DataRow newPerson = persons.NewRow();
         newPerson["FirstName"] = firstName;
         newPerson["LastName"] = lastName;
         persons.Rows.Add(newPerson);

         DataTable dataChanges = persons.GetChanges();

         mySchool.RowUpdated += OnRowUpdated;

         mySchool.Update(dataChanges);

         Console.WriteLine("Data before merging:");
         ShowDataTable(persons, 14);
         Console.WriteLine();

         persons.Merge(dataChanges);
         persons.AcceptChanges();

         Console.WriteLine("Data after merging");
         ShowDataTable(persons, 14);
      }
   }

   static void OnRowUpdated(object sender, OleDbRowUpdatedEventArgs e) {
      if (e.StatementType == StatementType.Insert) {
         // Retrieve the identity value
         OleDbCommand cmdNewId = new OleDbCommand("Select @@IDENTITY", e.Command.Connection);
         e.Row["PersonID"] = (Int32)cmdNewId.ExecuteScalar();

         // After the status is changed, the original values in the row are preserved. And the
         // Merge method will be called to merge the new identity value into the original DataTable.
         e.Status = UpdateStatus.SkipCurrentRow;
      }
   }

   // Create the Persons table before filling.
   private static DataTable CreatePersonsTable() {
      DataTable persons = new DataTable();

      DataColumn personId = new DataColumn();
      personId.DataType = Type.GetType("System.Int32");
      personId.ColumnName = "PersonID";
      personId.AutoIncrement = true;
      personId.AutoIncrementSeed = 0;
      personId.AutoIncrementStep = -1;
      persons.Columns.Add(personId);

      DataColumn firstName = new DataColumn();
      firstName.DataType = Type.GetType("System.String");
      firstName.ColumnName = "FirstName";
      persons.Columns.Add(firstName);

      DataColumn lastName = new DataColumn();
      lastName.DataType = Type.GetType("System.String");
      lastName.ColumnName = "LastName";
      persons.Columns.Add(lastName);

      DataColumn[] pkey = { personId };
      persons.PrimaryKey = pkey;

      return persons;
   }

   private static void ShowDataTable(DataTable table, Int32 length) {
      foreach (DataColumn col in table.Columns) {
         Console.Write("{0,-" + length + "}", col.ColumnName);
      }
      Console.WriteLine();

      foreach (DataRow row in table.Rows) {
         foreach (DataColumn col in table.Columns) {
            if (col.DataType.Equals(typeof(DateTime)))
               Console.Write("{0,-" + length + ":d}", row[col]);
            else if (col.DataType.Equals(typeof(Decimal)))
               Console.Write("{0,-" + length + ":C}", row[col]);
            else
               Console.Write("{0,-" + length + "}", row[col]);
         }

         Console.WriteLine();
      }
   }
}
```

## <a name="see-also"></a>См. также

- [Извлечение и изменение данных в ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [Объекты DataAdapter и DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [Состояния и версии строк](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)
- [AcceptChanges и RejectChanges](../../../../docs/framework/data/adonet/dataset-datatable-dataview/acceptchanges-and-rejectchanges.md)
- [Слияние содержимого набора данных](../../../../docs/framework/data/adonet/dataset-datatable-dataview/merging-dataset-contents.md)
- [Обновление источников данных с объектами DataAdapter](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
