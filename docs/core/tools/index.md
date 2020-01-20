---
title: Средства интерфейса командной строки (CLI) .NET Core
description: Обзор средств и возможностей интерфейса командной строки (CLI)NET Core.
ms.date: 08/14/2017
ms.openlocfilehash: f19dcb19fb9d0203b3d3795c3fdc0b026c4c60e3
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163219"
---
# <a name="net-core-command-line-interface-cli-tools"></a><span data-ttu-id="b2737-103">Средства интерфейса командной строки (CLI) .NET Core</span><span class="sxs-lookup"><span data-stu-id="b2737-103">.NET Core command-line interface (CLI) tools</span></span>

<span data-ttu-id="b2737-104">Интерфейс командной строки (CLI) .NET Core — это цепочка кроссплатформенных инструментов для разработки приложений .NET.</span><span class="sxs-lookup"><span data-stu-id="b2737-104">The .NET Core command-line interface (CLI) is a cross-platform toolchain for developing .NET applications.</span></span> <span data-ttu-id="b2737-105">Он является той основой, на которую могут опираться инструменты более высоких уровней, такие как интегрированные среды разработки (IDE), редакторы и оркестраторы сборки.</span><span class="sxs-lookup"><span data-stu-id="b2737-105">The CLI is a foundation upon which higher-level tools, such as integrated development environments (IDEs), editors, and build orchestrators, can rest.</span></span>

## <a name="installation"></a><span data-ttu-id="b2737-106">Установка</span><span class="sxs-lookup"><span data-stu-id="b2737-106">Installation</span></span>

<span data-ttu-id="b2737-107">Можно использовать либо собственные установщики, либо скрипты оболочки для установки:</span><span class="sxs-lookup"><span data-stu-id="b2737-107">Either use the native installers or use the installation shell scripts:</span></span>

- <span data-ttu-id="b2737-108">Собственные установщики в основном применяются на компьютерах разработчиков и используют собственные механизмы установки каждой поддерживаемой платформы, например пакеты DEB в Ubuntu или пакеты MSI в Windows.</span><span class="sxs-lookup"><span data-stu-id="b2737-108">The native installers are primarily used on developer's machines and use each supported platform's native install mechanism, for instance, DEB packages on Ubuntu or MSI bundles on Windows.</span></span> <span data-ttu-id="b2737-109">Эти установщики устанавливают и настраивают окружение для немедленного использования разработчиком, но им требуются права администратора на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b2737-109">These installers install and configure the environment for immediate use by the developer but require administrative privileges on the machine.</span></span> <span data-ttu-id="b2737-110">Инструкции по установке см. в [руководстве по установке .NET Core](https://aka.ms/dotnetcoregs).</span><span class="sxs-lookup"><span data-stu-id="b2737-110">You can view the installation instructions in the [.NET Core installation guide](https://aka.ms/dotnetcoregs).</span></span>
- <span data-ttu-id="b2737-111">Скрипты оболочки применяются в первую очередь для настройки серверов сборки или установки средств без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="b2737-111">Shell scripts are primarily used for setting up build servers or when you wish to install the tools without administrative privileges.</span></span> <span data-ttu-id="b2737-112">Скрипты установки не устанавливают на компьютере необходимые компоненты, поэтому их следует установить вручную.</span><span class="sxs-lookup"><span data-stu-id="b2737-112">Install scripts don't install prerequisites on the machine, which must be installed manually.</span></span> <span data-ttu-id="b2737-113">Дополнительные сведения см. в [справочном разделе по скриптам установки](dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="b2737-113">For more information, see the [install script reference topic](dotnet-install-script.md).</span></span> <span data-ttu-id="b2737-114">Сведения о настройке интерфейса командной строки на сервере сборки с непрерывной интеграцией см. в разделе [Использование пакета SDK и средств .NET Core при непрерывной интеграции (CI)](using-ci-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="b2737-114">For information on how to set up CLI on your continuous integration (CI) build server, see [Using .NET Core SDK and tools in Continuous Integration (CI)](using-ci-with-cli.md).</span></span>

