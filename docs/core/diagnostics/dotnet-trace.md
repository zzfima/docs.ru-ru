---
title: Программа dotnet-trace — .NET Core
description: Установка и использование программы командной строки dotnet-trace.
ms.date: 11/21/2019
ms.openlocfilehash: b19b159636fbf57fa2d461b398fcf9234aab491c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737639"
---
# <a name="dotnet-trace-performance-analysis-utility"></a><span data-ttu-id="bbb9e-103">Программа анализа производительности dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="bbb9e-103">dotnet-trace performance analysis utility</span></span>

<span data-ttu-id="bbb9e-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 3.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="bbb9e-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install-dotnet-trace"></a><span data-ttu-id="bbb9e-105">Установка dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="bbb9e-105">Install dotnet-trace</span></span>

<span data-ttu-id="bbb9e-106">Установите [пакет NuGet](https://www.nuget.org/packages/dotnet-trace) `dotnet-trace` с помощью команды [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="bbb9e-106">Install `dotnet-trace` [NuGet package](https://www.nuget.org/packages/dotnet-trace) with the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-trace
```

## <a name="synopsis"></a><span data-ttu-id="bbb9e-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="bbb9e-107">Synopsis</span></span>

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="bbb9e-108">Описание</span><span class="sxs-lookup"><span data-stu-id="bbb9e-108">Description</span></span>

<span data-ttu-id="bbb9e-109">Программа `dotnet-trace` —</span><span class="sxs-lookup"><span data-stu-id="bbb9e-109">The `dotnet-trace` tool:</span></span>

* <span data-ttu-id="bbb9e-110">это кроссплатформенное средство .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-110">Is a cross-platform .NET Core tool.</span></span>
* <span data-ttu-id="bbb9e-111">Выполняет сбор трассировок .NET Core для запущенного процесса без встроенного профилировщика.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-111">Enables the collection of .NET Core traces of a running process without a native profiler.</span></span>
* <span data-ttu-id="bbb9e-112">Создано на основе кроссплатформенной технологии `EventPipe` для среды выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-112">Is built around the cross-platform `EventPipe` technology of the .NET Core runtime.</span></span>
* <span data-ttu-id="bbb9e-113">Предоставляет одинаковые возможности в Windows, Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-113">Delivers the same experience on Windows, Linux, or macOS.</span></span>

## <a name="options"></a><span data-ttu-id="bbb9e-114">Параметры</span><span class="sxs-lookup"><span data-stu-id="bbb9e-114">Options</span></span>

- **`--version`**

  <span data-ttu-id="bbb9e-115">Отображение версии служебной программы dotnet-counters.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-115">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="bbb9e-116">Отображение справки в командной строке.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-116">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="bbb9e-117">Команды</span><span class="sxs-lookup"><span data-stu-id="bbb9e-117">Commands</span></span>

| <span data-ttu-id="bbb9e-118">Команда</span><span class="sxs-lookup"><span data-stu-id="bbb9e-118">Command</span></span>                                                     |
| ----------------------------------------------------------- |
| [<span data-ttu-id="bbb9e-119">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="bbb9e-119">dotnet-trace collect</span></span>](#dotnet-trace-collect)               |
| [<span data-ttu-id="bbb9e-120">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="bbb9e-120">dotnet-trace convert</span></span>](#dotnet-trace-convert)               |
| [<span data-ttu-id="bbb9e-121">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="bbb9e-121">dotnet-trace ps</span></span>](#dotnet-trace-ps) |
| [<span data-ttu-id="bbb9e-122">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="bbb9e-122">dotnet-trace list-profiles</span></span>](#dotnet-trace-list-profiles)   |

## <a name="dotnet-trace-collect"></a><span data-ttu-id="bbb9e-123">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="bbb9e-123">dotnet-trace collect</span></span>

<span data-ttu-id="bbb9e-124">Собирает диагностическую трассировку для выполняющегося процесса.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-124">Collects a diagnostic trace from a running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="bbb9e-125">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="bbb9e-125">Synopsis</span></span>

```console
dotnet-trace collect [-h|--help] [-p|--process-id] [--buffersize <size>] [-o|--output]
    [--providers] [--profile <profile-name>] [--format]
```

### <a name="options"></a><span data-ttu-id="bbb9e-126">Параметры</span><span class="sxs-lookup"><span data-stu-id="bbb9e-126">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="bbb9e-127">Процесс, для которого нужна трассировка.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-127">The process to collect the trace from.</span></span>

- **`--buffersize <size>`**

  <span data-ttu-id="bbb9e-128">Задает размер кольцевого буфера в памяти (в мегабайтах).</span><span class="sxs-lookup"><span data-stu-id="bbb9e-128">Sets the size of the in-memory circular buffer, in megabytes.</span></span> <span data-ttu-id="bbb9e-129">По умолчанию используется значение 256 МБ.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-129">Default 256 MB.</span></span>

- **`-o|--output <trace-file-path>`**

  <span data-ttu-id="bbb9e-130">Выходной путь для собранных данных трассировки.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-130">The output path for the collected trace data.</span></span> <span data-ttu-id="bbb9e-131">Если это значение не указано, по умолчанию используется `trace.nettrace`.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-131">If not specified it defaults to `trace.nettrace`.</span></span>

- **`--providers <list-of-comma-separated-providers>`**

  <span data-ttu-id="bbb9e-132">Список применяемых поставщиков `EventPipe`, разделенный запятыми.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-132">A comma-separated list of `EventPipe` providers to be enabled.</span></span> <span data-ttu-id="bbb9e-133">Поставщики из этого списка применяются в дополнение к тем, которые подразумеваются в `--profile <profile-name>`.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-133">These providers supplement any providers implied by `--profile <profile-name>`.</span></span> <span data-ttu-id="bbb9e-134">При наличии несогласованности по конкретному поставщику указанная здесь конфигурация имеет приоритет над неявной конфигурацией из профиля.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-134">If there's any inconsistency for a particular provider, this configuration takes precedence over the implicit configuration from the profile.</span></span>

  <span data-ttu-id="bbb9e-135">Список поставщиков предоставляется в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="bbb9e-135">This list of providers is in the form:</span></span>

  - `Provider[,Provider]`
  - <span data-ttu-id="bbb9e-136">`Provider` имеет формат `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`;</span><span class="sxs-lookup"><span data-stu-id="bbb9e-136">`Provider` is in the form: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span></span>
  - <span data-ttu-id="bbb9e-137">`KeyValueArgs` имеет формат `[key1=value1][;key2=value2]`.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-137">`KeyValueArgs` is in the form: `[key1=value1][;key2=value2]`.</span></span>

- **`--profile <profile-name>`**

  <span data-ttu-id="bbb9e-138">Заранее определенный именованный набор конфигураций поставщиков, который позволяет кратко указывать типичные сценарии трассировки.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-138">A named pre-defined set of provider configurations that allows common tracing scenarios to be specified succinctly.</span></span>

- **`--format {NetTrace|Speedscope}`**

  <span data-ttu-id="bbb9e-139">Задает формат выходных данных для преобразования файла трассировки.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-139">Sets the output format for the trace file conversion.</span></span> <span data-ttu-id="bbb9e-140">Значение по умолчанию — `NetTrace`.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-140">The default is `NetTrace`.</span></span>

## <a name="dotnet-trace-convert"></a><span data-ttu-id="bbb9e-141">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="bbb9e-141">dotnet-trace convert</span></span>

<span data-ttu-id="bbb9e-142">Преобразует трассировки `nettrace` в альтернативные форматы для использования с другими средствами анализа трассировок.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-142">Converts `nettrace` traces to alternate formats for use with alternate trace analysis tools.</span></span>

### <a name="synopsis"></a><span data-ttu-id="bbb9e-143">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="bbb9e-143">Synopsis</span></span>

```console
dotnet-trace convert [<input-filename>] [-h|--help] [--format] [-o|--output]
```

### <a name="arguments"></a><span data-ttu-id="bbb9e-144">Аргументы</span><span class="sxs-lookup"><span data-stu-id="bbb9e-144">Arguments</span></span>

- **`<input-filename>`**

  <span data-ttu-id="bbb9e-145">Исходный файл трассировки для преобразования.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-145">Input trace file to be converted.</span></span> <span data-ttu-id="bbb9e-146">По умолчанию используется значение *trace.nettrace*.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-146">Defaults to *trace.nettrace*.</span></span>

### <a name="options"></a><span data-ttu-id="bbb9e-147">Параметры</span><span class="sxs-lookup"><span data-stu-id="bbb9e-147">Options</span></span>

- **`--format <NetTrace|Speedscope>`**

  <span data-ttu-id="bbb9e-148">Задает формат выходных данных для преобразования файла трассировки.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-148">Sets the output format for the trace file conversion.</span></span>

- **`-o|--output <output-filename>`**

  <span data-ttu-id="bbb9e-149">Имя файла выходных данных.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-149">Output filename.</span></span> <span data-ttu-id="bbb9e-150">К нему добавляется расширение целевого формата.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-150">Extension of target format will be added.</span></span>

## <a name="dotnet-trace-ps"></a><span data-ttu-id="bbb9e-151">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="bbb9e-151">dotnet-trace ps</span></span>

<span data-ttu-id="bbb9e-152">Список процессов dotnet, к которым можно присоединиться.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-152">Lists dotnet processes that can be attached to.</span></span>

### <a name="synopsis"></a><span data-ttu-id="bbb9e-153">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="bbb9e-153">Synopsis</span></span>

```console
dotnet-trace ps [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a><span data-ttu-id="bbb9e-154">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="bbb9e-154">dotnet-trace list-profiles</span></span>

<span data-ttu-id="bbb9e-155">Список предварительно созданных профилей трассировки с перечислением поставщиков и фильтров в каждом профиле.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-155">Lists pre-built tracing profiles with a description of what providers and filters are in each profile.</span></span>

### <a name="synopsis"></a><span data-ttu-id="bbb9e-156">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="bbb9e-156">Synopsis</span></span>

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a><span data-ttu-id="bbb9e-157">Сбор трассировки с помощью dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="bbb9e-157">Collect a trace with dotnet-trace</span></span>

<span data-ttu-id="bbb9e-158">Для сбора трассировок с помощью `dotnet-trace` выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-158">To collect traces using `dotnet-trace`:</span></span>

- <span data-ttu-id="bbb9e-159">Получите идентификатор процесса (PID) для трассируемого приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-159">Get the process identifier (PID) of the .NET Core application to collect traces from.</span></span>

  - <span data-ttu-id="bbb9e-160">В Windows его можно получить, например, через диспетчер задач или с помощью команды `tasklist`.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-160">On Windows, you can use Task Manager or the `tasklist` command, for example.</span></span>
  - <span data-ttu-id="bbb9e-161">В Linux можно использовать, например, команду `ps`.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-161">On Linux, for example, the `ps` command.</span></span>
  - [<span data-ttu-id="bbb9e-162">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="bbb9e-162">dotnet-trace ps</span></span>](#dotnet-trace-ps)

- <span data-ttu-id="bbb9e-163">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bbb9e-163">Run the following command:</span></span>

  ```console
  dotnet-trace collect --process-id <PID>
  ```

  <span data-ttu-id="bbb9e-164">Приведенная выше команда создает выходные данные наподобие следующих:</span><span class="sxs-lookup"><span data-stu-id="bbb9e-164">The preceding command generates output similar to the following:</span></span>

  ```console
  Press <Enter> to exit...
  Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
  Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
  ```

- <span data-ttu-id="bbb9e-165">Чтобы остановить сбор, нажмите клавишу `<Enter>`.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-165">Stop collection by pressing the `<Enter>` key.</span></span> <span data-ttu-id="bbb9e-166">`dotnet-trace` завершит запись событий в файл *trace.nettrace*.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-166">`dotnet-trace` will finish logging events to the *trace.nettrace* file.</span></span>

## <a name="view-the-trace-captured-from-dotnet-trace"></a><span data-ttu-id="bbb9e-167">Просмотр трассировки, собранной с помощью dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="bbb9e-167">View the trace captured from dotnet-trace</span></span>

<span data-ttu-id="bbb9e-168">В Windows файлы *NETTRACE* можно просматривать и анализировать в [PerfView](https://github.com/microsoft/perfview). Если трассировка была собрана на другой платформе, ее файл можно переместить на компьютер с Windows для просмотра в PerfView.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-168">On Windows, *.nettrace* files can be viewed on [PerfView](https://github.com/microsoft/perfview) for analysis: For traces collected on other platforms, the trace file can be moved to a Windows machine to be viewed on PerfView.</span></span>

<span data-ttu-id="bbb9e-169">В Linux трассировку можно просмотреть, изменив формат выходных данных с `dotnet-trace` на `speedscope`.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-169">On Linux, the trace can be viewed by changing the output format of `dotnet-trace` to `speedscope`.</span></span> <span data-ttu-id="bbb9e-170">Чтобы изменить формат выходного файла, укажите параметр `-f|--format`. При значении `-f speedscope` программа `dotnet-trace` создаст файл `speedscope`.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-170">The output file format can be changed using the `-f|--format` option - `-f speedscope` will make `dotnet-trace` produce a `speedscope` file.</span></span> <span data-ttu-id="bbb9e-171">Вы можете выбрать варианты `nettrace` (по умолчанию) или `speedscope`.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-171">You can choose between `nettrace` (the default option) and `speedscope`.</span></span> <span data-ttu-id="bbb9e-172">Файлы `Speedscope` можно открывать с помощью <https://www.speedscope.app>.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-172">`Speedscope` files can be opened at <https://www.speedscope.app>.</span></span>

> [!NOTE]
> <span data-ttu-id="bbb9e-173">Среда выполнения .NET Core создает трассировки в формате `nettrace`.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-173">The .NET Core runtime generates traces in the `nettrace` format.</span></span> <span data-ttu-id="bbb9e-174">В формат speedscope (если требуется) они преобразуются уже после завершения трассировки.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-174">The traces are converted to speedscope (if specified) after the trace is completed.</span></span> <span data-ttu-id="bbb9e-175">Так как некоторые преобразования приводят к потере данных, исходный файл `nettrace` сохраняется рядом с преобразованным файлом.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-175">Since some conversions may result in loss of data, the original `nettrace` file is preserved next to the converted file.</span></span>

## <a name="use-dotnet-trace-to-collect-counter-values-over-time"></a><span data-ttu-id="bbb9e-176">Использование dotnet-trace для получения значений счетчиков за период времени</span><span class="sxs-lookup"><span data-stu-id="bbb9e-176">Use dotnet-trace to collect counter values over time</span></span>

<span data-ttu-id="bbb9e-177">Программа `dotnet-trace` позволяет выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="bbb9e-177">`dotnet-trace` can:</span></span>

* <span data-ttu-id="bbb9e-178">использовать `EventCounter` для простого мониторинга работоспособности в средах с высокой чувствительностью к производительности,</span><span class="sxs-lookup"><span data-stu-id="bbb9e-178">Use `EventCounter` for basic health monitoring in performance-sensitive environments.</span></span> <span data-ttu-id="bbb9e-179">например рабочих;</span><span class="sxs-lookup"><span data-stu-id="bbb9e-179">For example, in production.</span></span>
* <span data-ttu-id="bbb9e-180">собирать трассировки, чтобы их не нужно было просматривать в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-180">Collect traces so they don't need to be viewed in real time.</span></span>

<span data-ttu-id="bbb9e-181">Например, если вам нужны значения счетчика производительности из среды выполнения, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bbb9e-181">For example, to collect runtime performance counter values, use the following command:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

<span data-ttu-id="bbb9e-182">Эта команда означает, что счетчики среды выполнения будут отслеживаться каждую секунду, то есть реализует не требовательную к ресурсам схему мониторинга работоспособности.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-182">The preceding command tells the runtime counters to report once every second for lightweight health monitoring.</span></span> <span data-ttu-id="bbb9e-183">Заменив `EventCounterIntervalSec=1` большим значением (например, 60), вы получите трассировку данных счетчиков меньшего объема и с меньшим уровнем детализации.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-183">Replacing `EventCounterIntervalSec=1` with a higher value (for example, 60) allows collection of a smaller trace with less granularity in the counter data.</span></span>

<span data-ttu-id="bbb9e-184">Следующая команда сокращает накладные расходы и размер трассировки сильнее, чем предыдущая:</span><span class="sxs-lookup"><span data-stu-id="bbb9e-184">The following command reduces overhead and trace size more than the preceding one:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

<span data-ttu-id="bbb9e-185">Эта команда отключает события среды выполнения и профилировщик управляемого стека.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-185">The preceding command disables runtime events and the managed stack profiler.</span></span>

## <a name="net-providers"></a><span data-ttu-id="bbb9e-186">Поставщики .NET</span><span class="sxs-lookup"><span data-stu-id="bbb9e-186">.NET Providers</span></span>

<span data-ttu-id="bbb9e-187">Среда выполнения .NET Core поддерживает следующие поставщики .NET.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-187">The .NET Core runtime supports the following .NET providers.</span></span> <span data-ttu-id="bbb9e-188">.NET Core использует одинаковые ключевые слова для включения трассировок `Event Tracing for Windows (ETW)` и `EventPipe`.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-188">.NET Core uses the same keywords to enable both `Event Tracing for Windows (ETW)` and `EventPipe` traces.</span></span>

| <span data-ttu-id="bbb9e-189">Имя поставщика</span><span class="sxs-lookup"><span data-stu-id="bbb9e-189">Provider name</span></span>                            | <span data-ttu-id="bbb9e-190">Сведения</span><span class="sxs-lookup"><span data-stu-id="bbb9e-190">Information</span></span> |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [<span data-ttu-id="bbb9e-191">Поставщик среды выполнения</span><span class="sxs-lookup"><span data-stu-id="bbb9e-191">The Runtime Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[<span data-ttu-id="bbb9e-192">Ключевые слова среды выполнения CLR</span><span class="sxs-lookup"><span data-stu-id="bbb9e-192">CLR Runtime Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [<span data-ttu-id="bbb9e-193">Поставщик очистки</span><span class="sxs-lookup"><span data-stu-id="bbb9e-193">The Rundown Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[<span data-ttu-id="bbb9e-194">Ключевые слова очистки CLR</span><span class="sxs-lookup"><span data-stu-id="bbb9e-194">CLR Rundown Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | <span data-ttu-id="bbb9e-195">Включает пример профилировщика.</span><span class="sxs-lookup"><span data-stu-id="bbb9e-195">Enables the sample profiler.</span></span> |
