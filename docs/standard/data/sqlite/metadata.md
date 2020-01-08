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
# <a name="metadata"></a>Metadata

Существует два интерфейса API для получения метаданных в ADO.NET. Один извлекает метаданные о результатах запроса. Другой извлекает метаданные о схеме базы данных.

## <a name="query-result-metadata"></a>Метаданные результатов запроса

Метаданные о результатах запроса можно получить с помощью метода <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> в `SqliteDataReader`. Возвращаемый <xref:System.Data.DataTable> содержит следующие столбцы:

| Столбец             | Тип    | Описание                                                               |
| ------------------ | ------- | ------------------------------------------------------------------------- |
| `AllowDBNull`      | Логическое значение . | Значение true, если исходный столбец может иметь значение NULL.                                    |
| `BaseCatalogName`  | Строка  | Имя базы данных исходного столбца. Для выражений всегда имеет значение NULL.    |
| `BaseColumnName`   | Строка  | Имя исходного столбца, не являющийся псевдонимом. Для выражений всегда имеет значение NULL.    |
| `BaseSchemaName`   | Строка  | Всегда имеет значение NULL. SQLite не поддерживает схемы.                              |
| `BaseServerName`   | Строка  | Путь к файлу базы данных, указанному в строке подключения.         |
| `BaseTableName`    | Строка  | Имя таблицы исходного столбца. Для выражений всегда имеет значение NULL.       |
| `ColumnName`       | Строка  | Имя или псевдоним столбца в результирующем наборе.                        |
| `ColumnOrdinal`    | Int32   | Порядковый номер столбца в результирующем наборе.                              |
| `ColumnSize`       | Int32   | Всегда равно-1. Это может измениться в будущих версиях `Microsoft.Data.Sqlite`.   |
| `DataType`         | Тип    | Тип данных .NET по умолчанию для столбца.                                 |
| `DataTypeName`     | Строка  | Тип данных SQLite столбца.                                       |
| `IsAliased`        | Логическое значение . | Значение true, если имя столбца имеет псевдоним в результирующем наборе.                     |
| `IsAutoIncrement`  | Логическое значение . | Значение true, если исходный столбец был создан с помощью ключевого слова AutoIncrement.     |
| `IsExpression`     | Логическое значение . | Значение true, если столбец поступает из выражения в запросе.            |
| `IsKey`            | Логическое значение . | Значение true, если исходный столбец является частью ПЕРВИЧного ключа.                     |
| `IsUnique`         | Логическое значение . | Значение true, если исходный столбец УНИКАЛЕН.                                      |
| `NumericPrecision` | Int16   | Всегда имеет значение NULL. Это может измениться в будущих версиях `Microsoft.Data.Sqlite`. |
| `NumericScale`     | Int16   | Всегда имеет значение NULL. Это может измениться в будущих версиях `Microsoft.Data.Sqlite`. |

В следующем примере показано, как использовать `GetSchemaTable` для создания отладочной строки, которая показывает метаданные о результате:

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ResultMetadataSample/Program.cs?name=snippet_ResultMetadata)]

Например, в этом запросе будет выдаваться Следующая отладочная строка:

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

## <a name="schema-metadata"></a>Метаданные схемы

Microsoft. Data. SQLite не реализует метод GetSchema для DbConnection. Вместо этого можно выполнить запрос непосредственно к сведениям о схеме с помощью [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) таблицы и директивы pragma, таких как [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) и [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list).

Например, этот запрос извлечет метаданные обо всех столбцах в базе данных.

```sql
SELECT t.name AS tbl_name, c.name, c.type, c.notnull, c.dflt_value, c.pk
FROM sqlite_master AS t,
     pragma_table_info(t.name) AS c
WHERE t.type = 'table';
```

## <a name="see-also"></a>См. также:

* [Хранение схемы базы данных SQL](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema)
* [Директивы PRAGMA](https://www.sqlite.org/pragma.html)
* [Типы данных](types.md)
