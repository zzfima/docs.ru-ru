---
title: "Изменение данных большого размера (max) в ADO.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8aca5f00-d80e-4320-81b3-016d0466f7ee
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 6
---
# Изменение данных большого размера (max) в ADO.NET
Типы данных LOB \- это типы данных, размер которых превышает максимальный размер строки в 8 килобайт \(КБ\).  В SQL Server для типов данных `varchar`, `nvarchar` и `varbinary` имеется описатель `max`, позволяющий хранить значения размером до 2^32 байт.  Столбцы таблицы и переменные языка Transact\-SQL могут задавать типы данных `varchar(max)`, `nvarchar(max)` или `varbinary(max)`.  В ADO.NET типы данных `max` можно выбрать с помощью объекта `DataReader`, а также их можно задавать в качестве значений входных и выходных параметров без какой\-либо специальной обработки.  Данные больших типов данных `varchar` можно получать и обновлять добавочно.  
  
 Типы данных `max` можно использовать при сравнении, как переменные Transact\-SQL, а также для объединения.  Их можно использовать в предложениях DISTINCT, ORDER BY, GROUP BY инструкции SELECT, а также в статистических выражениях, соединениях и вложенных запросах.  
  
 В приведенной ниже таблице указаны ссылки на разделы электронной документации по SQL Server.  
  
 **Электронная документация по SQL Server**  
  
