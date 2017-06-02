---
title: "Сопоставление типов SQL и CLR | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4ed76327-54a7-414b-82a9-7579bfcec04b
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Сопоставление типов SQL и CLR
В LINQ to SQL модель данных реляционной базы данных сопоставляется с моделью объектов, выраженной на выбранном языке программирования.  При выполнении приложения LINQ to SQL преобразует запросы LINQ модели объектов в код SQL и направляет их в базу данных для выполнения.  Когда база данных возвращает результаты, LINQ to SQL преобразует их обратно в объекты, с которыми можно работать на языке программирования.  
  
 Для преобразования данных между моделью объектов и базой данных необходимо определить *сопоставление типов*.  В LINQ to SQL используется сопоставление типов, в котором каждому типу CLR ставится в соответствие определенный тип SQL Server.  Можно определить сопоставления типов и другие данные о сопоставлении, такие как структура базы данных и табличные связи, в рамках модели объектов, используя сопоставление на основе атрибутов.  Также можно задать данные о сопоставлении вне модели объектов с помощью внешнего файла сопоставления.  Дополнительные сведения см. в разделе [Сопоставление на основе атрибутов](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md) и [Внешние сопоставления](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).  
  
 В этом разделе обсуждаются следующие вопросы.  
  
-   [Сопоставление типов по умолчанию](#DefaultTypeMapping)  
  
-   [Таблица правил сопоставления типов во время выполнения](#BehaviorMatrix)  
  
-   [Различия при выполнении в среде CLR и на SQL Server](#BehaviorDiffs)  
  
-   [Сопоставление перечислений](#EnumMapping)  
  
-   [Сопоставление чисел](#NumericMapping)  
  
-   [Сопоставление текста и XML](#TextMapping)  
  
-   [Сопоставление даты и времени](#DateMapping)  
  
-   [Сопоставление двоичных объектов](#BinaryMapping)  
  
-   [Прочие виды сопоставления](#MiscMapping)  
  
<a name="DefaultTypeMapping"></a>   
## Сопоставление типов по умолчанию  
 Можно создать сопоставление модели объектов или внешний файл сопоставления автоматически в реляционном конструкторе объектов или в программе командной строки SQLMetal.  В сопоставлениях типов по умолчанию для этих средств определяется, какие типы CLR выбираются в соответствии со столбцами, находящимися в базе данных SQL Server.  Дополнительные сведения об их использовании см. в разделе [Создание модели объектов](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md).  
  
 Также можно использовать метод <xref:System.Data.Linq.DataContext.CreateDatabase%2A> для создания базы данных SQL Server на основе сведений о сопоставлении, содержащихся в модели объектов или во внешнем файле сопоставления.  В сопоставлениях типов по умолчанию для метода <xref:System.Data.Linq.DataContext.CreateDatabase%2A> определяется, какой тип выбирается для создаваемых столбцов SQL Server в соответствии с типами CLR в модели объектов.  Дополнительные сведения см. в разделе [Как динамически создать базу данных](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md).  
  
<a name="BehaviorMatrix"></a>   
## Таблица правил сопоставления типов во время выполнения  
 На следующей схеме показаны стандартные правила, по которым выполняется сопоставление определенных типов, когда данные получаются или сохраняются в базе данных.  За исключением сериализации, LINQ to SQL не поддерживает сопоставление между типами CLR или SQL Server, которые не указаны в этой таблице.  Дополнительные сведения о поддержке сериализации см. в разделе [Двоичная сериализация](#BinarySerialization).  
  
> [!NOTE]
>  Некоторые сопоставления типов могут приводить к возникновению исключений переполнения или потери данных в ходе преобразования данных в базу данных или из нее.  
  
### Нестандартное сопоставление типов  
 В LINQ to SQL помимо сопоставлений типов по умолчанию, используемых в реляционном конструкторе объектов, программе SQLMetal и методу <xref:System.Data.Linq.DataContext.CreateDatabase%2A> доступны и другие сопоставления.  Можно создать нестандартные сопоставления типов, явно указав их в DBML\-файле.  Затем этот DBML\-файл используется для создания кода модели объектов и файла сопоставления.  Подробнее: [Сопоставления пользовательских типов SQL\-CLR ](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-custom-type-mappings.md).  
  
<a name="BehaviorDiffs"></a>   
## Различия при выполнении в среде CLR и на SQL Server  
 Поскольку между средами CLR и SQL Server существуют различия в точности и правилах выполнения кода, то правила и результаты вычислений могут оказать различными \(в зависимости от их проведения\).  Вычисления, выполняемые в запросах LINQ to SQL, фактически преобразуются в язык Transact\-SQL, а затем выполняются в базе данных SQL Server.  Вычисления, проводимые вне запросов LINQ to SQL, выполняются в контексте среды CLR.  
  
 Например, ниже представлены некоторые отличия в работе среды CLR и SQL Server.  
  
-   SQL Server применяет для некоторых типов данных порядок, отличный от порядка эквивалентных типов в среде CLR.  Например, порядок данных типа `UNIQUEIDENTIFIER` в SQL Server отличается от порядка данных типа <xref:System.Guid?displayProperty=fullName> в среде CLR.  
  
-   Некоторые операции сравнения строк обрабатываются в SQL Server иначе, чем в среде CLR.  Порядок сравнения строк в SQL Server зависит от параметров сортировки на сервере.  Дополнительные сведения см. в разделе [Работа с параметрами сортировки](http://go.microsoft.com/fwlink/?LinkId=115330) электронной документации по SQL Server.  
  
-   Для некоторых сопоставленных функций SQL Server может возвращать значения, отличные от аналогичных значений, возвращаемых средой CLR.  Например, функции проверки равенства будут возвращать различные результаты, поскольку SQL Server считает равными две строки, различающиеся только конечными пробелами, в то время как с точки зрения среды CLR эти строки не равны.  
  
<a name="EnumMapping"></a>   
## Сопоставление перечислений  
 LINQ to SQL поддерживает два способа для сопоставления типа CLR <xref:System.Enum?displayProperty=fullName> с типами SQL Server.  
  
-   Сопоставление с числовыми типами SQL \(`TINYINT`, `SMALLINT`, `INT`, `BIGINT`\).  
  
     При сопоставлении типа <xref:System.Enum?displayProperty=fullName> среды CLR с числовым типом SQL, выполняется сопоставление базового целочисленного значения CLR <xref:System.Enum?displayProperty=fullName> со значением в столбце базы данных SQL Server.  Например, если объект <xref:System.Enum?displayProperty=fullName> с именем `DaysOfWeek` содержит элемент с именем `Tue`, базовое целочисленное значение для которого равно 3, то этому элементу сопоставляется значение 3 в базе данных.  
  
-   Сопоставление с текстовыми типами SQL \(`CHAR`, `NCHAR`, `VARCHAR`, `NVARCHAR`\).  
  
     При сопоставлении типа CLR <xref:System.Enum?displayProperty=fullName> с текстовым типом SQL выполняется сопоставление значения в базе данных SQL с именами элементов перечисления CLR <xref:System.Enum?displayProperty=fullName>.  Например, если объект <xref:System.Enum?displayProperty=fullName> с именем `DaysOfWeek` содержит элемент с именем `Tue`, базовое целочисленное значение для которого равно 3, то этому элементу сопоставляется значение `Tue` в базе данных.  
  
> [!NOTE]
>  При сопоставлении текстовых типов SQL с типом CLR <xref:System.Enum?displayProperty=fullName> в сопоставляемый столбец SQL включаются только имена элементов <xref:System.Enum>.  Прочие значения в столбце SQL, сопоставленном с <xref:System.Enum>, не поддерживаются.  
  
 Реляционный конструктор объектов и программа командной строки SQLMetal не выполняют автоматическое сопоставление типа SQL с классом CLR <xref:System.Enum>.  Такое сопоставление необходимо настроить вручную, изменив DBML\-файл для использования реляционным конструктором объектов и программой SQLMetal.  Подробнее о настраиваемом сопоставлении типов: [Сопоставления пользовательских типов SQL\-CLR ](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-custom-type-mappings.md).  
  
 Поскольку столбец SQL, предназначенный для перечисления, будет иметь тот же тип, что и другие числовые и текстовые столбцы, эти средства не смогут определить, что столбец должен использовать для перечисления, и по умолчанию выполнят сопоставление, описанное в разделах [Сопоставление чисел](#NumericMapping) и [Сопоставление текста и XML](#TextMapping).  Дополнительные сведения о создании кода с помощью DBML\-файла см. в разделе [Создание кода в LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).  
  
 Метод <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName> создает столбец SQL числового типа в соответствии с типом CLR <xref:System.Enum?displayProperty=fullName>.  
  
<a name="NumericMapping"></a>   
## Сопоставление чисел  
 LINQ to SQL позволяет сопоставлять многие числовые типы CLR и SQL Server.  В следующей таблице показаны типы CLR, которые выбираются реляционным конструктором объектов и программой SQLMetal при создании сопоставления модели объектов или внешнего файла сопоставления, основанного на базе данных.  
  
|Тип SQL Server|Тип CLR, по умолчанию используемый для сопоставления c реляционным конструктором объектов и программой SQLMetal|  
|--------------------|---------------------------------------------------------------------------------------------------------------------|  
|`BIT`|<xref:System.Boolean?displayProperty=fullName>|  
|`TINYINT`|<xref:System.Int16?displayProperty=fullName>|  
|`INT`|<xref:System.Int32?displayProperty=fullName>|  
|`BIGINT`|<xref:System.Int64?displayProperty=fullName>|  
|`SMALLMONEY`|<xref:System.Decimal?displayProperty=fullName>|  
|`MONEY`|<xref:System.Decimal?displayProperty=fullName>|  
|`DECIMAL`|<xref:System.Decimal?displayProperty=fullName>|  
|`NUMERIC`|<xref:System.Decimal?displayProperty=fullName>|  
|`REAL/FLOAT(24)`|<xref:System.Single?displayProperty=fullName>|  
|`FLOAT/FLOAT(53)`|<xref:System.Double?displayProperty=fullName>|  
  
 В следующей таблице показано сопоставление типов по умолчанию, используемое методом <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName> для определения типов столбцов SQL, которые должны создаваться в соответствии с типами CLR, определенными в модели объектов или во внешнем файле сопоставления.  
  
|Тип CLR|Тип SQL Server, по умолчанию используемый методом <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName>|  
|-------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Boolean?displayProperty=fullName>|`BIT`|  
|<xref:System.Byte?displayProperty=fullName>|`TINYINT`|  
|<xref:System.Int16?displayProperty=fullName>|`SMALLINT`|  
|<xref:System.Int32?displayProperty=fullName>|`INT`|  
|<xref:System.Int64?displayProperty=fullName>|`BIGINT`|  
|<xref:System.SByte?displayProperty=fullName>|`SMALLINT`|  
|<xref:System.UInt16?displayProperty=fullName>|`INT`|  
|<xref:System.UInt32?displayProperty=fullName>|`BIGINT`|  
|<xref:System.UInt64?displayProperty=fullName>|`DECIMAL(20)`|  
|<xref:System.Decimal?displayProperty=fullName>|`DECIMAL(29,4)`|  
|<xref:System.Single?displayProperty=fullName>|`REAL`|  
|<xref:System.Double?displayProperty=fullName>|`FLOAT`|  
  
 Можно выбрать другие сопоставления чисел, но некоторые из них могут вызвать исключения переполнения или потери данных в процессе преобразования данных в базу данных или из базы данных.  Дополнительные сведения см. в разделе [Таблица правил сопоставления типов во время выполнения](#BehaviorMatrix).  
  
### Типы Decimal и Money  
 Точность, используемая по умолчанию для типа SQL Server `DECIMAL` \(18 десятичных разрядов слева и справа от десятичного разделителя\), намного меньше точности типа CLR <xref:System.Decima?displayProperty=fullName>l, с которым он сопоставляется по умолчанию.  Это может вызвать потерю точности при сохранении данных в базе данных.  Однако противоположная ситуация может возникнуть, если для типа SQL Server `DECIMAL` задана точность, превышающая 29 разрядов.  Если для типа SQL Server `DECIMAL` задана точность, превышающая точность типа CLR <xref:System.Decimal?displayProperty=fullName>, то потеря точности может возникнуть при получении данных из базы данных.  
  
 Типы SQL Server `MONEY` и `SMALLMONEY`, которые также по умолчанию сопоставляются с типом CLR <xref:System.Decimal?displayProperty=fullName>, имеют намного меньшую точность, что может вызвать исключения переполнения или потери данных при сохранении данных в базу данных.  
  
<a name="TextMapping"></a>   
## Сопоставление текста и XML  
 Кроме того, существует множество текстовых типов и типов XML, для которых возможно сопоставление с помощью LINQ to SQL.  В следующей таблице показаны типы CLR, которые выбираются реляционным конструктором объектов и программой SQLMetal при создании сопоставления модели объектов или внешнего файла сопоставления, основанного на базе данных.  
  
|Тип SQL Server|Тип CLR, по умолчанию используемый для сопоставления c реляционным конструктором объектов и программой SQLMetal|  
|--------------------|---------------------------------------------------------------------------------------------------------------------|  
|`CHAR`|<xref:System.String?displayProperty=fullName>|  
|`NCHAR`|<xref:System.String?displayProperty=fullName>|  
|`VARCHAR`|<xref:System.String?displayProperty=fullName>|  
|`NVARCHAR`|<xref:System.String?displayProperty=fullName>|  
|`TEXT`|<xref:System.String?displayProperty=fullName>|  
|`NTEXT`|<xref:System.String?displayProperty=fullName>|  
|`XML`|<xref:System.Xml.Linq.XElement?displayProperty=fullName>|  
  
 В следующей таблице показано сопоставление типов по умолчанию, используемое методом <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName> для определения типов столбцов SQL, которые должны создаваться в соответствии с типами CLR, определенными в модели объектов или во внешнем файле сопоставления.  
  
|Тип CLR|Тип SQL Server, по умолчанию используемый методом <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName>|  
|-------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Char?displayProperty=fullName>|`NCHAR(1)`|  
|<xref:System.String?displayProperty=fullName>|`NVARCHAR(4000)`|  
|<xref:System.Char?displayProperty=fullName>\[\]|`NVARCHAR(4000)`|  
|Пользовательский тип, реализующий методы `Parse()` и `ToString()`|`NVARCHAR(MAX)`|  
  
 Можно выбрать множество других текстовых сопоставлений и сопоставлений XML, но некоторые из них могут вызвать исключения переполнения или потери данных в процессе преобразования данных в базу или из базы данных.  Дополнительные сведения см. в разделе [Таблица правил сопоставления типов во время выполнения](#BehaviorMatrix).  
  
### Типы XML  
 Тип данных SQL Server `XML` доступен в версиях Microsoft SQL Server 2005 и выше.  Тип данных SQL Server `XML` может быть сопоставлен с <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XDocument> или <xref:System.String>.  Если в столбце хранятся XML\-фрагменты, которые невозможно считать в объект <xref:System.Xml.Linq.XElement>, то столбец необходимо сопоставить с типом <xref:System.String>, чтобы избежать ошибок времени выполнения.  К XML\-фрагментам, для которых необходимо сопоставление с типом <xref:System.String>, относятся следующие:  
  
-   последовательность XML\-элементов;  
  
-   Атрибуты  
  
-   общие идентификаторы;  
  
-   Комментарии  
  
 Типы <xref:System.Xml.Linq.XElement> и <xref:System.Xml.Linq.XDocument> можно сопоставить с типами SQL Server, как показано в разделе [Таблица правил сопоставления типов во время выполнения](#BehaviorMatrix), однако в методе <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName> для этих типов отсутствует сопоставление типов SQL Server по умолчанию.  
  
### Пользовательские типы  
 Если класс реализует методы `Parse()` и `ToString()`, то объект этого класса можно сопоставить с любым текстовым типом SQL \(`CHAR`, `NCHAR`, `VARCHAR`, `NVARCHAR`, `TEXT`, `NTEXT`, `XML`\).  Объект сохраняется в базе данных путем передачи значения, возвращаемого методом `ToString()`, в сопоставленный столбец базы данных.  Объект воссоздается при вызове метода `Parse()` со строкой, возвращаемой из базы данных.  
  
> [!NOTE]
>  LINQ to SQL не поддерживает сериализацию, выполняемую с помощью <xref:System.Xml.Serialization.IXmlSerializable?displayProperty=fullName>.  
  
<a name="DateMapping"></a>   
## Сопоставление даты и времени  
 В LINQ to SQL можно сопоставлять многие типы даты и времени SQL Server.  В следующей таблице показаны типы CLR, которые выбираются реляционным конструктором объектов и программой SQLMetal при создании сопоставления модели объектов или внешнего файла сопоставления, основанного на базе данных.  
  
|Тип SQL Server|Тип CLR, по умолчанию используемый для сопоставления c реляционным конструктором объектов и программой SQLMetal|  
|--------------------|---------------------------------------------------------------------------------------------------------------------|  
|`SMALLDATETIME`|<xref:System.DateTime?displayProperty=fullName>|  
|`DATETIME`|<xref:System.DateTime?displayProperty=fullName>|  
|`DATETIME2`|<xref:System.DateTime?displayProperty=fullName>|  
|`DATETIMEOFFSET`|<xref:System.DateTimeOffset?displayProperty=fullName>|  
|`DATE`|<xref:System.DateTime?displayProperty=fullName>|  
|`TIME`|<xref:System.TimeSpan?displayProperty=fullName>|  
  
 В следующей таблице показано сопоставление типов по умолчанию, используемое методом <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName> для определения типов столбцов SQL, которые должны создаваться в соответствии с типами CLR, определенными в модели объектов или во внешнем файле сопоставления.  
  
|Тип CLR|Тип SQL Server, по умолчанию используемый методом <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName>|  
|-------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.DateTime?displayProperty=fullName>|`DATETIME`|  
|<xref:System.DateTimeOffset?displayProperty=fullName>|`DATETIMEOFFSET`|  
|<xref:System.TimeSpan?displayProperty=fullName>|`TIME`|  
  
 Можно выбрать другие сопоставления даты и времени, но некоторые из них могут вызвать исключения переполнения или потери данных в процессе преобразования данных в базу данных или из базы данных.  Дополнительные сведения см. в разделе [Таблица правил сопоставления типов во время выполнения](#BehaviorMatrix).  
  
> [!NOTE]
>  Типы данных SQL Server `DATETIME2`, `DATETIMEOFFSET`, `DATE` и `TIME` доступны в версиях Microsoft SQL Server 2008 и выше.  LINQ to SQL поддерживает сопоставление с этими новыми типами, начиная с версии платформы .NET Framework 3.5 с пакетом обновления 1 \(SP1\).  
  
### System.Datetime  
 Диапазон и точность типа CLR <xref:System.DateTime?displayProperty=fullName> превышают диапазон и точность типа SQL Server `DATETIME`, с которым по умолчанию выполняется сопоставление в методе <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName>.  Чтобы избежать исключений, связанных с датами вне диапазона `DATETIME`, используйте тип `DATETIME2`, который доступен, начиная с версии Microsoft SQL Server 2008.  Тип `DATETIME2` способен обеспечить соответствие параметров диапазона и точности с типом CLR <xref:System.DateTime?displayProperty=fullName>.  
  
 В датах SQL Server не учитывается часовой пояс \(<xref:System.TimeZone>\), который имеет широкую поддержку в среде CLR.  Значения <xref:System.TimeZone> сохраняются в базе данных без изменений и без преобразования <xref:System.TimeZone>, независимо от исходных данных <xref:System.DateTimeKind>.  Когда значения <xref:System.DateTime> получаются из базы данных, они загружаются в <xref:System.DateTime> без изменений, а <xref:System.DateTimeKind> получает значение <xref:System.DateTimeKind>.  Дополнительные сведения о поддерживаемых методах <xref:System.DateTime?displayProperty=fullName> см. в разделе [Методы System.DateTime](../../../../../../docs/framework/data/adonet/sql/linq/system-datetime-methods.md).  
  
### System.TimeSpan  
 Microsoft SQL Server 2008 и платформа .NET Framework 3.5 с пакетом обновления 1 \(SP1\) позволяют сопоставлять тип CLR <xref:System.TimeSpan?displayProperty=fullName> с типом SQL Server `TIME`.  Однако между типом CLR <xref:System.TimeSpan?displayProperty=fullName> и типом SQL Server `TIME` существует большая разница в поддерживаемом диапазоне.  Сопоставление значений \(меньше 0 или больше 23:59:59.9999999 часов\) с типом SQL `TIME` вызовет исключение переполнения.  Дополнительные сведения см. в разделе [Методы System.TimeSpan](../../../../../../docs/framework/data/adonet/sql/linq/system-timespan-methods.md).  
  
 В Microsoft SQL Server 2000 и SQL Server 2005 нельзя сопоставлять поля базы данных с типом <xref:System.TimeSpan>.  При этом операции с типом <xref:System.TimeSpan> поддерживаются, поскольку значения <xref:System.TimeSpan> могут возвращаться операцией вычитания <xref:System.DateTime> или входить в выражение в виде литерала или привязанной переменной.  
  
<a name="BinaryMapping"></a>   
## Сопоставление двоичных объектов  
 Для многих типов SQL Server возможно сопоставление с типом CLR <xref:System.Data.Linq.Binary?displayProperty=fullName>.  В следующей таблице показаны типы SQL Server, для которых реляционный конструктор объектов и программа SQLMetal определяют тип CLR <xref:System.Data.Linq.Binary?displayProperty=fullName> во время построения модели объектов или внешнего файла сопоставления, основанного на базе данных.  
  
|Тип SQL Server|Тип CLR, по умолчанию используемый для сопоставления c реляционным конструктором объектов и программой SQLMetal|  
|--------------------|---------------------------------------------------------------------------------------------------------------------|  
|`BINARY(50)`|<xref:System.Data.Linq.Binary?displayProperty=fullName>|  
|`VARBINARY(50)`|<xref:System.Data.Linq.Binary?displayProperty=fullName>|  
|`VARBINARY(MAX)`|<xref:System.Data.Linq.Binary?displayProperty=fullName>|  
|`VARBINARY(MAX)`  с атрибутом `FILESTREAM`|<xref:System.Data.Linq.Binary?displayProperty=fullName>|  
|`IMAGE`|<xref:System.Data.Linq.Binary?displayProperty=fullName>|  
|`TIMESTAMP`|<xref:System.Data.Linq.Binary?displayProperty=fullName>|  
  
 В следующей таблице показано сопоставление типов по умолчанию, используемое методом <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName> для определения типов столбцов SQL, которые должны создаваться в соответствии с типами CLR, определенными в модели объектов или во внешнем файле сопоставления.  
  
|Тип CLR|Тип SQL Server, по умолчанию используемый методом <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName>|  
|-------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Data.Linq.Binary?displayProperty=fullName>|`VARBINARY(MAX)`|  
|<xref:System.Byte?displayProperty=fullName>|`VARBINARY(MAX)`|  
|<xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName>|`VARBINARY(MAX)`|  
  
 Можно выбрать другие сопоставления двоичных объектов, но некоторые из них могут вызвать исключения переполнения или потери данных в процессе преобразования данных в базу данных или из базы данных.  Дополнительные сведения см. в разделе [Таблица правил сопоставления типов во время выполнения](#BehaviorMatrix).  
  
### SQL Server FILESTREAM  
 Атрибут `FILESTREAM` для столбцов `VARBINARY(MAX)` доступен, начиная с версии Microsoft SQL Server 2008. Сопоставление с этим типом в LINQ to SQL поддерживается, начиная с версии платформы .NET Framework 3.5 с пакетом обновления 1 \(SP1\).  
  
 Столбцы `VARBINARY(MAX)` с атрибутом `FILESTREAM` можно сопоставлять с объектами <xref:System.Data.Linq.Binary>, но метод <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName> не может автоматически создавать столбцы с атрибутом `FILESTREAM`.  Дополнительные сведения о `FILESTREAM` см. в разделе [Общие сведения об атрибуте FILESTREAM](http://go.microsoft.com/fwlink/?LinkId=115291) электронной документации по SQL Server.  
  
<a name="BinarySerialization"></a>   
### Двоичная сериализация  
 Если в классе реализован интерфейс <xref:System.Runtime.Serialization.ISerializable>, объект этого класса можно сериализовать в любое двоичное поле SQL \(`BINARY`, `VARBINARY`, `IMAGE`\).  Сериализация и десериализация объекта выполняется в соответствии с реализацией интерфейса <xref:System.Runtime.Serialization.ISerializable>.  Дополнительные сведения см. в разделе [Двоичная сериализация](http://go.microsoft.com/fwlink/?LinkId=115581).  
  
<a name="MiscMapping"></a>   
## Прочие виды сопоставления  
 В следующей таблице показаны сопоставления по умолчанию для некоторых типов, не упомянутых ранее.  В следующей таблице показаны типы CLR, которые выбираются реляционным конструктором объектов и программой SQLMetal при создании сопоставления модели объектов или внешнего файла сопоставления, основанного на базе данных.  
  
|Тип SQL Server|Тип CLR, по умолчанию используемый для сопоставления c реляционным конструктором объектов и программой SQLMetal|  
|--------------------|---------------------------------------------------------------------------------------------------------------------|  
|`UNIQUEIDENTIFIER`|<xref:System.Guid?displayProperty=fullName>|  
|`SQL_VARIANT`|<xref:System.Object?displayProperty=fullName>|  
  
 В следующей таблице показано сопоставление типов по умолчанию, используемое методом <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName> для определения типов столбцов SQL, которые должны создаваться в соответствии с типами CLR, определенными в модели объектов или во внешнем файле сопоставления.  
  
|Тип CLR|Тип SQL Server, по умолчанию используемый методом <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName>|  
|-------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Guid?displayProperty=fullName>|`UNIQUEIDENTIFIER`|  
|<xref:System.Object?displayProperty=fullName>|`SQL_VARIANT`|  
  
 LINQ to SQL не поддерживает для этих типов никаких других сопоставлений.  Дополнительные сведения см. в разделе [Таблица правил сопоставления типов во время выполнения](#BehaviorMatrix).  
  
## См. также  
 [Сопоставление на основе атрибутов](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)   
 [Внешние сопоставления](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)   
 [Типы данных и функции](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)   
 [Несоответствия типов SQL\-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mismatches.md)