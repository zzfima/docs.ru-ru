---
title: Команда dotnet add package
description: Команду dotnet add package удобно использовать для добавления ссылки на пакет NuGet в проект.
ms.date: 06/26/2019
ms.openlocfilehash: 210dcf0efe06672264ebfa297589bdb387591a42
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733327"
---
# <a name="dotnet-add-package"></a><span data-ttu-id="fea62-103">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="fea62-103">dotnet add package</span></span>

<span data-ttu-id="fea62-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 1.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="fea62-104">**This article applies to:** ✔️ .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="fea62-105">name</span><span class="sxs-lookup"><span data-stu-id="fea62-105">Name</span></span>

<span data-ttu-id="fea62-106">`dotnet add package` — добавляет ссылку на пакет в файл проекта.</span><span class="sxs-lookup"><span data-stu-id="fea62-106">`dotnet add package` - Adds a package reference to a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="fea62-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="fea62-107">Synopsis</span></span>

`dotnet add [<PROJECT>] package <PACKAGE_NAME> [-h|--help] [-f|--framework] [--interactive] [-n|--no-restore] [--package-directory] [-s|--source] [-v|--version]`

## <a name="description"></a><span data-ttu-id="fea62-108">Описание</span><span class="sxs-lookup"><span data-stu-id="fea62-108">Description</span></span>

<span data-ttu-id="fea62-109">Команда `dotnet add package` предоставляет удобный способ для добавления ссылки на пакет в файл проекта.</span><span class="sxs-lookup"><span data-stu-id="fea62-109">The `dotnet add package` command provides a convenient option to add a package reference to a project file.</span></span> <span data-ttu-id="fea62-110">После запуска этой команды выполняется проверка совместимости, чтобы убедиться, что пакет совместим со всеми платформами в проекте.</span><span class="sxs-lookup"><span data-stu-id="fea62-110">After running the command, there's a compatibility check to ensure the package is compatible with the frameworks in the project.</span></span> <span data-ttu-id="fea62-111">Если проверка проходит успешно, в файл проекта добавляется элемент `<PackageReference>` и выполняется команда [dotnet restore](dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="fea62-111">If the check passes, a `<PackageReference>` element is added to the project file and [dotnet restore](dotnet-restore.md) is run.</span></span>

[!INCLUDE[DotNet Restore Note](../../../includes/dotnet-restore-note.md)]

<span data-ttu-id="fea62-112">Например, при добавлении `Newtonsoft.Json` в *ToDo.csproj* создаются выходные данные примерно следующего вида:</span><span class="sxs-lookup"><span data-stu-id="fea62-112">For example, adding `Newtonsoft.Json` to *ToDo.csproj* produces output similar to the following example:</span></span>

```console
  Writing C:\Users\mairaw\AppData\Local\Temp\tmp95A8.tmp
info : Adding PackageReference for package 'Newtonsoft.Json' into project 'C:\projects\ToDo\ToDo.csproj'.
log  : Restoring packages for C:\Temp\projects\consoleproj\consoleproj.csproj...
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json 79ms
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/12.0.1/newtonsoft.json.12.0.1.nupkg
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/12.0.1/newtonsoft.json.12.0.1.nupkg 232ms
log  : Installing Newtonsoft.Json 12.0.1.
info : Package 'Newtonsoft.Json' is compatible with all the specified frameworks in project 'C:\projects\ToDo\ToDo.csproj'.
info : PackageReference for package 'Newtonsoft.Json' version '12.0.1' added to file 'C:\projects\ToDo\ToDo.csproj'.
```

