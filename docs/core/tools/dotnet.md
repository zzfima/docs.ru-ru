---
title: Команда dotnet
description: Сведения о команде dotnet (универсальном драйвере для средств CLI .NET Core) и ее использовании.
ms.date: 06/04/2018
ms.openlocfilehash: fe90968560b58471c279fcd2097741ea476cef0b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734063"
---
# <a name="dotnet-command"></a><span data-ttu-id="4f05f-103">Команда dotnet</span><span class="sxs-lookup"><span data-stu-id="4f05f-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="4f05f-104">name</span><span class="sxs-lookup"><span data-stu-id="4f05f-104">Name</span></span>

<span data-ttu-id="4f05f-105">`dotnet` — средство для управления исходным кодом .NET и двоичными объектами.</span><span class="sxs-lookup"><span data-stu-id="4f05f-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4f05f-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4f05f-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="4f05f-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="4f05f-107">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="4f05f-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="4f05f-108">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx]
    [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4f05f-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4f05f-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet [command] [arguments] [--additionalprobingpath] [--depsfile] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--runtimeconfig] [-v|--verbosity] [--version]
```

---

## <a name="description"></a><span data-ttu-id="4f05f-110">Описание</span><span class="sxs-lookup"><span data-stu-id="4f05f-110">Description</span></span>

<span data-ttu-id="4f05f-111">`dotnet` — это средство для управления исходным кодом .NET и двоичными объектами.</span><span class="sxs-lookup"><span data-stu-id="4f05f-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="4f05f-112">Он предоставляет команды, выполняющие определенные задачи, такие как [`dotnet build`](dotnet-build.md) и [`dotnet run`](dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="4f05f-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="4f05f-113">Каждая команда определяет свои аргументы.</span><span class="sxs-lookup"><span data-stu-id="4f05f-113">Each command defines its own arguments.</span></span> <span data-ttu-id="4f05f-114">Введите `--help` после каждой команды для доступа к краткой справочной документации.</span><span class="sxs-lookup"><span data-stu-id="4f05f-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="4f05f-115">`dotnet` можно использовать для запуска приложений путем указания библиотеки DLL приложения, например `dotnet myapp.dll`.</span><span class="sxs-lookup"><span data-stu-id="4f05f-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="4f05f-116">Дополнительные сведения о параметрах развертывания см. в разделе [Развертывание приложений .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="4f05f-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="4f05f-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="4f05f-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="4f05f-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="4f05f-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="4f05f-119">Путь к дополнительному файлу *.deps.json*.</span><span class="sxs-lookup"><span data-stu-id="4f05f-119">Path to an additional *.deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="4f05f-120">Путь, содержащий политику проверки и проверяемые сборки.</span><span class="sxs-lookup"><span data-stu-id="4f05f-120">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="4f05f-121">Путь к файлу *deps.json*.</span><span class="sxs-lookup"><span data-stu-id="4f05f-121">Path to a *deps.json* file.</span></span>

<span data-ttu-id="4f05f-122">Файл *deps.json* содержит список зависимостей, зависимости компиляции и сведения о версии, используемые для устранения конфликтов сборок.</span><span class="sxs-lookup"><span data-stu-id="4f05f-122">A *deps.json* file contains a list of dependencies, compilation dependencies, and version information used to address assembly conflicts.</span></span> <span data-ttu-id="4f05f-123">Дополнительные сведения об этом файле см. в разделе [Файлы конфигурации среды выполнения](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) на GitHub.</span><span class="sxs-lookup"><span data-stu-id="4f05f-123">For more information about this file, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

`-d|--diagnostics`

<span data-ttu-id="4f05f-124">Включает вывод диагностических данных.</span><span class="sxs-lookup"><span data-stu-id="4f05f-124">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="4f05f-125">Версия среды выполнения .NET Core, используемой для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="4f05f-125">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="4f05f-126">Выводит на экран документацию для определенной команды, например `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="4f05f-126">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="4f05f-127">`dotnet --help` выводит список доступных команд.</span><span class="sxs-lookup"><span data-stu-id="4f05f-127">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="4f05f-128">Выводит подробные сведения об установке .NET Core и среде компьютера, например текущую операционную систему и фиксацию SHA версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4f05f-128">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="4f05f-129">Отображает установленные среды выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4f05f-129">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="4f05f-130">Отображает установленные пакеты SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4f05f-130">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx <N>`

