---
title: Шифрование
ms.date: 12/13/2019
description: Узнайте, как зашифровать файл базы данных.
ms.openlocfilehash: ccdd4b6b8642b3cde1c2667c9ca432a9b0ef21f2
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450486"
---
# <a name="encryption"></a><span data-ttu-id="e3cb9-103">Шифрование</span><span class="sxs-lookup"><span data-stu-id="e3cb9-103">Encryption</span></span>

<span data-ttu-id="e3cb9-104">По умолчанию SQLite не поддерживает шифрование файлов базы данных.</span><span class="sxs-lookup"><span data-stu-id="e3cb9-104">SQLite doesn't support encrypting database files by default.</span></span> <span data-ttu-id="e3cb9-105">Вместо этого необходимо использовать измененную версию SQLite, например, [см](https://www.hwaci.com/sw/sqlite/see.html)., [склЦифер](https://www.zetetic.net/sqlcipher/), [склитекрипт](http://www.sqlite-crypt.com/)или [wxSQLite3](https://utelle.github.io/wxsqlite3).</span><span class="sxs-lookup"><span data-stu-id="e3cb9-105">Instead, you need to use a modified version of SQLite like [SEE](https://www.hwaci.com/sw/sqlite/see.html), [SQLCipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/), or [wxSQLite3](https://utelle.github.io/wxsqlite3).</span></span> <span data-ttu-id="e3cb9-106">В этой статье демонстрируется использование неподдерживаемой сборки СклЦифер с открытым исходным кодом, но информация также относится к другим решениям, так как они обычно соответствуют одному и тому же шаблону.</span><span class="sxs-lookup"><span data-stu-id="e3cb9-106">This article demonstrates using an unsupported, open-source build of SQLCipher, but the information also applies to other solutions since they generally follow the same pattern.</span></span>

## <a name="installation"></a><span data-ttu-id="e3cb9-107">Установка</span><span class="sxs-lookup"><span data-stu-id="e3cb9-107">Installation</span></span>

### <a name="net-core-clitabnetcore-cli"></a>[<span data-ttu-id="e3cb9-108">Интерфейс командной строки .NET Core</span><span class="sxs-lookup"><span data-stu-id="e3cb9-108">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet remove package Microsoft.Data.Sqlite
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studiotabvisual-studio"></a>[<span data-ttu-id="e3cb9-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e3cb9-109">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Remove-Package Microsoft.Data.Sqlite
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

<span data-ttu-id="e3cb9-110">Дополнительные сведения об использовании другой собственной библиотеки для шифрования см. в разделе [пользовательские версии SQLite](custom-versions.md).</span><span class="sxs-lookup"><span data-stu-id="e3cb9-110">For more information about using a different native library for encryption, see [Custom SQLite versions](custom-versions.md).</span></span>

## <a name="specify-the-key"></a><span data-ttu-id="e3cb9-111">Укажите ключ</span><span class="sxs-lookup"><span data-stu-id="e3cb9-111">Specify the key</span></span>

<span data-ttu-id="e3cb9-112">Чтобы включить шифрование, укажите ключ с помощью ключевого слова строки подключения `Password`.</span><span class="sxs-lookup"><span data-stu-id="e3cb9-112">To enable encryption, specify the key using the `Password` connection string keyword.</span></span> <span data-ttu-id="e3cb9-113">Используйте <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder>, чтобы добавить или обновить значение из входных данных пользователя и избежать атак путем внедрения строки подключения.</span><span class="sxs-lookup"><span data-stu-id="e3cb9-113">Use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> to add or update the value from user input and avoid connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="rekeying-the-database"></a><span data-ttu-id="e3cb9-114">Смена ключей базы данных</span><span class="sxs-lookup"><span data-stu-id="e3cb9-114">Rekeying the database</span></span>

<span data-ttu-id="e3cb9-115">Если необходимо изменить ключ шифрования базы данных, выдайте инструкцию `PRAGMA rekey`.</span><span class="sxs-lookup"><span data-stu-id="e3cb9-115">If you want to change the encryption key of a database, issue a `PRAGMA rekey` statement.</span></span> <span data-ttu-id="e3cb9-116">Чтобы расшифровать базу данных, укажите `NULL`.</span><span class="sxs-lookup"><span data-stu-id="e3cb9-116">To decrypt the database, specify `NULL`.</span></span>

<span data-ttu-id="e3cb9-117">К сожалению, SQLite не поддерживает параметры в инструкциях `PRAGMA`.</span><span class="sxs-lookup"><span data-stu-id="e3cb9-117">Unfortunately, SQLite doesn't support parameters in `PRAGMA` statements.</span></span> <span data-ttu-id="e3cb9-118">Вместо этого используйте функцию `quote()`, чтобы предотвратить внедрение кода SQL.</span><span class="sxs-lookup"><span data-stu-id="e3cb9-118">Instead, use the `quote()` function to prevent SQL injection.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_Rekey)]
