---
title: Строки подключения
ms.date: 12/13/2019
description: Поддерживаемые ключевые слова и значения строк подключения.
ms.openlocfilehash: bb54d152bac62a86c2a49192cf678a745159164e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450276"
---
# <a name="connection-strings"></a><span data-ttu-id="23daf-103">Строки подключения</span><span class="sxs-lookup"><span data-stu-id="23daf-103">Connection strings</span></span>

<span data-ttu-id="23daf-104">Строка подключения используется для указания способа подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="23daf-104">A connection string is used to specify how to connect to the database.</span></span> <span data-ttu-id="23daf-105">Строки подключения в Microsoft. Data. SQLite следуют стандартному [синтаксису ADO.NET](../../../framework/data/adonet/connection-strings.md) в виде разделенного точкой с запятой списка ключевых слов и значений.</span><span class="sxs-lookup"><span data-stu-id="23daf-105">Connection strings in Microsoft.Data.Sqlite follow the standard [ADO.NET syntax](../../../framework/data/adonet/connection-strings.md) as a semicolon-separated list of keywords and values.</span></span>

## <a name="keywords"></a><span data-ttu-id="23daf-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="23daf-106">Keywords</span></span>

<span data-ttu-id="23daf-107">С Microsoft. Data. SQLite можно использовать следующие ключевые слова строки подключения:</span><span class="sxs-lookup"><span data-stu-id="23daf-107">The following connection string keywords can be used with Microsoft.Data.Sqlite:</span></span>

### <a name="data-source"></a><span data-ttu-id="23daf-108">Источник данных</span><span class="sxs-lookup"><span data-stu-id="23daf-108">Data source</span></span>

<span data-ttu-id="23daf-109">Путь к файлу базы данных.</span><span class="sxs-lookup"><span data-stu-id="23daf-109">The path to the database file.</span></span> <span data-ttu-id="23daf-110">*Источник данных* (без пробела) и *имя файла* являются псевдонимами этого ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="23daf-110">*DataSource* (without a space) and *Filename* are aliases of this keyword.</span></span>

<span data-ttu-id="23daf-111">SQLite обрабатывает пути относительно текущего рабочего каталога.</span><span class="sxs-lookup"><span data-stu-id="23daf-111">SQLite treats paths relative to the current working directory.</span></span> <span data-ttu-id="23daf-112">Можно также указать абсолютные пути.</span><span class="sxs-lookup"><span data-stu-id="23daf-112">Absolute paths can also be specified.</span></span>

<span data-ttu-id="23daf-113">Если этот параметр **пуст**, SQLite создает временную базу данных на диске, которая удаляется при закрытии соединения.</span><span class="sxs-lookup"><span data-stu-id="23daf-113">If **empty**, SQLite creates a temporary on-disk database that's deleted when the connection is closed.</span></span>

<span data-ttu-id="23daf-114">Если `:memory:`, используется база данных в памяти.</span><span class="sxs-lookup"><span data-stu-id="23daf-114">If `:memory:`, an in-memory database is used.</span></span> <span data-ttu-id="23daf-115">Дополнительные сведения см. [в разделе базы данных в памяти](in-memory-databases.md).</span><span class="sxs-lookup"><span data-stu-id="23daf-115">For more information, see [In-Memory databases](in-memory-databases.md).</span></span>

<span data-ttu-id="23daf-116">Пути, начинающиеся со строки подстановки `|DataDirectory|`, обрабатываются так же, как и относительные пути.</span><span class="sxs-lookup"><span data-stu-id="23daf-116">Paths that start with the `|DataDirectory|` substitution string are treated the same as relative paths.</span></span> <span data-ttu-id="23daf-117">Если задано, пути выполняются относительно значения свойства домена приложения DataDirectory.</span><span class="sxs-lookup"><span data-stu-id="23daf-117">If set, paths are made relative to the DataDirectory application domain property value.</span></span>

