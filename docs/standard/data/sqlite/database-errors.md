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
# <a name="database-errors"></a><span data-ttu-id="63fe0-103">Ошибки базы данных</span><span class="sxs-lookup"><span data-stu-id="63fe0-103">Database errors</span></span>

<span data-ttu-id="63fe0-104"><xref:Microsoft.Data.Sqlite.SqliteException> возникает при обнаружении ошибки SQLite.</span><span class="sxs-lookup"><span data-stu-id="63fe0-104"><xref:Microsoft.Data.Sqlite.SqliteException> is thrown when a SQLite error is encountered.</span></span> <span data-ttu-id="63fe0-105">Сообщение предоставляется SQLite.</span><span class="sxs-lookup"><span data-stu-id="63fe0-105">The message is provided by SQLite.</span></span> <span data-ttu-id="63fe0-106">Свойства `SqliteErrorCode` и `SqliteExtendedErrorCode` содержат [код результата](https://www.sqlite.org/rescode.html) SQLite ошибки.</span><span class="sxs-lookup"><span data-stu-id="63fe0-106">The `SqliteErrorCode` and `SqliteExtendedErrorCode` properties contain the SQLite [result code](https://www.sqlite.org/rescode.html) of the error.</span></span>

<span data-ttu-id="63fe0-107">Ошибки могут возникать при каждом взаимодействии Microsoft. Data. SQLite со встроенной библиотекой SQLite.</span><span class="sxs-lookup"><span data-stu-id="63fe0-107">Errors may be encountered any time the Microsoft.Data.Sqlite interacts with the native SQLite library.</span></span> <span data-ttu-id="63fe0-108">В следующем списке приведены распространенные сценарии, в которых могут возникать ошибки.</span><span class="sxs-lookup"><span data-stu-id="63fe0-108">The following list shows the common scenarios where errors can occur:</span></span>

* <span data-ttu-id="63fe0-109">Открытие соединения.</span><span class="sxs-lookup"><span data-stu-id="63fe0-109">Opening a connection.</span></span>
* <span data-ttu-id="63fe0-110">Начало транзакции.</span><span class="sxs-lookup"><span data-stu-id="63fe0-110">Beginning a transaction.</span></span>
* <span data-ttu-id="63fe0-111">выполнение команды;</span><span class="sxs-lookup"><span data-stu-id="63fe0-111">Executing a command.</span></span>
* <span data-ttu-id="63fe0-112">Вызов <xref:Microsoft.Data.Sqlite.SqliteDataReader.NextResult%2A>.</span><span class="sxs-lookup"><span data-stu-id="63fe0-112">Calling <xref:Microsoft.Data.Sqlite.SqliteDataReader.NextResult%2A>.</span></span>

<span data-ttu-id="63fe0-113">Тщательно продумайте, как ваше приложение будет выполнять эти ошибки.</span><span class="sxs-lookup"><span data-stu-id="63fe0-113">Consider carefully how your app will handle these errors.</span></span>

## <a name="locking-retries-and-timeouts"></a><span data-ttu-id="63fe0-114">Блокировка, повторные попытки и время ожидания</span><span class="sxs-lookup"><span data-stu-id="63fe0-114">Locking, retries, and timeouts</span></span>

<span data-ttu-id="63fe0-115">SQLite является агрессивным, когда дело доходит до блокировки таблиц и файлов базы данных.</span><span class="sxs-lookup"><span data-stu-id="63fe0-115">SQLite is aggressive when it comes to locking tables and database files.</span></span> <span data-ttu-id="63fe0-116">Если приложение включает любой параллельный доступ к базе данных, скорее всего, будут возникать ошибки занятости и блокировки.</span><span class="sxs-lookup"><span data-stu-id="63fe0-116">If your app enables any concurrent database access, you'll likely encounter busy and locked errors.</span></span> <span data-ttu-id="63fe0-117">Вы можете уменьшить количество ошибок, используя [общий кэш](connection-strings.md#cache) и [упреждающее ведение журнала](async.md).</span><span class="sxs-lookup"><span data-stu-id="63fe0-117">You can mitigate many errors by using a [shared cache](connection-strings.md#cache) and [write-ahead logging](async.md).</span></span>

<span data-ttu-id="63fe0-118">Всякий раз, когда приложение Microsoft. Data. SQLite обнаруживает ошибку занятости или блокировки, оно автоматически повторяется до тех пор, пока оно не будет выполнено или не будет достигнуто время ожидания команды.</span><span class="sxs-lookup"><span data-stu-id="63fe0-118">Whenever Microsoft.Data.Sqlite encounters a busy or locked error, it will automatically retry until it succeeds or the command timeout is reached.</span></span>

<span data-ttu-id="63fe0-119">Можно увеличить время ожидания команды, установив <xref:Microsoft.Data.Sqlite.SqliteCommand.CommandTimeout%2A>.</span><span class="sxs-lookup"><span data-stu-id="63fe0-119">You can increase the timeout of command by setting <xref:Microsoft.Data.Sqlite.SqliteCommand.CommandTimeout%2A>.</span></span> <span data-ttu-id="63fe0-120">По умолчанию время ожидания составляет 30 секунд.</span><span class="sxs-lookup"><span data-stu-id="63fe0-120">The default timeout is 30 seconds.</span></span> <span data-ttu-id="63fe0-121">Значение `0` означает отсутствие времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="63fe0-121">A value of `0` means no timeout.</span></span>

```csharp
// Retry for 60 seconds while locked
command.CommandTimeout = 60;
```

<span data-ttu-id="63fe0-122">В Microsoft. Data. SQLite иногда требуется создать неявный объект команды.</span><span class="sxs-lookup"><span data-stu-id="63fe0-122">Microsoft.Data.Sqlite sometimes needs to create an implicit command object.</span></span> <span data-ttu-id="63fe0-123">Например, во время BeginTransaction.</span><span class="sxs-lookup"><span data-stu-id="63fe0-123">For example, during BeginTransaction.</span></span> <span data-ttu-id="63fe0-124">Чтобы задать время ожидания для этих команд, используйте <xref:Microsoft.Data.Sqlite.SqliteConnection.DefaultTimeout%2A>.</span><span class="sxs-lookup"><span data-stu-id="63fe0-124">To set the timeout for these commands, use <xref:Microsoft.Data.Sqlite.SqliteConnection.DefaultTimeout%2A>.</span></span>

```csharp
// Set the default timeout of all commands on this connection
connection.DefaultTimeout = 60;
```

## <a name="see-also"></a><span data-ttu-id="63fe0-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="63fe0-125">See also</span></span>

* [<span data-ttu-id="63fe0-126">Коды ошибок SQLite</span><span class="sxs-lookup"><span data-stu-id="63fe0-126">SQLite Error Codes</span></span>](https://www.sqlite.org/rescode.html)
* [<span data-ttu-id="63fe0-127">Блокировка файлов в SQLite</span><span class="sxs-lookup"><span data-stu-id="63fe0-127">File Locking In SQLite</span></span>](https://www.sqlite.org/lockingv3.html)
* [<span data-ttu-id="63fe0-128">Режим общего кэша</span><span class="sxs-lookup"><span data-stu-id="63fe0-128">Shared-Cache Mode</span></span>](https://www.sqlite.org/sharedcache.html)
* [<span data-ttu-id="63fe0-129">Ведение журнала с упреждающей записью</span><span class="sxs-lookup"><span data-stu-id="63fe0-129">Write-Ahead Logging</span></span>](https://www.sqlite.org/wal.html)
