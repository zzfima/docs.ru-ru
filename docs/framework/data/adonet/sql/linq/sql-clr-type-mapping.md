---
title: Сопоставление типов SQL-CLR
ms.date: 07/23/2018
ms.assetid: 4ed76327-54a7-414b-82a9-7579bfcec04b
ms.openlocfilehash: 336732e0fe7ca8955702d325309db6a8e61b1722
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174541"
---
# <a name="sql-clr-type-mapping"></a>Сопоставление типов SQL-CLR
В LINQ to SQL модель данных реляционной базы данных сопоставляется с моделью объектов, выраженной на выбранном языке программирования. При выполнении приложения LINQ to SQL преобразует запросы LINQ модели объектов в код SQL и направляет их в базу данных для выполнения. Когда база данных возвращает результаты, LINQ to SQL преобразует их обратно в объекты, с которыми можно работать на языке программирования.  
  
 Для перевода данных между моделью объекта и базой данных необходимо определить *отображение типов.* В LINQ to SQL используется сопоставление типов, в котором каждому типу CLR ставится в соответствие определенный тип SQL Server. Можно определить сопоставления типов и другие данные о сопоставлении, такие как структура базы данных и табличные связи, в рамках модели объектов, используя сопоставление на основе атрибутов. Также можно задать данные о сопоставлении вне модели объектов с помощью внешнего файла сопоставления. Для получения дополнительной информации [External Mapping](external-mapping.md)см. [Attribute-Based Mapping](attribute-based-mapping.md)  
  
 В этом разделе обсуждаются следующие вопросы.  
  
