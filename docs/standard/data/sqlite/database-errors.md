---
title: Ошибки базы данных
ms.date: 12/13/2019
description: Описывает способ обработки ошибок и отработок базы данных библиотекой.
ms.openlocfilehash: 9a613b6f94a89dc40e627c14f46836be77080035
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450492"
---
# <a name="database-errors"></a>Ошибки базы данных

<xref:Microsoft.Data.Sqlite.SqliteException> возникает при обнаружении ошибки SQLite. Сообщение предоставляется SQLite. Свойства `SqliteErrorCode` и `SqliteExtendedErrorCode` содержат [код результата](https://www.sqlite.org/rescode.html) SQLite ошибки.

Ошибки могут возникать при каждом взаимодействии Microsoft. Data. SQLite со встроенной библиотекой SQLite. В следующем списке приведены распространенные сценарии, в которых могут возникать ошибки.

* Открытие соединения.
* Начало транзакции.
* выполнение команды;
* Вызов <xref:Microsoft.Data.Sqlite.SqliteDataReader.NextResult%2A>.

Тщательно продумайте, как ваше приложение будет выполнять эти ошибки.

## <a name="locking-retries-and-timeouts"></a>Блокировка, повторные попытки и время ожидания

SQLite является агрессивным, когда дело доходит до блокировки таблиц и файлов базы данных. Если приложение включает любой параллельный доступ к базе данных, скорее всего, будут возникать ошибки занятости и блокировки. Вы можете уменьшить количество ошибок, используя [общий кэш](connection-strings.md#cache) и [упреждающее ведение журнала](async.md).

Всякий раз, когда приложение Microsoft. Data. SQLite обнаруживает ошибку занятости или блокировки, оно автоматически повторяется до тех пор, пока оно не будет выполнено или не будет достигнуто время ожидания команды.

Можно увеличить время ожидания команды, установив <xref:Microsoft.Data.Sqlite.SqliteCommand.CommandTimeout%2A>. По умолчанию время ожидания составляет 30 секунд. Значение `0` означает отсутствие времени ожидания.

```csharp
// Retry for 60 seconds while locked
command.CommandTimeout = 60;
```

В Microsoft. Data. SQLite иногда требуется создать неявный объект команды. Например, во время BeginTransaction. Чтобы задать время ожидания для этих команд, используйте <xref:Microsoft.Data.Sqlite.SqliteConnection.DefaultTimeout%2A>.

```csharp
// Set the default timeout of all commands on this connection
connection.DefaultTimeout = 60;
```

## <a name="see-also"></a>См. также:

* [Коды ошибок SQLite](https://www.sqlite.org/rescode.html)
* [Блокировка файлов в SQLite](https://www.sqlite.org/lockingv3.html)
* [Режим общего кэша](https://www.sqlite.org/sharedcache.html)
* [Ведение журнала с упреждающей записью](https://www.sqlite.org/wal.html)