<span data-ttu-id="fea62-113">Файл *ToDo.csproj* теперь содержит элемент [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) для пакета, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="fea62-113">The *ToDo.csproj* file now contains a [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) element for the referenced package.</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="12.0.1" />
```

## <a name="arguments"></a><span data-ttu-id="fea62-114">Аргументы</span><span class="sxs-lookup"><span data-stu-id="fea62-114">Arguments</span></span>

- **`PROJECT`**

  <span data-ttu-id="fea62-115">Указывает файл проекта.</span><span class="sxs-lookup"><span data-stu-id="fea62-115">Specifies the project file.</span></span> <span data-ttu-id="fea62-116">Если он не указан, команда ищет текущий каталог для него.</span><span class="sxs-lookup"><span data-stu-id="fea62-116">If not specified, the command searches the current directory for one.</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="fea62-117">Добавляемая ссылка на пакет.</span><span class="sxs-lookup"><span data-stu-id="fea62-117">The package reference to add.</span></span>

## <a name="options"></a><span data-ttu-id="fea62-118">Параметры</span><span class="sxs-lookup"><span data-stu-id="fea62-118">Options</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="fea62-119">Добавляет ссылку на пакет только при ориентации на конкретную [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="fea62-119">Adds a package reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

- **`-h|--help`**

  <span data-ttu-id="fea62-120">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="fea62-120">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="fea62-121">Позволяет остановить команду и дождаться, пока пользователь введет данные или выполнит действие (например, завершит проверку подлинности).</span><span class="sxs-lookup"><span data-stu-id="fea62-121">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span> <span data-ttu-id="fea62-122">Доступно с версии пакета SDK 2.1 для .NET Core версии 2.1.400 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="fea62-122">Available since .NET Core 2.1 SDK, version 2.1.400 or later.</span></span>

- **`-n|--no-restore`**

  <span data-ttu-id="fea62-123">Добавляет ссылку на пакет без предварительного просмотра восстановления и проверки совместимости.</span><span class="sxs-lookup"><span data-stu-id="fea62-123">Adds a package reference without performing a restore preview and compatibility check.</span></span>

- **`--package-directory <PACKAGE_DIRECTORY>`**

  <span data-ttu-id="fea62-124">Каталог, в который нужно восстановить пакеты.</span><span class="sxs-lookup"><span data-stu-id="fea62-124">The directory where to restore the packages.</span></span> <span data-ttu-id="fea62-125">Расположение по умолчанию для восстановления пакетов — `%userprofile%\.nuget\packages` в Windows и `~/.nuget/packages` в macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="fea62-125">The default package restore location is `%userprofile%\.nuget\packages` on Windows and `~/.nuget/packages` on macOS and Linux.</span></span> <span data-ttu-id="fea62-126">Дополнительные сведения см. в статье [Управление папкой установки глобальных пакетов, кэшем и временными папками](https://docs.microsoft.com/nuget/consume-packages/managing-the-global-packages-and-cache-folders).</span><span class="sxs-lookup"><span data-stu-id="fea62-126">For more information, see [Managing the global packages, cache, and temp folders in NuGet](https://docs.microsoft.com/nuget/consume-packages/managing-the-global-packages-and-cache-folders).</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="fea62-127">Источник пакета NuGet для использования в ходе операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="fea62-127">The NuGet package source to use during the restore operation.</span></span>

- **`-v|--version <VERSION>`**

  <span data-ttu-id="fea62-128">Версия пакета.</span><span class="sxs-lookup"><span data-stu-id="fea62-128">Version of the package.</span></span> <span data-ttu-id="fea62-129">См. статью [Package versioning](https://docs.microsoft.com/nuget/reference/package-versioning) (Управление версиями пакета).</span><span class="sxs-lookup"><span data-stu-id="fea62-129">See [NuGet package versioning](https://docs.microsoft.com/nuget/reference/package-versioning).</span></span>

## <a name="examples"></a><span data-ttu-id="fea62-130">Примеры</span><span class="sxs-lookup"><span data-stu-id="fea62-130">Examples</span></span>

- <span data-ttu-id="fea62-131">Добавление пакета NuGet `Newtonsoft.Json` в проект:</span><span class="sxs-lookup"><span data-stu-id="fea62-131">Add `Newtonsoft.Json` NuGet package to a project:</span></span>

  ```dotnetcli
  dotnet add package Newtonsoft.Json
  ```

- <span data-ttu-id="fea62-132">Добавление определенной версии пакета в проект:</span><span class="sxs-lookup"><span data-stu-id="fea62-132">Add a specific version of a package to a project:</span></span>

  ```dotnetcli
  dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0
  ```

- <span data-ttu-id="fea62-133">Добавление пакета с помощью определенного источника NuGet:</span><span class="sxs-lookup"><span data-stu-id="fea62-133">Add a package using a specific NuGet source:</span></span>

  ```dotnetcli
  dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json
  ```

## <a name="see-also"></a><span data-ttu-id="fea62-134">См. также</span><span class="sxs-lookup"><span data-stu-id="fea62-134">See also</span></span>

- [<span data-ttu-id="fea62-135">Управление папкой установки глобальных пакетов, кэшем и временными папками</span><span class="sxs-lookup"><span data-stu-id="fea62-135">Managing the global packages, cache, and temp folders in NuGet</span></span>](https://docs.microsoft.com/nuget/consume-packages/managing-the-global-packages-and-cache-folders)
- [<span data-ttu-id="fea62-136">Управление версиями пакета NuGet</span><span class="sxs-lookup"><span data-stu-id="fea62-136">NuGet package versioning</span></span>](https://docs.microsoft.com/nuget/reference/package-versioning)
