---
title: "Данные даты и времени | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6f5ff56a-a57e-49d7-8ae9-bbed697e42e3
caps.latest.revision: 7
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 7
---
# Данные даты и времени
В SQL Server 2008 появились указанные ниже новые типы данных для обработки сведений о дате и времени.  Новые типы данных включают отдельные типы для даты и времени, а также расширенные типы данных, обладающие большим диапазоном, большей точностью и учитывающие часовые пояса.  Начиная с .NET Framework 3.5 с пакетом обновления 1 \(SP1\), поставщик данных .NET Framework для SQL Server \(<xref:System.Data.SqlClient>\) полностью поддерживает все новые возможности ядра СУБД SQL Server 2008.  Для использования новых возможностей с SqlClient необходимо установить .NET Framework 3.5 с пакетом обновления 1 \(SP1\) или более поздней версии.  
  
 В версиях SQL Server ранее SQL Server 2008 было всего два типа данных для работы с датой и временем: `datetime` и `smalldatetime`.  Оба типа данных содержат как значение даты, так и значение времени, что затрудняет работу только со значениями даты или времени.  Кроме того, эти типы данных поддерживают только даты после введения григорианского календаря в Англии в 1753 г.  Другое ограничение заключается в том, что эти устаревшие типы данных не учитывают часовые пояса, что затрудняет работу с данными, поступившими из разных часовых поясов.  
  
 Полная документация по типам данных SQL Server доступна в электронной документации по SQL Server.  В приведенной ниже таблице перечислены разделы, посвященные дате и времени, для конкретных версий SQL Server.  
  
 **Электронная документация по SQL Server**  
  
