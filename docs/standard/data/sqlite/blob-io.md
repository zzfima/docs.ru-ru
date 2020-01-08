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
# <a name="blob-io"></a><span data-ttu-id="5381a-103">Ввод-вывод больших двоичных объектов</span><span class="sxs-lookup"><span data-stu-id="5381a-103">Blob I/O</span></span>

<span data-ttu-id="5381a-104">Можно уменьшить использование памяти при чтении и записи больших объектов путем потоковой передачи данных в базу данных и из нее.</span><span class="sxs-lookup"><span data-stu-id="5381a-104">You can reduce memory usage while reading and writing large objects by streaming the data into and out of the database.</span></span> <span data-ttu-id="5381a-105">Это может быть особенно полезно при анализе или преобразовании данных.</span><span class="sxs-lookup"><span data-stu-id="5381a-105">This can be especially useful when parsing or transforming the data.</span></span>

<span data-ttu-id="5381a-106">Для начала вставьте строку как обычную.</span><span class="sxs-lookup"><span data-stu-id="5381a-106">Start by inserting a row as normal.</span></span> <span data-ttu-id="5381a-107">Используйте функцию SQL `zeroblob()`, чтобы выделить место в базе данных для хранения большого объекта.</span><span class="sxs-lookup"><span data-stu-id="5381a-107">Use the `zeroblob()` SQL function to allocate space in the database to hold the large object.</span></span> <span data-ttu-id="5381a-108">Функция `last_insert_rowid()` предоставляет удобный способ получения ROWID.</span><span class="sxs-lookup"><span data-stu-id="5381a-108">The `last_insert_rowid()` function provides a convenient way to get its rowid.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Insert)]

<span data-ttu-id="5381a-109">После вставки строки откройте поток для записи большого объекта с помощью <xref:Microsoft.Data.Sqlite.SqliteBlob>.</span><span class="sxs-lookup"><span data-stu-id="5381a-109">After inserting the row, open a stream to write the large object using <xref:Microsoft.Data.Sqlite.SqliteBlob>.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Write)]

<span data-ttu-id="5381a-110">Чтобы выполнить потоковую передачу больших объектов из базы данных, необходимо выбрать ROWID или один из его псевдонимов, как показано здесь, помимо столбца больших объектов.</span><span class="sxs-lookup"><span data-stu-id="5381a-110">To stream the large object out of the database, you must select the rowid or one of its aliases as show here in addition to the large object's column.</span></span> <span data-ttu-id="5381a-111">Если вы не выберете ROWID, весь объект будет загружен в память.</span><span class="sxs-lookup"><span data-stu-id="5381a-111">If you don't select the rowid, the entire object will be loaded into memory.</span></span> <span data-ttu-id="5381a-112">Объект, возвращаемый `GetStream()`, будет `SqliteBlob`, когда выполняется правильно.</span><span class="sxs-lookup"><span data-stu-id="5381a-112">The object returned by `GetStream()` will be a `SqliteBlob` when done correctly.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Read)]
