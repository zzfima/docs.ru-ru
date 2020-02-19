---
title: Данные даты и времени
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6f5ff56a-a57e-49d7-8ae9-bbed697e42e3
ms.openlocfilehash: bdcbaffe1be4933b89c7bf0d3a11e1bb871bc2bd
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77450302"
---
# <a name="date-and-time-data"></a>Данные даты и времени
В SQL Server 2008 появились указанные ниже новые типы данных для обработки сведений о дате и времени. Новые типы данных включают отдельные типы для даты и времени, а также расширенные типы данных, обладающие большим диапазоном, большей точностью и учитывающие часовые пояса. Начиная с .NET Framework 3.5 с пакетом обновления 1 (SP1), поставщик данных .NET Framework для SQL Server (<xref:System.Data.SqlClient>) полностью поддерживает все новые возможности ядра СУБД SQL Server 2008. Для использования новых возможностей с SqlClient необходимо установить .NET Framework 3.5 с пакетом обновления 1 (SP1) или более поздней версии.  
  
 В версиях SQL Server, выпущенных до SQL Server 2008, было только два типа данных для работы с датами и временем: `datetime` и `smalldatetime`. Оба типа данных содержат как значение даты, так и значение времени, затрудняя работу только со значениями даты или времени. Кроме того, эти типы данных поддерживают только даты после введения григорианского календаря в Англии в 1753 г. Другое ограничение заключается в том, что эти устаревшие типы данных не учитывают часовые пояса, что затрудняет работу с данными, поступившими из разных часовых поясов.  
  
 Полная документация по типам данных SQL Server доступна в электронной документации по SQL Server. В приведенной ниже таблице перечислены разделы, посвященные дате и времени, для конкретных версий SQL Server.  
  
 **Документация по SQL Server**  
  
1. [Использование данных даты и времени](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))  
  
## <a name="datetime-data-types-introduced-in-sql-server-2008"></a>Типы данных даты и времени и только даты, появившиеся в SQL Server 2008  
 В приведенной ниже таблице описаны новые типы данных даты и времени.  
  
