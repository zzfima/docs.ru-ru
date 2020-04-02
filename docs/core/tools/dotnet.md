---
title: Команда dotnet
description: Узнайте о команде dotnet (универсальном драйвере для CLI .NET Core) и о том, как ее использовать.
ms.date: 02/13/2020
ms.openlocfilehash: 8692d419afd528bf49e1dc7dc1a7a5fd698b363b
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134075"
---
# <a name="dotnet-command"></a><span data-ttu-id="5c561-103">Команда dotnet</span><span class="sxs-lookup"><span data-stu-id="5c561-103">dotnet command</span></span>

<span data-ttu-id="5c561-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="5c561-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="5c561-105">name</span><span class="sxs-lookup"><span data-stu-id="5c561-105">Name</span></span>

<span data-ttu-id="5c561-106">`dotnet` — универсальный драйвер для интерфейса командной строки .NET Core (CLI).</span><span class="sxs-lookup"><span data-stu-id="5c561-106">`dotnet` - The generic driver for the .NET Core CLI.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5c561-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="5c561-107">Synopsis</span></span>

<span data-ttu-id="5c561-108">Чтобы получить сведения о среде и доступных командах, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5c561-108">To get information about the available commands and the environment:</span></span>

```dotnetcli
dotnet [-h|--help] [--version] [--info]
    [--list-runtimes] [--list-sdks]
```

<span data-ttu-id="5c561-109">Выполнение команды (требуется установка пакета SDK):</span><span class="sxs-lookup"><span data-stu-id="5c561-109">To run a command (requires SDK installation):</span></span>

```dotnetcli
dotnet <COMMAND> [-d|--diagnostics] [-h|--help] [--verbosity]
    [command-options] [arguments]
```

<span data-ttu-id="5c561-110">Запуск приложения:</span><span class="sxs-lookup"><span data-stu-id="5c561-110">To run an application:</span></span>

```dotnetcli
dotnet [--additionalprobingpath] [--additional-deps]
    [--fx-version]  [--roll-forward]
    <PATH_TO_APPLICATION> [arguments]

dotnet exec [--additionalprobingpath] [--additional-deps]
    [--fx-version]  [--roll-forward]
    <PATH_TO_APPLICATION> [arguments]
```

<span data-ttu-id="5c561-111">Команда `--roll-forward` доступна, начиная с версии .NET Core 3.x.</span><span class="sxs-lookup"><span data-stu-id="5c561-111">`--roll-forward` is available since .NET Core 3.x.</span></span> <span data-ttu-id="5c561-112">Для .NET Core 2.x следует использовать `--roll-forward-on-no-candidate-fx`.</span><span class="sxs-lookup"><span data-stu-id="5c561-112">Use `--roll-forward-on-no-candidate-fx` for .NET Core 2.x.</span></span>

## <a name="description"></a><span data-ttu-id="5c561-113">Описание</span><span class="sxs-lookup"><span data-stu-id="5c561-113">Description</span></span>

<span data-ttu-id="5c561-114">Команда `dotnet` выполняет две функции:</span><span class="sxs-lookup"><span data-stu-id="5c561-114">The `dotnet` command has two functions:</span></span>

- <span data-ttu-id="5c561-115">Она предоставляет команды для работы с проектами .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5c561-115">It provides commands for working with .NET Core projects.</span></span>

  <span data-ttu-id="5c561-116">Например, команда [`dotnet build`](dotnet-build.md) выполняет построение проекта.</span><span class="sxs-lookup"><span data-stu-id="5c561-116">For example, [`dotnet build`](dotnet-build.md) builds a project.</span></span> <span data-ttu-id="5c561-117">Каждая команда определяет свои параметры и аргументы.</span><span class="sxs-lookup"><span data-stu-id="5c561-117">Each command defines its own options and arguments.</span></span> <span data-ttu-id="5c561-118">Все команды поддерживают параметр `--help`, позволяющий вывести краткую справку по их использованию.</span><span class="sxs-lookup"><span data-stu-id="5c561-118">All commands support the `--help` option for printing out brief documentation about how to use the command.</span></span>