1.  [Использование данных даты и времени](http://go.microsoft.com/fwlink/?LinkID=98361)  
  
## Типы данных даты и времени и только даты, появившиеся в SQL Server 2008  
 В приведенной ниже таблице описаны новые типы данных даты и времени.  
  
|Тип данных SQL Server|Описание|  
|---------------------------|--------------|  
|`date`|Тип данных `date` имеет диапазон от 1 января 01 года н. э. до 31 декабря 9999 года н. э. с точностью до дня.  Значение по умолчанию \- 1 января 1900 года.  Размер хранения составляет 3 байта.|  
|`time`|Тип данных `time` сохраняет только значения времени, основанные на 24\-часовом формате.  Тип данных `time` имеет диапазон от 00:00:00.0000000 до 23:59:59.9999999 с точностью 100 наносекунд.  Значение по умолчанию \- 00:00:00.0000000 \(полночь\).  Тип данных `time` поддерживает определяемую пользователем точность в долях секунды, а размер хранения изменяется от 3 до 6 байт в зависимости от указанной точности.|  
|`datetime2`|Тип данных `datetime2` объединяет диапазон и точность типов данных `date` и `time` в один тип данных.<br /><br /> Значения по умолчанию и форматы строковых литералов аналогичны значениям, определенным для типов данных `date` и `time`.|  
|`datetimeoffset`|Тип данных `datetimeoffset` обладает всеми характеристиками типа `datetime2` с добавлением смещения часового пояса.  Смещение часового пояса представлено в виде \[\+&#124;\-\] ЧЧ:ММ.  ЧЧ \- это 2 разряда от 00 до 14, представляющие количество часов в смещении часового пояса.  ММ \- это 2 разряда от 00 до 59, представляющие количество дополнительных минут в смещении часового пояса.  Форматы времени поддерживаются с точностью до 100 наносекунд.  Обязательный знак «\+» или «\-» указывает, нужно ли прибавить смещение часового пояса ко времени в формате UTC \(универсальное время или время по Гринвичу\) или отнять его, чтобы получить местное время.|  
  
> [!NOTE]
>  Дополнительные сведения об использовании ключевого слова `Type System Version` см. в разделе <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.  
  
## Формат даты и порядок даты  
 Способ синтаксического разбора сервером SQL Server значений даты и времени зависит не только от версии системы типов и версии сервера, но также от установленных на сервере по умолчанию языковых параметров и параметров форматирования.  Строка даты, подходящая для форматов даты на одном языке, может не распознаваться, если запрос выполняется в подключении, в котором используется другой язык и другой формат даты.  
  
 Инструкция Transact\-SQL SET LANGUAGE неявным образом задает значение параметра DATEFORMAT, определяющего порядок компонентов даты.  Инструкцию Transact\-SQL SET DATEFORMAT можно использовать в подключении для устранения неоднозначности значений даты путем расположения компонентов даты в порядке МДГ, ДМГ, ГМД, ГДМ, МГД или ДГМ.  
  
 Если значение параметра DATEFORMAT для подключения не указано, SQL Server использует связанный с подключением язык по умолчанию.  Например, строка даты '01\/02\/03' будет интерпретирована как МДГ \(2 января 2003 г.\), если на сервере установлен английский язык \(США\), и как ДМГ \(1 февраля 2003 г.\), если на сервере установлен английский язык \(Великобритания\).  Год определяется по правилу отсечения двух цифр года SQL Server, которое определяет дату отсечения для выбора века.  Дополнительные сведения см. в разделе [Параметр отсечения двух цифр года](http://go.microsoft.com/fwlink/?LinkId=120473) электронной документации по SQL Server.  
  
> [!NOTE]
>  Формат даты ГДМ не поддерживается при преобразовании из строкового формата в формат `date`, `time`, `datetime2` или `datetimeoffset`.  
  
 Дополнительные сведения об интерпретации сервером SQL Server даты и времени см. в разделе [Использование данных даты и времени](http://go.microsoft.com/fwlink/?LinkID=98361) электронной документации по SQL Server 2008.  
  
## Параметры и типы данных даты\-времени  
 Можно указать тип данных <xref:System.Data.SqlClient.SqlParameter> с помощью одного из перечислений <xref:System.Data.SqlDbType>.  Для поддержки новых типов данных даты и времени к <xref:System.Data.SqlDbType> были добавлены следующие перечисления.  
  
-   `SqlDbType.Date`  
  
-   `SqlDbType.Time`  
  
-   `SqlDbType.DateTime2`  
  
-   `SqlDbType.DateTimeOffSet`  
  
 Также можно указать тип объекта <xref:System.Data.SqlClient.SqlParameter> в общей форме, задав для свойства <xref:System.Data.SqlClient.SqlParameter.DbType%2A> объекта `SqlParameter` особое значение перечисления <xref:System.Data.DbType>.  Для поддержки типов данных `datetime2` и `datetimeoffset` к свойству <xref:System.Data.DbType> были добавлены следующие значения перечисления.  
  
-   DbType.DateTime2  
  
-   DbType.DateTimeOffset  
  
 Новые перечисления дополняют перечисления `Date`, `Time` и `DateTime` из предыдущих версий .NET Framework.  
  
 Тип поставщика данных платформы .NET Framework объекта параметра выводится из значения типа платформы .NET Framework объекта параметра или из свойства `DbType` объекта параметра.  Для поддержки новых типов данных даты и времени не было представлено новых типов данных <xref:System.Data.SqlTypes>.  В следующей таблице описаны сопоставления между типами данных даты и времени SQL Server 2008 и типами данных CLR.  
  
|Тип данных SQL Server|Тип платформы .NET Framework|System.Data.SqlDbType|System.Data.DbType|  
|---------------------------|----------------------------------|---------------------------|------------------------|  
|date|System.DateTime|дата.|дата.|  
|время|System.TimeSpan|Время|Время|  
|datetime2|System.DateTime|DateTime2|DateTime2|  
|datetimeoffset|System.DateTimeOffset|DateTimeOffset|DateTimeOffset|  
|datetime|System.DateTime|DateTime|DateTime|  
|smalldatetime|System.DateTime|DateTime|DateTime|  
  
### Свойства SqlParameter  
 В приведенной ниже таблице описаны свойства `SqlParameter`, соответствующие типам данных даты и времени.  
  
|Свойство|Описание|  
|--------------|--------------|  
|<xref:System.Data.SqlClient.SqlParameter.IsNullable%2A>|Возвращает или задает значение, указывающее, можно ли использовать значения NULL.  При отправке на сервер параметра со значением NULL необходимо указывать значение <xref:System.DBNull>, а не значение `null` \(`Nothing` в Visual Basic\).  Дополнительные сведения о значении NULL базы данных см. в разделе [Обработка значений NULL](../../../../../docs/framework/data/adonet/sql/handling-null-values.md)|  
|<xref:System.Data.SqlClient.SqlParameter.Precision%2A>|Возвращает или задает максимальное количество разрядов, используемых для представления значения.  Этот параметр пропускается для типов данных даты и времени.|  
|<xref:System.Data.SqlClient.SqlParameter.Scale%2A>|Возвращает или задает число десятичных разрядов, до которых разрешается промежуток времени для `Time`, `DateTime2` `` и `DateTimeOffset`.  Значение по умолчанию — 0, означающее, что фактический масштаб выводится из значения и отправляется на сервер.|  
|<xref:System.Data.SqlClient.SqlParameter.Size%2A>|Пропускается для типов данных даты и времени.|  
|<xref:System.Data.SqlClient.SqlParameter.Value%2A>|Возвращает или задает значение параметра.|  
|<xref:System.Data.SqlClient.SqlParameter.SqlValue%2A>|Возвращает или задает значение параметра.|  
  
> [!NOTE]
>  Значения времени, меньшие нуля или большие либо равные 24 часам, приводят к вызову исключения <xref:System.ArgumentException>.  
  
### Создание параметров  
 Объект <xref:System.Data.SqlClient.SqlParameter> можно создать с помощью конструктора либо путем добавления этого объекта в коллекцию <xref:System.Data.SqlClient.SqlCommand> <xref:System.Data.SqlClient.SqlCommand.Parameters%2A> путем вызова метода `Add` класса <xref:System.Data.SqlClient.SqlParameterCollection>.  Метод `Add` принимает в качестве входных данных либо аргументы конструктора, либо существующий объект параметра.  
  
 В следующих подразделах данного раздела приведены примеры указания параметров даты и времени.  Дополнительные примеры по работе с параметрами см. в разделах [Настройка параметров и типы данных параметров](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md) и [Параметры DataAdapter](../../../../../docs/framework/data/adonet/dataadapter-parameters.md).  
  
### Пример работы с типом date  
 В нижеприведенном примере кода показано указание параметра `date`.  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@Date";  
parameter.SqlDbType = SqlDbType.Date;  
parameter.Value = "2007/12/1";  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@Date"  
parameter.SqlDbType = SqlDbType.Date  
parameter.Value = "2007/12/1"  
```  
  
### Пример работы с типом time  
 В нижеприведенном примере кода показано указание параметра `time`.  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@time";  
parameter.SqlDbType = SqlDbType.Time;  
parameter.Value = DateTime.Parse("23:59:59").TimeOfDay;  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@Time"  
parameter.SqlDbType = SqlDbType.Time  
parameter.Value = DateTime.Parse("23:59:59").TimeOfDay;  
```  
  
### Пример работы с типом Datetime2  
 В приведенном ниже примере кода демонстрируется указание параметра `datetime2`, содержащего компоненты даты и времени.  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@Datetime2";  
parameter.SqlDbType = SqlDbType.DateTime2;  
parameter.Value = DateTime.Parse("1666-09-02 1:00:00");  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@Datetime2"  
parameter.SqlDbType = SqlDbType.DateTime2  
parameter.Value = DateTime.Parse("1666-09-02 1:00:00");  
```  
  
### Пример работы с типом DateTimeOffSet  
 В приведенном ниже примере кода демонстрируется указание параметра `DateTimeOffSet`, содержащего дату, время и смещение часового пояса, равное 0.  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@DateTimeOffSet";  
parameter.SqlDbType = SqlDbType.DateTimeOffSet;  
parameter.Value = DateTimeOffset.Parse("1666-09-02 1:00:00+0");  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@DateTimeOffSet"  
parameter.SqlDbType = SqlDbType.DateTimeOffSet  
parameter.Value = DateTimeOffset.Parse("1666-09-02 1:00:00+0");  
```  
  
### Метод AddWithValue  
 Указать параметры также можно с помощью метода `AddWithValue` класса <xref:System.Data.SqlClient.SqlCommand>, как показано в приведенном ниже фрагменте кода.  Однако метод `AddWithValue` не позволяет указать для параметра значения свойств <xref:System.Data.SqlClient.SqlParameter.DbType%2A> и <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A>.  
  
```csharp  
command.Parameters.AddWithValue(   
    "@date", DateTimeOffset.Parse("16660902"));  
```  
  
```vb  
command.Parameters.AddWithValue( _  
    "@date", DateTimeOffset.Parse("16660902"))  
```  
  
 Параметр `@date` можно сопоставить типу данных `date`, `datetime` или `datetime2` на сервере.  При работе с новыми типами данных `datetime` необходимо явным образом присвоить свойству <xref:System.Data.SqlDbType> параметра тип данных экземпляра.  Использование <xref:System.Data.SqlDbType> или неявных значений параметра может привести к проблемам с обратной совместимостью для типов данных `datetime` и `smalldatetime`.  
  
 В приведенной ниже таблице показано, какие типы `SqlDbTypes` выводятся из каких типов среды CLR.  
  
|Тип CLR|Выводимый тип SqlDbType|  
|-------------|-----------------------------|  
|DateTime|SqlDbType.DateTime|  
|TimeSpan|SqlDbType.Time|  
|DateTimeOffset|SqlDbType.DateTimeOffset|  
  
## Извлечение данных даты и времени  
 В следующей таблице описаны методы, используемые для извлечения значений даты и времени SQL Server 2008.  
  
|Метод SqlClient|Описание|  
|---------------------|--------------|  
|<xref:System.Data.SqlClient.SqlDataReader.GetDateTime%2A>|Возвращает значение указанного столбца в виде структуры <xref:System.DateTime>.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetDateTimeOffset%2A>|Возвращает значение указанного столбца в виде структуры <xref:System.DateTimeOffset>.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificFieldType%2A>|Возвращает базовый тип поля, зависящий от поставщика.  Возвращает те же типы, что и метод `GetFieldType` для новых типов даты и времени.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValue%2A>|Возвращает значение указанного столбца.  Возвращает те же типы, что и `GetValue` для новых типов даты и времени.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValues%2A>|Извлекает значения из указанного массива.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlString%2A>|Возвращает значение столбца в виде <xref:System.Data.SqlTypes.SqlString>.  Если данные нельзя выразить в виде объекта `SqlString`, возникнет исключение <xref:System.InvalidCastException>.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A>|Возвращает данные столбца в качестве значений по умолчанию `SqlDbType`.  Возвращает те же типы, что и `GetValue` для новых типов даты и времени.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlValues%2A>|Извлекает значения из указанного массива.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetString%2A>|Возвращает значение столбца в виде строки, если Type System Version имеет значение «SQL Server 2005».  Если данные нельзя представить в виде строки, то возникнет исключение <xref:System.InvalidCastException>.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetTimeSpan%2A>|Возвращает значение указанного столбца в виде структуры <xref:System.Timespan>.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetValue%2A>|Возвращает значение указанного столбца в виде базового типа CLR.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetValues%2A>|Возвращает значения столбца в массив.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>|Возвращает объект <xref:System.Data.DataTable>, описывающий метаданные результирующего набора.|  
  
> [!NOTE]
>  Новые типы даты и времени `SqlDbTypes` не поддерживаются для кода, выполняющегося в SQL Server внутри процесса.  При передаче на сервер одного из этих типов возникает исключение.  
  
## Указание значений даты и времени в виде литералов  
 Типы данных даты и времени можно указать с помощью множества различных форматов строк литералов, которые SQL Server затем оценивает во время выполнения, преобразуя их во внутренние структуры даты и времени.  SQL Server распознает данные даты и времени, заключенные в апострофы \('\).  В приведенных ниже примерах демонстрируются некоторые форматы.  
  
-   Алфавитные форматы даты, например `'October 15, 2006'`.  
  
-   Численные форматы даты, например `'10/15/2006'`.  
  
-   Строковые форматы без разделителей, например строка `'20061015'`, которую можно интерпретировать как 15 октября 2006 г. при использовании стандартного формата даты ISO.  
  
> [!NOTE]
>  Полную документацию по всем литеральным строковым форматам и другим возможностям типов данных даты и времени можно найти в электронной документации по SQL Server.  
  
 Значения времени, меньшие нуля или большие либо равные 24 часам, приводят к вызову исключения <xref:System.ArgumentException>.  
  
## Ресурсы электронной документации по SQL Server 2008  
 Дополнительные сведения о работе со значениями даты и времени в SQL Server 2008 см. в приведенных ниже ресурсах электронной документации по SQL Server 2008.  
  
|Раздел|Описание|  
|------------|--------------|  
|[Типы данных и функции даты и времени \(Transact\-SQL\)](http://go.microsoft.com/fwlink/?LinkID=98360)|Приводятся общие сведения обо всех типах данных и функциях даты и времени в языке Transact\-SQL.|  
|[Использование данных даты и времени](http://go.microsoft.com/fwlink/?LinkId=98361)|Приводятся сведения о типах данных даты и времени, функциях для работы с этими типами данных и примеры их использования.|  
|[Типы данных \(Transact\-SQL\)](http://go.microsoft.com/fwlink/?LinkId=98362)|Описываются системные типы данных в SQL Server 2008.|  
  
## См. также  
 [Сопоставления типов данных SQL Server](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)   
 [Настройка параметров и типы данных параметров](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)   
 [Типы данных SQL Server и ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)