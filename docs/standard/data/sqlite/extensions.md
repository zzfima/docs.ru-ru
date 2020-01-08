---
title: Расширения
ms.date: 12/13/2019
description: Узнайте, как загружать расширения SQLite.
ms.openlocfilehash: ab00ccf31b8a22407fc177c18149fe4825a19091
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450480"
---
# <a name="extensions"></a><span data-ttu-id="e121d-103">Расширения</span><span class="sxs-lookup"><span data-stu-id="e121d-103">Extensions</span></span>

<span data-ttu-id="e121d-104">SQLite поддерживает загрузку расширений во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="e121d-104">SQLite supports loading extensions at run time.</span></span> <span data-ttu-id="e121d-105">Расширения включают такие возможности, как дополнительные функции SQL, параметры сортировки, виртуальные таблицы и многое другое.</span><span class="sxs-lookup"><span data-stu-id="e121d-105">Extensions include things like additional SQL functions, collations, virtual tables, and more.</span></span>

<span data-ttu-id="e121d-106">.NET Core включает дополнительную логику для поиска собственных библиотек в дополнительных местах, таких как ссылочные пакеты NuGet.</span><span class="sxs-lookup"><span data-stu-id="e121d-106">.NET Core includes additional logic for locating native libraries in additional places like referenced NuGet packages.</span></span> <span data-ttu-id="e121d-107">Увы, SQLite не может использовать эту логику; Он напрямую вызывает API платформы для загрузки библиотек.</span><span class="sxs-lookup"><span data-stu-id="e121d-107">Unfortunately, SQLite can't leverage this logic; it calls the platform API directly to load libraries.</span></span> <span data-ttu-id="e121d-108">По этой причине приложению может потребоваться изменить путь, LD_LIBRARY_PATH или DYLD_LIBRARY_PATH переменные среды перед загрузкой расширений SQLite.</span><span class="sxs-lookup"><span data-stu-id="e121d-108">Because of this, your app may need to modify the PATH, LD_LIBRARY_PATH, or DYLD_LIBRARY_PATH environment variables before loading SQLite extensions.</span></span> <span data-ttu-id="e121d-109">В GitHub есть [Пример](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) , демонстрирующий Поиск двоичных файлов для текущей среды выполнения внутри пакета NuGet, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="e121d-109">There's [a sample](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) on GitHub that demonstrates finding binaries for the current runtime inside a referenced NuGet package.</span></span>

<span data-ttu-id="e121d-110">Чтобы загрузить расширение, вызовите метод <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A>.</span><span class="sxs-lookup"><span data-stu-id="e121d-110">To load an extension, call the <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> method.</span></span> <span data-ttu-id="e121d-111">Microsoft. Data. SQLite обеспечит загрузку расширения даже при закрытии и повторном открытии соединения.</span><span class="sxs-lookup"><span data-stu-id="e121d-111">Microsoft.Data.Sqlite will ensure that the extension remains loaded even if the connection is closed and reopened.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a><span data-ttu-id="e121d-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="e121d-112">See also</span></span>

* [<span data-ttu-id="e121d-113">Расширения, загружаемые во время выполнения</span><span class="sxs-lookup"><span data-stu-id="e121d-113">Run-Time Loadable Extensions</span></span>](https://www.sqlite.org/loadext.html)
