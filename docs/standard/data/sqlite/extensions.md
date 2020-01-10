---
title: Расширения
ms.date: 12/13/2019
description: Узнайте, как загружать расширения SQLite.
ms.openlocfilehash: 74b207205492bac48c89cb756470326f8e4a13c4
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777375"
---
# <a name="extensions"></a><span data-ttu-id="a6857-103">Расширения</span><span class="sxs-lookup"><span data-stu-id="a6857-103">Extensions</span></span>

<span data-ttu-id="a6857-104">SQLite поддерживает загрузку расширений во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a6857-104">SQLite supports loading extensions at run time.</span></span> <span data-ttu-id="a6857-105">Расширения включают такие возможности, как дополнительные функции SQL, параметры сортировки, виртуальные таблицы и многое другое.</span><span class="sxs-lookup"><span data-stu-id="a6857-105">Extensions include things like additional SQL functions, collations, virtual tables, and more.</span></span>

<span data-ttu-id="a6857-106">.NET Core включает дополнительную логику для поиска собственных библиотек в дополнительных местах, таких как ссылочные пакеты NuGet.</span><span class="sxs-lookup"><span data-stu-id="a6857-106">.NET Core includes additional logic for locating native libraries in additional places like referenced NuGet packages.</span></span> <span data-ttu-id="a6857-107">Увы, SQLite не может использовать эту логику; Он напрямую вызывает API платформы для загрузки библиотек.</span><span class="sxs-lookup"><span data-stu-id="a6857-107">Unfortunately, SQLite can't leverage this logic; it calls the platform API directly to load libraries.</span></span> <span data-ttu-id="a6857-108">По этой причине приложению может потребоваться изменить путь, LD_LIBRARY_PATH или DYLD_LIBRARY_PATH переменные среды перед загрузкой расширений SQLite.</span><span class="sxs-lookup"><span data-stu-id="a6857-108">Because of this, your app may need to modify the PATH, LD_LIBRARY_PATH, or DYLD_LIBRARY_PATH environment variables before loading SQLite extensions.</span></span> <span data-ttu-id="a6857-109">В GitHub есть [Пример](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) , демонстрирующий Поиск двоичных файлов для текущей среды выполнения внутри пакета NuGet, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="a6857-109">There's [a sample](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) on GitHub that demonstrates finding binaries for the current runtime inside a referenced NuGet package.</span></span>

<span data-ttu-id="a6857-110">Чтобы загрузить расширение, вызовите метод <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A>.</span><span class="sxs-lookup"><span data-stu-id="a6857-110">To load an extension, call the <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> method.</span></span> <span data-ttu-id="a6857-111">Microsoft. Data. SQLite обеспечит загрузку расширения даже при закрытии и повторном открытии соединения.</span><span class="sxs-lookup"><span data-stu-id="a6857-111">Microsoft.Data.Sqlite will ensure that the extension remains loaded even if the connection is closed and reopened.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a><span data-ttu-id="a6857-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="a6857-112">See also</span></span>

* [<span data-ttu-id="a6857-113">Расширения, загружаемые во время выполнения</span><span class="sxs-lookup"><span data-stu-id="a6857-113">Run-Time Loadable Extensions</span></span>](https://www.sqlite.org/loadext.html)
