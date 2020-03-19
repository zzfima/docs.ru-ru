---
title: Строки подключения
ms.date: 12/13/2019
description: Поддерживаемые ключевые слова и значения строк соединения.
ms.openlocfilehash: bb54d152bac62a86c2a49192cf678a745159164e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401199"
---
# <a name="connection-strings"></a><span data-ttu-id="ad3fd-103">Строки подключения</span><span class="sxs-lookup"><span data-stu-id="ad3fd-103">Connection strings</span></span>

<span data-ttu-id="ad3fd-104">Строка соединения используется для определения того, как подключиться к базе данных.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-104">A connection string is used to specify how to connect to the database.</span></span> <span data-ttu-id="ad3fd-105">Строки подключения в Microsoft.Data.Sqlite следуют стандартному [ADO.NET синтаксису](../../../framework/data/adonet/connection-strings.md) как разделенному на запятой списку ключевых слов и значений.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-105">Connection strings in Microsoft.Data.Sqlite follow the standard [ADO.NET syntax](../../../framework/data/adonet/connection-strings.md) as a semicolon-separated list of keywords and values.</span></span>

## <a name="keywords"></a><span data-ttu-id="ad3fd-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="ad3fd-106">Keywords</span></span>

<span data-ttu-id="ad3fd-107">Следующие ключевые слова строки соединения могут быть использованы с Microsoft.Data.Sqlite:</span><span class="sxs-lookup"><span data-stu-id="ad3fd-107">The following connection string keywords can be used with Microsoft.Data.Sqlite:</span></span>

### <a name="data-source"></a><span data-ttu-id="ad3fd-108">Источник данных</span><span class="sxs-lookup"><span data-stu-id="ad3fd-108">Data source</span></span>

<span data-ttu-id="ad3fd-109">Путь к файлу базы данных.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-109">The path to the database file.</span></span> <span data-ttu-id="ad3fd-110">*DataSource* (без места) и *Filename* являются псевдонимами этого ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-110">*DataSource* (without a space) and *Filename* are aliases of this keyword.</span></span>

<span data-ttu-id="ad3fd-111">По отношению к текущему рабочему каталогу S'Lite обрабатывает пути.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-111">SQLite treats paths relative to the current working directory.</span></span> <span data-ttu-id="ad3fd-112">Можно также указать абсолютные пути.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-112">Absolute paths can also be specified.</span></span>

<span data-ttu-id="ad3fd-113">Если **пустой,** S'Lite создает временную базу данных на диске, которая удаляется при закрытии соединения.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-113">If **empty**, SQLite creates a temporary on-disk database that's deleted when the connection is closed.</span></span>

<span data-ttu-id="ad3fd-114">Если `:memory:`используется база данных в памяти.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-114">If `:memory:`, an in-memory database is used.</span></span> <span data-ttu-id="ad3fd-115">Для получения дополнительной [информации см.](in-memory-databases.md)</span><span class="sxs-lookup"><span data-stu-id="ad3fd-115">For more information, see [In-Memory databases](in-memory-databases.md).</span></span>

<span data-ttu-id="ad3fd-116">Пути, начинаюющиеся `|DataDirectory|` с строки замены, обрабатываются так же, как и относительные пути.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-116">Paths that start with the `|DataDirectory|` substitution string are treated the same as relative paths.</span></span> <span data-ttu-id="ad3fd-117">Если установлен, пути сделаны относительно значения свойства домена приложения DataDirectory.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-117">If set, paths are made relative to the DataDirectory application domain property value.</span></span>