|Тип данных SQL Server|Description|  
|--------------------------|-----------------|  
|`date`|Тип данных `date` имеет диапазон от 1 января 01 года до 31 декабря 9999 года с точностью до дня. Значение по умолчанию - 1 января 1900 года. Размер при хранении составляет 3 байта.|  
|`time`|Тип данных `time` сохраняет только значения времени, основанные на 24-часовом формате. Тип данных `time` имеет диапазон от 00:00:00.0000000 до 23:59:59.9999999 с точностью 100 наносекунд. Значение по умолчанию - 00:00:00.0000000 (полночь). Тип данных `time` поддерживает определяемую пользователем точность в долях секунды, и размер хранения изменяется от 3 до 6 байт в зависимости от указанной точности.|  
|`datetime2`|Тип данных `datetime2` объединяет диапазон и точность типов данных `date` и `time` в один тип данных.<br /><br /> Значения по умолчанию и форматы строковых литералов аналогичны значениям, определенным для типов данных `date` и `time`.|  
|`datetimeoffset`|Тип данных `datetimeoffset` обладает всеми характеристиками типа `datetime2` с добавлением смещения часового пояса. Смещение часового пояса представлено в виде [+&#124;-] ЧЧ:ММ. ЧЧ — двузначное число от 00 до 14, представляющее количество часов в смещении часового пояса. Обозначение ММ состоит из двух цифр, представляющих дополнительное смещение часового пояса в минутах, и принимает значения от 00 до 59. Форматы времени поддерживаются с точностью до 100 наносекунд. Обязательный знак «+» или «-» указывает, нужно ли прибавить смещение часового пояса ко времени в формате UTC (универсальное время или время по Гринвичу) или отнять его, чтобы получить местное время.|  
  
> [!NOTE]
> Дополнительные сведения об использовании `Type System Version` см. в разделе <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.  
  
## <a name="date-format-and-date-order"></a>Формат даты и порядок даты  
 Способ синтаксического разбора сервером SQL Server значений даты и времени зависит не только от версии системы типов и версии сервера, но также от установленных на сервере по умолчанию языковых параметров и параметров форматирования. Строка даты, подходящая для форматов даты на одном языке, может не распознаваться, если запрос выполняется в подключении, в котором используется другой язык и другой формат даты.  
  
 Инструкция Transact-SQL SET LANGUAGE неявным образом задает значение параметра DATEFORMAT, определяющего порядок компонентов даты. Инструкцию Transact-SQL SET DATEFORMAT можно использовать в подключении для устранения неоднозначности значений даты путем расположения компонентов даты в порядке МДГ, ДМГ, ГМД, ГДМ, МГД или ДГМ.  
  
 Если значение параметра DATEFORMAT для подключения не указано, SQL Server использует связанный с подключением язык по умолчанию. Например, строка даты '01/02/03' будет интерпретирована как МДГ (2 января 2003 г.), если на сервере установлен английский язык (США), и как ДМГ (1 февраля 2003 г.), если на сервере установлен английский язык (Великобритания). Год определяется по правилу отсечения двух цифр года SQL Server, которое определяет дату отсечения для выбора века. Дополнительные сведения см. в разделе [параметр "отсечение двух цифр года"](/sql/database-engine/configure-windows/configure-the-two-digit-year-cutoff-server-configuration-option).  
  
> [!NOTE]
> Формат даты ГДМ не поддерживается при преобразовании из строкового формата в формат `date`, `time`, `datetime2` или `datetimeoffset`.  
  
 Дополнительные сведения о том, как SQL Server интерпретирует данные даты и времени, см. [в разделе Использование данных даты и времени](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms180878(v=sql.100)).  
  
## <a name="datetime-data-types-and-parameters"></a>Параметры и типы данных даты-времени  
 Для поддержки новых типов данных даты и времени к <xref:System.Data.SqlDbType> были добавлены следующие перечисления.  
  
- `SqlDbType.Date`  
  
- `SqlDbType.Time`  
  
- `SqlDbType.DateTime2`  
  
- `SqlDbType.DateTimeOffSet`  

Можно указать тип данных <xref:System.Data.SqlClient.SqlParameter> с помощью одного из предшествующих перечислений <xref:System.Data.SqlDbType>. 

> [!NOTE]
> Невозможно задать для свойства `DbType` `SqlParameter` значение `SqlDbType.Date`.

 Также можно указать тип объекта <xref:System.Data.SqlClient.SqlParameter> в общей форме, задав для свойства <xref:System.Data.SqlClient.SqlParameter.DbType%2A> объекта `SqlParameter` особое значение перечисления <xref:System.Data.DbType>. Для поддержки типов данных <xref:System.Data.DbType> и `datetime2` к свойству `datetimeoffset` были добавлены следующие значения перечисления.  
  
- DbType.DateTime2  
  
- DbType.DateTimeOffset  
  
 Новые перечисления дополняют перечисления `Date`, `Time` и `DateTime` из предыдущих версий .NET Framework.  
  
 Тип поставщика данных платформы .NET Framework объекта параметра выводится из значения типа платформы .NET Framework объекта параметра или из свойства `DbType` объекта параметра. Для поддержки новых типов данных даты и времени не было представлено новых типов данных <xref:System.Data.SqlTypes>. В следующей таблице описаны сопоставления между типами данных даты и времени SQL Server 2008 и типами данных CLR.  
  
|Тип данных SQL Server|Тип .NET Framework|System.Data.SqlDbType|System.Data.DbType|  
|--------------------------|-------------------------|---------------------------|------------------------|  
|Дата|System.DateTime|Дата|Дата|  
|time|System.TimeSpan|Time|Time|  
|datetime2|System.DateTime|datetime2|datetime2|  
|datetimeoffset|System.DateTimeOffset|DateTimeOffset|DateTimeOffset|  
|DATETIME|System.DateTime|Дата и время|Дата и время|  
|smalldatetime|System.DateTime|Дата и время|Дата и время|  
  
### <a name="sqlparameter-properties"></a>Свойства SqlParameter  
 В приведенной ниже таблице описаны свойства `SqlParameter`, соответствующие типам данных даты и времени.  
  
|Свойство|Description|  
|--------------|-----------------|  
|<xref:System.Data.SqlClient.SqlParameter.IsNullable%2A>|Возвращает или задает значение, указывающее, можно ли использовать значения NULL. При отправке на сервер параметра со значением NULL необходимо указывать значение <xref:System.DBNull>, а не значение `null` (`Nothing` в Visual Basic). Дополнительные сведения о значении NULL базы данных см. в разделе [Handling Null Values](handling-null-values.md).|  
|<xref:System.Data.SqlClient.SqlParameter.Precision%2A>|Возвращает или задает максимальное количество цифр, используемых для представления значения. Этот параметр пропускается для типов данных даты и времени.|  
|<xref:System.Data.SqlClient.SqlParameter.Scale%2A>|Возвращает или задает число десятичных разрядов, до которых разрешается промежуток времени для `Time`, `DateTime2` и `DateTimeOffset`. Значение по умолчанию — 0, означающее, что фактический масштаб выводится из значения и отправляется на сервер.|  
|<xref:System.Data.SqlClient.SqlParameter.Size%2A>|Пропускается для типов данных даты и времени.|  
|<xref:System.Data.SqlClient.SqlParameter.Value%2A>|Возвращает или задает значение параметра.|  
|<xref:System.Data.SqlClient.SqlParameter.SqlValue%2A>|Возвращает или задает значение параметра.|  
  
> [!NOTE]
> Значения времени, меньшие нуля или большие либо равные 24 часам, приводят к вызову исключения <xref:System.ArgumentException>.  
  
### <a name="creating-parameters"></a>Создание параметров  
 Объект <xref:System.Data.SqlClient.SqlParameter> можно создать с помощью конструктора либо путем добавления этого объекта в коллекцию <xref:System.Data.SqlClient.SqlCommand><xref:System.Data.SqlClient.SqlCommand.Parameters%2A> путем вызова метода `Add` класса <xref:System.Data.SqlClient.SqlParameterCollection>. Метод `Add` принимает в качестве входных данных либо аргументы конструктора, либо существующий объект параметра.  
  
 В следующих подразделах данного раздела приведены примеры указания параметров даты и времени. Дополнительные примеры работы с параметрами см. в разделе [Настройка параметров и типов данных](../configuring-parameters-and-parameter-data-types.md) параметров и [параметров DataAdapter](../dataadapter-parameters.md).  
  
### <a name="date-example"></a>Пример работы с типом date  
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
  
### <a name="time-example"></a>Пример работы с типом time  
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
  
### <a name="datetime2-example"></a>Пример работы с типом Datetime2  
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
  
### <a name="datetimeoffset-example"></a>Пример работы с типом DateTimeOffSet  
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
  
### <a name="addwithvalue"></a>Метод AddWithValue  
 Указать параметры также можно с помощью метода `AddWithValue` класса <xref:System.Data.SqlClient.SqlCommand>, как показано в приведенном ниже фрагменте кода. Однако метод `AddWithValue` не позволяет указать для параметра значения свойств <xref:System.Data.SqlClient.SqlParameter.DbType%2A> и <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A>.  
  
```csharp  
command.Parameters.AddWithValue(   
    "@date", DateTimeOffset.Parse("16660902"));  
```  
  
```vb  
command.Parameters.AddWithValue( _  
    "@date", DateTimeOffset.Parse("16660902"))  
```  
  
 Параметр `@date` можно сопоставить типу данных `date`, `datetime` или `datetime2` на сервере. При работе с новыми типами данных `datetime` необходимо явным образом присвоить свойству <xref:System.Data.SqlDbType> параметра тип данных экземпляра. Использование <xref:System.Data.SqlDbType.Variant> или неявных значений параметра может привести к проблемам с обратной совместимостью для типов данных `datetime` и `smalldatetime`.  
  
 В приведенной ниже таблице показано, какие типы `SqlDbTypes` выводятся из каких типов среды CLR.  
  
|Тип среды CLR|Выводимый тип SqlDbType|  
|--------------|------------------------|  
|Дата и время|SqlDbType.DateTime|  
|TimeSpan|SqlDbType.Time|  
|DateTimeOffset|SqlDbType.DateTimeOffset|  
  
## <a name="retrieving-date-and-time-data"></a>Извлечение данных даты и времени  
 В следующей таблице описаны методы, используемые для получения значений даты и времени SQL Server 2008.  
  
|Метод SqlClient|Description|  
|----------------------|-----------------|  
|<xref:System.Data.SqlClient.SqlDataReader.GetDateTime%2A>|Извлекает значение указанного столбца в виде структуры <xref:System.DateTime>.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetDateTimeOffset%2A>|Извлекает значение указанного столбца в виде структуры <xref:System.DateTimeOffset>.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificFieldType%2A>|Возвращает базовый тип поля, зависящий от поставщика. Возвращает те же типы, что и метод `GetFieldType` для новых типов даты и времени.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValue%2A>|Возвращает значение указанного столбца. Возвращает те же типы, что и `GetValue` для новых типов даты и времени.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValues%2A>|Извлекает значения из указанного массива.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlString%2A>|Возвращает значение столбца в виде <xref:System.Data.SqlTypes.SqlString>. Если данные нельзя выразить в виде объекта <xref:System.InvalidCastException>, возникнет исключение `SqlString`.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A>|Возвращает данные столбца в качестве значений по умолчанию `SqlDbType`. Возвращает те же типы, что и `GetValue` для новых типов даты и времени.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlValues%2A>|Извлекает значения из указанного массива.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetString%2A>|Возвращает значение столбца в виде строки, если Type System Version имеет значение SQL Server 2005. Если данные нельзя представить в виде строки, то возникнет исключение <xref:System.InvalidCastException>.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetTimeSpan%2A>|Извлекает значение указанного столбца в виде структуры <xref:System.TimeSpan>.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetValue%2A>|Возвращает значение указанного столбца в виде базового типа CLR.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetValues%2A>|Возвращает значения столбца в массив.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>|Возвращает объект <xref:System.Data.DataTable>, описывающий метаданные результирующего набора.|  
  
> [!NOTE]
> Новые типы даты и времени `SqlDbTypes` не поддерживаются для кода, выполняющегося в SQL Server внутри процесса. При передаче на сервер одного из этих типов возникает исключение.  
  
## <a name="specifying-date-and-time-values-as-literals"></a>Указание значений даты и времени в виде литералов  
 Типы данных даты и времени можно указать с помощью множества различных форматов строк литералов, которые SQL Server затем оценивает во время выполнения, преобразуя их во внутренние структуры даты и времени. SQL Server распознает данные даты и времени, заключенные в апострофы ('). В приведенных ниже примерах демонстрируются некоторые форматы.  
  
- Алфавитные форматы даты, например `'October 15, 2006'`.  
  
- Численные форматы даты, например `'10/15/2006'`.  
  
- Строковые форматы без разделителей, например строка `'20061015'`, которую можно интерпретировать как 15 октября 2006 г. при использовании стандартного формата даты ISO.  
  
> [!NOTE]
> Полную документацию по всем литеральным строковым форматам и другим возможностям типов данных даты и времени можно найти в электронной документации по SQL Server.  
  
 Значения времени, меньшие нуля или большие либо равные 24 часам, приводят к вызову исключения <xref:System.ArgumentException>.  
  
## <a name="resources-in-sql-server-books-online"></a>Ресурсы электронной документации по SQL Server  
 Дополнительные сведения о работе со значениями даты и времени в SQL Server см. в следующих ресурсах в электронная документация на SQL Server.  
  
|Раздел|Description|  
|-----------|-----------------|  
|[Типы данных и функции даты и времени (Transact-SQL)](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql)|Приводятся общие сведения обо всех типах данных и функциях даты и времени в языке Transact-SQL.|  
|[Использование данных даты и времени](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))|Приводятся сведения и даются примеры использования функций и типов данных даты и времени.|  
|[Типы данных (Transact-SQL)](/sql/t-sql/data-types/data-types-transact-sql)|Описывает системные типы данных в SQL Server.|  
  
## <a name="see-also"></a>См. также раздел

- [Сопоставления типов данных SQL Server](../sql-server-data-type-mappings.md)
- [Настройка параметров и типы данных параметров](../configuring-parameters-and-parameter-data-types.md)
- [Типы данных SQL Server и ADO.NET](sql-server-data-types.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
