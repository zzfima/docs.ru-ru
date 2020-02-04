---
title: Интерфейс командной строки .NET Core
titleSuffix: ''
description: Общие сведения о .NET Core CLI и его функциях.
ms.date: 08/14/2017
ms.openlocfilehash: b0a8e0dd8cf77bb6f7567c27e9972f62515ec0f2
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920484"
---
# <a name="net-core-cli-overview"></a><span data-ttu-id="0f83d-103">Обзор .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="0f83d-103">.NET Core CLI overview</span></span>

<span data-ttu-id="0f83d-104">Интерфейс командной строки (CLI) .NET Core — это новая базовая кроссплатформенная цепочка инструментов для разработки, компиляции, запуска и публикации приложений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0f83d-104">The .NET Core command-line interface (CLI) is a cross-platform toolchain for developing, building, running, and publishing .NET Core applications.</span></span>

<span data-ttu-id="0f83d-105">.NET Core CLI входит в [пакет SDK для .NET Core](../sdk.md).</span><span class="sxs-lookup"><span data-stu-id="0f83d-105">The .NET Core CLI is included with the [.NET Core SDK](../sdk.md).</span></span> <span data-ttu-id="0f83d-106">Дополнительные сведения об установке пакета SDK для .NET Core см. [здесь](../install/sdk.md).</span><span class="sxs-lookup"><span data-stu-id="0f83d-106">To learn how to install the .NET Core SDK, see [Install the .NET Core SDK](../install/sdk.md).</span></span>

## <a name="cli-commands"></a><span data-ttu-id="0f83d-107">Команды CLI</span><span class="sxs-lookup"><span data-stu-id="0f83d-107">CLI commands</span></span>

<span data-ttu-id="0f83d-108">По умолчанию устанавливаются следующие команды:</span><span class="sxs-lookup"><span data-stu-id="0f83d-108">The following commands are installed by default:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="0f83d-109">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="0f83d-109">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="0f83d-110">**Основные команды**</span><span class="sxs-lookup"><span data-stu-id="0f83d-110">**Basic commands**</span></span>

- [<span data-ttu-id="0f83d-111">new</span><span class="sxs-lookup"><span data-stu-id="0f83d-111">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="0f83d-112">restore</span><span class="sxs-lookup"><span data-stu-id="0f83d-112">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="0f83d-113">build</span><span class="sxs-lookup"><span data-stu-id="0f83d-113">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="0f83d-114">publish</span><span class="sxs-lookup"><span data-stu-id="0f83d-114">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="0f83d-115">run</span><span class="sxs-lookup"><span data-stu-id="0f83d-115">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="0f83d-116">test</span><span class="sxs-lookup"><span data-stu-id="0f83d-116">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="0f83d-117">vstest</span><span class="sxs-lookup"><span data-stu-id="0f83d-117">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="0f83d-118">pack</span><span class="sxs-lookup"><span data-stu-id="0f83d-118">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="0f83d-119">migrate</span><span class="sxs-lookup"><span data-stu-id="0f83d-119">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="0f83d-120">clean</span><span class="sxs-lookup"><span data-stu-id="0f83d-120">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="0f83d-121">sln</span><span class="sxs-lookup"><span data-stu-id="0f83d-121">sln</span></span>](dotnet-sln.md)
- [<span data-ttu-id="0f83d-122">help</span><span class="sxs-lookup"><span data-stu-id="0f83d-122">help</span></span>](dotnet-help.md)
- [<span data-ttu-id="0f83d-123">store</span><span class="sxs-lookup"><span data-stu-id="0f83d-123">store</span></span>](dotnet-store.md)

<span data-ttu-id="0f83d-124">**Команды для изменения проекта**</span><span class="sxs-lookup"><span data-stu-id="0f83d-124">**Project modification commands**</span></span>

