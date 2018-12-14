---
title: Команда dotnet add package — CLI .NET Core
description: Команду dotnet add package удобно использовать для добавления ссылки на пакет NuGet в проект.
ms.date: 12/04/2018
ms.openlocfilehash: 8227e5a86a888f850304e8b94f46c7d31779653f
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53150827"
---
# <a name="dotnet-add-package"></a><span data-ttu-id="639ea-103">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="639ea-103">dotnet add package</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="639ea-104">name</span><span class="sxs-lookup"><span data-stu-id="639ea-104">Name</span></span>

<span data-ttu-id="639ea-105">`dotnet add package` — добавляет ссылку на пакет в файл проекта.</span><span class="sxs-lookup"><span data-stu-id="639ea-105">`dotnet add package` - Adds a package reference to a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="639ea-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="639ea-106">Synopsis</span></span>

`dotnet add [<PROJECT>] package <PACKAGE_NAME> [-h|--help] [-f|--framework] [--interactive] [-n|--no-restore] [--package-directory] [-s|--source] [-v|--version]`

## <a name="description"></a><span data-ttu-id="639ea-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="639ea-107">Description</span></span>

<span data-ttu-id="639ea-108">Команда `dotnet add package` предоставляет удобный способ для добавления ссылки на пакет в файл проекта.</span><span class="sxs-lookup"><span data-stu-id="639ea-108">The `dotnet add package` command provides a convenient option to add a package reference to a project file.</span></span> <span data-ttu-id="639ea-109">После запуска этой команды выполняется проверка совместимости, чтобы убедиться, что пакет совместим со всеми платформами в проекте.</span><span class="sxs-lookup"><span data-stu-id="639ea-109">After running the command, there's a compatibility check to ensure the package is compatible with the frameworks in the project.</span></span> <span data-ttu-id="639ea-110">Если проверка проходит успешно, в файл проекта добавляется элемент `<PackageReference>` и выполняется команда [dotnet restore](dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="639ea-110">If the check passes, a `<PackageReference>` element is added to the project file and [dotnet restore](dotnet-restore.md) is run.</span></span>

[!INCLUDE[DotNet Restore Note](../../../includes/dotnet-restore-note.md)]

<span data-ttu-id="639ea-111">Например, при добавлении `Newtonsoft.Json` в *ToDo.csproj* создаются выходные данные примерно следующего вида:</span><span class="sxs-lookup"><span data-stu-id="639ea-111">For example, adding `Newtonsoft.Json` to *ToDo.csproj* produces output similar to the following example:</span></span>

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

<span data-ttu-id="639ea-112">Файл *ToDo.csproj* теперь содержит элемент [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) для пакета, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="639ea-112">The *ToDo.csproj* file now contains a [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) element for the referenced package.</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="12.0.1" />
```

## <a name="arguments"></a><span data-ttu-id="639ea-113">Аргументы</span><span class="sxs-lookup"><span data-stu-id="639ea-113">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="639ea-114">Указывает файл проекта.</span><span class="sxs-lookup"><span data-stu-id="639ea-114">Specifies the project file.</span></span> <span data-ttu-id="639ea-115">Если он не указан, команда ищет текущий каталог для него.</span><span class="sxs-lookup"><span data-stu-id="639ea-115">If not specified, the command searches the current directory for one.</span></span>

* **`PACKAGE_NAME`**

  <span data-ttu-id="639ea-116">Добавляемая ссылка на пакет.</span><span class="sxs-lookup"><span data-stu-id="639ea-116">The package reference to add.</span></span>

## <a name="options"></a><span data-ttu-id="639ea-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="639ea-117">Options</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="639ea-118">Добавляет ссылку на пакет только при ориентации на конкретную [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="639ea-118">Adds a package reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

* **`-h|--help`**

  <span data-ttu-id="639ea-119">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="639ea-119">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="639ea-120">Позволяет остановить команду и дождаться, пока пользователь введет данные или выполнит действие (например, завершит проверку подлинности).</span><span class="sxs-lookup"><span data-stu-id="639ea-120">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span> <span data-ttu-id="639ea-121">Доступно с версии пакета SDK 2.1 для .NET Core версии 2.1.400 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="639ea-121">Available since .NET Core 2.1 SDK, version 2.1.400 or later.</span></span>

* **`-n|--no-restore`**

  <span data-ttu-id="639ea-122">Добавляет ссылку на пакет без предварительного просмотра восстановления и проверки совместимости.</span><span class="sxs-lookup"><span data-stu-id="639ea-122">Adds a package reference without performing a restore preview and compatibility check.</span></span>

* **`--package-directory <PACKAGE_DIRECTORY>`**

  <span data-ttu-id="639ea-123">Восстанавливает пакет в указанный каталог.</span><span class="sxs-lookup"><span data-stu-id="639ea-123">Restores the package to the specified directory.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="639ea-124">Указывает конкретный источник пакета NuGet во время операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="639ea-124">Uses a specific NuGet package source during the restore operation.</span></span>

* **`-v|--version <VERSION>`**

  <span data-ttu-id="639ea-125">Версия пакета.</span><span class="sxs-lookup"><span data-stu-id="639ea-125">Version of the package.</span></span>

## <a name="examples"></a><span data-ttu-id="639ea-126">Примеры</span><span class="sxs-lookup"><span data-stu-id="639ea-126">Examples</span></span>

* <span data-ttu-id="639ea-127">Добавление пакета NuGet `Newtonsoft.Json` в проект:</span><span class="sxs-lookup"><span data-stu-id="639ea-127">Add `Newtonsoft.Json` NuGet package to a project:</span></span>

  ```console
  dotnet add package Newtonsoft.Json
  ```

* <span data-ttu-id="639ea-128">Добавление определенной версии пакета в проект:</span><span class="sxs-lookup"><span data-stu-id="639ea-128">Add a specific version of a package to a project:</span></span>

  ```console
  dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0
  ```

* <span data-ttu-id="639ea-129">Добавление пакета с помощью определенного источника NuGet:</span><span class="sxs-lookup"><span data-stu-id="639ea-129">Add a package using a specific NuGet source:</span></span>

  ```console
  dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json
  ```