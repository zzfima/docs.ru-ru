---
title: Изменение данных с большой стоимостью (макс)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8aca5f00-d80e-4320-81b3-016d0466f7ee
ms.openlocfilehash: 00a4ae83270bb74e9703faebfc93e26b5c069478
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174281"
---
# <a name="modifying-large-value-max-data-in-adonet"></a>Изменение данных больших объемов (max) в ADO.NET
Типы данных LOB — это данные, размер которых превышает максимальный размер строки в 8 килобайт (КБ). SQL Server представляет описатель `max` для типов данных `varchar`, `nvarchar` и `varbinary`, позволяющий сохранять значения размером до 2^32 байт. В столбцах таблицы и переменных Transact-SQL может быть указан тип данных `varchar(max)`, `nvarchar(max)` или `varbinary(max)`. В ADO.NET типы данных `max` можно выбрать с помощью объекта `DataReader`, а также их можно задавать в качестве значений входных и выходных параметров без какой-либо специальной обработки. В случае типов больших значений `varchar` данные могут извлекаться и обновляться постепенно.  
  
 Типы данных `max` можно использовать для сравнения как переменные языка Transact-SQL, а также для объединения. Кроме того, их можно использовать в предложениях DISTINCT, ORDER BY и GROUP BY инструкции SELECT, а также в агрегатах, объединениях и вложенных запросах.  
  
 В приведенной ниже таблице указаны ссылки на разделы электронной документации по SQL Server.  
  
 **Документация сервера S'L**  
  
1. [Использование типов данных большого размера](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms178158(v=sql.100))  
  
## <a name="large-value-type-restrictions"></a>Ограничения для типов данных большого размера  
 Приведенные ниже ограничения применяются к типам данных `max`, которые не существуют для типов данных меньших значений.  
  
- `sql_variant` не может содержать тип данных больших значений `varchar`.  
  
- Столбцы с данными больших значений `varchar` нельзя указать в качестве ключевого столбца в индексе. Они разрешены в столбце, включенном в некластеризованный индекс.  
  
- Столбцы с данными больших значений `varchar` нельзя использовать в качестве ключевых столбцов секционирования.  
  
## <a name="working-with-large-value-types-in-transact-sql"></a>Работа с типами большого размера на языке Transact-SQL  
 Функция Transact-SQL `OPENROWSET` — это одноразовый метод подключения и получения доступа к удаленным данным. Включает все сведения о соединении, необходимые для доступа к удаленным данным источника данных OLE DB. Из предложения FROM запроса можно ссылаться на функцию `OPENROWSET` как на имя таблицы. Она также может быть использована в качестве целевой таблицы в инструкциях INSERT, UPDATE или DELETE. Это зависит от возможностей поставщика OLE DB.  
  
 Функция `OPENROWSET` содержит поставщик наборов строк `BULK`, который позволяет считывать данные напрямую из файла без загрузки в целевую таблицу. Это позволяет использовать функцию `OPENROWSET` в обычной инструкции INSERT SELECT.  
  
 С помощью аргументов параметра `OPENROWSET BULK` можно управлять началом и концом считывания данных, отладкой ошибок и способом представления полученных данных. Например, можно указать, что файл с данными будет считан как однострочный или как набор строк типа `varbinary`, `varchar` или `nvarchar` в один столбец. Полное описание синтаксиса и параметров см. в электронной документации на SQL Server.  
  
 Следующий пример вставляет фотографию в таблицу ProductPhoto в примере базы данных AdventureWorks. При использовании поставщика `BULK OPENROWSET` необходимо указывать именованный список столбцов, даже если значения не вставляются в каждый столбец. В этом случае первичный ключ определяется как столбец идентификаторов и может быть опущен в списке столбцов. Обратите внимание, что вам необходимо лишь указать имя корреляции (в данном случае ThumbnailPhoto) в конце инструкции `OPENROWSET`. Оно соотносится со столбцом в таблице `ProductPhoto`, в которую загружается файл.  
  
