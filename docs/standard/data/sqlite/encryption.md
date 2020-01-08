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
# <a name="encryption"></a>Шифрование

По умолчанию SQLite не поддерживает шифрование файлов базы данных. Вместо этого необходимо использовать измененную версию SQLite, например, [см](https://www.hwaci.com/sw/sqlite/see.html)., [склЦифер](https://www.zetetic.net/sqlcipher/), [склитекрипт](http://www.sqlite-crypt.com/)или [wxSQLite3](https://utelle.github.io/wxsqlite3). В этой статье демонстрируется использование неподдерживаемой сборки СклЦифер с открытым исходным кодом, но информация также относится к другим решениям, так как они обычно соответствуют одному и тому же шаблону.

## <a name="installation"></a>Установка

### <a name="net-core-clitabnetcore-cli"></a>[Интерфейс командной строки .NET Core](#tab/netcore-cli)

```dotnetcli
dotnet remove package Microsoft.Data.Sqlite
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studiotabvisual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Remove-Package Microsoft.Data.Sqlite
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

Дополнительные сведения об использовании другой собственной библиотеки для шифрования см. в разделе [пользовательские версии SQLite](custom-versions.md).

## <a name="specify-the-key"></a>Укажите ключ

Чтобы включить шифрование, укажите ключ с помощью ключевого слова строки подключения `Password`. Используйте <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder>, чтобы добавить или обновить значение из входных данных пользователя и избежать атак путем внедрения строки подключения.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="rekeying-the-database"></a>Смена ключей базы данных

Если необходимо изменить ключ шифрования базы данных, выдайте инструкцию `PRAGMA rekey`. Чтобы расшифровать базу данных, укажите `NULL`.

К сожалению, SQLite не поддерживает параметры в инструкциях `PRAGMA`. Вместо этого используйте функцию `quote()`, чтобы предотвратить внедрение кода SQL.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_Rekey)]
