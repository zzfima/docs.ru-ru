---
title: Интерфейс командной строки .NET Core
titleSuffix: ''
description: Общие сведения о .NET Core CLI и его функциях.
ms.date: 02/13/2020
ms.openlocfilehash: 1078d68ddc088274fa14b0094a81765f7af69dad
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543318"
---
# <a name="net-core-cli-overview"></a><span data-ttu-id="5b971-103">Обзор .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="5b971-103">.NET Core CLI overview</span></span>

<span data-ttu-id="5b971-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="5b971-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="5b971-105">Интерфейс командной строки (CLI) .NET Core — это новая базовая кроссплатформенная цепочка инструментов для разработки, компиляции, запуска и публикации приложений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5b971-105">The .NET Core command-line interface (CLI) is a cross-platform toolchain for developing, building, running, and publishing .NET Core applications.</span></span>

<span data-ttu-id="5b971-106">.NET Core CLI входит в [пакет SDK для .NET Core](../sdk.md).</span><span class="sxs-lookup"><span data-stu-id="5b971-106">The .NET Core CLI is included with the [.NET Core SDK](../sdk.md).</span></span> <span data-ttu-id="5b971-107">Дополнительные сведения об установке пакета SDK для .NET Core см. [здесь](../install/sdk.md).</span><span class="sxs-lookup"><span data-stu-id="5b971-107">To learn how to install the .NET Core SDK, see [Install the .NET Core SDK](../install/sdk.md).</span></span>

## <a name="cli-commands"></a><span data-ttu-id="5b971-108">Команды CLI</span><span class="sxs-lookup"><span data-stu-id="5b971-108">CLI commands</span></span>

<span data-ttu-id="5b971-109">По умолчанию устанавливаются следующие команды:</span><span class="sxs-lookup"><span data-stu-id="5b971-109">The following commands are installed by default:</span></span>

### <a name="basic-commands"></a><span data-ttu-id="5b971-110">Основные команды</span><span class="sxs-lookup"><span data-stu-id="5b971-110">Basic commands</span></span>

- [<span data-ttu-id="5b971-111">new</span><span class="sxs-lookup"><span data-stu-id="5b971-111">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="5b971-112">restore</span><span class="sxs-lookup"><span data-stu-id="5b971-112">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="5b971-113">build</span><span class="sxs-lookup"><span data-stu-id="5b971-113">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="5b971-114">publish</span><span class="sxs-lookup"><span data-stu-id="5b971-114">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="5b971-115">run</span><span class="sxs-lookup"><span data-stu-id="5b971-115">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="5b971-116">test</span><span class="sxs-lookup"><span data-stu-id="5b971-116">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="5b971-117">vstest</span><span class="sxs-lookup"><span data-stu-id="5b971-117">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="5b971-118">pack</span><span class="sxs-lookup"><span data-stu-id="5b971-118">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="5b971-119">migrate</span><span class="sxs-lookup"><span data-stu-id="5b971-119">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="5b971-120">clean</span><span class="sxs-lookup"><span data-stu-id="5b971-120">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="5b971-121">sln</span><span class="sxs-lookup"><span data-stu-id="5b971-121">sln</span></span>](dotnet-sln.md)
- [<span data-ttu-id="5b971-122">help</span><span class="sxs-lookup"><span data-stu-id="5b971-122">help</span></span>](dotnet-help.md)
- [<span data-ttu-id="5b971-123">store</span><span class="sxs-lookup"><span data-stu-id="5b971-123">store</span></span>](dotnet-store.md)

### <a name="project-modification-commands"></a><span data-ttu-id="5b971-124">Команды для изменения проекта</span><span class="sxs-lookup"><span data-stu-id="5b971-124">Project modification commands</span></span>

- [<span data-ttu-id="5b971-125">add package</span><span class="sxs-lookup"><span data-stu-id="5b971-125">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="5b971-126">add reference</span><span class="sxs-lookup"><span data-stu-id="5b971-126">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="5b971-127">remove package</span><span class="sxs-lookup"><span data-stu-id="5b971-127">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="5b971-128">remove reference</span><span class="sxs-lookup"><span data-stu-id="5b971-128">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="5b971-129">list reference</span><span class="sxs-lookup"><span data-stu-id="5b971-129">list reference</span></span>](dotnet-list-reference.md)