- [Сопоставление типов по умолчанию](#DefaultTypeMapping)  
  
- [Таблица правил сопоставления типов во время выполнения](#BehaviorMatrix)  
  
- [Различия при выполнении в среде CLR и на SQL Server](#BehaviorDiffs)  
  
- [Сопоставление перечислений](#EnumMapping)  
  
- [Сопоставление чисел](#NumericMapping)  
  
- [Сопоставление текста и XML](#TextMapping)  
  
- [Сопоставление даты и времени](#DateMapping)  
  
- [Сопоставление двоичных объектов](#BinaryMapping)  
  
- [Прочие виды сопоставления](#MiscMapping)  
  
<a name="DefaultTypeMapping"></a>
## <a name="default-type-mapping"></a>Сопоставление типов по умолчанию  
 Можно создать сопоставление модели объектов или внешний файл сопоставления автоматически в реляционном конструкторе объектов или в программе командной строки SQLMetal. В сопоставлениях типов по умолчанию для этих средств определяется, какие типы CLR выбираются в соответствии со столбцами, находящимися в базе данных SQL Server. Для получения дополнительной информации об [использовании](creating-the-object-model.md)этих инструментов см.  
  
 Также можно использовать метод <xref:System.Data.Linq.DataContext.CreateDatabase%2A> для создания базы данных SQL Server на основе сведений о сопоставлении, содержащихся в модели объектов или во внешнем файле сопоставления. В сопоставлениях типов по умолчанию для метода <xref:System.Data.Linq.DataContext.CreateDatabase%2A> определяется, какой тип выбирается для создаваемых столбцов SQL Server в соответствии с типами CLR в модели объектов. Для получения дополнительной информации [см. Как: Динамически создать базу данных](how-to-dynamically-create-a-database.md).  
  
<a name="BehaviorMatrix"></a>
## <a name="type-mapping-run-time-behavior-matrix"></a>Таблица правил сопоставления типов во время выполнения  
 На следующей схеме показаны стандартные правила, по которым выполняется сопоставление определенных типов, когда данные получаются или сохраняются в базе данных. За исключением сериализации, LINQ to SQL не поддерживает сопоставление между типами CLR или SQL Server, которые не указаны в этой таблице. Для получения дополнительной информации о поддержке сериализации [см.](#BinarySerialization)  

![Таблица отображения типа данных S'L CLR для S'L CLR](./media/sql-clr-type-mapping.png)

> [!NOTE]
> Некоторые сопоставления типов могут приводить к возникновению исключений переполнения или потери данных в ходе преобразования данных в базу данных или из нее.  
  
### <a name="custom-type-mapping"></a>Сопоставление пользовательских типов  
 В LINQ to SQL помимо сопоставлений типов по умолчанию, используемых в реляционном конструкторе объектов, программе SQLMetal и методу <xref:System.Data.Linq.DataContext.CreateDatabase%2A> доступны и другие сопоставления. Можно создать нестандартные сопоставления типов, явно указав их в DBML-файле. Затем этот DBML-файл используется для создания кода модели объектов и файла сопоставления. Для получения дополнительной [информации, см.](sql-clr-custom-type-mappings.md)  
  
<a name="BehaviorDiffs"></a>
## <a name="behavior-differences-between-clr-and-sql-execution"></a>Различия при выполнении в среде CLR и на SQL Server  
 Поскольку между средами CLR и SQL Server существуют различия в точности и правилах выполнения кода, то правила и результаты вычислений могут оказать различными (в зависимости от их проведения). Вычисления, выполняемые в запросах LINQ to SQL, фактически преобразуются в язык Transact-SQL, а затем выполняются в базе данных SQL Server. Вычисления, проводимые вне запросов LINQ to SQL, выполняются в контексте среды CLR.  
  
 Например, ниже представлены некоторые отличия в работе среды CLR и SQL Server.  
  
- SQL Server применяет для некоторых типов данных порядок, отличный от порядка эквивалентных типов в среде CLR. Например, порядок данных типа `UNIQUEIDENTIFIER` в SQL Server отличается от порядка данных типа <xref:System.Guid?displayProperty=nameWithType> в среде CLR.  
  
- Некоторые операции сравнения строк обрабатываются в SQL Server иначе, чем в среде CLR. Порядок сравнения строк в SQL Server зависит от параметров сортировки на сервере. Для получения дополнительной информации, [см. Работа с коллажами](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms187582(v=sql.105)) в Microsoft S'L Server Books Онлайн.  
  
- Для некоторых сопоставленных функций SQL Server может возвращать значения, отличные от аналогичных значений, возвращаемых средой CLR. Например, функции проверки равенства будут возвращать различные результаты, поскольку SQL Server считает равными две строки, различающиеся только конечными пробелами, в то время как с точки зрения среды CLR эти строки не равны.  
  
<a name="EnumMapping"></a>
## <a name="enum-mapping"></a>Сопоставление перечислений  
 LINQ to SQL поддерживает два способа для сопоставления типа CLR <xref:System.Enum?displayProperty=nameWithType> с типами SQL Server.  
  
- Сопоставление с числовыми типами SQL (`TINYINT`, `SMALLINT`, `INT`, `BIGINT`).  
  
     При сопоставлении типа <xref:System.Enum?displayProperty=nameWithType> среды CLR с числовым типом SQL, выполняется сопоставление базового целочисленного значения CLR <xref:System.Enum?displayProperty=nameWithType> со значением в столбце базы данных SQL Server. Например, если объект <xref:System.Enum?displayProperty=nameWithType> с именем `DaysOfWeek` содержит элемент с именем `Tue`, базовое целочисленное значение для которого равно 3, то этому элементу сопоставляется значение 3 в базе данных.  
  
- Сопоставление с текстовыми типами SQL (`CHAR`, `NCHAR`, `VARCHAR`, `NVARCHAR`).  
  
     При сопоставлении типа CLR <xref:System.Enum?displayProperty=nameWithType> с текстовым типом SQL выполняется сопоставление значения в базе данных SQL с именами элементов перечисления CLR <xref:System.Enum?displayProperty=nameWithType>. Например, если объект <xref:System.Enum?displayProperty=nameWithType> с именем `DaysOfWeek` содержит элемент с именем `Tue`, базовое целочисленное значение для которого равно 3, то этому элементу сопоставляется значение `Tue` в базе данных.  
  
> [!NOTE]
> При сопоставлении текстовых типов SQL с типом CLR <xref:System.Enum?displayProperty=nameWithType> в сопоставляемый столбец SQL включаются только имена элементов <xref:System.Enum>. Прочие значения в столбце SQL, сопоставленном с <xref:System.Enum>, не поддерживаются.  
  
 Реляционный конструктор объектов и программа командной строки SQLMetal не выполняют автоматическое сопоставление типа SQL с классом CLR <xref:System.Enum>. Такое сопоставление необходимо настроить вручную, изменив DBML-файл для использования реляционным конструктором объектов и программой SQLMetal. Для получения дополнительной информации о пользовательском отображении [шрифта](sql-clr-custom-type-mappings.md)см.  
  
 Потому что столбец S'L, предназначенный для перечисления, будет того же типа, что и другие числовые и текстовые столбцы; эти инструменты не распознают ваши намерения и по умолчанию для отображения, как описано в следующих [разделах количественного и](#NumericMapping) [текстового отображения.](#TextMapping) Для получения дополнительной информации о генерации кода с файлом DBML, [см.](code-generation-in-linq-to-sql.md)  
  
 Метод <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> создает столбец SQL числового типа в соответствии с типом CLR <xref:System.Enum?displayProperty=nameWithType>.  
  
<a name="NumericMapping"></a>
## <a name="numeric-mapping"></a>Сопоставление чисел  
 LINQ to SQL позволяет сопоставлять многие числовые типы CLR и SQL Server. В следующей таблице показаны типы CLR, которые выбираются реляционным конструктором объектов и программой SQLMetal при создании сопоставления модели объектов или внешнего файла сопоставления, основанного на базе данных.  
  
|Тип SQL Server|Тип CLR, по умолчанию используемый для сопоставления c реляционным конструктором объектов и программой SQLMetal|  
|---------------------|-----------------------------------------------------------------|  
|`BIT`|<xref:System.Boolean?displayProperty=nameWithType>|  
|`TINYINT`|<xref:System.Int16?displayProperty=nameWithType>|  
|`INT`|<xref:System.Int32?displayProperty=nameWithType>|  
|`BIGINT`|<xref:System.Int64?displayProperty=nameWithType>|  
|`SMALLMONEY`|<xref:System.Decimal?displayProperty=nameWithType>|  
|`MONEY`|<xref:System.Decimal?displayProperty=nameWithType>|  
|`DECIMAL`|<xref:System.Decimal?displayProperty=nameWithType>|  
|`NUMERIC`|<xref:System.Decimal?displayProperty=nameWithType>|  
|`REAL/FLOAT(24)`|<xref:System.Single?displayProperty=nameWithType>|  
|`FLOAT/FLOAT(53)`|<xref:System.Double?displayProperty=nameWithType>|  
  
 В следующей таблице показано сопоставление типов по умолчанию, используемое методом <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> для определения типов столбцов SQL, которые должны создаваться в соответствии с типами CLR, определенными в модели объектов или во внешнем файле сопоставления.  
  
|Тип CLR|Тип SQL Server, по умолчанию используемый методом <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Boolean?displayProperty=nameWithType>|`BIT`|  
|<xref:System.Byte?displayProperty=nameWithType>|`TINYINT`|  
|<xref:System.Int16?displayProperty=nameWithType>|`SMALLINT`|  
|<xref:System.Int32?displayProperty=nameWithType>|`INT`|  
|<xref:System.Int64?displayProperty=nameWithType>|`BIGINT`|  
|<xref:System.SByte?displayProperty=nameWithType>|`SMALLINT`|  
|<xref:System.UInt16?displayProperty=nameWithType>|`INT`|  
|<xref:System.UInt32?displayProperty=nameWithType>|`BIGINT`|  
|<xref:System.UInt64?displayProperty=nameWithType>|`DECIMAL(20)`|  
|<xref:System.Decimal?displayProperty=nameWithType>|`DECIMAL(29,4)`|  
|<xref:System.Single?displayProperty=nameWithType>|`REAL`|  
|<xref:System.Double?displayProperty=nameWithType>|`FLOAT`|  
  
 Можно выбрать другие сопоставления чисел, но некоторые из них могут вызвать исключения переполнения или потери данных в процессе преобразования данных в базу данных или из базы данных. Для получения дополнительной [информации](#BehaviorMatrix)см.  
  
### <a name="decimal-and-money-types"></a>Типы Decimal и Money  
 Точность по умолчанию `DECIMAL` типа S'L Server (18 десятичных цифр слева и справа от десятичной точки) <xref:System.Decimal?displayProperty=nameWithType> намного меньше, чем точность типа CLR, с которым он работает по умолчанию. Это может вызвать потерю точности при сохранении данных в базе данных. Однако противоположная ситуация может возникнуть, если для типа SQL Server `DECIMAL` задана точность, превышающая 29 разрядов. Если для типа SQL Server `DECIMAL` задана точность, превышающая точность типа CLR <xref:System.Decimal?displayProperty=nameWithType>, то потеря точности может возникнуть при получении данных из базы данных.  
  
 Типы SQL Server `MONEY` и `SMALLMONEY`, которые также по умолчанию сопоставляются с типом CLR <xref:System.Decimal?displayProperty=nameWithType>, имеют намного меньшую точность, что может вызвать исключения переполнения или потери данных при сохранении данных в базу данных.  
  
<a name="TextMapping"></a>
## <a name="text-and-xml-mapping"></a>Сопоставление текста и XML  
 Кроме того, существует множество текстовых типов и типов XML, для которых возможно сопоставление с помощью LINQ to SQL. В следующей таблице показаны типы CLR, которые выбираются реляционным конструктором объектов и программой SQLMetal при создании сопоставления модели объектов или внешнего файла сопоставления, основанного на базе данных.  
  
|Тип SQL Server|Тип CLR, по умолчанию используемый для сопоставления c реляционным конструктором объектов и программой SQLMetal|  
|---------------------|-----------------------------------------------------------------|  
|`CHAR`|<xref:System.String?displayProperty=nameWithType>|  
|`NCHAR`|<xref:System.String?displayProperty=nameWithType>|  
|`VARCHAR`|<xref:System.String?displayProperty=nameWithType>|  
|`NVARCHAR`|<xref:System.String?displayProperty=nameWithType>|  
|`TEXT`|<xref:System.String?displayProperty=nameWithType>|  
|`NTEXT`|<xref:System.String?displayProperty=nameWithType>|  
|`XML`|<xref:System.Xml.Linq.XElement?displayProperty=nameWithType>|  
  
 В следующей таблице показано сопоставление типов по умолчанию, используемое методом <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> для определения типов столбцов SQL, которые должны создаваться в соответствии с типами CLR, определенными в модели объектов или во внешнем файле сопоставления.  
  
|Тип CLR|Тип SQL Server, по умолчанию используемый методом <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Char?displayProperty=nameWithType>|`NCHAR(1)`|  
|<xref:System.String?displayProperty=nameWithType>|`NVARCHAR(4000)`|  
|<xref:System.Char?displayProperty=nameWithType>[]|`NVARCHAR(4000)`|  
|Пользовательский тип, реализующий методы `Parse()` и `ToString()`|`NVARCHAR(MAX)`|  
  
 Можно выбрать множество других текстовых сопоставлений и сопоставлений XML, но некоторые из них могут вызвать исключения переполнения или потери данных в процессе преобразования данных в базу или из базы данных. Для получения дополнительной [информации](#BehaviorMatrix)см.  
  
### <a name="xml-types"></a>Типы XML  
 Тип данных SQL Server `XML` доступен в версиях Microsoft SQL Server 2005 и выше. Тип данных SQL Server `XML` может быть сопоставлен с <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XDocument> или <xref:System.String>. Если в столбце хранятся XML-фрагменты, которые невозможно считать в объект <xref:System.Xml.Linq.XElement>, то столбец необходимо сопоставить с типом <xref:System.String>, чтобы избежать ошибок времени выполнения. К XML-фрагментам, для которых необходимо сопоставление с типом <xref:System.String>, относятся следующие:  
  
- последовательность XML-элементов;  
  
- Атрибуты  
  
- общие идентификаторы;  
  
- Комментарии  
  
 Несмотря на <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XDocument> то, что можно сопоставить карту и на сервере S'L, как показано в [матрице поведения времени отображения типа Картирования,](#BehaviorMatrix) <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> метод не имеет отображения типа сервера по умолчанию для этих типов.  
  
### <a name="custom-types"></a>Пользовательские типы  
 Если класс реализует `Parse()` `ToString()`и, вы можете сопоставить объект с`CHAR` `NCHAR`любым `VARCHAR` `NVARCHAR`типом текста S'L (, , , `TEXT`, `NTEXT`. `XML` Объект сохраняется в базе данных путем передачи значения, возвращаемого методом `ToString()`, в сопоставленный столбец базы данных. Объект воссоздается при вызове метода `Parse()` со строкой, возвращаемой из базы данных.  
  
> [!NOTE]
> LINQ to SQL не поддерживает сериализацию, выполняемую с помощью <xref:System.Xml.Serialization.IXmlSerializable?displayProperty=nameWithType>.  
  
<a name="DateMapping"></a>
## <a name="date-and-time-mapping"></a>Сопоставление даты и времени  
 В LINQ to SQL можно сопоставлять многие типы даты и времени SQL Server. В следующей таблице показаны типы CLR, которые выбираются реляционным конструктором объектов и программой SQLMetal при создании сопоставления модели объектов или внешнего файла сопоставления, основанного на базе данных.  
  
|Тип SQL Server|Тип CLR, по умолчанию используемый для сопоставления c реляционным конструктором объектов и программой SQLMetal|  
|---------------------|-----------------------------------------------------------------|  
|`SMALLDATETIME`|<xref:System.DateTime?displayProperty=nameWithType>|  
|`DATETIME`|<xref:System.DateTime?displayProperty=nameWithType>|  
|`DATETIME2`|<xref:System.DateTime?displayProperty=nameWithType>|  
|`DATETIMEOFFSET`|<xref:System.DateTimeOffset?displayProperty=nameWithType>|  
|`DATE`|<xref:System.DateTime?displayProperty=nameWithType>|  
|`TIME`|<xref:System.TimeSpan?displayProperty=nameWithType>|  
  
 В следующей таблице показано сопоставление типов по умолчанию, используемое методом <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> для определения типов столбцов SQL, которые должны создаваться в соответствии с типами CLR, определенными в модели объектов или во внешнем файле сопоставления.  
  
|Тип CLR|Тип SQL Server, по умолчанию используемый методом <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.DateTime?displayProperty=nameWithType>|`DATETIME`|  
|<xref:System.DateTimeOffset?displayProperty=nameWithType>|`DATETIMEOFFSET`|  
|<xref:System.TimeSpan?displayProperty=nameWithType>|`TIME`|  
  
 Можно выбрать другие сопоставления даты и времени, но некоторые из них могут вызвать исключения переполнения или потери данных в процессе преобразования данных в базу данных или из базы данных. Для получения дополнительной [информации](#BehaviorMatrix)см.  
  
> [!NOTE]
> Типы данных SQL Server `DATETIME2`, `DATETIMEOFFSET`, `DATE` и `TIME` доступны в версиях Microsoft SQL Server 2008 и выше. LINQ to SQL поддерживает сопоставление с этими новыми типами, начиная с версии платформы .NET Framework 3.5 с пакетом обновления 1 (SP1).  
  
### <a name="systemdatetime"></a>System.Datetime  
 Диапазон и точность типа CLR <xref:System.DateTime?displayProperty=nameWithType> превышают диапазон и точность типа SQL Server `DATETIME`, с которым по умолчанию выполняется сопоставление в методе <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>. Чтобы избежать исключений, связанных с датами вне диапазона `DATETIME`, используйте тип `DATETIME2`, который доступен, начиная с версии Microsoft SQL Server 2008. `DATETIME2`может соответствовать дальности и <xref:System.DateTime?displayProperty=nameWithType>точности CLR.  
  
 В датах SQL Server не учитывается часовой пояс (<xref:System.TimeZone>), который имеет широкую поддержку в среде CLR. Значения <xref:System.TimeZone> сохраняются в базе данных без изменений и без преобразования <xref:System.TimeZone>, независимо от исходных данных <xref:System.DateTimeKind>. Когда значения <xref:System.DateTime> получаются из базы данных, они загружаются в <xref:System.DateTime> без изменений, а <xref:System.DateTimeKind> получает значение <xref:System.DateTimeKind.Unspecified>. Для получения дополнительной <xref:System.DateTime?displayProperty=nameWithType> информации об поддерживаемых методах см. [System.DateTime Methods](system-datetime-methods.md)  
  
### <a name="systemtimespan"></a>System.TimeSpan  
 Microsoft SQL Server 2008 и платформа .NET Framework 3.5 с пакетом обновления 1 (SP1) позволяют сопоставлять тип CLR <xref:System.TimeSpan?displayProperty=nameWithType> с типом SQL Server `TIME`. Однако между типом CLR <xref:System.TimeSpan?displayProperty=nameWithType> и типом SQL Server `TIME` существует большая разница в поддерживаемом диапазоне. Сопоставление значений (меньше 0 или больше 23:59:59.9999999 часов) с типом SQL `TIME` вызовет исключение переполнения. Для получения дополнительной [информации см.](system-timespan-methods.md)  
  
 В Microsoft SQL Server 2000 и SQL Server 2005 нельзя сопоставлять поля базы данных с типом <xref:System.TimeSpan>. При этом операции с типом <xref:System.TimeSpan> поддерживаются, поскольку значения <xref:System.TimeSpan> могут возвращаться операцией вычитания <xref:System.DateTime> или входить в выражение в виде литерала или привязанной переменной.  
  
<a name="BinaryMapping"></a>
## <a name="binary-mapping"></a>Сопоставление двоичных объектов  
 Для многих типов SQL Server возможно сопоставление с типом CLR <xref:System.Data.Linq.Binary?displayProperty=nameWithType>. В следующей таблице показаны типы SQL Server, для которых реляционный конструктор объектов и программа SQLMetal определяют тип CLR <xref:System.Data.Linq.Binary?displayProperty=nameWithType> во время построения модели объектов или внешнего файла сопоставления, основанного на базе данных.  
  
|Тип SQL Server|Тип CLR, по умолчанию используемый для сопоставления c реляционным конструктором объектов и программой SQLMetal|  
|---------------------|-----------------------------------------------------------------|  
|`BINARY(50)`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|`VARBINARY(50)`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|`VARBINARY(MAX)`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|`VARBINARY(MAX)`с `FILESTREAM` атрибутом|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|`IMAGE`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|`TIMESTAMP`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
  
 В следующей таблице показано сопоставление типов по умолчанию, используемое методом <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> для определения типов столбцов SQL, которые должны создаваться в соответствии с типами CLR, определенными в модели объектов или во внешнем файле сопоставления.  
  
|Тип CLR|Тип SQL Server, по умолчанию используемый методом <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|`VARBINARY(MAX)`|  
|<xref:System.Byte?displayProperty=nameWithType>|`VARBINARY(MAX)`|  
|<xref:System.Runtime.Serialization.ISerializable?displayProperty=nameWithType>|`VARBINARY(MAX)`|  
  
 Можно выбрать другие сопоставления двоичных объектов, но некоторые из них могут вызвать исключения переполнения или потери данных в процессе преобразования данных в базу данных или из базы данных. Для получения дополнительной [информации](#BehaviorMatrix)см.  
  
### <a name="sql-server-filestream"></a>SQL Server FILESTREAM  
 Атрибут `FILESTREAM` для столбцов `VARBINARY(MAX)` доступен, начиная с версии Microsoft SQL Server 2008. Сопоставление с этим типом в LINQ to SQL поддерживается, начиная с версии платформы .NET Framework 3.5 с пакетом обновления 1 (SP1).  
  
 Столбцы `VARBINARY(MAX)` с атрибутом `FILESTREAM` можно сопоставлять с объектами <xref:System.Data.Linq.Binary>, но метод <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> не может автоматически создавать столбцы с атрибутом `FILESTREAM`. Для получения `FILESTREAM`дополнительной информации о , см [FILESTREAM Обзор](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb933993(v=sql.105)).  
  
<a name="BinarySerialization"></a>
### <a name="binary-serialization"></a>Двоичная сериализация  
 Если в классе реализован интерфейс <xref:System.Runtime.Serialization.ISerializable>, объект этого класса можно сериализовать в любое двоичное поле SQL (`BINARY`, `VARBINARY`, `IMAGE`). Сериализация и десериализация объекта выполняется в соответствии с реализацией интерфейса <xref:System.Runtime.Serialization.ISerializable>. Для получения дополнительной информации [см.](../../../../../standard/serialization/binary-serialization.md)
  
<a name="MiscMapping"></a>
## <a name="miscellaneous-mapping"></a>Прочие виды сопоставления  
 В следующей таблице показаны сопоставления по умолчанию для некоторых типов, не упомянутых ранее. В следующей таблице показаны типы CLR, которые выбираются реляционным конструктором объектов и программой SQLMetal при создании сопоставления модели объектов или внешнего файла сопоставления, основанного на базе данных.  
  
|Тип SQL Server|Тип CLR, по умолчанию используемый для сопоставления c реляционным конструктором объектов и программой SQLMetal|  
|---------------------|-----------------------------------------------------------------|  
|`UNIQUEIDENTIFIER`|<xref:System.Guid?displayProperty=nameWithType>|  
|`SQL_VARIANT`|<xref:System.Object?displayProperty=nameWithType>|  
  
 В следующей таблице показано сопоставление типов по умолчанию, используемое методом <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> для определения типов столбцов SQL, которые должны создаваться в соответствии с типами CLR, определенными в модели объектов или во внешнем файле сопоставления.  
  
|Тип CLR|Тип SQL Server, по умолчанию используемый методом <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Guid?displayProperty=nameWithType>|`UNIQUEIDENTIFIER`|  
|<xref:System.Object?displayProperty=nameWithType>|`SQL_VARIANT`|  
  
 LINQ to SQL не поддерживает для этих типов никаких других сопоставлений.  Для получения дополнительной [информации](#BehaviorMatrix)см.  
  
## <a name="see-also"></a>См. также раздел

- [Сопоставление, основанное на атрибутах](attribute-based-mapping.md)
- [Внешнее сопоставление](external-mapping.md)
- [Типы данных и функции](data-types-and-functions.md)
- [Несоответствия типов SQL-CLR](sql-clr-type-mismatches.md)
