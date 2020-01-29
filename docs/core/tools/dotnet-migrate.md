---
title: Команда dotnet migrate
description: Команда dotnet migrate переносит проект и все его зависимости.
ms.date: 01/07/2020
ms.openlocfilehash: b81669d3e4cffeaf10bea39639410d5f06579d84
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734144"
---
# <a name="dotnet-migrate"></a><span data-ttu-id="4fa67-103">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="4fa67-103">dotnet migrate</span></span>

<span data-ttu-id="4fa67-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 1.x ✔️ SDK для .NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="4fa67-104">**This article applies to:** ✔️ .NET Core 1.x SDK ✔️ .NET Core 2.x SDK</span></span>

## <a name="name"></a><span data-ttu-id="4fa67-105">name</span><span class="sxs-lookup"><span data-stu-id="4fa67-105">Name</span></span>

<span data-ttu-id="4fa67-106">`dotnet migrate` — перемещает проект .NET Core предварительной версии 2 в проект в стиле пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4fa67-106">`dotnet migrate` - Migrates a Preview 2 .NET Core project to a .NET Core SDK-style project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4fa67-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4fa67-107">Synopsis</span></span>

```dotnetcli
dotnet migrate [<SOLUTION_FILE|PROJECT_DIR>] [--format-report-file-json] [-r|--report-file] [-s|--skip-project-references] [--skip-backup] [-t|--template-file] [-v|--sdk-package-version] [-x|--xproj-file]
dotnet migrate [-h|--help]
```

## <a name="description"></a><span data-ttu-id="4fa67-108">Описание</span><span class="sxs-lookup"><span data-stu-id="4fa67-108">Description</span></span>

<span data-ttu-id="4fa67-109">Эта команда отключена.</span><span class="sxs-lookup"><span data-stu-id="4fa67-109">This command is deprecated.</span></span> <span data-ttu-id="4fa67-110">Команда `dotnet migrate` недоступна начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="4fa67-110">The `dotnet migrate` command is no longer available starting with .NET Core 3.0 SDK.</span></span> <span data-ttu-id="4fa67-111">Она выполняет только миграцию проекта .NET Core (предварительная версия 2) в проект .NET Core 1.x, который не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="4fa67-111">It can only migrate a Preview 2 .NET Core project to a 1.x .NET Core project, which is out of support.</span></span>

<span data-ttu-id="4fa67-112">По умолчанию команда переносит корневой проект и все ссылки, которые он содержит.</span><span class="sxs-lookup"><span data-stu-id="4fa67-112">By default, the command migrates the root project and any project references that the root project contains.</span></span> <span data-ttu-id="4fa67-113">Это поведение можно отключить в среде выполнения с помощью параметра `--skip-project-references`.</span><span class="sxs-lookup"><span data-stu-id="4fa67-113">This behavior is disabled using the `--skip-project-references` option at runtime.</span></span>

<span data-ttu-id="4fa67-114">Миграция выполняется для следующих ресурсов:</span><span class="sxs-lookup"><span data-stu-id="4fa67-114">Migration can be performed on the following assets:</span></span>

* <span data-ttu-id="4fa67-115">Отдельный проект посредством указания нужного файла *project.json*.</span><span class="sxs-lookup"><span data-stu-id="4fa67-115">A single project by specifying the *project.json* file to migrate.</span></span>
* <span data-ttu-id="4fa67-116">Все каталоги, указанные в файле *global.json*, посредством передачи пути в файл *global.json*.</span><span class="sxs-lookup"><span data-stu-id="4fa67-116">All of the directories specified in the *global.json* file by passing in a path to the *global.json* file.</span></span>
* <span data-ttu-id="4fa67-117">Файл *solution.sln*, куда переносятся проекты, на которые ссылается решение.</span><span class="sxs-lookup"><span data-stu-id="4fa67-117">A *solution.sln* file, where it migrates the projects referenced in the solution.</span></span>
* <span data-ttu-id="4fa67-118">Рекурсивно все подкаталоги в этом каталоге.</span><span class="sxs-lookup"><span data-stu-id="4fa67-118">On all subdirectories of the given directory recursively.</span></span>

