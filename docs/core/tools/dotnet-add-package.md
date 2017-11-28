---
title: "Команда dotnet add package — CLI .NET Core"
description: "Команду dotnet add package удобно использовать для добавления ссылки на пакет NuGet в проект."
author: mairaw
ms.author: mairaw
ms.date: 08/11/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: 7518ec32d669e64d713e77f687d285279b012967
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-add-package"></a><span data-ttu-id="de0bc-103">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="de0bc-103">dotnet add package</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="de0bc-104">Имя</span><span class="sxs-lookup"><span data-stu-id="de0bc-104">Name</span></span>

<span data-ttu-id="de0bc-105">`dotnet add package` — добавляет ссылку на пакет в файл проекта.</span><span class="sxs-lookup"><span data-stu-id="de0bc-105">`dotnet add package` - Adds a package reference to a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="de0bc-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="de0bc-106">Synopsis</span></span>

`dotnet add [<PROJECT>] package <PACKAGE_NAME> [-h|--help] [-v|--version] [-f|--framework] [-n|--no-restore] [-s|--source] [--package-directory]`

## <a name="description"></a><span data-ttu-id="de0bc-107">Описание</span><span class="sxs-lookup"><span data-stu-id="de0bc-107">Description</span></span>

<span data-ttu-id="de0bc-108">Команда `dotnet add package` предоставляет удобный способ для добавления ссылки на пакет в файл проекта.</span><span class="sxs-lookup"><span data-stu-id="de0bc-108">The `dotnet add package` command provides a convenient option to add a package reference to a project file.</span></span> <span data-ttu-id="de0bc-109">После запуска этой команды выполняется проверка совместимости, чтобы убедиться, что пакет совместим со всеми платформами в проекте.</span><span class="sxs-lookup"><span data-stu-id="de0bc-109">After running the command, there's a compatibility check to ensure the package is compatible with the frameworks in the project.</span></span> <span data-ttu-id="de0bc-110">Если проверка проходит успешно, в файл проекта добавляется элемент `<PackageReference>` и выполняется команда [dotnet restore](dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="de0bc-110">If the check passes, a `<PackageReference>` element is added to the project file and [dotnet restore](dotnet-restore.md) is run.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="de0bc-111">Например, при добавлении `Newtonsoft.Json` в *ToDo.csproj* создаются выходные данные примерно следующего вида:</span><span class="sxs-lookup"><span data-stu-id="de0bc-111">For example, adding `Newtonsoft.Json` to *ToDo.csproj* produces output similar to the following example:</span></span>

```
  Writing C:\Users\mairaw\AppData\Local\Temp\tmp95A8.tmp
info : Adding PackageReference for package 'Newtonsoft.Json' into project 'C:\projects\ToDo\ToDo.csproj'.
log  : Restoring packages for C:\projects\ToDo\ToDo.csproj...
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json 235ms
info : Package 'Newtonsoft.Json' is compatible with all the specified frameworks in project 'C:\projects\ToDo\ToDo.csproj'.
info : PackageReference for package 'Newtonsoft.Json' version '10.0.3' added to file 'C:\projects\ToDo\ToDo.csproj'.
```

<span data-ttu-id="de0bc-112">Файл *ToDo.csproj* теперь содержит элемент [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) для пакета, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="de0bc-112">The *ToDo.csproj* file now contains a [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) element for the referenced package.</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```

## <a name="arguments"></a><span data-ttu-id="de0bc-113">Аргументы</span><span class="sxs-lookup"><span data-stu-id="de0bc-113">Arguments</span></span>

`PROJECT`

<span data-ttu-id="de0bc-114">Указывает файл проекта.</span><span class="sxs-lookup"><span data-stu-id="de0bc-114">Specifies the project file.</span></span> <span data-ttu-id="de0bc-115">Если он не указан, команда ищет текущий каталог для него.</span><span class="sxs-lookup"><span data-stu-id="de0bc-115">If not specified, the command searches the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="de0bc-116">Добавляемая ссылка на пакет.</span><span class="sxs-lookup"><span data-stu-id="de0bc-116">The package reference to add.</span></span>

## <a name="options"></a><span data-ttu-id="de0bc-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="de0bc-117">Options</span></span>

`-h|--help`

<span data-ttu-id="de0bc-118">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="de0bc-118">Prints out a short help for the command.</span></span>

`-v|--version <VERSION>`

<span data-ttu-id="de0bc-119">Версия пакета.</span><span class="sxs-lookup"><span data-stu-id="de0bc-119">Version of the package.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="de0bc-120">Добавляет ссылку на пакет только при ориентации на конкретную [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="de0bc-120">Adds a package reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

`-n|--no-restore`

<span data-ttu-id="de0bc-121">Добавляет ссылку на пакет без предварительного просмотра восстановления и проверки совместимости.</span><span class="sxs-lookup"><span data-stu-id="de0bc-121">Adds a package reference without performing a restore preview and compatibility check.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="de0bc-122">Указывает конкретный источник пакета NuGet во время операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="de0bc-122">Uses a specific NuGet package source during the restore operation.</span></span>

`--package-directory <PACKAGE_DIRECTORY>`

<span data-ttu-id="de0bc-123">Восстанавливает пакет в указанный каталог.</span><span class="sxs-lookup"><span data-stu-id="de0bc-123">Restores the package to the specified directory.</span></span>

## <a name="examples"></a><span data-ttu-id="de0bc-124">Примеры</span><span class="sxs-lookup"><span data-stu-id="de0bc-124">Examples</span></span>

<span data-ttu-id="de0bc-125">Добавление пакета NuGet `Newtonsoft.Json` в проект:</span><span class="sxs-lookup"><span data-stu-id="de0bc-125">Add `Newtonsoft.Json` NuGet package to a project:</span></span>

`dotnet add package Newtonsoft.Json`

<span data-ttu-id="de0bc-126">Добавление определенной версии пакета в проект:</span><span class="sxs-lookup"><span data-stu-id="de0bc-126">Add a specific version of a package to a project:</span></span>

`dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0`

<span data-ttu-id="de0bc-127">Добавление пакета с помощью определенного источника NuGet:</span><span class="sxs-lookup"><span data-stu-id="de0bc-127">Add a package using a specific NuGet source:</span></span>

`dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json`
