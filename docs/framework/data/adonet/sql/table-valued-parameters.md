---
title: Параметры, возвращающие табличные значения
ms.date: 10/12/2018
dev_langs:
- csharp
- vb
ms.assetid: 370c16d5-db7b-43e3-945b-ccaab35b739b
ms.openlocfilehash: d99cea1641dc61c1cae6d6b1634359211ce788ae
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452309"
---
# <a name="table-valued-parameters"></a><span data-ttu-id="10771-102">Параметры, возвращающие табличные значения</span><span class="sxs-lookup"><span data-stu-id="10771-102">Table-Valued Parameters</span></span>
<span data-ttu-id="10771-103">Параметры, возвращающие табличное значение, упрощают маршалинг нескольких строк данных из клиентского приложения в SQL Server, устраняя потребность в нескольких круговых путях или специальной серверной логике для обработки данных.</span><span class="sxs-lookup"><span data-stu-id="10771-103">Table-valued parameters provide an easy way to marshal multiple rows of data from a client application to SQL Server without requiring multiple round trips or special server-side logic for processing the data.</span></span> <span data-ttu-id="10771-104">Параметры, возвращающие табличное значение, можно использовать для инкапсуляции строк данных в клиентском приложении и их отправки на сервер единой параметризованной командой.</span><span class="sxs-lookup"><span data-stu-id="10771-104">You can use table-valued parameters to encapsulate rows of data in a client application and send the data to the server in a single parameterized command.</span></span> <span data-ttu-id="10771-105">Входящие строки данных хранятся в переменной таблицы, которой затем можно управлять с помощью Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="10771-105">The incoming data rows are stored in a table variable that can then be operated on by using Transact-SQL.</span></span>  
  
 <span data-ttu-id="10771-106">Доступ к значениям столбца в возвращающих табличное значение параметрах обеспечивается с помощью стандартных инструкций Transact-SQL SELECT.</span><span class="sxs-lookup"><span data-stu-id="10771-106">Column values in table-valued parameters can be accessed using standard Transact-SQL SELECT statements.</span></span> <span data-ttu-id="10771-107">Возвращающие табличное значение параметры строго типизированы, и проверка их структуры происходит автоматически.</span><span class="sxs-lookup"><span data-stu-id="10771-107">Table-valued parameters are strongly typed and their structure is automatically validated.</span></span> <span data-ttu-id="10771-108">Объем, занимаемый возвращающими табличное значение параметрами, ограничен только размерами памяти на сервере.</span><span class="sxs-lookup"><span data-stu-id="10771-108">The size of table-valued parameters is limited only by server memory.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="10771-109">В возвращающий табличное значение параметр нельзя вернуть данные.</span><span class="sxs-lookup"><span data-stu-id="10771-109">You cannot return data in a table-valued parameter.</span></span> <span data-ttu-id="10771-110">Возвращающие табличное значение параметры являются исключительно входными. Ключевое слово OUTPUT не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="10771-110">Table-valued parameters are input-only; the OUTPUT keyword is not supported.</span></span>  
  
 <span data-ttu-id="10771-111">Дополнительные сведения о возвращающих табличное значение параметрах см. в приведенных ниже ресурсах.</span><span class="sxs-lookup"><span data-stu-id="10771-111">For more information about table-valued parameters, see the following resources.</span></span>  
  
