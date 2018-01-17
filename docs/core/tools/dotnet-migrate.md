---
title: "Команда dotnet migrate — CLI .NET Core"
description: "Команда dotnet migrate переносит проект и все его зависимости."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: 7fad6bf67dfe7b0d6f70ce527a153080aa17d888
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-migrate"></a><span data-ttu-id="1a488-103">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="1a488-103">dotnet migrate</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="1a488-104">name</span><span class="sxs-lookup"><span data-stu-id="1a488-104">Name</span></span>

<span data-ttu-id="1a488-105">`dotnet migrate` — перемещает проект .NET Core предварительной версии 2 в проект пакета SDK для .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="1a488-105">`dotnet migrate` - Migrates a Preview 2 .NET Core project to a .NET Core SDK 1.0 project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1a488-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="1a488-106">Synopsis</span></span>

`dotnet migrate [<SOLUTION_FILE|PROJECT_DIR>] [-t|--template-file] [-v|--sdk-package-version] [-x|--xproj-file] [-s|--skip-project-references] [-r|--report-file] [--format-report-file-json] [--skip-backup] [-h|--help]`

## <a name="description"></a><span data-ttu-id="1a488-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="1a488-107">Description</span></span>

<span data-ttu-id="1a488-108">Команда `dotnet migrate` переносит действительный проект предварительной версии 2 на основе *project.json* в действительный проект *CSPROJ* пакета SDK для .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="1a488-108">The `dotnet migrate` command migrates a valid Preview 2 *project.json*-based project to a valid .NET Core SDK 1.0 *csproj* project.</span></span> 

<span data-ttu-id="1a488-109">По умолчанию команда переносит корневой проект и все ссылки, которые он содержит.</span><span class="sxs-lookup"><span data-stu-id="1a488-109">By default, the command migrates the root project and any project references that the root project contains.</span></span> <span data-ttu-id="1a488-110">Это поведение можно отключить в среде выполнения с помощью параметра `--skip-project-references`.</span><span class="sxs-lookup"><span data-stu-id="1a488-110">This behavior is disabled using the `--skip-project-references` option at runtime.</span></span> 

<span data-ttu-id="1a488-111">Миграция выполняется для следующих объектов:</span><span class="sxs-lookup"><span data-stu-id="1a488-111">Migration is performed on the following:</span></span>

* <span data-ttu-id="1a488-112">Отдельный проект посредством указания нужного файла *project.json*.</span><span class="sxs-lookup"><span data-stu-id="1a488-112">A single project by specifying the *project.json* file to migrate.</span></span>
* <span data-ttu-id="1a488-113">Все каталоги, указанные в файле *global.json*, посредством передачи пути в файл *global.json*.</span><span class="sxs-lookup"><span data-stu-id="1a488-113">All of the directories specified in the *global.json* file by passing in a path to the *global.json* file.</span></span>
* <span data-ttu-id="1a488-114">Файл *solution.sln*, куда переносятся проекты, на которые ссылается решение.</span><span class="sxs-lookup"><span data-stu-id="1a488-114">A *solution.sln* file, where it migrates the projects referenced in the solution.</span></span>
* <span data-ttu-id="1a488-115">Рекурсивно все подкаталоги в этом каталоге.</span><span class="sxs-lookup"><span data-stu-id="1a488-115">On all sub-directories of the given directory recursively.</span></span>

<span data-ttu-id="1a488-116">Команда `dotnet migrate` сохраняет перенесенный файл *project.json* в каталоге `backup` (создается, если не существует).</span><span class="sxs-lookup"><span data-stu-id="1a488-116">The `dotnet migrate` command keeps the migrated *project.json* file inside a `backup` directory, which it creates if the directory doesn't exist.</span></span> <span data-ttu-id="1a488-117">Это поведение можно переопределить с помощью параметра `--skip-backup`.</span><span class="sxs-lookup"><span data-stu-id="1a488-117">This behavior is overridden using the `--skip-backup` option.</span></span>

