---
title: Изменение данных с большими значениями (max)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8aca5f00-d80e-4320-81b3-016d0466f7ee
ms.openlocfilehash: cb37fdb85d323d4f0816a3667a4624da8ec75e65
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "76979850"
---
# <a name="modifying-large-value-max-data-in-adonet"></a>Изменение данных больших объемов (max) в ADO.NET
Типы данных LOB - это типы данных, размер которых превышает максимальный размер строки в 8 килобайт (КБ). В SQL Server для типов данных `max`, `varchar` и `nvarchar` имеется описатель `varbinary`, позволяющий хранить значения размером до 2^32 байт. Столбцы таблицы и переменные языка Transact-SQL могут задавать типы данных `varchar(max)`, `nvarchar(max)` или `varbinary(max)`. В ADO.NET типы данных `max` можно выбрать с помощью объекта `DataReader`, а также их можно задавать в качестве значений входных и выходных параметров без какой-либо специальной обработки. Данные больших типов данных `varchar` можно получать и обновлять добавочно.  
  
 Типы данных `max` можно использовать при сравнении, как переменные Transact-SQL, а также для объединения. Их можно использовать в предложениях DISTINCT, ORDER BY, GROUP BY инструкции SELECT, а также в статистических выражениях, соединениях и вложенных запросах.  
  
 В приведенной ниже таблице указаны ссылки на разделы электронной документации по SQL Server.  
  
 **Электронная документация по SQL Server**  
  
