---
title: Пользовательские версии SQLite
ms.date: 12/13/2019
description: Узнайте, как использовать пользовательскую версию собственной библиотеки SQLite.
ms.openlocfilehash: dd27278c1dbe17b12e5067d04d19043bf259b1e8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746991"
---
# <a name="custom-sqlite-versions"></a><span data-ttu-id="5ddcb-103">Пользовательские версии SQLite</span><span class="sxs-lookup"><span data-stu-id="5ddcb-103">Custom SQLite versions</span></span>

<span data-ttu-id="5ddcb-104">Microsoft. Data. SQLite построен на основе Склитепклрав.</span><span class="sxs-lookup"><span data-stu-id="5ddcb-104">Microsoft.Data.Sqlite is built on top of SQLitePCLRaw.</span></span> <span data-ttu-id="5ddcb-105">Пользовательские версии библиотеки SQLite можно использовать с помощью пакета или путем настройки поставщика Склитепклрав.</span><span class="sxs-lookup"><span data-stu-id="5ddcb-105">You can use custom versions of the native SQLite library by using a bundle or by configuring a SQLitePCLRaw provider.</span></span>

## <a name="bundles"></a><span data-ttu-id="5ddcb-106">Пакеты</span><span class="sxs-lookup"><span data-stu-id="5ddcb-106">Bundles</span></span>

<span data-ttu-id="5ddcb-107">Склитепклрав предоставляет пакеты пакетов, которые упрощают создание правильных зависимостей на разных платформах.</span><span class="sxs-lookup"><span data-stu-id="5ddcb-107">SQLitePCLRaw provides bundle packages that make it easy to bring in the right dependencies across different platforms.</span></span>

<span data-ttu-id="5ddcb-108">Основной пакет Microsoft. Data. SQLite по умолчанию переносится в Склитепклрав. bundle_e_sqlite3.</span><span class="sxs-lookup"><span data-stu-id="5ddcb-108">The main Microsoft.Data.Sqlite package brings in SQLitePCLRaw.bundle_e_sqlite3 by default.</span></span>

<span data-ttu-id="5ddcb-109">Чтобы использовать другой набор, установите `Microsoft.Data.Sqlite.Core` пакет, а также пакет набора, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="5ddcb-109">To use a different bundle, install the `Microsoft.Data.Sqlite.Core` package instead along with the bundle package you want to use.</span></span> <span data-ttu-id="5ddcb-110">Пакеты автоматически инициализируются с помощью Microsoft. Data. SQLite.</span><span class="sxs-lookup"><span data-stu-id="5ddcb-110">Bundles are automatically initialized by Microsoft.Data.Sqlite.</span></span>

| <span data-ttu-id="5ddcb-111">Средство</span><span class="sxs-lookup"><span data-stu-id="5ddcb-111">Bundle</span></span> | <span data-ttu-id="5ddcb-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5ddcb-112">Description</span></span> |
| --- | --- |
| <span data-ttu-id="5ddcb-113">Склитепклрав. bundle_e_sqlite3</span><span class="sxs-lookup"><span data-stu-id="5ddcb-113">SQLitePCLRaw.bundle_e_sqlite3</span></span> | <span data-ttu-id="5ddcb-114">Обеспечивает последовательную версию SQLite на всех платформах.</span><span class="sxs-lookup"><span data-stu-id="5ddcb-114">Provides a consistent version of SQLite on all platforms.</span></span> <span data-ttu-id="5ddcb-115">Включает расширения дерева FTS4, FTS5, JSON1 и R \*.</span><span class="sxs-lookup"><span data-stu-id="5ddcb-115">Includes the FTS4, FTS5, JSON1, and R\*Tree extensions.</span></span> <span data-ttu-id="5ddcb-116">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5ddcb-116">This is the default.</span></span> |
| <span data-ttu-id="5ddcb-117">Склитепклрав. bundle_green</span><span class="sxs-lookup"><span data-stu-id="5ddcb-117">SQLitePCLRaw.bundle_green</span></span> | <span data-ttu-id="5ddcb-118">То же, что и bundle_e_sqlite3, за исключением iOS, где она использует библиотеку System SQLite.</span><span class="sxs-lookup"><span data-stu-id="5ddcb-118">Same as bundle_e_sqlite3, except on iOS where it uses the system SQLite library.</span></span> |
| <span data-ttu-id="5ddcb-119">Склитепклрав. bundle_zetetic</span><span class="sxs-lookup"><span data-stu-id="5ddcb-119">SQLitePCLRaw.bundle_zetetic</span></span> | <span data-ttu-id="5ddcb-120">Использует официальные сборки СклЦифер из Зететик (не включена).</span><span class="sxs-lookup"><span data-stu-id="5ddcb-120">Uses the official SQLCipher builds from Zetetic (not included).</span></span> |
| <span data-ttu-id="5ddcb-121">Склитепклрав. bundle_winsqlite3</span><span class="sxs-lookup"><span data-stu-id="5ddcb-121">SQLitePCLRaw.bundle_winsqlite3</span></span> | <span data-ttu-id="5ddcb-122">Использует winsqlite3. dll, библиотеку System SQLite в Windows 10.</span><span class="sxs-lookup"><span data-stu-id="5ddcb-122">Uses winsqlite3.dll, the system SQLite library on Windows 10.</span></span> |
| <span data-ttu-id="5ddcb-123">Склитепклрав. bundle_e_sqlcipher</span><span class="sxs-lookup"><span data-stu-id="5ddcb-123">SQLitePCLRaw.bundle_e_sqlcipher</span></span> | <span data-ttu-id="5ddcb-124">Предоставляет неофициальную сборку с открытым исходным кодом СклЦифер.</span><span class="sxs-lookup"><span data-stu-id="5ddcb-124">Provides an unofficial, open-source build of SQLCipher.</span></span> |

