---
title: Ограничения ADO.NET
ms.date: 12/13/2019
description: Описание некоторых ограничений ADO.NET, которые могут возникнуть.
ms.openlocfilehash: b58fd3a9ea324e9c17ad21479e53e45f5982db9d
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450342"
---
# <a name="adonet-limitations"></a>Ограничения ADO.NET

Microsoft. Data. SQLite предоставляет реализации многих абстракций ADO.NET, но существуют некоторые ограничения.

## <a name="database-schema-information"></a>Сведения о схеме базы данных

Метаданные о результатах запроса доступны с помощью метода <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A>.

`DbConnection.GetSchema()` не реализована. Этот API не определен правильно, поэтому мы рекомендуем получать метаданные базы данных непосредственно с помощью стандартных API-интерфейсов SQLite, таких как таблица [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) и директива pragma [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) .

Дополнительные сведения см. в разделе [метаданные](metadata.md).

## <a name="systemtransactions"></a>System.Transactions

Microsoft. Data. SQLite пока еще не поддерживает System. Transactions. Вместо этого используйте транзакции ADO.NET. Дополнительные сведения см. в разделе [Transactions](transactions.md).

Предоставьте отзыв о нехватке поддержки для System. Transactions в [#13825](https://github.com/aspnet/EntityFrameworkCore/issues/13825)выпуска.

## <a name="data-adapters"></a>Адаптеры данных

`DbDataAdapter` еще не реализована Microsoft. Data. SQLite. Это означает, что вы можете использовать только ADO.NET `DataSet` и `DataTable` для загрузки данных и не обновлять их.

Чтобы оставить отзыв о реализации `DbDataAdapter`, используйте [#13838](https://github.com/aspnet/EntityFrameworkCore/issues/13838) выпуска.

## <a name="output-parameters"></a>Параметры вывода

SQLite не поддерживает выходные параметры.

## <a name="positional-parameters"></a>Позиционные параметры

Microsoft. Data. SQLite поддерживает только именованные [Параметры](parameters.md). Позиционированные параметры не поддерживаются.

## <a name="stored-procedures"></a>Хранимые процедуры

SQLite не поддерживает хранимые процедуры.

## <a name="isolation-levels"></a>Уровни изоляции

Уровни изоляции `Chaos` и `Snapshot` не поддерживаются в транзакциях SQLite.

## <a name="see-also"></a>См. также:

* [Ограничения Async](async.md)
* [Типы данных](types.md)
* [Tранзакции](transactions.md)