1. [Использование типов данных больших значений](https://go.microsoft.com/fwlink/?LinkId=120498)  
  
## <a name="large-value-type-restrictions"></a>Ограничения для типов данных большого размера  
 Следующие ограничения, не существующие для более мелких типов данных, применяются к типам данных `max`.  
  
- Переменная `sql_variant` не может содержать большой тип данных `varchar`.  
  
- Большие столбцы `varchar` не могут указываться в качестве ключевого столбца индекса. Они разрешены во включенных столбцах некластеризованного индекса.  
  
- Большие столбцы типа `varchar` нельзя использовать в качестве ключевых столбцов секционирования.  
  
## <a name="working-with-large-value-types-in-transact-sql"></a>Работа с типами большого размера на языке Transact-SQL  
 Функция `OPENROWSET` языка Transact-SQL является единовременным методом соединения и доступа к удаленным данным. Включает все сведения о соединении, необходимые для доступа к удаленным данным источника данных OLE DB. Из предложения FROM запроса на `OPENROWSET` можно ссылаться как на имя таблицы. Она также может быть использована в качестве целевой таблицы в инструкциях INSERT, UPDATE или DELETE. Это зависит от возможностей поставщика OLE DB.  
  
 В функции `OPENROWSET` включен поставщик набора строк `BULK`, позволяющий считывать данные непосредственно из файла без загрузки данных в целевую таблицу. Это позволяет использовать `OPENROWSET` в простой инструкции INSERT SELECT.  
  
 Аргументы параметра `OPENROWSET BULK` обеспечивают значительный контроль над тем, где следует начинать и заканчивать чтение данных, как обрабатывать ошибки и как интерпретировать данные. Например, можно указать, что файл с данными будет считан как однострочный или как набор строк типа `varbinary`, `varchar` или `nvarchar` в один столбец. Полный синтаксис и параметры см. в электронной документации по SQL Server.  
  
 В следующем примере в таблицу ProductPhoto образца базы данных AdventureWorks вставляется фотография. При использовании поставщика `BULK OPENROWSET` необходимо указать именованный список столбцов, даже если значения не вставляются в каждый столбец. В этом случае первичный ключ определяется в качестве столбца идентификаторов и может быть исключен из списка столбцов. Обратите внимание, что в конце инструкции `OPENROWSET` необходимо также указать корреляционное имя, которым в данном случае является ThumbnailPhoto. Оно коррелировано со столбцом в таблице `ProductPhoto`, в которую загружается файл.  
  
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
 Инструкция UPDATE языка Transact-SQL имеет новый синтаксис WRITE, предназначенный для изменения содержимого столбцов типа `varchar(max)`, `nvarchar(max)` или `varbinary(max)`. Это позволяет выполнять частичное обновление данных. Синтаксис UPDATE .WRITE показан здесь в сокращенной форме:  
  
 UPDATE  
  
 { *\<объект >* }  
  
 SET  
  
 { *column_name* = {. WRITE ( *выражение* , @Offset, @Length)}  
  
 Метод WRITE указывает, что раздел значения *column_name* будет изменен. Выражение — это значение, которое будет скопировано в *column_name*, `@Offset` является начальной точкой, в которую будет записано выражение, а аргументом `@Length` — длиной раздела в столбце.  
  
|Если командлет|Затем|  
|--------|----------|  
|Выражение устанавливается в значение NULL.|`@Length` игнорируется, и значение в *column_name* усекается по указанному `@Offset`.|  
|`@Offset` равно NULL|Операция обновления добавляет выражение в конец существующего *column_name* значения, и `@Length` игнорируется.|  
|Аргумент `@Offset` больше, чем длина поля column_name.|SQL Server возвращает ошибку.|  
|`@Length` равно NULL|Операция обновления удаляет все данные, со значения `@Offset` до конца значения `column_name`.|  
  
> [!NOTE]
> Ни `@Offset`, ни `@Length` не могут быть отрицательными числами.  
  
## <a name="example"></a>Пример  
 Этот пример Transact-SQL обновляет часть значения в DocumentSummary, столбце типа `nvarchar(max)` таблицы Document в базе данных AdventureWorks. Слово «components» заменяется словом «features», при этом указывается новое слово, начальное смещение слова, заменяемого в исходном тексте, и число заменяемых символов (длина). Пример содержит инструкции SELECT перед и после инструкции UPDATE для сравнения результатов.  
  
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
 Вы можете работать с типами больших значений в ADO.NET, указав типы больших значений в качестве <xref:System.Data.SqlClient.SqlParameter> объектов в <xref:System.Data.SqlClient.SqlDataReader> для возвращения результирующего набора или используя <xref:System.Data.SqlClient.SqlDataAdapter> для заполнения `DataSet`/`DataTable`. Не существует разницы в способах работы с типами больших значений и связанных с ними более мелкими типами данных.  
  
### <a name="using-getsqlbytes-to-retrieve-data"></a>Использование метода GetSqlBytes для получения данных  
 Метод `GetSqlBytes` объекта <xref:System.Data.SqlClient.SqlDataReader> можно использовать для получения содержимого столбца `varbinary(max)`. Следующий фрагмент кода предполагает, что объект <xref:System.Data.SqlClient.SqlCommand> с именем `cmd` выбирает данные столбца `varbinary(max)` из таблицы, а объект <xref:System.Data.SqlClient.SqlDataReader> с именем `reader` получает данные в виде <xref:System.Data.SqlTypes.SqlBytes>.  
  
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
 Метод `GetSqlChars` объекта <xref:System.Data.SqlClient.SqlDataReader> можно использовать для получения содержимого столбца типа `varchar(max)` или `nvarchar(max)`. Следующий фрагмент кода предполагает, что объект <xref:System.Data.SqlClient.SqlCommand> с именем `cmd` выбирает данные из столбца типа `nvarchar(max)` из таблицы, а объект <xref:System.Data.SqlClient.SqlDataReader> с именем `reader` получает данные.  
  
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
 Метод `GetSqlBinary` объекта <xref:System.Data.SqlClient.SqlDataReader> можно использовать для получения содержимого столбца типа `varbinary(max)`. Следующий фрагмент кода предполагает, что объект <xref:System.Data.SqlClient.SqlCommand> с именем `cmd` выбирает данные из столбца типа `varbinary(max)` таблицы, а объект <xref:System.Data.SqlClient.SqlDataReader> с именем `reader` получает данные в виде потока <xref:System.Data.SqlTypes.SqlBinary>.  
  
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
 Метод `GetBytes` объекта <xref:System.Data.SqlClient.SqlDataReader> считывает поток байтов, начиная с указанного смещения столбца в массив байт, начиная с указанного смещения массива. Следующий фрагмент кода предполагает, что объект <xref:System.Data.SqlClient.SqlDataReader> с именем `reader` получает байты в массив байтов. Следует отметить, что, в отличие от метода `GetSqlBytes`, методу `GetBytes` требуется память под буфер массива.  
  
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
 Метод `GetValue` объекта <xref:System.Data.SqlClient.SqlDataReader> считывает значение по указанному смещению из столбца в массив. Следующий фрагмент кода предполагает, что объект <xref:System.Data.SqlClient.SqlDataReader> с именем `reader` получает двоичные данные из первого смещения столбца, а затем строковые данные из второго смещения столбца.  
  
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
 Содержимое столбцов типа `varchar(max)` и `nvarchar(max)` можно преобразовать при помощи строковых методов преобразования, например `ToString`. Следующий фрагмент кода предполагает, что объект <xref:System.Data.SqlClient.SqlDataReader> с именем `reader` получает данные.  
  
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
 Следующий код получает из таблицы `LargePhoto` в базе данных `ProductPhoto` имя и объект `AdventureWorks` и сохраняет их в файл. При компиляции сборки необходимо добавить ссылку на пространство имен <xref:System.Drawing>.  Метод <xref:System.Data.SqlClient.SqlDataReader.GetSqlBytes%2A> объекта <xref:System.Data.SqlClient.SqlDataReader> возвращает объект <xref:System.Data.SqlTypes.SqlBytes>, представляющий свойство `Stream`. Этот код использует для создания нового объекта `Bitmap`, а затем сохраняет его в `ImageFormat`GIF.  
  
 [!code-csharp[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/VB/source.vb#1)]  
  
## <a name="using-large-value-type-parameters"></a>Использование параметров типа больших значений  
 Типы больших значений могут использоваться в объектах <xref:System.Data.SqlClient.SqlParameter> способом, аналогичным способу, используемому для типов меньших значений в объектах <xref:System.Data.SqlClient.SqlParameter>. Типы больших значений можно получить в виде значений <xref:System.Data.SqlClient.SqlParameter>, как показано в следующем примере. Код предполагает, что следующая хранимая процедура GetDocumentSummary существует в образце базы данных AdventureWorks. Хранимая процедура принимает входной параметр с именем @DocumentID и возвращает содержимое столбца DocumentSummary в выходном параметре @DocumentSummary.  
  
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
 Для выполнения хранимой процедуры GetDocumentSummary код ADO.NET создает объекты <xref:System.Data.SqlClient.SqlConnection> и <xref:System.Data.SqlClient.SqlCommand> и получает сводку документа, которая хранится в виде типа больших значений. Код передает значение входного параметра @DocumentID и отображает результаты, переданные в выходном параметре @DocumentSummary в окне консоли.  
  
 [!code-csharp[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/VB/source.vb#1)]  
  
## <a name="see-also"></a>См. также:

- [Двоичные данные и данные большого объема SQL Server](sql-server-binary-and-large-value-data.md)
- [Сопоставления типов данных SQL Server](../sql-server-data-type-mappings.md)
- [Операции данных SQL Server Data в ADO.NET](sql-server-data-operations.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