```sql  
INSERT Production.ProductPhoto (  
    ThumbnailPhoto,
    ThumbnailPhotoFilePath,
    LargePhoto,
    LargePhotoFilePath)  
SELECT ThumbnailPhoto.*, null, null, N'tricycle_pink.gif'  
FROM OPENROWSET
    (BULK 'c:\images\tricycle.jpg', SINGLE_BLOB) ThumbnailPhoto  
```  
  
## <a name="updating-data-using-update-write"></a>Обновление данных с помощью инструкций UPDATE .WRITE  
 В инструкции Transact-SQL UPDATE имеется новый синтаксис WRITE, используемый для изменения содержимого столбцов `varchar(max)`, `nvarchar(max)` или `varbinary(max)`. Он позволяет выполнять частичные обновления данных. Синтаксис UPDATE .WRITE указан здесь в сокращенной форме.  
  
 UPDATE  
  
 - * \<объект>*  
  
 SET  
  
 *- column_name* . WRITE *(выражение* @Offset @Length , , )  
  
 Метод WRITE указывает, что часть значения *column_name* будет изменена. Выражение является значением, которое будет скопировано в поле *column_name*. Аргумент `@Offset` является начальной точкой записи выражения, а аргумент `@Length` — длиной изменяемой секции в столбце.  
  
|Если|То|  
|--------|----------|  
|Для выражения задано значение NULL.|Аргумент `@Length` не обрабатывается, а значение в поле *column_name* усекается в соответствии с указанным аргументом `@Offset`.|  
|`@Offset` равно NULL|Операция обновления добавляет выражение в конец существующего значения *column_name*, и аргумент `@Length` не обрабатывается.|  
|Значение аргумента `@Offset` больше, чем длина значения аргумента column_name.|SQL Server возвращает ошибку.|  
|`@Length` равно NULL|Операция обновления удаляет все данные, начиная с позиции `@Offset` до конца значения `column_name`.|  
  
> [!NOTE]
> Ни `@Offset`, ни `@Length` не может быть отрицательным числом.  
  
## <a name="example"></a>Пример  
 Этот пример Transact-SQL обновляет частичное значение в DocumentSummary, столбце `nvarchar(max)` таблицы Document в базе данных AdventureWorks. Слово components заменяется словом features, при этом указывается новое слово, начальное смещение слова, заменяемого в исходном тексте, и число заменяемых символов (длина). Этот пример содержит инструкцию SELECT перед и после инструкции UPDATE для сравнения результатов.  
  
```sql
USE AdventureWorks;  
GO  
--View the existing value.  
SELECT DocumentSummary  
FROM Production.Document  
WHERE DocumentID = 3;  
GO  
-- The first sentence of the results will be:  
-- Reflectors are vital safety components of your bicycle.  
  
--Modify a single word in the DocumentSummary column  
UPDATE Production.Document  
SET DocumentSummary .WRITE (N'features',28,10)  
WHERE DocumentID = 3 ;  
GO
--View the modified value.  
SELECT DocumentSummary  
FROM Production.Document  
WHERE DocumentID = 3;  
GO  
-- The first sentence of the results will be:  
-- Reflectors are vital safety features of your bicycle.  
```  
  
## <a name="working-with-large-value-types-in-adonet"></a>Работа с типами данных большого размера в ADO.NET  
 В ADO.NET можно работать с типами больших значений, указав их в качестве параметров <xref:System.Data.SqlClient.SqlParameter> в <xref:System.Data.SqlClient.SqlDataReader> для возврата результирующего набора либо воспользовавшись объектом <xref:System.Data.SqlClient.SqlDataAdapter> для заполнения набора `DataSet`/`DataTable`. Обработка типов больших значений и связанных с ними типов данных меньших значений ничем не отличается.  
  