<span data-ttu-id="4fa67-119">Команда `dotnet migrate` сохраняет перенесенный файл *project.json* в каталоге `backup` (создается, если не существует).</span><span class="sxs-lookup"><span data-stu-id="4fa67-119">The `dotnet migrate` command keeps the migrated *project.json* file inside a `backup` directory, which it creates if the directory doesn't exist.</span></span> <span data-ttu-id="4fa67-120">Это поведение можно переопределить с помощью параметра `--skip-backup`.</span><span class="sxs-lookup"><span data-stu-id="4fa67-120">This behavior is overridden using the `--skip-backup` option.</span></span>

<span data-ttu-id="4fa67-121">По умолчанию операция миграции выводит состояние процесса миграции в стандартный вывод (STDOUT).</span><span class="sxs-lookup"><span data-stu-id="4fa67-121">By default, the migration operation outputs the state of the migration process to standard output (STDOUT).</span></span> <span data-ttu-id="4fa67-122">Если вы используете параметр `--report-file <REPORT_FILE>`, выходные данные сохраняются в указанном файле.</span><span class="sxs-lookup"><span data-stu-id="4fa67-122">If you use the `--report-file <REPORT_FILE>` option, the output is saved to the file specify.</span></span>

<span data-ttu-id="4fa67-123">Команда `dotnet migrate` поддерживает только допустимые проекты предварительной версии 2 на основе *project.json*.</span><span class="sxs-lookup"><span data-stu-id="4fa67-123">The `dotnet migrate` command only supports valid Preview 2 *project.json*-based projects.</span></span> <span data-ttu-id="4fa67-124">Это означает, что она не позволяет перенести проекты DNX или проекты предварительной версии 1 на базе *project.json* непосредственно в проекты MSBuild/CSPROJ.</span><span class="sxs-lookup"><span data-stu-id="4fa67-124">This means that you cannot use it to migrate DNX or Preview 1 *project.json*-based projects directly to MSBuild/csproj projects.</span></span> <span data-ttu-id="4fa67-125">Сначала нужно вручную перенести проект в проект версии 2 на основе *project.json*, а затем воспользоваться командой `dotnet migrate` для переноса проекта.</span><span class="sxs-lookup"><span data-stu-id="4fa67-125">You first need to manually migrate the project to a Preview 2 *project.json*-based project and then use the `dotnet migrate` command to migrate the project.</span></span>

## <a name="arguments"></a><span data-ttu-id="4fa67-126">Аргументы</span><span class="sxs-lookup"><span data-stu-id="4fa67-126">Arguments</span></span>

`PROJECT_JSON/GLOBAL_JSON/SOLUTION_FILE/PROJECT_DIR`

<span data-ttu-id="4fa67-127">Путь к одному из следующих объектов:</span><span class="sxs-lookup"><span data-stu-id="4fa67-127">The path to one of the following:</span></span>

* <span data-ttu-id="4fa67-128">переносимый файл *project.json*;</span><span class="sxs-lookup"><span data-stu-id="4fa67-128">a *project.json* file to migrate.</span></span>
* <span data-ttu-id="4fa67-129">файл *global.json*: переносятся папки, указанные в *global.json*;</span><span class="sxs-lookup"><span data-stu-id="4fa67-129">a *global.json* file: the folders specified in *global.json* are migrated.</span></span>
* <span data-ttu-id="4fa67-130">файл *solution.sln*: переносятся проекты, на которые ссылается решение;</span><span class="sxs-lookup"><span data-stu-id="4fa67-130">a *solution.sln* file: the projects referenced in the solution are migrated.</span></span>
* <span data-ttu-id="4fa67-131">каталог для миграции: выполняется рекурсивный поиск переносимых файлов *project.json* в указанном каталоге.</span><span class="sxs-lookup"><span data-stu-id="4fa67-131">a directory to migrate: recursively searches for *project.json* files to migrate inside the specified directory.</span></span>

<span data-ttu-id="4fa67-132">Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="4fa67-132">Defaults to current directory if nothing is specified.</span></span>

## <a name="options"></a><span data-ttu-id="4fa67-133">Параметры</span><span class="sxs-lookup"><span data-stu-id="4fa67-133">Options</span></span>

`--format-report-file-json <REPORT_FILE>`