- <span data-ttu-id="5c561-119">Запускает приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5c561-119">It runs .NET Core applications.</span></span>

  <span data-ttu-id="5c561-120">Для запуска приложения необходимо указать путь к его файлу `.dll`.</span><span class="sxs-lookup"><span data-stu-id="5c561-120">You specify the path to an application `.dll` file to run the application.</span></span> <span data-ttu-id="5c561-121">Например, команда `dotnet myapp.dll` запускает приложение `myapp`.</span><span class="sxs-lookup"><span data-stu-id="5c561-121">For example, `dotnet myapp.dll` runs the `myapp` application.</span></span> <span data-ttu-id="5c561-122">Дополнительные сведения о параметрах развертывания см. в статье [Развертывание приложений .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="5c561-122">See [.NET Core application deployment](../deploying/index.md) to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="5c561-123">Параметры</span><span class="sxs-lookup"><span data-stu-id="5c561-123">Options</span></span>

<span data-ttu-id="5c561-124">Доступны параметры для `dotnet`, для выполнения команды, а также для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="5c561-124">Different options are available for `dotnet` by itself, for running a command, and for running an application.</span></span>

### <a name="options-for-dotnet-by-itself"></a><span data-ttu-id="5c561-125">Параметры для dotnet</span><span class="sxs-lookup"><span data-stu-id="5c561-125">Options for dotnet by itself</span></span>

<span data-ttu-id="5c561-126">Для `dotnet` доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="5c561-126">The following options are for `dotnet` by itself.</span></span> <span data-ttu-id="5c561-127">Например, `dotnet --info`.</span><span class="sxs-lookup"><span data-stu-id="5c561-127">For example, `dotnet --info`.</span></span> <span data-ttu-id="5c561-128">Выводит сведения о среде.</span><span class="sxs-lookup"><span data-stu-id="5c561-128">They print out information about the environment.</span></span>

- **`--info`**

  <span data-ttu-id="5c561-129">Выводит подробные сведения об установке .NET Core и среде компьютера, например текущую операционную систему и фиксацию SHA версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5c561-129">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

- **`--version`**

  <span data-ttu-id="5c561-130">Выводит версию используемого пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5c561-130">Prints out the version of the .NET Core SDK in use.</span></span>

- **`--list-runtimes`**

  <span data-ttu-id="5c561-131">Выводит список установленных сред выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5c561-131">Prints out a list of the installed .NET Core runtimes.</span></span>

- **`--list-sdks`**

  <span data-ttu-id="5c561-132">Выводит список установленных пакетов SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5c561-132">Prints out a list of the installed .NET Core SDKs.</span></span>

- **`-h|--help`**

  <span data-ttu-id="5c561-133">Выводит список доступных команд.</span><span class="sxs-lookup"><span data-stu-id="5c561-133">Prints out a list of available commands.</span></span>

### <a name="sdk-options-for-running-a-command"></a><span data-ttu-id="5c561-134">Параметры пакета SDK для выполнения команды</span><span class="sxs-lookup"><span data-stu-id="5c561-134">SDK options for running a command</span></span>

<span data-ttu-id="5c561-135">Для `dotnet` с командой доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="5c561-135">The following options are for `dotnet` with a command.</span></span> <span data-ttu-id="5c561-136">Например, `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="5c561-136">For example, `dotnet build --help`.</span></span>

- **`-d|--diagnostics`**

  <span data-ttu-id="5c561-137">Включает вывод диагностических данных.</span><span class="sxs-lookup"><span data-stu-id="5c561-137">Enables diagnostic output.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="5c561-138">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="5c561-138">Sets the verbosity level of the command.</span></span> <span data-ttu-id="5c561-139">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="5c561-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="5c561-140">Поддерживается не во всех командах.</span><span class="sxs-lookup"><span data-stu-id="5c561-140">Not supported in every command.</span></span> <span data-ttu-id="5c561-141">Дополнительные сведения см. на странице соответствующей команды.</span><span class="sxs-lookup"><span data-stu-id="5c561-141">See specific command page to determine if this option is available.</span></span>

- **`-h|--help`**

  <span data-ttu-id="5c561-142">Выводит на экран документацию для определенной команды, например `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="5c561-142">Prints out documentation for a given command, such as `dotnet build --help`.</span></span>

- **`command options`**

  <span data-ttu-id="5c561-143">Для каждой команды определяются относящиеся к ней параметры.</span><span class="sxs-lookup"><span data-stu-id="5c561-143">Each command defines options specific to that command.</span></span> <span data-ttu-id="5c561-144">Список доступных для команды параметров можно просмотреть на соответствующей ей странице.</span><span class="sxs-lookup"><span data-stu-id="5c561-144">See specific command page for a list of available options.</span></span>

### <a name="runtime-options"></a><span data-ttu-id="5c561-145">Параметры среды выполнения</span><span class="sxs-lookup"><span data-stu-id="5c561-145">Runtime options</span></span>

<span data-ttu-id="5c561-146">При запуске приложения в `dotnet` доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="5c561-146">The following options are available when `dotnet` runs an application.</span></span> <span data-ttu-id="5c561-147">Например, `dotnet myapp.dll --fx-version 3.1.1`.</span><span class="sxs-lookup"><span data-stu-id="5c561-147">For example, `dotnet myapp.dll --fx-version 3.1.1`.</span></span>

- **`--additionalprobingpath <PATH>`**

  <span data-ttu-id="5c561-148">Путь, содержащий политику проверки и проверяемые сборки.</span><span class="sxs-lookup"><span data-stu-id="5c561-148">Path containing probing policy and assemblies to probe.</span></span>

- **`--additional-deps <PATH>`**

  <span data-ttu-id="5c561-149">Путь к дополнительному файлу *.deps.json*.</span><span class="sxs-lookup"><span data-stu-id="5c561-149">Path to an additional *.deps.json* file.</span></span> <span data-ttu-id="5c561-150">Файл *deps.json* содержит список зависимостей, зависимости компиляции и сведения о версии, используемые для устранения конфликтов сборок.</span><span class="sxs-lookup"><span data-stu-id="5c561-150">A *deps.json* file contains a list of dependencies, compilation dependencies, and version information used to address assembly conflicts.</span></span> <span data-ttu-id="5c561-151">Дополнительные сведения см. в разделе [Файлы конфигурации среды выполнения](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) на GitHub.</span><span class="sxs-lookup"><span data-stu-id="5c561-151">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

- **`--fx-version <VERSION>`**

  <span data-ttu-id="5c561-152">Версия среды выполнения .NET Core, используемой для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="5c561-152">Version of the .NET Core runtime to use to run the application.</span></span>

- **`--runtimeconfig`**

  <span data-ttu-id="5c561-153">Путь к файлу *runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="5c561-153">Path to a *runtimeconfig.json* file.</span></span> <span data-ttu-id="5c561-154">Файл *runtimeconfig.json* представляет собой файл конфигурации, содержащий параметры среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="5c561-154">A *runtimeconfig.json* file is a configuration file that contains run-time settings.</span></span> <span data-ttu-id="5c561-155">Дополнительные сведения см. в статье [Параметры конфигурации среды выполнения .NET Core](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="5c561-155">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

- <span data-ttu-id="5c561-156">**`--roll-forward-on-no-candidate-fx <N>`** **Доступно в пакете SDK для .NET Core 2.x.**</span><span class="sxs-lookup"><span data-stu-id="5c561-156">**`--roll-forward-on-no-candidate-fx <N>`** **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="5c561-157">Определяет поведение, когда требуемая общая платформа недоступна.</span><span class="sxs-lookup"><span data-stu-id="5c561-157">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="5c561-158">Параметр `N` может принимать следующие значения:</span><span class="sxs-lookup"><span data-stu-id="5c561-158">`N` can be:</span></span>

  - <span data-ttu-id="5c561-159">`0` — отключает увеличение дополнительных версий.</span><span class="sxs-lookup"><span data-stu-id="5c561-159">`0` - Disable even minor version roll forward.</span></span>
  - <span data-ttu-id="5c561-160">`1` — позволяет увеличивать дополнительный номер версии, но не основной.</span><span class="sxs-lookup"><span data-stu-id="5c561-160">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="5c561-161">Это поведение установлено по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5c561-161">This is the default behavior.</span></span>
  - <span data-ttu-id="5c561-162">`2` — включает увеличение основных и дополнительных версий.</span><span class="sxs-lookup"><span data-stu-id="5c561-162">`2` - Roll forward on minor and major versions.</span></span>

   <span data-ttu-id="5c561-163">Дополнительные сведения о накате можно найти в [этой статье](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="5c561-163">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

- <span data-ttu-id="5c561-164">**`--roll-forward <SETTING>`** **Доступно, начиная с пакета SDK для .NET Core 3.0.**</span><span class="sxs-lookup"><span data-stu-id="5c561-164">**`--roll-forward <SETTING>`** **Available starting with .NET Core SDK 3.0.**</span></span>

  <span data-ttu-id="5c561-165">Управляет применением наката к приложению.</span><span class="sxs-lookup"><span data-stu-id="5c561-165">Controls how roll forward is applied to the app.</span></span> <span data-ttu-id="5c561-166">`SETTING` может иметь одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="5c561-166">The `SETTING` can be one of the following values.</span></span> <span data-ttu-id="5c561-167">Если тип не указан, по умолчанию используется вариант `Minor`.</span><span class="sxs-lookup"><span data-stu-id="5c561-167">If not specified, `Minor` is the default.</span></span>

  - <span data-ttu-id="5c561-168">`LatestPatch` — накат до версии с наибольшим номером исправления.</span><span class="sxs-lookup"><span data-stu-id="5c561-168">`LatestPatch` - Roll forward to the highest patch version.</span></span> <span data-ttu-id="5c561-169">Отключает накат дополнительных версий.</span><span class="sxs-lookup"><span data-stu-id="5c561-169">This disables minor version roll forward.</span></span>
  - <span data-ttu-id="5c561-170">`Minor` — накат до дополнительной версии со следующим по порядку возрастания номером, если запрошенная дополнительная версия отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5c561-170">`Minor` - Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="5c561-171">Если запрошенная дополнительная версия присутствует, используется политика LatestPatch.</span><span class="sxs-lookup"><span data-stu-id="5c561-171">If the requested minor version is present, then the LatestPatch policy is used.</span></span>
  - <span data-ttu-id="5c561-172">`Major` — накат до основной версии со следующим по порядку возрастания или дополнительной версии с наименьшим номером, если запрошенная дополнительная версия отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5c561-172">`Major` - Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="5c561-173">Если запрошенная основная версия присутствует, используется политика Minor.</span><span class="sxs-lookup"><span data-stu-id="5c561-173">If the requested major version is present, then the Minor policy is used.</span></span>
  - <span data-ttu-id="5c561-174">`LatestMinor` — накат до дополнительной версии с наибольшим номером, даже если запрошенная дополнительная версия присутствует.</span><span class="sxs-lookup"><span data-stu-id="5c561-174">`LatestMinor` - Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="5c561-175">Предназначен для сценариев размещения компонентов.</span><span class="sxs-lookup"><span data-stu-id="5c561-175">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="5c561-176">`LatestMajor` — накат до основной версии с наибольшим номером и дополнительной версии с наибольшим номером, даже если запрошенная основная версия присутствует.</span><span class="sxs-lookup"><span data-stu-id="5c561-176">`LatestMajor` - Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="5c561-177">Предназначен для сценариев размещения компонентов.</span><span class="sxs-lookup"><span data-stu-id="5c561-177">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="5c561-178">`Disable` — накат не выполняется.</span><span class="sxs-lookup"><span data-stu-id="5c561-178">`Disable` - Don't roll forward.</span></span> <span data-ttu-id="5c561-179">Привязка только к указанной версии.</span><span class="sxs-lookup"><span data-stu-id="5c561-179">Only bind to specified version.</span></span> <span data-ttu-id="5c561-180">Эта политика не рекомендуется для общего использования, поскольку отключает возможность наката до последних исправлений.</span><span class="sxs-lookup"><span data-stu-id="5c561-180">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="5c561-181">Это значение рекомендуется использовать только для тестирования.</span><span class="sxs-lookup"><span data-stu-id="5c561-181">This value is only recommended for testing.</span></span>

<span data-ttu-id="5c561-182">Все параметры, кроме параметра `Disable`, будут использовать версию с последним доступным исправлением.</span><span class="sxs-lookup"><span data-stu-id="5c561-182">With the exception of `Disable`, all settings will use the highest available patch version.</span></span>

<span data-ttu-id="5c561-183">Поведение наката также можно настроить в свойствах файла проекта, файла конфигурации среды выполнения и переменной среды.</span><span class="sxs-lookup"><span data-stu-id="5c561-183">Roll forward behavior can also be configured in a project file property, a run-time configuration file property, and an environment variable.</span></span> <span data-ttu-id="5c561-184">Дополнительные сведения см. в разделе [Накат основной версии среды выполнения](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span><span class="sxs-lookup"><span data-stu-id="5c561-184">For more information, see [Major-version runtime roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span></span>

## <a name="dotnet-commands"></a><span data-ttu-id="5c561-185">Команды dotnet</span><span class="sxs-lookup"><span data-stu-id="5c561-185">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="5c561-186">Общее</span><span class="sxs-lookup"><span data-stu-id="5c561-186">General</span></span>

| <span data-ttu-id="5c561-187">Команда</span><span class="sxs-lookup"><span data-stu-id="5c561-187">Command</span></span>                                       | <span data-ttu-id="5c561-188">Функция</span><span class="sxs-lookup"><span data-stu-id="5c561-188">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="5c561-189">dotnet build</span><span class="sxs-lookup"><span data-stu-id="5c561-189">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="5c561-190">Выполняет сборку приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5c561-190">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="5c561-191">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="5c561-191">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="5c561-192">Взаимодействует с серверами, запущенными сборкой.</span><span class="sxs-lookup"><span data-stu-id="5c561-192">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="5c561-193">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="5c561-193">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="5c561-194">Очищает выходные данные сборки.</span><span class="sxs-lookup"><span data-stu-id="5c561-194">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="5c561-195">dotnet help</span><span class="sxs-lookup"><span data-stu-id="5c561-195">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="5c561-196">Выводит более подробную документацию из Интернета для команды.</span><span class="sxs-lookup"><span data-stu-id="5c561-196">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="5c561-197">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="5c561-197">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="5c561-198">Переносит допустимый проект предварительной версии 2 в проект пакета SDK .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="5c561-198">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="5c561-199">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="5c561-199">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="5c561-200">Обеспечивает доступ к командной строке MSBuild.</span><span class="sxs-lookup"><span data-stu-id="5c561-200">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="5c561-201">dotnet new</span><span class="sxs-lookup"><span data-stu-id="5c561-201">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="5c561-202">Инициализирует проект C# или F# для заданного шаблона.</span><span class="sxs-lookup"><span data-stu-id="5c561-202">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="5c561-203">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="5c561-203">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="5c561-204">Создает пакет NuGet с кодом.</span><span class="sxs-lookup"><span data-stu-id="5c561-204">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="5c561-205">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="5c561-205">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="5c561-206">Публикует платформозависимое или автономное приложение .NET.</span><span class="sxs-lookup"><span data-stu-id="5c561-206">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="5c561-207">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="5c561-207">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="5c561-208">Восстанавливает зависимости для данного приложения.</span><span class="sxs-lookup"><span data-stu-id="5c561-208">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="5c561-209">dotnet run</span><span class="sxs-lookup"><span data-stu-id="5c561-209">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="5c561-210">Запускает приложение из источника.</span><span class="sxs-lookup"><span data-stu-id="5c561-210">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="5c561-211">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="5c561-211">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="5c561-212">Параметры для добавления, удаления и перечисления проектов в файле решения.</span><span class="sxs-lookup"><span data-stu-id="5c561-212">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="5c561-213">dotnet store</span><span class="sxs-lookup"><span data-stu-id="5c561-213">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="5c561-214">Сохраняет сборки в хранилище пакетов среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="5c561-214">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="5c561-215">dotnet test</span><span class="sxs-lookup"><span data-stu-id="5c561-215">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="5c561-216">Выполняет тесты с помощью средства запуска тестов.</span><span class="sxs-lookup"><span data-stu-id="5c561-216">Runs tests using a test runner.</span></span>                                     |

### <a name="project-references"></a><span data-ttu-id="5c561-217">Ссылки на проекты</span><span class="sxs-lookup"><span data-stu-id="5c561-217">Project references</span></span>

<span data-ttu-id="5c561-218">Команда</span><span class="sxs-lookup"><span data-stu-id="5c561-218">Command</span></span> | <span data-ttu-id="5c561-219">Функция</span><span class="sxs-lookup"><span data-stu-id="5c561-219">Function</span></span>
--- | ---
[<span data-ttu-id="5c561-220">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="5c561-220">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="5c561-221">Добавляет ссылку на проект.</span><span class="sxs-lookup"><span data-stu-id="5c561-221">Adds a project reference.</span></span>
[<span data-ttu-id="5c561-222">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="5c561-222">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="5c561-223">Перечисляет ссылки на проекты.</span><span class="sxs-lookup"><span data-stu-id="5c561-223">Lists project references.</span></span>
[<span data-ttu-id="5c561-224">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="5c561-224">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="5c561-225">Удаляет ссылку на проект.</span><span class="sxs-lookup"><span data-stu-id="5c561-225">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="5c561-226">Пакеты NuGet</span><span class="sxs-lookup"><span data-stu-id="5c561-226">NuGet packages</span></span>

<span data-ttu-id="5c561-227">Команда</span><span class="sxs-lookup"><span data-stu-id="5c561-227">Command</span></span> | <span data-ttu-id="5c561-228">Функция</span><span class="sxs-lookup"><span data-stu-id="5c561-228">Function</span></span>
--- | ---
[<span data-ttu-id="5c561-229">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="5c561-229">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="5c561-230">Добавляет пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="5c561-230">Adds a NuGet package.</span></span>
[<span data-ttu-id="5c561-231">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="5c561-231">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="5c561-232">Удаляет пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="5c561-232">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="5c561-233">Команды NuGet</span><span class="sxs-lookup"><span data-stu-id="5c561-233">NuGet commands</span></span>

<span data-ttu-id="5c561-234">Команда</span><span class="sxs-lookup"><span data-stu-id="5c561-234">Command</span></span> | <span data-ttu-id="5c561-235">Функция</span><span class="sxs-lookup"><span data-stu-id="5c561-235">Function</span></span>
--- | ---
[<span data-ttu-id="5c561-236">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="5c561-236">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="5c561-237">Удаляет пакет с сервера или из списка.</span><span class="sxs-lookup"><span data-stu-id="5c561-237">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="5c561-238">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="5c561-238">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="5c561-239">Отправляет пакет на сервер и публикует его.</span><span class="sxs-lookup"><span data-stu-id="5c561-239">Pushes a package to the server and publishes it.</span></span>
[<span data-ttu-id="5c561-240">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="5c561-240">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="5c561-241">Очищает или перечисляет локальные ресурсы NuGet в кэше HTTP-запросов, временном кэше или папке пакетов, используемой на уровне компьютера.</span><span class="sxs-lookup"><span data-stu-id="5c561-241">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="5c561-242">dotnet nuget add source</span><span class="sxs-lookup"><span data-stu-id="5c561-242">dotnet nuget add source</span></span>](dotnet-nuget-add-source.md) | <span data-ttu-id="5c561-243">Добавляет источник NuGet.</span><span class="sxs-lookup"><span data-stu-id="5c561-243">Adds a NuGet source.</span></span>
[<span data-ttu-id="5c561-244">dotnet nuget disable source</span><span class="sxs-lookup"><span data-stu-id="5c561-244">dotnet nuget disable source</span></span>](dotnet-nuget-disable-source.md) | <span data-ttu-id="5c561-245">Отключает источник NuGet.</span><span class="sxs-lookup"><span data-stu-id="5c561-245">Disables a NuGet source.</span></span>
[<span data-ttu-id="5c561-246">dotnet nuget enable source</span><span class="sxs-lookup"><span data-stu-id="5c561-246">dotnet nuget enable source</span></span>](dotnet-nuget-enable-source.md) | <span data-ttu-id="5c561-247">Включает источник NuGet.</span><span class="sxs-lookup"><span data-stu-id="5c561-247">Enables a NuGet source.</span></span>
[<span data-ttu-id="5c561-248">dotnet nuget list source</span><span class="sxs-lookup"><span data-stu-id="5c561-248">dotnet nuget list source</span></span>](dotnet-nuget-list-source.md) | <span data-ttu-id="5c561-249">Перечисляет все настроенные источники NuGet.</span><span class="sxs-lookup"><span data-stu-id="5c561-249">Lists all configured NuGet sources.</span></span>
[<span data-ttu-id="5c561-250">dotnet nuget remove source</span><span class="sxs-lookup"><span data-stu-id="5c561-250">dotnet nuget remove source</span></span>](dotnet-nuget-remove-source.md) | <span data-ttu-id="5c561-251">Удаляет источник NuGet.</span><span class="sxs-lookup"><span data-stu-id="5c561-251">Removes a NuGet source.</span></span>
[<span data-ttu-id="5c561-252">dotnet nuget update source</span><span class="sxs-lookup"><span data-stu-id="5c561-252">dotnet nuget update source</span></span>](dotnet-nuget-update-source.md) | <span data-ttu-id="5c561-253">Обновляет источник NuGet.</span><span class="sxs-lookup"><span data-stu-id="5c561-253">Updates a NuGet source.</span></span>

### <a name="global-tool-path-and-local-tools-commands"></a><span data-ttu-id="5c561-254">Команды глобального, установочного и локального средства</span><span class="sxs-lookup"><span data-stu-id="5c561-254">Global, tool-path, and local tools commands</span></span>

<span data-ttu-id="5c561-255">Средства — это консольные приложения, которые устанавливаются из пакетов NuGet и вызываются из командной строки.</span><span class="sxs-lookup"><span data-stu-id="5c561-255">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="5c561-256">Вы можете писать средства самостоятельно или устанавливать средства, написанные другими.</span><span class="sxs-lookup"><span data-stu-id="5c561-256">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="5c561-257">Средства также называются глобальными средствами, средствами пути к средству и локальными средствами.</span><span class="sxs-lookup"><span data-stu-id="5c561-257">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="5c561-258">Дополнительные сведения см. в [обзоре средств .NET Core](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5c561-258">For more information, see [.NET Core tools overview](global-tools.md).</span></span> <span data-ttu-id="5c561-259">Глобальные и установочные средства доступны, начиная с версии пакета SDK .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="5c561-259">Global and tool-path tools are available starting with .NET Core SDK 2.1.</span></span> <span data-ttu-id="5c561-260">Локальные средства доступны в пакете SDK для .NET Core, начиная с версии 3.0.</span><span class="sxs-lookup"><span data-stu-id="5c561-260">Local tools are available starting with .NET Core SDK 3.0.</span></span>

<span data-ttu-id="5c561-261">Команда</span><span class="sxs-lookup"><span data-stu-id="5c561-261">Command</span></span> | <span data-ttu-id="5c561-262">Функция</span><span class="sxs-lookup"><span data-stu-id="5c561-262">Function</span></span>
--- | ---
[<span data-ttu-id="5c561-263">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="5c561-263">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="5c561-264">Устанавливает средство на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5c561-264">Installs a tool on your machine.</span></span>
[<span data-ttu-id="5c561-265">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="5c561-265">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="5c561-266">Выводит все глобальные, установочные и локальные средства, установленные на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5c561-266">Lists all global, tool-path, or local tools currently installed on your machine.</span></span>
[<span data-ttu-id="5c561-267">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="5c561-267">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="5c561-268">Удаляет средство с компьютера.</span><span class="sxs-lookup"><span data-stu-id="5c561-268">Uninstalls a tool from your machine.</span></span>
[<span data-ttu-id="5c561-269">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="5c561-269">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="5c561-270">Обновляет средство, установленное на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5c561-270">Updates a tool that is installed on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="5c561-271">Дополнительные средства</span><span class="sxs-lookup"><span data-stu-id="5c561-271">Additional tools</span></span>

<span data-ttu-id="5c561-272">Ряд средств, которые ранее были доступны только для отдельных проектов через `DotnetCliToolReference`, стали частью пакета SDK для .NET начиная с версии 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="5c561-272">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="5c561-273">Эти средства перечислены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="5c561-273">These tools are listed in the following table:</span></span>

| <span data-ttu-id="5c561-274">Средство</span><span class="sxs-lookup"><span data-stu-id="5c561-274">Tool</span></span>                                              | <span data-ttu-id="5c561-275">Функция</span><span class="sxs-lookup"><span data-stu-id="5c561-275">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="5c561-276">dev-certs</span><span class="sxs-lookup"><span data-stu-id="5c561-276">dev-certs</span></span>                                         | <span data-ttu-id="5c561-277">Создает сертификаты разработки и управляет ими.</span><span class="sxs-lookup"><span data-stu-id="5c561-277">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="5c561-278">ef</span><span class="sxs-lookup"><span data-stu-id="5c561-278">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="5c561-279">Средства командной строки для Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="5c561-279">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="5c561-280">sql-cache</span><span class="sxs-lookup"><span data-stu-id="5c561-280">sql-cache</span></span>                                         | <span data-ttu-id="5c561-281">Средства командной строки для кэша SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5c561-281">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="5c561-282">user-secrets</span><span class="sxs-lookup"><span data-stu-id="5c561-282">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="5c561-283">Управляет секретами пользователей для разработки.</span><span class="sxs-lookup"><span data-stu-id="5c561-283">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="5c561-284">watch</span><span class="sxs-lookup"><span data-stu-id="5c561-284">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="5c561-285">Запускает наблюдатель за файлами, который выполняет команду при изменении файлов.</span><span class="sxs-lookup"><span data-stu-id="5c561-285">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="5c561-286">Дополнительные сведения о каждом средстве можно получить с помощью команды `dotnet <tool-name> --help`.</span><span class="sxs-lookup"><span data-stu-id="5c561-286">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="5c561-287">Примеры</span><span class="sxs-lookup"><span data-stu-id="5c561-287">Examples</span></span>

<span data-ttu-id="5c561-288">Создание консольного приложения .NET Core:</span><span class="sxs-lookup"><span data-stu-id="5c561-288">Create a new .NET Core console application:</span></span>

```dotnetcli
dotnet new console
```

<span data-ttu-id="5c561-289">Сборка проекта и его зависимостей в указанном каталоге:</span><span class="sxs-lookup"><span data-stu-id="5c561-289">Build a project and its dependencies in a given directory:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="5c561-290">Запуск приложения:</span><span class="sxs-lookup"><span data-stu-id="5c561-290">Run an application:</span></span>

```dotnetcli
dotnet myapp.dll
```

## <a name="environment-variables"></a><span data-ttu-id="5c561-291">Переменные среды</span><span class="sxs-lookup"><span data-stu-id="5c561-291">Environment variables</span></span>

- <span data-ttu-id="5c561-292">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span><span class="sxs-lookup"><span data-stu-id="5c561-292">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span></span>

  <span data-ttu-id="5c561-293">Указывает расположение сред выполнения .NET Core, если оно отличается от задаваемого по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5c561-293">Specifies the location of the .NET Core runtimes, if they are not installed in the default location.</span></span> <span data-ttu-id="5c561-294">В ОС Windows по умолчанию используется расположение `C:\Program Files\dotnet`.</span><span class="sxs-lookup"><span data-stu-id="5c561-294">The default location on Windows is `C:\Program Files\dotnet`.</span></span> <span data-ttu-id="5c561-295">В ОС Linux и macOS по умолчанию используется расположение `/usr/share/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="5c561-295">The default location on Linux and macOS is `/usr/share/dotnet`.</span></span> <span data-ttu-id="5c561-296">Эта переменная среды используется только при запуске приложений с помощью созданных исполняемых файлов (apphost).</span><span class="sxs-lookup"><span data-stu-id="5c561-296">This environment variable is used only when running apps via generated executables (apphosts).</span></span> <span data-ttu-id="5c561-297">При запуске 32-разрядного исполняемого файла в 64-разрядной ОС вместо нее используется `DOTNET_ROOT(x86)`.</span><span class="sxs-lookup"><span data-stu-id="5c561-297">`DOTNET_ROOT(x86)` is used instead when running a 32-bit executable on a 64-bit OS.</span></span>

- `DOTNET_PACKAGES`

  <span data-ttu-id="5c561-298">Папка глобальных пакетов.</span><span class="sxs-lookup"><span data-stu-id="5c561-298">The global packages folder.</span></span> <span data-ttu-id="5c561-299">Если значение не задано, то по умолчанию в Unix используется `~/.nuget/packages`, а в Windows — `%userprofile%\.nuget\packages`.</span><span class="sxs-lookup"><span data-stu-id="5c561-299">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

- `DOTNET_SERVICING`

  <span data-ttu-id="5c561-300">Задает расположение служебного индекса, который будет использоваться общим узлом при загрузке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="5c561-300">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

- `DOTNET_NOLOGO`

  <span data-ttu-id="5c561-301">Указывает, отображаются ли сообщения приветствия и данные телеметрии .NET Core при первом запуске.</span><span class="sxs-lookup"><span data-stu-id="5c561-301">Specifies whether .NET Core welcome and telemetry messages are displayed on first run.</span></span> <span data-ttu-id="5c561-302">Установите значение `true` для отключения звука этих сообщений (принимаются значения `true`, `1` или `yes`) или установите значение `false` для разрешения звука (принимаются значения `false`, `0` или `no`).</span><span class="sxs-lookup"><span data-stu-id="5c561-302">Set to `true` to mute these messages (values `true`, `1`, or `yes` accepted) or set to `false` to allow (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="5c561-303">Если не задано, по умолчанию используется `false` и при первом запуске будут отображаться сообщения.</span><span class="sxs-lookup"><span data-stu-id="5c561-303">If not set, the default is `false` and the messages will be displayed on first run.</span></span> <span data-ttu-id="5c561-304">Обратите внимание, что этот флаг не влияет на данные телеметрии (см. `DOTNET_CLI_TELEMETRY_OPTOUT`, чтобы отменить отправку телеметрии).</span><span class="sxs-lookup"><span data-stu-id="5c561-304">Note that this flag has no effect on telemetry (see `DOTNET_CLI_TELEMETRY_OPTOUT` for opting out of sending telemetry).</span></span>

- `DOTNET_CLI_TELEMETRY_OPTOUT`

  <span data-ttu-id="5c561-305">Указывает, собираются ли данные по использованию средств .NET Core для отправки в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5c561-305">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="5c561-306">Установите значение `true`, чтобы отказаться от функций телеметрии (поддерживаются значения `true`, `1` или `yes`).</span><span class="sxs-lookup"><span data-stu-id="5c561-306">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="5c561-307">Также можно установить значение `false`, чтобы согласиться на функции телеметрии (поддерживаются значения `false`, `0` или `no`).</span><span class="sxs-lookup"><span data-stu-id="5c561-307">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="5c561-308">Если значение не задано, то по умолчанию используется `false`, то есть функция телеметрии включена.</span><span class="sxs-lookup"><span data-stu-id="5c561-308">If not set, the default is `false` and the telemetry feature is active.</span></span>

- `DOTNET_MULTILEVEL_LOOKUP`

  <span data-ttu-id="5c561-309">Указывает, разрешается ли из глобального расположения среда выполнения .NET Core, общая платформа или пакет SDK.</span><span class="sxs-lookup"><span data-stu-id="5c561-309">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="5c561-310">Если не задано, используется значение по умолчанию 1 (логическое значение `true`).</span><span class="sxs-lookup"><span data-stu-id="5c561-310">If not set, it defaults to 1 (logical `true`).</span></span> <span data-ttu-id="5c561-311">Задайте значение 0 (логическое значение `false`), чтобы не разрешать эти сущности из глобального расположения и использовать изолированные установки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5c561-311">Set to 0 (logical `false`) to not resolve from the global location and have isolated .NET Core installations.</span></span> <span data-ttu-id="5c561-312">Дополнительные сведения о многоуровневом поиске см. в разделе [Многоуровневый поиск SharedFX](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span><span class="sxs-lookup"><span data-stu-id="5c561-312">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

- <span data-ttu-id="5c561-313">`DOTNET_ROLL_FORWARD` **Доступно, начиная с пакета SDK для .NET Core 3.x.**</span><span class="sxs-lookup"><span data-stu-id="5c561-313">`DOTNET_ROLL_FORWARD` **Available starting with .NET Core 3.x SDK.**</span></span>

  <span data-ttu-id="5c561-314">Определяет поведение наката.</span><span class="sxs-lookup"><span data-stu-id="5c561-314">Determines roll forward behavior.</span></span> <span data-ttu-id="5c561-315">Дополнительные сведения см. в описании параметра `--roll-forward`, приведенном выше в этой статье.</span><span class="sxs-lookup"><span data-stu-id="5c561-315">For more information, see the `--roll-forward` option earlier in this article.</span></span>

- <span data-ttu-id="5c561-316">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **Доступно в пакете SDK для .NET Core 2.x.**</span><span class="sxs-lookup"><span data-stu-id="5c561-316">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="5c561-317">Отключает накат дополнительных версий, если установлено `0`.</span><span class="sxs-lookup"><span data-stu-id="5c561-317">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="5c561-318">Дополнительные сведения о накате можно найти в [этой статье](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="5c561-318">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

- `DOTNET_CLI_UI_LANGUAGE`

  <span data-ttu-id="5c561-319">Задает язык пользовательского интерфейса CLI с помощью значения языкового стандарта, например `en-us`.</span><span class="sxs-lookup"><span data-stu-id="5c561-319">Sets the language of the CLI UI using a locale value such as `en-us`.</span></span> <span data-ttu-id="5c561-320">Поддерживаются те же значения, что и для Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5c561-320">The supported values are the same as for Visual Studio.</span></span> <span data-ttu-id="5c561-321">Дополнительные сведения см. в разделе, посвященном изменению языка установщика, в [документации по установке Visual Studio](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019).</span><span class="sxs-lookup"><span data-stu-id="5c561-321">For more information, see the section on changing the installer language in the [Visual Studio installation documentation](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019).</span></span> <span data-ttu-id="5c561-322">Применяются правила диспетчера ресурсов .NET, в связи с чем вам не нужно выбирать точное соответствие &mdash; можно также выбрать потомков в дереве `CultureInfo`.</span><span class="sxs-lookup"><span data-stu-id="5c561-322">The .NET resource manager rules apply, so you don't have to pick an exact match&mdash;you can also pick descendants in the `CultureInfo` tree.</span></span> <span data-ttu-id="5c561-323">Например, если задать значение `fr-CA`, интерфейс командной строки будет находить и использовать переводы `fr`.</span><span class="sxs-lookup"><span data-stu-id="5c561-323">For example, if you set it to `fr-CA`, the CLI will find and use the `fr` translations.</span></span> <span data-ttu-id="5c561-324">Если задать язык, который не поддерживается, для интерфейса командной строки будет использоваться английский язык.</span><span class="sxs-lookup"><span data-stu-id="5c561-324">If you set it to a language that is not supported, the CLI falls back to English.</span></span>

- `DOTNET_DISABLE_GUI_ERRORS`

  <span data-ttu-id="5c561-325">Для создаваемых исполняемых файлов с поддержкой графического пользовательского интерфейса отключает всплывающее диалоговое окно, которое обычно выводится для определенных классов ошибок.</span><span class="sxs-lookup"><span data-stu-id="5c561-325">For GUI-enabled generated executables - disables dialog popup, which normally shows for certain classes of errors.</span></span> <span data-ttu-id="5c561-326">В таких случаях выполняются только запись в `stderr` и выход.</span><span class="sxs-lookup"><span data-stu-id="5c561-326">It only writes to `stderr` and exits in those cases.</span></span>
  
- `DOTNET_ADDITIONAL_DEPS`

  <span data-ttu-id="5c561-327">Эквивалентно параметру `--additional-deps` интерфейса командной строки.</span><span class="sxs-lookup"><span data-stu-id="5c561-327">Equivalent to CLI option `--additional-deps`.</span></span>

- `DOTNET_RUNTIME_ID`

  <span data-ttu-id="5c561-328">Переопределяет обнаруженный RID.</span><span class="sxs-lookup"><span data-stu-id="5c561-328">Overrides the detected RID.</span></span>

- `DOTNET_SHARED_STORE`

  <span data-ttu-id="5c561-329">Расположение общего хранилища, которое в некоторых случаях используется для разрешения сборки.</span><span class="sxs-lookup"><span data-stu-id="5c561-329">Location of the "shared store" which assembly resolution falls back to in some cases.</span></span>

- `DOTNET_STARTUP_HOOKS`

  <span data-ttu-id="5c561-330">Список сборок, из которого осуществляется загрузка и выполнение перехватчиков запуска.</span><span class="sxs-lookup"><span data-stu-id="5c561-330">List of assemblies to load and execute startup hooks from.</span></span>

- <span data-ttu-id="5c561-331">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span><span class="sxs-lookup"><span data-stu-id="5c561-331">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span></span>

  <span data-ttu-id="5c561-332">Управляет диагностической трассировкой из компонентов размещения, таких как `dotnet.exe`, `hostfxr` и `hostpolicy`.</span><span class="sxs-lookup"><span data-stu-id="5c561-332">Controls diagnostics tracing from the hosting components, such as `dotnet.exe`, `hostfxr`, and `hostpolicy`.</span></span>

## <a name="see-also"></a><span data-ttu-id="5c561-333">См. также</span><span class="sxs-lookup"><span data-stu-id="5c561-333">See also</span></span>

- [<span data-ttu-id="5c561-334">Файлы конфигурации среды выполнения</span><span class="sxs-lookup"><span data-stu-id="5c561-334">Runtime Configuration Files</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
- [<span data-ttu-id="5c561-335">Параметры конфигурации среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="5c561-335">.NET Core run-time configuration settings</span></span>](../run-time-config/index.md)
