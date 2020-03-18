---
title: Обзор
ms.date: 12/13/2019
description: Общие сведения о Microsoft.Data.Sqlite
ms.openlocfilehash: e84c68f0615f187e8dea7ab87ac917c0ad796a1c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "77543603"
---
# <a name="microsoftdatasqlite-overview"></a><span data-ttu-id="e063b-103">Общие сведения о Microsoft.Data.Sqlite</span><span class="sxs-lookup"><span data-stu-id="e063b-103">Microsoft.Data.Sqlite overview</span></span>

<span data-ttu-id="e063b-104">Microsoft.Data.Sqlite — это упрощенный поставщик [ADO.NET](../../../framework/data/adonet/index.md) для SQLite.</span><span class="sxs-lookup"><span data-stu-id="e063b-104">Microsoft.Data.Sqlite is a lightweight [ADO.NET](../../../framework/data/adonet/index.md) provider for SQLite.</span></span> <span data-ttu-id="e063b-105">На основе этой библиотеки построен поставщик [Entity Framework Core](/ef/core/) для SQLite.</span><span class="sxs-lookup"><span data-stu-id="e063b-105">The [Entity Framework Core](/ef/core/) provider for SQLite is built on top of this library.</span></span> <span data-ttu-id="e063b-106">Тем не менее, ее также можно использовать независимо или с другими библиотеками доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="e063b-106">However, it can also be used independently or with other data access libraries.</span></span>

## <a name="installation"></a><span data-ttu-id="e063b-107">Установка</span><span class="sxs-lookup"><span data-stu-id="e063b-107">Installation</span></span>

<span data-ttu-id="e063b-108">Последняя стабильная версия доступна на сайте [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite).</span><span class="sxs-lookup"><span data-stu-id="e063b-108">The latest stable version is available on [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite).</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="e063b-109">Интерфейс командной строки .NET Core</span><span class="sxs-lookup"><span data-stu-id="e063b-109">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite
```

### <a name="visual-studio"></a>[<span data-ttu-id="e063b-110">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e063b-110">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite
```

---

## <a name="usage"></a><span data-ttu-id="e063b-111">Использование</span><span class="sxs-lookup"><span data-stu-id="e063b-111">Usage</span></span>

<span data-ttu-id="e063b-112">В этой библиотеке реализуются общие абстракции ADO.NET для подключений, команд, модулей чтения данных и других элементов.</span><span class="sxs-lookup"><span data-stu-id="e063b-112">This library implements the common ADO.NET abstractions for connections, commands, data readers, and so on.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_HelloWorld)]

## <a name="see-also"></a><span data-ttu-id="e063b-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e063b-113">See also</span></span>

* [<span data-ttu-id="e063b-114">Строки подключения</span><span class="sxs-lookup"><span data-stu-id="e063b-114">Connection strings</span></span>](connection-strings.md)
* [<span data-ttu-id="e063b-115">Справочник по интерфейсам API</span><span class="sxs-lookup"><span data-stu-id="e063b-115">API Reference</span></span>](/dotnet/api/?view=msdata-sqlite-3.0)
* [<span data-ttu-id="e063b-116">Синтаксис SQL</span><span class="sxs-lookup"><span data-stu-id="e063b-116">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
