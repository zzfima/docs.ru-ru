---
title: Metadata
ms.date: 12/13/2019
description: Узнайте, как получить метаданные о базе данных.
ms.openlocfilehash: b2f2704a748627d9943943fa2fa7b1b7e9f3007f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450432"
---
# <a name="metadata"></a><span data-ttu-id="68d1f-103">Metadata</span><span class="sxs-lookup"><span data-stu-id="68d1f-103">Metadata</span></span>

<span data-ttu-id="68d1f-104">Существует два интерфейса API для получения метаданных в ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="68d1f-104">There are two APIs for retrieving metadata in ADO.NET.</span></span> <span data-ttu-id="68d1f-105">Один извлекает метаданные о результатах запроса.</span><span class="sxs-lookup"><span data-stu-id="68d1f-105">One retrieves metadata about query results.</span></span> <span data-ttu-id="68d1f-106">Другой извлекает метаданные о схеме базы данных.</span><span class="sxs-lookup"><span data-stu-id="68d1f-106">The other retrieves metadata about the database schema.</span></span>

## <a name="query-result-metadata"></a><span data-ttu-id="68d1f-107">Метаданные результатов запроса</span><span class="sxs-lookup"><span data-stu-id="68d1f-107">Query result metadata</span></span>

<span data-ttu-id="68d1f-108">Метаданные о результатах запроса можно получить с помощью метода <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> в `SqliteDataReader`.</span><span class="sxs-lookup"><span data-stu-id="68d1f-108">You can retrieve metadata about the results of a query using the <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> method on `SqliteDataReader`.</span></span> <span data-ttu-id="68d1f-109">Возвращаемый <xref:System.Data.DataTable> содержит следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="68d1f-109">The returned <xref:System.Data.DataTable> contains the following columns:</span></span>

