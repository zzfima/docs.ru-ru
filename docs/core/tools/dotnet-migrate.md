---
title: Команда dotnet migrate
description: Команда dotnet migrate переносит проект и все его зависимости.
ms.date: 08/08/2019
ms.openlocfilehash: afc16161761d151e743e53a8572a6564add43517
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117694"
---
# <a name="dotnet-migrate"></a><span data-ttu-id="9d4f0-103">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="9d4f0-103">dotnet migrate</span></span>

<span data-ttu-id="9d4f0-104">**Эта статья применима к: ✓**Пакет SDK для .NET Core 1.x **✓**Пакет SDK для .NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="9d4f0-104">**This article applies to: ✓** .NET Core 1.x SDK **✓** .NET Core 2.x SDK</span></span>

## <a name="name"></a><span data-ttu-id="9d4f0-105">name</span><span class="sxs-lookup"><span data-stu-id="9d4f0-105">Name</span></span>

<span data-ttu-id="9d4f0-106">`dotnet migrate` — перемещает проект .NET Core предварительной версии 2 в проект в стиле пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-106">`dotnet migrate` - Migrates a Preview 2 .NET Core project to a .NET Core SDK-style project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="9d4f0-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9d4f0-107">Synopsis</span></span>

```dotnetcli
dotnet migrate [<SOLUTION_FILE|PROJECT_DIR>] [--format-report-file-json] [-r|--report-file] [-s|--skip-project-references] [--skip-backup] [-t|--template-file] [-v|--sdk-package-version] [-x|--xproj-file]
dotnet migrate [-h|--help]
```

## <a name="description"></a><span data-ttu-id="9d4f0-108">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="9d4f0-108">Description</span></span>

<span data-ttu-id="9d4f0-109">Команда `dotnet migrate` переносит действительный проект предварительной версии 2 на основе *project.json* в действительный проект *CSPROJ* в стиле пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-109">The `dotnet migrate` command migrates a valid Preview 2 *project.json*-based project to a valid .NET Core SDK-style *csproj* project.</span></span>

<span data-ttu-id="9d4f0-110">По умолчанию команда переносит корневой проект и все ссылки, которые он содержит.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-110">By default, the command migrates the root project and any project references that the root project contains.</span></span> <span data-ttu-id="9d4f0-111">Это поведение можно отключить в среде выполнения с помощью параметра `--skip-project-references`.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-111">This behavior is disabled using the `--skip-project-references` option at runtime.</span></span>

<span data-ttu-id="9d4f0-112">Миграция выполняется для следующих ресурсов:</span><span class="sxs-lookup"><span data-stu-id="9d4f0-112">Migration can be performed on the following assets:</span></span>

* <span data-ttu-id="9d4f0-113">Отдельный проект посредством указания нужного файла *project.json*.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-113">A single project by specifying the *project.json* file to migrate.</span></span>
* <span data-ttu-id="9d4f0-114">Все каталоги, указанные в файле *global.json*, посредством передачи пути в файл *global.json*.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-114">All of the directories specified in the *global.json* file by passing in a path to the *global.json* file.</span></span>
* <span data-ttu-id="9d4f0-115">Файл *solution.sln*, куда переносятся проекты, на которые ссылается решение.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-115">A *solution.sln* file, where it migrates the projects referenced in the solution.</span></span>
* <span data-ttu-id="9d4f0-116">Рекурсивно все подкаталоги в этом каталоге.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-116">On all subdirectories of the given directory recursively.</span></span>

<span data-ttu-id="9d4f0-117">Команда `dotnet migrate` сохраняет перенесенный файл *project.json* в каталоге `backup` (создается, если не существует).</span><span class="sxs-lookup"><span data-stu-id="9d4f0-117">The `dotnet migrate` command keeps the migrated *project.json* file inside a `backup` directory, which it creates if the directory doesn't exist.</span></span> <span data-ttu-id="9d4f0-118">Это поведение можно переопределить с помощью параметра `--skip-backup`.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-118">This behavior is overridden using the `--skip-backup` option.</span></span>

<span data-ttu-id="9d4f0-119">По умолчанию операция миграции выводит состояние процесса миграции в стандартный вывод (STDOUT).</span><span class="sxs-lookup"><span data-stu-id="9d4f0-119">By default, the migration operation outputs the state of the migration process to standard output (STDOUT).</span></span> <span data-ttu-id="9d4f0-120">Если вы используете параметр `--report-file <REPORT_FILE>`, выходные данные сохраняются в указанном файле.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-120">If you use the `--report-file <REPORT_FILE>` option, the output is saved to the file specify.</span></span>

<span data-ttu-id="9d4f0-121">Команда `dotnet migrate` поддерживает только допустимые проекты предварительной версии 2 на основе *project.json*.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-121">The `dotnet migrate` command only supports valid Preview 2 *project.json*-based projects.</span></span> <span data-ttu-id="9d4f0-122">Это означает, что она не позволяет перенести проекты DNX или проекты предварительной версии 1 на базе *project.json* непосредственно в проекты MSBuild/CSPROJ.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-122">This means that you cannot use it to migrate DNX or Preview 1 *project.json*-based projects directly to MSBuild/csproj projects.</span></span> <span data-ttu-id="9d4f0-123">Сначала нужно вручную перенести проект в проект версии 2 на основе *project.json*, а затем воспользоваться командой `dotnet migrate` для переноса проекта.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-123">You first need to manually migrate the project to a Preview 2 *project.json*-based project and then use the `dotnet migrate` command to migrate the project.</span></span>

