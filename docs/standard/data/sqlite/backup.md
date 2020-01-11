---
title: Резервное копирование в сети
ms.date: 12/13/2019
description: Узнайте, как использовать функцию интерактивного резервного копирования SQLite.
ms.openlocfilehash: d857dcb69f2b2d10b034a0abf222b30c2e20bb41
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901287"
---
# <a name="online-backup"></a>Резервное копирование в сети

SQLite может создавать резервные копии файлов базы данных во время работы приложения. Эта функция доступна в Microsoft. Data. SQLite в качестве метода <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> для `SqliteConnection`.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BackupSample/Program.cs?name=snippet_Backup)]

В настоящее время `BackupDatabase` создает резервную копию базы данных как можно быстрее и блокирует другие соединения от записи в базу данных. Выдача [#13834](https://github.com/dotnet/efcore/issues/13834) представит альтернативный API для резервного копирования базы данных в фоновом режиме и позволяет другим подключениям прерывать резервное копирование и запись в базу данных. Если вы заинтересованы, предоставьте отзыв о возникшей ошибке.