| <span data-ttu-id="68d1f-110">Столбец</span><span class="sxs-lookup"><span data-stu-id="68d1f-110">Column</span></span>             | <span data-ttu-id="68d1f-111">Тип</span><span class="sxs-lookup"><span data-stu-id="68d1f-111">Type</span></span>    | <span data-ttu-id="68d1f-112">Описание</span><span class="sxs-lookup"><span data-stu-id="68d1f-112">Description</span></span>                                                               |
| ------------------ | ------- | ------------------------------------------------------------------------- |
| `AllowDBNull`      | <span data-ttu-id="68d1f-113">Логическое значение .</span><span class="sxs-lookup"><span data-stu-id="68d1f-113">Boolean</span></span> | <span data-ttu-id="68d1f-114">Значение true, если исходный столбец может иметь значение NULL.</span><span class="sxs-lookup"><span data-stu-id="68d1f-114">True if the origin column may be NULL.</span></span>                                    |
| `BaseCatalogName`  | <span data-ttu-id="68d1f-115">Строка</span><span class="sxs-lookup"><span data-stu-id="68d1f-115">String</span></span>  | <span data-ttu-id="68d1f-116">Имя базы данных исходного столбца.</span><span class="sxs-lookup"><span data-stu-id="68d1f-116">The name of the origin column's database.</span></span> <span data-ttu-id="68d1f-117">Для выражений всегда имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="68d1f-117">Always NULL for expressions.</span></span>    |
| `BaseColumnName`   | <span data-ttu-id="68d1f-118">Строка</span><span class="sxs-lookup"><span data-stu-id="68d1f-118">String</span></span>  | <span data-ttu-id="68d1f-119">Имя исходного столбца, не являющийся псевдонимом.</span><span class="sxs-lookup"><span data-stu-id="68d1f-119">The unaliased name of the origin column.</span></span> <span data-ttu-id="68d1f-120">Для выражений всегда имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="68d1f-120">Always NULL for expressions.</span></span>    |
| `BaseSchemaName`   | <span data-ttu-id="68d1f-121">Строка</span><span class="sxs-lookup"><span data-stu-id="68d1f-121">String</span></span>  | <span data-ttu-id="68d1f-122">Всегда имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="68d1f-122">Always NULL.</span></span> <span data-ttu-id="68d1f-123">SQLite не поддерживает схемы.</span><span class="sxs-lookup"><span data-stu-id="68d1f-123">SQLite doesn't support schemas.</span></span>                              |
| `BaseServerName`   | <span data-ttu-id="68d1f-124">Строка</span><span class="sxs-lookup"><span data-stu-id="68d1f-124">String</span></span>  | <span data-ttu-id="68d1f-125">Путь к файлу базы данных, указанному в строке подключения.</span><span class="sxs-lookup"><span data-stu-id="68d1f-125">The path to the database file specified in the connection string.</span></span>         |
| `BaseTableName`    | <span data-ttu-id="68d1f-126">Строка</span><span class="sxs-lookup"><span data-stu-id="68d1f-126">String</span></span>  | <span data-ttu-id="68d1f-127">Имя таблицы исходного столбца.</span><span class="sxs-lookup"><span data-stu-id="68d1f-127">The name of the origin column's table.</span></span> <span data-ttu-id="68d1f-128">Для выражений всегда имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="68d1f-128">Always NULL for expressions.</span></span>       |
| `ColumnName`       | <span data-ttu-id="68d1f-129">Строка</span><span class="sxs-lookup"><span data-stu-id="68d1f-129">String</span></span>  | <span data-ttu-id="68d1f-130">Имя или псевдоним столбца в результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="68d1f-130">The name or alias of the column in the result set.</span></span>                        |
| `ColumnOrdinal`    | <span data-ttu-id="68d1f-131">Int32</span><span class="sxs-lookup"><span data-stu-id="68d1f-131">Int32</span></span>   | <span data-ttu-id="68d1f-132">Порядковый номер столбца в результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="68d1f-132">The ordinal of the column in the result set.</span></span>                              |
| `ColumnSize`       | <span data-ttu-id="68d1f-133">Int32</span><span class="sxs-lookup"><span data-stu-id="68d1f-133">Int32</span></span>   | <span data-ttu-id="68d1f-134">Всегда равно-1.</span><span class="sxs-lookup"><span data-stu-id="68d1f-134">Always -1.</span></span> <span data-ttu-id="68d1f-135">Это может измениться в будущих версиях `Microsoft.Data.Sqlite`.</span><span class="sxs-lookup"><span data-stu-id="68d1f-135">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span>   |
| `DataType`         | <span data-ttu-id="68d1f-136">Тип</span><span class="sxs-lookup"><span data-stu-id="68d1f-136">Type</span></span>    | <span data-ttu-id="68d1f-137">Тип данных .NET по умолчанию для столбца.</span><span class="sxs-lookup"><span data-stu-id="68d1f-137">The default .NET data type of the column.</span></span>                                 |
| `DataTypeName`     | <span data-ttu-id="68d1f-138">Строка</span><span class="sxs-lookup"><span data-stu-id="68d1f-138">String</span></span>  | <span data-ttu-id="68d1f-139">Тип данных SQLite столбца.</span><span class="sxs-lookup"><span data-stu-id="68d1f-139">The SQLite data type of the column.</span></span>                                       |
| `IsAliased`        | <span data-ttu-id="68d1f-140">Логическое значение .</span><span class="sxs-lookup"><span data-stu-id="68d1f-140">Boolean</span></span> | <span data-ttu-id="68d1f-141">Значение true, если имя столбца имеет псевдоним в результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="68d1f-141">True if the column name is aliased in the result set.</span></span>                     |
| `IsAutoIncrement`  | <span data-ttu-id="68d1f-142">Логическое значение .</span><span class="sxs-lookup"><span data-stu-id="68d1f-142">Boolean</span></span> | <span data-ttu-id="68d1f-143">Значение true, если исходный столбец был создан с помощью ключевого слова AutoIncrement.</span><span class="sxs-lookup"><span data-stu-id="68d1f-143">True if the origin column was created with the AUTOINCREMENT keyword.</span></span>     |
| `IsExpression`     | <span data-ttu-id="68d1f-144">Логическое значение .</span><span class="sxs-lookup"><span data-stu-id="68d1f-144">Boolean</span></span> | <span data-ttu-id="68d1f-145">Значение true, если столбец поступает из выражения в запросе.</span><span class="sxs-lookup"><span data-stu-id="68d1f-145">True if the column originates from an expression in the query.</span></span>            |
| `IsKey`            | <span data-ttu-id="68d1f-146">Логическое значение .</span><span class="sxs-lookup"><span data-stu-id="68d1f-146">Boolean</span></span> | <span data-ttu-id="68d1f-147">Значение true, если исходный столбец является частью ПЕРВИЧного ключа.</span><span class="sxs-lookup"><span data-stu-id="68d1f-147">True if the origin column is part of the PRIMARY KEY.</span></span>                     |
| `IsUnique`         | <span data-ttu-id="68d1f-148">Логическое значение .</span><span class="sxs-lookup"><span data-stu-id="68d1f-148">Boolean</span></span> | <span data-ttu-id="68d1f-149">Значение true, если исходный столбец УНИКАЛЕН.</span><span class="sxs-lookup"><span data-stu-id="68d1f-149">True if the origin column is UNIQUE.</span></span>                                      |
| `NumericPrecision` | <span data-ttu-id="68d1f-150">Int16</span><span class="sxs-lookup"><span data-stu-id="68d1f-150">Int16</span></span>   | <span data-ttu-id="68d1f-151">Всегда имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="68d1f-151">Always NULL.</span></span> <span data-ttu-id="68d1f-152">Это может измениться в будущих версиях `Microsoft.Data.Sqlite`.</span><span class="sxs-lookup"><span data-stu-id="68d1f-152">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span> |
| `NumericScale`     | <span data-ttu-id="68d1f-153">Int16</span><span class="sxs-lookup"><span data-stu-id="68d1f-153">Int16</span></span>   | <span data-ttu-id="68d1f-154">Всегда имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="68d1f-154">Always NULL.</span></span> <span data-ttu-id="68d1f-155">Это может измениться в будущих версиях `Microsoft.Data.Sqlite`.</span><span class="sxs-lookup"><span data-stu-id="68d1f-155">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span> |

