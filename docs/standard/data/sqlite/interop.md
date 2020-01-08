---
title: Взаимодействие
ms.date: 12/13/2019
description: Узнайте, как взаимодействовать с другими библиотеками SQLite.
ms.openlocfilehash: 486e2a8e00999b8ebe9c85a5fcc1539c514676d3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450462"
---
# <a name="interoperability"></a><span data-ttu-id="60c6a-103">Взаимодействие</span><span class="sxs-lookup"><span data-stu-id="60c6a-103">Interoperability</span></span>

<span data-ttu-id="60c6a-104">Microsoft. Data. SQLite использует Склитепклрав для взаимодействия со встроенной библиотекой SQLite.</span><span class="sxs-lookup"><span data-stu-id="60c6a-104">Microsoft.Data.Sqlite uses SQLitePCLRaw to interact with the native SQLite library.</span></span> <span data-ttu-id="60c6a-105">Склитепклрав предоставляет тонкий API .NET для собственного API SQLite.</span><span class="sxs-lookup"><span data-stu-id="60c6a-105">SQLitePCLRaw provides a thin .NET API over the native SQLite API.</span></span> <span data-ttu-id="60c6a-106">Склитеконнектион и Склитедатареадер предоставляют доступ к базовым объектам Склитепклрав, позволяя напрямую вызывать эти API.</span><span class="sxs-lookup"><span data-stu-id="60c6a-106">SqliteConnection and SqliteDataReader provide access to the underlying SQLitePCLRaw objects letting you call these APIs directly.</span></span>

<span data-ttu-id="60c6a-107">В следующем примере показано, как вызвать `sqlite3_trace` для записи выполненных инструкций SQL в консоль:</span><span class="sxs-lookup"><span data-stu-id="60c6a-107">The following example shows how to call `sqlite3_trace` to write executed SQL statements to the console:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_Trace)]

<span data-ttu-id="60c6a-108">А в следующем примере показан вызов `sqlite3_stmt_status`, чтобы увидеть, сколько шагов SQLite виртуальная машина выполнила инструкцию SQL.</span><span class="sxs-lookup"><span data-stu-id="60c6a-108">And the following example shows calling `sqlite3_stmt_status` to see how many SQLite virtual machine steps a SQL statement compiled into:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_StatementStatus)]

<span data-ttu-id="60c6a-109">Объекты Склитепклрав даже предоставляют указатель на собственные объекты, что позволяет P/Invokeть дополнительные интерфейсы API SQLite.</span><span class="sxs-lookup"><span data-stu-id="60c6a-109">The SQLitePCLRaw objects even expose a pointer to the native objects letting you P/Invoke additional native SQLite APIs.</span></span>