<span data-ttu-id="23daf-118">Это ключевое слово также поддерживает [имена файлов URI](https://www.sqlite.org/uri.html).</span><span class="sxs-lookup"><span data-stu-id="23daf-118">This keyword also supports [URI Filenames](https://www.sqlite.org/uri.html).</span></span>

### <a name="mode"></a><span data-ttu-id="23daf-119">Режим</span><span class="sxs-lookup"><span data-stu-id="23daf-119">Mode</span></span>

<span data-ttu-id="23daf-120">Режим подключения.</span><span class="sxs-lookup"><span data-stu-id="23daf-120">The connection mode.</span></span>

| <span data-ttu-id="23daf-121">{2&gt;Value&lt;2}</span><span class="sxs-lookup"><span data-stu-id="23daf-121">Value</span></span>           | <span data-ttu-id="23daf-122">Описание</span><span class="sxs-lookup"><span data-stu-id="23daf-122">Description</span></span>                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="23daf-123">реадвритекреате</span><span class="sxs-lookup"><span data-stu-id="23daf-123">ReadWriteCreate</span></span> | <span data-ttu-id="23daf-124">Открывает базу данных для чтения и записи и создает ее, если она не существует.</span><span class="sxs-lookup"><span data-stu-id="23daf-124">Opens the database for reading and writing, and creates it if it doesn't exist.</span></span> <span data-ttu-id="23daf-125">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="23daf-125">This is the default.</span></span> |
| <span data-ttu-id="23daf-126">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="23daf-126">ReadWrite</span></span>       | <span data-ttu-id="23daf-127">Открывает базу данных для чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="23daf-127">Opens the database for reading and writing.</span></span>                                                        |
| <span data-ttu-id="23daf-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="23daf-128">ReadOnly</span></span>        | <span data-ttu-id="23daf-129">Открывает базу данных в режиме только для чтения.</span><span class="sxs-lookup"><span data-stu-id="23daf-129">Opens the database in read-only mode.</span></span>                                                              |
| <span data-ttu-id="23daf-130">Память</span><span class="sxs-lookup"><span data-stu-id="23daf-130">Memory</span></span>          | <span data-ttu-id="23daf-131">Открывает базу данных в памяти.</span><span class="sxs-lookup"><span data-stu-id="23daf-131">Opens an in-memory database.</span></span>                                                                       |

### <a name="cache"></a><span data-ttu-id="23daf-132">Кэш</span><span class="sxs-lookup"><span data-stu-id="23daf-132">Cache</span></span>

<span data-ttu-id="23daf-133">Режим кэширования, используемый соединением.</span><span class="sxs-lookup"><span data-stu-id="23daf-133">The caching mode used by the connection.</span></span>

| <span data-ttu-id="23daf-134">{2&gt;Value&lt;2}</span><span class="sxs-lookup"><span data-stu-id="23daf-134">Value</span></span>   | <span data-ttu-id="23daf-135">Описание</span><span class="sxs-lookup"><span data-stu-id="23daf-135">Description</span></span>                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| <span data-ttu-id="23daf-136">Default</span><span class="sxs-lookup"><span data-stu-id="23daf-136">Default</span></span> | <span data-ttu-id="23daf-137">Использует режим по умолчанию базовой библиотеки SQLite.</span><span class="sxs-lookup"><span data-stu-id="23daf-137">Uses the default mode of the underlying SQLite library.</span></span> <span data-ttu-id="23daf-138">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="23daf-138">This is the default.</span></span>                   |
| <span data-ttu-id="23daf-139">Private</span><span class="sxs-lookup"><span data-stu-id="23daf-139">Private</span></span> | <span data-ttu-id="23daf-140">Для каждого соединения используется частный кэш.</span><span class="sxs-lookup"><span data-stu-id="23daf-140">Each connection uses a private cache.</span></span>                                                          |
| <span data-ttu-id="23daf-141">Общий</span><span class="sxs-lookup"><span data-stu-id="23daf-141">Shared</span></span>  | <span data-ttu-id="23daf-142">Подключения совместно используют кэш.</span><span class="sxs-lookup"><span data-stu-id="23daf-142">Connections share a cache.</span></span> <span data-ttu-id="23daf-143">Этот режим может изменить поведение блокировки транзакций и таблиц.</span><span class="sxs-lookup"><span data-stu-id="23daf-143">This mode can change the behavior of transaction and table locking.</span></span> |

### <a name="password"></a><span data-ttu-id="23daf-144">Password</span><span class="sxs-lookup"><span data-stu-id="23daf-144">Password</span></span>

<span data-ttu-id="23daf-145">Ключ шифрования.</span><span class="sxs-lookup"><span data-stu-id="23daf-145">The encryption key.</span></span> <span data-ttu-id="23daf-146">Если этот параметр указан, `PRAGMA key` отправляется сразу после открытия соединения.</span><span class="sxs-lookup"><span data-stu-id="23daf-146">When specified, `PRAGMA key` is sent immediately after opening the connection.</span></span>

> [!WARNING]
> <span data-ttu-id="23daf-147">Пароль не действует, если шифрование не поддерживается собственной библиотекой SQLite.</span><span class="sxs-lookup"><span data-stu-id="23daf-147">Password has no effect when encryption isn't supported by the native SQLite library.</span></span>

### <a name="foreign-keys"></a><span data-ttu-id="23daf-148">Внешние ключи</span><span class="sxs-lookup"><span data-stu-id="23daf-148">Foreign Keys</span></span>

<span data-ttu-id="23daf-149">Значение, указывающее, следует ли включить ограничения внешнего ключа.</span><span class="sxs-lookup"><span data-stu-id="23daf-149">A value indicating whether to enable foreign key constraints.</span></span>

| <span data-ttu-id="23daf-150">{2&gt;Value&lt;2}</span><span class="sxs-lookup"><span data-stu-id="23daf-150">Value</span></span>   | <span data-ttu-id="23daf-151">Описание</span><span class="sxs-lookup"><span data-stu-id="23daf-151">Description</span></span>
| ------- | --- |
| <span data-ttu-id="23daf-152">Да</span><span class="sxs-lookup"><span data-stu-id="23daf-152">True</span></span>    | <span data-ttu-id="23daf-153">Отправляет `PRAGMA foreign_keys = 1` сразу после открытия соединения.</span><span class="sxs-lookup"><span data-stu-id="23daf-153">Sends `PRAGMA foreign_keys = 1` immediately after opening the connection.</span></span>
| <span data-ttu-id="23daf-154">Ложь</span><span class="sxs-lookup"><span data-stu-id="23daf-154">False</span></span>   | <span data-ttu-id="23daf-155">Отправляет `PRAGMA foreign_keys = 0` сразу после открытия соединения.</span><span class="sxs-lookup"><span data-stu-id="23daf-155">Sends `PRAGMA foreign_keys = 0` immediately after opening the connection.</span></span>
| <span data-ttu-id="23daf-156">(пусто)</span><span class="sxs-lookup"><span data-stu-id="23daf-156">(empty)</span></span> | <span data-ttu-id="23daf-157">Не отправляет `PRAGMA foreign_keys`.</span><span class="sxs-lookup"><span data-stu-id="23daf-157">Doesn't send `PRAGMA foreign_keys`.</span></span> <span data-ttu-id="23daf-158">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="23daf-158">This is the default.</span></span> |

<span data-ttu-id="23daf-159">Нет необходимости включать внешние ключи, если, как в e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS использовалась для компиляции собственной библиотеки SQLite.</span><span class="sxs-lookup"><span data-stu-id="23daf-159">There's no need enable foreign keys if, like in e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS was used to compile the native SQLite library.</span></span>

### <a name="recursive-triggers"></a><span data-ttu-id="23daf-160">Рекурсивные триггеры</span><span class="sxs-lookup"><span data-stu-id="23daf-160">Recursive triggers</span></span>

<span data-ttu-id="23daf-161">Значение, указывающее, следует ли включить рекурсивные триггеры.</span><span class="sxs-lookup"><span data-stu-id="23daf-161">A value that indicates whether to enable recursive triggers.</span></span>

| <span data-ttu-id="23daf-162">{2&gt;Value&lt;2}</span><span class="sxs-lookup"><span data-stu-id="23daf-162">Value</span></span> | <span data-ttu-id="23daf-163">Описание</span><span class="sxs-lookup"><span data-stu-id="23daf-163">Description</span></span>                                                                 |
| ----- | --------------------------------------------------------------------------- |
| <span data-ttu-id="23daf-164">Да</span><span class="sxs-lookup"><span data-stu-id="23daf-164">True</span></span>  | <span data-ttu-id="23daf-165">Отправляет `PRAGMA recursive_triggers` сразу после открытия соединения.</span><span class="sxs-lookup"><span data-stu-id="23daf-165">Sends `PRAGMA recursive_triggers` immediately after opening the connection.</span></span> |
| <span data-ttu-id="23daf-166">Ложь</span><span class="sxs-lookup"><span data-stu-id="23daf-166">False</span></span> | <span data-ttu-id="23daf-167">Не отправляет `PRAGMA recursive_triggers`.</span><span class="sxs-lookup"><span data-stu-id="23daf-167">Doesn't send `PRAGMA recursive_triggers`.</span></span> <span data-ttu-id="23daf-168">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="23daf-168">This is the default.</span></span>              |

## <a name="connection-string-builder"></a><span data-ttu-id="23daf-169">Построитель строк подключения</span><span class="sxs-lookup"><span data-stu-id="23daf-169">Connection string builder</span></span>

<span data-ttu-id="23daf-170"><xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> можно использовать как строго типизированный способ создания строк подключения.</span><span class="sxs-lookup"><span data-stu-id="23daf-170">You can use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> as a strongly typed way of creating connection strings.</span></span> <span data-ttu-id="23daf-171">Его также можно использовать для предотвращения атак путем внедрения строки подключения.</span><span class="sxs-lookup"><span data-stu-id="23daf-171">It can also be used to prevent connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a><span data-ttu-id="23daf-172">Примеры</span><span class="sxs-lookup"><span data-stu-id="23daf-172">Examples</span></span>

### <a name="basic"></a><span data-ttu-id="23daf-173">Basic</span><span class="sxs-lookup"><span data-stu-id="23daf-173">Basic</span></span>

<span data-ttu-id="23daf-174">Базовая строка подключения с общим кэшем для повышения параллелизма.</span><span class="sxs-lookup"><span data-stu-id="23daf-174">A basic connection string with a shared cache for improved concurrency.</span></span>

```ConnectionString
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a><span data-ttu-id="23daf-175">Зашифровано</span><span class="sxs-lookup"><span data-stu-id="23daf-175">Encrypted</span></span>

<span data-ttu-id="23daf-176">Зашифрованная база данных.</span><span class="sxs-lookup"><span data-stu-id="23daf-176">An encrypted database.</span></span>

```ConnectionString
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a><span data-ttu-id="23daf-177">Только чтение</span><span class="sxs-lookup"><span data-stu-id="23daf-177">Read-only</span></span>

<span data-ttu-id="23daf-178">База данных только для чтения, которая не может быть изменена приложением.</span><span class="sxs-lookup"><span data-stu-id="23daf-178">A read-only database that cannot be modified by the app.</span></span>

```ConnectionString
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a><span data-ttu-id="23daf-179">In-memory</span><span class="sxs-lookup"><span data-stu-id="23daf-179">In-memory</span></span>

<span data-ttu-id="23daf-180">Закрытая, в памяти база данных.</span><span class="sxs-lookup"><span data-stu-id="23daf-180">A private, in-memory database.</span></span>

```ConnectionString
Data Source=:memory:
```

### <a name="sharable-in-memory"></a><span data-ttu-id="23daf-181">Совместное в памяти</span><span class="sxs-lookup"><span data-stu-id="23daf-181">Sharable in-memory</span></span>

<span data-ttu-id="23daf-182">Совместно используемая база данных в памяти, определяемая именем, которая является *совместно*используемой.</span><span class="sxs-lookup"><span data-stu-id="23daf-182">A sharable, in-memory database identified by the name *Sharable*.</span></span>

```ConnectionString
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a><span data-ttu-id="23daf-183">См. также:</span><span class="sxs-lookup"><span data-stu-id="23daf-183">See also</span></span>

* [<span data-ttu-id="23daf-184">Строки подключения в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="23daf-184">Connection Strings in ADO.NET</span></span>](../../../framework/data/adonet/connection-strings.md)
* [<span data-ttu-id="23daf-185">Базы данных в памяти</span><span class="sxs-lookup"><span data-stu-id="23daf-185">In-Memory databases</span></span>](in-memory-databases.md)
* [<span data-ttu-id="23daf-186">Tранзакции</span><span class="sxs-lookup"><span data-stu-id="23daf-186">Transactions</span></span>](transactions.md)