<span data-ttu-id="4fa67-134">Вывод отчета о миграции в файл JSON вместо отправки сообщений пользователю.</span><span class="sxs-lookup"><span data-stu-id="4fa67-134">Output migration report file as JSON rather than user messages.</span></span>

`-h|--help`

<span data-ttu-id="4fa67-135">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="4fa67-135">Prints out a short help for the command.</span></span>

`-r|--report-file <REPORT_FILE>`

<span data-ttu-id="4fa67-136">Вывод отчета о миграции в файл наряду с выводом в консоль.</span><span class="sxs-lookup"><span data-stu-id="4fa67-136">Output migration report to a file in addition to the console.</span></span>

`-s|--skip-project-references [Debug|Release]`

<span data-ttu-id="4fa67-137">Пропуск ссылок проекта для миграции.</span><span class="sxs-lookup"><span data-stu-id="4fa67-137">Skip migrating project references.</span></span> <span data-ttu-id="4fa67-138">По умолчанию ссылки проекта переносятся рекурсивно.</span><span class="sxs-lookup"><span data-stu-id="4fa67-138">By default, project references are migrated recursively.</span></span>

`--skip-backup`

<span data-ttu-id="4fa67-139">Пропуск перемещения *project.json*, *global.json* и *\*.xproj* в каталог `backup` после успешной миграции.</span><span class="sxs-lookup"><span data-stu-id="4fa67-139">Skip moving *project.json*, *global.json*, and *\*.xproj* to a `backup` directory after successful migration.</span></span>

`-t|--template-file <TEMPLATE_FILE>`

<span data-ttu-id="4fa67-140">Файл CSPROJ шаблона для переноса.</span><span class="sxs-lookup"><span data-stu-id="4fa67-140">Template csproj file to use for migration.</span></span> <span data-ttu-id="4fa67-141">По умолчанию используется тот же шаблон, что и проигнорированный в `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="4fa67-141">By default, the same template as the one dropped by `dotnet new console` is used.</span></span>

`-v|--sdk-package-version <VERSION>`

<span data-ttu-id="4fa67-142">Версия пакета SDK, на которую ссылается перенесенное приложение.</span><span class="sxs-lookup"><span data-stu-id="4fa67-142">The version of the sdk package that's referenced in the migrated app.</span></span> <span data-ttu-id="4fa67-143">По умолчанию используется версия пакета SDK в `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="4fa67-143">The default is the version of the SDK in `dotnet new`.</span></span>

`-x|--xproj-file <FILE>`

<span data-ttu-id="4fa67-144">Путь к файлу XPROJ, который будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="4fa67-144">The path to the xproj file to use.</span></span> <span data-ttu-id="4fa67-145">Требуется, если в каталоге проекта несколько файлов XPROJ.</span><span class="sxs-lookup"><span data-stu-id="4fa67-145">Required when there is more than one xproj in a project directory.</span></span>

## <a name="examples"></a><span data-ttu-id="4fa67-146">Примеры</span><span class="sxs-lookup"><span data-stu-id="4fa67-146">Examples</span></span>

<span data-ttu-id="4fa67-147">Перенос проекта в текущем каталоге и всех взаимных зависимостей проектов.</span><span class="sxs-lookup"><span data-stu-id="4fa67-147">Migrate a project in the current directory and all of its project-to-project dependencies:</span></span>

`dotnet migrate`

<span data-ttu-id="4fa67-148">Перенос всех проектов, включенных в файл *global.json*:</span><span class="sxs-lookup"><span data-stu-id="4fa67-148">Migrate all projects that *global.json* file includes:</span></span>

`dotnet migrate path/to/global.json`

<span data-ttu-id="4fa67-149">Перенос только текущего проекта без взаимных зависимостей проектов.</span><span class="sxs-lookup"><span data-stu-id="4fa67-149">Migrate only the current project and no project-to-project (P2P) dependencies.</span></span> <span data-ttu-id="4fa67-150">Кроме того, используется определенная версия пакета SDK:</span><span class="sxs-lookup"><span data-stu-id="4fa67-150">Also, use a specific SDK version:</span></span>

`dotnet migrate -s -v 1.0.0-preview4`
