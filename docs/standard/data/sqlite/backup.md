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
# <a name="online-backup"></a>Резервное копирование в сети

SQLite может создавать резервные копии файлов базы данных во время работы приложения. Эта функция доступна в Microsoft. Data. SQLite в качестве метода <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> для `SqliteConnection`.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BackupSample/Program.cs?name=snippet_Backup)]

В настоящее время `BackupDatabase` создает резервную копию базы данных как можно быстрее и блокирует другие соединения от записи в базу данных. Выдача [#13834](https://github.com/aspnet/EntityFrameworkCore/issues/13834) представит альтернативный API для резервного копирования базы данных в фоновом режиме и позволяет другим подключениям прерывать резервное копирование и запись в базу данных. Если вы заинтересованы, предоставьте отзыв о возникшей ошибке.