<span data-ttu-id="b2737-115">По умолчанию интерфейс выполняет установку параллельно, чтобы на одном компьютере могли сосуществовать разные версии средств CLI.</span><span class="sxs-lookup"><span data-stu-id="b2737-115">By default, the CLI installs in a side-by-side (SxS) manner, so multiple versions of the CLI tools can coexist on a single machine.</span></span> <span data-ttu-id="b2737-116">Сведения о том, как определить, какая из нескольких версий используется на компьютере, см. в разделе [Драйвер](#driver).</span><span class="sxs-lookup"><span data-stu-id="b2737-116">Determining which version is used on a machine where multiple versions are installed is explained in more detail in the [Driver](#driver) section.</span></span>

## <a name="cli-commands"></a><span data-ttu-id="b2737-117">Команды CLI</span><span class="sxs-lookup"><span data-stu-id="b2737-117">CLI commands</span></span>

<span data-ttu-id="b2737-118">По умолчанию устанавливаются следующие команды:</span><span class="sxs-lookup"><span data-stu-id="b2737-118">The following commands are installed by default:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="b2737-119">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="b2737-119">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="b2737-120">**Основные команды**</span><span class="sxs-lookup"><span data-stu-id="b2737-120">**Basic commands**</span></span>

- [<span data-ttu-id="b2737-121">new</span><span class="sxs-lookup"><span data-stu-id="b2737-121">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="b2737-122">restore</span><span class="sxs-lookup"><span data-stu-id="b2737-122">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="b2737-123">build</span><span class="sxs-lookup"><span data-stu-id="b2737-123">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="b2737-124">publish</span><span class="sxs-lookup"><span data-stu-id="b2737-124">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="b2737-125">run</span><span class="sxs-lookup"><span data-stu-id="b2737-125">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="b2737-126">test</span><span class="sxs-lookup"><span data-stu-id="b2737-126">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="b2737-127">vstest</span><span class="sxs-lookup"><span data-stu-id="b2737-127">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="b2737-128">pack</span><span class="sxs-lookup"><span data-stu-id="b2737-128">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="b2737-129">migrate</span><span class="sxs-lookup"><span data-stu-id="b2737-129">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="b2737-130">clean</span><span class="sxs-lookup"><span data-stu-id="b2737-130">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="b2737-131">sln</span><span class="sxs-lookup"><span data-stu-id="b2737-131">sln</span></span>](dotnet-sln.md)
- [<span data-ttu-id="b2737-132">help</span><span class="sxs-lookup"><span data-stu-id="b2737-132">help</span></span>](dotnet-help.md)
- [<span data-ttu-id="b2737-133">store</span><span class="sxs-lookup"><span data-stu-id="b2737-133">store</span></span>](dotnet-store.md)

<span data-ttu-id="b2737-134">**Команды для изменения проекта**</span><span class="sxs-lookup"><span data-stu-id="b2737-134">**Project modification commands**</span></span>

- [<span data-ttu-id="b2737-135">add package</span><span class="sxs-lookup"><span data-stu-id="b2737-135">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="b2737-136">add reference</span><span class="sxs-lookup"><span data-stu-id="b2737-136">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="b2737-137">remove package</span><span class="sxs-lookup"><span data-stu-id="b2737-137">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="b2737-138">remove reference</span><span class="sxs-lookup"><span data-stu-id="b2737-138">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="b2737-139">list reference</span><span class="sxs-lookup"><span data-stu-id="b2737-139">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="b2737-140">**Расширенные команды**</span><span class="sxs-lookup"><span data-stu-id="b2737-140">**Advanced commands**</span></span>

- [<span data-ttu-id="b2737-141">nuget delete</span><span class="sxs-lookup"><span data-stu-id="b2737-141">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="b2737-142">nuget locals</span><span class="sxs-lookup"><span data-stu-id="b2737-142">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="b2737-143">nuget push</span><span class="sxs-lookup"><span data-stu-id="b2737-143">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="b2737-144">msbuild</span><span class="sxs-lookup"><span data-stu-id="b2737-144">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="b2737-145">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="b2737-145">dotnet install script</span></span>](dotnet-install-script.md)

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b2737-146">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b2737-146">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="b2737-147">**Основные команды**</span><span class="sxs-lookup"><span data-stu-id="b2737-147">**Basic commands**</span></span>

- [<span data-ttu-id="b2737-148">new</span><span class="sxs-lookup"><span data-stu-id="b2737-148">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="b2737-149">restore</span><span class="sxs-lookup"><span data-stu-id="b2737-149">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="b2737-150">build</span><span class="sxs-lookup"><span data-stu-id="b2737-150">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="b2737-151">publish</span><span class="sxs-lookup"><span data-stu-id="b2737-151">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="b2737-152">run</span><span class="sxs-lookup"><span data-stu-id="b2737-152">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="b2737-153">test</span><span class="sxs-lookup"><span data-stu-id="b2737-153">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="b2737-154">vstest</span><span class="sxs-lookup"><span data-stu-id="b2737-154">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="b2737-155">pack</span><span class="sxs-lookup"><span data-stu-id="b2737-155">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="b2737-156">migrate</span><span class="sxs-lookup"><span data-stu-id="b2737-156">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="b2737-157">clean</span><span class="sxs-lookup"><span data-stu-id="b2737-157">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="b2737-158">sln</span><span class="sxs-lookup"><span data-stu-id="b2737-158">sln</span></span>](dotnet-sln.md)

<span data-ttu-id="b2737-159">**Команды для изменения проекта**</span><span class="sxs-lookup"><span data-stu-id="b2737-159">**Project modification commands**</span></span>

- [<span data-ttu-id="b2737-160">add package</span><span class="sxs-lookup"><span data-stu-id="b2737-160">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="b2737-161">add reference</span><span class="sxs-lookup"><span data-stu-id="b2737-161">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="b2737-162">remove package</span><span class="sxs-lookup"><span data-stu-id="b2737-162">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="b2737-163">remove reference</span><span class="sxs-lookup"><span data-stu-id="b2737-163">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="b2737-164">list reference</span><span class="sxs-lookup"><span data-stu-id="b2737-164">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="b2737-165">**Расширенные команды**</span><span class="sxs-lookup"><span data-stu-id="b2737-165">**Advanced commands**</span></span>

- [<span data-ttu-id="b2737-166">nuget delete</span><span class="sxs-lookup"><span data-stu-id="b2737-166">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="b2737-167">nuget locals</span><span class="sxs-lookup"><span data-stu-id="b2737-167">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="b2737-168">nuget push</span><span class="sxs-lookup"><span data-stu-id="b2737-168">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="b2737-169">msbuild</span><span class="sxs-lookup"><span data-stu-id="b2737-169">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="b2737-170">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="b2737-170">dotnet install script</span></span>](dotnet-install-script.md)

---

<span data-ttu-id="b2737-171">Интерфейс CLI использует модель расширяемости, которая позволяет указывать дополнительные средства для проектов.</span><span class="sxs-lookup"><span data-stu-id="b2737-171">The CLI adopts an extensibility model that allows you to specify additional tools for your projects.</span></span> <span data-ttu-id="b2737-172">Дополнительные сведения см. в разделе [Модель расширяемости CLI .NET Core](extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="b2737-172">For more information, see the [.NET Core CLI extensibility model](extensibility.md) topic.</span></span>

## <a name="command-structure"></a><span data-ttu-id="b2737-173">Структура команд</span><span class="sxs-lookup"><span data-stu-id="b2737-173">Command structure</span></span>

<span data-ttu-id="b2737-174">Структура команд CLI состоит из [драйвера ("dotnet")](#driver), [самой команды](#command) и ее возможных [аргументов](#arguments) и [параметров](#options).</span><span class="sxs-lookup"><span data-stu-id="b2737-174">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="b2737-175">Этот шаблон используется в большинстве операций интерфейса командной строки, таких как создание консольного приложения и его запуск из командной строки, как показывают следующие команды при выполнении из каталога *my_app*:</span><span class="sxs-lookup"><span data-stu-id="b2737-175">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="b2737-176">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="b2737-176">.NET Core 2.x</span></span>](#tab/netcore2x)

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b2737-177">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b2737-177">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet new console
dotnet restore
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

---

### <a name="driver"></a><span data-ttu-id="b2737-178">Драйвер</span><span class="sxs-lookup"><span data-stu-id="b2737-178">Driver</span></span>

<span data-ttu-id="b2737-179">Драйвер называется [dotnet](dotnet.md) и имеет два вида ответственности — выполнение [платформозависимого приложения](../deploying/index.md) или выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="b2737-179">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span> 

<span data-ttu-id="b2737-180">Для запуска платформозависимого приложения укажите его драйвера, например `dotnet /path/to/my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="b2737-180">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="b2737-181">При выполнении команды из папки, где находится библиотека DLL приложения, просто выполните `dotnet my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="b2737-181">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="b2737-182">Если вы хотите использовать конкретную версию среды выполнения .NET Core, используйте параметр `--fx-version <VERSION>` (см. справку по [команде dotnet](dotnet.md)).</span><span class="sxs-lookup"><span data-stu-id="b2737-182">If you want to use a specific version of the .NET Core Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="b2737-183">При указании команды для драйвера `dotnet.exe` запускает процесс выполнения команды CLI.</span><span class="sxs-lookup"><span data-stu-id="b2737-183">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="b2737-184">Пример:</span><span class="sxs-lookup"><span data-stu-id="b2737-184">For example:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="b2737-185">Сначала драйвер определяет нужную версию пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="b2737-185">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="b2737-186">Если файл ["global.json"](global-json.md) отсутствует, используется последняя доступная версия пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="b2737-186">If there is no ['global.json'](global-json.md), the latest version of the SDK available is used.</span></span> <span data-ttu-id="b2737-187">Это может быть предварительная или стабильная версия, в зависимости от того, какая версия является последней на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b2737-187">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="b2737-188">После определения версии пакета SDK он выполняет команду.</span><span class="sxs-lookup"><span data-stu-id="b2737-188">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="b2737-189">Команда</span><span class="sxs-lookup"><span data-stu-id="b2737-189">Command</span></span>

<span data-ttu-id="b2737-190">Команда выполняет действие.</span><span class="sxs-lookup"><span data-stu-id="b2737-190">The command performs an action.</span></span> <span data-ttu-id="b2737-191">Например, `dotnet build` проводит сборку кода.</span><span class="sxs-lookup"><span data-stu-id="b2737-191">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="b2737-192">`dotnet publish` публикует код.</span><span class="sxs-lookup"><span data-stu-id="b2737-192">`dotnet publish` publishes code.</span></span> <span data-ttu-id="b2737-193">Команды реализуются как консольное приложение с использованием соглашения `dotnet {command}`.</span><span class="sxs-lookup"><span data-stu-id="b2737-193">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="b2737-194">Аргументы</span><span class="sxs-lookup"><span data-stu-id="b2737-194">Arguments</span></span>

<span data-ttu-id="b2737-195">Аргументы, указываемые в командной строке, передаются непосредственно в вызываемую команду.</span><span class="sxs-lookup"><span data-stu-id="b2737-195">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="b2737-196">Например, если выполнить `dotnet publish my_app.csproj`, аргумент `my_app.csproj` указывает публикуемый проект и передается в команду `publish`.</span><span class="sxs-lookup"><span data-stu-id="b2737-196">For example when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="b2737-197">Параметры</span><span class="sxs-lookup"><span data-stu-id="b2737-197">Options</span></span>

<span data-ttu-id="b2737-198">Параметры, указываемые в командной строке, передаются непосредственно в вызываемую команду.</span><span class="sxs-lookup"><span data-stu-id="b2737-198">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="b2737-199">Например, при выполнении `dotnet publish --output /build_output` параметр `--output` и его значение передаются в команду `publish`.</span><span class="sxs-lookup"><span data-stu-id="b2737-199">For example when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="migration-from-projectjson"></a><span data-ttu-id="b2737-200">Перенос из проекта project.json</span><span class="sxs-lookup"><span data-stu-id="b2737-200">Migration from project.json</span></span>

<span data-ttu-id="b2737-201">Если вы использовали средства предварительной версии 2 для создания проектов на основе *project.json*, обратитесь к разделу о [dotnet migrate](dotnet-migrate.md) за информацией о переносе проекта в MSBuild/ *.csproj*, чтобы его можно было использовать со средствами версии выпуска.</span><span class="sxs-lookup"><span data-stu-id="b2737-201">If you used Preview 2 tooling to produce *project.json*-based projects, consult the [dotnet migrate](dotnet-migrate.md) topic for information on migrating your project to MSBuild/*.csproj* for use with release tooling.</span></span> <span data-ttu-id="b2737-202">Для проектов .NET Core, созданных до выхода средств предварительной версии 2, обновите проект вручную, выполнив указания из раздела [Переход с DNX на интерфейс CLI .NET Core (project.json)](../migration/from-dnx.md) и воспользовавшись `dotnet migrate`, либо обновите свои проекты напрямую.</span><span class="sxs-lookup"><span data-stu-id="b2737-202">For .NET Core projects created prior to the release of Preview 2 tooling, either manually update the project following the guidance in [Migrating from DNX to .NET Core CLI (project.json)](../migration/from-dnx.md) and then use `dotnet migrate` or directly upgrade your projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2737-203">См. также</span><span class="sxs-lookup"><span data-stu-id="b2737-203">See also</span></span>

- [<span data-ttu-id="b2737-204">Репозиторий dotnet/CLI на сайте GitHub</span><span class="sxs-lookup"><span data-stu-id="b2737-204">dotnet/CLI GitHub Repository</span></span>](https://github.com/dotnet/cli/)
- [<span data-ttu-id="b2737-205">Руководство по установке .NET Core</span><span class="sxs-lookup"><span data-stu-id="b2737-205">.NET Core installation guide</span></span>](https://aka.ms/dotnetcoregs)
