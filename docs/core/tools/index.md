---
title: Интерфейс командной строки .NET Core
titleSuffix: ''
description: Общие сведения о .NET Core CLI и его функциях.
ms.date: 02/13/2020
ms.openlocfilehash: 45a40063f70a621e807abf5e01ceecb125aecd7c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "79397602"
---
# <a name="net-core-cli-overview"></a><span data-ttu-id="1e299-103">Обзор .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="1e299-103">.NET Core CLI overview</span></span>

<span data-ttu-id="1e299-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="1e299-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="1e299-105">Интерфейс командной строки (CLI) .NET Core — это новая базовая кроссплатформенная цепочка инструментов для разработки, компиляции, запуска и публикации приложений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1e299-105">The .NET Core command-line interface (CLI) is a cross-platform toolchain for developing, building, running, and publishing .NET Core applications.</span></span>

<span data-ttu-id="1e299-106">.NET Core CLI входит в [пакет SDK для .NET Core](../sdk.md).</span><span class="sxs-lookup"><span data-stu-id="1e299-106">The .NET Core CLI is included with the [.NET Core SDK](../sdk.md).</span></span> <span data-ttu-id="1e299-107">Дополнительные сведения об установке пакета SDK для .NET Core см. [здесь](../install/sdk.md).</span><span class="sxs-lookup"><span data-stu-id="1e299-107">To learn how to install the .NET Core SDK, see [Install the .NET Core SDK](../install/sdk.md).</span></span>

## <a name="cli-commands"></a><span data-ttu-id="1e299-108">Команды CLI</span><span class="sxs-lookup"><span data-stu-id="1e299-108">CLI commands</span></span>

<span data-ttu-id="1e299-109">По умолчанию устанавливаются следующие команды:</span><span class="sxs-lookup"><span data-stu-id="1e299-109">The following commands are installed by default:</span></span>

### <a name="basic-commands"></a><span data-ttu-id="1e299-110">Основные команды</span><span class="sxs-lookup"><span data-stu-id="1e299-110">Basic commands</span></span>

- [`new`](dotnet-new.md)
- [`restore`](dotnet-restore.md)
- [`build`](dotnet-build.md)
- [`publish`](dotnet-publish.md)
- [`run`](dotnet-run.md)
- [`test`](dotnet-test.md)
- [`vstest`](dotnet-vstest.md)
- [`pack`](dotnet-pack.md)
- [`migrate`](dotnet-migrate.md)
- [`clean`](dotnet-clean.md)
- [`sln`](dotnet-sln.md)
- [`help`](dotnet-help.md)
- [`store`](dotnet-store.md)

### <a name="project-modification-commands"></a><span data-ttu-id="1e299-111">Команды для изменения проекта</span><span class="sxs-lookup"><span data-stu-id="1e299-111">Project modification commands</span></span>

- [`add package`](dotnet-add-package.md)
- [`add reference`](dotnet-add-reference.md)
- [`remove package`](dotnet-remove-package.md)
- [`remove reference`](dotnet-remove-reference.md)
- [`list reference`](dotnet-list-reference.md)

### <a name="advanced-commands"></a><span data-ttu-id="1e299-112">Расширенные команды</span><span class="sxs-lookup"><span data-stu-id="1e299-112">Advanced commands</span></span>

- [`nuget delete`](dotnet-nuget-delete.md)
- [`nuget locals`](dotnet-nuget-locals.md)
- [`nuget push`](dotnet-nuget-push.md)
- [`msbuild`](dotnet-msbuild.md)
- [`dotnet install script`](dotnet-install-script.md)

### <a name="tool-management-commands"></a><span data-ttu-id="1e299-113">Команды управления средством</span><span class="sxs-lookup"><span data-stu-id="1e299-113">Tool management commands</span></span>