1.  [Использование типов данных большого размера](http://go.microsoft.com/fwlink/?LinkID=120498)  
  
## Ограничения для типов данных большого размера  
 Следующие ограничения, не существующие для более мелких типов данных, применяются к типам данных `max`.  
  
-   Переменная `sql_variant` не может содержать большой тип данных `varchar`.  
  
-   Большие столбцы `varchar` не могут указываться в качестве ключевого столбца индекса.  Они разрешены во включенных столбцах некластеризованного индекса.  
  
-   Большие столбцы типа `varchar` нельзя использовать в качестве ключевых столбцов секционирования.  
  
## Работа с типами большого размера на языке Transact\-SQL  
 Функция `OPENROWSET` языка Transact\-SQL является единовременным методом соединения и доступа к удаленным данным.  Включает все сведения о соединении, необходимые для доступа к удаленным данным источника данных OLE DB.  Из предложения FROM запроса на `OPENROWSET` можно ссылаться как на имя таблицы.  Она также может быть использована в качестве целевой таблицы в инструкциях INSERT, UPDATE или DELETE. Это зависит от возможностей поставщика OLE DB.  
  
 В функции `OPENROWSET` включен поставщик набора строк `BULK`, позволяющий считывать данные непосредственно из файла без загрузки данных в целевую таблицу.  Это позволяет использовать `OPENROWSET` в простой инструкции INSERT SELECT.  
  
 С помощью аргументов параметра `BULK` функции `OPENROWSET` можно управлять началом и концом считывания данных, отладкой ошибок и способом представления полученных данных.  Например, можно указать, что файл с данными будет считан как однострочный или как набор строк типа `varbinary`, `varchar` или `nvarchar` в один столбец.  Полный синтаксис и параметры см. в электронной документации по SQL Server.  
  
 В следующем примере в таблицу ProductPhoto образца базы данных AdventureWorks вставляется фотография.  При использовании поставщика `OPENROWSET` аргумента `BULK` необходимо указывать именованный список столбцов, даже если значения не вставляются в каждый столбец.  В этом случае первичный ключ определяется в качестве столбца идентификаторов и может быть исключен из списка столбцов.  Обратите внимание, что в конце инструкции `OPENROWSET` необходимо также указать корреляционное имя, которым в данном случае является ThumbnailPhoto.  Оно коррелировано со столбцом в таблице `ProductPhoto`, в которую загружается файл.  
  
```  
INSERT Production.ProductPhoto (  
    ThumbnailPhoto,   
    ThumbnailPhotoFilePath,   
    LargePhoto,   
    LargePhotoFilePath)  
SELECT ThumbnailPhoto.*, null, null, N'tricycle_pink.gif'  
FROM OPENROWSET   
    (BULK 'c:\images\tricycle.jpg', SINGLE_BLOB) ThumbnailPhoto  
```  
  
## Обновление данных с помощью инструкций UPDATE .WRITE  
 Инструкция UPDATE языка Transact\-SQL имеет новый синтаксис WRITE, предназначенный для изменения содержимого столбцов типа `varchar(max)`, `nvarchar(max)` или `varbinary(max)`.  Это позволяет выполнять частичное обновление данных.  Синтаксис UPDATE .WRITE показан здесь в сокращенной форме:  
  
 UPDATE  
  
 { *\<объект\>* }  
  
 SET  
  
 { *имя\_столбца* \= { .WRITE \( *выражение* , @Offset , @Length \) }  
  
 Метод WRITE указывает, что секция значения *имя\_столбца* будет изменена.  Выражение является значением, которое будет скопировано в поле *имя\_столбца*. Аргумент `@Offset` является начальной точкой записи выражения, а аргумент `@Length` — длиной раздела в столбце.  
  
|If|Следующее действие|  
|--------|------------------------|  
|Выражение устанавливается в значение NULL.|Аргумент `@Length` не обрабатывается, а значение в поле *column\_name* усекается в соответствии с указанным аргументом `@Offset`.|  
|`@Offset` равно NULL|Операция обновления добавляет выражение в конец существующего значения *column\_name*, и аргумент `@Length` не обрабатывается.|  
|Аргумент `@Offset` больше, чем длина поля column\_name.|SQL Server возвращает ошибку.|  
|`@Length` равно NULL|Операция обновления удаляет все данные, со значения `@Offset` до конца значения `column_name`.|  
  
> [!NOTE]
>  Ни `@Offset`, ни `@Length` не могут быть отрицательными числами.  
  
## Пример  
 Этот пример Transact\-SQL обновляет часть значения в DocumentSummary, столбце типа `nvarchar(max)` таблицы Document в базе данных AdventureWorks.  Слово «components» заменяется словом «features», при этом указывается новое слово, начальное смещение слова, заменяемого в исходном тексте, и число заменяемых символов \(длина\).  Пример содержит инструкции SELECT перед и после инструкции UPDATE для сравнения результатов.  
  
```  
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
  
## Работа с типами данных большого размера в ADO.NET  
 В ADO.NET можно работать с типами больших значений, указав их в качестве параметров <xref:System.Data.SqlClient.SqlParameter> `` метода <xref:System.Data.SqlClient.SqlDataReader> для возврата результирующего набора либо воспользовавшись объектом <xref:System.Data.SqlClient.SqlDataAdapter> для заполнения набора `DataSet`\/`DataTable`.  Не существует разницы в способах работы с типами больших значений и связанных с ними более мелкими типами данных.  
  
### Использование метода GetSqlBytes для получения данных  
 Метод `GetSqlBytes` объекта <xref:System.Data.SqlClient.SqlDataReader> можно использовать для получения содержимого столбца `varbinary(max)`.  Следующий фрагмент кода предполагает, что объект <xref:System.Data.SqlClient.SqlCommand> с именем `cmd` выбирает данные столбца `varbinary(max)` из таблицы, а объект <xref:System.Data.SqlClient.SqlDataReader> с именем `reader` получает данные в виде <xref:System.Data.SqlTypes.SqlBytes>.  
  
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
  
### Использование метода GetSqlChars для получения данных  
 Метод `GetSqlChars` объекта <xref:System.Data.SqlClient.SqlDataReader> можно использовать для получения содержимого столбца типа `varchar(max)` или `nvarchar(max)`.  Следующий фрагмент кода предполагает, что объект <xref:System.Data.SqlClient.SqlCommand> с именем `cmd` выбирает данные из столбца типа `nvarchar(max)` из таблицы, а объект <xref:System.Data.SqlClient.SqlDataReader> с именем `reader` получает данные.  
  
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
  
### Использование метода GetSqlBinary для получения данных  
 Метод `GetSqlBinary` объекта <xref:System.Data.SqlClient.SqlDataReader> можно использовать для получения содержимого столбца типа `varbinary(max)`.  Следующий фрагмент кода предполагает, что объект <xref:System.Data.SqlClient.SqlCommand> с именем `cmd` выбирает данные из столбца типа `varbinary(max)` таблицы, а объект <xref:System.Data.SqlClient.SqlDataReader> с именем `reader` получает данные в виде потока <xref:System.Data.SqlTypes.SqlBinary>.  
  
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
  
### Использование метода GetBytes для получения данных  
 Метод `GetBytes` объекта <xref:System.Data.SqlClient.SqlDataReader> считывает поток байтов, начиная с указанного смещения столбца в массив байт, начиная с указанного смещения массива.  Следующий фрагмент кода предполагает, что объект <xref:System.Data.SqlClient.SqlDataReader> с именем `reader` получает байты в массив байтов.  Следует отметить, что, в отличие от метода `GetSqlBytes`, методу `GetBytes` требуется память под буфер массива.  
  
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
  
### Использование метода GetValue для получения данных  
 Метод `GetValue` объекта <xref:System.Data.SqlClient.SqlDataReader> считывает значение по указанному смещению из столбца в массив.  Следующий фрагмент кода предполагает, что объект <xref:System.Data.SqlClient.SqlDataReader> с именем `reader` получает двоичные данные из первого смещения столбца, а затем строковые данные из второго смещения столбца.  
  
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
  
## Преобразование типов больших значений в типы CLR  
 Содержимое столбцов типа `varchar(max)` и `nvarchar(max)` можно преобразовать при помощи строковых методов преобразования, например `ToString`.  Следующий фрагмент кода предполагает, что объект <xref:System.Data.SqlClient.SqlDataReader> с именем `reader` получает данные.  
  
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
  
### Пример  
 Следующий код получает из таблицы `ProductPhoto` в базе данных `AdventureWorks` имя и объект `LargePhoto` и сохраняет их в файл.  При компиляции сборки необходимо добавить ссылку на пространство имен <xref:System.Drawing>.  Метод <xref:System.Data.SqlClient.SqlDataReader.GetSqlBytes%2A> объекта <xref:System.Data.SqlClient.SqlDataReader> возвращает объект <xref:System.Data.SqlTypes.SqlBytes>, представляющий свойство `Stream`.  Код использует его для создания нового объекта `Bitmap`, а затем сохраняет его как изображение `ImageFormat` в формате Gif.  
  
 [!code-csharp[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/VB/source.vb#1)]  
  
## Использование параметров типа больших значений  
 Типы больших значений могут использоваться в объектах <xref:System.Data.SqlClient.SqlParameter> способом, аналогичным способу, используемому для типов меньших значений в объектах <xref:System.Data.SqlClient.SqlParameter>.  Типы больших значений можно извлекать в виде значений <xref:System.Data.SqlClient.SqlParameter> `` , как показано в следующем примере.  Код предполагает, что следующая хранимая процедура GetDocumentSummary существует в образце базы данных AdventureWorks.  Хранимая процедура принимает входной параметр с именем @DocumentID и возвращает содержимое столбца DocumentSummary в выходной параметр @DocumentSummary.  
  
```  
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
  
### Пример  
 Для выполнения хранимой процедуры GetDocumentSummary код ADO.NET создает объекты <xref:System.Data.SqlClient.SqlConnection> и <xref:System.Data.SqlClient.SqlCommand> и получает сводку документа, которая хранится в виде типа больших значений.  Код передает значение входному параметру @DocumentID и отображает результаты, переданные обратно в выходной параметр @DocumentSummary, в окне консоли.  
  
 [!code-csharp[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/VB/source.vb#1)]  
  
## См. также  
 [Двоичные данные и данные большого размера SQL Server](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)   
 [Сопоставления типов данных SQL Server](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)   
 [Операции с данными SQL Server в ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)