- [<span data-ttu-id="0f83d-125">add package</span><span class="sxs-lookup"><span data-stu-id="0f83d-125">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="0f83d-126">add reference</span><span class="sxs-lookup"><span data-stu-id="0f83d-126">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="0f83d-127">remove package</span><span class="sxs-lookup"><span data-stu-id="0f83d-127">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="0f83d-128">remove reference</span><span class="sxs-lookup"><span data-stu-id="0f83d-128">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="0f83d-129">list reference</span><span class="sxs-lookup"><span data-stu-id="0f83d-129">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="0f83d-130">**Расширенные команды**</span><span class="sxs-lookup"><span data-stu-id="0f83d-130">**Advanced commands**</span></span>

- [<span data-ttu-id="0f83d-131">nuget delete</span><span class="sxs-lookup"><span data-stu-id="0f83d-131">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="0f83d-132">nuget locals</span><span class="sxs-lookup"><span data-stu-id="0f83d-132">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="0f83d-133">nuget push</span><span class="sxs-lookup"><span data-stu-id="0f83d-133">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="0f83d-134">msbuild</span><span class="sxs-lookup"><span data-stu-id="0f83d-134">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="0f83d-135">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="0f83d-135">dotnet install script</span></span>](dotnet-install-script.md)

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0f83d-136">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0f83d-136">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="0f83d-137">**Основные команды**</span><span class="sxs-lookup"><span data-stu-id="0f83d-137">**Basic commands**</span></span>

- [<span data-ttu-id="0f83d-138">new</span><span class="sxs-lookup"><span data-stu-id="0f83d-138">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="0f83d-139">restore</span><span class="sxs-lookup"><span data-stu-id="0f83d-139">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="0f83d-140">build</span><span class="sxs-lookup"><span data-stu-id="0f83d-140">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="0f83d-141">publish</span><span class="sxs-lookup"><span data-stu-id="0f83d-141">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="0f83d-142">run</span><span class="sxs-lookup"><span data-stu-id="0f83d-142">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="0f83d-143">test</span><span class="sxs-lookup"><span data-stu-id="0f83d-143">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="0f83d-144">vstest</span><span class="sxs-lookup"><span data-stu-id="0f83d-144">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="0f83d-145">pack</span><span class="sxs-lookup"><span data-stu-id="0f83d-145">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="0f83d-146">migrate</span><span class="sxs-lookup"><span data-stu-id="0f83d-146">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="0f83d-147">clean</span><span class="sxs-lookup"><span data-stu-id="0f83d-147">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="0f83d-148">sln</span><span class="sxs-lookup"><span data-stu-id="0f83d-148">sln</span></span>](dotnet-sln.md)

<span data-ttu-id="0f83d-149">**Команды для изменения проекта**</span><span class="sxs-lookup"><span data-stu-id="0f83d-149">**Project modification commands**</span></span>

- [<span data-ttu-id="0f83d-150">add package</span><span class="sxs-lookup"><span data-stu-id="0f83d-150">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="0f83d-151">add reference</span><span class="sxs-lookup"><span data-stu-id="0f83d-151">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="0f83d-152">remove package</span><span class="sxs-lookup"><span data-stu-id="0f83d-152">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="0f83d-153">remove reference</span><span class="sxs-lookup"><span data-stu-id="0f83d-153">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="0f83d-154">list reference</span><span class="sxs-lookup"><span data-stu-id="0f83d-154">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="0f83d-155">**Расширенные команды**</span><span class="sxs-lookup"><span data-stu-id="0f83d-155">**Advanced commands**</span></span>

- [<span data-ttu-id="0f83d-156">nuget delete</span><span class="sxs-lookup"><span data-stu-id="0f83d-156">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="0f83d-157">nuget locals</span><span class="sxs-lookup"><span data-stu-id="0f83d-157">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="0f83d-158">nuget push</span><span class="sxs-lookup"><span data-stu-id="0f83d-158">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="0f83d-159">msbuild</span><span class="sxs-lookup"><span data-stu-id="0f83d-159">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="0f83d-160">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="0f83d-160">dotnet install script</span></span>](dotnet-install-script.md)

---

<span data-ttu-id="0f83d-161">Интерфейс CLI использует модель расширяемости, которая позволяет указывать дополнительные средства для проектов.</span><span class="sxs-lookup"><span data-stu-id="0f83d-161">The CLI adopts an extensibility model that allows you to specify additional tools for your projects.</span></span> <span data-ttu-id="0f83d-162">Дополнительные сведения см. в разделе [Модель расширяемости CLI .NET Core](extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="0f83d-162">For more information, see the [.NET Core CLI extensibility model](extensibility.md) topic.</span></span>

## <a name="command-structure"></a><span data-ttu-id="0f83d-163">Структура команд</span><span class="sxs-lookup"><span data-stu-id="0f83d-163">Command structure</span></span>

<span data-ttu-id="0f83d-164">Структура команд CLI состоит из [драйвера ("dotnet")](#driver), [самой команды](#command) и ее возможных [аргументов](#arguments) и [параметров](#options).</span><span class="sxs-lookup"><span data-stu-id="0f83d-164">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="0f83d-165">Этот шаблон используется в большинстве операций интерфейса командной строки, таких как создание консольного приложения и его запуск из командной строки, как показывают следующие команды при выполнении из каталога *my_app*:</span><span class="sxs-lookup"><span data-stu-id="0f83d-165">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="0f83d-166">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="0f83d-166">.NET Core 2.x</span></span>](#tab/netcore2x)

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0f83d-167">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0f83d-167">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet new console
dotnet restore
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

---

### <a name="driver"></a><span data-ttu-id="0f83d-168">Драйвер</span><span class="sxs-lookup"><span data-stu-id="0f83d-168">Driver</span></span>

<span data-ttu-id="0f83d-169">Драйвер называется [dotnet](dotnet.md) и имеет два вида ответственности — выполнение [платформозависимого приложения](../deploying/index.md) или выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="0f83d-169">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span> 

<span data-ttu-id="0f83d-170">Для запуска платформозависимого приложения укажите его драйвера, например `dotnet /path/to/my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="0f83d-170">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="0f83d-171">При выполнении команды из папки, где находится библиотека DLL приложения, просто выполните `dotnet my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="0f83d-171">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="0f83d-172">Если вы хотите использовать конкретную версию среды выполнения .NET Core, используйте параметр `--fx-version <VERSION>` (см. справку по [команде dotnet](dotnet.md)).</span><span class="sxs-lookup"><span data-stu-id="0f83d-172">If you want to use a specific version of the .NET Core Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="0f83d-173">При указании команды для драйвера `dotnet.exe` запускает процесс выполнения команды CLI.</span><span class="sxs-lookup"><span data-stu-id="0f83d-173">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="0f83d-174">Пример:</span><span class="sxs-lookup"><span data-stu-id="0f83d-174">For example:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="0f83d-175">Сначала драйвер определяет нужную версию пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="0f83d-175">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="0f83d-176">Если файл ["global.json"](global-json.md) отсутствует, используется последняя доступная версия пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="0f83d-176">If there is no ['global.json'](global-json.md), the latest version of the SDK available is used.</span></span> <span data-ttu-id="0f83d-177">Это может быть предварительная или стабильная версия, в зависимости от того, какая версия является последней на компьютере.</span><span class="sxs-lookup"><span data-stu-id="0f83d-177">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="0f83d-178">После определения версии пакета SDK он выполняет команду.</span><span class="sxs-lookup"><span data-stu-id="0f83d-178">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="0f83d-179">Команда</span><span class="sxs-lookup"><span data-stu-id="0f83d-179">Command</span></span>

<span data-ttu-id="0f83d-180">Команда выполняет действие.</span><span class="sxs-lookup"><span data-stu-id="0f83d-180">The command performs an action.</span></span> <span data-ttu-id="0f83d-181">Например, `dotnet build` проводит сборку кода.</span><span class="sxs-lookup"><span data-stu-id="0f83d-181">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="0f83d-182">`dotnet publish` публикует код.</span><span class="sxs-lookup"><span data-stu-id="0f83d-182">`dotnet publish` publishes code.</span></span> <span data-ttu-id="0f83d-183">Команды реализуются как консольное приложение с использованием соглашения `dotnet {command}`.</span><span class="sxs-lookup"><span data-stu-id="0f83d-183">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="0f83d-184">Аргументы</span><span class="sxs-lookup"><span data-stu-id="0f83d-184">Arguments</span></span>

<span data-ttu-id="0f83d-185">Аргументы, указываемые в командной строке, передаются непосредственно в вызываемую команду.</span><span class="sxs-lookup"><span data-stu-id="0f83d-185">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="0f83d-186">Например, если выполнить `dotnet publish my_app.csproj`, аргумент `my_app.csproj` указывает публикуемый проект и передается в команду `publish`.</span><span class="sxs-lookup"><span data-stu-id="0f83d-186">For example when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="0f83d-187">Параметры</span><span class="sxs-lookup"><span data-stu-id="0f83d-187">Options</span></span>

<span data-ttu-id="0f83d-188">Параметры, указываемые в командной строке, передаются непосредственно в вызываемую команду.</span><span class="sxs-lookup"><span data-stu-id="0f83d-188">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="0f83d-189">Например, при выполнении `dotnet publish --output /build_output` параметр `--output` и его значение передаются в команду `publish`.</span><span class="sxs-lookup"><span data-stu-id="0f83d-189">For example when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="migration-from-projectjson"></a><span data-ttu-id="0f83d-190">Перенос из проекта project.json</span><span class="sxs-lookup"><span data-stu-id="0f83d-190">Migration from project.json</span></span>

<span data-ttu-id="0f83d-191">Если вы использовали средства предварительной версии 2 для создания проектов на основе *project.json*, обратитесь к разделу о [dotnet migrate](dotnet-migrate.md) за информацией о переносе проекта в MSBuild/*.csproj*, чтобы его можно было использовать со средствами версии выпуска.</span><span class="sxs-lookup"><span data-stu-id="0f83d-191">If you used Preview 2 tooling to produce *project.json*-based projects, consult the [dotnet migrate](dotnet-migrate.md) topic for information on migrating your project to MSBuild/*.csproj* for use with release tooling.</span></span> <span data-ttu-id="0f83d-192">Для проектов .NET Core, созданных до выхода средств предварительной версии 2, обновите проект вручную, выполнив указания из раздела [Переход с DNX на интерфейс CLI .NET Core (project.json)](../migration/from-dnx.md) и воспользовавшись `dotnet migrate`, либо обновите свои проекты напрямую.</span><span class="sxs-lookup"><span data-stu-id="0f83d-192">For .NET Core projects created prior to the release of Preview 2 tooling, either manually update the project following the guidance in [Migrating from DNX to .NET Core CLI (project.json)](../migration/from-dnx.md) and then use `dotnet migrate` or directly upgrade your projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="0f83d-193">См. также</span><span class="sxs-lookup"><span data-stu-id="0f83d-193">See also</span></span>

- [<span data-ttu-id="0f83d-194">Репозиторий GitHub dotnet/sdk</span><span class="sxs-lookup"><span data-stu-id="0f83d-194">dotnet/sdk GitHub repository</span></span>](https://github.com/dotnet/sdk/)
- [<span data-ttu-id="0f83d-195">Руководство по установке .NET Core</span><span class="sxs-lookup"><span data-stu-id="0f83d-195">.NET Core installation guide</span></span>](https://aka.ms/dotnetcoregs)