<span data-ttu-id="1a488-118">По умолчанию операция миграции выводит состояние процесса миграции в стандартный вывод (STDOUT).</span><span class="sxs-lookup"><span data-stu-id="1a488-118">By default, the migration operation outputs the state of the migration process to standard output (STDOUT).</span></span> <span data-ttu-id="1a488-119">Если вы используете параметр `--report-file <REPORT_FILE>`, выходные данные сохраняются в указанном файле.</span><span class="sxs-lookup"><span data-stu-id="1a488-119">If you use the `--report-file <REPORT_FILE>` option, the output is saved to the file specify.</span></span> 

<span data-ttu-id="1a488-120">Команда `dotnet migrate` поддерживает только допустимые проекты предварительной версии 2 на основе *project.json*.</span><span class="sxs-lookup"><span data-stu-id="1a488-120">The `dotnet migrate` command only supports valid Preview 2 *project.json*-based projects.</span></span> <span data-ttu-id="1a488-121">Это означает, что она не позволяет перенести проекты DNX или проекты предварительной версии 1 на базе *project.json* непосредственно в проекты MSBuild/CSPROJ.</span><span class="sxs-lookup"><span data-stu-id="1a488-121">This means that you cannot use it to migrate DNX or Preview 1 *project.json*-based projects directly to MSBuild/csproj projects.</span></span> <span data-ttu-id="1a488-122">Сначала нужно вручную перенести проект в проект версии 2 на основе *project.json*, а затем воспользоваться командой `dotnet migrate` для переноса проекта.</span><span class="sxs-lookup"><span data-stu-id="1a488-122">You first need to manually migrate the project to a Preview 2 *project.json*-based project and then use the `dotnet migrate` command to migrate the project.</span></span>

## <a name="arguments"></a><span data-ttu-id="1a488-123">Аргументы</span><span class="sxs-lookup"><span data-stu-id="1a488-123">Arguments</span></span>

`PROJECT_JSON/GLOBAL_JSON/SOLUTION_FILE/PROJECT_DIR`

<span data-ttu-id="1a488-124">Путь к одному из следующих объектов:</span><span class="sxs-lookup"><span data-stu-id="1a488-124">The path to one of the following:</span></span>

* <span data-ttu-id="1a488-125">переносимый файл *project.json*;</span><span class="sxs-lookup"><span data-stu-id="1a488-125">a *project.json* file to migrate.</span></span>
* <span data-ttu-id="1a488-126">файл *global.json*, куда переносятся папки, указанные в *global.json*;</span><span class="sxs-lookup"><span data-stu-id="1a488-126">a *global.json* file, it will migrate the folders specified in *global.json*.</span></span>
* <span data-ttu-id="1a488-127">файл *solution.sln*, куда переносятся проекты, на которые ссылается решение;</span><span class="sxs-lookup"><span data-stu-id="1a488-127">a *solution.sln* file, it will migrate the projects referenced in the solution.</span></span>
* <span data-ttu-id="1a488-128">каталог для миграции, где выполняется рекурсивный поиск переносимых файлов *project.json*.</span><span class="sxs-lookup"><span data-stu-id="1a488-128">a directory to migrate, it will recursively search for *project.json* files to migrate.</span></span>

<span data-ttu-id="1a488-129">Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="1a488-129">Defaults to current directory if nothing is specified.</span></span>

## <a name="options"></a><span data-ttu-id="1a488-130">Параметры</span><span class="sxs-lookup"><span data-stu-id="1a488-130">Options</span></span>

`-h|--help`

<span data-ttu-id="1a488-131">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="1a488-131">Prints out a short help for the command.</span></span>

`-t|--template-file <TEMPLATE_FILE>`