|<span data-ttu-id="10771-112">Ресурс</span><span class="sxs-lookup"><span data-stu-id="10771-112">Resource</span></span>|<span data-ttu-id="10771-113">Description</span><span class="sxs-lookup"><span data-stu-id="10771-113">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="10771-114">Использование параметров, возвращающих табличные значения (ядро СУБД)</span><span class="sxs-lookup"><span data-stu-id="10771-114">Use Table-Valued Parameters (Database Engine)</span></span>](/sql/relational-databases/tables/use-table-valued-parameters-database-engine)|<span data-ttu-id="10771-115">Описывается создание и использование возвращающих табличное значение параметров.</span><span class="sxs-lookup"><span data-stu-id="10771-115">Describes how to create and use table-valued parameters.</span></span>|  
|<span data-ttu-id="10771-116">[Определяемые пользователем табличные типы](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/bb522526(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="10771-116">[User-Defined Table Types](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/bb522526(v=sql.100))</span></span>|<span data-ttu-id="10771-117">Описывает использование определяемых пользователем табличных типов для объявления возвращающих табличное значение параметров.</span><span class="sxs-lookup"><span data-stu-id="10771-117">Describes user-defined table types that are used to declare table-valued parameters.</span></span>|  
  
## <a name="passing-multiple-rows-in-previous-versions-of-sql-server"></a><span data-ttu-id="10771-118">Передача нескольких строк в предыдущие версии SQL Server</span><span class="sxs-lookup"><span data-stu-id="10771-118">Passing Multiple Rows in Previous Versions of SQL Server</span></span>  
 <span data-ttu-id="10771-119">До появления в SQL Server 2008 параметров, возвращающих табличное значение, были ограниченны возможности передачи нескольких строк данных в хранимую процедуру или параметризованную команду SQL.</span><span class="sxs-lookup"><span data-stu-id="10771-119">Before table-valued parameters were introduced to SQL Server 2008, the options for passing multiple rows of data to a stored procedure or a parameterized SQL command were limited.</span></span> <span data-ttu-id="10771-120">При передаче нескольких строк на сервер разработчик может воспользоваться одним из описанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="10771-120">A developer could choose from the following options for passing multiple rows to the server:</span></span>  
  
- <span data-ttu-id="10771-121">Использование ряда отдельных параметров, представляющих значения в нескольких столбцах и строках данных.</span><span class="sxs-lookup"><span data-stu-id="10771-121">Use a series of individual parameters to represent the values in multiple columns and rows of data.</span></span> <span data-ttu-id="10771-122">Объем данных, который можно передать с помощью этого метода, ограничен максимально допустимым количеством параметров.</span><span class="sxs-lookup"><span data-stu-id="10771-122">The amount of data that can be passed by using this method is limited by the number of parameters allowed.</span></span> <span data-ttu-id="10771-123">В процедурах SQL Server можно использовать не более 2100 параметров.</span><span class="sxs-lookup"><span data-stu-id="10771-123">SQL Server procedures can have, at most, 2100 parameters.</span></span> <span data-ttu-id="10771-124">Для сборки отдельных значений в табличную переменную или временную таблицу для дальнейшей обработки необходимо реализовать логику на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="10771-124">Server-side logic is required to assemble these individual values into a table variable or a temporary table for processing.</span></span>  
  
- <span data-ttu-id="10771-125">Объединение нескольких значений данных в строки с разделителями или XML-документы и последующая передача этих текстовых значений в процедуру или инструкцию.</span><span class="sxs-lookup"><span data-stu-id="10771-125">Bundle multiple data values into delimited strings or XML documents and then pass those text values to a procedure or statement.</span></span> <span data-ttu-id="10771-126">При этом в процедуру или инструкцию необходимо включить логику для проверки структур данных и разделения значений.</span><span class="sxs-lookup"><span data-stu-id="10771-126">This requires the procedure or statement to include the logic necessary for validating the data structures and unbundling the values.</span></span>  
  
- <span data-ttu-id="10771-127">Создание ряда отдельных инструкций SQL для изменения данных в нескольких строках, например инструкций, создаваемых при вызове метода `Update` класса <xref:System.Data.SqlClient.SqlDataAdapter>.</span><span class="sxs-lookup"><span data-stu-id="10771-127">Create a series of individual SQL statements for data modifications that affect multiple rows, such as those created by calling the `Update` method of a <xref:System.Data.SqlClient.SqlDataAdapter>.</span></span> <span data-ttu-id="10771-128">Изменения можно отправить на сервер по отдельности или объединенными в группы.</span><span class="sxs-lookup"><span data-stu-id="10771-128">Changes can be submitted to the server individually or batched into groups.</span></span> <span data-ttu-id="10771-129">Тем не менее, даже при отправке в пакетах из нескольких инструкций, каждая инструкция выполняется на сервере отдельно.</span><span class="sxs-lookup"><span data-stu-id="10771-129">However, even when submitted in batches that contain multiple statements, each statement is executed separately on the server.</span></span>  
  
- <span data-ttu-id="10771-130">Чтобы загрузить несколько строк данных в таблицу, воспользуйтесь служебной программой `bcp` или объектом <xref:System.Data.SqlClient.SqlBulkCopy>.</span><span class="sxs-lookup"><span data-stu-id="10771-130">Use the `bcp` utility program or the <xref:System.Data.SqlClient.SqlBulkCopy> object to load many rows of data into a table.</span></span> <span data-ttu-id="10771-131">Хотя этот метод весьма эффективен, в нем не поддерживается обработка данных на стороне сервера, если данные не загружены во временную таблицу или табличную переменную.</span><span class="sxs-lookup"><span data-stu-id="10771-131">Although this technique is very efficient, it does not support server-side processing unless the data is loaded into a temporary table or table variable.</span></span>  
  
## <a name="creating-table-valued-parameter-types"></a><span data-ttu-id="10771-132">Создание типов параметров, возвращающих табличное значение</span><span class="sxs-lookup"><span data-stu-id="10771-132">Creating Table-Valued Parameter Types</span></span>  
 <span data-ttu-id="10771-133">Возвращающие табличное значение параметры основаны на строго типизированных табличных структурах, заданных с помощью инструкций Transact-SQL CREATE TYPE.</span><span class="sxs-lookup"><span data-stu-id="10771-133">Table-valued parameters are based on strongly-typed table structures that are defined by using Transact-SQL CREATE TYPE statements.</span></span> <span data-ttu-id="10771-134">Перед использованием в клиентских приложениях возвращающих табличное значение параметров в SQL Server необходимо создать табличный тип и определить структуру.</span><span class="sxs-lookup"><span data-stu-id="10771-134">You have to create a table type and define the structure in SQL Server before you can use table-valued parameters in your client applications.</span></span> <span data-ttu-id="10771-135">Дополнительные сведения о создании табличных типов см. в разделе [определяемые пользователем табличные типы](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/bb522526(v=sql.100)).</span><span class="sxs-lookup"><span data-stu-id="10771-135">For more information about creating table types, see [User-Defined Table Types](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/bb522526(v=sql.100)).</span></span>  
  
 <span data-ttu-id="10771-136">Приведенная ниже инструкция создает табличный тип с именем CategoryTableType, которая состоит из столбцов CategoryID и CategoryName.</span><span class="sxs-lookup"><span data-stu-id="10771-136">The following statement creates a table type named CategoryTableType that consists of CategoryID and CategoryName columns:</span></span>  
  
```sql
CREATE TYPE dbo.CategoryTableType AS TABLE  
    ( CategoryID int, CategoryName nvarchar(50) )  
```  
  
 <span data-ttu-id="10771-137">После создания табличного типа можно объявить возвращающие табличное значение параметры, основанные на этом типе.</span><span class="sxs-lookup"><span data-stu-id="10771-137">After you create a table type, you can declare table-valued parameters based on that type.</span></span> <span data-ttu-id="10771-138">В приведенном ниже фрагменте кода Transact-SQL демонстрируется объявление возвращающего табличное значение параметра в определении хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="10771-138">The following Transact-SQL fragment demonstrates how to declare a table-valued parameter in a stored procedure definition.</span></span> <span data-ttu-id="10771-139">Обратите внимание, что для объявления возвращающего табличное значение параметра необходимо использовать ключевое слово READONLY.</span><span class="sxs-lookup"><span data-stu-id="10771-139">Note that the READONLY keyword is required for declaring a table-valued parameter.</span></span>  
  
```sql
CREATE PROCEDURE usp_UpdateCategories   
    (@tvpNewCategories dbo.CategoryTableType READONLY)  
```  
  
## <a name="modifying-data-with-table-valued-parameters-transact-sql"></a><span data-ttu-id="10771-140">Изменение данных с помощью возвращающих табличное значение параметров (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="10771-140">Modifying Data with Table-Valued Parameters (Transact-SQL)</span></span>  
 <span data-ttu-id="10771-141">Возвращающие табличное значение параметры можно использовать для изменения данных на основе наборов, при котором в одной инструкции затрагивается несколько строк.</span><span class="sxs-lookup"><span data-stu-id="10771-141">Table-valued parameters can be used in set-based data modifications that affect multiple rows by executing a single statement.</span></span> <span data-ttu-id="10771-142">Например, можно выбрать все строки возвращающего табличное значение параметра и вставить их в таблицу базы данных или создать инструкцию UPDATE, соединив возвращающий табличное значение параметр с таблицей, которую необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="10771-142">For example, you can select all the rows in a table-valued parameter and insert them into a database table, or you can create an update statement by joining a table-valued parameter to the table you want to update.</span></span>  
  
 <span data-ttu-id="10771-143">В приведенной ниже инструкции Transact-SQL UPDATE демонстрируется соединение возвращающего табличное значение параметра с таблицей Categories.</span><span class="sxs-lookup"><span data-stu-id="10771-143">The following Transact-SQL UPDATE statement demonstrates how to use a table-valued parameter by joining it to the Categories table.</span></span> <span data-ttu-id="10771-144">При использовании возвращающего табличное значение параметра в операторе JOIN предложения FROM необходимо создать для этого параметра псевдоним; как показано здесь, для возвращающего табличное значение параметра используется псевдоним «ec»:</span><span class="sxs-lookup"><span data-stu-id="10771-144">When you use a table-valued parameter with a JOIN in a FROM clause, you must also alias it, as shown here, where the table-valued parameter is aliased as "ec":</span></span>  
  
```sql
UPDATE dbo.Categories  
    SET Categories.CategoryName = ec.CategoryName  
    FROM dbo.Categories INNER JOIN @tvpEditedCategories AS ec  
    ON dbo.Categories.CategoryID = ec.CategoryID;  
```  
  
 <span data-ttu-id="10771-145">В этом примере кода Transact-SQL демонстрируется выбор строк из возвращающего табличное значение параметра для выполнения инструкции INSERT в одной операции на основе набора данных.</span><span class="sxs-lookup"><span data-stu-id="10771-145">This Transact-SQL example demonstrates how to select rows from a table-valued parameter to perform an INSERT in a single set-based operation.</span></span>  
  
```sql
INSERT INTO dbo.Categories (CategoryID, CategoryName)  
    SELECT nc.CategoryID, nc.CategoryName FROM @tvpNewCategories AS nc;  
```  
  
## <a name="limitations-of-table-valued-parameters"></a><span data-ttu-id="10771-146">Ограничения возвращающих табличное значение параметров</span><span class="sxs-lookup"><span data-stu-id="10771-146">Limitations of Table-Valued Parameters</span></span>  
 <span data-ttu-id="10771-147">На использование возвращающих табличное значение параметров накладывается ряд указанных ниже ограничений.</span><span class="sxs-lookup"><span data-stu-id="10771-147">There are several limitations to table-valued parameters:</span></span>  
  
- <span data-ttu-id="10771-148">Возвращающие табличное значение параметры нельзя передавать [определяемым пользователем функциям CLR](/sql/relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions).</span><span class="sxs-lookup"><span data-stu-id="10771-148">You cannot pass table-valued parameters to [CLR user-defined functions](/sql/relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions).</span></span>  
  
- <span data-ttu-id="10771-149">Возвращающие табличное значение параметры можно индексировать только для поддержки ограничений UNIQUE и PRIMARY KEY.</span><span class="sxs-lookup"><span data-stu-id="10771-149">Table-valued parameters can only be indexed to support UNIQUE or PRIMARY KEY constraints.</span></span> <span data-ttu-id="10771-150">SQL Server не ведет статистику возвращающих табличные значения параметров.</span><span class="sxs-lookup"><span data-stu-id="10771-150">SQL Server does not maintain statistics on table-valued parameters.</span></span>  
  
- <span data-ttu-id="10771-151">В коде Transact-SQL возвращающие табличное значение параметры предназначены только для чтения.</span><span class="sxs-lookup"><span data-stu-id="10771-151">Table-valued parameters are read-only in Transact-SQL code.</span></span> <span data-ttu-id="10771-152">Значения столбцов в строках возвращающего табличное значение параметра нельзя обновить; также нельзя вставлять и удалять строки.</span><span class="sxs-lookup"><span data-stu-id="10771-152">You cannot update the column values in the rows of a table-valued parameter and you cannot insert or delete rows.</span></span> <span data-ttu-id="10771-153">Чтобы изменить данные, передаваемые в хранимую процедуру или параметризованную инструкцию через возвращающий табличное значение параметр, необходимо вставить данные во временную таблицу или табличную переменную.</span><span class="sxs-lookup"><span data-stu-id="10771-153">To modify the data that is passed to a stored procedure or parameterized statement in table-valued parameter, you must insert the data into a temporary table or into a table variable.</span></span>  
  
- <span data-ttu-id="10771-154">Для изменения структуры возвращающего табличное значение параметра нельзя использовать инструкции ALTER TABLE.</span><span class="sxs-lookup"><span data-stu-id="10771-154">You cannot use ALTER TABLE statements to modify the design of table-valued parameters.</span></span>  
  
## <a name="configuring-a-sqlparameter-example"></a><span data-ttu-id="10771-155">Пример настройки параметра SqlParameter</span><span class="sxs-lookup"><span data-stu-id="10771-155">Configuring a SqlParameter Example</span></span>  
 <span data-ttu-id="10771-156">Поставщик <xref:System.Data.SqlClient> поддерживает заполнение возвращающих табличное значение параметров из объектов <xref:System.Data.DataTable>, <xref:System.Data.Common.DbDataReader> или <xref:System.Collections.Generic.IEnumerable%601> \ <xref:Microsoft.SqlServer.Server.SqlDataRecord>.</span><span class="sxs-lookup"><span data-stu-id="10771-156"><xref:System.Data.SqlClient> supports populating table-valued parameters from <xref:System.Data.DataTable>, <xref:System.Data.Common.DbDataReader> or <xref:System.Collections.Generic.IEnumerable%601> \ <xref:Microsoft.SqlServer.Server.SqlDataRecord> objects.</span></span> <span data-ttu-id="10771-157">Необходимо указать имя типа возвращающего табличное значение параметра с помощью свойства <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> объекта <xref:System.Data.SqlClient.SqlParameter>.</span><span class="sxs-lookup"><span data-stu-id="10771-157">You must specify a type name for the table-valued parameter by using the <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> property of a <xref:System.Data.SqlClient.SqlParameter>.</span></span> <span data-ttu-id="10771-158">Значение `TypeName` должно совпадать с именем совместимого типа, созданного ранее на сервере.</span><span class="sxs-lookup"><span data-stu-id="10771-158">The `TypeName` must match the name of a compatible type previously created on the server.</span></span> <span data-ttu-id="10771-159">В приведенном ниже фрагменте кода демонстрируется настройка объекта <xref:System.Data.SqlClient.SqlParameter> для вставки данных.</span><span class="sxs-lookup"><span data-stu-id="10771-159">The following code fragment demonstrates how to configure <xref:System.Data.SqlClient.SqlParameter> to insert data.</span></span>  
 
<span data-ttu-id="10771-160">В следующем примере переменная `addedCategories` содержит <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="10771-160">In the following example, the `addedCategories` variable contains a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="10771-161">Чтобы увидеть, как заполняется переменная, см. примеры в следующем разделе [передача возвращающего табличное значение параметра хранимой процедуре](#passing).</span><span class="sxs-lookup"><span data-stu-id="10771-161">To see how the variable is populated, see the examples in the next section, [Passing a Table-Valued Parameter to a Stored Procedure](#passing).</span></span>

```csharp  
// Configure the command and parameter.  
SqlCommand insertCommand = new SqlCommand(sqlInsert, connection);  
SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
tvpParam.SqlDbType = SqlDbType.Structured;  
tvpParam.TypeName = "dbo.CategoryTableType";  
```  
  
```vb  
' Configure the command and parameter.  
Dim insertCommand As New SqlCommand(sqlInsert, connection)  
Dim tvpParam As SqlParameter = _  
   insertCommand.Parameters.AddWithValue( _  
  "@tvpNewCategories", addedCategories)  
tvpParam.SqlDbType = SqlDbType.Structured  
tvpParam.TypeName = "dbo.CategoryTableType"  
```  
  
 <span data-ttu-id="10771-162">Также для передачи строк данных в возвращающий табличное значение параметр можно использовать любой производный от <xref:System.Data.Common.DbDataReader> объект, как показано в этом фрагменте.</span><span class="sxs-lookup"><span data-stu-id="10771-162">You can also use any object derived from <xref:System.Data.Common.DbDataReader> to stream rows of data to a table-valued parameter, as shown in this fragment:</span></span>  
  
```csharp  
// Configure the SqlCommand and table-valued parameter.  
SqlCommand insertCommand = new SqlCommand("usp_InsertCategories", connection);  
insertCommand.CommandType = CommandType.StoredProcedure;  
SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", dataReader);  
tvpParam.SqlDbType = SqlDbType.Structured;  
```  
  
```vb  
' Configure the SqlCommand and table-valued parameter.  
Dim insertCommand As New SqlCommand("usp_InsertCategories", connection)  
insertCommand.CommandType = CommandType.StoredProcedure  
Dim tvpParam As SqlParameter = _  
  insertCommand.Parameters.AddWithValue("@tvpNewCategories", _  
  dataReader)  
tvpParam.SqlDbType = SqlDbType.Structured  
```  
  
## <a name="passing"></a><span data-ttu-id="10771-163">Передача возвращающего табличное значение параметра в хранимую процедуру</span><span class="sxs-lookup"><span data-stu-id="10771-163">Passing a Table-Valued Parameter to a Stored Procedure</span></span>  
 <span data-ttu-id="10771-164">В данном примере демонстрируется передача возвращающего табличное значение параметра в хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="10771-164">This example demonstrates how to pass table-valued parameter data to a stored procedure.</span></span> <span data-ttu-id="10771-165">Добавленные строки извлекаются в коде в новый объект <xref:System.Data.DataTable> с помощью метода <xref:System.Data.DataTable.GetChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="10771-165">The code extracts added rows into a new <xref:System.Data.DataTable> by using the <xref:System.Data.DataTable.GetChanges%2A> method.</span></span> <span data-ttu-id="10771-166">Затем в коде задается команда <xref:System.Data.SqlClient.SqlCommand>, присваивающая свойству <xref:System.Data.SqlClient.SqlCommand.CommandType%2A> значение <xref:System.Data.CommandType.StoredProcedure>.</span><span class="sxs-lookup"><span data-stu-id="10771-166">The code then defines a <xref:System.Data.SqlClient.SqlCommand>, setting the <xref:System.Data.SqlClient.SqlCommand.CommandType%2A> property to <xref:System.Data.CommandType.StoredProcedure>.</span></span> <span data-ttu-id="10771-167">Объект <xref:System.Data.SqlClient.SqlParameter> заполняется с помощью метода <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A>, а свойству <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> присваивается значение `Structured`.</span><span class="sxs-lookup"><span data-stu-id="10771-167">The <xref:System.Data.SqlClient.SqlParameter> is populated by using the <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> method and the <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> is set to `Structured`.</span></span> <span data-ttu-id="10771-168">Затем с помощью метода выполняется <xref:System.Data.SqlClient.SqlCommand> команда <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>.</span><span class="sxs-lookup"><span data-stu-id="10771-168">The <xref:System.Data.SqlClient.SqlCommand> is then executed by using the <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> method.</span></span>  
  
```csharp  
// Assumes connection is an open SqlConnection object.  
using (connection)  
{  
  // Create a DataTable with the modified rows.  
  DataTable addedCategories = CategoriesDataTable.GetChanges(DataRowState.Added);  

  // Configure the SqlCommand and SqlParameter.  
  SqlCommand insertCommand = new SqlCommand("usp_InsertCategories", connection);  
  insertCommand.CommandType = CommandType.StoredProcedure;  
  SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
  tvpParam.SqlDbType = SqlDbType.Structured;  

  // Execute the command.  
  insertCommand.ExecuteNonQuery();  
}  
```  
  
```vb  
' Assumes connection is an open SqlConnection object.  
Using connection  
   '  Create a DataTable with the modified rows.  
   Dim addedCategories As DataTable = _  
     CategoriesDataTable.GetChanges(DataRowState.Added)  
  
  ' Configure the SqlCommand and SqlParameter.  
   Dim insertCommand As New SqlCommand( _  
     "usp_InsertCategories", connection)  
   insertCommand.CommandType = CommandType.StoredProcedure  
   Dim tvpParam As SqlParameter = _  
     insertCommand.Parameters.AddWithValue( _  
     "@tvpNewCategories", addedCategories)  
   tvpParam.SqlDbType = SqlDbType.Structured  
  
   '  Execute the command.  
   insertCommand.ExecuteNonQuery()  
End Using  
```  
  
### <a name="passing-a-table-valued-parameter-to-a-parameterized-sql-statement"></a><span data-ttu-id="10771-169">Передача возвращающего табличное значение параметра в параметризованную инструкцию SQL</span><span class="sxs-lookup"><span data-stu-id="10771-169">Passing a Table-Valued Parameter to a Parameterized SQL Statement</span></span>  
 <span data-ttu-id="10771-170">В приведенном ниже примере кода демонстрируется вставка данных в таблицу dbo.Categories с помощью инструкции INSERT с вложенным запросом SELECT, для которого в качестве источника данных указан возвращающий табличное значение параметр.</span><span class="sxs-lookup"><span data-stu-id="10771-170">The following example demonstrates how to insert data into the dbo.Categories table by using an INSERT statement with a SELECT subquery that has a table-valued parameter as the data source.</span></span> <span data-ttu-id="10771-171">При передаче в параметризованную инструкцию SQL возвращающего табличное значение параметра необходимо указать для этого параметра имя типа с помощью нового свойства <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> класса <xref:System.Data.SqlClient.SqlParameter>.</span><span class="sxs-lookup"><span data-stu-id="10771-171">When passing a table-valued parameter to a parameterized SQL statement, you must specify a type name for the table-valued parameter by using the new <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> property of a <xref:System.Data.SqlClient.SqlParameter>.</span></span> <span data-ttu-id="10771-172">Значение `TypeName` должно совпадать с именем совместимого типа, созданного ранее на сервере.</span><span class="sxs-lookup"><span data-stu-id="10771-172">This `TypeName` must match the name of a compatible type previously created on the server.</span></span> <span data-ttu-id="10771-173">Для ссылки на структуру типов, заданную в dbo.CategoryTableType, в данном примере кода используется свойство `TypeName`.</span><span class="sxs-lookup"><span data-stu-id="10771-173">The code in this example uses the `TypeName` property to reference the type structure defined in dbo.CategoryTableType.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="10771-174">При указании значения для столбца идентификаторов в возвращающем табличное значение параметре необходимо выполнить для сеанса инструкцию SET IDENTITY_INSERT.</span><span class="sxs-lookup"><span data-stu-id="10771-174">If you supply a value for an identity column in a table-valued parameter, you must issue the SET IDENTITY_INSERT statement for the session.</span></span>  
  
```csharp  
// Assumes connection is an open SqlConnection.  
using (connection)  
{  
  // Create a DataTable with the modified rows.  
  DataTable addedCategories = CategoriesDataTable.GetChanges(DataRowState.Added);  

  // Define the INSERT-SELECT statement.  
  string sqlInsert =   
      "INSERT INTO dbo.Categories (CategoryID, CategoryName)"  
      + " SELECT nc.CategoryID, nc.CategoryName"  
      + " FROM @tvpNewCategories AS nc;"  

  // Configure the command and parameter.  
  SqlCommand insertCommand = new SqlCommand(sqlInsert, connection);  
  SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
  tvpParam.SqlDbType = SqlDbType.Structured;  
  tvpParam.TypeName = "dbo.CategoryTableType";  

  // Execute the command.  
  insertCommand.ExecuteNonQuery();  
}  
```  
  
```vb  
' Assumes connection is an open SqlConnection.  
Using connection  
  ' Create a DataTable with the modified rows.  
  Dim addedCategories As DataTable = _  
    CategoriesDataTable.GetChanges(DataRowState.Added)  
  
  ' Define the INSERT-SELECT statement.  
  Dim sqlInsert As String = _  
  "INSERT INTO dbo.Categories (CategoryID, CategoryName)" _  
  & " SELECT nc.CategoryID, nc.CategoryName" _  
  & " FROM @tvpNewCategories AS nc;"  
  
  ' Configure the command and parameter.  
  Dim insertCommand As New SqlCommand(sqlInsert, connection)  
  Dim tvpParam As SqlParameter = _  
     insertCommand.Parameters.AddWithValue( _  
    "@tvpNewCategories", addedCategories)  
  tvpParam.SqlDbType = SqlDbType.Structured  
  tvpParam.TypeName = "dbo.CategoryTableType"  
  
  ' Execute the query  
  insertCommand.ExecuteNonQuery()  
End Using  
```  
  
## <a name="streaming-rows-with-a-datareader"></a><span data-ttu-id="10771-175">Потоковая передача строк с помощью объекта DataReader</span><span class="sxs-lookup"><span data-stu-id="10771-175">Streaming Rows with a DataReader</span></span>  
 <span data-ttu-id="10771-176">Также для передачи строк данных в возвращающий табличное значение параметр можно использовать любой производный от <xref:System.Data.Common.DbDataReader> объект.</span><span class="sxs-lookup"><span data-stu-id="10771-176">You can also use any object derived from <xref:System.Data.Common.DbDataReader> to stream rows of data to a table-valued parameter.</span></span> <span data-ttu-id="10771-177">В приведенном ниже фрагменте кода демонстрируется загрузка данных из базы данных Oracle с помощью <xref:System.Data.OracleClient.OracleCommand> и <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="10771-177">The following code fragment demonstrates retrieving data from an Oracle database by using an <xref:System.Data.OracleClient.OracleCommand> and an <xref:System.Data.OracleClient.OracleDataReader>.</span></span> <span data-ttu-id="10771-178">Затем в коде настраивается команда <xref:System.Data.SqlClient.SqlCommand>, предназначенная для вызова хранимой процедуры с одним входным параметром.</span><span class="sxs-lookup"><span data-stu-id="10771-178">The code then configures a <xref:System.Data.SqlClient.SqlCommand> to invoke a stored procedure with a single input parameter.</span></span> <span data-ttu-id="10771-179">Свойству <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> класса <xref:System.Data.SqlClient.SqlParameter> присваивается значение `Structured`.</span><span class="sxs-lookup"><span data-stu-id="10771-179">The <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> property of the <xref:System.Data.SqlClient.SqlParameter> is set to `Structured`.</span></span> <span data-ttu-id="10771-180">Метод <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> передает результирующий набор `OracleDataReader` в хранимую процедуру в виде возвращающего табличное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="10771-180">The <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> passes the `OracleDataReader` result set to the stored procedure as a table-valued parameter.</span></span>  
  
```csharp  
// Assumes connection is an open SqlConnection.  
// Retrieve data from Oracle.  
OracleCommand selectCommand = new OracleCommand(  
   "Select CategoryID, CategoryName FROM Categories;",  
   oracleConnection);  
OracleDataReader oracleReader = selectCommand.ExecuteReader(  
   CommandBehavior.CloseConnection);  
  
 // Configure the SqlCommand and table-valued parameter.  
 SqlCommand insertCommand = new SqlCommand(  
   "usp_InsertCategories", connection);  
 insertCommand.CommandType = CommandType.StoredProcedure;  
 SqlParameter tvpParam =  
    insertCommand.Parameters.AddWithValue(  
    "@tvpNewCategories", oracleReader);  
 tvpParam.SqlDbType = SqlDbType.Structured;  
  
 // Execute the command.  
 insertCommand.ExecuteNonQuery();  
```  
  
```vb  
' Assumes connection is an open SqlConnection.  
' Retrieve data from Oracle.  
Dim selectCommand As New OracleCommand( _  
  "Select CategoryID, CategoryName FROM Categories;", _  
  oracleConnection)  
Dim oracleReader As OracleDataReader = _  
  selectCommand.ExecuteReader(CommandBehavior.CloseConnection)  
  
' Configure SqlCommand and table-valued parameter.  
Dim insertCommand As New SqlCommand("usp_InsertCategories", connection)  
insertCommand.CommandType = CommandType.StoredProcedure  
Dim tvpParam As SqlParameter = _  
  insertCommand.Parameters.AddWithValue("@tvpNewCategories", _  
  oracleReader)  
tvpParam.SqlDbType = SqlDbType.Structured  
  
' Execute the command.  
insertCommand.ExecuteNonQuery()  
```  
  
## <a name="see-also"></a><span data-ttu-id="10771-181">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="10771-181">See also</span></span>

- [<span data-ttu-id="10771-182">Настройка параметров и типы данных параметров</span><span class="sxs-lookup"><span data-stu-id="10771-182">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="10771-183">Команды и параметры</span><span class="sxs-lookup"><span data-stu-id="10771-183">Commands and Parameters</span></span>](../commands-and-parameters.md)
- [<span data-ttu-id="10771-184">Параметры DataAdapter</span><span class="sxs-lookup"><span data-stu-id="10771-184">DataAdapter Parameters</span></span>](../dataadapter-parameters.md)
- [<span data-ttu-id="10771-185">Операции данных SQL Server Data в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="10771-185">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)
- [<span data-ttu-id="10771-186">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="10771-186">ADO.NET Overview</span></span>](../ado-net-overview.md)