<span data-ttu-id="ad3fd-118">Это ключевое слово также поддерживает [URI Filenames](https://www.sqlite.org/uri.html).</span><span class="sxs-lookup"><span data-stu-id="ad3fd-118">This keyword also supports [URI Filenames](https://www.sqlite.org/uri.html).</span></span>

### <a name="mode"></a><span data-ttu-id="ad3fd-119">Режим</span><span class="sxs-lookup"><span data-stu-id="ad3fd-119">Mode</span></span>

<span data-ttu-id="ad3fd-120">Режим подключения.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-120">The connection mode.</span></span>

| <span data-ttu-id="ad3fd-121">Значение</span><span class="sxs-lookup"><span data-stu-id="ad3fd-121">Value</span></span>           | <span data-ttu-id="ad3fd-122">Описание</span><span class="sxs-lookup"><span data-stu-id="ad3fd-122">Description</span></span>                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="ad3fd-123">ReadWriteCreate</span><span class="sxs-lookup"><span data-stu-id="ad3fd-123">ReadWriteCreate</span></span> | <span data-ttu-id="ad3fd-124">Открывает базу данных для чтения и письма и создает ее, если ее не существует.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-124">Opens the database for reading and writing, and creates it if it doesn't exist.</span></span> <span data-ttu-id="ad3fd-125">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-125">This is the default.</span></span> |
| <span data-ttu-id="ad3fd-126">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="ad3fd-126">ReadWrite</span></span>       | <span data-ttu-id="ad3fd-127">Открывает базу данных для чтения и письма.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-127">Opens the database for reading and writing.</span></span>                                                        |
| <span data-ttu-id="ad3fd-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="ad3fd-128">ReadOnly</span></span>        | <span data-ttu-id="ad3fd-129">Открывает базу данных в режиме только для чтения.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-129">Opens the database in read-only mode.</span></span>                                                              |
| <span data-ttu-id="ad3fd-130">Память</span><span class="sxs-lookup"><span data-stu-id="ad3fd-130">Memory</span></span>          | <span data-ttu-id="ad3fd-131">Открывает базу данных в памяти.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-131">Opens an in-memory database.</span></span>                                                                       |

### <a name="cache"></a><span data-ttu-id="ad3fd-132">Кэш</span><span class="sxs-lookup"><span data-stu-id="ad3fd-132">Cache</span></span>

<span data-ttu-id="ad3fd-133">Режим кэширования, используемый соединением.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-133">The caching mode used by the connection.</span></span>

| <span data-ttu-id="ad3fd-134">Значение</span><span class="sxs-lookup"><span data-stu-id="ad3fd-134">Value</span></span>   | <span data-ttu-id="ad3fd-135">Описание</span><span class="sxs-lookup"><span data-stu-id="ad3fd-135">Description</span></span>                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| <span data-ttu-id="ad3fd-136">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="ad3fd-136">Default</span></span> | <span data-ttu-id="ad3fd-137">Использует режим по умолчанию в базовой библиотеке S'Lite.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-137">Uses the default mode of the underlying SQLite library.</span></span> <span data-ttu-id="ad3fd-138">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-138">This is the default.</span></span>                   |
| <span data-ttu-id="ad3fd-139">Private</span><span class="sxs-lookup"><span data-stu-id="ad3fd-139">Private</span></span> | <span data-ttu-id="ad3fd-140">Каждое соединение использует частный кэш.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-140">Each connection uses a private cache.</span></span>                                                          |
| <span data-ttu-id="ad3fd-141">Совмещаемая блокировка</span><span class="sxs-lookup"><span data-stu-id="ad3fd-141">Shared</span></span>  | <span data-ttu-id="ad3fd-142">Соединения разделяют кэш.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-142">Connections share a cache.</span></span> <span data-ttu-id="ad3fd-143">Этот режим может изменить поведение транзакций и блокировки таблицы.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-143">This mode can change the behavior of transaction and table locking.</span></span> |

### <a name="password"></a><span data-ttu-id="ad3fd-144">Пароль</span><span class="sxs-lookup"><span data-stu-id="ad3fd-144">Password</span></span>

<span data-ttu-id="ad3fd-145">Ключ шифрования.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-145">The encryption key.</span></span> <span data-ttu-id="ad3fd-146">При указании отправляется `PRAGMA key` сразу после открытия соединения.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-146">When specified, `PRAGMA key` is sent immediately after opening the connection.</span></span>

> [!WARNING]
> <span data-ttu-id="ad3fd-147">Пароль не имеет эффекта, когда шифрование не поддерживается родной библиотекой S'Lite.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-147">Password has no effect when encryption isn't supported by the native SQLite library.</span></span>

### <a name="foreign-keys"></a><span data-ttu-id="ad3fd-148">Внешние ключи</span><span class="sxs-lookup"><span data-stu-id="ad3fd-148">Foreign Keys</span></span>

<span data-ttu-id="ad3fd-149">Значение, указывающее, следует ли ввести ограничения иностранных ключевых моментов.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-149">A value indicating whether to enable foreign key constraints.</span></span>

| <span data-ttu-id="ad3fd-150">Значение</span><span class="sxs-lookup"><span data-stu-id="ad3fd-150">Value</span></span>   | <span data-ttu-id="ad3fd-151">Описание</span><span class="sxs-lookup"><span data-stu-id="ad3fd-151">Description</span></span>
| ------- | --- |
| <span data-ttu-id="ad3fd-152">True</span><span class="sxs-lookup"><span data-stu-id="ad3fd-152">True</span></span>    | <span data-ttu-id="ad3fd-153">Отправляет `PRAGMA foreign_keys = 1` сразу после открытия соединения.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-153">Sends `PRAGMA foreign_keys = 1` immediately after opening the connection.</span></span>
| <span data-ttu-id="ad3fd-154">False</span><span class="sxs-lookup"><span data-stu-id="ad3fd-154">False</span></span>   | <span data-ttu-id="ad3fd-155">Отправляет `PRAGMA foreign_keys = 0` сразу после открытия соединения.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-155">Sends `PRAGMA foreign_keys = 0` immediately after opening the connection.</span></span>
| <span data-ttu-id="ad3fd-156">(пусто)</span><span class="sxs-lookup"><span data-stu-id="ad3fd-156">(empty)</span></span> | <span data-ttu-id="ad3fd-157">Не отправляет `PRAGMA foreign_keys`.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-157">Doesn't send `PRAGMA foreign_keys`.</span></span> <span data-ttu-id="ad3fd-158">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-158">This is the default.</span></span> |

<span data-ttu-id="ad3fd-159">Нет необходимости включать иностранные ключи, если, как и в e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS использовалась для компиляции родной библиотеки S'Lite.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-159">There's no need enable foreign keys if, like in e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS was used to compile the native SQLite library.</span></span>

### <a name="recursive-triggers"></a><span data-ttu-id="ad3fd-160">Рекурсивные триггеры</span><span class="sxs-lookup"><span data-stu-id="ad3fd-160">Recursive triggers</span></span>

<span data-ttu-id="ad3fd-161">Значение, указывающее, включать ли рекурсивные триггеры.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-161">A value that indicates whether to enable recursive triggers.</span></span>

| <span data-ttu-id="ad3fd-162">Значение</span><span class="sxs-lookup"><span data-stu-id="ad3fd-162">Value</span></span> | <span data-ttu-id="ad3fd-163">Описание</span><span class="sxs-lookup"><span data-stu-id="ad3fd-163">Description</span></span>                                                                 |
| ----- | --------------------------------------------------------------------------- |
| <span data-ttu-id="ad3fd-164">True</span><span class="sxs-lookup"><span data-stu-id="ad3fd-164">True</span></span>  | <span data-ttu-id="ad3fd-165">Отправляет `PRAGMA recursive_triggers` сразу после открытия соединения.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-165">Sends `PRAGMA recursive_triggers` immediately after opening the connection.</span></span> |
| <span data-ttu-id="ad3fd-166">False</span><span class="sxs-lookup"><span data-stu-id="ad3fd-166">False</span></span> | <span data-ttu-id="ad3fd-167">Не отправляет `PRAGMA recursive_triggers`.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-167">Doesn't send `PRAGMA recursive_triggers`.</span></span> <span data-ttu-id="ad3fd-168">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-168">This is the default.</span></span>              |

## <a name="connection-string-builder"></a><span data-ttu-id="ad3fd-169">Строитель строк соединения</span><span class="sxs-lookup"><span data-stu-id="ad3fd-169">Connection string builder</span></span>

<span data-ttu-id="ad3fd-170">Вы можете <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> использовать в качестве сильно набранного способа создания строк соединения.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-170">You can use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> as a strongly typed way of creating connection strings.</span></span> <span data-ttu-id="ad3fd-171">Он также может быть использован для предотвращения атак инъекций строки соединения.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-171">It can also be used to prevent connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a><span data-ttu-id="ad3fd-172">Примеры</span><span class="sxs-lookup"><span data-stu-id="ad3fd-172">Examples</span></span>

### <a name="basic"></a><span data-ttu-id="ad3fd-173">Basic</span><span class="sxs-lookup"><span data-stu-id="ad3fd-173">Basic</span></span>

<span data-ttu-id="ad3fd-174">Базовая строка соединения с общим кэшем для улучшения параллелизма.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-174">A basic connection string with a shared cache for improved concurrency.</span></span>

```ConnectionString
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a><span data-ttu-id="ad3fd-175">зашифрованные;</span><span class="sxs-lookup"><span data-stu-id="ad3fd-175">Encrypted</span></span>

<span data-ttu-id="ad3fd-176">Зашифрованная база данных.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-176">An encrypted database.</span></span>

```ConnectionString
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a><span data-ttu-id="ad3fd-177">Только для чтения</span><span class="sxs-lookup"><span data-stu-id="ad3fd-177">Read-only</span></span>

<span data-ttu-id="ad3fd-178">База данных только для чтения, которая не может быть изменена приложением.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-178">A read-only database that cannot be modified by the app.</span></span>

```ConnectionString
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a><span data-ttu-id="ad3fd-179">В памяти</span><span class="sxs-lookup"><span data-stu-id="ad3fd-179">In-memory</span></span>

<span data-ttu-id="ad3fd-180">Частная база данных в памяти.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-180">A private, in-memory database.</span></span>

```ConnectionString
Data Source=:memory:
```

### <a name="sharable-in-memory"></a><span data-ttu-id="ad3fd-181">Шарибл в памяти</span><span class="sxs-lookup"><span data-stu-id="ad3fd-181">Sharable in-memory</span></span>

<span data-ttu-id="ad3fd-182">Sharable, в памяти базы данных, определенные по имени *Sharable*.</span><span class="sxs-lookup"><span data-stu-id="ad3fd-182">A sharable, in-memory database identified by the name *Sharable*.</span></span>

```ConnectionString
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a><span data-ttu-id="ad3fd-183">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ad3fd-183">See also</span></span>

* [<span data-ttu-id="ad3fd-184">Строки подключения в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ad3fd-184">Connection Strings in ADO.NET</span></span>](../../../framework/data/adonet/connection-strings.md)
* [<span data-ttu-id="ad3fd-185">Базы данных в памяти</span><span class="sxs-lookup"><span data-stu-id="ad3fd-185">In-Memory databases</span></span>](in-memory-databases.md)
* [<span data-ttu-id="ad3fd-186">Транзакции</span><span class="sxs-lookup"><span data-stu-id="ad3fd-186">Transactions</span></span>](transactions.md)