<span data-ttu-id="1a488-132">Файл CSPROJ шаблона для переноса.</span><span class="sxs-lookup"><span data-stu-id="1a488-132">Template csproj file to use for migration.</span></span> <span data-ttu-id="1a488-133">По умолчанию используется тот же шаблон, что и проигнорированный в `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="1a488-133">By default, the same template as the one dropped by `dotnet new console` is used.</span></span>

`-v|--sdk-package-version <VERSION>`

<span data-ttu-id="1a488-134">Версия пакета SDK, на которую ссылается перенесенное приложение.</span><span class="sxs-lookup"><span data-stu-id="1a488-134">The version of the sdk package that's referenced in the migrated app.</span></span> <span data-ttu-id="1a488-135">По умолчанию используется версия пакета SDK в `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="1a488-135">The default is the version of the SDK in `dotnet new`.</span></span>

`-x|--xproj-file <FILE>`

<span data-ttu-id="1a488-136">Путь к файлу XPROJ, который будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="1a488-136">The path to the xproj file to use.</span></span> <span data-ttu-id="1a488-137">Требуется, если в каталоге проекта несколько файлов XPROJ.</span><span class="sxs-lookup"><span data-stu-id="1a488-137">Required when there is more than one xproj in a project directory.</span></span>

`-s|--skip-project-references [Debug|Release]`

<span data-ttu-id="1a488-138">Пропуск ссылок проекта для миграции.</span><span class="sxs-lookup"><span data-stu-id="1a488-138">Skip migrating project references.</span></span> <span data-ttu-id="1a488-139">По умолчанию ссылки проекта переносятся рекурсивно.</span><span class="sxs-lookup"><span data-stu-id="1a488-139">By default, project references are migrated recursively.</span></span>

`-r|--report-file <REPORT_FILE>`

<span data-ttu-id="1a488-140">Вывод отчета о миграции в файл наряду с выводом в консоль.</span><span class="sxs-lookup"><span data-stu-id="1a488-140">Output migration report to a file in addition to the console.</span></span>

`--format-report-file-json <REPORT_FILE>`

<span data-ttu-id="1a488-141">Вывод отчета о миграции в файл JSON вместо отправки сообщений пользователю.</span><span class="sxs-lookup"><span data-stu-id="1a488-141">Output migration report file as JSON rather than user messages.</span></span>

`--skip-backup`

<span data-ttu-id="1a488-142">Пропуск перемещения *project.json*, *global.json* и *\\*.xproj* в каталог `backup` после успешной миграции.</span><span class="sxs-lookup"><span data-stu-id="1a488-142">Skip moving *project.json*, *global.json*, and *\\*.xproj* to a `backup` directory after successful migration.</span></span>

## <a name="examples"></a><span data-ttu-id="1a488-143">Примеры</span><span class="sxs-lookup"><span data-stu-id="1a488-143">Examples</span></span>

<span data-ttu-id="1a488-144">Перенос проекта в текущем каталоге и всех взаимных зависимостей проектов.</span><span class="sxs-lookup"><span data-stu-id="1a488-144">Migrate a project in the current directory and all of its project-to-project dependencies:</span></span>

`dotnet migrate`

<span data-ttu-id="1a488-145">Перенос всех проектов, включенных в файл *global.json*:</span><span class="sxs-lookup"><span data-stu-id="1a488-145">Migrate all projects that *global.json* file includes:</span></span>

`dotnet migrate path/to/global.json`

<span data-ttu-id="1a488-146">Перенос только текущего проекта без взаимных зависимостей проектов.</span><span class="sxs-lookup"><span data-stu-id="1a488-146">Migrate only the current project and no project-to-project (P2P) dependencies.</span></span> <span data-ttu-id="1a488-147">Кроме того, используется определенная версия пакета SDK:</span><span class="sxs-lookup"><span data-stu-id="1a488-147">Also, use a specific SDK version:</span></span>

`dotnet migrate -s -v 1.0.0-preview4`
