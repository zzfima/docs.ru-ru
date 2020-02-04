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
# <a name="modifying-large-value-max-data-in-adonet"></a><span data-ttu-id="408a8-102">Изменение данных больших объемов (max) в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="408a8-102">Modifying Large-Value (max) Data in ADO.NET</span></span>
<span data-ttu-id="408a8-103">Типы данных LOB - это типы данных, размер которых превышает максимальный размер строки в 8 килобайт (КБ).</span><span class="sxs-lookup"><span data-stu-id="408a8-103">Large object (LOB) data types are those that exceed the maximum row size of 8 kilobytes (KB).</span></span> <span data-ttu-id="408a8-104">В SQL Server для типов данных `max`, `varchar` и `nvarchar` имеется описатель `varbinary`, позволяющий хранить значения размером до 2^32 байт.</span><span class="sxs-lookup"><span data-stu-id="408a8-104">SQL Server provides a `max` specifier for `varchar`, `nvarchar`, and `varbinary` data types to allow storage of values as large as 2^32 bytes.</span></span> <span data-ttu-id="408a8-105">Столбцы таблицы и переменные языка Transact-SQL могут задавать типы данных `varchar(max)`, `nvarchar(max)` или `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="408a8-105">Table columns and Transact-SQL variables may specify `varchar(max)`, `nvarchar(max)`, or `varbinary(max)` data types.</span></span> <span data-ttu-id="408a8-106">В ADO.NET типы данных `max` можно выбрать с помощью объекта `DataReader`, а также их можно задавать в качестве значений входных и выходных параметров без какой-либо специальной обработки.</span><span class="sxs-lookup"><span data-stu-id="408a8-106">In ADO.NET, the `max` data types can be fetched by a `DataReader`, and can also be specified as both input and output parameter values without any special handling.</span></span> <span data-ttu-id="408a8-107">Данные больших типов данных `varchar` можно получать и обновлять добавочно.</span><span class="sxs-lookup"><span data-stu-id="408a8-107">For large `varchar` data types, data can be retrieved and updated incrementally.</span></span>  
  
 <span data-ttu-id="408a8-108">Типы данных `max` можно использовать при сравнении, как переменные Transact-SQL, а также для объединения.</span><span class="sxs-lookup"><span data-stu-id="408a8-108">The `max` data types can be used for comparisons, as Transact-SQL variables, and for concatenation.</span></span> <span data-ttu-id="408a8-109">Их можно использовать в предложениях DISTINCT, ORDER BY, GROUP BY инструкции SELECT, а также в статистических выражениях, соединениях и вложенных запросах.</span><span class="sxs-lookup"><span data-stu-id="408a8-109">They can also be used in the DISTINCT, ORDER BY, GROUP BY clauses of a SELECT statement as well as in aggregates, joins, and subqueries.</span></span>  
  
 <span data-ttu-id="408a8-110">В приведенной ниже таблице указаны ссылки на разделы электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="408a8-110">The following table provides links to the documentation in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="408a8-111">**Электронная документация по SQL Server**</span><span class="sxs-lookup"><span data-stu-id="408a8-111">**SQL Server Books Online**</span></span>  
  
1. [<span data-ttu-id="408a8-112">Использование типов данных больших значений</span><span class="sxs-lookup"><span data-stu-id="408a8-112">Using Large-Value Data Types</span></span>](https://go.microsoft.com/fwlink/?LinkId=120498)  
  
## <a name="large-value-type-restrictions"></a><span data-ttu-id="408a8-113">Ограничения для типов данных большого размера</span><span class="sxs-lookup"><span data-stu-id="408a8-113">Large-Value Type Restrictions</span></span>  
 <span data-ttu-id="408a8-114">Следующие ограничения, не существующие для более мелких типов данных, применяются к типам данных `max`.</span><span class="sxs-lookup"><span data-stu-id="408a8-114">The following restrictions apply to the `max` data types, which do not exist for smaller data types:</span></span>  
  
- <span data-ttu-id="408a8-115">Переменная `sql_variant` не может содержать большой тип данных `varchar`.</span><span class="sxs-lookup"><span data-stu-id="408a8-115">A `sql_variant` cannot contain a large `varchar` data type.</span></span>  
  
- <span data-ttu-id="408a8-116">Большие столбцы `varchar` не могут указываться в качестве ключевого столбца индекса.</span><span class="sxs-lookup"><span data-stu-id="408a8-116">Large `varchar` columns cannot be specified as a key column in an index.</span></span> <span data-ttu-id="408a8-117">Они разрешены во включенных столбцах некластеризованного индекса.</span><span class="sxs-lookup"><span data-stu-id="408a8-117">They are allowed in an included column in a non-clustered index.</span></span>  
  
- <span data-ttu-id="408a8-118">Большие столбцы типа `varchar` нельзя использовать в качестве ключевых столбцов секционирования.</span><span class="sxs-lookup"><span data-stu-id="408a8-118">Large `varchar` columns cannot be used as partitioning key columns.</span></span>  
  
## <a name="working-with-large-value-types-in-transact-sql"></a><span data-ttu-id="408a8-119">Работа с типами большого размера на языке Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="408a8-119">Working with Large-Value Types in Transact-SQL</span></span>  
 <span data-ttu-id="408a8-120">Функция `OPENROWSET` языка Transact-SQL является единовременным методом соединения и доступа к удаленным данным.</span><span class="sxs-lookup"><span data-stu-id="408a8-120">The Transact-SQL `OPENROWSET` function is a one-time method of connecting and accessing remote data.</span></span> <span data-ttu-id="408a8-121">Включает все сведения о соединении, необходимые для доступа к удаленным данным источника данных OLE DB.</span><span class="sxs-lookup"><span data-stu-id="408a8-121">It includes all of the connection information necessary to access remote data from an OLE DB data source.</span></span> <span data-ttu-id="408a8-122">Из предложения FROM запроса на `OPENROWSET` можно ссылаться как на имя таблицы.</span><span class="sxs-lookup"><span data-stu-id="408a8-122">`OPENROWSET` can be referenced in the FROM clause of a query as though it were a table name.</span></span> <span data-ttu-id="408a8-123">Она также может быть использована в качестве целевой таблицы в инструкциях INSERT, UPDATE или DELETE. Это зависит от возможностей поставщика OLE DB.</span><span class="sxs-lookup"><span data-stu-id="408a8-123">It can also be referenced as the target table of an INSERT, UPDATE, or DELETE statement, subject to the capabilities of the OLE DB provider.</span></span>  
  
 <span data-ttu-id="408a8-124">В функции `OPENROWSET` включен поставщик набора строк `BULK`, позволяющий считывать данные непосредственно из файла без загрузки данных в целевую таблицу.</span><span class="sxs-lookup"><span data-stu-id="408a8-124">The `OPENROWSET` function includes the `BULK` rowset provider, which allows you to read data directly from a file without loading the data into a target table.</span></span> <span data-ttu-id="408a8-125">Это позволяет использовать `OPENROWSET` в простой инструкции INSERT SELECT.</span><span class="sxs-lookup"><span data-stu-id="408a8-125">This enables you to use `OPENROWSET` in a simple INSERT SELECT statement.</span></span>  
  
 <span data-ttu-id="408a8-126">Аргументы параметра `OPENROWSET BULK` обеспечивают значительный контроль над тем, где следует начинать и заканчивать чтение данных, как обрабатывать ошибки и как интерпретировать данные.</span><span class="sxs-lookup"><span data-stu-id="408a8-126">The `OPENROWSET BULK` option arguments provide significant control over where to begin and end reading data, how to deal with errors, and how data is interpreted.</span></span> <span data-ttu-id="408a8-127">Например, можно указать, что файл с данными будет считан как однострочный или как набор строк типа `varbinary`, `varchar` или `nvarchar` в один столбец.</span><span class="sxs-lookup"><span data-stu-id="408a8-127">For example, you can specify that the data file be read as a single-row, single-column rowset of type `varbinary`, `varchar`, or `nvarchar`.</span></span> <span data-ttu-id="408a8-128">Полный синтаксис и параметры см. в электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="408a8-128">For the complete syntax and options, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="408a8-129">В следующем примере в таблицу ProductPhoto образца базы данных AdventureWorks вставляется фотография.</span><span class="sxs-lookup"><span data-stu-id="408a8-129">The following example inserts a photo into the ProductPhoto table in the AdventureWorks sample database.</span></span> <span data-ttu-id="408a8-130">При использовании поставщика `BULK OPENROWSET` необходимо указать именованный список столбцов, даже если значения не вставляются в каждый столбец.</span><span class="sxs-lookup"><span data-stu-id="408a8-130">When using the `BULK OPENROWSET` provider, you must supply the named list of columns even if you aren't inserting values into every column.</span></span> <span data-ttu-id="408a8-131">В этом случае первичный ключ определяется в качестве столбца идентификаторов и может быть исключен из списка столбцов.</span><span class="sxs-lookup"><span data-stu-id="408a8-131">The primary key in this case is defined as an identity column, and may be omitted from the column list.</span></span> <span data-ttu-id="408a8-132">Обратите внимание, что в конце инструкции `OPENROWSET` необходимо также указать корреляционное имя, которым в данном случае является ThumbnailPhoto.</span><span class="sxs-lookup"><span data-stu-id="408a8-132">Note that you must also supply a correlation name at the end of the `OPENROWSET` statement, which in this case is ThumbnailPhoto.</span></span> <span data-ttu-id="408a8-133">Оно коррелировано со столбцом в таблице `ProductPhoto`, в которую загружается файл.</span><span class="sxs-lookup"><span data-stu-id="408a8-133">This correlates with the column in the `ProductPhoto` table into which the file is being loaded.</span></span>  
  
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
  
## <a name="updating-data-using-update-write"></a><span data-ttu-id="408a8-134">Обновление данных с помощью инструкций UPDATE .WRITE</span><span class="sxs-lookup"><span data-stu-id="408a8-134">Updating Data Using UPDATE .WRITE</span></span>  
 <span data-ttu-id="408a8-135">Инструкция UPDATE языка Transact-SQL имеет новый синтаксис WRITE, предназначенный для изменения содержимого столбцов типа `varchar(max)`, `nvarchar(max)` или `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="408a8-135">The Transact-SQL UPDATE statement has new WRITE syntax for modifying the contents of `varchar(max)`, `nvarchar(max)`, or `varbinary(max)` columns.</span></span> <span data-ttu-id="408a8-136">Это позволяет выполнять частичное обновление данных.</span><span class="sxs-lookup"><span data-stu-id="408a8-136">This allows you to perform partial updates of the data.</span></span> <span data-ttu-id="408a8-137">Синтаксис UPDATE .WRITE показан здесь в сокращенной форме:</span><span class="sxs-lookup"><span data-stu-id="408a8-137">The UPDATE .WRITE syntax is shown here in abbreviated form:</span></span>  
  
 <span data-ttu-id="408a8-138">UPDATE</span><span class="sxs-lookup"><span data-stu-id="408a8-138">UPDATE</span></span>  
  
 <span data-ttu-id="408a8-139">{ *\<объект >* }</span><span class="sxs-lookup"><span data-stu-id="408a8-139">{ *\<object>* }</span></span>  
  
 <span data-ttu-id="408a8-140">SET</span><span class="sxs-lookup"><span data-stu-id="408a8-140">SET</span></span>  
  
 <span data-ttu-id="408a8-141">{ *column_name* = {. WRITE ( *выражение* , @Offset, @Length)}</span><span class="sxs-lookup"><span data-stu-id="408a8-141">{ *column_name* = { .WRITE ( *expression* , @Offset , @Length ) }</span></span>  
  
 <span data-ttu-id="408a8-142">Метод WRITE указывает, что раздел значения *column_name* будет изменен.</span><span class="sxs-lookup"><span data-stu-id="408a8-142">The WRITE method specifies that a section of the value of the *column_name* will be modified.</span></span> <span data-ttu-id="408a8-143">Выражение — это значение, которое будет скопировано в *column_name*, `@Offset` является начальной точкой, в которую будет записано выражение, а аргументом `@Length` — длиной раздела в столбце.</span><span class="sxs-lookup"><span data-stu-id="408a8-143">The expression is the value that will be copied to the *column_name*, the `@Offset` is the beginning point at which the expression will be written, and the `@Length` argument is the length of the section in the column.</span></span>  
  
|<span data-ttu-id="408a8-144">Если командлет</span><span class="sxs-lookup"><span data-stu-id="408a8-144">If</span></span>|<span data-ttu-id="408a8-145">Затем</span><span class="sxs-lookup"><span data-stu-id="408a8-145">Then</span></span>|  
|--------|----------|  
|<span data-ttu-id="408a8-146">Выражение устанавливается в значение NULL.</span><span class="sxs-lookup"><span data-stu-id="408a8-146">The expression is set to NULL</span></span>|<span data-ttu-id="408a8-147">`@Length` игнорируется, и значение в *column_name* усекается по указанному `@Offset`.</span><span class="sxs-lookup"><span data-stu-id="408a8-147">`@Length` is ignored and the value in *column_name* is truncated at the specified `@Offset`.</span></span>|  
|<span data-ttu-id="408a8-148">`@Offset` равно NULL</span><span class="sxs-lookup"><span data-stu-id="408a8-148">`@Offset` is NULL</span></span>|<span data-ttu-id="408a8-149">Операция обновления добавляет выражение в конец существующего *column_name* значения, и `@Length` игнорируется.</span><span class="sxs-lookup"><span data-stu-id="408a8-149">The update operation appends the expression at the end of the existing *column_name* value and `@Length` is ignored.</span></span>|  
|<span data-ttu-id="408a8-150">Аргумент `@Offset` больше, чем длина поля column_name.</span><span class="sxs-lookup"><span data-stu-id="408a8-150">`@Offset` is greater than the length of the column_name value</span></span>|<span data-ttu-id="408a8-151">SQL Server возвращает ошибку.</span><span class="sxs-lookup"><span data-stu-id="408a8-151">SQL Server returns an error.</span></span>|  
|<span data-ttu-id="408a8-152">`@Length` равно NULL</span><span class="sxs-lookup"><span data-stu-id="408a8-152">`@Length` is NULL</span></span>|<span data-ttu-id="408a8-153">Операция обновления удаляет все данные, со значения `@Offset` до конца значения `column_name`.</span><span class="sxs-lookup"><span data-stu-id="408a8-153">The update operation removes all data from `@Offset` to the end of the `column_name` value.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="408a8-154">Ни `@Offset`, ни `@Length` не могут быть отрицательными числами.</span><span class="sxs-lookup"><span data-stu-id="408a8-154">Neither `@Offset` nor `@Length` can be a negative number.</span></span>  
  
## <a name="example"></a><span data-ttu-id="408a8-155">Пример</span><span class="sxs-lookup"><span data-stu-id="408a8-155">Example</span></span>  
 <span data-ttu-id="408a8-156">Этот пример Transact-SQL обновляет часть значения в DocumentSummary, столбце типа `nvarchar(max)` таблицы Document в базе данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="408a8-156">This Transact-SQL example updates a partial value in DocumentSummary, an `nvarchar(max)` column in the Document table in the AdventureWorks database.</span></span> <span data-ttu-id="408a8-157">Слово «components» заменяется словом «features», при этом указывается новое слово, начальное смещение слова, заменяемого в исходном тексте, и число заменяемых символов (длина).</span><span class="sxs-lookup"><span data-stu-id="408a8-157">The word 'components' is replaced by the word 'features' by specifying the replacement word, the beginning location (offset) of the word to be replaced in the existing data, and the number of characters to be replaced (length).</span></span> <span data-ttu-id="408a8-158">Пример содержит инструкции SELECT перед и после инструкции UPDATE для сравнения результатов.</span><span class="sxs-lookup"><span data-stu-id="408a8-158">The example includes SELECT statements before and after the UPDATE statement to compare results.</span></span>  
  
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
  
## <a name="working-with-large-value-types-in-adonet"></a><span data-ttu-id="408a8-159">Работа с типами данных большого размера в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="408a8-159">Working with Large-Value Types in ADO.NET</span></span>  
 <span data-ttu-id="408a8-160">Вы можете работать с типами больших значений в ADO.NET, указав типы больших значений в качестве <xref:System.Data.SqlClient.SqlParameter> объектов в <xref:System.Data.SqlClient.SqlDataReader> для возвращения результирующего набора или используя <xref:System.Data.SqlClient.SqlDataAdapter> для заполнения `DataSet`/`DataTable`.</span><span class="sxs-lookup"><span data-stu-id="408a8-160">You can work with large value types in ADO.NET by specifying large value types as <xref:System.Data.SqlClient.SqlParameter> objects in a <xref:System.Data.SqlClient.SqlDataReader> to return a result set, or by using a <xref:System.Data.SqlClient.SqlDataAdapter> to fill a `DataSet`/`DataTable`.</span></span> <span data-ttu-id="408a8-161">Не существует разницы в способах работы с типами больших значений и связанных с ними более мелкими типами данных.</span><span class="sxs-lookup"><span data-stu-id="408a8-161">There is no difference between the way you work with a large value type and its related, smaller value data type.</span></span>  
  
### <a name="using-getsqlbytes-to-retrieve-data"></a><span data-ttu-id="408a8-162">Использование метода GetSqlBytes для получения данных</span><span class="sxs-lookup"><span data-stu-id="408a8-162">Using GetSqlBytes to Retrieve Data</span></span>  
 <span data-ttu-id="408a8-163">Метод `GetSqlBytes` объекта <xref:System.Data.SqlClient.SqlDataReader> можно использовать для получения содержимого столбца `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="408a8-163">The `GetSqlBytes` method of the <xref:System.Data.SqlClient.SqlDataReader> can be used to retrieve the contents of a `varbinary(max)` column.</span></span> <span data-ttu-id="408a8-164">Следующий фрагмент кода предполагает, что объект <xref:System.Data.SqlClient.SqlCommand> с именем `cmd` выбирает данные столбца `varbinary(max)` из таблицы, а объект <xref:System.Data.SqlClient.SqlDataReader> с именем `reader` получает данные в виде <xref:System.Data.SqlTypes.SqlBytes>.</span><span class="sxs-lookup"><span data-stu-id="408a8-164">The following code fragment assumes a <xref:System.Data.SqlClient.SqlCommand> object named `cmd` that selects `varbinary(max)` data from a table and a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data as <xref:System.Data.SqlTypes.SqlBytes>.</span></span>  
  
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
  
### <a name="using-getsqlchars-to-retrieve-data"></a><span data-ttu-id="408a8-165">Использование метода GetSqlChars для получения данных</span><span class="sxs-lookup"><span data-stu-id="408a8-165">Using GetSqlChars to Retrieve Data</span></span>  
 <span data-ttu-id="408a8-166">Метод `GetSqlChars` объекта <xref:System.Data.SqlClient.SqlDataReader> можно использовать для получения содержимого столбца типа `varchar(max)` или `nvarchar(max)`.</span><span class="sxs-lookup"><span data-stu-id="408a8-166">The `GetSqlChars` method of the <xref:System.Data.SqlClient.SqlDataReader> can be used to retrieve the contents of a `varchar(max)` or `nvarchar(max)` column.</span></span> <span data-ttu-id="408a8-167">Следующий фрагмент кода предполагает, что объект <xref:System.Data.SqlClient.SqlCommand> с именем `cmd` выбирает данные из столбца типа `nvarchar(max)` из таблицы, а объект <xref:System.Data.SqlClient.SqlDataReader> с именем `reader` получает данные.</span><span class="sxs-lookup"><span data-stu-id="408a8-167">The following code fragment assumes a <xref:System.Data.SqlClient.SqlCommand> object named `cmd` that selects `nvarchar(max)` data from a table and a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data.</span></span>  
  
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
  
### <a name="using-getsqlbinary-to-retrieve-data"></a><span data-ttu-id="408a8-168">Использование метода GetSqlBinary для получения данных</span><span class="sxs-lookup"><span data-stu-id="408a8-168">Using GetSqlBinary to Retrieve Data</span></span>  
 <span data-ttu-id="408a8-169">Метод `GetSqlBinary` объекта <xref:System.Data.SqlClient.SqlDataReader> можно использовать для получения содержимого столбца типа `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="408a8-169">The `GetSqlBinary` method of a <xref:System.Data.SqlClient.SqlDataReader> can be used to retrieve the contents of a `varbinary(max)` column.</span></span> <span data-ttu-id="408a8-170">Следующий фрагмент кода предполагает, что объект <xref:System.Data.SqlClient.SqlCommand> с именем `cmd` выбирает данные из столбца типа `varbinary(max)` таблицы, а объект <xref:System.Data.SqlClient.SqlDataReader> с именем `reader` получает данные в виде потока <xref:System.Data.SqlTypes.SqlBinary>.</span><span class="sxs-lookup"><span data-stu-id="408a8-170">The following code fragment assumes a <xref:System.Data.SqlClient.SqlCommand> object named `cmd` that selects `varbinary(max)` data from a table and a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data as a <xref:System.Data.SqlTypes.SqlBinary> stream.</span></span>  
  
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
  
### <a name="using-getbytes-to-retrieve-data"></a><span data-ttu-id="408a8-171">Использование метода GetBytes для получения данных</span><span class="sxs-lookup"><span data-stu-id="408a8-171">Using GetBytes to Retrieve Data</span></span>  
 <span data-ttu-id="408a8-172">Метод `GetBytes` объекта <xref:System.Data.SqlClient.SqlDataReader> считывает поток байтов, начиная с указанного смещения столбца в массив байт, начиная с указанного смещения массива.</span><span class="sxs-lookup"><span data-stu-id="408a8-172">The `GetBytes` method of a <xref:System.Data.SqlClient.SqlDataReader> reads a stream of bytes from the specified column offset into a byte array starting at the specified array offset.</span></span> <span data-ttu-id="408a8-173">Следующий фрагмент кода предполагает, что объект <xref:System.Data.SqlClient.SqlDataReader> с именем `reader` получает байты в массив байтов.</span><span class="sxs-lookup"><span data-stu-id="408a8-173">The following code fragment assumes a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves bytes into a byte array.</span></span> <span data-ttu-id="408a8-174">Следует отметить, что, в отличие от метода `GetSqlBytes`, методу `GetBytes` требуется память под буфер массива.</span><span class="sxs-lookup"><span data-stu-id="408a8-174">Note that, unlike `GetSqlBytes`, `GetBytes` requires a size for the array buffer.</span></span>  
  
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
  
### <a name="using-getvalue-to-retrieve-data"></a><span data-ttu-id="408a8-175">Использование метода GetValue для получения данных</span><span class="sxs-lookup"><span data-stu-id="408a8-175">Using GetValue to Retrieve Data</span></span>  
 <span data-ttu-id="408a8-176">Метод `GetValue` объекта <xref:System.Data.SqlClient.SqlDataReader> считывает значение по указанному смещению из столбца в массив.</span><span class="sxs-lookup"><span data-stu-id="408a8-176">The `GetValue` method of a <xref:System.Data.SqlClient.SqlDataReader> reads the value from the specified column offset into an array.</span></span> <span data-ttu-id="408a8-177">Следующий фрагмент кода предполагает, что объект <xref:System.Data.SqlClient.SqlDataReader> с именем `reader` получает двоичные данные из первого смещения столбца, а затем строковые данные из второго смещения столбца.</span><span class="sxs-lookup"><span data-stu-id="408a8-177">The following code fragment assumes a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves binary data from the first column offset, and then string data from the second column offset.</span></span>  
  
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
  
## <a name="converting-from-large-value-types-to-clr-types"></a><span data-ttu-id="408a8-178">Преобразование типов больших значений в типы CLR</span><span class="sxs-lookup"><span data-stu-id="408a8-178">Converting from Large Value Types to CLR Types</span></span>  
 <span data-ttu-id="408a8-179">Содержимое столбцов типа `varchar(max)` и `nvarchar(max)` можно преобразовать при помощи строковых методов преобразования, например `ToString`.</span><span class="sxs-lookup"><span data-stu-id="408a8-179">You can convert the contents of a `varchar(max)` or `nvarchar(max)` column using any of the string conversion methods, such as `ToString`.</span></span> <span data-ttu-id="408a8-180">Следующий фрагмент кода предполагает, что объект <xref:System.Data.SqlClient.SqlDataReader> с именем `reader` получает данные.</span><span class="sxs-lookup"><span data-stu-id="408a8-180">The following code fragment assumes a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data.</span></span>  
  
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
  
### <a name="example"></a><span data-ttu-id="408a8-181">Пример</span><span class="sxs-lookup"><span data-stu-id="408a8-181">Example</span></span>  
 <span data-ttu-id="408a8-182">Следующий код получает из таблицы `LargePhoto` в базе данных `ProductPhoto` имя и объект `AdventureWorks` и сохраняет их в файл.</span><span class="sxs-lookup"><span data-stu-id="408a8-182">The following code retrieves the name and the `LargePhoto` object from the `ProductPhoto` table in the `AdventureWorks` database and saves it to a file.</span></span> <span data-ttu-id="408a8-183">При компиляции сборки необходимо добавить ссылку на пространство имен <xref:System.Drawing>.</span><span class="sxs-lookup"><span data-stu-id="408a8-183">The assembly needs to be compiled with a reference to the <xref:System.Drawing> namespace.</span></span>  <span data-ttu-id="408a8-184">Метод <xref:System.Data.SqlClient.SqlDataReader.GetSqlBytes%2A> объекта <xref:System.Data.SqlClient.SqlDataReader> возвращает объект <xref:System.Data.SqlTypes.SqlBytes>, представляющий свойство `Stream`.</span><span class="sxs-lookup"><span data-stu-id="408a8-184">The <xref:System.Data.SqlClient.SqlDataReader.GetSqlBytes%2A> method of the <xref:System.Data.SqlClient.SqlDataReader> returns a <xref:System.Data.SqlTypes.SqlBytes> object that exposes a `Stream` property.</span></span> <span data-ttu-id="408a8-185">Этот код использует для создания нового объекта `Bitmap`, а затем сохраняет его в `ImageFormat`GIF.</span><span class="sxs-lookup"><span data-stu-id="408a8-185">The code uses this to create a new `Bitmap` object, and then saves it in the Gif `ImageFormat`.</span></span>  
  
 [!code-csharp[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/VB/source.vb#1)]  
  
## <a name="using-large-value-type-parameters"></a><span data-ttu-id="408a8-186">Использование параметров типа больших значений</span><span class="sxs-lookup"><span data-stu-id="408a8-186">Using Large Value Type Parameters</span></span>  
 <span data-ttu-id="408a8-187">Типы больших значений могут использоваться в объектах <xref:System.Data.SqlClient.SqlParameter> способом, аналогичным способу, используемому для типов меньших значений в объектах <xref:System.Data.SqlClient.SqlParameter>.</span><span class="sxs-lookup"><span data-stu-id="408a8-187">Large value types can be used in <xref:System.Data.SqlClient.SqlParameter> objects the same way you use smaller value types in <xref:System.Data.SqlClient.SqlParameter> objects.</span></span> <span data-ttu-id="408a8-188">Типы больших значений можно получить в виде значений <xref:System.Data.SqlClient.SqlParameter>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="408a8-188">You can retrieve large value types as <xref:System.Data.SqlClient.SqlParameter> values, as shown in the following example.</span></span> <span data-ttu-id="408a8-189">Код предполагает, что следующая хранимая процедура GetDocumentSummary существует в образце базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="408a8-189">The code assumes that the following GetDocumentSummary stored procedure exists in the AdventureWorks sample database.</span></span> <span data-ttu-id="408a8-190">Хранимая процедура принимает входной параметр с именем @DocumentID и возвращает содержимое столбца DocumentSummary в выходном параметре @DocumentSummary.</span><span class="sxs-lookup"><span data-stu-id="408a8-190">The stored procedure takes an input parameter named @DocumentID and returns the contents of the DocumentSummary column in the @DocumentSummary output parameter.</span></span>  
  
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
  
### <a name="example"></a><span data-ttu-id="408a8-191">Пример</span><span class="sxs-lookup"><span data-stu-id="408a8-191">Example</span></span>  
 <span data-ttu-id="408a8-192">Для выполнения хранимой процедуры GetDocumentSummary код ADO.NET создает объекты <xref:System.Data.SqlClient.SqlConnection> и <xref:System.Data.SqlClient.SqlCommand> и получает сводку документа, которая хранится в виде типа больших значений.</span><span class="sxs-lookup"><span data-stu-id="408a8-192">The ADO.NET code creates <xref:System.Data.SqlClient.SqlConnection> and <xref:System.Data.SqlClient.SqlCommand> objects to execute the GetDocumentSummary stored procedure and retrieve the document summary, which is stored as a large value type.</span></span> <span data-ttu-id="408a8-193">Код передает значение входного параметра @DocumentID и отображает результаты, переданные в выходном параметре @DocumentSummary в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="408a8-193">The code passes a value for the @DocumentID input parameter, and displays the results passed back in the @DocumentSummary output parameter in the Console window.</span></span>  
  
 [!code-csharp[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="408a8-194">См. также:</span><span class="sxs-lookup"><span data-stu-id="408a8-194">See also</span></span>

- [<span data-ttu-id="408a8-195">Двоичные данные и данные большого объема SQL Server</span><span class="sxs-lookup"><span data-stu-id="408a8-195">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="408a8-196">Сопоставления типов данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="408a8-196">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="408a8-197">Операции данных SQL Server Data в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="408a8-197">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)
- [<span data-ttu-id="408a8-198">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="408a8-198">ADO.NET Overview</span></span>](../ado-net-overview.md)
