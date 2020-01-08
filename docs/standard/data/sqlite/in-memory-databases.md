---
title: Базы данных в памяти
ms.date: 12/13/2019
description: Узнайте, как использовать базы данных SQLite в памяти.
ms.openlocfilehash: b125ff5aa4128bd4c3ff558c5573b7d11802090a
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450468"
---
# <a name="in-memory-databases"></a><span data-ttu-id="8b145-103">Базы данных в памяти</span><span class="sxs-lookup"><span data-stu-id="8b145-103">In-memory databases</span></span>

<span data-ttu-id="8b145-104">Базы данных SQLite в памяти — это базы данных, которые полностью хранятся в памяти, а не на диске.</span><span class="sxs-lookup"><span data-stu-id="8b145-104">SQLite in-memory databases are databases stored entirely in memory, not on disk.</span></span> <span data-ttu-id="8b145-105">Используйте имя файла специального источника данных `:memory:` для создания базы данных в памяти.</span><span class="sxs-lookup"><span data-stu-id="8b145-105">Use the special data source filename `:memory:` to create an in-memory database.</span></span> <span data-ttu-id="8b145-106">Когда соединение закрывается, база данных удаляется.</span><span class="sxs-lookup"><span data-stu-id="8b145-106">When the connection is closed, the database is deleted.</span></span> <span data-ttu-id="8b145-107">При использовании `:memory:`каждое соединение создает собственную базу данных.</span><span class="sxs-lookup"><span data-stu-id="8b145-107">When using `:memory:`, each connection creates its own database.</span></span>

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a><span data-ttu-id="8b145-108">Совместное использование баз данных в памяти</span><span class="sxs-lookup"><span data-stu-id="8b145-108">Shareable in-memory databases</span></span>

<span data-ttu-id="8b145-109">Базы данных в памяти могут совместно использоваться несколькими подключениями с помощью `Mode=Memory` и `Cache=Shared` в строке подключения.</span><span class="sxs-lookup"><span data-stu-id="8b145-109">In-memory databases can be shared between multiple connections by using `Mode=Memory` and `Cache=Shared` in the connection string.</span></span> <span data-ttu-id="8b145-110">Ключевое слово `Data Source` используется для присвоения имени базе данных в памяти.</span><span class="sxs-lookup"><span data-stu-id="8b145-110">The `Data Source` keyword is used to give the in-memory database a name.</span></span> <span data-ttu-id="8b145-111">Строки подключения, использующие одно и то же имя, будут обращаться к одной и той же базе данных в памяти.</span><span class="sxs-lookup"><span data-stu-id="8b145-111">Connection strings using the same name will access the same in-memory database.</span></span> <span data-ttu-id="8b145-112">База данных сохраняется, пока по крайней мере одно подключение к ней остается открытым.</span><span class="sxs-lookup"><span data-stu-id="8b145-112">The database persists as long as at least one connection to it remains open.</span></span> <span data-ttu-id="8b145-113">[Пример](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) , демонстрирующий это, можно найти на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="8b145-113">A [sample](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) demonstrating this is available on GitHub.</span></span>

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