<span data-ttu-id="5ddcb-125">Например, чтобы использовать неофициальную сборку с открытым исходным кодом для СклЦифер, используйте следующие команды.</span><span class="sxs-lookup"><span data-stu-id="5ddcb-125">For example, to use the unofficial, open-source build of SQLCipher use the following commands.</span></span>

### <a name="net-core-clitabnetcore-cli"></a>[<span data-ttu-id="5ddcb-126">Интерфейс командной строки .NET Core</span><span class="sxs-lookup"><span data-stu-id="5ddcb-126">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studiotabvisual-studio"></a>[<span data-ttu-id="5ddcb-127">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5ddcb-127">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

## <a name="sqlitepclraw-providers"></a><span data-ttu-id="5ddcb-128">Поставщики Склитепклрав</span><span class="sxs-lookup"><span data-stu-id="5ddcb-128">SQLitePCLRaw providers</span></span>

<span data-ttu-id="5ddcb-129">Вы можете использовать собственную сборку SQLite, используя пакет `SQLitePCLRaw.provider.dynamic_cdecl`.</span><span class="sxs-lookup"><span data-stu-id="5ddcb-129">You can use your own build of SQLite by leveraging the `SQLitePCLRaw.provider.dynamic_cdecl` package.</span></span> <span data-ttu-id="5ddcb-130">В этом случае вы несете ответственность за развертывание собственной библиотеки с приложением.</span><span class="sxs-lookup"><span data-stu-id="5ddcb-130">In this case, you're responsible for deploying the native library with your app.</span></span> <span data-ttu-id="5ddcb-131">Обратите внимание, что сведения о развертывании собственных библиотек в приложении значительно зависят от платформы и среды выполнения .NET, которые вы используете.</span><span class="sxs-lookup"><span data-stu-id="5ddcb-131">Note, the details of deploying native libraries with your app vary considerably depending on which .NET platform and runtime you're using.</span></span>

<span data-ttu-id="5ddcb-132">Сначала необходимо реализовать Ижетфунктионпоинтер.</span><span class="sxs-lookup"><span data-stu-id="5ddcb-132">First, you'll need to implement IGetFunctionPointer.</span></span> <span data-ttu-id="5ddcb-133">Реализация является довольно тривиальной в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5ddcb-133">The implementation is fairly trivial on .NET Core.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

<span data-ttu-id="5ddcb-134">Затем настройте поставщик Склитепклрав.</span><span class="sxs-lookup"><span data-stu-id="5ddcb-134">Next, configure the SQLitePCLRaw provider.</span></span> <span data-ttu-id="5ddcb-135">Убедитесь, что это делается до того, как в приложении будет использоваться Microsoft. Data. SQLite.</span><span class="sxs-lookup"><span data-stu-id="5ddcb-135">Ensure this is done before Microsoft.Data.Sqlite is used in your app.</span></span> <span data-ttu-id="5ddcb-136">Кроме того, не используйте пакет пакета Склитепклрав, который может переопределять поставщик.</span><span class="sxs-lookup"><span data-stu-id="5ddcb-136">Also, avoid using a SQLitePCLRaw bundle package which might override your provider.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