<span data-ttu-id="9d4f0-124">Команда `dotnet migrate` недоступна начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-124">The `dotnet migrate` command is no longer available starting with .NET Core 3.0 SDK.</span></span>

## <a name="arguments"></a><span data-ttu-id="9d4f0-125">Аргументы</span><span class="sxs-lookup"><span data-stu-id="9d4f0-125">Arguments</span></span>

`PROJECT_JSON/GLOBAL_JSON/SOLUTION_FILE/PROJECT_DIR`

<span data-ttu-id="9d4f0-126">Путь к одному из следующих объектов:</span><span class="sxs-lookup"><span data-stu-id="9d4f0-126">The path to one of the following:</span></span>

* <span data-ttu-id="9d4f0-127">переносимый файл *project.json*;</span><span class="sxs-lookup"><span data-stu-id="9d4f0-127">a *project.json* file to migrate.</span></span>
* <span data-ttu-id="9d4f0-128">файл *global.json*: переносятся папки, указанные в *global.json*;</span><span class="sxs-lookup"><span data-stu-id="9d4f0-128">a *global.json* file: the folders specified in *global.json* are migrated.</span></span>
* <span data-ttu-id="9d4f0-129">файл *solution.sln*: переносятся проекты, на которые ссылается решение;</span><span class="sxs-lookup"><span data-stu-id="9d4f0-129">a *solution.sln* file: the projects referenced in the solution are migrated.</span></span>
* <span data-ttu-id="9d4f0-130">каталог для миграции: выполняется рекурсивный поиск переносимых файлов *project.json* в указанном каталоге.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-130">a directory to migrate: recursively searches for *project.json* files to migrate inside the specified directory.</span></span>

<span data-ttu-id="9d4f0-131">Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-131">Defaults to current directory if nothing is specified.</span></span>

## <a name="options"></a><span data-ttu-id="9d4f0-132">Параметры</span><span class="sxs-lookup"><span data-stu-id="9d4f0-132">Options</span></span>

`--format-report-file-json <REPORT_FILE>`

<span data-ttu-id="9d4f0-133">Вывод отчета о миграции в файл JSON вместо отправки сообщений пользователю.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-133">Output migration report file as JSON rather than user messages.</span></span>

`-h|--help`

<span data-ttu-id="9d4f0-134">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-134">Prints out a short help for the command.</span></span>

`-r|--report-file <REPORT_FILE>`

<span data-ttu-id="9d4f0-135">Вывод отчета о миграции в файл наряду с выводом в консоль.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-135">Output migration report to a file in addition to the console.</span></span>

`-s|--skip-project-references [Debug|Release]`

<span data-ttu-id="9d4f0-136">Пропуск ссылок проекта для миграции.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-136">Skip migrating project references.</span></span> <span data-ttu-id="9d4f0-137">По умолчанию ссылки проекта переносятся рекурсивно.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-137">By default, project references are migrated recursively.</span></span>

`--skip-backup`

<span data-ttu-id="9d4f0-138">Пропуск перемещения *project.json*, *global.json* и *\*.xproj* в каталог `backup` после успешной миграции.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-138">Skip moving *project.json*, *global.json*, and *\*.xproj* to a `backup` directory after successful migration.</span></span>

`-t|--template-file <TEMPLATE_FILE>`

<span data-ttu-id="9d4f0-139">Файл CSPROJ шаблона для переноса.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-139">Template csproj file to use for migration.</span></span> <span data-ttu-id="9d4f0-140">По умолчанию используется тот же шаблон, что и проигнорированный в `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-140">By default, the same template as the one dropped by `dotnet new console` is used.</span></span>

`-v|--sdk-package-version <VERSION>`

<span data-ttu-id="9d4f0-141">Версия пакета SDK, на которую ссылается перенесенное приложение.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-141">The version of the sdk package that's referenced in the migrated app.</span></span> <span data-ttu-id="9d4f0-142">По умолчанию используется версия пакета SDK в `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-142">The default is the version of the SDK in `dotnet new`.</span></span>

`-x|--xproj-file <FILE>`

<span data-ttu-id="9d4f0-143">Путь к файлу XPROJ, который будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-143">The path to the xproj file to use.</span></span> <span data-ttu-id="9d4f0-144">Требуется, если в каталоге проекта несколько файлов XPROJ.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-144">Required when there is more than one xproj in a project directory.</span></span>

## <a name="examples"></a><span data-ttu-id="9d4f0-145">Примеры</span><span class="sxs-lookup"><span data-stu-id="9d4f0-145">Examples</span></span>

<span data-ttu-id="9d4f0-146">Перенос проекта в текущем каталоге и всех взаимных зависимостей проектов.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-146">Migrate a project in the current directory and all of its project-to-project dependencies:</span></span>

`dotnet migrate`

<span data-ttu-id="9d4f0-147">Перенос всех проектов, включенных в файл *global.json*:</span><span class="sxs-lookup"><span data-stu-id="9d4f0-147">Migrate all projects that *global.json* file includes:</span></span>

`dotnet migrate path/to/global.json`

<span data-ttu-id="9d4f0-148">Перенос только текущего проекта без взаимных зависимостей проектов.</span><span class="sxs-lookup"><span data-stu-id="9d4f0-148">Migrate only the current project and no project-to-project (P2P) dependencies.</span></span> <span data-ttu-id="9d4f0-149">Кроме того, используется определенная версия пакета SDK:</span><span class="sxs-lookup"><span data-stu-id="9d4f0-149">Also, use a specific SDK version:</span></span>

`dotnet migrate -s -v 1.0.0-preview4`