### <a name="advanced-commands"></a><span data-ttu-id="5b971-130">Расширенные команды</span><span class="sxs-lookup"><span data-stu-id="5b971-130">Advanced commands</span></span>

- [<span data-ttu-id="5b971-131">nuget delete</span><span class="sxs-lookup"><span data-stu-id="5b971-131">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="5b971-132">nuget locals</span><span class="sxs-lookup"><span data-stu-id="5b971-132">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="5b971-133">nuget push</span><span class="sxs-lookup"><span data-stu-id="5b971-133">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="5b971-134">msbuild</span><span class="sxs-lookup"><span data-stu-id="5b971-134">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="5b971-135">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="5b971-135">dotnet install script</span></span>](dotnet-install-script.md)

### <a name="tool-management-commands"></a><span data-ttu-id="5b971-136">Команды управления средством</span><span class="sxs-lookup"><span data-stu-id="5b971-136">Tool management commands</span></span>

- [<span data-ttu-id="5b971-137">tool install</span><span class="sxs-lookup"><span data-stu-id="5b971-137">tool install</span></span>](dotnet-tool-install.md)
- [<span data-ttu-id="5b971-138">tool list</span><span class="sxs-lookup"><span data-stu-id="5b971-138">tool list</span></span>](dotnet-tool-list.md)
- [<span data-ttu-id="5b971-139">tool update</span><span class="sxs-lookup"><span data-stu-id="5b971-139">tool update</span></span>](dotnet-tool-update.md)
- <span data-ttu-id="5b971-140">[tool restore](global-tools.md#install-a-local-tool) **Доступно начиная с пакета SDK для .NET Core 3.0**</span><span class="sxs-lookup"><span data-stu-id="5b971-140">[tool restore](global-tools.md#install-a-local-tool) **Available starting with .NET Core SDK 3.0**</span></span>
- <span data-ttu-id="5b971-141">[tool run](global-tools.md#invoke-a-local-tool) **Доступно начиная с пакета SDK для .NET Core 3.0**</span><span class="sxs-lookup"><span data-stu-id="5b971-141">[tool run](global-tools.md#invoke-a-local-tool) **Available starting with .NET Core SDK 3.0**</span></span>
- [<span data-ttu-id="5b971-142">tool uninstall</span><span class="sxs-lookup"><span data-stu-id="5b971-142">tool uninstall</span></span>](dotnet-tool-uninstall.md)

<span data-ttu-id="5b971-143">Средства — это консольные приложения, которые устанавливаются из пакетов NuGet и вызываются из командной строки.</span><span class="sxs-lookup"><span data-stu-id="5b971-143">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="5b971-144">Вы можете писать средства самостоятельно или устанавливать средства, написанные другими.</span><span class="sxs-lookup"><span data-stu-id="5b971-144">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="5b971-145">Средства также называются глобальными средствами, средствами пути к средству и локальными средствами.</span><span class="sxs-lookup"><span data-stu-id="5b971-145">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="5b971-146">Дополнительные сведения см. в [обзоре средств .NET Core](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5b971-146">For more information, see [.NET Core tools overview](global-tools.md).</span></span>

## <a name="command-structure"></a><span data-ttu-id="5b971-147">Структура команд</span><span class="sxs-lookup"><span data-stu-id="5b971-147">Command structure</span></span>

<span data-ttu-id="5b971-148">Структура команд CLI состоит из [драйвера ("dotnet")](#driver), [самой команды](#command) и ее возможных [аргументов](#arguments) и [параметров](#options).</span><span class="sxs-lookup"><span data-stu-id="5b971-148">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="5b971-149">Этот шаблон используется в большинстве операций интерфейса командной строки, таких как создание консольного приложения и его запуск из командной строки, как показывают следующие команды при выполнении из каталога *my_app*:</span><span class="sxs-lookup"><span data-stu-id="5b971-149">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

### <a name="driver"></a><span data-ttu-id="5b971-150">Драйвер</span><span class="sxs-lookup"><span data-stu-id="5b971-150">Driver</span></span>

<span data-ttu-id="5b971-151">Драйвер называется [dotnet](dotnet.md) и имеет два вида ответственности — выполнение [платформозависимого приложения](../deploying/index.md) или выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="5b971-151">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span> 

<span data-ttu-id="5b971-152">Для запуска платформозависимого приложения укажите его драйвера, например `dotnet /path/to/my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="5b971-152">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="5b971-153">При выполнении команды из папки, где находится библиотека DLL приложения, просто выполните `dotnet my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="5b971-153">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="5b971-154">Если вы хотите использовать конкретную версию среды выполнения .NET Core, используйте параметр `--fx-version <VERSION>` (см. справку по [команде dotnet](dotnet.md)).</span><span class="sxs-lookup"><span data-stu-id="5b971-154">If you want to use a specific version of the .NET Core Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="5b971-155">При указании команды для драйвера `dotnet.exe` запускает процесс выполнения команды CLI.</span><span class="sxs-lookup"><span data-stu-id="5b971-155">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="5b971-156">Пример:</span><span class="sxs-lookup"><span data-stu-id="5b971-156">For example:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="5b971-157">Сначала драйвер определяет нужную версию пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="5b971-157">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="5b971-158">Если файл ["global.json"](global-json.md) отсутствует, используется последняя доступная версия пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="5b971-158">If there is no ['global.json'](global-json.md), the latest version of the SDK available is used.</span></span> <span data-ttu-id="5b971-159">Это может быть предварительная или стабильная версия, в зависимости от того, какая версия является последней на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5b971-159">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="5b971-160">После определения версии пакета SDK он выполняет команду.</span><span class="sxs-lookup"><span data-stu-id="5b971-160">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="5b971-161">Команда</span><span class="sxs-lookup"><span data-stu-id="5b971-161">Command</span></span>

<span data-ttu-id="5b971-162">Команда выполняет действие.</span><span class="sxs-lookup"><span data-stu-id="5b971-162">The command performs an action.</span></span> <span data-ttu-id="5b971-163">Например, `dotnet build` проводит сборку кода.</span><span class="sxs-lookup"><span data-stu-id="5b971-163">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="5b971-164">`dotnet publish` публикует код.</span><span class="sxs-lookup"><span data-stu-id="5b971-164">`dotnet publish` publishes code.</span></span> <span data-ttu-id="5b971-165">Команды реализуются как консольное приложение с использованием соглашения `dotnet {command}`.</span><span class="sxs-lookup"><span data-stu-id="5b971-165">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="5b971-166">Аргументы</span><span class="sxs-lookup"><span data-stu-id="5b971-166">Arguments</span></span>

<span data-ttu-id="5b971-167">Аргументы, указываемые в командной строке, передаются непосредственно в вызываемую команду.</span><span class="sxs-lookup"><span data-stu-id="5b971-167">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="5b971-168">Например, если выполнить `dotnet publish my_app.csproj`, аргумент `my_app.csproj` указывает публикуемый проект и передается в команду `publish`.</span><span class="sxs-lookup"><span data-stu-id="5b971-168">For example when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="5b971-169">Параметры</span><span class="sxs-lookup"><span data-stu-id="5b971-169">Options</span></span>

<span data-ttu-id="5b971-170">Параметры, указываемые в командной строке, передаются непосредственно в вызываемую команду.</span><span class="sxs-lookup"><span data-stu-id="5b971-170">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="5b971-171">Например, при выполнении `dotnet publish --output /build_output` параметр `--output` и его значение передаются в команду `publish`.</span><span class="sxs-lookup"><span data-stu-id="5b971-171">For example when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b971-172">См. также</span><span class="sxs-lookup"><span data-stu-id="5b971-172">See also</span></span>

- [<span data-ttu-id="5b971-173">Репозиторий GitHub dotnet/sdk</span><span class="sxs-lookup"><span data-stu-id="5b971-173">dotnet/sdk GitHub repository</span></span>](https://github.com/dotnet/sdk/)
- [<span data-ttu-id="5b971-174">Руководство по установке .NET Core</span><span class="sxs-lookup"><span data-stu-id="5b971-174">.NET Core installation guide</span></span>](../install/sdk.md)
