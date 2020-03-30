---
title: Базы данных в памяти
ms.date: 12/13/2019
description: Узнайте, как использовать базы данных в памяти S'Lite.
ms.openlocfilehash: 408c81f538e27dcfffad20db74b7809912b7905f
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391212"
---
# <a name="in-memory-databases"></a><span data-ttu-id="de625-103">Базы данных в памяти</span><span class="sxs-lookup"><span data-stu-id="de625-103">In-memory databases</span></span>

<span data-ttu-id="de625-104">Базы данных памяти S'Lite — это базы данных, хранящиеся исключительно в памяти, а не на диске.</span><span class="sxs-lookup"><span data-stu-id="de625-104">SQLite in-memory databases are databases stored entirely in memory, not on disk.</span></span> <span data-ttu-id="de625-105">Используйте специальное имя `:memory:` источника данных для создания базы данных в памяти.</span><span class="sxs-lookup"><span data-stu-id="de625-105">Use the special data source filename `:memory:` to create an in-memory database.</span></span> <span data-ttu-id="de625-106">При закрытии соединения база данных удаляется.</span><span class="sxs-lookup"><span data-stu-id="de625-106">When the connection is closed, the database is deleted.</span></span> <span data-ttu-id="de625-107">При `:memory:`использовании каждое соединение создает свою собственную базу данных.</span><span class="sxs-lookup"><span data-stu-id="de625-107">When using `:memory:`, each connection creates its own database.</span></span>

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a><span data-ttu-id="de625-108">Общие базы данных в памяти</span><span class="sxs-lookup"><span data-stu-id="de625-108">Shareable in-memory databases</span></span>

<span data-ttu-id="de625-109">Базы данных в памяти могут быть `Mode=Memory` `Cache=Shared` разделены между несколькими соединениями с помощью и в строке соединения.</span><span class="sxs-lookup"><span data-stu-id="de625-109">In-memory databases can be shared between multiple connections by using `Mode=Memory` and `Cache=Shared` in the connection string.</span></span> <span data-ttu-id="de625-110">Ключевое `Data Source` слово используется для привить базе данных в памяти имя.</span><span class="sxs-lookup"><span data-stu-id="de625-110">The `Data Source` keyword is used to give the in-memory database a name.</span></span> <span data-ttu-id="de625-111">Строки подключения с использованием одного и того же имени будут получать доступ к той же базе данных в памяти.</span><span class="sxs-lookup"><span data-stu-id="de625-111">Connection strings using the same name will access the same in-memory database.</span></span> <span data-ttu-id="de625-112">База данных сохраняется до тех пор, пока по крайней мере одно подключение к ней остается открытым.</span><span class="sxs-lookup"><span data-stu-id="de625-112">The database persists as long as at least one connection to it remains open.</span></span> <span data-ttu-id="de625-113">[Пример,](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) демонстрирующий это, доступен на GitHub.</span><span class="sxs-lookup"><span data-stu-id="de625-113">A [sample](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) demonstrating this is available on GitHub.</span></span>

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