<span data-ttu-id="68d1f-156">В следующем примере показано, как использовать `GetSchemaTable` для создания отладочной строки, которая показывает метаданные о результате:</span><span class="sxs-lookup"><span data-stu-id="68d1f-156">The following example shows how to use `GetSchemaTable` to create a debug string that shows metadata about a result:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ResultMetadataSample/Program.cs?name=snippet_ResultMetadata)]

<span data-ttu-id="68d1f-157">Например, в этом запросе будет выдаваться Следующая отладочная строка:</span><span class="sxs-lookup"><span data-stu-id="68d1f-157">For example, this query would produce the following debug string:</span></span>

```sql
SELECT id AS post_id,
       title,
       body,
       random() AS random
FROM post
```

```output
post.id AS post_id INTEGER PRIMARY KEY AUTOINCREMENT
post.title TEXT NOT NULL UNIQUE
post.body TEXT
(expression) AS random BLOB
```

## <a name="schema-metadata"></a><span data-ttu-id="68d1f-158">Метаданные схемы</span><span class="sxs-lookup"><span data-stu-id="68d1f-158">Schema metadata</span></span>

<span data-ttu-id="68d1f-159">Microsoft. Data. SQLite не реализует метод GetSchema для DbConnection.</span><span class="sxs-lookup"><span data-stu-id="68d1f-159">Microsoft.Data.Sqlite doesn't implement the GetSchema method on DbConnection.</span></span> <span data-ttu-id="68d1f-160">Вместо этого можно выполнить запрос непосредственно к сведениям о схеме с помощью [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) таблицы и директивы pragma, таких как [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) и [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list).</span><span class="sxs-lookup"><span data-stu-id="68d1f-160">Instead, you can query directly for schema information using the [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) table and PRAGMA statements like [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) and [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list).</span></span>

<span data-ttu-id="68d1f-161">Например, этот запрос извлечет метаданные обо всех столбцах в базе данных.</span><span class="sxs-lookup"><span data-stu-id="68d1f-161">For example, this query will retrieve metadata about all the columns in the database.</span></span>

```sql
SELECT t.name AS tbl_name, c.name, c.type, c.notnull, c.dflt_value, c.pk
FROM sqlite_master AS t,
     pragma_table_info(t.name) AS c
WHERE t.type = 'table';
```

## <a name="see-also"></a><span data-ttu-id="68d1f-162">См. также:</span><span class="sxs-lookup"><span data-stu-id="68d1f-162">See also</span></span>

* [<span data-ttu-id="68d1f-163">Хранение схемы базы данных SQL</span><span class="sxs-lookup"><span data-stu-id="68d1f-163">Storage of the SQL Database Schema</span></span>](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema)
* [<span data-ttu-id="68d1f-164">Директивы PRAGMA</span><span class="sxs-lookup"><span data-stu-id="68d1f-164">PRAGMA Statements</span></span>](https://www.sqlite.org/pragma.html)
* [<span data-ttu-id="68d1f-165">Типы данных</span><span class="sxs-lookup"><span data-stu-id="68d1f-165">Data types</span></span>](types.md)