### <a name="using-getsqlbytes-to-retrieve-data"></a>Извлечение данных с помощью GetSqlBytes  
 Метод `GetSqlBytes` класса <xref:System.Data.SqlClient.SqlDataReader> можно использовать для извлечения содержимого столбца `varbinary(max)`. В приведенном ниже фрагменте кода предполагается наличие объекта <xref:System.Data.SqlClient.SqlCommand> с именем `cmd`, который выбирает данные `varbinary(max)` из таблицы, и объекта <xref:System.Data.SqlClient.SqlDataReader> с именем `reader`, который извлекает данные в качестве класса <xref:System.Data.SqlTypes.SqlBytes>.  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim bytes As SqlBytes = reader.GetSqlBytes(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
    {  
        SqlBytes bytes = reader.GetSqlBytes(0);  
    }  
```  
  
### <a name="using-getsqlchars-to-retrieve-data"></a>Использование метода GetSqlChars для получения данных  
 Метод `GetSqlChars` класса <xref:System.Data.SqlClient.SqlDataReader> можно использовать для извлечения содержимого столбца `varchar(max)` или `nvarchar(max)`. В приведенном ниже фрагменте кода предполагается наличие объекта <xref:System.Data.SqlClient.SqlCommand> с именем `cmd`, который выбирает данные `nvarchar(max)` из таблицы, и объекта <xref:System.Data.SqlClient.SqlDataReader> с именем `reader`, который извлекает данные.  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim buffer As SqlChars = reader.GetSqlChars(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
{  
    SqlChars buffer = reader.GetSqlChars(0);  
}  
```  
  
### <a name="using-getsqlbinary-to-retrieve-data"></a>Использование метода GetSqlBinary для получения данных  
 Метод `GetSqlBinary` класса <xref:System.Data.SqlClient.SqlDataReader> можно использовать для извлечения содержимого столбца `varbinary(max)`. В приведенном ниже фрагменте кода предполагается наличие объекта <xref:System.Data.SqlClient.SqlCommand> с именем `cmd`, который выбирает данные `varbinary(max)` из таблицы, и объекта <xref:System.Data.SqlClient.SqlDataReader> с именем `reader`, который извлекает данные в качестве потока <xref:System.Data.SqlTypes.SqlBinary>.  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim binaryStream As SqlBinary = reader.GetSqlBinary(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
    {  
        SqlBinary binaryStream = reader.GetSqlBinary(0);  
    }  
```  
  
### <a name="using-getbytes-to-retrieve-data"></a>Использование метода GetBytes для получения данных  
 Метод `GetBytes` класса <xref:System.Data.SqlClient.SqlDataReader> считывает поток байтов с указанного смещения столбца в массив байтов, начиная с указанного смещения массива. В приведенном ниже фрагменте кода предполагается наличие объекта <xref:System.Data.SqlClient.SqlDataReader> с именем `reader`, который извлекает байты в массив байтов. Обратите внимание, что в отличие от `GetSqlBytes` для метода `GetBytes` требуется размер для буфера массива.  
  
```vb  
While reader.Read()  
    Dim buffer(4000) As Byte  
    Dim byteCount As Integer = _  
    CInt(reader.GetBytes(1, 0, buffer, 0, 4000))  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
    byte[] buffer = new byte[4000];  
    long byteCount = reader.GetBytes(1, 0, buffer, 0, 4000);  
}  
```  
  
### <a name="using-getvalue-to-retrieve-data"></a>Использование метода GetValue для получения данных  
 Метод `GetValue` класса <xref:System.Data.SqlClient.SqlDataReader> считывает значение из указанного смещения столбца в массив. В приведенном ниже фрагменте кода предполагается наличие объекта <xref:System.Data.SqlClient.SqlDataReader> с именем `reader`, который извлекает двоичные данные из первого смещения столбца, а затем данные строки из второго смещения столбца.  
  
```vb  
While reader.Read()  
    ' Read the data from varbinary(max) column  
    Dim binaryData() As Byte = CByte(reader.GetValue(0))  
  
    ' Read the data from varchar(max) or nvarchar(max) column  
    Dim stringData() As String = Cstr((reader.GetValue(1))  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
    // Read the data from varbinary(max) column  
    byte[] binaryData = (byte[])reader.GetValue(0);  
  
    // Read the data from varchar(max) or nvarchar(max) column  
    String stringData = (String)reader.GetValue(1);  
}  
```  
  
## <a name="converting-from-large-value-types-to-clr-types"></a>Преобразование типов больших значений в типы CLR  
 Вы можете преобразовать содержимое столбца `varchar(max)` или `nvarchar(max)` с использованием любого метода преобразования строк, например `ToString`. В приведенном ниже фрагменте кода предполагается наличие объекта <xref:System.Data.SqlClient.SqlDataReader> с именем `reader`, который извлекает данные.  
  
```vb  
While reader.Read()  
    Dim str as String = reader(0).ToString()  
    Console.WriteLine(str)  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
     string str = reader[0].ToString();  
     Console.WriteLine(str);  
}  
```  
  
### <a name="example"></a>Пример  
 Приведенный ниже код извлекает имя и объект `LargePhoto` из таблицы `ProductPhoto` в базе данных `AdventureWorks` и сохраняет его в файле. Сборку необходимо скомпилировать со ссылкой на пространство имен <xref:System.Drawing>.  Метод <xref:System.Data.SqlClient.SqlDataReader.GetSqlBytes%2A> класса <xref:System.Data.SqlClient.SqlDataReader> возвращает объект <xref:System.Data.SqlTypes.SqlBytes>, который предоставляет свойство `Stream`. Код использует его для создания нового объекта `Bitmap`, а затем сохраняет его как изображение `ImageFormat` в формате Gif.  
  
 [!code-csharp[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/VB/source.vb#1)]  
  
## <a name="using-large-value-type-parameters"></a>Использование параметров типа больших значений  
 Типы больших значений можно использовать в объектах <xref:System.Data.SqlClient.SqlParameter> точно так же, как и типы меньших значений в объектах <xref:System.Data.SqlClient.SqlParameter>. Типы больших значений можно извлекать в виде значений <xref:System.Data.SqlClient.SqlParameter>, как показано в следующем примере. В коде предполагается существование в примере базы данных AdventureWorks приведенной ниже хранимой процедуры GetDocumentSummary. Хранимая процедура принимает входной параметр @DocumentID и возвращает содержимое столбца DocumentSummary в выходной параметр @DocumentSummary.  
  
```sql
CREATE PROCEDURE GetDocumentSummary
(  
    @DocumentID int,  
    @DocumentSummary nvarchar(MAX) OUTPUT  
)  
AS  
SET NOCOUNT ON  
SELECT  @DocumentSummary=Convert(nvarchar(MAX), DocumentSummary)  
FROM    Production.Document  
WHERE   DocumentID=@DocumentID  
```  
  
### <a name="example"></a>Пример  
 Код ADO.NET создает объекты <xref:System.Data.SqlClient.SqlConnection> и <xref:System.Data.SqlClient.SqlCommand> для выполнения хранимой процедуры GetDocumentSummary и извлечения сводки документа, которая сохраняется как тип больших значений. Код передает значение входному параметру @DocumentID и отображает результаты, переданные обратно в выходной параметр @DocumentSummary, в окне консоли.  
  
 [!code-csharp[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/VB/source.vb#1)]  
  
## <a name="see-also"></a>См. также раздел

- [Двоичные и высокоценные данные сервера S'L](sql-server-binary-and-large-value-data.md)
- [Сопоставления типов данных SQL Server](../sql-server-data-type-mappings.md)
- [Операции с серверами серверов в ADO.NET](sql-server-data-operations.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
