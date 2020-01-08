---
title: Резервное копирование в сети
ms.date: 12/13/2019
description: Узнайте, как использовать функцию интерактивного резервного копирования SQLite.
ms.openlocfilehash: 885aa2c5555b58deb2551c0a4e6933742a093457
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450348"
---
# <a name="online-backup"></a><span data-ttu-id="d6e99-103">Резервное копирование в сети</span><span class="sxs-lookup"><span data-stu-id="d6e99-103">Online backup</span></span>

<span data-ttu-id="d6e99-104">SQLite может создавать резервные копии файлов базы данных во время работы приложения.</span><span class="sxs-lookup"><span data-stu-id="d6e99-104">SQLite can back up database files while the app is running.</span></span> <span data-ttu-id="d6e99-105">Эта функция доступна в Microsoft. Data. SQLite в качестве метода <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> для `SqliteConnection`.</span><span class="sxs-lookup"><span data-stu-id="d6e99-105">This functionality is available in Microsoft.Data.Sqlite as the <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> method on `SqliteConnection`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BackupSample/Program.cs?name=snippet_Backup)]

<span data-ttu-id="d6e99-106">В настоящее время `BackupDatabase` создает резервную копию базы данных как можно быстрее и блокирует другие соединения от записи в базу данных.</span><span class="sxs-lookup"><span data-stu-id="d6e99-106">Currently, `BackupDatabase` will back up the database as quickly as possible and blocks other connections from writing to the database.</span></span> <span data-ttu-id="d6e99-107">Выдача [#13834](https://github.com/aspnet/EntityFrameworkCore/issues/13834) представит альтернативный API для резервного копирования базы данных в фоновом режиме и позволяет другим подключениям прерывать резервное копирование и запись в базу данных.</span><span class="sxs-lookup"><span data-stu-id="d6e99-107">Issue [#13834](https://github.com/aspnet/EntityFrameworkCore/issues/13834) would provide an alternative API to back up the database in the background and allow other connections to interrupt the backup and write to the database.</span></span> <span data-ttu-id="d6e99-108">Если вы заинтересованы, предоставьте отзыв о возникшей ошибке.</span><span class="sxs-lookup"><span data-stu-id="d6e99-108">If you're interested, provide feedback on the issue.</span></span>
