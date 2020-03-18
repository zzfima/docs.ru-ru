---
title: dotnet-counters (.NET Core)
description: Сведения о том, как установить и использовать программу командной строки dotnet-counter.
ms.date: 02/26/2020
ms.openlocfilehash: dc95297478784ca06fe442a939f8489a40b29da7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147182"
---
# <a name="dotnet-counters"></a><span data-ttu-id="7068d-103">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="7068d-103">dotnet-counters</span></span>

<span data-ttu-id="7068d-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 3.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="7068d-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install-dotnet-counters"></a><span data-ttu-id="7068d-105">Установка dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="7068d-105">Install dotnet-counters</span></span>

<span data-ttu-id="7068d-106">Чтобы установить последнюю версию [пакета NuGet](https://www.nuget.org/packages/dotnet-counters) `dotnet-counters`, используйте команду [dotnet tool install](../tools/dotnet-tool-install.md).</span><span class="sxs-lookup"><span data-stu-id="7068d-106">To install the latest release version of the `dotnet-counters` [NuGet package](https://www.nuget.org/packages/dotnet-counters), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-counters
```

## <a name="synopsis"></a><span data-ttu-id="7068d-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="7068d-107">Synopsis</span></span>

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="7068d-108">Описание</span><span class="sxs-lookup"><span data-stu-id="7068d-108">Description</span></span>

<span data-ttu-id="7068d-109">`dotnet-counters` — это средство мониторинга производительности и первого уровня анализа производительности.</span><span class="sxs-lookup"><span data-stu-id="7068d-109">`dotnet-counters` is a performance monitoring tool for ad-hoc health monitoring and first-level performance investigation.</span></span> <span data-ttu-id="7068d-110">Оно умеет отслеживать значения счетчиков производительности, опубликованные через API <xref:System.Diagnostics.Tracing.EventCounter>.</span><span class="sxs-lookup"><span data-stu-id="7068d-110">It can observe performance counter values that are published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="7068d-111">Например, вы можете быстро отслеживать такие параметры, как загрузка ЦП или частота возникновения исключений в приложении .NET Core, чтобы обнаружить подозрительное поведение перед началом более серьезных расследований с помощью `PerfView` или `dotnet-trace`.</span><span class="sxs-lookup"><span data-stu-id="7068d-111">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application to see if there's anything suspicious before diving into more serious performance investigation using `PerfView` or `dotnet-trace`.</span></span>

## <a name="options"></a><span data-ttu-id="7068d-112">Параметры</span><span class="sxs-lookup"><span data-stu-id="7068d-112">Options</span></span>

- **`--version`**

  <span data-ttu-id="7068d-113">Отображение версии служебной программы dotnet-counters.</span><span class="sxs-lookup"><span data-stu-id="7068d-113">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="7068d-114">Отображение справки в командной строке.</span><span class="sxs-lookup"><span data-stu-id="7068d-114">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="7068d-115">Команды</span><span class="sxs-lookup"><span data-stu-id="7068d-115">Commands</span></span>

| <span data-ttu-id="7068d-116">Команда</span><span class="sxs-lookup"><span data-stu-id="7068d-116">Command</span></span>                                             |
| --------------------------------------------------- |
| [<span data-ttu-id="7068d-117">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="7068d-117">dotnet-counters collect</span></span>](#dotnet-counters-collect) |
| [<span data-ttu-id="7068d-118">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="7068d-118">dotnet-counters list</span></span>](#dotnet-counters-list)       |
| [<span data-ttu-id="7068d-119">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="7068d-119">dotnet-counters monitor</span></span>](#dotnet-counters-monitor) |
| [<span data-ttu-id="7068d-120">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="7068d-120">dotnet-counters ps</span></span>](#dotnet-counters-ps) |

## <a name="dotnet-counters-collect"></a><span data-ttu-id="7068d-121">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="7068d-121">dotnet-counters collect</span></span>

<span data-ttu-id="7068d-122">Периодический сбор выбранных значений счетчиков и их экспорт в указанном формате файла для последующей обработки.</span><span class="sxs-lookup"><span data-stu-id="7068d-122">Periodically collect selected counter values and export them into a specified file format for post-processing.</span></span>

### <a name="synopsis"></a><span data-ttu-id="7068d-123">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="7068d-123">Synopsis</span></span>

```console
dotnet-counters collect [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list] [--format] [-o|--output]
```

### <a name="options"></a><span data-ttu-id="7068d-124">Параметры</span><span class="sxs-lookup"><span data-stu-id="7068d-124">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="7068d-125">Идентификатор отслеживаемого процесса.</span><span class="sxs-lookup"><span data-stu-id="7068d-125">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="7068d-126">Время (в секундах) между обновлением значений отображаемых счетчиков</span><span class="sxs-lookup"><span data-stu-id="7068d-126">The number of seconds to delay between updating the displayed counters</span></span>

- **`counter_list <COUNTERS>`**

  <span data-ttu-id="7068d-127">Список счетчиков, разделенный пробелами.</span><span class="sxs-lookup"><span data-stu-id="7068d-127">A space separated list of counters.</span></span> <span data-ttu-id="7068d-128">Вы можете объявить счетчики как `provider_name[:counter_name]`.</span><span class="sxs-lookup"><span data-stu-id="7068d-128">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="7068d-129">Если используется `provider_name` без указания `counter_name`, отображаются все счетчики.</span><span class="sxs-lookup"><span data-stu-id="7068d-129">If the `provider_name` is used without a qualifying `counter_name`, then all counters are shown.</span></span> <span data-ttu-id="7068d-130">Для обнаружения имен поставщиков и счетчиков используйте команду [dotnet-counters list](#dotnet-counters-list).</span><span class="sxs-lookup"><span data-stu-id="7068d-130">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

- **`--format <csv|json>`**

  <span data-ttu-id="7068d-131">Экспортируемый формат.</span><span class="sxs-lookup"><span data-stu-id="7068d-131">TThe format to be exported.</span></span> <span data-ttu-id="7068d-132">В настоящее время доступно: csv, json.</span><span class="sxs-lookup"><span data-stu-id="7068d-132">Currently available: csv, json.</span></span>

- **`-o|--output <output>`**

  <span data-ttu-id="7068d-133">Имя выходного файла.</span><span class="sxs-lookup"><span data-stu-id="7068d-133">The name of the output file.</span></span>

### <a name="examples"></a><span data-ttu-id="7068d-134">Примеры</span><span class="sxs-lookup"><span data-stu-id="7068d-134">Examples</span></span>

- <span data-ttu-id="7068d-135">Сбор всех счетчиков с интервалом обновления в 3 секунды и создание CSV-файла в качестве выходных данных:</span><span class="sxs-lookup"><span data-stu-id="7068d-135">Collect all counters at a refresh interval of 3 seconds and generate a csv as output:</span></span>

  ```console
  > dotnet-counters collect --process-id 1902 --refresh-interval 3 --format csv

  counter_list is unspecified. Monitoring all counters by default.
  Starting a counter session. Press Q to quit.
  ```

## <a name="dotnet-counters-list"></a><span data-ttu-id="7068d-136">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="7068d-136">dotnet-counters list</span></span>

<span data-ttu-id="7068d-137">Отображение списка имен и описаний счетчиков, сгруппированных по поставщикам.</span><span class="sxs-lookup"><span data-stu-id="7068d-137">Displays a list of counter names and descriptions, grouped by provider.</span></span>

### <a name="synopsis"></a><span data-ttu-id="7068d-138">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="7068d-138">Synopsis</span></span>

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a><span data-ttu-id="7068d-139">Пример</span><span class="sxs-lookup"><span data-stu-id="7068d-139">Example</span></span>

```console
> dotnet-counters list

    Showing well-known counters only. Specific processes may support additional counters.
    System.Runtime
        cpu-usage                    Amount of time the process has utilized the CPU (ms)
        working-set                  Amount of working set used by the process (MB)
        gc-heap-size                 Total heap size reported by the GC (MB)
        gen-0-gc-count               Number of Gen 0 GCs / sec
        gen-1-gc-count               Number of Gen 1 GCs / sec
        gen-2-gc-count               Number of Gen 2 GCs / sec
        exception-count              Number of Exceptions / sec
```

## <a name="dotnet-counters-monitor"></a><span data-ttu-id="7068d-140">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="7068d-140">dotnet-counters monitor</span></span>

<span data-ttu-id="7068d-141">Отображение периодически обновляемых значений для выбранных счетчиков.</span><span class="sxs-lookup"><span data-stu-id="7068d-141">Displays periodically refreshing values of selected counters.</span></span>

### <a name="synopsis"></a><span data-ttu-id="7068d-142">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="7068d-142">Synopsis</span></span>

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list]
```

### <a name="options"></a><span data-ttu-id="7068d-143">Параметры</span><span class="sxs-lookup"><span data-stu-id="7068d-143">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="7068d-144">Идентификатор отслеживаемого процесса.</span><span class="sxs-lookup"><span data-stu-id="7068d-144">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="7068d-145">Время (в секундах) между обновлением значений отображаемых счетчиков</span><span class="sxs-lookup"><span data-stu-id="7068d-145">The number of seconds to delay between updating the displayed counters</span></span>

- **`counter_list <COUNTERS>`**

  <span data-ttu-id="7068d-146">Список счетчиков, разделенный пробелами.</span><span class="sxs-lookup"><span data-stu-id="7068d-146">A space separated list of counters.</span></span> <span data-ttu-id="7068d-147">Вы можете объявить счетчики как `provider_name[:counter_name]`.</span><span class="sxs-lookup"><span data-stu-id="7068d-147">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="7068d-148">Если используется `provider_name` без указания `counter_name`, отображаются все счетчики.</span><span class="sxs-lookup"><span data-stu-id="7068d-148">If the `provider_name` is used without a qualifying `counter_name`, then all counters are shown.</span></span> <span data-ttu-id="7068d-149">Для обнаружения имен поставщиков и счетчиков используйте команду [dotnet-counters list](#dotnet-counters-list).</span><span class="sxs-lookup"><span data-stu-id="7068d-149">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

### <a name="examples"></a><span data-ttu-id="7068d-150">Примеры</span><span class="sxs-lookup"><span data-stu-id="7068d-150">Examples</span></span>

- <span data-ttu-id="7068d-151">Мониторинг всех счетчиков из `System.Runtime` с интервалом обновления 3 секунды:</span><span class="sxs-lookup"><span data-stu-id="7068d-151">Monitor all counters from `System.Runtime` at a refresh interval of 3 seconds:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902  --refresh-interval 3 System.Runtime

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      Working Set (MB)                            1982
      GC Heap Size (MB)                            811
      Gen 0 GC / second                             20
      Gen 1 GC / second                              4
      Gen 2 GC / second                              1
      Number of Exceptions / sec                     4
  ```

- <span data-ttu-id="7068d-152">Мониторинг только счетчиков использования ЦП и размера кучи GC из `System.Runtime`:</span><span class="sxs-lookup"><span data-stu-id="7068d-152">Monitor just CPU usage and GC heap size from `System.Runtime`:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- <span data-ttu-id="7068d-153">Мониторинг значений `EventCounter` из определяемых пользователем `EventSource`:</span><span class="sxs-lookup"><span data-stu-id="7068d-153">Monitor `EventCounter` values from user-defined `EventSource`.</span></span> <span data-ttu-id="7068d-154">Дополнительные сведения см. в статье [Руководство. How to measure performance for very frequent events using EventCounters](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md) (Как измерять производительность для очень часто выполняемых событий с помощью EventCounters).</span><span class="sxs-lookup"><span data-stu-id="7068d-154">For more information, see [Tutorial: How to measure performance for very frequent events using EventCounters](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md).</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```
  
## <a name="dotnet-counters-ps"></a><span data-ttu-id="7068d-155">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="7068d-155">dotnet-counters ps</span></span>

<span data-ttu-id="7068d-156">Отображение списка процессов dotnet, которые можно отслеживать.</span><span class="sxs-lookup"><span data-stu-id="7068d-156">Display a list of dotnet processes that can be monitored.</span></span>

### <a name="synopsis"></a><span data-ttu-id="7068d-157">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="7068d-157">Synopsis</span></span>

```console
dotnet-counters ps [-h|--help]
```

### <a name="example"></a><span data-ttu-id="7068d-158">Пример</span><span class="sxs-lookup"><span data-stu-id="7068d-158">Example</span></span>

```console
> dotnet-counters ps
  
  15683 WebApi     /home/suwhang/repos/WebApi/WebApi
  16324 dotnet     /usr/local/share/dotnet/dotnet
```