- [`tool install`](dotnet-tool-install.md)
- [`tool list`](dotnet-tool-list.md)
- [`tool update`](dotnet-tool-update.md)
- <span data-ttu-id="1e299-114">[`tool restore`](global-tools.md#install-a-local-tool) (доступна, начиная с пакета SDK для .NET Core 3.0)</span><span class="sxs-lookup"><span data-stu-id="1e299-114">[`tool restore`](global-tools.md#install-a-local-tool) Available since .NET Core SDK 3.0.</span></span>
- <span data-ttu-id="1e299-115">[`tool run`](global-tools.md#invoke-a-local-tool) (доступна, начиная с пакета SDK для .NET Core 3.0)</span><span class="sxs-lookup"><span data-stu-id="1e299-115">[`tool run`](global-tools.md#invoke-a-local-tool) Available since .NET Core SDK 3.0.</span></span>
- [`tool uninstall`](dotnet-tool-uninstall.md)

<span data-ttu-id="1e299-116">Средства — это консольные приложения, которые устанавливаются из пакетов NuGet и вызываются из командной строки.</span><span class="sxs-lookup"><span data-stu-id="1e299-116">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="1e299-117">Вы можете писать средства самостоятельно или устанавливать средства, написанные другими.</span><span class="sxs-lookup"><span data-stu-id="1e299-117">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="1e299-118">Средства также называются глобальными средствами, средствами пути к средству и локальными средствами.</span><span class="sxs-lookup"><span data-stu-id="1e299-118">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="1e299-119">Дополнительные сведения см. в [обзоре средств .NET Core](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1e299-119">For more information, see [.NET Core tools overview](global-tools.md).</span></span>

## <a name="command-structure"></a><span data-ttu-id="1e299-120">Структура команд</span><span class="sxs-lookup"><span data-stu-id="1e299-120">Command structure</span></span>

<span data-ttu-id="1e299-121">Структура команд CLI состоит из [драйвера ("dotnet")](#driver), [самой команды](#command) и ее возможных [аргументов](#arguments) и [параметров](#options).</span><span class="sxs-lookup"><span data-stu-id="1e299-121">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="1e299-122">Этот шаблон используется в большинстве операций интерфейса командной строки, таких как создание консольного приложения и его запуск из командной строки, как показывают следующие команды при выполнении из каталога *my_app*:</span><span class="sxs-lookup"><span data-stu-id="1e299-122">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

### <a name="driver"></a><span data-ttu-id="1e299-123">Драйвер</span><span class="sxs-lookup"><span data-stu-id="1e299-123">Driver</span></span>

<span data-ttu-id="1e299-124">Драйвер называется [dotnet](dotnet.md) и имеет два вида ответственности — выполнение [платформозависимого приложения](../deploying/index.md) или выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="1e299-124">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span>

<span data-ttu-id="1e299-125">Для запуска платформозависимого приложения укажите его драйвера, например `dotnet /path/to/my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="1e299-125">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="1e299-126">При выполнении команды из папки, где находится библиотека DLL приложения, просто выполните `dotnet my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="1e299-126">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="1e299-127">Если вы хотите использовать конкретную версию среды выполнения .NET Core, используйте параметр `--fx-version <VERSION>` (см. справку по [команде dotnet](dotnet.md)).</span><span class="sxs-lookup"><span data-stu-id="1e299-127">If you want to use a specific version of the .NET Core Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="1e299-128">При указании команды для драйвера `dotnet.exe` запускает процесс выполнения команды CLI.</span><span class="sxs-lookup"><span data-stu-id="1e299-128">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="1e299-129">Пример:</span><span class="sxs-lookup"><span data-stu-id="1e299-129">For example:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="1e299-130">Сначала драйвер определяет нужную версию пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="1e299-130">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="1e299-131">Если файл [global.json](global-json.md) отсутствует, используется последняя доступная версия пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="1e299-131">If there is no [global.json](global-json.md) file, the latest version of the SDK available is used.</span></span> <span data-ttu-id="1e299-132">Это может быть предварительная или стабильная версия, в зависимости от того, какая версия является последней на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1e299-132">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="1e299-133">После определения версии пакета SDK он выполняет команду.</span><span class="sxs-lookup"><span data-stu-id="1e299-133">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="1e299-134">Команда</span><span class="sxs-lookup"><span data-stu-id="1e299-134">Command</span></span>

<span data-ttu-id="1e299-135">Команда выполняет действие.</span><span class="sxs-lookup"><span data-stu-id="1e299-135">The command performs an action.</span></span> <span data-ttu-id="1e299-136">Например, `dotnet build` проводит сборку кода.</span><span class="sxs-lookup"><span data-stu-id="1e299-136">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="1e299-137">`dotnet publish` публикует код.</span><span class="sxs-lookup"><span data-stu-id="1e299-137">`dotnet publish` publishes code.</span></span> <span data-ttu-id="1e299-138">Команды реализуются как консольное приложение с использованием соглашения `dotnet {command}`.</span><span class="sxs-lookup"><span data-stu-id="1e299-138">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="1e299-139">Аргументы</span><span class="sxs-lookup"><span data-stu-id="1e299-139">Arguments</span></span>

<span data-ttu-id="1e299-140">Аргументы, указываемые в командной строке, передаются непосредственно в вызываемую команду.</span><span class="sxs-lookup"><span data-stu-id="1e299-140">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="1e299-141">Например, если выполнить `dotnet publish my_app.csproj`, аргумент `my_app.csproj` указывает публикуемый проект и передается в команду `publish`.</span><span class="sxs-lookup"><span data-stu-id="1e299-141">For example when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="1e299-142">Параметры</span><span class="sxs-lookup"><span data-stu-id="1e299-142">Options</span></span>

<span data-ttu-id="1e299-143">Параметры, указываемые в командной строке, передаются непосредственно в вызываемую команду.</span><span class="sxs-lookup"><span data-stu-id="1e299-143">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="1e299-144">Например, при выполнении `dotnet publish --output /build_output` параметр `--output` и его значение передаются в команду `publish`.</span><span class="sxs-lookup"><span data-stu-id="1e299-144">For example when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e299-145">См. также</span><span class="sxs-lookup"><span data-stu-id="1e299-145">See also</span></span>

- [<span data-ttu-id="1e299-146">Репозиторий GitHub dotnet/sdk</span><span class="sxs-lookup"><span data-stu-id="1e299-146">dotnet/sdk GitHub repository</span></span>](https://github.com/dotnet/sdk/)
- [<span data-ttu-id="1e299-147">Руководство по установке .NET Core</span><span class="sxs-lookup"><span data-stu-id="1e299-147">.NET Core installation guide</span></span>](../install/sdk.md)