<span data-ttu-id="4f05f-131">Определяет поведение, когда требуемая общая платформа недоступна.</span><span class="sxs-lookup"><span data-stu-id="4f05f-131">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="4f05f-132">Параметр `N` может принимать следующие значения:</span><span class="sxs-lookup"><span data-stu-id="4f05f-132">`N` can be:</span></span>

- <span data-ttu-id="4f05f-133">`0` — отключает увеличение дополнительных версий.</span><span class="sxs-lookup"><span data-stu-id="4f05f-133">`0` - Disable even minor version roll forward.</span></span>
- <span data-ttu-id="4f05f-134">`1` — позволяет увеличивать дополнительный номер версии, но не основной.</span><span class="sxs-lookup"><span data-stu-id="4f05f-134">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="4f05f-135">Это поведение установлено по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4f05f-135">This is the default behavior.</span></span>
- <span data-ttu-id="4f05f-136">`2` — включает увеличение основных и дополнительных версий.</span><span class="sxs-lookup"><span data-stu-id="4f05f-136">`2` - Roll forward on minor and major versions.</span></span>

 <span data-ttu-id="4f05f-137">Дополнительные сведения о накате можно найти в [этой статье](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="4f05f-137">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`--runtimeconfig`

<span data-ttu-id="4f05f-138">Путь к файлу *runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="4f05f-138">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="4f05f-139">Файл *runtimeconfig.json* представляет собой файл конфигурации, содержащий параметры среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4f05f-139">A *runtimeconfig.json* file is a configuration file containing run-time settings.</span></span> <span data-ttu-id="4f05f-140">Дополнительные сведения см. в статье [Параметры конфигурации среды выполнения .NET Core](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="4f05f-140">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="4f05f-141">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="4f05f-141">Sets the verbosity level of the command.</span></span> <span data-ttu-id="4f05f-142">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="4f05f-142">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="4f05f-143">Поддерживается не во всех командах. Дополнительную информацию см. на странице определенной команды.</span><span class="sxs-lookup"><span data-stu-id="4f05f-143">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="4f05f-144">Выводит версию используемого пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4f05f-144">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="4f05f-145">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="4f05f-145">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="4f05f-146">Путь к дополнительному файлу *.deps.json*.</span><span class="sxs-lookup"><span data-stu-id="4f05f-146">Path to an additional *.deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="4f05f-147">Путь, содержащий политику проверки и проверяемые сборки.</span><span class="sxs-lookup"><span data-stu-id="4f05f-147">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="4f05f-148">Путь к файлу *deps.json*.</span><span class="sxs-lookup"><span data-stu-id="4f05f-148">Path to a *deps.json* file.</span></span>

<span data-ttu-id="4f05f-149">Файл *deps.json* содержит список зависимостей, зависимости компиляции и сведения о версии, используемые для устранения конфликтов сборок.</span><span class="sxs-lookup"><span data-stu-id="4f05f-149">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="4f05f-150">Дополнительные сведения об этом файле см. в разделе [Файлы конфигурации среды выполнения](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) на GitHub.</span><span class="sxs-lookup"><span data-stu-id="4f05f-150">For more details on this file, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-d|--diagnostics`

<span data-ttu-id="4f05f-151">Включает вывод диагностических данных.</span><span class="sxs-lookup"><span data-stu-id="4f05f-151">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="4f05f-152">Версия среды выполнения .NET Core, используемой для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="4f05f-152">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="4f05f-153">Выводит на экран документацию для определенной команды, например `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="4f05f-153">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="4f05f-154">`dotnet --help` выводит список доступных команд.</span><span class="sxs-lookup"><span data-stu-id="4f05f-154">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="4f05f-155">Выводит подробные сведения об установке .NET Core и среде компьютера, например текущую операционную систему и фиксацию SHA версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4f05f-155">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="4f05f-156">Отключает накат дополнительных версий, если установлено `0`.</span><span class="sxs-lookup"><span data-stu-id="4f05f-156">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="4f05f-157">Дополнительные сведения о накате можно найти в [этой статье](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="4f05f-157">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`--runtimeconfig`

<span data-ttu-id="4f05f-158">Путь к файлу *runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="4f05f-158">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="4f05f-159">Файл *runtimeconfig.json* представляет собой файл конфигурации, содержащий параметры среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4f05f-159">A *runtimeconfig.json* file is a configuration file containing run-time settings.</span></span> <span data-ttu-id="4f05f-160">Дополнительные сведения см. в статье [Параметры конфигурации среды выполнения .NET Core](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="4f05f-160">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="4f05f-161">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="4f05f-161">Sets the verbosity level of the command.</span></span> <span data-ttu-id="4f05f-162">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="4f05f-162">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="4f05f-163">Поддерживается не во всех командах. Дополнительную информацию см. на странице определенной команды.</span><span class="sxs-lookup"><span data-stu-id="4f05f-163">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="4f05f-164">Выводит версию используемого пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4f05f-164">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4f05f-165">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4f05f-165">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="4f05f-166">Путь, содержащий политику проверки и проверяемые сборки.</span><span class="sxs-lookup"><span data-stu-id="4f05f-166">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="4f05f-167">Путь к файлу *deps.json*.</span><span class="sxs-lookup"><span data-stu-id="4f05f-167">Path to a *deps.json* file.</span></span>

<span data-ttu-id="4f05f-168">Файл *deps.json* содержит список зависимостей, зависимости компиляции и сведения о версии, используемые для устранения конфликтов сборок.</span><span class="sxs-lookup"><span data-stu-id="4f05f-168">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="4f05f-169">Дополнительные сведения об этом файле см. в разделе [Файлы конфигурации среды выполнения](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) на GitHub.</span><span class="sxs-lookup"><span data-stu-id="4f05f-169">For more details on this file, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-d|--diagnostics`

<span data-ttu-id="4f05f-170">Включает вывод диагностических данных.</span><span class="sxs-lookup"><span data-stu-id="4f05f-170">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="4f05f-171">Версия среды выполнения .NET Core, используемой для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="4f05f-171">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="4f05f-172">Выводит на экран документацию для определенной команды, например `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="4f05f-172">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="4f05f-173">`dotnet --help` выводит список доступных команд.</span><span class="sxs-lookup"><span data-stu-id="4f05f-173">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="4f05f-174">Выводит подробные сведения об установке .NET Core и среде компьютера, например текущую операционную систему и фиксацию SHA версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4f05f-174">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--runtimeconfig`

<span data-ttu-id="4f05f-175">Путь к файлу *runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="4f05f-175">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="4f05f-176">Файл *runtimeconfig.json* представляет собой файл конфигурации, содержащий параметры среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4f05f-176">A *runtimeconfig.json* file is a configuration file containing run-time settings.</span></span> <span data-ttu-id="4f05f-177">Дополнительные сведения см. в статье [Параметры конфигурации среды выполнения .NET Core](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="4f05f-177">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="4f05f-178">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="4f05f-178">Sets the verbosity level of the command.</span></span> <span data-ttu-id="4f05f-179">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="4f05f-179">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="4f05f-180">Поддерживается не во всех командах. Дополнительную информацию см. на странице определенной команды.</span><span class="sxs-lookup"><span data-stu-id="4f05f-180">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="4f05f-181">Выводит версию используемого пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4f05f-181">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="4f05f-182">Команды dotnet</span><span class="sxs-lookup"><span data-stu-id="4f05f-182">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="4f05f-183">Общее</span><span class="sxs-lookup"><span data-stu-id="4f05f-183">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="4f05f-184">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="4f05f-184">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="4f05f-185">Команда</span><span class="sxs-lookup"><span data-stu-id="4f05f-185">Command</span></span>                                       | <span data-ttu-id="4f05f-186">Функция</span><span class="sxs-lookup"><span data-stu-id="4f05f-186">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="4f05f-187">dotnet build</span><span class="sxs-lookup"><span data-stu-id="4f05f-187">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="4f05f-188">Выполняет сборку приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4f05f-188">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="4f05f-189">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="4f05f-189">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="4f05f-190">Взаимодействует с серверами, запущенными сборкой.</span><span class="sxs-lookup"><span data-stu-id="4f05f-190">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="4f05f-191">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="4f05f-191">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="4f05f-192">Очищает выходные данные сборки.</span><span class="sxs-lookup"><span data-stu-id="4f05f-192">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="4f05f-193">dotnet help</span><span class="sxs-lookup"><span data-stu-id="4f05f-193">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="4f05f-194">Выводит более подробную документацию из Интернета для команды.</span><span class="sxs-lookup"><span data-stu-id="4f05f-194">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="4f05f-195">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="4f05f-195">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="4f05f-196">Переносит допустимый проект предварительной версии 2 в проект пакета SDK .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="4f05f-196">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="4f05f-197">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="4f05f-197">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="4f05f-198">Обеспечивает доступ к командной строке MSBuild.</span><span class="sxs-lookup"><span data-stu-id="4f05f-198">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="4f05f-199">dotnet new</span><span class="sxs-lookup"><span data-stu-id="4f05f-199">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="4f05f-200">Инициализирует проект C# или F# для заданного шаблона.</span><span class="sxs-lookup"><span data-stu-id="4f05f-200">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="4f05f-201">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="4f05f-201">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="4f05f-202">Создает пакет NuGet с кодом.</span><span class="sxs-lookup"><span data-stu-id="4f05f-202">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="4f05f-203">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="4f05f-203">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="4f05f-204">Публикует платформозависимое или автономное приложение .NET.</span><span class="sxs-lookup"><span data-stu-id="4f05f-204">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="4f05f-205">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="4f05f-205">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="4f05f-206">Восстанавливает зависимости для данного приложения.</span><span class="sxs-lookup"><span data-stu-id="4f05f-206">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="4f05f-207">dotnet run</span><span class="sxs-lookup"><span data-stu-id="4f05f-207">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="4f05f-208">Запускает приложение из источника.</span><span class="sxs-lookup"><span data-stu-id="4f05f-208">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="4f05f-209">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="4f05f-209">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="4f05f-210">Параметры для добавления, удаления и перечисления проектов в файле решения.</span><span class="sxs-lookup"><span data-stu-id="4f05f-210">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="4f05f-211">dotnet store</span><span class="sxs-lookup"><span data-stu-id="4f05f-211">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="4f05f-212">Сохраняет сборки в хранилище пакетов среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4f05f-212">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="4f05f-213">dotnet test</span><span class="sxs-lookup"><span data-stu-id="4f05f-213">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="4f05f-214">Выполняет тесты с помощью средства запуска тестов.</span><span class="sxs-lookup"><span data-stu-id="4f05f-214">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="4f05f-215">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="4f05f-215">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="4f05f-216">Команда</span><span class="sxs-lookup"><span data-stu-id="4f05f-216">Command</span></span>                             | <span data-ttu-id="4f05f-217">Функция</span><span class="sxs-lookup"><span data-stu-id="4f05f-217">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="4f05f-218">dotnet build</span><span class="sxs-lookup"><span data-stu-id="4f05f-218">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="4f05f-219">Выполняет сборку приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4f05f-219">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="4f05f-220">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="4f05f-220">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="4f05f-221">Очищает выходные данные сборки.</span><span class="sxs-lookup"><span data-stu-id="4f05f-221">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="4f05f-222">dotnet help</span><span class="sxs-lookup"><span data-stu-id="4f05f-222">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="4f05f-223">Выводит более подробную документацию из Интернета для команды.</span><span class="sxs-lookup"><span data-stu-id="4f05f-223">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="4f05f-224">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="4f05f-224">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="4f05f-225">Переносит допустимый проект предварительной версии 2 в проект пакета SDK .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="4f05f-225">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="4f05f-226">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="4f05f-226">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="4f05f-227">Обеспечивает доступ к командной строке MSBuild.</span><span class="sxs-lookup"><span data-stu-id="4f05f-227">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="4f05f-228">dotnet new</span><span class="sxs-lookup"><span data-stu-id="4f05f-228">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="4f05f-229">Инициализирует проект C# или F# для заданного шаблона.</span><span class="sxs-lookup"><span data-stu-id="4f05f-229">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="4f05f-230">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="4f05f-230">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="4f05f-231">Создает пакет NuGet с кодом.</span><span class="sxs-lookup"><span data-stu-id="4f05f-231">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="4f05f-232">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="4f05f-232">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="4f05f-233">Публикует платформозависимое или автономное приложение .NET.</span><span class="sxs-lookup"><span data-stu-id="4f05f-233">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="4f05f-234">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="4f05f-234">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="4f05f-235">Восстанавливает зависимости для данного приложения.</span><span class="sxs-lookup"><span data-stu-id="4f05f-235">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="4f05f-236">dotnet run</span><span class="sxs-lookup"><span data-stu-id="4f05f-236">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="4f05f-237">Запускает приложение из источника.</span><span class="sxs-lookup"><span data-stu-id="4f05f-237">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="4f05f-238">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="4f05f-238">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="4f05f-239">Параметры для добавления, удаления и перечисления проектов в файле решения.</span><span class="sxs-lookup"><span data-stu-id="4f05f-239">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="4f05f-240">dotnet store</span><span class="sxs-lookup"><span data-stu-id="4f05f-240">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="4f05f-241">Сохраняет сборки в хранилище пакетов среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4f05f-241">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="4f05f-242">dotnet test</span><span class="sxs-lookup"><span data-stu-id="4f05f-242">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="4f05f-243">Выполняет тесты с помощью средства запуска тестов.</span><span class="sxs-lookup"><span data-stu-id="4f05f-243">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4f05f-244">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4f05f-244">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="4f05f-245">Команда</span><span class="sxs-lookup"><span data-stu-id="4f05f-245">Command</span></span>                             | <span data-ttu-id="4f05f-246">Функция</span><span class="sxs-lookup"><span data-stu-id="4f05f-246">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="4f05f-247">dotnet build</span><span class="sxs-lookup"><span data-stu-id="4f05f-247">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="4f05f-248">Выполняет сборку приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4f05f-248">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="4f05f-249">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="4f05f-249">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="4f05f-250">Очищает выходные данные сборки.</span><span class="sxs-lookup"><span data-stu-id="4f05f-250">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="4f05f-251">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="4f05f-251">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="4f05f-252">Переносит допустимый проект предварительной версии 2 в проект пакета SDK .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="4f05f-252">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="4f05f-253">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="4f05f-253">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="4f05f-254">Обеспечивает доступ к командной строке MSBuild.</span><span class="sxs-lookup"><span data-stu-id="4f05f-254">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="4f05f-255">dotnet new</span><span class="sxs-lookup"><span data-stu-id="4f05f-255">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="4f05f-256">Инициализирует проект C# или F# для заданного шаблона.</span><span class="sxs-lookup"><span data-stu-id="4f05f-256">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="4f05f-257">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="4f05f-257">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="4f05f-258">Создает пакет NuGet с кодом.</span><span class="sxs-lookup"><span data-stu-id="4f05f-258">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="4f05f-259">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="4f05f-259">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="4f05f-260">Публикует платформозависимое или автономное приложение .NET.</span><span class="sxs-lookup"><span data-stu-id="4f05f-260">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="4f05f-261">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="4f05f-261">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="4f05f-262">Восстанавливает зависимости для данного приложения.</span><span class="sxs-lookup"><span data-stu-id="4f05f-262">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="4f05f-263">dotnet run</span><span class="sxs-lookup"><span data-stu-id="4f05f-263">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="4f05f-264">Запускает приложение из источника.</span><span class="sxs-lookup"><span data-stu-id="4f05f-264">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="4f05f-265">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="4f05f-265">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="4f05f-266">Параметры для добавления, удаления и перечисления проектов в файле решения.</span><span class="sxs-lookup"><span data-stu-id="4f05f-266">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="4f05f-267">dotnet test</span><span class="sxs-lookup"><span data-stu-id="4f05f-267">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="4f05f-268">Выполняет тесты с помощью средства запуска тестов.</span><span class="sxs-lookup"><span data-stu-id="4f05f-268">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="4f05f-269">Ссылки на проекты</span><span class="sxs-lookup"><span data-stu-id="4f05f-269">Project references</span></span>

<span data-ttu-id="4f05f-270">Команда</span><span class="sxs-lookup"><span data-stu-id="4f05f-270">Command</span></span> | <span data-ttu-id="4f05f-271">Функция</span><span class="sxs-lookup"><span data-stu-id="4f05f-271">Function</span></span>
--- | ---
[<span data-ttu-id="4f05f-272">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="4f05f-272">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="4f05f-273">Добавляет ссылку на проект.</span><span class="sxs-lookup"><span data-stu-id="4f05f-273">Adds a project reference.</span></span>
[<span data-ttu-id="4f05f-274">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="4f05f-274">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="4f05f-275">Перечисляет ссылки на проекты.</span><span class="sxs-lookup"><span data-stu-id="4f05f-275">Lists project references.</span></span>
[<span data-ttu-id="4f05f-276">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="4f05f-276">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="4f05f-277">Удаляет ссылку на проект.</span><span class="sxs-lookup"><span data-stu-id="4f05f-277">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="4f05f-278">Пакеты NuGet</span><span class="sxs-lookup"><span data-stu-id="4f05f-278">NuGet packages</span></span>

<span data-ttu-id="4f05f-279">Команда</span><span class="sxs-lookup"><span data-stu-id="4f05f-279">Command</span></span> | <span data-ttu-id="4f05f-280">Функция</span><span class="sxs-lookup"><span data-stu-id="4f05f-280">Function</span></span>
--- | ---
[<span data-ttu-id="4f05f-281">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="4f05f-281">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="4f05f-282">Добавляет пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="4f05f-282">Adds a NuGet package.</span></span>
[<span data-ttu-id="4f05f-283">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="4f05f-283">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="4f05f-284">Удаляет пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="4f05f-284">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="4f05f-285">Команды NuGet</span><span class="sxs-lookup"><span data-stu-id="4f05f-285">NuGet commands</span></span>

<span data-ttu-id="4f05f-286">Команда</span><span class="sxs-lookup"><span data-stu-id="4f05f-286">Command</span></span> | <span data-ttu-id="4f05f-287">Функция</span><span class="sxs-lookup"><span data-stu-id="4f05f-287">Function</span></span>
--- | ---
[<span data-ttu-id="4f05f-288">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="4f05f-288">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="4f05f-289">Удаляет пакет с сервера или из списка.</span><span class="sxs-lookup"><span data-stu-id="4f05f-289">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="4f05f-290">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="4f05f-290">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="4f05f-291">Очищает или перечисляет локальные ресурсы NuGet в кэше HTTP-запросов, временном кэше или папке пакетов, используемой на уровне компьютера.</span><span class="sxs-lookup"><span data-stu-id="4f05f-291">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="4f05f-292">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="4f05f-292">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="4f05f-293">Отправляет пакет на сервер и публикует его.</span><span class="sxs-lookup"><span data-stu-id="4f05f-293">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="4f05f-294">Команды глобальных средств</span><span class="sxs-lookup"><span data-stu-id="4f05f-294">Global Tools commands</span></span>

<span data-ttu-id="4f05f-295">[Глобальные средства .NET Core](global-tools.md) появились в пакете SDK для .NET Core, начиная с версии 2.1.300:</span><span class="sxs-lookup"><span data-stu-id="4f05f-295">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="4f05f-296">Команда</span><span class="sxs-lookup"><span data-stu-id="4f05f-296">Command</span></span> | <span data-ttu-id="4f05f-297">Функция</span><span class="sxs-lookup"><span data-stu-id="4f05f-297">Function</span></span>
--- | ---
[<span data-ttu-id="4f05f-298">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="4f05f-298">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="4f05f-299">Устанавливает глобальное средство на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="4f05f-299">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="4f05f-300">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="4f05f-300">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="4f05f-301">Перечисляет выводит все глобальные средства, установленные на компьютере в каталоге по умолчанию или по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="4f05f-301">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="4f05f-302">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="4f05f-302">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="4f05f-303">Удаляет глобальное средство с компьютера.</span><span class="sxs-lookup"><span data-stu-id="4f05f-303">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="4f05f-304">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="4f05f-304">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="4f05f-305">Обновляет глобальное средство на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="4f05f-305">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="4f05f-306">Дополнительные средства</span><span class="sxs-lookup"><span data-stu-id="4f05f-306">Additional tools</span></span>

<span data-ttu-id="4f05f-307">Ряд средств, которые ранее были доступны только для отдельных проектов через `DotnetCliToolReference`, стали частью пакета SDK для .NET начиная с версии 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="4f05f-307">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="4f05f-308">Эти средства перечислены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="4f05f-308">These tools are listed in the following table:</span></span>

| <span data-ttu-id="4f05f-309">Средство</span><span class="sxs-lookup"><span data-stu-id="4f05f-309">Tool</span></span>                                              | <span data-ttu-id="4f05f-310">Функция</span><span class="sxs-lookup"><span data-stu-id="4f05f-310">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="4f05f-311">dev-certs</span><span class="sxs-lookup"><span data-stu-id="4f05f-311">dev-certs</span></span>                                         | <span data-ttu-id="4f05f-312">Создает сертификаты разработки и управляет ими.</span><span class="sxs-lookup"><span data-stu-id="4f05f-312">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="4f05f-313">ef</span><span class="sxs-lookup"><span data-stu-id="4f05f-313">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="4f05f-314">Средства командной строки для Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="4f05f-314">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="4f05f-315">sql-cache</span><span class="sxs-lookup"><span data-stu-id="4f05f-315">sql-cache</span></span>                                         | <span data-ttu-id="4f05f-316">Средства командной строки для кэша SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4f05f-316">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="4f05f-317">user-secrets</span><span class="sxs-lookup"><span data-stu-id="4f05f-317">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="4f05f-318">Управляет секретами пользователей для разработки.</span><span class="sxs-lookup"><span data-stu-id="4f05f-318">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="4f05f-319">watch</span><span class="sxs-lookup"><span data-stu-id="4f05f-319">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="4f05f-320">Запускает наблюдатель за файлами, который выполняет команду при изменении файлов.</span><span class="sxs-lookup"><span data-stu-id="4f05f-320">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="4f05f-321">Дополнительные сведения о каждом средстве можно получить с помощью команды `dotnet <tool-name> --help`.</span><span class="sxs-lookup"><span data-stu-id="4f05f-321">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="4f05f-322">Примеры</span><span class="sxs-lookup"><span data-stu-id="4f05f-322">Examples</span></span>

<span data-ttu-id="4f05f-323">Создание проекта консольного приложения .NET Core:</span><span class="sxs-lookup"><span data-stu-id="4f05f-323">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="4f05f-324">Восстановление зависимостей для данного приложения:</span><span class="sxs-lookup"><span data-stu-id="4f05f-324">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="4f05f-325">Сборка проекта и его зависимостей в указанном каталоге:</span><span class="sxs-lookup"><span data-stu-id="4f05f-325">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="4f05f-326">Запустите библиотеку DLL приложения, например `myapp.dll`:</span><span class="sxs-lookup"><span data-stu-id="4f05f-326">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="4f05f-327">Переменные среды</span><span class="sxs-lookup"><span data-stu-id="4f05f-327">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="4f05f-328">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="4f05f-328">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="4f05f-329">Папка глобальных пакетов.</span><span class="sxs-lookup"><span data-stu-id="4f05f-329">The global packages folder.</span></span> <span data-ttu-id="4f05f-330">Если значение не задано, то по умолчанию в Unix используется `~/.nuget/packages`, а в Windows — `%userprofile%\.nuget\packages`.</span><span class="sxs-lookup"><span data-stu-id="4f05f-330">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="4f05f-331">Задает расположение служебного индекса, который будет использоваться общим узлом при загрузке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4f05f-331">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="4f05f-332">Указывает, собираются ли данные по использованию средств .NET Core для отправки в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4f05f-332">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="4f05f-333">Установите значение `true`, чтобы отказаться от функций телеметрии (поддерживаются значения `true`, `1` или `yes`).</span><span class="sxs-lookup"><span data-stu-id="4f05f-333">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="4f05f-334">Также можно установить значение `false`, чтобы согласиться на функции телеметрии (поддерживаются значения `false`, `0` или `no`).</span><span class="sxs-lookup"><span data-stu-id="4f05f-334">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="4f05f-335">Если значение не задано, то по умолчанию используется `false`, то есть функция телеметрии включена.</span><span class="sxs-lookup"><span data-stu-id="4f05f-335">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="4f05f-336">Указывает, разрешается ли из глобального расположения среда выполнения .NET Core, общая платформа или пакет SDK.</span><span class="sxs-lookup"><span data-stu-id="4f05f-336">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="4f05f-337">Если не задано, используется значение по умолчанию `true`.</span><span class="sxs-lookup"><span data-stu-id="4f05f-337">If not set, it defaults to `true`.</span></span> <span data-ttu-id="4f05f-338">Задайте значение `false`, чтобы не разрешать эти сущности из глобального расположения и использовать изолированные установки .NET Core (принимаются значения `0` или `false`).</span><span class="sxs-lookup"><span data-stu-id="4f05f-338">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="4f05f-339">Дополнительные сведения о многоуровневом поиске см. в разделе [Многоуровневый поиск SharedFX](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span><span class="sxs-lookup"><span data-stu-id="4f05f-339">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="4f05f-340">Отключает накат дополнительных версий, если установлено `0`.</span><span class="sxs-lookup"><span data-stu-id="4f05f-340">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="4f05f-341">Дополнительные сведения о накате можно найти в [этой статье](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="4f05f-341">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="4f05f-342">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="4f05f-342">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="4f05f-343">Основной кэш пакетов.</span><span class="sxs-lookup"><span data-stu-id="4f05f-343">The primary package cache.</span></span> <span data-ttu-id="4f05f-344">Если значение не задано, то по умолчанию в Unix используется `$HOME/.nuget/packages`, а в Windows — `%userprofile%\.nuget\packages`.</span><span class="sxs-lookup"><span data-stu-id="4f05f-344">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="4f05f-345">Задает расположение служебного индекса, который будет использоваться общим узлом при загрузке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4f05f-345">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="4f05f-346">Указывает, собираются ли данные по использованию средств .NET Core для отправки в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4f05f-346">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="4f05f-347">Установите значение `true`, чтобы отказаться от функций телеметрии (поддерживаются значения `true`, `1` или `yes`).</span><span class="sxs-lookup"><span data-stu-id="4f05f-347">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="4f05f-348">Также можно установить значение `false`, чтобы согласиться на функции телеметрии (поддерживаются значения `false`, `0` или `no`).</span><span class="sxs-lookup"><span data-stu-id="4f05f-348">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="4f05f-349">Если значение не задано, то по умолчанию используется `false`, то есть функция телеметрии включена.</span><span class="sxs-lookup"><span data-stu-id="4f05f-349">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="4f05f-350">Указывает, разрешается ли из глобального расположения среда выполнения .NET Core, общая платформа или пакет SDK.</span><span class="sxs-lookup"><span data-stu-id="4f05f-350">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="4f05f-351">Если не задано, используется значение по умолчанию `true`.</span><span class="sxs-lookup"><span data-stu-id="4f05f-351">If not set, it defaults to `true`.</span></span> <span data-ttu-id="4f05f-352">Задайте значение `false`, чтобы не разрешать эти сущности из глобального расположения и использовать изолированные установки .NET Core (принимаются значения `0` или `false`).</span><span class="sxs-lookup"><span data-stu-id="4f05f-352">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="4f05f-353">Дополнительные сведения о многоуровневом поиске см. в разделе [Многоуровневый поиск SharedFX](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span><span class="sxs-lookup"><span data-stu-id="4f05f-353">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4f05f-354">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4f05f-354">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="4f05f-355">Основной кэш пакетов.</span><span class="sxs-lookup"><span data-stu-id="4f05f-355">The primary package cache.</span></span> <span data-ttu-id="4f05f-356">Если значение не задано, то по умолчанию в Unix используется `$HOME/.nuget/packages`, а в Windows — `%userprofile%\.nuget\packages`.</span><span class="sxs-lookup"><span data-stu-id="4f05f-356">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="4f05f-357">Задает расположение служебного индекса, который будет использоваться общим узлом при загрузке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4f05f-357">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="4f05f-358">Указывает, собираются ли данные по использованию средств .NET Core для отправки в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4f05f-358">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="4f05f-359">Установите значение `true`, чтобы отказаться от функций телеметрии (поддерживаются значения `true`, `1` или `yes`).</span><span class="sxs-lookup"><span data-stu-id="4f05f-359">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="4f05f-360">Также можно установить значение `false`, чтобы согласиться на функции телеметрии (поддерживаются значения `false`, `0` или `no`).</span><span class="sxs-lookup"><span data-stu-id="4f05f-360">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="4f05f-361">Если значение не задано, то по умолчанию используется `false`, то есть функция телеметрии включена.</span><span class="sxs-lookup"><span data-stu-id="4f05f-361">If not set, the default is `false` and the telemetry feature is active.</span></span>

---

## <a name="see-also"></a><span data-ttu-id="4f05f-362">См. также</span><span class="sxs-lookup"><span data-stu-id="4f05f-362">See also</span></span>

- [<span data-ttu-id="4f05f-363">Файлы конфигурации среды выполнения</span><span class="sxs-lookup"><span data-stu-id="4f05f-363">Runtime Configuration Files</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
- [<span data-ttu-id="4f05f-364">Параметры конфигурации среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="4f05f-364">.NET Core run-time configuration settings</span></span>](../run-time-config/index.md)
