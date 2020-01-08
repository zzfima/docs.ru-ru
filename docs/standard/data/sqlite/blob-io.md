---
title: Ввод-вывод больших двоичных объектов
ms.date: 12/13/2019
description: Узнайте, как использовать функцию ввода-вывода объекта SQLite.
ms.openlocfilehash: 0c133deacdc19684eca3a6724fb398dc01fda558
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450306"
---
# <a name="blob-io"></a>Ввод-вывод больших двоичных объектов

Можно уменьшить использование памяти при чтении и записи больших объектов путем потоковой передачи данных в базу данных и из нее. Это может быть особенно полезно при анализе или преобразовании данных.

Для начала вставьте строку как обычную. Используйте функцию SQL `zeroblob()`, чтобы выделить место в базе данных для хранения большого объекта. Функция `last_insert_rowid()` предоставляет удобный способ получения ROWID.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Insert)]

После вставки строки откройте поток для записи большого объекта с помощью <xref:Microsoft.Data.Sqlite.SqliteBlob>.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Write)]

Чтобы выполнить потоковую передачу больших объектов из базы данных, необходимо выбрать ROWID или один из его псевдонимов, как показано здесь, помимо столбца больших объектов. Если вы не выберете ROWID, весь объект будет загружен в память. Объект, возвращаемый `GetStream()`, будет `SqliteBlob`, когда выполняется правильно.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Read)]
